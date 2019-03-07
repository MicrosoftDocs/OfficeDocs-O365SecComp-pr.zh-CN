---
title: 使用敏感信息类型查找什么
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Office 365 安全&amp;合规中心中的数据丢失防护 (DLP) 包括可供您在 DLP 策略中使用的80敏感信息类型。 本主题列出了所有这些敏感信息类型，并显示 DLP 策略在检测到每种类型时查找的内容。
ms.openlocfilehash: 55fa8b6855a9a5bf2c84f6555dd8c8227a2ad9cf
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "30455264"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="95cb4-104">使用敏感信息类型查找什么</span><span class="sxs-lookup"><span data-stu-id="95cb4-104">What the sensitive information types look for</span></span>

<span data-ttu-id="95cb4-105">Office 365 安全&amp;合规中心中的数据丢失防护 (DLP) 包括许多可供您在 DLP 策略中使用的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="95cb4-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="95cb4-106">本主题列出了所有这些敏感信息类型，并显示 DLP 策略在检测到每种类型时查找的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="95cb4-107">敏感信息类型通过正则表达式或函数可以识别的模式定义。</span><span class="sxs-lookup"><span data-stu-id="95cb4-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="95cb4-108">此外，关键字和校验和等确凿的证据可用于识别敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="95cb4-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="95cb4-109">可信度和相似度也会在评估过程中使用。</span><span class="sxs-lookup"><span data-stu-id="95cb4-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="95cb4-110">ABA 银行代号</span><span class="sxs-lookup"><span data-stu-id="95cb4-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-111">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-111">Format</span></span>

<span data-ttu-id="95cb4-112">9 个数字，可以是格式化模式，也可以是非格式化模式 </span><span class="sxs-lookup"><span data-stu-id="95cb4-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-113">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-113">Pattern</span></span>

<span data-ttu-id="95cb4-114">格式</span><span class="sxs-lookup"><span data-stu-id="95cb4-114">Formatted:</span></span>
- <span data-ttu-id="95cb4-115">四个数字，以 0、 1、 2、 3、 6、 7 或 8 开头</span><span class="sxs-lookup"><span data-stu-id="95cb4-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="95cb4-116">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="95cb4-116">A hyphen</span></span>
- <span data-ttu-id="95cb4-117">四个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-117">Four digits</span></span>
- <span data-ttu-id="95cb4-118">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="95cb4-118">A hyphen</span></span>
- <span data-ttu-id="95cb4-119">一个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-119">A digit</span></span>

<span data-ttu-id="95cb4-120">无格式: 9 个连续的数字, 以0、1、2、3、6、7或8开头</span><span class="sxs-lookup"><span data-stu-id="95cb4-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="95cb4-121">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-121">Checksum</span></span>

<span data-ttu-id="95cb4-122">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-123">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-123">Definition</span></span>

<span data-ttu-id="95cb4-124">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-125">函数 Func_aba_routing 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-126">找到 Keyword_ABA_Routing 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="95cb4-127">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-127">Keywords</span></span>

#### <a name="keywordabarouting"></a><span data-ttu-id="95cb4-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="95cb4-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="95cb4-129">aba</span><span class="sxs-lookup"><span data-stu-id="95cb4-129">aba</span></span>
- <span data-ttu-id="95cb4-130">aba #</span><span class="sxs-lookup"><span data-stu-id="95cb4-130">aba #</span></span>
- <span data-ttu-id="95cb4-131">aba routing #</span><span class="sxs-lookup"><span data-stu-id="95cb4-131">aba routing #</span></span>
- <span data-ttu-id="95cb4-132">aba routing number</span><span class="sxs-lookup"><span data-stu-id="95cb4-132">aba routing number</span></span>
- <span data-ttu-id="95cb4-133">aba</span><span class="sxs-lookup"><span data-stu-id="95cb4-133">aba#</span></span>
- <span data-ttu-id="95cb4-134">abarouting #</span><span class="sxs-lookup"><span data-stu-id="95cb4-134">abarouting#</span></span>
- <span data-ttu-id="95cb4-135">aba number</span><span class="sxs-lookup"><span data-stu-id="95cb4-135">aba number</span></span>
- <span data-ttu-id="95cb4-136">abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="95cb4-136">abaroutingnumber</span></span>
- <span data-ttu-id="95cb4-137">american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="95cb4-137">american bank association routing #</span></span>
- <span data-ttu-id="95cb4-138">american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="95cb4-138">american bank association routing number</span></span>
- <span data-ttu-id="95cb4-139">americanbankassociationrouting #</span><span class="sxs-lookup"><span data-stu-id="95cb4-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="95cb4-140">americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="95cb4-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="95cb4-141">bank routing number</span><span class="sxs-lookup"><span data-stu-id="95cb4-141">bank routing number</span></span>
- <span data-ttu-id="95cb4-142">bankrouting #</span><span class="sxs-lookup"><span data-stu-id="95cb4-142">bankrouting#</span></span>
- <span data-ttu-id="95cb4-143">bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="95cb4-143">bankroutingnumber</span></span>
- <span data-ttu-id="95cb4-144">routing transit number</span><span class="sxs-lookup"><span data-stu-id="95cb4-144">routing transit number</span></span>
- <span data-ttu-id="95cb4-145">RTN</span><span class="sxs-lookup"><span data-stu-id="95cb4-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="95cb4-146">阿根廷国家身份证 (DNI) 号</span><span class="sxs-lookup"><span data-stu-id="95cb4-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-147">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-147">Format</span></span>

<span data-ttu-id="95cb4-148">八个数字，用点分隔</span><span class="sxs-lookup"><span data-stu-id="95cb4-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-149">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-149">Pattern</span></span>

<span data-ttu-id="95cb4-150">八个数字：</span><span class="sxs-lookup"><span data-stu-id="95cb4-150">Eight digits:</span></span>
- <span data-ttu-id="95cb4-151">两个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-151">Two digits</span></span>
- <span data-ttu-id="95cb4-152">一个点 </span><span class="sxs-lookup"><span data-stu-id="95cb4-152">A period</span></span>
- <span data-ttu-id="95cb4-153">三个数字 </span><span class="sxs-lookup"><span data-stu-id="95cb4-153">Three digits</span></span>
- <span data-ttu-id="95cb4-154">一个点 </span><span class="sxs-lookup"><span data-stu-id="95cb4-154">A period</span></span>
- <span data-ttu-id="95cb4-155">三位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-156">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-156">Checksum</span></span>

<span data-ttu-id="95cb4-157">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-158">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-158">Definition</span></span>

<span data-ttu-id="95cb4-159">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-160">正则表达式 Regex_argentina_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-161">找到 Keyword_argentina_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-162">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-162">Keywords</span></span>

#### <a name="keywordargentinanationalid"></a><span data-ttu-id="95cb4-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="95cb4-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="95cb4-164">Argentina National Identity number</span><span class="sxs-lookup"><span data-stu-id="95cb4-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="95cb4-165">标识</span><span class="sxs-lookup"><span data-stu-id="95cb4-165">Identity</span></span> 
- <span data-ttu-id="95cb4-166">标识国家/地区身份卡片</span><span class="sxs-lookup"><span data-stu-id="95cb4-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="95cb4-167">DNI</span><span class="sxs-lookup"><span data-stu-id="95cb4-167">DNI</span></span> 
- <span data-ttu-id="95cb4-168">个人的网络国家注册表</span><span class="sxs-lookup"><span data-stu-id="95cb4-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="95cb4-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="95cb4-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="95cb4-170">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="95cb4-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="95cb4-171">Identidad</span><span class="sxs-lookup"><span data-stu-id="95cb4-171">Identidad</span></span> 
- <span data-ttu-id="95cb4-172">Identificación</span><span class="sxs-lookup"><span data-stu-id="95cb4-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="95cb4-173">澳大利亚银行帐号</span><span class="sxs-lookup"><span data-stu-id="95cb4-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-174">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-174">Format</span></span>

<span data-ttu-id="95cb4-175">6-10 个数字，带或不带 BSB 号码 </span><span class="sxs-lookup"><span data-stu-id="95cb4-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-176">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-176">Pattern</span></span>

<span data-ttu-id="95cb4-177">帐号为 6-10 个数字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="95cb4-178">澳大利亚银行州级分部编号：</span><span class="sxs-lookup"><span data-stu-id="95cb4-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="95cb4-179">三个数字 </span><span class="sxs-lookup"><span data-stu-id="95cb4-179">Three digits</span></span> 
- <span data-ttu-id="95cb4-180">连字符</span><span class="sxs-lookup"><span data-stu-id="95cb4-180">A hyphen</span></span> 
- <span data-ttu-id="95cb4-181">三位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-182">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-182">Checksum</span></span>

<span data-ttu-id="95cb4-183">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-184">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-184">Definition</span></span>

<span data-ttu-id="95cb4-185">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-186">正则表达式 Regex_australia_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="95cb4-187">找到 Keyword_australia_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="95cb4-188">正则表达式 Regex_australia_bank_account_number_bsb 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="95cb4-189">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-190">正则表达式 Regex_australia_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="95cb4-191">找到 Keyword_australia_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

```
<!-- Australia Bank Account Number -->
<Entity id="74a54de9-2a30-4aa0-a8aa-3d9327fc07c7" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
        <Match idRef="Regex_australia_bank_account_number_bsb" />
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
  </Pattern>
 </Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-192">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-192">Keywords</span></span>

#### <a name="keywordaustraliabankaccountnumber"></a><span data-ttu-id="95cb4-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="95cb4-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="95cb4-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="95cb4-194">swift bank code</span></span>
- <span data-ttu-id="95cb4-195">correspondent bank</span><span class="sxs-lookup"><span data-stu-id="95cb4-195">correspondent bank</span></span>
- <span data-ttu-id="95cb4-196">base currency</span><span class="sxs-lookup"><span data-stu-id="95cb4-196">base currency</span></span>
- <span data-ttu-id="95cb4-197">usa account</span><span class="sxs-lookup"><span data-stu-id="95cb4-197">usa account</span></span>
- <span data-ttu-id="95cb4-198">holder address</span><span class="sxs-lookup"><span data-stu-id="95cb4-198">holder address</span></span>
- <span data-ttu-id="95cb4-199">bank address</span><span class="sxs-lookup"><span data-stu-id="95cb4-199">bank address</span></span>
- <span data-ttu-id="95cb4-200">information account</span><span class="sxs-lookup"><span data-stu-id="95cb4-200">information account</span></span>
- <span data-ttu-id="95cb4-201">fund transfers</span><span class="sxs-lookup"><span data-stu-id="95cb4-201">fund transfers</span></span>
- <span data-ttu-id="95cb4-202">bank charges</span><span class="sxs-lookup"><span data-stu-id="95cb4-202">bank charges</span></span>
- <span data-ttu-id="95cb4-203">bank details</span><span class="sxs-lookup"><span data-stu-id="95cb4-203">bank details</span></span>
- <span data-ttu-id="95cb4-204">banking information</span><span class="sxs-lookup"><span data-stu-id="95cb4-204">banking information</span></span>
- <span data-ttu-id="95cb4-205">full names</span><span class="sxs-lookup"><span data-stu-id="95cb4-205">full names</span></span>
- <span data-ttu-id="95cb4-206">iaea</span><span class="sxs-lookup"><span data-stu-id="95cb4-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="95cb4-207">澳大利亚驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-208">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-208">Format</span></span>

<span data-ttu-id="95cb4-209">九个字母和数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-210">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-210">Pattern</span></span>

<span data-ttu-id="95cb4-211">九个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="95cb4-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="95cb4-212">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="95cb4-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="95cb4-213">两位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-213">Two digits</span></span> 
- <span data-ttu-id="95cb4-214">五位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="95cb4-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="95cb4-215">或者</span><span class="sxs-lookup"><span data-stu-id="95cb4-215">OR</span></span>

- <span data-ttu-id="95cb4-216">1-2 个可选字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="95cb4-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="95cb4-217">4-9 位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-217">4-9 digits</span></span>

<span data-ttu-id="95cb4-218">或者</span><span class="sxs-lookup"><span data-stu-id="95cb4-218">OR</span></span>

- <span data-ttu-id="95cb4-219">九个数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="95cb4-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-220">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-220">Checksum</span></span>

<span data-ttu-id="95cb4-221">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-222">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-222">Definition</span></span>

<span data-ttu-id="95cb4-223">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-224">正则表达式 Regex_australia_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-225">找到 Keyword_australia_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="95cb4-226">未找到 Keyword_australia_drivers_license_number_exclusions 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

```
<!-- Australia Drivers License Number -->
<Entity id="1cbbc8f5-9216-4392-9eb5-5ac2298d1356" patternsProximity="300" recommendedConfidence="75">
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_drivers_license_number" />
        <Match idRef="Keyword_australia_drivers_license_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_australia_drivers_license_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-227">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-227">Keywords</span></span>

#### <a name="keywordaustraliadriverslicensenumber"></a><span data-ttu-id="95cb4-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="95cb4-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="95cb4-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="95cb4-229">international driving permits</span></span>
- <span data-ttu-id="95cb4-230">australian automobile association</span><span class="sxs-lookup"><span data-stu-id="95cb4-230">australian automobile association</span></span>
- <span data-ttu-id="95cb4-231">international driving permit</span><span class="sxs-lookup"><span data-stu-id="95cb4-231">international driving permit</span></span>
- <span data-ttu-id="95cb4-232">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="95cb4-232">DriverLicence</span></span>
- <span data-ttu-id="95cb4-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="95cb4-233">DriverLicences</span></span>
- <span data-ttu-id="95cb4-234">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="95cb4-234">Driver Lic</span></span>
- <span data-ttu-id="95cb4-235">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="95cb4-235">Driver Licence</span></span>
- <span data-ttu-id="95cb4-236">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="95cb4-236">Driver Licences</span></span>
- <span data-ttu-id="95cb4-237">DriversLic</span><span class="sxs-lookup"><span data-stu-id="95cb4-237">DriversLic</span></span>
- <span data-ttu-id="95cb4-238">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="95cb4-238">DriversLicence</span></span>
- <span data-ttu-id="95cb4-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="95cb4-239">DriversLicences</span></span>
- <span data-ttu-id="95cb4-240">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="95cb4-240">Drivers Lic</span></span>
- <span data-ttu-id="95cb4-241">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="95cb4-241">Drivers Lics</span></span>
- <span data-ttu-id="95cb4-242">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="95cb4-242">Drivers Licence</span></span>
- <span data-ttu-id="95cb4-243">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="95cb4-243">Drivers Licences</span></span>
- <span data-ttu-id="95cb4-244">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="95cb4-244">Driver'Lic</span></span>
- <span data-ttu-id="95cb4-245">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="95cb4-245">Driver'Lics</span></span>
- <span data-ttu-id="95cb4-246">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="95cb4-246">Driver'Licence</span></span>
- <span data-ttu-id="95cb4-247">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="95cb4-247">Driver'Licences</span></span>
- <span data-ttu-id="95cb4-248">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="95cb4-248">Driver' Lic</span></span>
- <span data-ttu-id="95cb4-249">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="95cb4-249">Driver' Lics</span></span>
- <span data-ttu-id="95cb4-250">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="95cb4-250">Driver' Licence</span></span>
- <span data-ttu-id="95cb4-251">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="95cb4-251">Driver' Licences</span></span>
- <span data-ttu-id="95cb4-252">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="95cb4-252">Driver'sLic</span></span>
- <span data-ttu-id="95cb4-253">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="95cb4-253">Driver'sLics</span></span>
- <span data-ttu-id="95cb4-254">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="95cb4-254">Driver'sLicence</span></span>
- <span data-ttu-id="95cb4-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="95cb4-255">Driver'sLicences</span></span>
- <span data-ttu-id="95cb4-256">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="95cb4-256">Driver's Lic</span></span>
- <span data-ttu-id="95cb4-257">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="95cb4-257">Driver's Lics</span></span>
- <span data-ttu-id="95cb4-258">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="95cb4-258">Driver's Licence</span></span>
- <span data-ttu-id="95cb4-259">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="95cb4-259">Driver's Licences</span></span>
- <span data-ttu-id="95cb4-260">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="95cb4-260">DriverLic#</span></span>
- <span data-ttu-id="95cb4-261">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="95cb4-261">DriverLics#</span></span>
- <span data-ttu-id="95cb4-262">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="95cb4-262">DriverLicence#</span></span>
- <span data-ttu-id="95cb4-263">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="95cb4-263">DriverLicences#</span></span>
- <span data-ttu-id="95cb4-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="95cb4-264">Driver Lic#</span></span>
- <span data-ttu-id="95cb4-265">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="95cb4-265">Driver Lics#</span></span>
- <span data-ttu-id="95cb4-266">Driver Licence#</span><span class="sxs-lookup"><span data-stu-id="95cb4-266">Driver Licence#</span></span>
- <span data-ttu-id="95cb4-267">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="95cb4-267">Driver Licences#</span></span>
- <span data-ttu-id="95cb4-268">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="95cb4-268">DriversLic#</span></span>
- <span data-ttu-id="95cb4-269">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="95cb4-269">DriversLics#</span></span>
- <span data-ttu-id="95cb4-270">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="95cb4-270">DriversLicence#</span></span>
- <span data-ttu-id="95cb4-271">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="95cb4-271">DriversLicences#</span></span>
- <span data-ttu-id="95cb4-272">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="95cb4-272">Drivers Lic#</span></span>
- <span data-ttu-id="95cb4-273">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="95cb4-273">Drivers Lics#</span></span>
- <span data-ttu-id="95cb4-274">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="95cb4-274">Drivers Licence#</span></span>
- <span data-ttu-id="95cb4-275">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="95cb4-275">Drivers Licences#</span></span>
- <span data-ttu-id="95cb4-276">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="95cb4-276">Driver'Lic#</span></span>
- <span data-ttu-id="95cb4-277">Driver'Lics #</span><span class="sxs-lookup"><span data-stu-id="95cb4-277">Driver'Lics#</span></span>
- <span data-ttu-id="95cb4-278">Driver'Licence #</span><span class="sxs-lookup"><span data-stu-id="95cb4-278">Driver'Licence#</span></span>
- <span data-ttu-id="95cb4-279">Driver'Licences #</span><span class="sxs-lookup"><span data-stu-id="95cb4-279">Driver'Licences#</span></span>
- <span data-ttu-id="95cb4-280">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="95cb4-280">Driver' Lic#</span></span>
- <span data-ttu-id="95cb4-281">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="95cb4-281">Driver' Lics#</span></span>
- <span data-ttu-id="95cb4-282">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="95cb4-282">Driver' Licence#</span></span>
- <span data-ttu-id="95cb4-283">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="95cb4-283">Driver' Licences#</span></span>
- <span data-ttu-id="95cb4-284">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="95cb4-284">Driver'sLic#</span></span>
- <span data-ttu-id="95cb4-285">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="95cb4-285">Driver'sLics#</span></span>
- <span data-ttu-id="95cb4-286">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="95cb4-286">Driver'sLicence#</span></span>
- <span data-ttu-id="95cb4-287">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="95cb4-287">Driver'sLicences#</span></span>
- <span data-ttu-id="95cb4-288">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="95cb4-288">Driver's Lic#</span></span>
- <span data-ttu-id="95cb4-289">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="95cb4-289">Driver's Lics#</span></span>
- <span data-ttu-id="95cb4-290">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="95cb4-290">Driver's Licence#</span></span>
- <span data-ttu-id="95cb4-291">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="95cb4-291">Driver's Licences#</span></span> 

#### <a name="keywordaustraliadriverslicensenumberexclusions"></a><span data-ttu-id="95cb4-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="95cb4-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="95cb4-293">aaa</span><span class="sxs-lookup"><span data-stu-id="95cb4-293">aaa</span></span>
- <span data-ttu-id="95cb4-294">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="95cb4-294">DriverLicense</span></span>
- <span data-ttu-id="95cb4-295">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="95cb4-295">DriverLicenses</span></span>
- <span data-ttu-id="95cb4-296">Driver License</span><span class="sxs-lookup"><span data-stu-id="95cb4-296">Driver License</span></span>
- <span data-ttu-id="95cb4-297">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="95cb4-297">Driver Licenses</span></span>
- <span data-ttu-id="95cb4-298">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="95cb4-298">DriversLicense</span></span>
- <span data-ttu-id="95cb4-299">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="95cb4-299">DriversLicenses</span></span>
- <span data-ttu-id="95cb4-300">Drivers License</span><span class="sxs-lookup"><span data-stu-id="95cb4-300">Drivers License</span></span>
- <span data-ttu-id="95cb4-301">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="95cb4-301">Drivers Licenses</span></span>
- <span data-ttu-id="95cb4-302">Driver'License</span><span class="sxs-lookup"><span data-stu-id="95cb4-302">Driver'License</span></span>
- <span data-ttu-id="95cb4-303">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="95cb4-303">Driver'Licenses</span></span>
- <span data-ttu-id="95cb4-304">Driver' License</span><span class="sxs-lookup"><span data-stu-id="95cb4-304">Driver' License</span></span>
- <span data-ttu-id="95cb4-305">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="95cb4-305">Driver' Licenses</span></span>
- <span data-ttu-id="95cb4-306">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="95cb4-306">Driver'sLicense</span></span>
- <span data-ttu-id="95cb4-307">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="95cb4-307">Driver'sLicenses</span></span>
- <span data-ttu-id="95cb4-308">Driver's License</span><span class="sxs-lookup"><span data-stu-id="95cb4-308">Driver's License</span></span>
- <span data-ttu-id="95cb4-309">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="95cb4-309">Driver's Licenses</span></span>
- <span data-ttu-id="95cb4-310">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="95cb4-310">DriverLicense#</span></span>
- <span data-ttu-id="95cb4-311">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="95cb4-311">DriverLicenses#</span></span>
- <span data-ttu-id="95cb4-312">Driver License#</span><span class="sxs-lookup"><span data-stu-id="95cb4-312">Driver License#</span></span>
- <span data-ttu-id="95cb4-313">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="95cb4-313">Driver Licenses#</span></span>
- <span data-ttu-id="95cb4-314">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="95cb4-314">DriversLicense#</span></span>
- <span data-ttu-id="95cb4-315">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="95cb4-315">DriversLicenses#</span></span>
- <span data-ttu-id="95cb4-316">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="95cb4-316">Drivers License#</span></span>
- <span data-ttu-id="95cb4-317">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="95cb4-317">Drivers Licenses#</span></span>
- <span data-ttu-id="95cb4-318">Driver'License #</span><span class="sxs-lookup"><span data-stu-id="95cb4-318">Driver'License#</span></span>
- <span data-ttu-id="95cb4-319">Driver'Licenses #</span><span class="sxs-lookup"><span data-stu-id="95cb4-319">Driver'Licenses#</span></span>
- <span data-ttu-id="95cb4-320">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="95cb4-320">Driver' License#</span></span>
- <span data-ttu-id="95cb4-321">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="95cb4-321">Driver' Licenses#</span></span>
- <span data-ttu-id="95cb4-322">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="95cb4-322">Driver'sLicense#</span></span>
- <span data-ttu-id="95cb4-323">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="95cb4-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="95cb4-324">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="95cb4-324">Driver's License#</span></span>
- <span data-ttu-id="95cb4-325">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="95cb4-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="95cb4-326">澳大利亚医疗帐号</span><span class="sxs-lookup"><span data-stu-id="95cb4-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-327">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-327">Format</span></span>

<span data-ttu-id="95cb4-328">10-11 个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-329">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-329">Pattern</span></span>

<span data-ttu-id="95cb4-330">10-11 个数字：</span><span class="sxs-lookup"><span data-stu-id="95cb4-330">10-11 digits:</span></span>
- <span data-ttu-id="95cb4-331">第一个数字范围为 2-6</span><span class="sxs-lookup"><span data-stu-id="95cb4-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="95cb4-332">第九个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="95cb4-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="95cb4-333">第十个数字是问题数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="95cb4-334">第十一个数字（可选）是个人号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-335">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-335">Checksum</span></span>

<span data-ttu-id="95cb4-336">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-337">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-337">Definition</span></span>

<span data-ttu-id="95cb4-338">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-339">函数 Func_australian_medical_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-340">找到 Keyword_Australia_Medical_Account_Number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="95cb4-341">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-341">The checksum passes.</span></span>

<span data-ttu-id="95cb4-342">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-343">函数 Func_australian_medical_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-344">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-344">The checksum passes.</span></span>

```
  <!-- Australia Medical Account Number -->
<Entity id="104a99a0-3d3b-4542-a40d-ab0b9e1efe63" recommendedConfidence="85" patternsProximity="300">
    <Pattern confidenceLevel="95">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="1">
     <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
<Pattern confidenceLevel="85">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="0" maxMatches="0">
  <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-345">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-345">Keywords</span></span>

#### <a name="keywordaustraliamedicalaccountnumber"></a><span data-ttu-id="95cb4-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="95cb4-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="95cb4-347">bank account details</span></span>
- <span data-ttu-id="95cb4-348">medicare payments</span><span class="sxs-lookup"><span data-stu-id="95cb4-348">medicare payments</span></span>
- <span data-ttu-id="95cb4-349">mortgage account</span><span class="sxs-lookup"><span data-stu-id="95cb4-349">mortgage account</span></span>
- <span data-ttu-id="95cb4-350">bank payments</span><span class="sxs-lookup"><span data-stu-id="95cb4-350">bank payments</span></span>
- <span data-ttu-id="95cb4-351">information branch</span><span class="sxs-lookup"><span data-stu-id="95cb4-351">information branch</span></span>
- <span data-ttu-id="95cb4-352">credit card loan</span><span class="sxs-lookup"><span data-stu-id="95cb4-352">credit card loan</span></span>
- <span data-ttu-id="95cb4-353">department of human services</span><span class="sxs-lookup"><span data-stu-id="95cb4-353">department of human services</span></span>
- <span data-ttu-id="95cb4-354">local service</span><span class="sxs-lookup"><span data-stu-id="95cb4-354">local service</span></span>
- <span data-ttu-id="95cb4-355">medicare</span><span class="sxs-lookup"><span data-stu-id="95cb4-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="95cb4-356">澳大利亚护照号</span><span class="sxs-lookup"><span data-stu-id="95cb4-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-357">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-357">Format</span></span>

<span data-ttu-id="95cb4-358">一个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-359">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-359">Pattern</span></span>

<span data-ttu-id="95cb4-360">一个字母（不区分大小写）后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-361">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-361">Checksum</span></span>

<span data-ttu-id="95cb4-362">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-363">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-363">Definition</span></span>

<span data-ttu-id="95cb4-364">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-365">正则表达式 Regex_australia_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-366">找到来自 Keyword_passport 或 Keyword_australia_passport_number 的关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

```
<!-- Australia Passport Number -->
<Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_australia_passport_number" />
        </Any>
   </Pattern>
</Entity>   
```

### <a name="keywords"></a><span data-ttu-id="95cb4-367">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-367">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="95cb4-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="95cb4-368">Keyword_passport</span></span>

- <span data-ttu-id="95cb4-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-369">Passport Number</span></span>
- <span data-ttu-id="95cb4-370">Passport No</span><span class="sxs-lookup"><span data-stu-id="95cb4-370">Passport No</span></span>
- <span data-ttu-id="95cb4-371">Passport #</span><span class="sxs-lookup"><span data-stu-id="95cb4-371">Passport #</span></span>
- <span data-ttu-id="95cb4-372">登记卡</span><span class="sxs-lookup"><span data-stu-id="95cb4-372">Passport#</span></span>
- <span data-ttu-id="95cb4-373">PassportID</span><span class="sxs-lookup"><span data-stu-id="95cb4-373">PassportID</span></span>
- <span data-ttu-id="95cb4-374">Passportno</span><span class="sxs-lookup"><span data-stu-id="95cb4-374">Passportno</span></span>
- <span data-ttu-id="95cb4-375">passportnumber</span><span class="sxs-lookup"><span data-stu-id="95cb4-375">passportnumber</span></span>
- <span data-ttu-id="95cb4-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="95cb4-376">パスポート</span></span>
- <span data-ttu-id="95cb4-377">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="95cb4-377">パスポート番号</span></span>
- <span data-ttu-id="95cb4-378">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="95cb4-378">パスポートのNum</span></span>
- <span data-ttu-id="95cb4-379">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="95cb4-379">パスポート ＃</span></span> 
- <span data-ttu-id="95cb4-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="95cb4-380">Numéro de passeport</span></span>
- <span data-ttu-id="95cb4-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="95cb4-381">Passeport n °</span></span>
- <span data-ttu-id="95cb4-382">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="95cb4-382">Passeport Non</span></span>
- <span data-ttu-id="95cb4-383">Passeport #</span><span class="sxs-lookup"><span data-stu-id="95cb4-383">Passeport #</span></span>
- <span data-ttu-id="95cb4-384">Passeport #</span><span class="sxs-lookup"><span data-stu-id="95cb4-384">Passeport#</span></span>
- <span data-ttu-id="95cb4-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="95cb4-385">PasseportNon</span></span>
- <span data-ttu-id="95cb4-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="95cb4-386">Passeportn °</span></span>

#### <a name="keywordaustraliapassportnumber"></a><span data-ttu-id="95cb4-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="95cb4-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="95cb4-388">登记卡</span><span class="sxs-lookup"><span data-stu-id="95cb4-388">passport</span></span>
- <span data-ttu-id="95cb4-389">passport details</span><span class="sxs-lookup"><span data-stu-id="95cb4-389">passport details</span></span>
- <span data-ttu-id="95cb4-390">immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="95cb4-390">immigration and citizenship</span></span>
- <span data-ttu-id="95cb4-391">commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="95cb4-391">commonwealth of australia</span></span>
- <span data-ttu-id="95cb4-392">department of immigration</span><span class="sxs-lookup"><span data-stu-id="95cb4-392">department of immigration</span></span>
- <span data-ttu-id="95cb4-393">residential address</span><span class="sxs-lookup"><span data-stu-id="95cb4-393">residential address</span></span>
- <span data-ttu-id="95cb4-394">department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="95cb4-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="95cb4-395">反之</span><span class="sxs-lookup"><span data-stu-id="95cb4-395">visa</span></span>
- <span data-ttu-id="95cb4-396">national identity card</span><span class="sxs-lookup"><span data-stu-id="95cb4-396">national identity card</span></span>
- <span data-ttu-id="95cb4-397">passport number</span><span class="sxs-lookup"><span data-stu-id="95cb4-397">passport number</span></span>
- <span data-ttu-id="95cb4-398">travel document</span><span class="sxs-lookup"><span data-stu-id="95cb4-398">travel document</span></span>
- <span data-ttu-id="95cb4-399">issuing authority</span><span class="sxs-lookup"><span data-stu-id="95cb4-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="95cb4-400">澳大利亚税号</span><span class="sxs-lookup"><span data-stu-id="95cb4-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-401">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-401">Format</span></span>

<span data-ttu-id="95cb4-402">8-9 个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-403">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-403">Pattern</span></span>

<span data-ttu-id="95cb4-404">通常 8-9 位数字，显示中包含空格，如下所示：</span><span class="sxs-lookup"><span data-stu-id="95cb4-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="95cb4-405">三位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-405">Three digits</span></span> 
- <span data-ttu-id="95cb4-406">可选空格</span><span class="sxs-lookup"><span data-stu-id="95cb4-406">An optional space</span></span> 
- <span data-ttu-id="95cb4-407">三位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-407">Three digits</span></span> 
- <span data-ttu-id="95cb4-408">可选空格</span><span class="sxs-lookup"><span data-stu-id="95cb4-408">An optional space</span></span> 
- <span data-ttu-id="95cb4-409">2-3 位数字，最后一位数字是校验位</span><span class="sxs-lookup"><span data-stu-id="95cb4-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-410">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-410">Checksum</span></span>

<span data-ttu-id="95cb4-411">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-412">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-412">Definition</span></span>

<span data-ttu-id="95cb4-413">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-414">函数 Func_australian_tax_file_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-415">未找到 Keyword_Australia_Tax_File_Number 或 Keyword_number_exclusions 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="95cb4-416">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-416">The checksum passes.</span></span>

```
    <!-- Australia Tax File Number -->
<Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
    
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_Australia_Tax_File_Number" />
          <Match idRef="Keyword_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-417">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-417">Keywords</span></span>

#### <a name="keywordaustraliataxfilenumber"></a><span data-ttu-id="95cb4-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="95cb4-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="95cb4-419">australian business number</span></span>
- <span data-ttu-id="95cb4-420">marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="95cb4-420">marginal tax rate</span></span>
- <span data-ttu-id="95cb4-421">medicare levy</span><span class="sxs-lookup"><span data-stu-id="95cb4-421">medicare levy</span></span>
- <span data-ttu-id="95cb4-422">portfolio number</span><span class="sxs-lookup"><span data-stu-id="95cb4-422">portfolio number</span></span>
- <span data-ttu-id="95cb4-423">service veterans</span><span class="sxs-lookup"><span data-stu-id="95cb4-423">service veterans</span></span>
- <span data-ttu-id="95cb4-424">withholding tax</span><span class="sxs-lookup"><span data-stu-id="95cb4-424">withholding tax</span></span>
- <span data-ttu-id="95cb4-425">individual tax return</span><span class="sxs-lookup"><span data-stu-id="95cb4-425">individual tax return</span></span>
- <span data-ttu-id="95cb4-426">tax file number</span><span class="sxs-lookup"><span data-stu-id="95cb4-426">tax file number</span></span>

#### <a name="keywordnumberexclusions"></a><span data-ttu-id="95cb4-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="95cb4-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="95cb4-428">00000000</span><span class="sxs-lookup"><span data-stu-id="95cb4-428">00000000</span></span>
- <span data-ttu-id="95cb4-429">11111111</span><span class="sxs-lookup"><span data-stu-id="95cb4-429">11111111</span></span>
- <span data-ttu-id="95cb4-430">22222222</span><span class="sxs-lookup"><span data-stu-id="95cb4-430">22222222</span></span>
- <span data-ttu-id="95cb4-431">33333333</span><span class="sxs-lookup"><span data-stu-id="95cb4-431">33333333</span></span>
- <span data-ttu-id="95cb4-432">44444444</span><span class="sxs-lookup"><span data-stu-id="95cb4-432">44444444</span></span>
- <span data-ttu-id="95cb4-433">55555555</span><span class="sxs-lookup"><span data-stu-id="95cb4-433">55555555</span></span>
- <span data-ttu-id="95cb4-434">66666666</span><span class="sxs-lookup"><span data-stu-id="95cb4-434">66666666</span></span>
- <span data-ttu-id="95cb4-435">77777777</span><span class="sxs-lookup"><span data-stu-id="95cb4-435">77777777</span></span>
- <span data-ttu-id="95cb4-436">88888888</span><span class="sxs-lookup"><span data-stu-id="95cb4-436">88888888</span></span>
- <span data-ttu-id="95cb4-437">99999999</span><span class="sxs-lookup"><span data-stu-id="95cb4-437">99999999</span></span>
- <span data-ttu-id="95cb4-438">000000000</span><span class="sxs-lookup"><span data-stu-id="95cb4-438">000000000</span></span>
- <span data-ttu-id="95cb4-439">111111111</span><span class="sxs-lookup"><span data-stu-id="95cb4-439">111111111</span></span>
- <span data-ttu-id="95cb4-440">222222222</span><span class="sxs-lookup"><span data-stu-id="95cb4-440">222222222</span></span>
- <span data-ttu-id="95cb4-441">333333333</span><span class="sxs-lookup"><span data-stu-id="95cb4-441">333333333</span></span>
- <span data-ttu-id="95cb4-442">444444444</span><span class="sxs-lookup"><span data-stu-id="95cb4-442">444444444</span></span>
- <span data-ttu-id="95cb4-443">555555555</span><span class="sxs-lookup"><span data-stu-id="95cb4-443">555555555</span></span>
- <span data-ttu-id="95cb4-444">666666666</span><span class="sxs-lookup"><span data-stu-id="95cb4-444">666666666</span></span>
- <span data-ttu-id="95cb4-445">777777777</span><span class="sxs-lookup"><span data-stu-id="95cb4-445">777777777</span></span>
- <span data-ttu-id="95cb4-446">888888888</span><span class="sxs-lookup"><span data-stu-id="95cb4-446">888888888</span></span>
- <span data-ttu-id="95cb4-447">999999999</span><span class="sxs-lookup"><span data-stu-id="95cb4-447">999999999</span></span>
- <span data-ttu-id="95cb4-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="95cb4-448">0000000000</span></span>
- <span data-ttu-id="95cb4-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="95cb4-449">1111111111</span></span>
- <span data-ttu-id="95cb4-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="95cb4-450">2222222222</span></span>
- <span data-ttu-id="95cb4-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="95cb4-451">3333333333</span></span>
- <span data-ttu-id="95cb4-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="95cb4-452">4444444444</span></span>
- <span data-ttu-id="95cb4-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="95cb4-453">5555555555</span></span>
- <span data-ttu-id="95cb4-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="95cb4-454">6666666666</span></span>
- <span data-ttu-id="95cb4-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="95cb4-455">7777777777</span></span>
- <span data-ttu-id="95cb4-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="95cb4-456">8888888888</span></span>
- <span data-ttu-id="95cb4-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="95cb4-457">9999999999</span></span>
   
## <a name="belgium-national-number"></a><span data-ttu-id="95cb4-458">比利时国家号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-458">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-459">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-459">Format</span></span>

<span data-ttu-id="95cb4-460">11 个数字加分隔符</span><span class="sxs-lookup"><span data-stu-id="95cb4-460">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-461">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-461">Pattern</span></span>

<span data-ttu-id="95cb4-462">11 个数字加分隔符：</span><span class="sxs-lookup"><span data-stu-id="95cb4-462">11 digits plus delimiters:</span></span>
- <span data-ttu-id="95cb4-463">六个数字加两个点，采用格式  YY.MM.DD，代表出生日期  </span><span class="sxs-lookup"><span data-stu-id="95cb4-463">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="95cb4-464">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="95cb4-464">A hyphen</span></span> 
- <span data-ttu-id="95cb4-465">三个连续的数字（男性用奇数，女性用偶数） </span><span class="sxs-lookup"><span data-stu-id="95cb4-465">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="95cb4-466">一个点 </span><span class="sxs-lookup"><span data-stu-id="95cb4-466">A period</span></span> 
- <span data-ttu-id="95cb4-467">两个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="95cb4-467">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-468">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-468">Checksum</span></span>

<span data-ttu-id="95cb4-469">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-469">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-470">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-470">Definition</span></span>

<span data-ttu-id="95cb4-471">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-472">函数 Func_belgium_national_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-472">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-473">找到 Keyword_belgium_national_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-473">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="95cb4-474">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-474">The checksum passes.</span></span>

```
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-475">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-475">Keywords</span></span>

#### <a name="keywordbelgiumnationalnumber"></a><span data-ttu-id="95cb4-476">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="95cb4-476">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="95cb4-477">标识</span><span class="sxs-lookup"><span data-stu-id="95cb4-477">Identity</span></span>
- <span data-ttu-id="95cb4-478">注册</span><span class="sxs-lookup"><span data-stu-id="95cb4-478">Registration</span></span>
- <span data-ttu-id="95cb4-479">id</span><span class="sxs-lookup"><span data-stu-id="95cb4-479">Identification</span></span> 
- <span data-ttu-id="95cb4-480">ID</span><span class="sxs-lookup"><span data-stu-id="95cb4-480">ID</span></span> 
- <span data-ttu-id="95cb4-481">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="95cb4-481">Identiteitskaart</span></span>
- <span data-ttu-id="95cb4-482">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="95cb4-482">Registratie nummer</span></span> 
- <span data-ttu-id="95cb4-483">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="95cb4-483">Identificatie nummer</span></span> 
- <span data-ttu-id="95cb4-484">Identiteit</span><span class="sxs-lookup"><span data-stu-id="95cb4-484">Identiteit</span></span>
- <span data-ttu-id="95cb4-485">Registratie</span><span class="sxs-lookup"><span data-stu-id="95cb4-485">Registratie</span></span>
- <span data-ttu-id="95cb4-486">Identificatie</span><span class="sxs-lookup"><span data-stu-id="95cb4-486">Identificatie</span></span> 
- <span data-ttu-id="95cb4-487">Carte d’identité</span><span class="sxs-lookup"><span data-stu-id="95cb4-487">Carte d’identité</span></span> 
- <span data-ttu-id="95cb4-488">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="95cb4-488">numéro d'immatriculation</span></span>
- <span data-ttu-id="95cb4-489">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="95cb4-489">numéro d'identification</span></span>
- <span data-ttu-id="95cb4-490">identité</span><span class="sxs-lookup"><span data-stu-id="95cb4-490">identité</span></span> 
- <span data-ttu-id="95cb4-491">inscription</span><span class="sxs-lookup"><span data-stu-id="95cb4-491">inscription</span></span> 
- <span data-ttu-id="95cb4-492">Identifikation</span><span class="sxs-lookup"><span data-stu-id="95cb4-492">Identifikation</span></span>
- <span data-ttu-id="95cb4-493">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="95cb4-493">Identifizierung</span></span>
- <span data-ttu-id="95cb4-494">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="95cb4-494">Identifikationsnummer</span></span>
- <span data-ttu-id="95cb4-495">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="95cb4-495">Personalausweis</span></span>
- <span data-ttu-id="95cb4-496">Registrierung</span><span class="sxs-lookup"><span data-stu-id="95cb4-496">Registrierung</span></span>
- <span data-ttu-id="95cb4-497">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="95cb4-497">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="95cb4-498">巴西 CPF 号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-498">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-499">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-499">Format</span></span>

<span data-ttu-id="95cb4-500">11 个数字（包括校验位），可以格式化，也可以非格式化</span><span class="sxs-lookup"><span data-stu-id="95cb4-500">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-501">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-501">Pattern</span></span>

<span data-ttu-id="95cb4-502">格式</span><span class="sxs-lookup"><span data-stu-id="95cb4-502">Formatted:</span></span>
- <span data-ttu-id="95cb4-503">三位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-503">Three digits</span></span> 
- <span data-ttu-id="95cb4-504">一个点 </span><span class="sxs-lookup"><span data-stu-id="95cb4-504">A period</span></span> 
- <span data-ttu-id="95cb4-505">三位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-505">Three digits</span></span> 
- <span data-ttu-id="95cb4-506">一个点 </span><span class="sxs-lookup"><span data-stu-id="95cb4-506">A period</span></span> 
- <span data-ttu-id="95cb4-507">三位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-507">Three digits</span></span> 
- <span data-ttu-id="95cb4-508">连字符</span><span class="sxs-lookup"><span data-stu-id="95cb4-508">A hyphen</span></span> 
- <span data-ttu-id="95cb4-509">两个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="95cb4-509">Two digits which are check digits</span></span>

<span data-ttu-id="95cb4-510">纯</span><span class="sxs-lookup"><span data-stu-id="95cb4-510">Unformatted:</span></span>
- <span data-ttu-id="95cb4-511">11 个数字，其中最后两个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="95cb4-511">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-512">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-512">Checksum</span></span>

<span data-ttu-id="95cb4-513">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-513">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-514">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-514">Definition</span></span>

<span data-ttu-id="95cb4-515">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-515">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-516">函数 Func_brazil_cpf 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-516">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-517">找到 Keyword_brazil_cpf 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-517">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="95cb4-518">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-518">The checksum passes.</span></span>

<span data-ttu-id="95cb4-519">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-519">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-520">函数 Func_brazil_cpf 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-520">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-521">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-521">The checksum passes.</span></span>

```
<!-- Brazil CPF Number -->
<Entity id="78e09124-f2c3-4656-b32a-c1a132cd2711" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cpf"/>
     <Match idRef="Keyword_brazil_cpf"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cpf"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-522">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-522">Keywords</span></span>

#### <a name="keywordbrazilcpf"></a><span data-ttu-id="95cb4-523">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="95cb4-523">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="95cb4-524">CPF</span><span class="sxs-lookup"><span data-stu-id="95cb4-524">CPF</span></span>
- <span data-ttu-id="95cb4-525">id</span><span class="sxs-lookup"><span data-stu-id="95cb4-525">Identification</span></span>
- <span data-ttu-id="95cb4-526">注册</span><span class="sxs-lookup"><span data-stu-id="95cb4-526">Registration</span></span>
- <span data-ttu-id="95cb4-527">营业</span><span class="sxs-lookup"><span data-stu-id="95cb4-527">Revenue</span></span>
- <span data-ttu-id="95cb4-528">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="95cb4-528">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="95cb4-529">Imposto</span><span class="sxs-lookup"><span data-stu-id="95cb4-529">Imposto</span></span> 
- <span data-ttu-id="95cb4-530">Identificação</span><span class="sxs-lookup"><span data-stu-id="95cb4-530">Identificação</span></span> 
- <span data-ttu-id="95cb4-531">Inscrição</span><span class="sxs-lookup"><span data-stu-id="95cb4-531">Inscrição</span></span> 
- <span data-ttu-id="95cb4-532">Receita</span><span class="sxs-lookup"><span data-stu-id="95cb4-532">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="95cb4-533">巴西法律实体编号 (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="95cb4-533">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-534">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-534">Format</span></span>

<span data-ttu-id="95cb4-535">14 个数字（包括注册号、分行号码和校验位），再加上分隔符</span><span class="sxs-lookup"><span data-stu-id="95cb4-535">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-536">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-536">Pattern</span></span>
<span data-ttu-id="95cb4-537">14 个数字，再加上分隔符：</span><span class="sxs-lookup"><span data-stu-id="95cb4-537">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="95cb4-538">两个数字 </span><span class="sxs-lookup"><span data-stu-id="95cb4-538">Two digits</span></span> 
- <span data-ttu-id="95cb4-539">一个点 </span><span class="sxs-lookup"><span data-stu-id="95cb4-539">A period</span></span> 
- <span data-ttu-id="95cb4-540">三位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-540">Three digits</span></span> 
- <span data-ttu-id="95cb4-541">一个点 </span><span class="sxs-lookup"><span data-stu-id="95cb4-541">A period</span></span> 
- <span data-ttu-id="95cb4-542">三个数字（前 8 位数是注册号） </span><span class="sxs-lookup"><span data-stu-id="95cb4-542">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="95cb4-543">正斜杠 </span><span class="sxs-lookup"><span data-stu-id="95cb4-543">A forward slash</span></span> 
- <span data-ttu-id="95cb4-544">四位分行号码 </span><span class="sxs-lookup"><span data-stu-id="95cb4-544">Four-digit branch number</span></span> 
- <span data-ttu-id="95cb4-545">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="95cb4-545">A hyphen</span></span> 
- <span data-ttu-id="95cb4-546">两个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="95cb4-546">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-547">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-547">Checksum</span></span>

<span data-ttu-id="95cb4-548">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-548">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-549">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-549">Definition</span></span>

<span data-ttu-id="95cb4-550">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-550">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-551">函数 Func_brazil_cnpj 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-551">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-552">找到 Keyword_brazil_cnpj 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-552">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="95cb4-553">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-553">The checksum passes.</span></span>

<span data-ttu-id="95cb4-554">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-554">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-555">函数 Func_brazil_cnpj 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-555">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-556">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-556">The checksum passes.</span></span>

```
<!-- Brazil Legal Entity Number (CNPJ) -->
<Entity id="9b58b5cd-5e90-4df6-b34f-1ebcc88ceae4" recommendedConfidence="85" patternsProximity="300">
   <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cnpj"/>
     <Match idRef="Keyword_brazil_cnpj"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cnpj"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-557">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-557">Keywords</span></span>

#### <a name="keywordbrazilcnpj"></a><span data-ttu-id="95cb4-558">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="95cb4-558">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="95cb4-559">CNPJ</span><span class="sxs-lookup"><span data-stu-id="95cb4-559">CNPJ</span></span> 
- <span data-ttu-id="95cb4-560">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="95cb4-560">CNPJ/MF</span></span> 
- <span data-ttu-id="95cb4-561">CNPJ-MF</span><span class="sxs-lookup"><span data-stu-id="95cb4-561">CNPJ-MF</span></span> 
- <span data-ttu-id="95cb4-562">National Registry of Legal Entities</span><span class="sxs-lookup"><span data-stu-id="95cb4-562">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="95cb4-563">Taxpayers Registry</span><span class="sxs-lookup"><span data-stu-id="95cb4-563">Taxpayers Registry</span></span> 
- <span data-ttu-id="95cb4-564">Legal entity</span><span class="sxs-lookup"><span data-stu-id="95cb4-564">Legal entity</span></span> 
- <span data-ttu-id="95cb4-565">Legal entities</span><span class="sxs-lookup"><span data-stu-id="95cb4-565">Legal entities</span></span> 
- <span data-ttu-id="95cb4-566">Registration Status</span><span class="sxs-lookup"><span data-stu-id="95cb4-566">Registration Status</span></span> 
- <span data-ttu-id="95cb4-567">商业版</span><span class="sxs-lookup"><span data-stu-id="95cb4-567">Business</span></span> 
- <span data-ttu-id="95cb4-568">Company</span><span class="sxs-lookup"><span data-stu-id="95cb4-568">Company</span></span>
- <span data-ttu-id="95cb4-569">CNPJ</span><span class="sxs-lookup"><span data-stu-id="95cb4-569">CNPJ</span></span> 
- <span data-ttu-id="95cb4-570">Cadastro Nacional da Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="95cb4-570">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="95cb4-571">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="95cb4-571">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="95cb4-572">CGC</span><span class="sxs-lookup"><span data-stu-id="95cb4-572">CGC</span></span> 
- <span data-ttu-id="95cb4-573">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="95cb4-573">Pessoa jurídica</span></span> 
- <span data-ttu-id="95cb4-574">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="95cb4-574">Pessoas jurídicas</span></span> 
- <span data-ttu-id="95cb4-575">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="95cb4-575">Situação cadastral</span></span> 
- <span data-ttu-id="95cb4-576">Inscrição</span><span class="sxs-lookup"><span data-stu-id="95cb4-576">Inscrição</span></span> 
- <span data-ttu-id="95cb4-577">Empresa</span><span class="sxs-lookup"><span data-stu-id="95cb4-577">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="95cb4-578">	巴西国家身份证 (RG)</span><span class="sxs-lookup"><span data-stu-id="95cb4-578">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-579">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-579">Format</span></span>

<span data-ttu-id="95cb4-580">Registro Geral (旧格式): 9 个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-580">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="95cb4-581">Registro de Identidade (RIC) (新格式):11 个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-581">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-582">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-582">Pattern</span></span>

<span data-ttu-id="95cb4-583">Registro Geral（旧格式）：</span><span class="sxs-lookup"><span data-stu-id="95cb4-583">Registro Geral (old format):</span></span>
- <span data-ttu-id="95cb4-584">两个数字 </span><span class="sxs-lookup"><span data-stu-id="95cb4-584">Two digits</span></span> 
- <span data-ttu-id="95cb4-585">一个点 </span><span class="sxs-lookup"><span data-stu-id="95cb4-585">A period</span></span> 
- <span data-ttu-id="95cb4-586">三位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-586">Three digits</span></span> 
- <span data-ttu-id="95cb4-587">一个点 </span><span class="sxs-lookup"><span data-stu-id="95cb4-587">A period</span></span> 
- <span data-ttu-id="95cb4-588">三位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-588">Three digits</span></span> 
- <span data-ttu-id="95cb4-589">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="95cb4-589">A hyphen</span></span> 
- <span data-ttu-id="95cb4-590">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="95cb4-590">One digit which is a check digit</span></span>

<span data-ttu-id="95cb4-591">Registro de Identidade (RIC) (新格式):</span><span class="sxs-lookup"><span data-stu-id="95cb4-591">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="95cb4-592">10 个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-592">10 digits</span></span> 
- <span data-ttu-id="95cb4-593">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="95cb4-593">A hyphen</span></span> 
- <span data-ttu-id="95cb4-594">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="95cb4-594">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-595">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-595">Checksum</span></span>

<span data-ttu-id="95cb4-596">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-596">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-597">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-597">Definition</span></span>

<span data-ttu-id="95cb4-598">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-598">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-599">函数 Func_brazil_rg 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-599">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-600">找到 Keyword_brazil_rg 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-600">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="95cb4-601">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-601">The checksum passes.</span></span>

<span data-ttu-id="95cb4-602">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-602">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-603">函数 Func_brazil_rg 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-603">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-604">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-604">The checksum passes.</span></span>

```
<!-- Brazil National ID Card (RG) -->
<Entity id="486de900-db70-41b3-a886-abdf25af119c" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_rg"/>
     <Match idRef="Keyword_brazil_rg"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_rg"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-605">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-605">Keywords</span></span>

#### <a name="keywordbrazilrg"></a><span data-ttu-id="95cb4-606">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="95cb4-606">Keyword_brazil_rg</span></span>

<span data-ttu-id="95cb4-607">Cédula de identidade identity 卡片国家 id número de rregistro registro de Iidentidade registro geral RG (此关键字区分大小写) RIC (此关键字区分大小写)</span><span class="sxs-lookup"><span data-stu-id="95cb4-607">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="95cb4-608">加拿大银行帐号</span><span class="sxs-lookup"><span data-stu-id="95cb4-608">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-609">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-609">Format</span></span>

<span data-ttu-id="95cb4-610">七个或十二个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-610">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-611">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-611">Pattern</span></span>

<span data-ttu-id="95cb4-612">加拿大银行帐号是七个或十二个数字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-612">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="95cb4-613">加拿大银行帐户的银行代号是：</span><span class="sxs-lookup"><span data-stu-id="95cb4-613">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="95cb4-614">五位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-614">Five digits</span></span> 
- <span data-ttu-id="95cb4-615">连字符</span><span class="sxs-lookup"><span data-stu-id="95cb4-615">A hyphen</span></span> 
- <span data-ttu-id="95cb4-616">三位数字或</span><span class="sxs-lookup"><span data-stu-id="95cb4-616">Three digits OR</span></span>
- <span data-ttu-id="95cb4-617">一个零“0” </span><span class="sxs-lookup"><span data-stu-id="95cb4-617">A zero "0"</span></span> 
- <span data-ttu-id="95cb4-618">八位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-618">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-619">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-619">Checksum</span></span>

<span data-ttu-id="95cb4-620">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-620">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-621">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-621">Definition</span></span>

<span data-ttu-id="95cb4-622">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-622">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-623">正则表达式 Regex_canada_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-623">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-624">找到 Keyword_canada_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-624">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="95cb4-625">正则表达式 Regex_canada_bank_account_transit_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-625">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="95cb4-626">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-627">正则表达式 Regex_canada_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-627">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-628">找到 Keyword_canada_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-628">A keyword from Keyword_canada_bank_account_number is found.</span></span>

```
<!-- Canada Bank Account Number -->
<Entity id="552e814c-cb50-4d94-bbaa-bb1d1ffb34de" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
        <Match idRef="Regex_canada_bank_account_transit_number" />
   </Pattern>
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-629">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-629">Keywords</span></span>

#### <a name="keywordcanadabankaccountnumber"></a><span data-ttu-id="95cb4-630">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="95cb4-630">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="95cb4-631">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="95cb4-631">canada savings bonds</span></span>
- <span data-ttu-id="95cb4-632">canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="95cb4-632">canada revenue agency</span></span>
- <span data-ttu-id="95cb4-633">canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="95cb4-633">canadian financial institution</span></span>
- <span data-ttu-id="95cb4-634">direct deposit form</span><span class="sxs-lookup"><span data-stu-id="95cb4-634">direct deposit form</span></span>
- <span data-ttu-id="95cb4-635">canadian citizen</span><span class="sxs-lookup"><span data-stu-id="95cb4-635">canadian citizen</span></span>
- <span data-ttu-id="95cb4-636">legal representative</span><span class="sxs-lookup"><span data-stu-id="95cb4-636">legal representative</span></span>
- <span data-ttu-id="95cb4-637">notary public</span><span class="sxs-lookup"><span data-stu-id="95cb4-637">notary public</span></span>
- <span data-ttu-id="95cb4-638">commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="95cb4-638">commissioner for oaths</span></span>
- <span data-ttu-id="95cb4-639">child care benefit</span><span class="sxs-lookup"><span data-stu-id="95cb4-639">child care benefit</span></span>
- <span data-ttu-id="95cb4-640">universal child care</span><span class="sxs-lookup"><span data-stu-id="95cb4-640">universal child care</span></span>
- <span data-ttu-id="95cb4-641">canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="95cb4-641">canada child tax benefit</span></span>
- <span data-ttu-id="95cb4-642">income tax benefit</span><span class="sxs-lookup"><span data-stu-id="95cb4-642">income tax benefit</span></span>
- <span data-ttu-id="95cb4-643">harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="95cb4-643">harmonized sales tax</span></span>
- <span data-ttu-id="95cb4-644">social insurance number</span><span class="sxs-lookup"><span data-stu-id="95cb4-644">social insurance number</span></span>
- <span data-ttu-id="95cb4-645">income tax refund</span><span class="sxs-lookup"><span data-stu-id="95cb4-645">income tax refund</span></span>
- <span data-ttu-id="95cb4-646">child tax benefit</span><span class="sxs-lookup"><span data-stu-id="95cb4-646">child tax benefit</span></span>
- <span data-ttu-id="95cb4-647">territorial payments</span><span class="sxs-lookup"><span data-stu-id="95cb4-647">territorial payments</span></span>
- <span data-ttu-id="95cb4-648">institution number</span><span class="sxs-lookup"><span data-stu-id="95cb4-648">institution number</span></span>
- <span data-ttu-id="95cb4-649">deposit request</span><span class="sxs-lookup"><span data-stu-id="95cb4-649">deposit request</span></span>
- <span data-ttu-id="95cb4-650">banking information</span><span class="sxs-lookup"><span data-stu-id="95cb4-650">banking information</span></span>
- <span data-ttu-id="95cb4-651">direct deposit</span><span class="sxs-lookup"><span data-stu-id="95cb4-651">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="95cb4-652">加拿大驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-652">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-653">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-653">Format</span></span>

<span data-ttu-id="95cb4-654">因省而异</span><span class="sxs-lookup"><span data-stu-id="95cb4-654">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-655">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-655">Pattern</span></span>

<span data-ttu-id="95cb4-656">各种模式，涵盖艾伯塔、 不列颠哥伦比亚、 马尼托巴、 新不伦瑞克、 纽芬兰/拉布拉多、 新斯科舍、 安大略、 爱德华王子岛，魁北克和萨斯喀彻温</span><span class="sxs-lookup"><span data-stu-id="95cb4-656">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-657">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-657">Checksum</span></span>

<span data-ttu-id="95cb4-658">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-658">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-659">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-659">Definition</span></span>

<span data-ttu-id="95cb4-660">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-660">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-661">函数 Func_[province_name]_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-661">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-662">找到 Keyword_[province_name]_drivers_license_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-662">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="95cb4-663">找到 Keyword_canada_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-663">A keyword from Keyword_canada_drivers_license is found.</span></span>

```
<!-- Canada Driver's License Number -->
    <Entity id="37186abb-8e48-4800-ad3c-e3d1610b3db0" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_alberta_drivers_license_number" />
        <Match idRef="Keyword_alberta_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_british_columbia_drivers_license_number" />
        <Match idRef="Keyword_british_columbia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_manitoba_drivers_license_number" />
        <Match idRef="Keyword_manitoba_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_brunswick_drivers_license_number" />
        <Match idRef="Keyword_new_brunswick_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_newfoundland_labrador_drivers_license_number" />
        <Match idRef="Keyword_newfoundland_labrador_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_nova_scotia_drivers_license_number" />
        <Match idRef="Keyword_nova_scotia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_ontario_drivers_license_number" />
        <Match idRef="Keyword_ontario_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_prince_edward_island_drivers_license_number" />
        <Match idRef="Keyword_prince_edward_island_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_quebec_drivers_license_number" />
        <Match idRef="Keyword_quebec_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_saskatchewan_drivers_license_number" />
        <Match idRef="Keyword_saskatchewan_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-664">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-664">Keywords</span></span>

#### <a name="keywordprovincenamedriverslicensename"></a><span data-ttu-id="95cb4-665">Keyword_ [province_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="95cb4-665">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="95cb4-666">省/市/自治区的缩写，例如 AB</span><span class="sxs-lookup"><span data-stu-id="95cb4-666">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="95cb4-667">省名称，例如 Alberta</span><span class="sxs-lookup"><span data-stu-id="95cb4-667">The province name, for example Alberta</span></span>

#### <a name="keywordcanadadriverslicense"></a><span data-ttu-id="95cb4-668">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="95cb4-668">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="95cb4-669">通讯</span><span class="sxs-lookup"><span data-stu-id="95cb4-669">DL</span></span>
- <span data-ttu-id="95cb4-670">DLS</span><span class="sxs-lookup"><span data-stu-id="95cb4-670">DLS</span></span>
- <span data-ttu-id="95cb4-671">采用</span><span class="sxs-lookup"><span data-stu-id="95cb4-671">CDL</span></span>
- <span data-ttu-id="95cb4-672">CDLS</span><span class="sxs-lookup"><span data-stu-id="95cb4-672">CDLS</span></span>
- <span data-ttu-id="95cb4-673">DriverLic</span><span class="sxs-lookup"><span data-stu-id="95cb4-673">DriverLic</span></span>
- <span data-ttu-id="95cb4-674">DriverLics</span><span class="sxs-lookup"><span data-stu-id="95cb4-674">DriverLics</span></span>
- <span data-ttu-id="95cb4-675">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="95cb4-675">DriverLicense</span></span>
- <span data-ttu-id="95cb4-676">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="95cb4-676">DriverLicenses</span></span>
- <span data-ttu-id="95cb4-677">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="95cb4-677">DriverLicence</span></span>
- <span data-ttu-id="95cb4-678">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="95cb4-678">DriverLicences</span></span>
- <span data-ttu-id="95cb4-679">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="95cb4-679">Driver Lic</span></span>
- <span data-ttu-id="95cb4-680">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="95cb4-680">Driver Lics</span></span>
- <span data-ttu-id="95cb4-681">Driver License</span><span class="sxs-lookup"><span data-stu-id="95cb4-681">Driver License</span></span>
- <span data-ttu-id="95cb4-682">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="95cb4-682">Driver Licenses</span></span>
- <span data-ttu-id="95cb4-683">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="95cb4-683">Driver Licence</span></span>
- <span data-ttu-id="95cb4-684">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="95cb4-684">Driver Licences</span></span>
- <span data-ttu-id="95cb4-685">DriversLic</span><span class="sxs-lookup"><span data-stu-id="95cb4-685">DriversLic</span></span>
- <span data-ttu-id="95cb4-686">DriversLics</span><span class="sxs-lookup"><span data-stu-id="95cb4-686">DriversLics</span></span>
- <span data-ttu-id="95cb4-687">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="95cb4-687">DriversLicence</span></span>
- <span data-ttu-id="95cb4-688">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="95cb4-688">DriversLicences</span></span>
- <span data-ttu-id="95cb4-689">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="95cb4-689">DriversLicense</span></span>
- <span data-ttu-id="95cb4-690">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="95cb4-690">DriversLicenses</span></span>
- <span data-ttu-id="95cb4-691">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="95cb4-691">Drivers Lic</span></span>
- <span data-ttu-id="95cb4-692">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="95cb4-692">Drivers Lics</span></span>
- <span data-ttu-id="95cb4-693">Drivers License</span><span class="sxs-lookup"><span data-stu-id="95cb4-693">Drivers License</span></span>
- <span data-ttu-id="95cb4-694">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="95cb4-694">Drivers Licenses</span></span>
- <span data-ttu-id="95cb4-695">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="95cb4-695">Drivers Licence</span></span>
- <span data-ttu-id="95cb4-696">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="95cb4-696">Drivers Licences</span></span>
- <span data-ttu-id="95cb4-697">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="95cb4-697">Driver'Lic</span></span>
- <span data-ttu-id="95cb4-698">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="95cb4-698">Driver'Lics</span></span>
- <span data-ttu-id="95cb4-699">Driver'License</span><span class="sxs-lookup"><span data-stu-id="95cb4-699">Driver'License</span></span>
- <span data-ttu-id="95cb4-700">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="95cb4-700">Driver'Licenses</span></span>
- <span data-ttu-id="95cb4-701">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="95cb4-701">Driver'Licence</span></span>
- <span data-ttu-id="95cb4-702">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="95cb4-702">Driver'Licences</span></span>
- <span data-ttu-id="95cb4-703">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="95cb4-703">Driver' Lic</span></span>
- <span data-ttu-id="95cb4-704">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="95cb4-704">Driver' Lics</span></span>
- <span data-ttu-id="95cb4-705">Driver' License</span><span class="sxs-lookup"><span data-stu-id="95cb4-705">Driver' License</span></span>
- <span data-ttu-id="95cb4-706">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="95cb4-706">Driver' Licenses</span></span>
- <span data-ttu-id="95cb4-707">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="95cb4-707">Driver' Licence</span></span>
- <span data-ttu-id="95cb4-708">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="95cb4-708">Driver' Licences</span></span>
- <span data-ttu-id="95cb4-709">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="95cb4-709">Driver'sLic</span></span>
- <span data-ttu-id="95cb4-710">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="95cb4-710">Driver'sLics</span></span>
- <span data-ttu-id="95cb4-711">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="95cb4-711">Driver'sLicense</span></span>
- <span data-ttu-id="95cb4-712">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="95cb4-712">Driver'sLicenses</span></span>
- <span data-ttu-id="95cb4-713">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="95cb4-713">Driver'sLicence</span></span>
- <span data-ttu-id="95cb4-714">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="95cb4-714">Driver'sLicences</span></span>
- <span data-ttu-id="95cb4-715">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="95cb4-715">Driver's Lic</span></span>
- <span data-ttu-id="95cb4-716">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="95cb4-716">Driver's Lics</span></span>
- <span data-ttu-id="95cb4-717">Driver's License</span><span class="sxs-lookup"><span data-stu-id="95cb4-717">Driver's License</span></span>
- <span data-ttu-id="95cb4-718">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="95cb4-718">Driver's Licenses</span></span>
- <span data-ttu-id="95cb4-719">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="95cb4-719">Driver's Licence</span></span>
- <span data-ttu-id="95cb4-720">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="95cb4-720">Driver's Licences</span></span>
- <span data-ttu-id="95cb4-721">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="95cb4-721">Permis de Conduire</span></span>
- <span data-ttu-id="95cb4-722">id</span><span class="sxs-lookup"><span data-stu-id="95cb4-722">id</span></span>
- <span data-ttu-id="95cb4-723">ids</span><span class="sxs-lookup"><span data-stu-id="95cb4-723">ids</span></span>
- <span data-ttu-id="95cb4-724">idcard number</span><span class="sxs-lookup"><span data-stu-id="95cb4-724">idcard number</span></span>
- <span data-ttu-id="95cb4-725">idcard numbers</span><span class="sxs-lookup"><span data-stu-id="95cb4-725">idcard numbers</span></span>
- <span data-ttu-id="95cb4-726">idcard #</span><span class="sxs-lookup"><span data-stu-id="95cb4-726">idcard #</span></span>
- <span data-ttu-id="95cb4-727">idcard #s</span><span class="sxs-lookup"><span data-stu-id="95cb4-727">idcard #s</span></span>
- <span data-ttu-id="95cb4-728">idcard card</span><span class="sxs-lookup"><span data-stu-id="95cb4-728">idcard card</span></span>
- <span data-ttu-id="95cb4-729">idcard cards</span><span class="sxs-lookup"><span data-stu-id="95cb4-729">idcard cards</span></span>
- <span data-ttu-id="95cb4-730">idcard</span><span class="sxs-lookup"><span data-stu-id="95cb4-730">idcard</span></span>
- <span data-ttu-id="95cb4-731">identification number</span><span class="sxs-lookup"><span data-stu-id="95cb4-731">identification number</span></span>
- <span data-ttu-id="95cb4-732">identification numbers</span><span class="sxs-lookup"><span data-stu-id="95cb4-732">identification numbers</span></span>
- <span data-ttu-id="95cb4-733">identification #</span><span class="sxs-lookup"><span data-stu-id="95cb4-733">identification #</span></span>
- <span data-ttu-id="95cb4-734">identification #s</span><span class="sxs-lookup"><span data-stu-id="95cb4-734">identification #s</span></span>
- <span data-ttu-id="95cb4-735">identification card</span><span class="sxs-lookup"><span data-stu-id="95cb4-735">identification card</span></span>
- <span data-ttu-id="95cb4-736">identification cards</span><span class="sxs-lookup"><span data-stu-id="95cb4-736">identification cards</span></span>
- <span data-ttu-id="95cb4-737">id</span><span class="sxs-lookup"><span data-stu-id="95cb4-737">identification</span></span> 
- <span data-ttu-id="95cb4-738">通讯</span><span class="sxs-lookup"><span data-stu-id="95cb4-738">DL#</span></span>
- <span data-ttu-id="95cb4-739">DLS</span><span class="sxs-lookup"><span data-stu-id="95cb4-739">DLS#</span></span> 
- <span data-ttu-id="95cb4-740">采用</span><span class="sxs-lookup"><span data-stu-id="95cb4-740">CDL#</span></span> 
- <span data-ttu-id="95cb4-741">CDLS #</span><span class="sxs-lookup"><span data-stu-id="95cb4-741">CDLS#</span></span> 
- <span data-ttu-id="95cb4-742">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="95cb4-742">DriverLic#</span></span> 
- <span data-ttu-id="95cb4-743">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="95cb4-743">DriverLics#</span></span> 
- <span data-ttu-id="95cb4-744">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="95cb4-744">DriverLicense#</span></span> 
- <span data-ttu-id="95cb4-745">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="95cb4-745">DriverLicenses#</span></span> 
- <span data-ttu-id="95cb4-746">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="95cb4-746">DriverLicence#</span></span> 
- <span data-ttu-id="95cb4-747">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="95cb4-747">DriverLicences#</span></span> 
- <span data-ttu-id="95cb4-748">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="95cb4-748">Driver Lic#</span></span>
- <span data-ttu-id="95cb4-749">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="95cb4-749">Driver Lics#</span></span> 
- <span data-ttu-id="95cb4-750">Driver License#</span><span class="sxs-lookup"><span data-stu-id="95cb4-750">Driver License#</span></span> 
- <span data-ttu-id="95cb4-751">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="95cb4-751">Driver Licenses#</span></span> 
- <span data-ttu-id="95cb4-752">Driver License#</span><span class="sxs-lookup"><span data-stu-id="95cb4-752">Driver License#</span></span> 
- <span data-ttu-id="95cb4-753">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="95cb4-753">Driver Licences#</span></span> 
- <span data-ttu-id="95cb4-754">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="95cb4-754">DriversLic#</span></span> 
- <span data-ttu-id="95cb4-755">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="95cb4-755">DriversLics#</span></span> 
- <span data-ttu-id="95cb4-756">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="95cb4-756">DriversLicense#</span></span> 
- <span data-ttu-id="95cb4-757">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="95cb4-757">DriversLicenses#</span></span> 
- <span data-ttu-id="95cb4-758">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="95cb4-758">DriversLicence#</span></span> 
- <span data-ttu-id="95cb4-759">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="95cb4-759">DriversLicences#</span></span> 
- <span data-ttu-id="95cb4-760">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="95cb4-760">Drivers Lic#</span></span> 
- <span data-ttu-id="95cb4-761">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="95cb4-761">Drivers Lics#</span></span> 
- <span data-ttu-id="95cb4-762">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="95cb4-762">Drivers License#</span></span> 
- <span data-ttu-id="95cb4-763">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="95cb4-763">Drivers Licenses#</span></span> 
- <span data-ttu-id="95cb4-764">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="95cb4-764">Drivers Licence#</span></span> 
- <span data-ttu-id="95cb4-765">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="95cb4-765">Drivers Licences#</span></span> 
- <span data-ttu-id="95cb4-766">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="95cb4-766">Driver'Lic#</span></span> 
- <span data-ttu-id="95cb4-767">Driver'Lics #</span><span class="sxs-lookup"><span data-stu-id="95cb4-767">Driver'Lics#</span></span> 
- <span data-ttu-id="95cb4-768">Driver'License #</span><span class="sxs-lookup"><span data-stu-id="95cb4-768">Driver'License#</span></span> 
- <span data-ttu-id="95cb4-769">Driver'Licenses #</span><span class="sxs-lookup"><span data-stu-id="95cb4-769">Driver'Licenses#</span></span> 
- <span data-ttu-id="95cb4-770">Driver'Licence #</span><span class="sxs-lookup"><span data-stu-id="95cb4-770">Driver'Licence#</span></span> 
- <span data-ttu-id="95cb4-771">Driver'Licences #</span><span class="sxs-lookup"><span data-stu-id="95cb4-771">Driver'Licences#</span></span> 
- <span data-ttu-id="95cb4-772">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="95cb4-772">Driver' Lic#</span></span> 
- <span data-ttu-id="95cb4-773">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="95cb4-773">Driver' Lics#</span></span> 
- <span data-ttu-id="95cb4-774">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="95cb4-774">Driver' License#</span></span> 
- <span data-ttu-id="95cb4-775">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="95cb4-775">Driver' Licenses#</span></span> 
- <span data-ttu-id="95cb4-776">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="95cb4-776">Driver' Licence#</span></span> 
- <span data-ttu-id="95cb4-777">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="95cb4-777">Driver' Licences#</span></span> 
- <span data-ttu-id="95cb4-778">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="95cb4-778">Driver'sLic#</span></span> 
- <span data-ttu-id="95cb4-779">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="95cb4-779">Driver'sLics#</span></span> 
- <span data-ttu-id="95cb4-780">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="95cb4-780">Driver'sLicense#</span></span> 
- <span data-ttu-id="95cb4-781">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="95cb4-781">Driver'sLicenses#</span></span> 
- <span data-ttu-id="95cb4-782">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="95cb4-782">Driver'sLicence#</span></span> 
- <span data-ttu-id="95cb4-783">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="95cb4-783">Driver'sLicences#</span></span> 
- <span data-ttu-id="95cb4-784">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="95cb4-784">Driver's Lic#</span></span> 
- <span data-ttu-id="95cb4-785">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="95cb4-785">Driver's Lics#</span></span> 
- <span data-ttu-id="95cb4-786">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="95cb4-786">Driver's License#</span></span> 
- <span data-ttu-id="95cb4-787">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="95cb4-787">Driver's Licenses#</span></span> 
- <span data-ttu-id="95cb4-788">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="95cb4-788">Driver's Licence#</span></span> 
- <span data-ttu-id="95cb4-789">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="95cb4-789">Driver's Licences#</span></span> 
- <span data-ttu-id="95cb4-790">Permis de Conduire#</span><span class="sxs-lookup"><span data-stu-id="95cb4-790">Permis de Conduire#</span></span> 
- <span data-ttu-id="95cb4-791">号</span><span class="sxs-lookup"><span data-stu-id="95cb4-791">id#</span></span> 
- <span data-ttu-id="95cb4-792">id</span><span class="sxs-lookup"><span data-stu-id="95cb4-792">ids#</span></span> 
- <span data-ttu-id="95cb4-793">idcard card#</span><span class="sxs-lookup"><span data-stu-id="95cb4-793">idcard card#</span></span> 
- <span data-ttu-id="95cb4-794">idcard cards#</span><span class="sxs-lookup"><span data-stu-id="95cb4-794">idcard cards#</span></span> 
- <span data-ttu-id="95cb4-795">idcard #</span><span class="sxs-lookup"><span data-stu-id="95cb4-795">idcard#</span></span> 
- <span data-ttu-id="95cb4-796">identification card#</span><span class="sxs-lookup"><span data-stu-id="95cb4-796">identification card#</span></span> 
- <span data-ttu-id="95cb4-797">identification cards#</span><span class="sxs-lookup"><span data-stu-id="95cb4-797">identification cards#</span></span> 
- <span data-ttu-id="95cb4-798">id</span><span class="sxs-lookup"><span data-stu-id="95cb4-798">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="95cb4-799">加拿大卫生服务号</span><span class="sxs-lookup"><span data-stu-id="95cb4-799">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-800">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-800">Format</span></span>

<span data-ttu-id="95cb4-801">10 个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-801">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-802">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-802">Pattern</span></span>

<span data-ttu-id="95cb4-803">10 个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-803">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-804">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-804">Checksum</span></span>

<span data-ttu-id="95cb4-805">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-805">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-806">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-806">Definition</span></span>

<span data-ttu-id="95cb4-807">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-807">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-808">正则表达式 Regex_canada_health_service_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-808">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-809">找到 Keyword_canada_health_service_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-809">A keyword from Keyword_canada_health_service_number is found.</span></span>

```
<!-- Canada Health Service Number -->
<Entity id="59c0bf39-7fab-482c-af25-00faa4384c94" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_health_service_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_health_service_number" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-810">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-810">Keywords</span></span>

#### <a name="keywordcanadahealthservicenumber"></a><span data-ttu-id="95cb4-811">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="95cb4-811">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="95cb4-812">personal health number</span><span class="sxs-lookup"><span data-stu-id="95cb4-812">personal health number</span></span>
- <span data-ttu-id="95cb4-813">patient information</span><span class="sxs-lookup"><span data-stu-id="95cb4-813">patient information</span></span>
- <span data-ttu-id="95cb4-814">health services</span><span class="sxs-lookup"><span data-stu-id="95cb4-814">health services</span></span>
- <span data-ttu-id="95cb4-815">speciality services</span><span class="sxs-lookup"><span data-stu-id="95cb4-815">speciality services</span></span>
- <span data-ttu-id="95cb4-816">automobile accident</span><span class="sxs-lookup"><span data-stu-id="95cb4-816">automobile accident</span></span>
- <span data-ttu-id="95cb4-817">patient hospital</span><span class="sxs-lookup"><span data-stu-id="95cb4-817">patient hospital</span></span>
- <span data-ttu-id="95cb4-818">psychiatrist</span><span class="sxs-lookup"><span data-stu-id="95cb4-818">psychiatrist</span></span>
- <span data-ttu-id="95cb4-819">workers compensation</span><span class="sxs-lookup"><span data-stu-id="95cb4-819">workers compensation</span></span>
- <span data-ttu-id="95cb4-820">障碍</span><span class="sxs-lookup"><span data-stu-id="95cb4-820">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="95cb4-821">加拿大护照号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-821">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-822">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-822">Format</span></span>

<span data-ttu-id="95cb4-823">两个大写字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-823">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-824">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-824">Pattern</span></span>

<span data-ttu-id="95cb4-825">两个大写字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-825">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-826">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-826">Checksum</span></span>

<span data-ttu-id="95cb4-827">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-827">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-828">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-828">Definition</span></span>

<span data-ttu-id="95cb4-829">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-829">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-830">正则表达式 Regex_canada_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-830">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-831">找到来自 Keyword_canada_passport_number 或 Keyword_passport 的关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-831">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

``` 
<!-- Canada Passport Number -->
<Entity id="14d0db8b-498a-43ed-9fca-f6097ae687eb" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_passport_number" />
          <Match idRef="Keyword_passport" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-832">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-832">Keywords</span></span>

#### <a name="keywordcanadapassportnumber"></a><span data-ttu-id="95cb4-833">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="95cb4-833">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="95cb4-834">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="95cb4-834">canadian citizenship</span></span>
- <span data-ttu-id="95cb4-835">canadian passport</span><span class="sxs-lookup"><span data-stu-id="95cb4-835">canadian passport</span></span>
- <span data-ttu-id="95cb4-836">passport application</span><span class="sxs-lookup"><span data-stu-id="95cb4-836">passport application</span></span>
- <span data-ttu-id="95cb4-837">passport photos</span><span class="sxs-lookup"><span data-stu-id="95cb4-837">passport photos</span></span>
- <span data-ttu-id="95cb4-838">certified translator</span><span class="sxs-lookup"><span data-stu-id="95cb4-838">certified translator</span></span>
- <span data-ttu-id="95cb4-839">canadian citizens</span><span class="sxs-lookup"><span data-stu-id="95cb4-839">canadian citizens</span></span>
- <span data-ttu-id="95cb4-840">processing times</span><span class="sxs-lookup"><span data-stu-id="95cb4-840">processing times</span></span>
- <span data-ttu-id="95cb4-841">renewal application</span><span class="sxs-lookup"><span data-stu-id="95cb4-841">renewal application</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="95cb4-842">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="95cb4-842">Keyword_passport</span></span>

- <span data-ttu-id="95cb4-843">Passport Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-843">Passport Number</span></span>
- <span data-ttu-id="95cb4-844">Passport No</span><span class="sxs-lookup"><span data-stu-id="95cb4-844">Passport No</span></span>
- <span data-ttu-id="95cb4-845">Passport #</span><span class="sxs-lookup"><span data-stu-id="95cb4-845">Passport #</span></span>
- <span data-ttu-id="95cb4-846">登记卡</span><span class="sxs-lookup"><span data-stu-id="95cb4-846">Passport#</span></span>
- <span data-ttu-id="95cb4-847">PassportID</span><span class="sxs-lookup"><span data-stu-id="95cb4-847">PassportID</span></span>
- <span data-ttu-id="95cb4-848">Passportno</span><span class="sxs-lookup"><span data-stu-id="95cb4-848">Passportno</span></span>
- <span data-ttu-id="95cb4-849">passportnumber</span><span class="sxs-lookup"><span data-stu-id="95cb4-849">passportnumber</span></span>
- <span data-ttu-id="95cb4-850">パスポート</span><span class="sxs-lookup"><span data-stu-id="95cb4-850">パスポート</span></span>
- <span data-ttu-id="95cb4-851">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="95cb4-851">パスポート番号</span></span>
- <span data-ttu-id="95cb4-852">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="95cb4-852">パスポートのNum</span></span>
- <span data-ttu-id="95cb4-853">パスポート #</span><span class="sxs-lookup"><span data-stu-id="95cb4-853">パスポート＃</span></span>
- <span data-ttu-id="95cb4-854">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="95cb4-854">Numéro de passeport</span></span>
- <span data-ttu-id="95cb4-855">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="95cb4-855">Passeport n °</span></span>
- <span data-ttu-id="95cb4-856">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="95cb4-856">Passeport Non</span></span>
- <span data-ttu-id="95cb4-857">Passeport #</span><span class="sxs-lookup"><span data-stu-id="95cb4-857">Passeport #</span></span>
- <span data-ttu-id="95cb4-858">Passeport #</span><span class="sxs-lookup"><span data-stu-id="95cb4-858">Passeport#</span></span>
- <span data-ttu-id="95cb4-859">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="95cb4-859">PasseportNon</span></span>
- <span data-ttu-id="95cb4-860">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="95cb4-860">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="95cb4-861">加拿大个人健康标识号 (PHIN)</span><span class="sxs-lookup"><span data-stu-id="95cb4-861">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-862">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-862">Format</span></span>

<span data-ttu-id="95cb4-863">九个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-863">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-864">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-864">Pattern</span></span>

<span data-ttu-id="95cb4-865">九个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-865">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-866">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-866">Checksum</span></span>

<span data-ttu-id="95cb4-867">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-867">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-868">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-868">Definition</span></span>

<span data-ttu-id="95cb4-869">DLP 策略 75% 确信在300个字符的邻近度内检测到此类型的敏感信息: 正则表达式 Regex_canada_phin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-869">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="95cb4-870">找到 Keyword_canada_phin 或 Keyword_canada_provinces 中至少有两个关键字。。</span><span class="sxs-lookup"><span data-stu-id="95cb4-870">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

```
<!-- Canada PHIN -->
<Entity id="722e12ac-c89a-4ec8-a1b7-fea3469f89db" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_phin" />
        <Any minMatches="2">
          <Match idRef="Keyword_canada_phin" />
          <Match idRef="Keyword_canada_provinces" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-871">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-871">Keywords</span></span>

#### <a name="keywordcanadaphin"></a><span data-ttu-id="95cb4-872">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="95cb4-872">Keyword_canada_phin</span></span>

- <span data-ttu-id="95cb4-873">social insurance number</span><span class="sxs-lookup"><span data-stu-id="95cb4-873">social insurance number</span></span>
- <span data-ttu-id="95cb4-874">health information act</span><span class="sxs-lookup"><span data-stu-id="95cb4-874">health information act</span></span>
- <span data-ttu-id="95cb4-875">income tax information</span><span class="sxs-lookup"><span data-stu-id="95cb4-875">income tax information</span></span>
- <span data-ttu-id="95cb4-876">manitoba health</span><span class="sxs-lookup"><span data-stu-id="95cb4-876">manitoba health</span></span>
- <span data-ttu-id="95cb4-877">health registration</span><span class="sxs-lookup"><span data-stu-id="95cb4-877">health registration</span></span>
- <span data-ttu-id="95cb4-878">prescription purchases</span><span class="sxs-lookup"><span data-stu-id="95cb4-878">prescription purchases</span></span>
- <span data-ttu-id="95cb4-879">benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="95cb4-879">benefit eligibility</span></span>
- <span data-ttu-id="95cb4-880">personal health</span><span class="sxs-lookup"><span data-stu-id="95cb4-880">personal health</span></span>
- <span data-ttu-id="95cb4-881">power of attorney</span><span class="sxs-lookup"><span data-stu-id="95cb4-881">power of attorney</span></span>
- <span data-ttu-id="95cb4-882">registration number</span><span class="sxs-lookup"><span data-stu-id="95cb4-882">registration number</span></span>
- <span data-ttu-id="95cb4-883">personal health number</span><span class="sxs-lookup"><span data-stu-id="95cb4-883">personal health number</span></span>
- <span data-ttu-id="95cb4-884">practitioner referral</span><span class="sxs-lookup"><span data-stu-id="95cb4-884">practitioner referral</span></span>
- <span data-ttu-id="95cb4-885">wellness professional</span><span class="sxs-lookup"><span data-stu-id="95cb4-885">wellness professional</span></span>
- <span data-ttu-id="95cb4-886">patient referral</span><span class="sxs-lookup"><span data-stu-id="95cb4-886">patient referral</span></span>
- <span data-ttu-id="95cb4-887">health and wellness</span><span class="sxs-lookup"><span data-stu-id="95cb4-887">health and wellness</span></span>

#### <a name="keywordcanadaprovinces"></a><span data-ttu-id="95cb4-888">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="95cb4-888">Keyword_canada_provinces</span></span>

- <span data-ttu-id="95cb4-889">Nunavut</span><span class="sxs-lookup"><span data-stu-id="95cb4-889">Nunavut</span></span>
- <span data-ttu-id="95cb4-890">省</span><span class="sxs-lookup"><span data-stu-id="95cb4-890">Quebec</span></span>
- <span data-ttu-id="95cb4-891">Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="95cb4-891">Northwest Territories</span></span>
- <span data-ttu-id="95cb4-892">省</span><span class="sxs-lookup"><span data-stu-id="95cb4-892">Ontario</span></span>
- <span data-ttu-id="95cb4-893">British Columbia</span><span class="sxs-lookup"><span data-stu-id="95cb4-893">British Columbia</span></span>
- <span data-ttu-id="95cb4-894">Alberta</span><span class="sxs-lookup"><span data-stu-id="95cb4-894">Alberta</span></span>
- <span data-ttu-id="95cb4-895">彻</span><span class="sxs-lookup"><span data-stu-id="95cb4-895">Saskatchewan</span></span>
- <span data-ttu-id="95cb4-896">Manitoba</span><span class="sxs-lookup"><span data-stu-id="95cb4-896">Manitoba</span></span>
- <span data-ttu-id="95cb4-897">Yukon</span><span class="sxs-lookup"><span data-stu-id="95cb4-897">Yukon</span></span>
- <span data-ttu-id="95cb4-898">Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="95cb4-898">Newfoundland and Labrador</span></span>
- <span data-ttu-id="95cb4-899">New Brunswick</span><span class="sxs-lookup"><span data-stu-id="95cb4-899">New Brunswick</span></span>
- <span data-ttu-id="95cb4-900">Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="95cb4-900">Nova Scotia</span></span>
- <span data-ttu-id="95cb4-901">Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="95cb4-901">Prince Edward Island</span></span>
- <span data-ttu-id="95cb4-902">加拿大</span><span class="sxs-lookup"><span data-stu-id="95cb4-902">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="95cb4-903">加拿大社会保险号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-903">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-904">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-904">Format</span></span>

<span data-ttu-id="95cb4-905">九个数字，包含可选连字符或空格</span><span class="sxs-lookup"><span data-stu-id="95cb4-905">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-906">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-906">Pattern</span></span>

<span data-ttu-id="95cb4-907">格式</span><span class="sxs-lookup"><span data-stu-id="95cb4-907">Formatted:</span></span>
- <span data-ttu-id="95cb4-908">三个数字 </span><span class="sxs-lookup"><span data-stu-id="95cb4-908">Three digits</span></span> 
- <span data-ttu-id="95cb4-909">连字符或空格</span><span class="sxs-lookup"><span data-stu-id="95cb4-909">A hyphen or space</span></span> 
- <span data-ttu-id="95cb4-910">三位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-910">Three digits</span></span> 
- <span data-ttu-id="95cb4-911">连字符或空格</span><span class="sxs-lookup"><span data-stu-id="95cb4-911">A hyphen or space</span></span> 
- <span data-ttu-id="95cb4-912">三位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-912">Three digits</span></span>

<span data-ttu-id="95cb4-913">未格式化: 9 个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-913">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-914">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-914">Checksum</span></span>

<span data-ttu-id="95cb4-915">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-915">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-916">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-916">Definition</span></span>

<span data-ttu-id="95cb4-917">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-917">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-918">函数 Func_canadian_sin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-918">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-919">至少两个以下任意组合：</span><span class="sxs-lookup"><span data-stu-id="95cb4-919">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="95cb4-920">找到 Keyword_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-920">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="95cb4-921">找到 Keyword_sin_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-921">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="95cb4-922">函数 Func_eu_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="95cb4-922">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="95cb4-923">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-923">The checksum passes.</span></span>

<span data-ttu-id="95cb4-924">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-924">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-925">函数 Func_unformatted_canadian_sin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-925">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-926">找到 Keyword_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-926">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="95cb4-927">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-927">The checksum passes.</span></span>

```
<!-- Canada Social Insurance Number -->
<Entity id="a2f29c85-ecb8-4514-a610-364790c0773e" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_canadian_sin" />
        <Any minMatches="2">
          <Match idRef="Keyword_sin" />
          <Match idRef="Keyword_sin_collaborative" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_canadian_sin" />
        <Match idRef="Keyword_sin" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-928">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-928">Keywords</span></span>

#### <a name="keywordsin"></a><span data-ttu-id="95cb4-929">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="95cb4-929">Keyword_sin</span></span>

- <span data-ttu-id="95cb4-930">sin</span><span class="sxs-lookup"><span data-stu-id="95cb4-930">sin</span></span> 
- <span data-ttu-id="95cb4-931">social insurance</span><span class="sxs-lookup"><span data-stu-id="95cb4-931">social insurance</span></span> 
- <span data-ttu-id="95cb4-932">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="95cb4-932">numero d'assurance sociale</span></span> 
- <span data-ttu-id="95cb4-933">罪</span><span class="sxs-lookup"><span data-stu-id="95cb4-933">sins</span></span> 
- <span data-ttu-id="95cb4-934">ssn</span><span class="sxs-lookup"><span data-stu-id="95cb4-934">ssn</span></span> 
- <span data-ttu-id="95cb4-935">ssn</span><span class="sxs-lookup"><span data-stu-id="95cb4-935">ssns</span></span> 
- <span data-ttu-id="95cb4-936">social security</span><span class="sxs-lookup"><span data-stu-id="95cb4-936">social security</span></span> 
- <span data-ttu-id="95cb4-937">numero d'assurance social</span><span class="sxs-lookup"><span data-stu-id="95cb4-937">numero d'assurance social</span></span> 
- <span data-ttu-id="95cb4-938">national identification number</span><span class="sxs-lookup"><span data-stu-id="95cb4-938">national identification number</span></span> 
- <span data-ttu-id="95cb4-939">national id</span><span class="sxs-lookup"><span data-stu-id="95cb4-939">national id</span></span> 
- <span data-ttu-id="95cb4-940">sin</span><span class="sxs-lookup"><span data-stu-id="95cb4-940">sin#</span></span> 
- <span data-ttu-id="95cb4-941">soc ins</span><span class="sxs-lookup"><span data-stu-id="95cb4-941">soc ins</span></span> 
- <span data-ttu-id="95cb4-942">social ins</span><span class="sxs-lookup"><span data-stu-id="95cb4-942">social ins</span></span> 

#### <a name="keywordsincollaborative"></a><span data-ttu-id="95cb4-943">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="95cb4-943">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="95cb4-944">driver's license</span><span class="sxs-lookup"><span data-stu-id="95cb4-944">driver's license</span></span> 
- <span data-ttu-id="95cb4-945">drivers license</span><span class="sxs-lookup"><span data-stu-id="95cb4-945">drivers license</span></span> 
- <span data-ttu-id="95cb4-946">driver's licence</span><span class="sxs-lookup"><span data-stu-id="95cb4-946">driver's licence</span></span> 
- <span data-ttu-id="95cb4-947">drivers licence</span><span class="sxs-lookup"><span data-stu-id="95cb4-947">drivers licence</span></span> 
- <span data-ttu-id="95cb4-948">DOB</span><span class="sxs-lookup"><span data-stu-id="95cb4-948">DOB</span></span> 
- <span data-ttu-id="95cb4-949">出生日期</span><span class="sxs-lookup"><span data-stu-id="95cb4-949">Birthdate</span></span> 
- <span data-ttu-id="95cb4-950">生日</span><span class="sxs-lookup"><span data-stu-id="95cb4-950">Birthday</span></span> 
- <span data-ttu-id="95cb4-951">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="95cb4-951">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="95cb4-952">	智利身份证号</span><span class="sxs-lookup"><span data-stu-id="95cb4-952">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-953">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-953">Format</span></span>

<span data-ttu-id="95cb4-954">7-8 位数加上分隔符一个校验位或字母</span><span class="sxs-lookup"><span data-stu-id="95cb4-954">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-955">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-955">Pattern</span></span>

<span data-ttu-id="95cb4-956">7-8 个数字加分隔符：</span><span class="sxs-lookup"><span data-stu-id="95cb4-956">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="95cb4-957">1-2 个数字 </span><span class="sxs-lookup"><span data-stu-id="95cb4-957">1-2 digits</span></span> 
- <span data-ttu-id="95cb4-958">一个点 </span><span class="sxs-lookup"><span data-stu-id="95cb4-958">A period</span></span> 
- <span data-ttu-id="95cb4-959">三位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-959">Three digits</span></span> 
- <span data-ttu-id="95cb4-960">一个点 </span><span class="sxs-lookup"><span data-stu-id="95cb4-960">A period</span></span> 
- <span data-ttu-id="95cb4-961">三位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-961">Three digits</span></span> 
- <span data-ttu-id="95cb4-962">一个短划线 </span><span class="sxs-lookup"><span data-stu-id="95cb4-962">A dash</span></span> 
- <span data-ttu-id="95cb4-963">一个数字或字母（不区分大小写），是校验位</span><span class="sxs-lookup"><span data-stu-id="95cb4-963">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-964">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-964">Checksum</span></span>

<span data-ttu-id="95cb4-965">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-965">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-966">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-966">Definition</span></span>

<span data-ttu-id="95cb4-967">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-967">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-968">函数 Func_chile_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-968">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-969">找到 Keyword_chile_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-969">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="95cb4-970">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-970">The checksum passes.</span></span>

<span data-ttu-id="95cb4-971">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-971">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-972">函数 Func_chile_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-972">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-973">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-973">The checksum passes.</span></span>

```
<!-- Chile Identity Card Number -->
<Entity id="4e979794-49a0-407e-a0b9-2c536937b925" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_chile_id_card"/>
     <Match idRef="Keyword_chile_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_chile_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-974">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-974">Keywords</span></span>

#### <a name="keywordchileidcard"></a><span data-ttu-id="95cb4-975">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="95cb4-975">Keyword_chile_id_card</span></span>

- <span data-ttu-id="95cb4-976">National Identification Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-976">National Identification Number</span></span> 
- <span data-ttu-id="95cb4-977">Identity card</span><span class="sxs-lookup"><span data-stu-id="95cb4-977">Identity card</span></span> 
- <span data-ttu-id="95cb4-978">ID</span><span class="sxs-lookup"><span data-stu-id="95cb4-978">ID</span></span> 
- <span data-ttu-id="95cb4-979">id</span><span class="sxs-lookup"><span data-stu-id="95cb4-979">Identification</span></span> 
- <span data-ttu-id="95cb4-980">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="95cb4-980">Rol Único Nacional</span></span> 
- <span data-ttu-id="95cb4-981">以</span><span class="sxs-lookup"><span data-stu-id="95cb4-981">RUN</span></span> 
- <span data-ttu-id="95cb4-982">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="95cb4-982">Rol Único Tributario</span></span> 
- <span data-ttu-id="95cb4-983">墨守成规</span><span class="sxs-lookup"><span data-stu-id="95cb4-983">RUT</span></span> 
- <span data-ttu-id="95cb4-984">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="95cb4-984">Cédula de Identidad</span></span> 
- <span data-ttu-id="95cb4-985">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="95cb4-985">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="95cb4-986">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="95cb4-986">Tarjeta de identificación</span></span> 
- <span data-ttu-id="95cb4-987">Identificación</span><span class="sxs-lookup"><span data-stu-id="95cb4-987">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="95cb4-988">	中国居民身份证号</span><span class="sxs-lookup"><span data-stu-id="95cb4-988">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-989">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-989">Format</span></span>

<span data-ttu-id="95cb4-990">18 个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-990">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-991">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-991">Pattern</span></span>

<span data-ttu-id="95cb4-992">18 个数字：</span><span class="sxs-lookup"><span data-stu-id="95cb4-992">18 digits:</span></span>
- <span data-ttu-id="95cb4-993">其中六个数字是地址代码 </span><span class="sxs-lookup"><span data-stu-id="95cb4-993">Six digits which are an address code</span></span> 
- <span data-ttu-id="95cb4-994">八个数字，采用  YYYYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="95cb4-994">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="95cb4-995">三个数字，是顺序代码 </span><span class="sxs-lookup"><span data-stu-id="95cb4-995">Three digits which are an order code</span></span> 
- <span data-ttu-id="95cb4-996">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="95cb4-996">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-997">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-997">Checksum</span></span>

<span data-ttu-id="95cb4-998">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-998">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-999">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-999">Definition</span></span>

<span data-ttu-id="95cb4-1000">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-1000">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-1001">函数 Func_china_resident_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1001">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-1002">找到 Keyword_china_resident_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1002">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="95cb4-1003">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1003">The checksum passes.</span></span>

<span data-ttu-id="95cb4-1004">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-1004">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-1005">函数 Func_china_resident_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1005">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-1006">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1006">The checksum passes.</span></span>

```
<!-- China Resident Identity Card (PRC) Number -->
<Entity id="c92daa86-2d16-4871-901f-816b3f554fc1" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_china_resident_id"/>
     <Match idRef="Keyword_china_resident_id"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_china_resident_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-1007">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1007">Keywords</span></span>

### <a name="keywordchinaresidentid"></a><span data-ttu-id="95cb4-1008">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="95cb4-1008">Keyword_china_resident_id</span></span>

- <span data-ttu-id="95cb4-1009">Resident Identity Card</span><span class="sxs-lookup"><span data-stu-id="95cb4-1009">Resident Identity Card</span></span> 
- <span data-ttu-id="95cb4-1010">台湾</span><span class="sxs-lookup"><span data-stu-id="95cb4-1010">PRC</span></span> 
- <span data-ttu-id="95cb4-1011">National Identification Card</span><span class="sxs-lookup"><span data-stu-id="95cb4-1011">National Identification Card</span></span> 
- <span data-ttu-id="95cb4-1012">身份证</span><span class="sxs-lookup"><span data-stu-id="95cb4-1012">身份证</span></span> 
- <span data-ttu-id="95cb4-1013">居民 身份证</span><span class="sxs-lookup"><span data-stu-id="95cb4-1013">居民 身份证</span></span> 
- <span data-ttu-id="95cb4-1014">居民身份证</span><span class="sxs-lookup"><span data-stu-id="95cb4-1014">居民身份证</span></span> 
- <span data-ttu-id="95cb4-1015">鉴定</span><span class="sxs-lookup"><span data-stu-id="95cb4-1015">鉴定</span></span> 
- <span data-ttu-id="95cb4-1016">身分證</span><span class="sxs-lookup"><span data-stu-id="95cb4-1016">身分證</span></span> 
- <span data-ttu-id="95cb4-1017">居民身份證</span><span class="sxs-lookup"><span data-stu-id="95cb4-1017">居民 身份證</span></span>
- <span data-ttu-id="95cb4-1018">鑑定</span><span class="sxs-lookup"><span data-stu-id="95cb4-1018">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="95cb4-1019">信用卡号</span><span class="sxs-lookup"><span data-stu-id="95cb4-1019">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-1020">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-1020">Format</span></span>

<span data-ttu-id="95cb4-1021">16个数字, 可以是格式化或无格式 (dddddddddddddddd), 并且必须通过 Luhn 测试。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1021">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-1022">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-1022">Pattern</span></span>

<span data-ttu-id="95cb4-1023">非常复杂且强大的模式，检测到来自世界各地所有重要品牌的卡，包括 Visa、万事达卡、发现卡、JCB卡、美国运通卡、礼品卡以及大莱卡。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1023">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-1024">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-1024">Checksum</span></span>

<span data-ttu-id="95cb4-1025">是，Luhn 校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-1025">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-1026">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-1026">Definition</span></span>

<span data-ttu-id="95cb4-1027">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-1027">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-1028">函数 Func_credit_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1028">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-1029">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="95cb4-1029">One of the following is true:</span></span>
    - <span data-ttu-id="95cb4-1030">找到 Keyword_cc_verification 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1030">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="95cb4-1031">找到 Keyword_cc_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1031">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="95cb4-1032">函数 Func_expiration_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1032">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="95cb4-1033">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1033">The checksum passes.</span></span>

<span data-ttu-id="95cb4-1034">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-1034">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-1035">函数 Func_credit_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1035">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-1036">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1036">The checksum passes.</span></span>

```
<!-- Credit Card Number -->
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_credit_card" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-1037">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1037">Keywords</span></span>

#### <a name="keywordccverification"></a><span data-ttu-id="95cb4-1038">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="95cb4-1038">Keyword_cc_verification</span></span>

- <span data-ttu-id="95cb4-1039">card verification</span><span class="sxs-lookup"><span data-stu-id="95cb4-1039">card verification</span></span>
- <span data-ttu-id="95cb4-1040">card identification number</span><span class="sxs-lookup"><span data-stu-id="95cb4-1040">card identification number</span></span>
- <span data-ttu-id="95cb4-1041">cvn</span><span class="sxs-lookup"><span data-stu-id="95cb4-1041">cvn</span></span>
- <span data-ttu-id="95cb4-1042">cid</span><span class="sxs-lookup"><span data-stu-id="95cb4-1042">cid</span></span>
- <span data-ttu-id="95cb4-1043">cvc2</span><span class="sxs-lookup"><span data-stu-id="95cb4-1043">cvc2</span></span>
- <span data-ttu-id="95cb4-1044">cvv2</span><span class="sxs-lookup"><span data-stu-id="95cb4-1044">cvv2</span></span>
- <span data-ttu-id="95cb4-1045">pin block</span><span class="sxs-lookup"><span data-stu-id="95cb4-1045">pin block</span></span>
- <span data-ttu-id="95cb4-1046">security code</span><span class="sxs-lookup"><span data-stu-id="95cb4-1046">security code</span></span>
- <span data-ttu-id="95cb4-1047">security number</span><span class="sxs-lookup"><span data-stu-id="95cb4-1047">security number</span></span>
- <span data-ttu-id="95cb4-1048">security no</span><span class="sxs-lookup"><span data-stu-id="95cb4-1048">security no</span></span>
- <span data-ttu-id="95cb4-1049">issue number</span><span class="sxs-lookup"><span data-stu-id="95cb4-1049">issue number</span></span>
- <span data-ttu-id="95cb4-1050">issue no</span><span class="sxs-lookup"><span data-stu-id="95cb4-1050">issue no</span></span>
- <span data-ttu-id="95cb4-1051">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="95cb4-1051">cryptogramme</span></span>
- <span data-ttu-id="95cb4-1052">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="95cb4-1052">numéro de sécurité</span></span>
- <span data-ttu-id="95cb4-1053">numero de securite</span><span class="sxs-lookup"><span data-stu-id="95cb4-1053">numero de securite</span></span>
- <span data-ttu-id="95cb4-1054">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="95cb4-1054">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="95cb4-1055">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="95cb4-1055">kreditkartenprufnummer</span></span>
- <span data-ttu-id="95cb4-1056">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="95cb4-1056">prüfziffer</span></span>
- <span data-ttu-id="95cb4-1057">prufziffer</span><span class="sxs-lookup"><span data-stu-id="95cb4-1057">prufziffer</span></span>
- <span data-ttu-id="95cb4-1058">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="95cb4-1058">sicherheits Kode</span></span>
- <span data-ttu-id="95cb4-1059">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="95cb4-1059">sicherheitscode</span></span>
- <span data-ttu-id="95cb4-1060">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="95cb4-1060">sicherheitsnummer</span></span>
- <span data-ttu-id="95cb4-1061">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="95cb4-1061">verfalldatum</span></span>
- <span data-ttu-id="95cb4-1062">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="95cb4-1062">codice di verifica</span></span>
- <span data-ttu-id="95cb4-1063">货.</span><span class="sxs-lookup"><span data-stu-id="95cb4-1063">cod.</span></span> <span data-ttu-id="95cb4-1064">sicurezza</span><span class="sxs-lookup"><span data-stu-id="95cb4-1064">sicurezza</span></span>
- <span data-ttu-id="95cb4-1065">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="95cb4-1065">cod sicurezza</span></span>
- <span data-ttu-id="95cb4-1066">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="95cb4-1066">n autorizzazione</span></span>
- <span data-ttu-id="95cb4-1067">código</span><span class="sxs-lookup"><span data-stu-id="95cb4-1067">código</span></span>
- <span data-ttu-id="95cb4-1068">codigo</span><span class="sxs-lookup"><span data-stu-id="95cb4-1068">codigo</span></span>
- <span data-ttu-id="95cb4-1069">货.</span><span class="sxs-lookup"><span data-stu-id="95cb4-1069">cod.</span></span> <span data-ttu-id="95cb4-1070">seg</span><span class="sxs-lookup"><span data-stu-id="95cb4-1070">seg</span></span>
- <span data-ttu-id="95cb4-1071">cod seg</span><span class="sxs-lookup"><span data-stu-id="95cb4-1071">cod seg</span></span>
- <span data-ttu-id="95cb4-1072">código de segurança</span><span class="sxs-lookup"><span data-stu-id="95cb4-1072">código de segurança</span></span>
- <span data-ttu-id="95cb4-1073">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="95cb4-1073">codigo de seguranca</span></span>
- <span data-ttu-id="95cb4-1074">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="95cb4-1074">codigo de segurança</span></span>
- <span data-ttu-id="95cb4-1075">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="95cb4-1075">código de seguranca</span></span>
- <span data-ttu-id="95cb4-1076">cód。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1076">cód.</span></span> <span data-ttu-id="95cb4-1077">segurança</span><span class="sxs-lookup"><span data-stu-id="95cb4-1077">segurança</span></span>
- <span data-ttu-id="95cb4-1078">货.</span><span class="sxs-lookup"><span data-stu-id="95cb4-1078">cod.</span></span> <span data-ttu-id="95cb4-1079">seguranca 货到付款。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1079">seguranca cod.</span></span> <span data-ttu-id="95cb4-1080">segurança</span><span class="sxs-lookup"><span data-stu-id="95cb4-1080">segurança</span></span>
- <span data-ttu-id="95cb4-1081">cód。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1081">cód.</span></span> <span data-ttu-id="95cb4-1082">seguranca</span><span class="sxs-lookup"><span data-stu-id="95cb4-1082">seguranca</span></span>
- <span data-ttu-id="95cb4-1083">cód segurança</span><span class="sxs-lookup"><span data-stu-id="95cb4-1083">cód segurança</span></span>
- <span data-ttu-id="95cb4-1084">货到付款 seguranca 货到付款 segurança</span><span class="sxs-lookup"><span data-stu-id="95cb4-1084">cod seguranca cod segurança</span></span>
- <span data-ttu-id="95cb4-1085">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="95cb4-1085">cód seguranca</span></span>
- <span data-ttu-id="95cb4-1086">número de verificação</span><span class="sxs-lookup"><span data-stu-id="95cb4-1086">número de verificação</span></span>
- <span data-ttu-id="95cb4-1087">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="95cb4-1087">numero de verificacao</span></span>
- <span data-ttu-id="95cb4-1088">ablauf</span><span class="sxs-lookup"><span data-stu-id="95cb4-1088">ablauf</span></span>
- <span data-ttu-id="95cb4-1089">gültig bis</span><span class="sxs-lookup"><span data-stu-id="95cb4-1089">gültig bis</span></span>
- <span data-ttu-id="95cb4-1090">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="95cb4-1090">gültigkeitsdatum</span></span>
- <span data-ttu-id="95cb4-1091">gultig bis</span><span class="sxs-lookup"><span data-stu-id="95cb4-1091">gultig bis</span></span>
- <span data-ttu-id="95cb4-1092">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="95cb4-1092">gultigkeitsdatum</span></span>
- <span data-ttu-id="95cb4-1093">scadenza</span><span class="sxs-lookup"><span data-stu-id="95cb4-1093">scadenza</span></span>
- <span data-ttu-id="95cb4-1094">data scad</span><span class="sxs-lookup"><span data-stu-id="95cb4-1094">data scad</span></span>
- <span data-ttu-id="95cb4-1095">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="95cb4-1095">fecha de expiracion</span></span>
- <span data-ttu-id="95cb4-1096">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="95cb4-1096">fecha de venc</span></span>
- <span data-ttu-id="95cb4-1097">vencimiento</span><span class="sxs-lookup"><span data-stu-id="95cb4-1097">vencimiento</span></span>
- <span data-ttu-id="95cb4-1098">válido hasta</span><span class="sxs-lookup"><span data-stu-id="95cb4-1098">válido hasta</span></span>
- <span data-ttu-id="95cb4-1099">valido hasta</span><span class="sxs-lookup"><span data-stu-id="95cb4-1099">valido hasta</span></span>
- <span data-ttu-id="95cb4-1100">vto</span><span class="sxs-lookup"><span data-stu-id="95cb4-1100">vto</span></span>
- <span data-ttu-id="95cb4-1101">data de expiração</span><span class="sxs-lookup"><span data-stu-id="95cb4-1101">data de expiração</span></span>
- <span data-ttu-id="95cb4-1102">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="95cb4-1102">data de expiracao</span></span>
- <span data-ttu-id="95cb4-1103">data em que expira</span><span class="sxs-lookup"><span data-stu-id="95cb4-1103">data em que expira</span></span>
- <span data-ttu-id="95cb4-1104">validade</span><span class="sxs-lookup"><span data-stu-id="95cb4-1104">validade</span></span>
- <span data-ttu-id="95cb4-1105">valor</span><span class="sxs-lookup"><span data-stu-id="95cb4-1105">valor</span></span>
- <span data-ttu-id="95cb4-1106">vencimento</span><span class="sxs-lookup"><span data-stu-id="95cb4-1106">vencimento</span></span>
- <span data-ttu-id="95cb4-1107">Venc</span><span class="sxs-lookup"><span data-stu-id="95cb4-1107">Venc</span></span> 

#### <a name="keywordccname"></a><span data-ttu-id="95cb4-1108">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="95cb4-1108">Keyword_cc_name</span></span>

- <span data-ttu-id="95cb4-1109">amex</span><span class="sxs-lookup"><span data-stu-id="95cb4-1109">amex</span></span>
- <span data-ttu-id="95cb4-1110">american express</span><span class="sxs-lookup"><span data-stu-id="95cb4-1110">american express</span></span>
- <span data-ttu-id="95cb4-1111">americanexpress</span><span class="sxs-lookup"><span data-stu-id="95cb4-1111">americanexpress</span></span>
- <span data-ttu-id="95cb4-1112">反之</span><span class="sxs-lookup"><span data-stu-id="95cb4-1112">Visa</span></span>
- <span data-ttu-id="95cb4-1113">mastercard</span><span class="sxs-lookup"><span data-stu-id="95cb4-1113">mastercard</span></span>
- <span data-ttu-id="95cb4-1114">Master Card</span><span class="sxs-lookup"><span data-stu-id="95cb4-1114">master card</span></span>
- <span data-ttu-id="95cb4-1115">emc</span><span class="sxs-lookup"><span data-stu-id="95cb4-1115">mc</span></span> 
- <span data-ttu-id="95cb4-1116">mastercards</span><span class="sxs-lookup"><span data-stu-id="95cb4-1116">mastercards</span></span>
- <span data-ttu-id="95cb4-1117">master cards</span><span class="sxs-lookup"><span data-stu-id="95cb4-1117">master cards</span></span>
- <span data-ttu-id="95cb4-1118">diner's Club</span><span class="sxs-lookup"><span data-stu-id="95cb4-1118">diner's Club</span></span>
- <span data-ttu-id="95cb4-1119">diners club</span><span class="sxs-lookup"><span data-stu-id="95cb4-1119">diners club</span></span>
- <span data-ttu-id="95cb4-1120">dinersclub</span><span class="sxs-lookup"><span data-stu-id="95cb4-1120">dinersclub</span></span>
- <span data-ttu-id="95cb4-1121">discover card</span><span class="sxs-lookup"><span data-stu-id="95cb4-1121">discover card</span></span>
- <span data-ttu-id="95cb4-1122">discovercard</span><span class="sxs-lookup"><span data-stu-id="95cb4-1122">discovercard</span></span>
- <span data-ttu-id="95cb4-1123">discover cards</span><span class="sxs-lookup"><span data-stu-id="95cb4-1123">discover cards</span></span>
- <span data-ttu-id="95cb4-1124">JCB</span><span class="sxs-lookup"><span data-stu-id="95cb4-1124">JCB</span></span>
- <span data-ttu-id="95cb4-1125">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="95cb4-1125">japanese card bureau</span></span>
- <span data-ttu-id="95cb4-1126">carte blanche</span><span class="sxs-lookup"><span data-stu-id="95cb4-1126">carte blanche</span></span>
- <span data-ttu-id="95cb4-1127">carteblanche</span><span class="sxs-lookup"><span data-stu-id="95cb4-1127">carteblanche</span></span>
- <span data-ttu-id="95cb4-1128">credit card</span><span class="sxs-lookup"><span data-stu-id="95cb4-1128">credit card</span></span>
- <span data-ttu-id="95cb4-1129">收件人</span><span class="sxs-lookup"><span data-stu-id="95cb4-1129">cc#</span></span>
- <span data-ttu-id="95cb4-1130">cc #:</span><span class="sxs-lookup"><span data-stu-id="95cb4-1130">cc#:</span></span>
- <span data-ttu-id="95cb4-1131">expiration date</span><span class="sxs-lookup"><span data-stu-id="95cb4-1131">expiration date</span></span>
- <span data-ttu-id="95cb4-1132">exp date</span><span class="sxs-lookup"><span data-stu-id="95cb4-1132">exp date</span></span>
- <span data-ttu-id="95cb4-1133">expiry date</span><span class="sxs-lookup"><span data-stu-id="95cb4-1133">expiry date</span></span>
- <span data-ttu-id="95cb4-1134">date d’expiration</span><span class="sxs-lookup"><span data-stu-id="95cb4-1134">date d’expiration</span></span>
- <span data-ttu-id="95cb4-1135">date d'exp</span><span class="sxs-lookup"><span data-stu-id="95cb4-1135">date d'exp</span></span>
- <span data-ttu-id="95cb4-1136">date expiration</span><span class="sxs-lookup"><span data-stu-id="95cb4-1136">date expiration</span></span>
- <span data-ttu-id="95cb4-1137">bank card</span><span class="sxs-lookup"><span data-stu-id="95cb4-1137">bank card</span></span>
- <span data-ttu-id="95cb4-1138">bankcard</span><span class="sxs-lookup"><span data-stu-id="95cb4-1138">bankcard</span></span>
- <span data-ttu-id="95cb4-1139">card number</span><span class="sxs-lookup"><span data-stu-id="95cb4-1139">card number</span></span>
- <span data-ttu-id="95cb4-1140">card num</span><span class="sxs-lookup"><span data-stu-id="95cb4-1140">card num</span></span>
- <span data-ttu-id="95cb4-1141">cardnumber</span><span class="sxs-lookup"><span data-stu-id="95cb4-1141">cardnumber</span></span>
- <span data-ttu-id="95cb4-1142">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="95cb4-1142">cardnumbers</span></span>
- <span data-ttu-id="95cb4-1143">card numbers</span><span class="sxs-lookup"><span data-stu-id="95cb4-1143">card numbers</span></span>
- <span data-ttu-id="95cb4-1144">creditcard</span><span class="sxs-lookup"><span data-stu-id="95cb4-1144">creditcard</span></span>
- <span data-ttu-id="95cb4-1145">credit cards</span><span class="sxs-lookup"><span data-stu-id="95cb4-1145">credit cards</span></span>
- <span data-ttu-id="95cb4-1146">creditcards</span><span class="sxs-lookup"><span data-stu-id="95cb4-1146">creditcards</span></span>
- <span data-ttu-id="95cb4-1147">ccn</span><span class="sxs-lookup"><span data-stu-id="95cb4-1147">ccn</span></span>
- <span data-ttu-id="95cb4-1148">card holder</span><span class="sxs-lookup"><span data-stu-id="95cb4-1148">card holder</span></span>
- <span data-ttu-id="95cb4-1149">持卡人</span><span class="sxs-lookup"><span data-stu-id="95cb4-1149">cardholder</span></span>
- <span data-ttu-id="95cb4-1150">card holders</span><span class="sxs-lookup"><span data-stu-id="95cb4-1150">card holders</span></span>
- <span data-ttu-id="95cb4-1151">cardholders</span><span class="sxs-lookup"><span data-stu-id="95cb4-1151">cardholders</span></span>
- <span data-ttu-id="95cb4-1152">check card</span><span class="sxs-lookup"><span data-stu-id="95cb4-1152">check card</span></span>
- <span data-ttu-id="95cb4-1153">checkcard</span><span class="sxs-lookup"><span data-stu-id="95cb4-1153">checkcard</span></span>
- <span data-ttu-id="95cb4-1154">check cards</span><span class="sxs-lookup"><span data-stu-id="95cb4-1154">check cards</span></span>
- <span data-ttu-id="95cb4-1155">checkcards</span><span class="sxs-lookup"><span data-stu-id="95cb4-1155">checkcards</span></span>
- <span data-ttu-id="95cb4-1156">debit card</span><span class="sxs-lookup"><span data-stu-id="95cb4-1156">debit card</span></span>
- <span data-ttu-id="95cb4-1157">debitcard</span><span class="sxs-lookup"><span data-stu-id="95cb4-1157">debitcard</span></span>
- <span data-ttu-id="95cb4-1158">debit cards</span><span class="sxs-lookup"><span data-stu-id="95cb4-1158">debit cards</span></span>
- <span data-ttu-id="95cb4-1159">debitcards</span><span class="sxs-lookup"><span data-stu-id="95cb4-1159">debitcards</span></span>
- <span data-ttu-id="95cb4-1160">atm card</span><span class="sxs-lookup"><span data-stu-id="95cb4-1160">atm card</span></span>
- <span data-ttu-id="95cb4-1161">atmcard</span><span class="sxs-lookup"><span data-stu-id="95cb4-1161">atmcard</span></span>
- <span data-ttu-id="95cb4-1162">atm cards</span><span class="sxs-lookup"><span data-stu-id="95cb4-1162">atm cards</span></span>
- <span data-ttu-id="95cb4-1163">atmcards</span><span class="sxs-lookup"><span data-stu-id="95cb4-1163">atmcards</span></span>
- <span data-ttu-id="95cb4-1164">enroute</span><span class="sxs-lookup"><span data-stu-id="95cb4-1164">enroute</span></span>
- <span data-ttu-id="95cb4-1165">en route</span><span class="sxs-lookup"><span data-stu-id="95cb4-1165">en route</span></span>
- <span data-ttu-id="95cb4-1166">card type</span><span class="sxs-lookup"><span data-stu-id="95cb4-1166">card type</span></span>
- <span data-ttu-id="95cb4-1167">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="95cb4-1167">carte bancaire</span></span>
- <span data-ttu-id="95cb4-1168">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="95cb4-1168">carte de crédit</span></span>
- <span data-ttu-id="95cb4-1169">carte de credit</span><span class="sxs-lookup"><span data-stu-id="95cb4-1169">carte de credit</span></span>
- <span data-ttu-id="95cb4-1170">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="95cb4-1170">numéro de carte</span></span>
- <span data-ttu-id="95cb4-1171">numero de carte</span><span class="sxs-lookup"><span data-stu-id="95cb4-1171">numero de carte</span></span>
- <span data-ttu-id="95cb4-1172">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="95cb4-1172">nº de la carte</span></span>
- <span data-ttu-id="95cb4-1173">nº de carte</span><span class="sxs-lookup"><span data-stu-id="95cb4-1173">nº de carte</span></span>
- <span data-ttu-id="95cb4-1174">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="95cb4-1174">kreditkarte</span></span>
- <span data-ttu-id="95cb4-1175">karte</span><span class="sxs-lookup"><span data-stu-id="95cb4-1175">karte</span></span>
- <span data-ttu-id="95cb4-1176">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="95cb4-1176">karteninhaber</span></span>
- <span data-ttu-id="95cb4-1177">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="95cb4-1177">karteninhabers</span></span>
- <span data-ttu-id="95cb4-1178">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="95cb4-1178">kreditkarteninhaber</span></span>
- <span data-ttu-id="95cb4-1179">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="95cb4-1179">kreditkarteninstitut</span></span>
- <span data-ttu-id="95cb4-1180">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="95cb4-1180">kreditkartentyp</span></span>
- <span data-ttu-id="95cb4-1181">eigentümername</span><span class="sxs-lookup"><span data-stu-id="95cb4-1181">eigentümername</span></span>
- <span data-ttu-id="95cb4-1182">kartennr</span><span class="sxs-lookup"><span data-stu-id="95cb4-1182">kartennr</span></span> 
- <span data-ttu-id="95cb4-1183">kartennummer</span><span class="sxs-lookup"><span data-stu-id="95cb4-1183">kartennummer</span></span>
- <span data-ttu-id="95cb4-1184">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="95cb4-1184">kreditkartennummer</span></span>
- <span data-ttu-id="95cb4-1185">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="95cb4-1185">kreditkarten-nummer</span></span>
- <span data-ttu-id="95cb4-1186">carta di credito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1186">carta di credito</span></span>
- <span data-ttu-id="95cb4-1187">carta credito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1187">carta credito</span></span>
- <span data-ttu-id="95cb4-1188">carta</span><span class="sxs-lookup"><span data-stu-id="95cb4-1188">carta</span></span>
- <span data-ttu-id="95cb4-1189">n carta</span><span class="sxs-lookup"><span data-stu-id="95cb4-1189">n carta</span></span>
- <span data-ttu-id="95cb4-1190">führerschein-nr.</span><span class="sxs-lookup"><span data-stu-id="95cb4-1190">nr.</span></span> <span data-ttu-id="95cb4-1191">carta</span><span class="sxs-lookup"><span data-stu-id="95cb4-1191">carta</span></span>
- <span data-ttu-id="95cb4-1192">nr carta</span><span class="sxs-lookup"><span data-stu-id="95cb4-1192">nr carta</span></span>
- <span data-ttu-id="95cb4-1193">numero carta</span><span class="sxs-lookup"><span data-stu-id="95cb4-1193">numero carta</span></span>
- <span data-ttu-id="95cb4-1194">numero della carta</span><span class="sxs-lookup"><span data-stu-id="95cb4-1194">numero della carta</span></span>
- <span data-ttu-id="95cb4-1195">numero di carta</span><span class="sxs-lookup"><span data-stu-id="95cb4-1195">numero di carta</span></span>
- <span data-ttu-id="95cb4-1196">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1196">tarjeta credito</span></span>
- <span data-ttu-id="95cb4-1197">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1197">tarjeta de credito</span></span>
- <span data-ttu-id="95cb4-1198">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1198">tarjeta crédito</span></span>
- <span data-ttu-id="95cb4-1199">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1199">tarjeta de crédito</span></span>
- <span data-ttu-id="95cb4-1200">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="95cb4-1200">tarjeta de atm</span></span>
- <span data-ttu-id="95cb4-1201">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="95cb4-1201">tarjeta atm</span></span>
- <span data-ttu-id="95cb4-1202">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1202">tarjeta debito</span></span>
- <span data-ttu-id="95cb4-1203">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1203">tarjeta de debito</span></span>
- <span data-ttu-id="95cb4-1204">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1204">tarjeta débito</span></span>
- <span data-ttu-id="95cb4-1205">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1205">tarjeta de débito</span></span>
- <span data-ttu-id="95cb4-1206">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="95cb4-1206">nº de tarjeta</span></span>
- <span data-ttu-id="95cb4-1207">不。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1207">no.</span></span> <span data-ttu-id="95cb4-1208">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="95cb4-1208">de tarjeta</span></span>
- <span data-ttu-id="95cb4-1209">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="95cb4-1209">no de tarjeta</span></span>
- <span data-ttu-id="95cb4-1210">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="95cb4-1210">numero de tarjeta</span></span>
- <span data-ttu-id="95cb4-1211">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="95cb4-1211">número de tarjeta</span></span>
- <span data-ttu-id="95cb4-1212">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="95cb4-1212">tarjeta no</span></span>
- <span data-ttu-id="95cb4-1213">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="95cb4-1213">tarjetahabiente</span></span>
- <span data-ttu-id="95cb4-1214">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1214">cartão de crédito</span></span>
- <span data-ttu-id="95cb4-1215">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1215">cartão de credito</span></span>
- <span data-ttu-id="95cb4-1216">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1216">cartao de crédito</span></span>
- <span data-ttu-id="95cb4-1217">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1217">cartao de credito</span></span>
- <span data-ttu-id="95cb4-1218">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1218">cartão de débito</span></span>
- <span data-ttu-id="95cb4-1219">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1219">cartao de débito</span></span>
- <span data-ttu-id="95cb4-1220">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1220">cartão de debito</span></span>
- <span data-ttu-id="95cb4-1221">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1221">cartao de debito</span></span>
- <span data-ttu-id="95cb4-1222">débito automático</span><span class="sxs-lookup"><span data-stu-id="95cb4-1222">débito automático</span></span>
- <span data-ttu-id="95cb4-1223">debito automatico</span><span class="sxs-lookup"><span data-stu-id="95cb4-1223">debito automatico</span></span>
- <span data-ttu-id="95cb4-1224">número do cartão</span><span class="sxs-lookup"><span data-stu-id="95cb4-1224">número do cartão</span></span>
- <span data-ttu-id="95cb4-1225">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="95cb4-1225">numero do cartão</span></span> 
- <span data-ttu-id="95cb4-1226">número do cartao</span><span class="sxs-lookup"><span data-stu-id="95cb4-1226">número do cartao</span></span>
- <span data-ttu-id="95cb4-1227">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="95cb4-1227">numero do cartao</span></span>
- <span data-ttu-id="95cb4-1228">número de cartão</span><span class="sxs-lookup"><span data-stu-id="95cb4-1228">número de cartão</span></span>
- <span data-ttu-id="95cb4-1229">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="95cb4-1229">numero de cartão</span></span>
- <span data-ttu-id="95cb4-1230">número de cartao</span><span class="sxs-lookup"><span data-stu-id="95cb4-1230">número de cartao</span></span>
- <span data-ttu-id="95cb4-1231">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="95cb4-1231">numero de cartao</span></span>
- <span data-ttu-id="95cb4-1232">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="95cb4-1232">nº do cartão</span></span>
- <span data-ttu-id="95cb4-1233">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="95cb4-1233">nº do cartao</span></span>
- <span data-ttu-id="95cb4-1234">n º。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1234">nº.</span></span> <span data-ttu-id="95cb4-1235">do cartão</span><span class="sxs-lookup"><span data-stu-id="95cb4-1235">do cartão</span></span>
- <span data-ttu-id="95cb4-1236">no do cartão</span><span class="sxs-lookup"><span data-stu-id="95cb4-1236">no do cartão</span></span>
- <span data-ttu-id="95cb4-1237">no do cartao</span><span class="sxs-lookup"><span data-stu-id="95cb4-1237">no do cartao</span></span>
- <span data-ttu-id="95cb4-1238">不。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1238">no.</span></span> <span data-ttu-id="95cb4-1239">do cartão</span><span class="sxs-lookup"><span data-stu-id="95cb4-1239">do cartão</span></span>
- <span data-ttu-id="95cb4-1240">不。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1240">no.</span></span> <span data-ttu-id="95cb4-1241">do cartao</span><span class="sxs-lookup"><span data-stu-id="95cb4-1241">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="95cb4-1242">	克罗地亚身份证号</span><span class="sxs-lookup"><span data-stu-id="95cb4-1242">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-1243">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-1243">Format</span></span>

<span data-ttu-id="95cb4-1244">九个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1244">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-1245">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-1245">Pattern</span></span>

<span data-ttu-id="95cb4-1246">九个连续的数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1246">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-1247">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-1247">Checksum</span></span>

<span data-ttu-id="95cb4-1248">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-1248">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-1249">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-1249">Definition</span></span>

<span data-ttu-id="95cb4-1250">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-1250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-1251">函数 Func_croatia_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1251">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-1252">找到 Keyword_croatia_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1252">A keyword from Keyword_croatia_id_card is found.</span></span>

```
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-1253">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1253">Keywords</span></span>

#### <a name="keywordcroatiaidcard"></a><span data-ttu-id="95cb4-1254">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="95cb4-1254">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="95cb4-1255">Croatian identity card</span><span class="sxs-lookup"><span data-stu-id="95cb4-1255">Croatian identity card</span></span>
- <span data-ttu-id="95cb4-1256">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="95cb4-1256">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="95cb4-1257">	Croatia Personal Identification (OIB) Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-1257">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-1258">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-1258">Format</span></span>

<span data-ttu-id="95cb4-1259">11 个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1259">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-1260">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-1260">Pattern</span></span>

<span data-ttu-id="95cb4-1261">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="95cb4-1261">11 digits:</span></span>
- <span data-ttu-id="95cb4-1262">10 个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1262">10 digits</span></span> 
- <span data-ttu-id="95cb4-1263">最后一个数字是用于国际数据交换目的的校验位, 字母 HR 将加上11位数字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1263">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-1264">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-1264">Checksum</span></span>

<span data-ttu-id="95cb4-1265">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-1265">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-1266">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-1266">Definition</span></span>

<span data-ttu-id="95cb4-1267">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-1267">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-1268">函数 Func_croatia_oib_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1268">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-1269">找到 Keyword_croatia_oib_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1269">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="95cb4-1270">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1270">The checksum passes.</span></span>

<span data-ttu-id="95cb4-1271">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-1271">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-1272">函数 Func_croatia_oib_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1272">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-1273">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1273">The checksum passes.</span></span>

```
<!-- Croatia Personal Identification (OIB) Number -->
<Entity id="31983b6d-db95-4eb2-a630-b44bd091968d" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_croatia_oib_number"/>
     <Match idRef="Keyword_croatia_oib_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_oib_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-1274">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1274">Keywords</span></span>

#### <a name="keywordcroatiaoibnumber"></a><span data-ttu-id="95cb4-1275">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="95cb4-1275">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="95cb4-1276">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-1276">Personal Identification Number</span></span>
- <span data-ttu-id="95cb4-1277">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="95cb4-1277">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="95cb4-1278">OIB</span><span class="sxs-lookup"><span data-stu-id="95cb4-1278">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="95cb4-1279">捷克个人识别码</span><span class="sxs-lookup"><span data-stu-id="95cb4-1279">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-1280">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-1280">Format</span></span>

<span data-ttu-id="95cb4-1281">9个带可选正斜杠 (旧格式) 的数字, 带可选正斜杠的10个数字 (新的格式)</span><span class="sxs-lookup"><span data-stu-id="95cb4-1281">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-1282">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-1282">Pattern</span></span>

<span data-ttu-id="95cb4-1283">9个数字 (旧格式):</span><span class="sxs-lookup"><span data-stu-id="95cb4-1283">Nine digits (old format):</span></span>
- <span data-ttu-id="95cb4-1284">九个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1284">Nine digits</span></span>

<span data-ttu-id="95cb4-1285">或者</span><span class="sxs-lookup"><span data-stu-id="95cb4-1285">OR</span></span>

- <span data-ttu-id="95cb4-1286">代表出生日期的六个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1286">Six digits that represent date of birth</span></span>
- <span data-ttu-id="95cb4-1287">一个正斜杠 </span><span class="sxs-lookup"><span data-stu-id="95cb4-1287">A forward slash</span></span>
- <span data-ttu-id="95cb4-1288">三位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1288">Three digits</span></span>

<span data-ttu-id="95cb4-1289">10个数字 (新格式):</span><span class="sxs-lookup"><span data-stu-id="95cb4-1289">10 digits (new format):</span></span>
- <span data-ttu-id="95cb4-1290">10 个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1290">10 digits</span></span>

<span data-ttu-id="95cb4-1291">或者</span><span class="sxs-lookup"><span data-stu-id="95cb4-1291">OR</span></span>

- <span data-ttu-id="95cb4-1292">代表出生日期的六个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1292">Six digits that represent date of birth</span></span>
- <span data-ttu-id="95cb4-1293">一个正斜杠 </span><span class="sxs-lookup"><span data-stu-id="95cb4-1293">A forward slash</span></span> 
- <span data-ttu-id="95cb4-1294">四个数字, 其中最后一个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="95cb4-1294">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-1295">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-1295">Checksum</span></span>

<span data-ttu-id="95cb4-1296">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-1296">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-1297">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-1297">Definition</span></span>

<span data-ttu-id="95cb4-1298">DLP 策略 85% 确信在300个字符的邻近度内检测到此类型的敏感信息: 函数 Func_czech_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1298">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="95cb4-1299">找到 Keyword_czech_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1299">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="95cb4-1300">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1300">The checksum passes.</span></span>

```
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="95cb4-1301">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1301">Keywords</span></span>

- <span data-ttu-id="95cb4-1302">捷克个人识别码</span><span class="sxs-lookup"><span data-stu-id="95cb4-1302">czech personal identity number</span></span>
- <span data-ttu-id="95cb4-1303">Rodnéčíslo</span><span class="sxs-lookup"><span data-stu-id="95cb4-1303">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="95cb4-1304">	丹麦个人身份号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-1304">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-1305">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-1305">Format</span></span>

<span data-ttu-id="95cb4-1306">10 个数字，包含连字符</span><span class="sxs-lookup"><span data-stu-id="95cb4-1306">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-1307">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-1307">Pattern</span></span>

<span data-ttu-id="95cb4-1308">10 个数字：</span><span class="sxs-lookup"><span data-stu-id="95cb4-1308">10 digits:</span></span>
- <span data-ttu-id="95cb4-1309">六个数字，采用  DDMMYY 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="95cb4-1309">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="95cb4-1310">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="95cb4-1310">A hyphen</span></span> 
- <span data-ttu-id="95cb4-1311">四个数字，最后一位数字是校验位</span><span class="sxs-lookup"><span data-stu-id="95cb4-1311">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-1312">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-1312">Checksum</span></span>

<span data-ttu-id="95cb4-1313">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-1313">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-1314">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-1314">Definition</span></span>

<span data-ttu-id="95cb4-1315">DLP 策略 75% 确信在300个字符的邻近度内检测到此类型的敏感信息: 正则表达式 Regex_denmark_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1315">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="95cb4-1316">找到 Keyword_denmark_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1316">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="95cb4-1317">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1317">The checksum passes.</span></span>

```
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-1318">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1318">Keywords</span></span>

#### <a name="keyworddenmarkid"></a><span data-ttu-id="95cb4-1319">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="95cb4-1319">Keyword_denmark_id</span></span>

- <span data-ttu-id="95cb4-1320">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-1320">Personal Identification Number</span></span>
- <span data-ttu-id="95cb4-1321">CPR</span><span class="sxs-lookup"><span data-stu-id="95cb4-1321">CPR</span></span>
- <span data-ttu-id="95cb4-1322">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="95cb4-1322">Det Centrale Personregister</span></span>
- <span data-ttu-id="95cb4-1323">Personnummer</span><span class="sxs-lookup"><span data-stu-id="95cb4-1323">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="95cb4-1324">药品管制局 (DEA) 号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-1324">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-1325">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-1325">Format</span></span>

<span data-ttu-id="95cb4-1326">两个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1326">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-1327">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-1327">Pattern</span></span>

<span data-ttu-id="95cb4-1328">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="95cb4-1328">Pattern must include all of the following:</span></span>
- <span data-ttu-id="95cb4-1329">这一组可能的字母（不区分大小写）中的一个字母：abcdefghjklmnprstux，这是注册人代码</span><span class="sxs-lookup"><span data-stu-id="95cb4-1329">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="95cb4-1330">一个字母（不区分大小写），这是注册人姓氏的第一个字母</span><span class="sxs-lookup"><span data-stu-id="95cb4-1330">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="95cb4-1331">七位数字，最后一个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="95cb4-1331">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-1332">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-1332">Checksum</span></span>

<span data-ttu-id="95cb4-1333">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-1333">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-1334">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-1334">Definition</span></span>

<span data-ttu-id="95cb4-1335">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-1335">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-1336">函数 Func_dea_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1336">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-1337">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1337">The checksum passes.</span></span>

```
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-1338">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1338">Keywords</span></span>

<span data-ttu-id="95cb4-1339">None</span><span class="sxs-lookup"><span data-stu-id="95cb4-1339">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="95cb4-1340">欧盟借记卡号</span><span class="sxs-lookup"><span data-stu-id="95cb4-1340">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-1341">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-1341">Format</span></span>

<span data-ttu-id="95cb4-1342">16 个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1342">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-1343">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-1343">Pattern</span></span>

<span data-ttu-id="95cb4-1344">非常复杂且强大的模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-1344">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-1345">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-1345">Checksum</span></span>

<span data-ttu-id="95cb4-1346">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-1346">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-1347">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-1347">Definition</span></span>

<span data-ttu-id="95cb4-1348">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-1348">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-1349">函数 Func_eu_debit_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1349">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-1350">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="95cb4-1350">At least one of the following is true:</span></span>
    - <span data-ttu-id="95cb4-1351">找到 Keyword_eu_debit_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1351">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="95cb4-1352">找到 Keyword_card_terms_dict 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1352">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="95cb4-1353">找到 Keyword_card_security_terms_dict 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1353">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="95cb4-1354">找到 Keyword_card_expiration_terms_dict 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1354">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="95cb4-1355">函数 Func_expiration_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1355">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="95cb4-1356">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1356">The checksum passes.</span></span>

```
    <!-- EU Debit Card Number -->
    <Entity id="0e9b3178-9678-47dd-a509-37222ca96b42" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_eu_debit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_eu_debit_card" />
          <Match idRef="Keyword_card_terms_dict" />
          <Match idRef="Keyword_card_security_terms_dict" />
          <Match idRef="Keyword_card_expiration_terms_dict" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-1357">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1357">Keywords</span></span>

#### <a name="keywordeudebitcard"></a><span data-ttu-id="95cb4-1358">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="95cb4-1358">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="95cb4-1359">account number</span><span class="sxs-lookup"><span data-stu-id="95cb4-1359">account number</span></span> 
- <span data-ttu-id="95cb4-1360">card number</span><span class="sxs-lookup"><span data-stu-id="95cb4-1360">card number</span></span> 
- <span data-ttu-id="95cb4-1361">card no.</span><span class="sxs-lookup"><span data-stu-id="95cb4-1361">card no.</span></span> 
- <span data-ttu-id="95cb4-1362">security number</span><span class="sxs-lookup"><span data-stu-id="95cb4-1362">security number</span></span> 
- <span data-ttu-id="95cb4-1363">收件人</span><span class="sxs-lookup"><span data-stu-id="95cb4-1363">cc#</span></span> 

#### <a name="keywordcardtermsdict"></a><span data-ttu-id="95cb4-1364">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="95cb4-1364">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="95cb4-1365">acct nbr</span><span class="sxs-lookup"><span data-stu-id="95cb4-1365">acct nbr</span></span> 
- <span data-ttu-id="95cb4-1366">acct num</span><span class="sxs-lookup"><span data-stu-id="95cb4-1366">acct num</span></span> 
- <span data-ttu-id="95cb4-1367">acct no</span><span class="sxs-lookup"><span data-stu-id="95cb4-1367">acct no</span></span> 
- <span data-ttu-id="95cb4-1368">american express</span><span class="sxs-lookup"><span data-stu-id="95cb4-1368">american express</span></span> 
- <span data-ttu-id="95cb4-1369">americanexpress</span><span class="sxs-lookup"><span data-stu-id="95cb4-1369">americanexpress</span></span> 
- <span data-ttu-id="95cb4-1370">americano espresso</span><span class="sxs-lookup"><span data-stu-id="95cb4-1370">americano espresso</span></span> 
- <span data-ttu-id="95cb4-1371">amex</span><span class="sxs-lookup"><span data-stu-id="95cb4-1371">amex</span></span> 
- <span data-ttu-id="95cb4-1372">atm card</span><span class="sxs-lookup"><span data-stu-id="95cb4-1372">atm card</span></span> 
- <span data-ttu-id="95cb4-1373">atm cards</span><span class="sxs-lookup"><span data-stu-id="95cb4-1373">atm cards</span></span> 
- <span data-ttu-id="95cb4-1374">atm kaart</span><span class="sxs-lookup"><span data-stu-id="95cb4-1374">atm kaart</span></span> 
- <span data-ttu-id="95cb4-1375">atmcard</span><span class="sxs-lookup"><span data-stu-id="95cb4-1375">atmcard</span></span> 
- <span data-ttu-id="95cb4-1376">atmcards</span><span class="sxs-lookup"><span data-stu-id="95cb4-1376">atmcards</span></span> 
- <span data-ttu-id="95cb4-1377">atmkaart</span><span class="sxs-lookup"><span data-stu-id="95cb4-1377">atmkaart</span></span> 
- <span data-ttu-id="95cb4-1378">atmkaarten</span><span class="sxs-lookup"><span data-stu-id="95cb4-1378">atmkaarten</span></span> 
- <span data-ttu-id="95cb4-1379">bancontact</span><span class="sxs-lookup"><span data-stu-id="95cb4-1379">bancontact</span></span> 
- <span data-ttu-id="95cb4-1380">bank card</span><span class="sxs-lookup"><span data-stu-id="95cb4-1380">bank card</span></span> 
- <span data-ttu-id="95cb4-1381">bankkaart</span><span class="sxs-lookup"><span data-stu-id="95cb4-1381">bankkaart</span></span> 
- <span data-ttu-id="95cb4-1382">card holder</span><span class="sxs-lookup"><span data-stu-id="95cb4-1382">card holder</span></span> 
- <span data-ttu-id="95cb4-1383">card holders</span><span class="sxs-lookup"><span data-stu-id="95cb4-1383">card holders</span></span> 
- <span data-ttu-id="95cb4-1384">card num</span><span class="sxs-lookup"><span data-stu-id="95cb4-1384">card num</span></span> 
- <span data-ttu-id="95cb4-1385">card number</span><span class="sxs-lookup"><span data-stu-id="95cb4-1385">card number</span></span> 
- <span data-ttu-id="95cb4-1386">card numbers</span><span class="sxs-lookup"><span data-stu-id="95cb4-1386">card numbers</span></span> 
- <span data-ttu-id="95cb4-1387">card type</span><span class="sxs-lookup"><span data-stu-id="95cb4-1387">card type</span></span> 
- <span data-ttu-id="95cb4-1388">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="95cb4-1388">cardano numerico</span></span> 
- <span data-ttu-id="95cb4-1389">持卡人</span><span class="sxs-lookup"><span data-stu-id="95cb4-1389">cardholder</span></span> 
- <span data-ttu-id="95cb4-1390">cardholders</span><span class="sxs-lookup"><span data-stu-id="95cb4-1390">cardholders</span></span> 
- <span data-ttu-id="95cb4-1391">cardnumber</span><span class="sxs-lookup"><span data-stu-id="95cb4-1391">cardnumber</span></span> 
- <span data-ttu-id="95cb4-1392">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="95cb4-1392">cardnumbers</span></span> 
- <span data-ttu-id="95cb4-1393">carta bianca</span><span class="sxs-lookup"><span data-stu-id="95cb4-1393">carta bianca</span></span> 
- <span data-ttu-id="95cb4-1394">carta credito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1394">carta credito</span></span> 
- <span data-ttu-id="95cb4-1395">carta di credito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1395">carta di credito</span></span> 
- <span data-ttu-id="95cb4-1396">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1396">cartao de credito</span></span> 
- <span data-ttu-id="95cb4-1397">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1397">cartao de crédito</span></span> 
- <span data-ttu-id="95cb4-1398">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1398">cartao de debito</span></span> 
- <span data-ttu-id="95cb4-1399">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1399">cartao de débito</span></span> 
- <span data-ttu-id="95cb4-1400">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="95cb4-1400">carte bancaire</span></span> 
- <span data-ttu-id="95cb4-1401">carte blanche</span><span class="sxs-lookup"><span data-stu-id="95cb4-1401">carte blanche</span></span> 
- <span data-ttu-id="95cb4-1402">carte bleue</span><span class="sxs-lookup"><span data-stu-id="95cb4-1402">carte bleue</span></span> 
- <span data-ttu-id="95cb4-1403">carte de credit</span><span class="sxs-lookup"><span data-stu-id="95cb4-1403">carte de credit</span></span> 
- <span data-ttu-id="95cb4-1404">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="95cb4-1404">carte de crédit</span></span> 
- <span data-ttu-id="95cb4-1405">carte di credito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1405">carte di credito</span></span> 
- <span data-ttu-id="95cb4-1406">carteblanche</span><span class="sxs-lookup"><span data-stu-id="95cb4-1406">carteblanche</span></span> 
- <span data-ttu-id="95cb4-1407">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1407">cartão de credito</span></span> 
- <span data-ttu-id="95cb4-1408">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1408">cartão de crédito</span></span> 
- <span data-ttu-id="95cb4-1409">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1409">cartão de debito</span></span> 
- <span data-ttu-id="95cb4-1410">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1410">cartão de débito</span></span> 
- <span data-ttu-id="95cb4-1411">cb</span><span class="sxs-lookup"><span data-stu-id="95cb4-1411">cb</span></span> 
- <span data-ttu-id="95cb4-1412">ccn</span><span class="sxs-lookup"><span data-stu-id="95cb4-1412">ccn</span></span> 
- <span data-ttu-id="95cb4-1413">check card</span><span class="sxs-lookup"><span data-stu-id="95cb4-1413">check card</span></span> 
- <span data-ttu-id="95cb4-1414">check cards</span><span class="sxs-lookup"><span data-stu-id="95cb4-1414">check cards</span></span> 
- <span data-ttu-id="95cb4-1415">checkcard</span><span class="sxs-lookup"><span data-stu-id="95cb4-1415">checkcard</span></span>
- <span data-ttu-id="95cb4-1416">checkcards</span><span class="sxs-lookup"><span data-stu-id="95cb4-1416">checkcards</span></span> 
- <span data-ttu-id="95cb4-1417">chequekaart</span><span class="sxs-lookup"><span data-stu-id="95cb4-1417">chequekaart</span></span> 
- <span data-ttu-id="95cb4-1418">cirrus</span><span class="sxs-lookup"><span data-stu-id="95cb4-1418">cirrus</span></span> 
- <span data-ttu-id="95cb4-1419">cirrus-edc-maestro</span><span class="sxs-lookup"><span data-stu-id="95cb4-1419">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="95cb4-1420">controlekaart</span><span class="sxs-lookup"><span data-stu-id="95cb4-1420">controlekaart</span></span> 
- <span data-ttu-id="95cb4-1421">controlekaarten</span><span class="sxs-lookup"><span data-stu-id="95cb4-1421">controlekaarten</span></span> 
- <span data-ttu-id="95cb4-1422">credit card</span><span class="sxs-lookup"><span data-stu-id="95cb4-1422">credit card</span></span> 
- <span data-ttu-id="95cb4-1423">credit cards</span><span class="sxs-lookup"><span data-stu-id="95cb4-1423">credit cards</span></span> 
- <span data-ttu-id="95cb4-1424">creditcard</span><span class="sxs-lookup"><span data-stu-id="95cb4-1424">creditcard</span></span> 
- <span data-ttu-id="95cb4-1425">creditcards</span><span class="sxs-lookup"><span data-stu-id="95cb4-1425">creditcards</span></span> 
- <span data-ttu-id="95cb4-1426">debetkaart</span><span class="sxs-lookup"><span data-stu-id="95cb4-1426">debetkaart</span></span> 
- <span data-ttu-id="95cb4-1427">debetkaarten</span><span class="sxs-lookup"><span data-stu-id="95cb4-1427">debetkaarten</span></span> 
- <span data-ttu-id="95cb4-1428">debit card</span><span class="sxs-lookup"><span data-stu-id="95cb4-1428">debit card</span></span> 
- <span data-ttu-id="95cb4-1429">debit cards</span><span class="sxs-lookup"><span data-stu-id="95cb4-1429">debit cards</span></span> 
- <span data-ttu-id="95cb4-1430">debitcard</span><span class="sxs-lookup"><span data-stu-id="95cb4-1430">debitcard</span></span> 
- <span data-ttu-id="95cb4-1431">debitcards</span><span class="sxs-lookup"><span data-stu-id="95cb4-1431">debitcards</span></span> 
- <span data-ttu-id="95cb4-1432">debito automatico</span><span class="sxs-lookup"><span data-stu-id="95cb4-1432">debito automatico</span></span> 
- <span data-ttu-id="95cb4-1433">diners club</span><span class="sxs-lookup"><span data-stu-id="95cb4-1433">diners club</span></span> 
- <span data-ttu-id="95cb4-1434">dinersclub</span><span class="sxs-lookup"><span data-stu-id="95cb4-1434">dinersclub</span></span> 
- <span data-ttu-id="95cb4-1435">确定</span><span class="sxs-lookup"><span data-stu-id="95cb4-1435">discover</span></span> 
- <span data-ttu-id="95cb4-1436">discover card</span><span class="sxs-lookup"><span data-stu-id="95cb4-1436">discover card</span></span> 
- <span data-ttu-id="95cb4-1437">discover cards</span><span class="sxs-lookup"><span data-stu-id="95cb4-1437">discover cards</span></span> 
- <span data-ttu-id="95cb4-1438">discovercard</span><span class="sxs-lookup"><span data-stu-id="95cb4-1438">discovercard</span></span> 
- <span data-ttu-id="95cb4-1439">discovercards</span><span class="sxs-lookup"><span data-stu-id="95cb4-1439">discovercards</span></span> 
- <span data-ttu-id="95cb4-1440">débito automático</span><span class="sxs-lookup"><span data-stu-id="95cb4-1440">débito automático</span></span>
- <span data-ttu-id="95cb4-1441">edc</span><span class="sxs-lookup"><span data-stu-id="95cb4-1441">edc</span></span> 
- <span data-ttu-id="95cb4-1442">eigentümername</span><span class="sxs-lookup"><span data-stu-id="95cb4-1442">eigentümername</span></span> 
- <span data-ttu-id="95cb4-1443">european debit card</span><span class="sxs-lookup"><span data-stu-id="95cb4-1443">european debit card</span></span> 
- <span data-ttu-id="95cb4-1444">hoofdkaart</span><span class="sxs-lookup"><span data-stu-id="95cb4-1444">hoofdkaart</span></span> 
- <span data-ttu-id="95cb4-1445">hoofdkaarten</span><span class="sxs-lookup"><span data-stu-id="95cb4-1445">hoofdkaarten</span></span> 
- <span data-ttu-id="95cb4-1446">in viaggio</span><span class="sxs-lookup"><span data-stu-id="95cb4-1446">in viaggio</span></span> 
- <span data-ttu-id="95cb4-1447">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="95cb4-1447">japanese card bureau</span></span> 
- <span data-ttu-id="95cb4-1448">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="95cb4-1448">japanse kaartdienst</span></span> 
- <span data-ttu-id="95cb4-1449">jcb</span><span class="sxs-lookup"><span data-stu-id="95cb4-1449">jcb</span></span> 
- <span data-ttu-id="95cb4-1450">kaart</span><span class="sxs-lookup"><span data-stu-id="95cb4-1450">kaart</span></span> 
- <span data-ttu-id="95cb4-1451">kaart num</span><span class="sxs-lookup"><span data-stu-id="95cb4-1451">kaart num</span></span> 
- <span data-ttu-id="95cb4-1452">kaartaantal</span><span class="sxs-lookup"><span data-stu-id="95cb4-1452">kaartaantal</span></span> 
- <span data-ttu-id="95cb4-1453">kaartaantallen</span><span class="sxs-lookup"><span data-stu-id="95cb4-1453">kaartaantallen</span></span> 
- <span data-ttu-id="95cb4-1454">kaarthouder</span><span class="sxs-lookup"><span data-stu-id="95cb4-1454">kaarthouder</span></span> 
- <span data-ttu-id="95cb4-1455">kaarthouders</span><span class="sxs-lookup"><span data-stu-id="95cb4-1455">kaarthouders</span></span> 
- <span data-ttu-id="95cb4-1456">karte</span><span class="sxs-lookup"><span data-stu-id="95cb4-1456">karte</span></span>  
- <span data-ttu-id="95cb4-1457">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="95cb4-1457">karteninhaber</span></span> 
- <span data-ttu-id="95cb4-1458">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="95cb4-1458">karteninhabers</span></span>
- <span data-ttu-id="95cb4-1459">kartennr</span><span class="sxs-lookup"><span data-stu-id="95cb4-1459">kartennr</span></span> 
- <span data-ttu-id="95cb4-1460">kartennummer</span><span class="sxs-lookup"><span data-stu-id="95cb4-1460">kartennummer</span></span> 
- <span data-ttu-id="95cb4-1461">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="95cb4-1461">kreditkarte</span></span> 
- <span data-ttu-id="95cb4-1462">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="95cb4-1462">kreditkarten-nummer</span></span> 
- <span data-ttu-id="95cb4-1463">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="95cb4-1463">kreditkarteninhaber</span></span> 
- <span data-ttu-id="95cb4-1464">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="95cb4-1464">kreditkarteninstitut</span></span> 
- <span data-ttu-id="95cb4-1465">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="95cb4-1465">kreditkartennummer</span></span> 
- <span data-ttu-id="95cb4-1466">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="95cb4-1466">kreditkartentyp</span></span> 
- <span data-ttu-id="95cb4-1467">maestro</span><span class="sxs-lookup"><span data-stu-id="95cb4-1467">maestro</span></span> 
- <span data-ttu-id="95cb4-1468">Master Card</span><span class="sxs-lookup"><span data-stu-id="95cb4-1468">master card</span></span> 
- <span data-ttu-id="95cb4-1469">master cards</span><span class="sxs-lookup"><span data-stu-id="95cb4-1469">master cards</span></span> 
- <span data-ttu-id="95cb4-1470">mastercard</span><span class="sxs-lookup"><span data-stu-id="95cb4-1470">mastercard</span></span> 
- <span data-ttu-id="95cb4-1471">mastercards</span><span class="sxs-lookup"><span data-stu-id="95cb4-1471">mastercards</span></span> 
- <span data-ttu-id="95cb4-1472">emc</span><span class="sxs-lookup"><span data-stu-id="95cb4-1472">mc</span></span> 
- <span data-ttu-id="95cb4-1473">mister cash</span><span class="sxs-lookup"><span data-stu-id="95cb4-1473">mister cash</span></span> 
- <span data-ttu-id="95cb4-1474">n carta</span><span class="sxs-lookup"><span data-stu-id="95cb4-1474">n carta</span></span> 
- <span data-ttu-id="95cb4-1475">carta</span><span class="sxs-lookup"><span data-stu-id="95cb4-1475">carta</span></span> 
- <span data-ttu-id="95cb4-1476">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="95cb4-1476">no de tarjeta</span></span> 
- <span data-ttu-id="95cb4-1477">no do cartao</span><span class="sxs-lookup"><span data-stu-id="95cb4-1477">no do cartao</span></span> 
- <span data-ttu-id="95cb4-1478">no do cartão</span><span class="sxs-lookup"><span data-stu-id="95cb4-1478">no do cartão</span></span> 
- <span data-ttu-id="95cb4-1479">不。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1479">no.</span></span> <span data-ttu-id="95cb4-1480">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="95cb4-1480">de tarjeta</span></span> 
- <span data-ttu-id="95cb4-1481">不。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1481">no.</span></span> <span data-ttu-id="95cb4-1482">do cartao</span><span class="sxs-lookup"><span data-stu-id="95cb4-1482">do cartao</span></span> 
- <span data-ttu-id="95cb4-1483">不。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1483">no.</span></span> <span data-ttu-id="95cb4-1484">do cartão</span><span class="sxs-lookup"><span data-stu-id="95cb4-1484">do cartão</span></span> 
- <span data-ttu-id="95cb4-1485">nr carta</span><span class="sxs-lookup"><span data-stu-id="95cb4-1485">nr carta</span></span> 
- <span data-ttu-id="95cb4-1486">führerschein-nr.</span><span class="sxs-lookup"><span data-stu-id="95cb4-1486">nr.</span></span> <span data-ttu-id="95cb4-1487">carta</span><span class="sxs-lookup"><span data-stu-id="95cb4-1487">carta</span></span> 
- <span data-ttu-id="95cb4-1488">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="95cb4-1488">numeri di scheda</span></span> 
- <span data-ttu-id="95cb4-1489">numero carta</span><span class="sxs-lookup"><span data-stu-id="95cb4-1489">numero carta</span></span> 
- <span data-ttu-id="95cb4-1490">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="95cb4-1490">numero de cartao</span></span> 
- <span data-ttu-id="95cb4-1491">numero de carte</span><span class="sxs-lookup"><span data-stu-id="95cb4-1491">numero de carte</span></span> 
- <span data-ttu-id="95cb4-1492">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="95cb4-1492">numero de cartão</span></span> 
- <span data-ttu-id="95cb4-1493">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="95cb4-1493">numero de tarjeta</span></span>
- <span data-ttu-id="95cb4-1494">numero della carta</span><span class="sxs-lookup"><span data-stu-id="95cb4-1494">numero della carta</span></span> 
- <span data-ttu-id="95cb4-1495">numero di carta</span><span class="sxs-lookup"><span data-stu-id="95cb4-1495">numero di carta</span></span> 
- <span data-ttu-id="95cb4-1496">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="95cb4-1496">numero di scheda</span></span> 
- <span data-ttu-id="95cb4-1497">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="95cb4-1497">numero do cartao</span></span> 
- <span data-ttu-id="95cb4-1498">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="95cb4-1498">numero do cartão</span></span> 
- <span data-ttu-id="95cb4-1499">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="95cb4-1499">numéro de carte</span></span> 
- <span data-ttu-id="95cb4-1500">nº carta</span><span class="sxs-lookup"><span data-stu-id="95cb4-1500">nº carta</span></span> 
- <span data-ttu-id="95cb4-1501">nº de carte</span><span class="sxs-lookup"><span data-stu-id="95cb4-1501">nº de carte</span></span> 
- <span data-ttu-id="95cb4-1502">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="95cb4-1502">nº de la carte</span></span> 
- <span data-ttu-id="95cb4-1503">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="95cb4-1503">nº de tarjeta</span></span> 
- <span data-ttu-id="95cb4-1504">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="95cb4-1504">nº do cartao</span></span> 
- <span data-ttu-id="95cb4-1505">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="95cb4-1505">nº do cartão</span></span> 
- <span data-ttu-id="95cb4-1506">n º。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1506">nº.</span></span> <span data-ttu-id="95cb4-1507">do cartão</span><span class="sxs-lookup"><span data-stu-id="95cb4-1507">do cartão</span></span> 
- <span data-ttu-id="95cb4-1508">número de cartao</span><span class="sxs-lookup"><span data-stu-id="95cb4-1508">número de cartao</span></span> 
- <span data-ttu-id="95cb4-1509">número de cartão</span><span class="sxs-lookup"><span data-stu-id="95cb4-1509">número de cartão</span></span> 
- <span data-ttu-id="95cb4-1510">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="95cb4-1510">número de tarjeta</span></span> 
- <span data-ttu-id="95cb4-1511">número do cartao</span><span class="sxs-lookup"><span data-stu-id="95cb4-1511">número do cartao</span></span> 
- <span data-ttu-id="95cb4-1512">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="95cb4-1512">scheda dell'assegno</span></span> 
- <span data-ttu-id="95cb4-1513">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="95cb4-1513">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="95cb4-1514">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="95cb4-1514">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="95cb4-1515">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="95cb4-1515">scheda della banca</span></span> 
- <span data-ttu-id="95cb4-1516">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="95cb4-1516">scheda di controllo</span></span> 
- <span data-ttu-id="95cb4-1517">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1517">scheda di debito</span></span> 
- <span data-ttu-id="95cb4-1518">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="95cb4-1518">scheda matrice</span></span> 
- <span data-ttu-id="95cb4-1519">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="95cb4-1519">schede dell'atmosfera</span></span> 
- <span data-ttu-id="95cb4-1520">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="95cb4-1520">schede di controllo</span></span> 
- <span data-ttu-id="95cb4-1521">schede di debito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1521">schede di debito</span></span> 
- <span data-ttu-id="95cb4-1522">schede matrici</span><span class="sxs-lookup"><span data-stu-id="95cb4-1522">schede matrici</span></span> 
- <span data-ttu-id="95cb4-1523">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="95cb4-1523">scoprono la scheda</span></span> 
- <span data-ttu-id="95cb4-1524">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="95cb4-1524">scoprono le schede</span></span> 
- <span data-ttu-id="95cb4-1525">solo</span><span class="sxs-lookup"><span data-stu-id="95cb4-1525">solo</span></span> 
- <span data-ttu-id="95cb4-1526">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="95cb4-1526">supporti di scheda</span></span> 
- <span data-ttu-id="95cb4-1527">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="95cb4-1527">supporto di scheda</span></span> 
- <span data-ttu-id="95cb4-1528">器</span><span class="sxs-lookup"><span data-stu-id="95cb4-1528">switch</span></span> 
- <span data-ttu-id="95cb4-1529">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="95cb4-1529">tarjeta atm</span></span> 
- <span data-ttu-id="95cb4-1530">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1530">tarjeta credito</span></span> 
- <span data-ttu-id="95cb4-1531">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="95cb4-1531">tarjeta de atm</span></span> 
- <span data-ttu-id="95cb4-1532">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1532">tarjeta de credito</span></span> 
- <span data-ttu-id="95cb4-1533">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1533">tarjeta de debito</span></span> 
- <span data-ttu-id="95cb4-1534">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="95cb4-1534">tarjeta debito</span></span> 
- <span data-ttu-id="95cb4-1535">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="95cb4-1535">tarjeta no</span></span>
- <span data-ttu-id="95cb4-1536">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="95cb4-1536">tarjetahabiente</span></span> 
- <span data-ttu-id="95cb4-1537">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="95cb4-1537">tipo della scheda</span></span> 
- <span data-ttu-id="95cb4-1538">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="95cb4-1538">ufficio giapponese della</span></span> 
- <span data-ttu-id="95cb4-1539">scheda</span><span class="sxs-lookup"><span data-stu-id="95cb4-1539">scheda</span></span> 
- <span data-ttu-id="95cb4-1540">v pay</span><span class="sxs-lookup"><span data-stu-id="95cb4-1540">v pay</span></span> 
- <span data-ttu-id="95cb4-1541">v-支付</span><span class="sxs-lookup"><span data-stu-id="95cb4-1541">v-pay</span></span> 
- <span data-ttu-id="95cb4-1542">反之</span><span class="sxs-lookup"><span data-stu-id="95cb4-1542">visa</span></span> 
- <span data-ttu-id="95cb4-1543">visa plus</span><span class="sxs-lookup"><span data-stu-id="95cb4-1543">visa plus</span></span> 
- <span data-ttu-id="95cb4-1544">visa electron</span><span class="sxs-lookup"><span data-stu-id="95cb4-1544">visa electron</span></span> 
- <span data-ttu-id="95cb4-1545">visto</span><span class="sxs-lookup"><span data-stu-id="95cb4-1545">visto</span></span> 
- <span data-ttu-id="95cb4-1546">visum</span><span class="sxs-lookup"><span data-stu-id="95cb4-1546">visum</span></span> 
- <span data-ttu-id="95cb4-1547">vpay</span><span class="sxs-lookup"><span data-stu-id="95cb4-1547">vpay</span></span>   

#### <a name="keywordcardsecuritytermsdict"></a><span data-ttu-id="95cb4-1548">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="95cb4-1548">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="95cb4-1549">card identification number</span><span class="sxs-lookup"><span data-stu-id="95cb4-1549">card identification number</span></span>
- <span data-ttu-id="95cb4-1550">card verification</span><span class="sxs-lookup"><span data-stu-id="95cb4-1550">card verification</span></span> 
- <span data-ttu-id="95cb4-1551">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="95cb4-1551">cardi la verifica</span></span> 
- <span data-ttu-id="95cb4-1552">cid</span><span class="sxs-lookup"><span data-stu-id="95cb4-1552">cid</span></span> 
- <span data-ttu-id="95cb4-1553">cod seg</span><span class="sxs-lookup"><span data-stu-id="95cb4-1553">cod seg</span></span> 
- <span data-ttu-id="95cb4-1554">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="95cb4-1554">cod seguranca</span></span> 
- <span data-ttu-id="95cb4-1555">cod segurança</span><span class="sxs-lookup"><span data-stu-id="95cb4-1555">cod segurança</span></span> 
- <span data-ttu-id="95cb4-1556">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="95cb4-1556">cod sicurezza</span></span> 
- <span data-ttu-id="95cb4-1557">货.</span><span class="sxs-lookup"><span data-stu-id="95cb4-1557">cod.</span></span> <span data-ttu-id="95cb4-1558">seg</span><span class="sxs-lookup"><span data-stu-id="95cb4-1558">seg</span></span> 
- <span data-ttu-id="95cb4-1559">货.</span><span class="sxs-lookup"><span data-stu-id="95cb4-1559">cod.</span></span> <span data-ttu-id="95cb4-1560">seguranca</span><span class="sxs-lookup"><span data-stu-id="95cb4-1560">seguranca</span></span> 
- <span data-ttu-id="95cb4-1561">货.</span><span class="sxs-lookup"><span data-stu-id="95cb4-1561">cod.</span></span> <span data-ttu-id="95cb4-1562">segurança</span><span class="sxs-lookup"><span data-stu-id="95cb4-1562">segurança</span></span> 
- <span data-ttu-id="95cb4-1563">货.</span><span class="sxs-lookup"><span data-stu-id="95cb4-1563">cod.</span></span> <span data-ttu-id="95cb4-1564">sicurezza</span><span class="sxs-lookup"><span data-stu-id="95cb4-1564">sicurezza</span></span> 
- <span data-ttu-id="95cb4-1565">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="95cb4-1565">codice di sicurezza</span></span> 
- <span data-ttu-id="95cb4-1566">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="95cb4-1566">codice di verifica</span></span> 
- <span data-ttu-id="95cb4-1567">codigo</span><span class="sxs-lookup"><span data-stu-id="95cb4-1567">codigo</span></span> 
- <span data-ttu-id="95cb4-1568">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="95cb4-1568">codigo de seguranca</span></span> 
- <span data-ttu-id="95cb4-1569">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="95cb4-1569">codigo de segurança</span></span> 
- <span data-ttu-id="95cb4-1570">crittogramma</span><span class="sxs-lookup"><span data-stu-id="95cb4-1570">crittogramma</span></span> 
- <span data-ttu-id="95cb4-1571">cryptogram</span><span class="sxs-lookup"><span data-stu-id="95cb4-1571">cryptogram</span></span> 
- <span data-ttu-id="95cb4-1572">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="95cb4-1572">cryptogramme</span></span> 
- <span data-ttu-id="95cb4-1573">cv2</span><span class="sxs-lookup"><span data-stu-id="95cb4-1573">cv2</span></span> 
- <span data-ttu-id="95cb4-1574">cvc</span><span class="sxs-lookup"><span data-stu-id="95cb4-1574">cvc</span></span> 
- <span data-ttu-id="95cb4-1575">cvc2</span><span class="sxs-lookup"><span data-stu-id="95cb4-1575">cvc2</span></span> 
- <span data-ttu-id="95cb4-1576">cvn</span><span class="sxs-lookup"><span data-stu-id="95cb4-1576">cvn</span></span> 
- <span data-ttu-id="95cb4-1577">cvv</span><span class="sxs-lookup"><span data-stu-id="95cb4-1577">cvv</span></span> 
- <span data-ttu-id="95cb4-1578">cvv2</span><span class="sxs-lookup"><span data-stu-id="95cb4-1578">cvv2</span></span> 
- <span data-ttu-id="95cb4-1579">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="95cb4-1579">cód seguranca</span></span> 
- <span data-ttu-id="95cb4-1580">cód segurança</span><span class="sxs-lookup"><span data-stu-id="95cb4-1580">cód segurança</span></span> 
- <span data-ttu-id="95cb4-1581">cód。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1581">cód.</span></span> <span data-ttu-id="95cb4-1582">seguranca</span><span class="sxs-lookup"><span data-stu-id="95cb4-1582">seguranca</span></span> 
- <span data-ttu-id="95cb4-1583">cód。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1583">cód.</span></span> <span data-ttu-id="95cb4-1584">segurança</span><span class="sxs-lookup"><span data-stu-id="95cb4-1584">segurança</span></span> 
- <span data-ttu-id="95cb4-1585">código</span><span class="sxs-lookup"><span data-stu-id="95cb4-1585">código</span></span> 
- <span data-ttu-id="95cb4-1586">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="95cb4-1586">código de seguranca</span></span> 
- <span data-ttu-id="95cb4-1587">código de segurança</span><span class="sxs-lookup"><span data-stu-id="95cb4-1587">código de segurança</span></span> 
- <span data-ttu-id="95cb4-1588">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="95cb4-1588">de kaart controle</span></span> 
- <span data-ttu-id="95cb4-1589">geeft nr uit</span><span class="sxs-lookup"><span data-stu-id="95cb4-1589">geeft nr uit</span></span> 
- <span data-ttu-id="95cb4-1590">issue no</span><span class="sxs-lookup"><span data-stu-id="95cb4-1590">issue no</span></span> 
- <span data-ttu-id="95cb4-1591">issue number</span><span class="sxs-lookup"><span data-stu-id="95cb4-1591">issue number</span></span> 
- <span data-ttu-id="95cb4-1592">kaartidentificatienummer</span><span class="sxs-lookup"><span data-stu-id="95cb4-1592">kaartidentificatienummer</span></span> 
- <span data-ttu-id="95cb4-1593">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="95cb4-1593">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="95cb4-1594">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="95cb4-1594">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="95cb4-1595">kwestieaantal</span><span class="sxs-lookup"><span data-stu-id="95cb4-1595">kwestieaantal</span></span> 
- <span data-ttu-id="95cb4-1596">不。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1596">no.</span></span> <span data-ttu-id="95cb4-1597">dell'edizione</span><span class="sxs-lookup"><span data-stu-id="95cb4-1597">dell'edizione</span></span> 
- <span data-ttu-id="95cb4-1598">不。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1598">no.</span></span> <span data-ttu-id="95cb4-1599">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="95cb4-1599">di sicurezza</span></span> 
- <span data-ttu-id="95cb4-1600">numero de securite</span><span class="sxs-lookup"><span data-stu-id="95cb4-1600">numero de securite</span></span> 
- <span data-ttu-id="95cb4-1601">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="95cb4-1601">numero de verificacao</span></span> 
- <span data-ttu-id="95cb4-1602">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="95cb4-1602">numero dell'edizione</span></span> 
- <span data-ttu-id="95cb4-1603">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="95cb4-1603">numero di identificazione della</span></span> 
- <span data-ttu-id="95cb4-1604">scheda</span><span class="sxs-lookup"><span data-stu-id="95cb4-1604">scheda</span></span> 
- <span data-ttu-id="95cb4-1605">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="95cb4-1605">numero di sicurezza</span></span> 
- <span data-ttu-id="95cb4-1606">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="95cb4-1606">numero van veiligheid</span></span> 
- <span data-ttu-id="95cb4-1607">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="95cb4-1607">numéro de sécurité</span></span> 
- <span data-ttu-id="95cb4-1608">nº autorizzazione</span><span class="sxs-lookup"><span data-stu-id="95cb4-1608">nº autorizzazione</span></span> 
- <span data-ttu-id="95cb4-1609">número de verificação</span><span class="sxs-lookup"><span data-stu-id="95cb4-1609">número de verificação</span></span> 
- <span data-ttu-id="95cb4-1610">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="95cb4-1610">perno il blocco</span></span> 
- <span data-ttu-id="95cb4-1611">pin block</span><span class="sxs-lookup"><span data-stu-id="95cb4-1611">pin block</span></span> 
- <span data-ttu-id="95cb4-1612">prufziffer</span><span class="sxs-lookup"><span data-stu-id="95cb4-1612">prufziffer</span></span> 
- <span data-ttu-id="95cb4-1613">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="95cb4-1613">prüfziffer</span></span> 
- <span data-ttu-id="95cb4-1614">security code</span><span class="sxs-lookup"><span data-stu-id="95cb4-1614">security code</span></span> 
- <span data-ttu-id="95cb4-1615">security no</span><span class="sxs-lookup"><span data-stu-id="95cb4-1615">security no</span></span> 
- <span data-ttu-id="95cb4-1616">security number</span><span class="sxs-lookup"><span data-stu-id="95cb4-1616">security number</span></span> 
- <span data-ttu-id="95cb4-1617">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="95cb4-1617">sicherheits kode</span></span> 
- <span data-ttu-id="95cb4-1618">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="95cb4-1618">sicherheitscode</span></span> 
- <span data-ttu-id="95cb4-1619">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="95cb4-1619">sicherheitsnummer</span></span> 
- <span data-ttu-id="95cb4-1620">speldblok</span><span class="sxs-lookup"><span data-stu-id="95cb4-1620">speldblok</span></span> 
- <span data-ttu-id="95cb4-1621">veiligheid nr</span><span class="sxs-lookup"><span data-stu-id="95cb4-1621">veiligheid nr</span></span> 
- <span data-ttu-id="95cb4-1622">veiligheidsaantal</span><span class="sxs-lookup"><span data-stu-id="95cb4-1622">veiligheidsaantal</span></span> 
- <span data-ttu-id="95cb4-1623">veiligheidscode</span><span class="sxs-lookup"><span data-stu-id="95cb4-1623">veiligheidscode</span></span> 
- <span data-ttu-id="95cb4-1624">veiligheidsnummer</span><span class="sxs-lookup"><span data-stu-id="95cb4-1624">veiligheidsnummer</span></span> 
- <span data-ttu-id="95cb4-1625">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="95cb4-1625">verfalldatum</span></span> 

#### <a name="keywordcardexpirationtermsdict"></a><span data-ttu-id="95cb4-1626">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="95cb4-1626">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="95cb4-1627">ablauf</span><span class="sxs-lookup"><span data-stu-id="95cb4-1627">ablauf</span></span> 
- <span data-ttu-id="95cb4-1628">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="95cb4-1628">data de expiracao</span></span> 
- <span data-ttu-id="95cb4-1629">data de expiração</span><span class="sxs-lookup"><span data-stu-id="95cb4-1629">data de expiração</span></span> 
- <span data-ttu-id="95cb4-1630">data del exp</span><span class="sxs-lookup"><span data-stu-id="95cb4-1630">data del exp</span></span> 
- <span data-ttu-id="95cb4-1631">data di exp</span><span class="sxs-lookup"><span data-stu-id="95cb4-1631">data di exp</span></span> 
- <span data-ttu-id="95cb4-1632">data di scadenza</span><span class="sxs-lookup"><span data-stu-id="95cb4-1632">data di scadenza</span></span> 
- <span data-ttu-id="95cb4-1633">data em que expira</span><span class="sxs-lookup"><span data-stu-id="95cb4-1633">data em que expira</span></span> 
- <span data-ttu-id="95cb4-1634">data scad</span><span class="sxs-lookup"><span data-stu-id="95cb4-1634">data scad</span></span> 
- <span data-ttu-id="95cb4-1635">data scadenza</span><span class="sxs-lookup"><span data-stu-id="95cb4-1635">data scadenza</span></span> 
- <span data-ttu-id="95cb4-1636">date de validité</span><span class="sxs-lookup"><span data-stu-id="95cb4-1636">date de validité</span></span> 
- <span data-ttu-id="95cb4-1637">datum afloop</span><span class="sxs-lookup"><span data-stu-id="95cb4-1637">datum afloop</span></span> 
- <span data-ttu-id="95cb4-1638">datum van exp</span><span class="sxs-lookup"><span data-stu-id="95cb4-1638">datum van exp</span></span> 
- <span data-ttu-id="95cb4-1639">de afloop</span><span class="sxs-lookup"><span data-stu-id="95cb4-1639">de afloop</span></span> 
- <span data-ttu-id="95cb4-1640">espira</span><span class="sxs-lookup"><span data-stu-id="95cb4-1640">espira</span></span> 
- <span data-ttu-id="95cb4-1641">espira</span><span class="sxs-lookup"><span data-stu-id="95cb4-1641">espira</span></span> 
- <span data-ttu-id="95cb4-1642">exp date</span><span class="sxs-lookup"><span data-stu-id="95cb4-1642">exp date</span></span> 
- <span data-ttu-id="95cb4-1643">exp datum</span><span class="sxs-lookup"><span data-stu-id="95cb4-1643">exp datum</span></span> 
- <span data-ttu-id="95cb4-1644">时间</span><span class="sxs-lookup"><span data-stu-id="95cb4-1644">expiration</span></span> 
- <span data-ttu-id="95cb4-1645">何时</span><span class="sxs-lookup"><span data-stu-id="95cb4-1645">expire</span></span> 
- <span data-ttu-id="95cb4-1646">不久</span><span class="sxs-lookup"><span data-stu-id="95cb4-1646">expires</span></span> 
- <span data-ttu-id="95cb4-1647">过期</span><span class="sxs-lookup"><span data-stu-id="95cb4-1647">expiry</span></span> 
- <span data-ttu-id="95cb4-1648">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="95cb4-1648">fecha de expiracion</span></span> 
- <span data-ttu-id="95cb4-1649">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="95cb4-1649">fecha de venc</span></span> 
- <span data-ttu-id="95cb4-1650">gultig bis</span><span class="sxs-lookup"><span data-stu-id="95cb4-1650">gultig bis</span></span> 
- <span data-ttu-id="95cb4-1651">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="95cb4-1651">gultigkeitsdatum</span></span> 
- <span data-ttu-id="95cb4-1652">gültig bis</span><span class="sxs-lookup"><span data-stu-id="95cb4-1652">gültig bis</span></span> 
- <span data-ttu-id="95cb4-1653">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="95cb4-1653">gültigkeitsdatum</span></span> 
- <span data-ttu-id="95cb4-1654">la scadenza</span><span class="sxs-lookup"><span data-stu-id="95cb4-1654">la scadenza</span></span> 
- <span data-ttu-id="95cb4-1655">scadenza</span><span class="sxs-lookup"><span data-stu-id="95cb4-1655">scadenza</span></span> 
- <span data-ttu-id="95cb4-1656">valable</span><span class="sxs-lookup"><span data-stu-id="95cb4-1656">valable</span></span> 
- <span data-ttu-id="95cb4-1657">validade</span><span class="sxs-lookup"><span data-stu-id="95cb4-1657">validade</span></span> 
- <span data-ttu-id="95cb4-1658">valido hasta</span><span class="sxs-lookup"><span data-stu-id="95cb4-1658">valido hasta</span></span> 
- <span data-ttu-id="95cb4-1659">valor</span><span class="sxs-lookup"><span data-stu-id="95cb4-1659">valor</span></span> 
- <span data-ttu-id="95cb4-1660">venc</span><span class="sxs-lookup"><span data-stu-id="95cb4-1660">venc</span></span> 
- <span data-ttu-id="95cb4-1661">vencimento</span><span class="sxs-lookup"><span data-stu-id="95cb4-1661">vencimento</span></span> 
- <span data-ttu-id="95cb4-1662">vencimiento</span><span class="sxs-lookup"><span data-stu-id="95cb4-1662">vencimiento</span></span> 
- <span data-ttu-id="95cb4-1663">verloopt</span><span class="sxs-lookup"><span data-stu-id="95cb4-1663">verloopt</span></span> 
- <span data-ttu-id="95cb4-1664">vervaldag</span><span class="sxs-lookup"><span data-stu-id="95cb4-1664">vervaldag</span></span> 
- <span data-ttu-id="95cb4-1665">vervaldatum</span><span class="sxs-lookup"><span data-stu-id="95cb4-1665">vervaldatum</span></span> 
- <span data-ttu-id="95cb4-1666">vto</span><span class="sxs-lookup"><span data-stu-id="95cb4-1666">vto</span></span> 
- <span data-ttu-id="95cb4-1667">válido hasta</span><span class="sxs-lookup"><span data-stu-id="95cb4-1667">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="95cb4-1668">欧盟驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-1668">EU Driver's License Number</span></span>

<span data-ttu-id="95cb4-1669">若要了解详细信息, 请参阅[EU 驱动程序的许可号敏感信息类型](eu-driver-s-license-number.md)。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1669">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="95cb4-1670">欧盟国家身份证号</span><span class="sxs-lookup"><span data-stu-id="95cb4-1670">EU National Identification Number</span></span>

<span data-ttu-id="95cb4-1671">若要了解详细信息, 请参阅[EU 国家身份证号敏感信息类型](eu-national-identification-number.md)。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1671">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="95cb4-1672">EU 护照号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-1672">EU Passport Number</span></span>

<span data-ttu-id="95cb4-1673">若要了解详细信息, 请参阅[EU 护照号敏感信息类型](eu-passport-number.md)。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1673">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="95cb4-1674">欧盟社会安全号码或等效 ID</span><span class="sxs-lookup"><span data-stu-id="95cb4-1674">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="95cb4-1675">若要了解详细信息, 请参阅[EU 社会保险号或等效 ID 敏感信息类型](eu-social-security-number-or-equivalent-id.md)。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1675">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="95cb4-1676">EU 税标识号</span><span class="sxs-lookup"><span data-stu-id="95cb4-1676">EU Tax Identification Number</span></span>

<span data-ttu-id="95cb4-1677">若要了解详细信息, 请参阅[EU 纳税识别号敏感信息类型](eu-tax-identification-number.md)。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1677">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="95cb4-1678">芬兰国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="95cb4-1678">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-1679">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-1679">Format</span></span>

<span data-ttu-id="95cb4-1680">六个数字加一个字符（表示一个世纪），加三个数字再加一个校验位</span><span class="sxs-lookup"><span data-stu-id="95cb4-1680">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-1681">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-1681">Pattern</span></span>

<span data-ttu-id="95cb4-1682">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="95cb4-1682">Pattern must include all of the following:</span></span>
- <span data-ttu-id="95cb4-1683">采用 DDMMYY 格式的六位数字，表示出生日期</span><span class="sxs-lookup"><span data-stu-id="95cb4-1683">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="95cb4-1684">世纪标记（“-”、“+”或“a”）</span><span class="sxs-lookup"><span data-stu-id="95cb4-1684">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="95cb4-1685">三位个人标识号</span><span class="sxs-lookup"><span data-stu-id="95cb4-1685">Three-digit personal identification number</span></span> 
- <span data-ttu-id="95cb4-1686">一个数字或字母（区分大小写），是校验位</span><span class="sxs-lookup"><span data-stu-id="95cb4-1686">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-1687">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-1687">Checksum</span></span>

<span data-ttu-id="95cb4-1688">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-1688">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-1689">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-1689">Definition</span></span>

<span data-ttu-id="95cb4-1690">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-1690">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-1691">函数 Func_finnish_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1691">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-1692">找到 Keyword_finnish_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1692">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="95cb4-1693">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1693">The checksum passes.</span></span>

```
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-1694">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1694">Keywords</span></span>

- <span data-ttu-id="95cb4-1695">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="95cb4-1695">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="95cb4-1696">Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="95cb4-1696">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="95cb4-1697">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="95cb4-1697">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="95cb4-1698">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="95cb4-1698">Personbeteckning</span></span>
- <span data-ttu-id="95cb4-1699">Personnummer</span><span class="sxs-lookup"><span data-stu-id="95cb4-1699">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="95cb4-1700">芬兰护照号</span><span class="sxs-lookup"><span data-stu-id="95cb4-1700">Finland Passport Number</span></span>

<span data-ttu-id="95cb4-1701">设置九个字母和数字的组合的组合九个字母和数字的组合: 两个字母 (不区分大小写) 七个数字校验和无定义 DLP 策略是 75% 确信它检测到这种类型的敏感信息, 如果在300个字符的邻近性: 正则表达式 Regex_finland_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1701">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
<span data-ttu-id="95cb4-1702">找到 Keyword_finland_passport_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1702">A keyword from Keyword_finland_passport_number is found.</span></span>
<span data-ttu-id="95cb4-1703"><!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="95cb4-1703"></span></span>
<span data-ttu-id="95cb4-1704">关键字 Keyword_finland_passport_number passport Passi</span><span class="sxs-lookup"><span data-stu-id="95cb4-1704">Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="95cb4-1705">法国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-1705">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-1706">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-1706">Format</span></span>

<span data-ttu-id="95cb4-1707">12 个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1707">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-1708">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-1708">Pattern</span></span>

<span data-ttu-id="95cb4-1709">12 个数字，会对类似模式（如法国电话号码）进行验证</span><span class="sxs-lookup"><span data-stu-id="95cb4-1709">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-1710">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-1710">Checksum</span></span>

<span data-ttu-id="95cb4-1711">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-1711">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-1712">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-1712">Definition</span></span>

<span data-ttu-id="95cb4-1713">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-1713">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-1714">函数 Func_french_drivers_license 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1714">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-1715">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="95cb4-1715">At least one of the following is true:</span></span>
- <span data-ttu-id="95cb4-1716">找到 Keyword_french_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1716">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="95cb4-1717">函数 Func_eu_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1717">The function Func_eu_date finds a date in the right date format.</span></span>

```
<!-- France Driver's License Number -->
<Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_french_drivers_license" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-1718">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1718">Keywords</span></span>

#### <a name="keywordfrenchdriverslicense"></a><span data-ttu-id="95cb4-1719">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="95cb4-1719">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="95cb4-1720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="95cb4-1720">drivers licence</span></span>
- <span data-ttu-id="95cb4-1721">drivers license</span><span class="sxs-lookup"><span data-stu-id="95cb4-1721">drivers license</span></span>
- <span data-ttu-id="95cb4-1722">driving licence</span><span class="sxs-lookup"><span data-stu-id="95cb4-1722">driving licence</span></span>
- <span data-ttu-id="95cb4-1723">driving license</span><span class="sxs-lookup"><span data-stu-id="95cb4-1723">driving license</span></span>
- <span data-ttu-id="95cb4-1724">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="95cb4-1724">permis de conduire</span></span>
- <span data-ttu-id="95cb4-1725">licence number</span><span class="sxs-lookup"><span data-stu-id="95cb4-1725">licence number</span></span>
- <span data-ttu-id="95cb4-1726">license number</span><span class="sxs-lookup"><span data-stu-id="95cb4-1726">license number</span></span>
- <span data-ttu-id="95cb4-1727">licence numbers</span><span class="sxs-lookup"><span data-stu-id="95cb4-1727">licence numbers</span></span>
- <span data-ttu-id="95cb4-1728">license numbers</span><span class="sxs-lookup"><span data-stu-id="95cb4-1728">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="95cb4-1729">法国国家/地区 ID 卡 (CNI)</span><span class="sxs-lookup"><span data-stu-id="95cb4-1729">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-1730">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-1730">Format</span></span>

<span data-ttu-id="95cb4-1731">12 个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1731">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-1732">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-1732">Pattern</span></span>

<span data-ttu-id="95cb4-1733">12 个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1733">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-1734">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-1734">Checksum</span></span>

<span data-ttu-id="95cb4-1735">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-1735">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-1736">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-1736">Definition</span></span>

<span data-ttu-id="95cb4-1737">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-1737">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-1738">正则表达式 Regex_france_cni 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1738">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-1739">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1739">Keywords</span></span>

<span data-ttu-id="95cb4-1740">None</span><span class="sxs-lookup"><span data-stu-id="95cb4-1740">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="95cb4-1741">法国护照号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-1741">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-1742">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-1742">Format</span></span>

<span data-ttu-id="95cb4-1743">9 个数字和字母</span><span class="sxs-lookup"><span data-stu-id="95cb4-1743">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-1744">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-1744">Pattern</span></span>

<span data-ttu-id="95cb4-1745">九位数字和字母：</span><span class="sxs-lookup"><span data-stu-id="95cb4-1745">Nine digits and letters:</span></span>
- <span data-ttu-id="95cb4-1746">两位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1746">Two digits</span></span> 
- <span data-ttu-id="95cb4-1747">两个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="95cb4-1747">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="95cb4-1748">五位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1748">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-1749">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-1749">Checksum</span></span>

<span data-ttu-id="95cb4-1750">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-1750">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-1751">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-1751">Definition</span></span>

<span data-ttu-id="95cb4-1752">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-1752">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-1753">函数 Func_fr_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1753">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-1754">找到 Keyword_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1754">A keyword from Keyword_passport is found.</span></span>

```
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-1755">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1755">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="95cb4-1756">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="95cb4-1756">Keyword_passport</span></span>

- <span data-ttu-id="95cb4-1757">Passport Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-1757">Passport Number</span></span>
- <span data-ttu-id="95cb4-1758">Passport No</span><span class="sxs-lookup"><span data-stu-id="95cb4-1758">Passport No</span></span>
- <span data-ttu-id="95cb4-1759">Passport #</span><span class="sxs-lookup"><span data-stu-id="95cb4-1759">Passport #</span></span>
- <span data-ttu-id="95cb4-1760">登记卡</span><span class="sxs-lookup"><span data-stu-id="95cb4-1760">Passport#</span></span>
- <span data-ttu-id="95cb4-1761">PassportID</span><span class="sxs-lookup"><span data-stu-id="95cb4-1761">PassportID</span></span>
- <span data-ttu-id="95cb4-1762">Passportno</span><span class="sxs-lookup"><span data-stu-id="95cb4-1762">Passportno</span></span>
- <span data-ttu-id="95cb4-1763">passportnumber</span><span class="sxs-lookup"><span data-stu-id="95cb4-1763">passportnumber</span></span>
- <span data-ttu-id="95cb4-1764">パスポート</span><span class="sxs-lookup"><span data-stu-id="95cb4-1764">パスポート</span></span>
- <span data-ttu-id="95cb4-1765">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="95cb4-1765">パスポート番号</span></span>
- <span data-ttu-id="95cb4-1766">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="95cb4-1766">パスポートのNum</span></span>
- <span data-ttu-id="95cb4-1767">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="95cb4-1767">パスポート ＃</span></span> 
- <span data-ttu-id="95cb4-1768">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="95cb4-1768">Numéro de passeport</span></span>
- <span data-ttu-id="95cb4-1769">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="95cb4-1769">Passeport n °</span></span>
- <span data-ttu-id="95cb4-1770">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="95cb4-1770">Passeport Non</span></span>
- <span data-ttu-id="95cb4-1771">Passeport #</span><span class="sxs-lookup"><span data-stu-id="95cb4-1771">Passeport #</span></span>
- <span data-ttu-id="95cb4-1772">Passeport #</span><span class="sxs-lookup"><span data-stu-id="95cb4-1772">Passeport#</span></span>
- <span data-ttu-id="95cb4-1773">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="95cb4-1773">PasseportNon</span></span>
- <span data-ttu-id="95cb4-1774">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="95cb4-1774">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="95cb4-1775">法国社会保险号 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="95cb4-1775">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-1776">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-1776">Format</span></span>

<span data-ttu-id="95cb4-1777">15 个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1777">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-1778">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-1778">Pattern</span></span>

<span data-ttu-id="95cb4-1779">必须匹配两种模式之一：</span><span class="sxs-lookup"><span data-stu-id="95cb4-1779">Must match one of two patterns:</span></span>
- <span data-ttu-id="95cb4-1780">13位数, 后跟一个空格, 后跟两个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1780">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="95cb4-1781">或者</span><span class="sxs-lookup"><span data-stu-id="95cb4-1781">or</span></span>
- <span data-ttu-id="95cb4-1782">15 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1782">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-1783">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-1783">Checksum</span></span>

<span data-ttu-id="95cb4-1784">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-1784">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-1785">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-1785">Definition</span></span>

<span data-ttu-id="95cb4-1786">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-1786">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-1787">函数 Func_french_insee 或 Func_fr_insee 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1787">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-1788">找到 Keyword_fr_insee 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1788">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="95cb4-1789">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1789">The checksum passes.</span></span>

<span data-ttu-id="95cb4-1790">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-1790">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-1791">函数 Func_french_insee 或 Func_fr_insee 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1791">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-1792">未找到 Keyword_fr_insee 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1792">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="95cb4-1793">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1793">The checksum passes.</span></span>

```
<!-- France INSEE -->
<Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="95">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="1">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-1794">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1794">Keywords</span></span>

#### <a name="keywordfrinsee"></a><span data-ttu-id="95cb4-1795">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="95cb4-1795">Keyword_fr_insee</span></span>

- <span data-ttu-id="95cb4-1796">insee</span><span class="sxs-lookup"><span data-stu-id="95cb4-1796">insee</span></span>
- <span data-ttu-id="95cb4-1797">securité sociale</span><span class="sxs-lookup"><span data-stu-id="95cb4-1797">securité sociale</span></span>
- <span data-ttu-id="95cb4-1798">securite sociale</span><span class="sxs-lookup"><span data-stu-id="95cb4-1798">securite sociale</span></span>
- <span data-ttu-id="95cb4-1799">national id</span><span class="sxs-lookup"><span data-stu-id="95cb4-1799">national id</span></span>
- <span data-ttu-id="95cb4-1800">national identification</span><span class="sxs-lookup"><span data-stu-id="95cb4-1800">national identification</span></span>
- <span data-ttu-id="95cb4-1801">numéro d identité</span><span class="sxs-lookup"><span data-stu-id="95cb4-1801">numéro d'identité</span></span>
- <span data-ttu-id="95cb4-1802">no d'identité</span><span class="sxs-lookup"><span data-stu-id="95cb4-1802">no d'identité</span></span>
- <span data-ttu-id="95cb4-1803">不。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1803">no.</span></span> <span data-ttu-id="95cb4-1804">d'identité</span><span class="sxs-lookup"><span data-stu-id="95cb4-1804">d'identité</span></span>
- <span data-ttu-id="95cb4-1805">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="95cb4-1805">numero d'identite</span></span>
- <span data-ttu-id="95cb4-1806">no d'identite</span><span class="sxs-lookup"><span data-stu-id="95cb4-1806">no d'identite</span></span>
- <span data-ttu-id="95cb4-1807">不。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1807">no.</span></span> <span data-ttu-id="95cb4-1808">d'identite</span><span class="sxs-lookup"><span data-stu-id="95cb4-1808">d'identite</span></span>
- <span data-ttu-id="95cb4-1809">social security number</span><span class="sxs-lookup"><span data-stu-id="95cb4-1809">social security number</span></span>
- <span data-ttu-id="95cb4-1810">social security code</span><span class="sxs-lookup"><span data-stu-id="95cb4-1810">social security code</span></span>
- <span data-ttu-id="95cb4-1811">social insurance number</span><span class="sxs-lookup"><span data-stu-id="95cb4-1811">social insurance number</span></span>
- <span data-ttu-id="95cb4-1812">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="95cb4-1812">le numéro d'identification nationale</span></span>
- <span data-ttu-id="95cb4-1813">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="95cb4-1813">d'identité nationale</span></span>
- <span data-ttu-id="95cb4-1814">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="95cb4-1814">numéro de sécurité sociale</span></span>
- <span data-ttu-id="95cb4-1815">le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="95cb4-1815">le code de la sécurité sociale</span></span>
- <span data-ttu-id="95cb4-1816">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="95cb4-1816">numéro d'assurance sociale</span></span>
- <span data-ttu-id="95cb4-1817">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="95cb4-1817">numéro de sécu</span></span>
- <span data-ttu-id="95cb4-1818">code sécu</span><span class="sxs-lookup"><span data-stu-id="95cb4-1818">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="95cb4-1819">德国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-1819">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-1820">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-1820">Format</span></span>

<span data-ttu-id="95cb4-1821">11 个数字和字母组合</span><span class="sxs-lookup"><span data-stu-id="95cb4-1821">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-1822">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-1822">Pattern</span></span>

<span data-ttu-id="95cb4-1823">11 位数字和字母（不区分大小写）：</span><span class="sxs-lookup"><span data-stu-id="95cb4-1823">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="95cb4-1824">一个数字或字母</span><span class="sxs-lookup"><span data-stu-id="95cb4-1824">A digit or letter</span></span> 
- <span data-ttu-id="95cb4-1825">两位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1825">Two digits</span></span> 
- <span data-ttu-id="95cb4-1826">六位数字或字母</span><span class="sxs-lookup"><span data-stu-id="95cb4-1826">Six digits or letters</span></span> 
- <span data-ttu-id="95cb4-1827">一位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1827">A digit</span></span> 
- <span data-ttu-id="95cb4-1828">一个数字或字母</span><span class="sxs-lookup"><span data-stu-id="95cb4-1828">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-1829">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-1829">Checksum</span></span>

<span data-ttu-id="95cb4-1830">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-1830">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-1831">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-1831">Definition</span></span>

<span data-ttu-id="95cb4-1832">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-1832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-1833">函数 Func_german_drivers_license 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1833">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-1834">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="95cb4-1834">At least one of the following is true:</span></span>
    - <span data-ttu-id="95cb4-1835">找到 Keyword_german_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1835">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="95cb4-1836">找到 Keyword_german_drivers_license_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1836">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="95cb4-1837">找到 Keyword_german_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1837">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="95cb4-1838">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1838">The checksum passes.</span></span>

```
<!-- German Driver's License Number -->
<Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_drivers_license_number" />
          <Match idRef="Keyword_german_drivers_license_collaborative" />
          <Match idRef="Keyword_german_drivers_license" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-1839">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1839">Keywords</span></span>

#### <a name="keywordgermandriverslicensenumber"></a><span data-ttu-id="95cb4-1840">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="95cb4-1840">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="95cb4-1841">führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="95cb4-1841">Führerschein</span></span>
- <span data-ttu-id="95cb4-1842">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="95cb4-1842">Fuhrerschein</span></span>
- <span data-ttu-id="95cb4-1843">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="95cb4-1843">Fuehrerschein</span></span>
- <span data-ttu-id="95cb4-1844">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="95cb4-1844">Führerscheinnummer</span></span>
- <span data-ttu-id="95cb4-1845">Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="95cb4-1845">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="95cb4-1846">Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="95cb4-1846">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="95cb4-1847">führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="95cb4-1847">Führerschein-</span></span> 
- <span data-ttu-id="95cb4-1848">Fuhrerschein-</span><span class="sxs-lookup"><span data-stu-id="95cb4-1848">Fuhrerschein-</span></span> 
- <span data-ttu-id="95cb4-1849">Fuehrerschein-</span><span class="sxs-lookup"><span data-stu-id="95cb4-1849">Fuehrerschein-</span></span> 
- <span data-ttu-id="95cb4-1850">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="95cb4-1850">FührerscheinnummerNr</span></span>
- <span data-ttu-id="95cb4-1851">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="95cb4-1851">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="95cb4-1852">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="95cb4-1852">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="95cb4-1853">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="95cb4-1853">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="95cb4-1854">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="95cb4-1854">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="95cb4-1855">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="95cb4-1855">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="95cb4-1856">Führerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="95cb4-1856">Führerschein- Nr</span></span>
- <span data-ttu-id="95cb4-1857">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="95cb4-1857">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="95cb4-1858">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="95cb4-1858">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="95cb4-1859">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="95cb4-1859">Führerschein- Klasse</span></span> 
- <span data-ttu-id="95cb4-1860">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="95cb4-1860">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="95cb4-1861">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="95cb4-1861">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="95cb4-1862">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="95cb4-1862">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="95cb4-1863">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="95cb4-1863">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="95cb4-1864">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="95cb4-1864">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="95cb4-1865">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="95cb4-1865">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="95cb4-1866">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="95cb4-1866">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="95cb4-1867">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="95cb4-1867">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="95cb4-1868">Führerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="95cb4-1868">Führerschein- Nr</span></span> 
- <span data-ttu-id="95cb4-1869">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="95cb4-1869">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="95cb4-1870">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="95cb4-1870">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="95cb4-1871">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="95cb4-1871">Führerschein- Klasse</span></span> 
- <span data-ttu-id="95cb4-1872">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="95cb4-1872">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="95cb4-1873">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="95cb4-1873">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="95cb4-1874">通讯</span><span class="sxs-lookup"><span data-stu-id="95cb4-1874">DL</span></span> 
- <span data-ttu-id="95cb4-1875">DLS</span><span class="sxs-lookup"><span data-stu-id="95cb4-1875">DLS</span></span>
- <span data-ttu-id="95cb4-1876">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="95cb4-1876">Driv Lic</span></span> 
- <span data-ttu-id="95cb4-1877">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="95cb4-1877">Driv Licen</span></span> 
- <span data-ttu-id="95cb4-1878">Driv License</span><span class="sxs-lookup"><span data-stu-id="95cb4-1878">Driv License</span></span>
- <span data-ttu-id="95cb4-1879">Driv Licenses</span><span class="sxs-lookup"><span data-stu-id="95cb4-1879">Driv Licenses</span></span> 
- <span data-ttu-id="95cb4-1880">Driv Licence</span><span class="sxs-lookup"><span data-stu-id="95cb4-1880">Driv Licence</span></span> 
- <span data-ttu-id="95cb4-1881">Driv Licences</span><span class="sxs-lookup"><span data-stu-id="95cb4-1881">Driv Licences</span></span> 
- <span data-ttu-id="95cb4-1882">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="95cb4-1882">Driv Lic</span></span> 
- <span data-ttu-id="95cb4-1883">Driver Licen</span><span class="sxs-lookup"><span data-stu-id="95cb4-1883">Driver Licen</span></span> 
- <span data-ttu-id="95cb4-1884">Driver License</span><span class="sxs-lookup"><span data-stu-id="95cb4-1884">Driver License</span></span> 
- <span data-ttu-id="95cb4-1885">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="95cb4-1885">Driver Licenses</span></span> 
- <span data-ttu-id="95cb4-1886">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="95cb4-1886">Driver Licence</span></span> 
- <span data-ttu-id="95cb4-1887">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="95cb4-1887">Driver Licences</span></span> 
- <span data-ttu-id="95cb4-1888">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="95cb4-1888">Drivers Lic</span></span> 
- <span data-ttu-id="95cb4-1889">Drivers Licen</span><span class="sxs-lookup"><span data-stu-id="95cb4-1889">Drivers Licen</span></span> 
- <span data-ttu-id="95cb4-1890">Drivers License</span><span class="sxs-lookup"><span data-stu-id="95cb4-1890">Drivers License</span></span> 
- <span data-ttu-id="95cb4-1891">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="95cb4-1891">Drivers Licenses</span></span> 
- <span data-ttu-id="95cb4-1892">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="95cb4-1892">Drivers Licence</span></span> 
- <span data-ttu-id="95cb4-1893">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="95cb4-1893">Drivers Licences</span></span> 
- <span data-ttu-id="95cb4-1894">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="95cb4-1894">Driver's Lic</span></span> 
- <span data-ttu-id="95cb4-1895">Driver's Licen</span><span class="sxs-lookup"><span data-stu-id="95cb4-1895">Driver's Licen</span></span> 
- <span data-ttu-id="95cb4-1896">Driver's License</span><span class="sxs-lookup"><span data-stu-id="95cb4-1896">Driver's License</span></span> 
- <span data-ttu-id="95cb4-1897">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="95cb4-1897">Driver's Licenses</span></span> 
- <span data-ttu-id="95cb4-1898">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="95cb4-1898">Driver's Licence</span></span> 
- <span data-ttu-id="95cb4-1899">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="95cb4-1899">Driver's Licences</span></span> 
- <span data-ttu-id="95cb4-1900">Driving Lic</span><span class="sxs-lookup"><span data-stu-id="95cb4-1900">Driving Lic</span></span> 
- <span data-ttu-id="95cb4-1901">Driving Licen</span><span class="sxs-lookup"><span data-stu-id="95cb4-1901">Driving Licen</span></span> 
- <span data-ttu-id="95cb4-1902">Driving License</span><span class="sxs-lookup"><span data-stu-id="95cb4-1902">Driving License</span></span> 
- <span data-ttu-id="95cb4-1903">Driving Licenses</span><span class="sxs-lookup"><span data-stu-id="95cb4-1903">Driving Licenses</span></span> 
- <span data-ttu-id="95cb4-1904">Driving Licence</span><span class="sxs-lookup"><span data-stu-id="95cb4-1904">Driving Licence</span></span> 
- <span data-ttu-id="95cb4-1905">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="95cb4-1905">Driving Licences</span></span>

#### <a name="keywordgermandriverslicensecollaborative"></a><span data-ttu-id="95cb4-1906">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="95cb4-1906">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="95cb4-1907">Nr-führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="95cb4-1907">Nr-Führerschein</span></span> 
- <span data-ttu-id="95cb4-1908">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="95cb4-1908">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="95cb4-1909">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="95cb4-1909">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="95cb4-1910">führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="95cb4-1910">No-Führerschein</span></span> 
- <span data-ttu-id="95cb4-1911">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="95cb4-1911">No-Fuhrerschein</span></span> 
- <span data-ttu-id="95cb4-1912">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="95cb4-1912">No-Fuehrerschein</span></span> 
- <span data-ttu-id="95cb4-1913">N-führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="95cb4-1913">N-Führerschein</span></span> 
- <span data-ttu-id="95cb4-1914">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="95cb4-1914">N-Fuhrerschein</span></span> 
- <span data-ttu-id="95cb4-1915">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="95cb4-1915">N-Fuehrerschein</span></span>
- <span data-ttu-id="95cb4-1916">Nr-führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="95cb4-1916">Nr-Führerschein</span></span> 
- <span data-ttu-id="95cb4-1917">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="95cb4-1917">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="95cb4-1918">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="95cb4-1918">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="95cb4-1919">führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="95cb4-1919">No-Führerschein</span></span> 
- <span data-ttu-id="95cb4-1920">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="95cb4-1920">No-Fuhrerschein</span></span> 
- <span data-ttu-id="95cb4-1921">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="95cb4-1921">No-Fuehrerschein</span></span> 
- <span data-ttu-id="95cb4-1922">N-führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="95cb4-1922">N-Führerschein</span></span> 
- <span data-ttu-id="95cb4-1923">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="95cb4-1923">N-Fuhrerschein</span></span> 
- <span data-ttu-id="95cb4-1924">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="95cb4-1924">N-Fuehrerschein</span></span> 

#### <a name="keywordgermandriverslicense"></a><span data-ttu-id="95cb4-1925">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="95cb4-1925">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="95cb4-1926">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="95cb4-1926">ausstellungsdatum</span></span>
- <span data-ttu-id="95cb4-1927">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="95cb4-1927">ausstellungsort</span></span>
- <span data-ttu-id="95cb4-1928">ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="95cb4-1928">ausstellende behöde</span></span>
- <span data-ttu-id="95cb4-1929">ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="95cb4-1929">ausstellende behorde</span></span>
- <span data-ttu-id="95cb4-1930">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="95cb4-1930">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="95cb4-1931">德国护照号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-1931">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-1932">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-1932">Format</span></span>

<span data-ttu-id="95cb4-1933">10 个数字或字母</span><span class="sxs-lookup"><span data-stu-id="95cb4-1933">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-1934">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-1934">Pattern</span></span>

<span data-ttu-id="95cb4-1935">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="95cb4-1935">Pattern must include all of the following:</span></span>
- <span data-ttu-id="95cb4-1936">第一个字符是这一组（C、F、G、H、J、K）中的数字或字母</span><span class="sxs-lookup"><span data-stu-id="95cb4-1936">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="95cb4-1937">三位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1937">Three digits</span></span> 
- <span data-ttu-id="95cb4-1938">五位数字或字母都来源于这一组（C、-H、J-N、P、R、T，V-Z）</span><span class="sxs-lookup"><span data-stu-id="95cb4-1938">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="95cb4-1939">一位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1939">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-1940">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-1940">Checksum</span></span>

<span data-ttu-id="95cb4-1941">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-1941">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-1942">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-1942">Definition</span></span>

<span data-ttu-id="95cb4-1943">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-1943">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-1944">函数 Func_german_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1944">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-1945">找到以下任意五个关键字列表中的关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1945">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="95cb4-1946">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1946">The checksum passes.</span></span>

<span data-ttu-id="95cb4-1947">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-1947">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-1948">函数 Func_german_passport_data 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1948">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-1949">找到以下任意五个关键字列表中的关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1949">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="95cb4-1950">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1950">The checksum passes.</span></span>

```
<!-- German Passport Number -->
<Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport_data" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-1951">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1951">Keywords</span></span>

#### <a name="keywordgermanpassport"></a><span data-ttu-id="95cb4-1952">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="95cb4-1952">Keyword_german_passport</span></span>

- <span data-ttu-id="95cb4-1953">reisepass</span><span class="sxs-lookup"><span data-stu-id="95cb4-1953">reisepass</span></span>
- <span data-ttu-id="95cb4-1954">reisepasse</span><span class="sxs-lookup"><span data-stu-id="95cb4-1954">reisepasse</span></span>
- <span data-ttu-id="95cb4-1955">reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="95cb4-1955">reisepassnummer</span></span>
- <span data-ttu-id="95cb4-1956">登记卡</span><span class="sxs-lookup"><span data-stu-id="95cb4-1956">passport</span></span>
- <span data-ttu-id="95cb4-1957">passports</span><span class="sxs-lookup"><span data-stu-id="95cb4-1957">passports</span></span>

#### <a name="keywordgermanpassportcollaborative"></a><span data-ttu-id="95cb4-1958">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="95cb4-1958">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="95cb4-1959">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="95cb4-1959">geburtsdatum</span></span>
- <span data-ttu-id="95cb4-1960">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="95cb4-1960">ausstellungsdatum</span></span>
- <span data-ttu-id="95cb4-1961">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="95cb4-1961">ausstellungsort</span></span>

#### <a name="keywordgermanpassportnumber"></a><span data-ttu-id="95cb4-1962">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="95cb4-1962">Keyword_german_passport_number</span></span>

<span data-ttu-id="95cb4-1963">Reisepass Nr-Reisepass</span><span class="sxs-lookup"><span data-stu-id="95cb4-1963">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keywordgermanpassport1"></a><span data-ttu-id="95cb4-1964">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="95cb4-1964">Keyword_german_passport1</span></span>

<span data-ttu-id="95cb4-1965">Reisepass-Nr</span><span class="sxs-lookup"><span data-stu-id="95cb4-1965">Reisepass-Nr</span></span>

#### <a name="keywordgermanpassport2"></a><span data-ttu-id="95cb4-1966">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="95cb4-1966">Keyword_german_passport2</span></span>

<span data-ttu-id="95cb4-1967">bnationalit</span><span class="sxs-lookup"><span data-stu-id="95cb4-1967">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="95cb4-1968">德国身份证号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-1968">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-1969">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-1969">Format</span></span>

<span data-ttu-id="95cb4-1970">自2010年11月1日起: 九个字母和数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1970">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="95cb4-1971">从1年4月1987至31年10月 2010:10 位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1971">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-1972">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-1972">Pattern</span></span>

<span data-ttu-id="95cb4-1973">自 2010 年 11 月 1 日起：</span><span class="sxs-lookup"><span data-stu-id="95cb4-1973">Since 1 November 2010:</span></span>
- <span data-ttu-id="95cb4-1974">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="95cb4-1974">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="95cb4-1975">八个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1975">Eight digits</span></span>

<span data-ttu-id="95cb4-1976">介于1年4月1987至 31 10 月 2010:</span><span class="sxs-lookup"><span data-stu-id="95cb4-1976">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="95cb4-1977">10 个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1977">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-1978">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-1978">Checksum</span></span>

<span data-ttu-id="95cb4-1979">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-1979">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-1980">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-1980">Definition</span></span>

<span data-ttu-id="95cb4-1981">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-1981">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-1982">正则表达式 Regex_germany_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1982">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-1983">找到 Keyword_germany_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-1983">A keyword from Keyword_germany_id_card is found.</span></span>

```
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-1984">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-1984">Keywords</span></span>

#### <a name="keywordgermanyidcard"></a><span data-ttu-id="95cb4-1985">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="95cb4-1985">Keyword_germany_id_card</span></span>

- <span data-ttu-id="95cb4-1986">Identity Card</span><span class="sxs-lookup"><span data-stu-id="95cb4-1986">Identity Card</span></span>
- <span data-ttu-id="95cb4-1987">ID</span><span class="sxs-lookup"><span data-stu-id="95cb4-1987">ID</span></span>
- <span data-ttu-id="95cb4-1988">id</span><span class="sxs-lookup"><span data-stu-id="95cb4-1988">Identification</span></span>
- <span data-ttu-id="95cb4-1989">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="95cb4-1989">Personalausweis</span></span>
- <span data-ttu-id="95cb4-1990">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="95cb4-1990">Identifizierungsnummer</span></span>
- <span data-ttu-id="95cb4-1991">Ausweis</span><span class="sxs-lookup"><span data-stu-id="95cb4-1991">Ausweis</span></span>
- <span data-ttu-id="95cb4-1992">Identifikation</span><span class="sxs-lookup"><span data-stu-id="95cb4-1992">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="95cb4-1993">希腊国家 ID 卡</span><span class="sxs-lookup"><span data-stu-id="95cb4-1993">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-1994">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-1994">Format</span></span>

<span data-ttu-id="95cb4-1995">7-8 个字母和数字组合加一个短划线</span><span class="sxs-lookup"><span data-stu-id="95cb4-1995">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-1996">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-1996">Pattern</span></span>

<span data-ttu-id="95cb4-1997">七个字母和数字（旧格式）：</span><span class="sxs-lookup"><span data-stu-id="95cb4-1997">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="95cb4-1998">一个字母（希腊字母表中的任一字母） </span><span class="sxs-lookup"><span data-stu-id="95cb4-1998">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="95cb4-1999">一个短划线 </span><span class="sxs-lookup"><span data-stu-id="95cb4-1999">A dash</span></span> 
- <span data-ttu-id="95cb4-2000">六个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2000">Six digits</span></span>

<span data-ttu-id="95cb4-2001">八个字母和数字（新格式）：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2001">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="95cb4-2002">大写字符同时出现在希腊和拉丁字母表中的两个字母 (ABEZHIKMNOPTYX) </span><span class="sxs-lookup"><span data-stu-id="95cb4-2002">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="95cb4-2003">一个短划线 </span><span class="sxs-lookup"><span data-stu-id="95cb4-2003">A dash</span></span> 
- <span data-ttu-id="95cb4-2004">六位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2004">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2005">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2005">Checksum</span></span>

<span data-ttu-id="95cb4-2006">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-2006">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2007">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2007">Definition</span></span>

<span data-ttu-id="95cb4-2008">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2008">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2009">正则表达式 Regex_greece_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2009">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2010">找到 Keyword_greece_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2010">A keyword from Keyword_greece_id_card is found.</span></span>

```
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2011">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2011">Keywords</span></span>

#### <a name="keywordgreeceidcard"></a><span data-ttu-id="95cb4-2012">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="95cb4-2012">Keyword_greece_id_card</span></span>

- <span data-ttu-id="95cb4-2013">Greek identity Card</span><span class="sxs-lookup"><span data-stu-id="95cb4-2013">Greek identity Card</span></span>
- <span data-ttu-id="95cb4-2014">Tautotita</span><span class="sxs-lookup"><span data-stu-id="95cb4-2014">Tautotita</span></span>
- <span data-ttu-id="95cb4-2015">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="95cb4-2015">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="95cb4-2016">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="95cb4-2016">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="95cb4-2017">香港身份证 (HKID) 号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2017">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2018">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2018">Format</span></span>

<span data-ttu-id="95cb4-2019">8-9 个字母和数字组合，最后一个字符两边可选择加括号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2019">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2020">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2020">Pattern</span></span>

<span data-ttu-id="95cb4-2021">8-9 个字母组合：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2021">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="95cb4-2022">1-2 个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="95cb4-2022">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="95cb4-2023">六个数字 </span><span class="sxs-lookup"><span data-stu-id="95cb4-2023">Six digits</span></span> 
- <span data-ttu-id="95cb4-2024">最后一个字符（任意数字或字母 A）是校验位，两边可以选择加括号。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2024">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2025">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2025">Checksum</span></span>

<span data-ttu-id="95cb4-2026">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-2026">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2027">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2027">Definition</span></span>

<span data-ttu-id="95cb4-2028">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2028">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2029">函数 Func_hong_kong_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2029">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2030">找到 Keyword_hong_kong_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2030">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="95cb4-2031">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2031">The checksum passes.</span></span>

<span data-ttu-id="95cb4-2032">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2032">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2033">函数 Func_hong_kong_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2033">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2034">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2034">The checksum passes.</span></span>

```
<!-- Hong Kong Identity Card (HKID) number -->
<Entity id="e63c28a7-ad29-4c17-a41a-3d2a0b70fd9c" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_hong_kong_id_card"/>
     <Match idRef="Keyword_hong_kong_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_hong_kong_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2035">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2035">Keywords</span></span>

#### <a name="keywordhongkongidcard"></a><span data-ttu-id="95cb4-2036">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="95cb4-2036">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="95cb4-2037">中国香港恒等卡片</span><span class="sxs-lookup"><span data-stu-id="95cb4-2037">hong kong identity card</span></span>
- <span data-ttu-id="95cb4-2038">HKIDC</span><span class="sxs-lookup"><span data-stu-id="95cb4-2038">HKIDC</span></span>
- <span data-ttu-id="95cb4-2039">id card</span><span class="sxs-lookup"><span data-stu-id="95cb4-2039">id card</span></span>
- <span data-ttu-id="95cb4-2040">identity card</span><span class="sxs-lookup"><span data-stu-id="95cb4-2040">identity card</span></span>
- <span data-ttu-id="95cb4-2041">hk identity 卡片</span><span class="sxs-lookup"><span data-stu-id="95cb4-2041">hk identity card</span></span>
- <span data-ttu-id="95cb4-2042">香港 id</span><span class="sxs-lookup"><span data-stu-id="95cb4-2042">hong kong id</span></span>
- <span data-ttu-id="95cb4-2043">香港身份證</span><span class="sxs-lookup"><span data-stu-id="95cb4-2043">香港身份證</span></span>
- <span data-ttu-id="95cb4-2044">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="95cb4-2044">香港永久性居民身份證</span></span>
- <span data-ttu-id="95cb4-2045">證</span><span class="sxs-lookup"><span data-stu-id="95cb4-2045">身份證</span></span>
- <span data-ttu-id="95cb4-2046">身份証</span><span class="sxs-lookup"><span data-stu-id="95cb4-2046">身份証</span></span>
- <span data-ttu-id="95cb4-2047">身分證</span><span class="sxs-lookup"><span data-stu-id="95cb4-2047">身分證</span></span>
- <span data-ttu-id="95cb4-2048">身分証</span><span class="sxs-lookup"><span data-stu-id="95cb4-2048">身分証</span></span>
- <span data-ttu-id="95cb4-2049">香港身份証</span><span class="sxs-lookup"><span data-stu-id="95cb4-2049">香港身份証</span></span>
- <span data-ttu-id="95cb4-2050">香港身分證</span><span class="sxs-lookup"><span data-stu-id="95cb4-2050">香港身分證</span></span>
- <span data-ttu-id="95cb4-2051">香港身分証</span><span class="sxs-lookup"><span data-stu-id="95cb4-2051">香港身分証</span></span>
- <span data-ttu-id="95cb4-2052">香港身份證</span><span class="sxs-lookup"><span data-stu-id="95cb4-2052">香港身份證</span></span>
- <span data-ttu-id="95cb4-2053">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="95cb4-2053">香港居民身份證</span></span>
- <span data-ttu-id="95cb4-2054">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="95cb4-2054">香港居民身份証</span></span>
- <span data-ttu-id="95cb4-2055">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="95cb4-2055">香港居民身分證</span></span>
- <span data-ttu-id="95cb4-2056">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="95cb4-2056">香港居民身分証</span></span>
- <span data-ttu-id="95cb4-2057">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="95cb4-2057">香港永久性居民身份証</span></span>
- <span data-ttu-id="95cb4-2058">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="95cb4-2058">香港永久性居民身分證</span></span>
- <span data-ttu-id="95cb4-2059">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="95cb4-2059">香港永久性居民身分証</span></span>
- <span data-ttu-id="95cb4-2060">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="95cb4-2060">香港永久性居民身份證</span></span>
- <span data-ttu-id="95cb4-2061">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="95cb4-2061">香港非永久性居民身份證</span></span>
- <span data-ttu-id="95cb4-2062">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="95cb4-2062">香港非永久性居民身份証</span></span>
- <span data-ttu-id="95cb4-2063">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="95cb4-2063">香港非永久性居民身分證</span></span>
- <span data-ttu-id="95cb4-2064">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="95cb4-2064">香港非永久性居民身分証</span></span>
- <span data-ttu-id="95cb4-2065">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="95cb4-2065">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="95cb4-2066">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="95cb4-2066">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="95cb4-2067">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="95cb4-2067">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="95cb4-2068">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="95cb4-2068">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="95cb4-2069">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="95cb4-2069">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="95cb4-2070">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="95cb4-2070">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="95cb4-2071">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="95cb4-2071">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="95cb4-2072">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="95cb4-2072">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="95cb4-2073">印度永久帐号 (PAN)</span><span class="sxs-lookup"><span data-stu-id="95cb4-2073">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2074">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2074">Format</span></span>

<span data-ttu-id="95cb4-2075">10 个字母或数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2075">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2076">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2076">Pattern</span></span>

<span data-ttu-id="95cb4-2077">10 个字母或数字：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2077">10 letters or digits:</span></span>
- <span data-ttu-id="95cb4-2078">五个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="95cb4-2078">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="95cb4-2079">四位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2079">Four digits</span></span> 
- <span data-ttu-id="95cb4-2080">一个字母，是字母校验位</span><span class="sxs-lookup"><span data-stu-id="95cb4-2080">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2081">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2081">Checksum</span></span>

<span data-ttu-id="95cb4-2082">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-2082">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2083">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2083">Definition</span></span>

<span data-ttu-id="95cb4-2084">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2084">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2085">正则表达式 Regex_india_permanent_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2085">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2086">找到 Keyword_india_permanent_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2086">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="95cb4-2087">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2087">The checksum passes.</span></span>

```
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2088">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2088">Keywords</span></span>

#### <a name="keywordindiapermanentaccountnumber"></a><span data-ttu-id="95cb4-2089">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2089">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="95cb4-2090">Permanent Account Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2090">Permanent Account Number</span></span> 
- <span data-ttu-id="95cb4-2091">蛋糕</span><span class="sxs-lookup"><span data-stu-id="95cb4-2091">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="95cb4-2092">India Unique Identification (Aadhaar) Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2092">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2093">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2093">Format</span></span>

<span data-ttu-id="95cb4-2094">12 个数字（包含可选空格或短划线）</span><span class="sxs-lookup"><span data-stu-id="95cb4-2094">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2095">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2095">Pattern</span></span>

<span data-ttu-id="95cb4-2096">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2096">12 digits:</span></span>
- <span data-ttu-id="95cb4-2097">四个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2097">Four digits</span></span> 
- <span data-ttu-id="95cb4-2098">一个可选空格或短划线 </span><span class="sxs-lookup"><span data-stu-id="95cb4-2098">An optional space or dash</span></span> 
- <span data-ttu-id="95cb4-2099">四个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2099">Four digits</span></span> 
- <span data-ttu-id="95cb4-2100">一个可选空格或短划线 </span><span class="sxs-lookup"><span data-stu-id="95cb4-2100">An optional space or dash</span></span> 
- <span data-ttu-id="95cb4-2101">最后一个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="95cb4-2101">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2102">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2102">Checksum</span></span>

<span data-ttu-id="95cb4-2103">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-2103">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2104">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2104">Definition</span></span>

<span data-ttu-id="95cb4-2105">DLP 策略 85% 确信在300个字符的邻近度内检测到此类型的敏感信息: 函数 Func_india_aadhaar 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2105">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="95cb4-2106">找到 Keyword_india_aadhar 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2106">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="95cb4-2107">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2107">The checksum passes.</span></span>
<span data-ttu-id="95cb4-2108">DLP 策略 75% 确信在300个字符的邻近度内检测到此类型的敏感信息: 函数 Func_india_aadhaar 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2108">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="95cb4-2109">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2109">The checksum passes.</span></span>
<span data-ttu-id="95cb4-2110"><!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="95cb4-2110"></span></span>

### <a name="keywords"></a><span data-ttu-id="95cb4-2111">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2111">Keywords</span></span>
   
#### <a name="keywordindiaaadhar"></a><span data-ttu-id="95cb4-2112">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="95cb4-2112">Keyword_india_aadhar</span></span>
- <span data-ttu-id="95cb4-2113">Aadhar</span><span class="sxs-lookup"><span data-stu-id="95cb4-2113">Aadhar</span></span>
- <span data-ttu-id="95cb4-2114">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="95cb4-2114">Aadhaar</span></span>
- <span data-ttu-id="95cb4-2115">UID</span><span class="sxs-lookup"><span data-stu-id="95cb4-2115">UID</span></span>
- <span data-ttu-id="95cb4-2116">आधार</span><span class="sxs-lookup"><span data-stu-id="95cb4-2116">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="95cb4-2117">印度尼西亚身份证 (KTP) 号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2117">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2118">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2118">Format</span></span>

<span data-ttu-id="95cb4-2119">16 个数字（包含可选点）</span><span class="sxs-lookup"><span data-stu-id="95cb4-2119">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2120">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2120">Pattern</span></span>

<span data-ttu-id="95cb4-2121">16 个数字：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2121">16 digits:</span></span>
- <span data-ttu-id="95cb4-2122">两位省代码 </span><span class="sxs-lookup"><span data-stu-id="95cb4-2122">Two-digit province code</span></span> 
- <span data-ttu-id="95cb4-2123">一个点（可选） </span><span class="sxs-lookup"><span data-stu-id="95cb4-2123">A period (optional)</span></span> 
- <span data-ttu-id="95cb4-2124">两位摄政统治区或城市代码 </span><span class="sxs-lookup"><span data-stu-id="95cb4-2124">Two-digit regency or city code</span></span> 
- <span data-ttu-id="95cb4-2125">两位住宅小区代码 </span><span class="sxs-lookup"><span data-stu-id="95cb4-2125">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="95cb4-2126">一个点（可选） </span><span class="sxs-lookup"><span data-stu-id="95cb4-2126">A period (optional)</span></span> 
- <span data-ttu-id="95cb4-2127">六个数字，采用  DDMMYY 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="95cb4-2127">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="95cb4-2128">一个点（可选） </span><span class="sxs-lookup"><span data-stu-id="95cb4-2128">A period (optional)</span></span> 
- <span data-ttu-id="95cb4-2129">四个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2129">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2130">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2130">Checksum</span></span>

<span data-ttu-id="95cb4-2131">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-2131">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2132">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2132">Definition</span></span>

<span data-ttu-id="95cb4-2133">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2133">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2134">正则表达式 Regex_indonesia_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2134">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2135">找到 Keyword_indonesia_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2135">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="95cb4-2136">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2136">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2137">正则表达式 Regex_indonesia_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2137">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

```
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_indonesia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2138">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2138">Keywords</span></span>
   
#### <a name="keywordindonesiaidcard"></a><span data-ttu-id="95cb4-2139">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="95cb4-2139">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="95cb4-2140">KTP</span><span class="sxs-lookup"><span data-stu-id="95cb4-2140">KTP</span></span>
- <span data-ttu-id="95cb4-2141">Kartu Tanda Penduduk</span><span class="sxs-lookup"><span data-stu-id="95cb4-2141">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="95cb4-2142">Nomor Induk Kependudukan</span><span class="sxs-lookup"><span data-stu-id="95cb4-2142">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="95cb4-2143">国际银行帐号 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="95cb4-2143">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2144">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2144">Format</span></span>

<span data-ttu-id="95cb4-2145">国家/地区代码（两个字母）加校验位（两个数字）以及 bban 号码（最多 30 个字符）</span><span class="sxs-lookup"><span data-stu-id="95cb4-2145">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2146">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2146">Pattern</span></span>

<span data-ttu-id="95cb4-2147">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2147">Pattern must include all of the following:</span></span>

- <span data-ttu-id="95cb4-2148">两个字母的国家/地区代码</span><span class="sxs-lookup"><span data-stu-id="95cb4-2148">Two-letter country code</span></span>
- <span data-ttu-id="95cb4-2149">两个校验位（后跟一个可选空间） </span><span class="sxs-lookup"><span data-stu-id="95cb4-2149">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="95cb4-2150">1-7 个包含 4 个字母或数字的组（可以使用空格进行分隔）</span><span class="sxs-lookup"><span data-stu-id="95cb4-2150">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="95cb4-2151">1-3 个字母或数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2151">1-3 letters or digits</span></span>

<span data-ttu-id="95cb4-p134">每个国家/地区的格式稍有不同。IBAN 敏感信息类型涵盖这 60 个国家/地区：</span><span class="sxs-lookup"><span data-stu-id="95cb4-p134">The format for each country is slightly different. The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="95cb4-2154">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span><span class="sxs-lookup"><span data-stu-id="95cb4-2154">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2155">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2155">Checksum</span></span>

<span data-ttu-id="95cb4-2156">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-2156">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2157">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2157">Definition</span></span>

<span data-ttu-id="95cb4-2158">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2158">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2159">函数 Func_iban 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2159">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2160">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2160">The checksum passes.</span></span>

```
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2161">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2161">Keywords</span></span>

<span data-ttu-id="95cb4-2162">None</span><span class="sxs-lookup"><span data-stu-id="95cb4-2162">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="95cb4-2163">IP 地址</span><span class="sxs-lookup"><span data-stu-id="95cb4-2163">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2164">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2164">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="95cb4-2165">IPv4</span><span class="sxs-lookup"><span data-stu-id="95cb4-2165">IPv4:</span></span>
<span data-ttu-id="95cb4-2166">解释 IPv4 地址格式化（点）版本或非格式化（没有点）版本的复杂模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2166">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="95cb4-2167">ipv4</span><span class="sxs-lookup"><span data-stu-id="95cb4-2167">IPv6:</span></span>
<span data-ttu-id="95cb4-2168"> 解释格式化 IPv6 号码（包含冒号）的复杂模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2168">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2169">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2169">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2170">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2170">Checksum</span></span>

<span data-ttu-id="95cb4-2171">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-2171">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2172">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2172">Definition</span></span>

<span data-ttu-id="95cb4-2173">对于 IPv6，在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2173">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2174">正则表达式 Regex_ipv6_address 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2174">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2175">未找到 Keyword_ipaddress 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2175">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="95cb4-2176">对于 IPv4，在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2176">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2177">正则表达式 Regex_ipv4_address 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2177">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2178">找到 Keyword_ipaddress 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2178">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="95cb4-2179">对于 IPv6，在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2179">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2180">正则表达式 Regex_ipv6_address 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2180">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2181">未找到 Keyword_ipaddress 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2181">No keyword from Keyword_ipaddress is found.</span></span>

```
    <!-- IP Address -->
    <Entity id="1daa4ad5-e2dd-4ca4-a788-54722c09efb2" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv4_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2182">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2182">Keywords</span></span>

#### <a name="keywordipaddress"></a><span data-ttu-id="95cb4-2183">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="95cb4-2183">Keyword_ipaddress</span></span>

- <span data-ttu-id="95cb4-2184">IP（此关键字区分大小写）</span><span class="sxs-lookup"><span data-stu-id="95cb4-2184">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="95cb4-2185">ip address</span><span class="sxs-lookup"><span data-stu-id="95cb4-2185">ip address</span></span> 
- <span data-ttu-id="95cb4-2186">ip addresses</span><span class="sxs-lookup"><span data-stu-id="95cb4-2186">ip addresses</span></span>
- <span data-ttu-id="95cb4-2187">internet protocol</span><span class="sxs-lookup"><span data-stu-id="95cb4-2187">internet protocol</span></span>
- <span data-ttu-id="95cb4-2188">IP-כתובת ה</span><span class="sxs-lookup"><span data-stu-id="95cb4-2188">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="95cb4-2189">国际分类的 Diseases (ICD-10 CM)</span><span class="sxs-lookup"><span data-stu-id="95cb4-2189">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2190">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2190">Format</span></span>

<span data-ttu-id="95cb4-2191">Dictionary</span><span class="sxs-lookup"><span data-stu-id="95cb4-2191">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2192">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2192">Pattern</span></span>

<span data-ttu-id="95cb4-2193">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2193">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2194">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2194">Checksum</span></span>

<span data-ttu-id="95cb4-2195">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-2195">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2196">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2196">Definition</span></span>

<span data-ttu-id="95cb4-2197">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2197">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2198">找到 Dictionary_icd_10_cm 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2198">A keyword from Dictionary_icd_10_cm is found.</span></span>

```
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

<span data-ttu-id="95cb4-2199">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2199">Keywords</span></span>

<span data-ttu-id="95cb4-2200">Dictionary_icd_10_cm 关键字词典中的任何术语, 它基于[Diseases 的国际分类、第十个修订、临床修改 (icd-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604)。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2200">Any term from the Dictionary_icd_10_cm keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="95cb4-2201">此类型仅查找术语, 而不是保险代码。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2201">This type looks only for the term, not the insurance codes.</span></span>

   
## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="95cb4-2202">国际分类的 Diseases (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="95cb4-2202">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2203">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2203">Format</span></span>

<span data-ttu-id="95cb4-2204">Dictionary</span><span class="sxs-lookup"><span data-stu-id="95cb4-2204">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2205">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2205">Pattern</span></span>

<span data-ttu-id="95cb4-2206">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2206">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2207">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2207">Checksum</span></span>

<span data-ttu-id="95cb4-2208">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-2208">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2209">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2209">Definition</span></span>

<span data-ttu-id="95cb4-2210">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2210">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2211">找到 Dictionary_icd_9_cm 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2211">A keyword from Dictionary_icd_9_cm is found.</span></span>

```
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2212">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2212">Keywords</span></span>

<span data-ttu-id="95cb4-2213">Dictionary_icd_9_cm 关键字词典中的任何术语, 基于[Diseases 的国际分类、第九修订版、临床修改 (icd-9 cm)](https://go.microsoft.com/fwlink/?linkid=852605)。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2213">Any term from the Dictionary_icd_9_cm keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="95cb4-2214">此类型仅查找术语, 而不是保险代码。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2214">This type looks only for the term, not the insurance codes.</span></span>
   
## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="95cb4-2215">爱尔兰个人公共服务 (PPS) 号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-2215">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2216">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2216">Format</span></span>

<span data-ttu-id="95cb4-2217">旧格式 (到 31 Dec 2012):</span><span class="sxs-lookup"><span data-stu-id="95cb4-2217">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="95cb4-2218">七位数字后跟 1-2  个字母 </span><span class="sxs-lookup"><span data-stu-id="95cb4-2218">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="95cb4-2219">新格式 (2013 年1月1日和之后):</span><span class="sxs-lookup"><span data-stu-id="95cb4-2219">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="95cb4-2220">七位数字后跟两个字母</span><span class="sxs-lookup"><span data-stu-id="95cb4-2220">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2221">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2221">Pattern</span></span>

<span data-ttu-id="95cb4-2222">旧格式 (到 31 Dec 2012):</span><span class="sxs-lookup"><span data-stu-id="95cb4-2222">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="95cb4-2223">七个数字 </span><span class="sxs-lookup"><span data-stu-id="95cb4-2223">Seven digits</span></span> 
- <span data-ttu-id="95cb4-2224">1-2 个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="95cb4-2224">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="95cb4-2225">新格式 (2013 年1月1日和之后):</span><span class="sxs-lookup"><span data-stu-id="95cb4-2225">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="95cb4-2226">七个数字 </span><span class="sxs-lookup"><span data-stu-id="95cb4-2226">Seven digits</span></span> 
- <span data-ttu-id="95cb4-2227">一个字母（不区分大小写），是字母校验位 </span><span class="sxs-lookup"><span data-stu-id="95cb4-2227">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="95cb4-2228">字母“A”或“H”（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="95cb4-2228">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2229">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2229">Checksum</span></span>

<span data-ttu-id="95cb4-2230">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-2230">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2231">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2231">Definition</span></span>

<span data-ttu-id="95cb4-2232">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2232">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2233">函数 Func_ireland_pps 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2233">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2234">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2234">One of the following is true:</span></span>
    - <span data-ttu-id="95cb4-2235">找到 Keyword_ireland_pps 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2235">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="95cb4-2236">函数 Func_eu_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2236">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="95cb4-2237">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2237">The checksum passes.</span></span>

<span data-ttu-id="95cb4-2238">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2238">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2239">函数 Func_ireland_pps 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2239">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2240">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2240">The checksum passes.</span></span>

```
<!-- Ireland Personal Public Service (PPS) Number -->
<Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_ireland_pps"/>
     <Any minMatches="1">
  <Match idRef="Keyword_ireland_pps"/>
  <Match idRef="Func_eu_date"/>
     </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_ireland_pps"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2241">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2241">Keywords</span></span>

#### <a name="keywordirelandpps"></a><span data-ttu-id="95cb4-2242">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="95cb4-2242">Keyword_ireland_pps</span></span>

- <span data-ttu-id="95cb4-2243">Personal Public Service Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2243">Personal Public Service Number</span></span> 
- <span data-ttu-id="95cb4-2244">PPS Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2244">PPS Number</span></span> 
- <span data-ttu-id="95cb4-2245">PPS Num</span><span class="sxs-lookup"><span data-stu-id="95cb4-2245">PPS Num</span></span> 
- <span data-ttu-id="95cb4-2246">PPS No.</span><span class="sxs-lookup"><span data-stu-id="95cb4-2246">PPS No.</span></span> 
- <span data-ttu-id="95cb4-2247">PPS #</span><span class="sxs-lookup"><span data-stu-id="95cb4-2247">PPS #</span></span> 
- <span data-ttu-id="95cb4-2248">.pps</span><span class="sxs-lookup"><span data-stu-id="95cb4-2248">PPS#</span></span> 
- <span data-ttu-id="95cb4-2249">PPSN</span><span class="sxs-lookup"><span data-stu-id="95cb4-2249">PPSN</span></span> 
- <span data-ttu-id="95cb4-2250">Public Services Card</span><span class="sxs-lookup"><span data-stu-id="95cb4-2250">Public Services Card</span></span> 
- <span data-ttu-id="95cb4-2251">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="95cb4-2251">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="95cb4-2252">Uimh。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2252">Uimh.</span></span> <span data-ttu-id="95cb4-2253">PSP</span><span class="sxs-lookup"><span data-stu-id="95cb4-2253">PSP</span></span> 
- <span data-ttu-id="95cb4-2254">PSP</span><span class="sxs-lookup"><span data-stu-id="95cb4-2254">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="95cb4-2255">以色列银行帐号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2255">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2256">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2256">Format</span></span>

<span data-ttu-id="95cb4-2257">13 位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2257">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2258">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2258">Pattern</span></span>

<span data-ttu-id="95cb4-2259">格式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2259">Formatted:</span></span>
- <span data-ttu-id="95cb4-2260">两位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2260">Two digits</span></span> 
- <span data-ttu-id="95cb4-2261">破折号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2261">A dash</span></span> 
- <span data-ttu-id="95cb4-2262">三位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2262">Three digits</span></span> 
- <span data-ttu-id="95cb4-2263">破折号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2263">A dash</span></span> 
- <span data-ttu-id="95cb4-2264">八位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2264">Eight digits</span></span>

<span data-ttu-id="95cb4-2265">纯</span><span class="sxs-lookup"><span data-stu-id="95cb4-2265">Unformatted:</span></span>
- <span data-ttu-id="95cb4-2266">	13 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2266">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2267">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2267">Checksum</span></span>

<span data-ttu-id="95cb4-2268">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-2268">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2269">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2269">Definition</span></span>

<span data-ttu-id="95cb4-2270">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2270">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2271">正则表达式 Regex_israel_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2271">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2272">找到 Keyword_israel_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2272">A keyword from Keyword_israel_bank_account_number is found.</span></span>

```
<!-- Israel Bank Account Number -->
<Entity id="7d08b2ff-a0b9-437f-957c-aeddbf9b2b25" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_israel_bank_account_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_israel_bank_account_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2273">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2273">Keywords</span></span>

#### <a name="keywordisraelbankaccountnumber"></a><span data-ttu-id="95cb4-2274">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2274">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="95cb4-2275">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2275">Bank Account Number</span></span> 
- <span data-ttu-id="95cb4-2276">Bank Account</span><span class="sxs-lookup"><span data-stu-id="95cb4-2276">Bank Account</span></span> 
- <span data-ttu-id="95cb4-2277">Account Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2277">Account Number</span></span> 
- <span data-ttu-id="95cb4-2278">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="95cb4-2278">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="95cb4-2279">以色列国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="95cb4-2279">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2280">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2280">Format</span></span>

<span data-ttu-id="95cb4-2281">九个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2281">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2282">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2282">Pattern</span></span>

<span data-ttu-id="95cb4-2283">九个连续的数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2283">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2284">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2284">Checksum</span></span>

<span data-ttu-id="95cb4-2285">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-2285">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2286">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2286">Definition</span></span>

<span data-ttu-id="95cb4-2287">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2287">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2288">函数 Func_israeli_national_id_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2288">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2289">找到 Keyword_Israel_National_ID 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2289">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="95cb4-2290">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2290">The checksum passes.</span></span>

```
<!-- Israel National ID Number -->
<Entity id="e05881f5-1db1-418c-89aa-a3ac5c5277ee" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_israeli_national_id_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_Israel_National_ID" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2291">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2291">Keywords</span></span>

#### <a name="keywordisraelnationalid"></a><span data-ttu-id="95cb4-2292">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="95cb4-2292">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="95cb4-2293">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="95cb4-2293">מספר זהות</span></span> 
- <span data-ttu-id="95cb4-2294">National ID Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2294">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="95cb4-2295">意大利驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-2295">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2296">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2296">Format</span></span>

<span data-ttu-id="95cb4-2297">10 个字母和数字的组合</span><span class="sxs-lookup"><span data-stu-id="95cb4-2297">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2298">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2298">Pattern</span></span>

- <span data-ttu-id="95cb4-2299">10 个字母和数字的组合：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2299">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="95cb4-2300">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="95cb4-2300">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="95cb4-2301">字母“A”或者“V”（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="95cb4-2301">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="95cb4-2302">七个字母（不区分大小写）、数字或下划线字符</span><span class="sxs-lookup"><span data-stu-id="95cb4-2302">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="95cb4-2303">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="95cb4-2303">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2304">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2304">Checksum</span></span>

<span data-ttu-id="95cb4-2305">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-2305">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2306">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2306">Definition</span></span>

<span data-ttu-id="95cb4-2307">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2307">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2308">正则表达式 Regex_italy_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2308">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2309">找到 Keyword_italy_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2309">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

```
<!-- Italy Driver's license Number -->
<Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_italy_drivers_license_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2310">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2310">Keywords</span></span>

#### <a name="keyworditalydriverslicensenumber"></a><span data-ttu-id="95cb4-2311">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2311">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="95cb4-2312">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="95cb4-2312">numero di patente di guida</span></span> 
- <span data-ttu-id="95cb4-2313">patente di guida</span><span class="sxs-lookup"><span data-stu-id="95cb4-2313">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="95cb4-2314">日本银行帐号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2314">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2315">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2315">Format</span></span>

<span data-ttu-id="95cb4-2316">七个或八个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2316">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2317">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2317">Pattern</span></span>

<span data-ttu-id="95cb4-2318">银行帐号：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2318">Bank account number:</span></span>
- <span data-ttu-id="95cb4-2319">七个或八个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2319">Seven or eight digits</span></span>
- <span data-ttu-id="95cb4-2320">银行帐户分支代码：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2320">Bank account branch code:</span></span>
- <span data-ttu-id="95cb4-2321">四位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2321">Four digits</span></span> 
- <span data-ttu-id="95cb4-2322">空格或破折号（可选）</span><span class="sxs-lookup"><span data-stu-id="95cb4-2322">A space or dash (optional)</span></span> 
- <span data-ttu-id="95cb4-2323">三位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2323">Three digits</span></span>

<span data-ttu-id="95cb4-2324">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2324">Checksum</span></span>

<span data-ttu-id="95cb4-2325">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-2325">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2326">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2326">Definition</span></span>

<span data-ttu-id="95cb4-2327">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2327">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2328">函数 Func_jp_bank_account 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2328">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2329">找到 Keyword_jp_bank_account 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2329">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="95cb4-2330">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2330">One of the following is true:</span></span>
- <span data-ttu-id="95cb4-2331">函数 Func_jp_bank_account_branch_code 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2331">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2332">找到 Keyword_jp_bank_branch_code 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2332">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="95cb4-2333">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2333">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2334">函数 Func_jp_bank_account 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2334">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2335">找到 Keyword_jp_bank_account 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2335">A keyword from Keyword_jp_bank_account is found.</span></span>

```
<!-- Japan Bank Account Number -->
<Entity id="d354f95b-96ee-4b80-80bc-4377312b55bc" patternsProximity="300" recommendedConfidence="75">
  <Version minEngineVersion="15.01.0131.000">
    <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_jp_bank_account" />
          <Match idRef="Keyword_jp_bank_account" />
          <Any minMatches="1">
            <Match idRef="Func_jp_bank_account_branch_code" />
            <Match idRef="Keyword_jp_bank_branch_code" />
          </Any>
      </Pattern>
  </Version>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_bank_account" />
        <Match idRef="Keyword_jp_bank_account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2336">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2336">Keywords</span></span>

#### <a name="keywordjpbankaccount"></a><span data-ttu-id="95cb4-2337">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="95cb4-2337">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="95cb4-2338">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2338">Checking Account Number</span></span> 
- <span data-ttu-id="95cb4-2339">Checking Account</span><span class="sxs-lookup"><span data-stu-id="95cb4-2339">Checking Account</span></span> 
- <span data-ttu-id="95cb4-2340">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="95cb4-2340">Checking Account #</span></span> 
- <span data-ttu-id="95cb4-2341">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2341">Checking Acct Number</span></span> 
- <span data-ttu-id="95cb4-2342">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="95cb4-2342">Checking Acct #</span></span> 
- <span data-ttu-id="95cb4-2343">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="95cb4-2343">Checking Acct No.</span></span> 
- <span data-ttu-id="95cb4-2344">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="95cb4-2344">Checking Account No.</span></span> 
- <span data-ttu-id="95cb4-2345">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2345">Bank Account Number</span></span> 
- <span data-ttu-id="95cb4-2346">Bank Account</span><span class="sxs-lookup"><span data-stu-id="95cb4-2346">Bank Account</span></span> 
- <span data-ttu-id="95cb4-2347">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="95cb4-2347">Bank Account #</span></span> 
- <span data-ttu-id="95cb4-2348">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2348">Bank Acct Number</span></span> 
- <span data-ttu-id="95cb4-2349">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="95cb4-2349">Bank Acct #</span></span> 
- <span data-ttu-id="95cb4-2350">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="95cb4-2350">Bank Acct No.</span></span> 
- <span data-ttu-id="95cb4-2351">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="95cb4-2351">Bank Account No.</span></span> 
- <span data-ttu-id="95cb4-2352">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2352">Savings Account Number</span></span> 
- <span data-ttu-id="95cb4-2353">Savings Account</span><span class="sxs-lookup"><span data-stu-id="95cb4-2353">Savings Account</span></span> 
- <span data-ttu-id="95cb4-2354">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="95cb4-2354">Savings Account #</span></span> 
- <span data-ttu-id="95cb4-2355">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2355">Savings Acct Number</span></span> 
- <span data-ttu-id="95cb4-2356">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="95cb4-2356">Savings Acct #</span></span> 
- <span data-ttu-id="95cb4-2357">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="95cb4-2357">Savings Acct No.</span></span> 
- <span data-ttu-id="95cb4-2358">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="95cb4-2358">Savings Account No.</span></span> 
- <span data-ttu-id="95cb4-2359">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2359">Debit Account Number</span></span> 
- <span data-ttu-id="95cb4-2360">Debit Account</span><span class="sxs-lookup"><span data-stu-id="95cb4-2360">Debit Account</span></span> 
- <span data-ttu-id="95cb4-2361">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="95cb4-2361">Debit Account #</span></span> 
- <span data-ttu-id="95cb4-2362">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2362">Debit Acct Number</span></span> 
- <span data-ttu-id="95cb4-2363">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="95cb4-2363">Debit Acct #</span></span> 
- <span data-ttu-id="95cb4-2364">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="95cb4-2364">Debit Acct No.</span></span> 
- <span data-ttu-id="95cb4-2365">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="95cb4-2365">Debit Account No.</span></span> 
- <span data-ttu-id="95cb4-2366">口座番号を当座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="95cb4-2366">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="95cb4-2367">#アカウントの確認、勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="95cb4-2367">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="95cb4-2368">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="95cb4-2368">＃勘定の確認</span></span> 
- <span data-ttu-id="95cb4-2369">勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="95cb4-2369">勘定番号の確認</span></span> 
- <span data-ttu-id="95cb4-2370">口座番号の確認</span><span class="sxs-lookup"><span data-stu-id="95cb4-2370">口座番号の確認</span></span> 
- <span data-ttu-id="95cb4-2371">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2371">銀行口座番号</span></span> 
- <span data-ttu-id="95cb4-2372">銀行口座</span><span class="sxs-lookup"><span data-stu-id="95cb4-2372">銀行口座</span></span> 
- <span data-ttu-id="95cb4-2373">銀行口座 #</span><span class="sxs-lookup"><span data-stu-id="95cb4-2373">銀行口座＃</span></span> 
- <span data-ttu-id="95cb4-2374">銀行の勘定番号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2374">銀行の勘定番号</span></span> 
- <span data-ttu-id="95cb4-2375">銀行のacct #</span><span class="sxs-lookup"><span data-stu-id="95cb4-2375">銀行のacct＃</span></span> 
- <span data-ttu-id="95cb4-2376">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="95cb4-2376">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="95cb4-2377">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2377">銀行口座番号</span></span>
- <span data-ttu-id="95cb4-2378">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2378">普通預金口座番号</span></span> 
- <span data-ttu-id="95cb4-2379">預金口座</span><span class="sxs-lookup"><span data-stu-id="95cb4-2379">預金口座</span></span> 
- <span data-ttu-id="95cb4-2380">貯蓄口座 #</span><span class="sxs-lookup"><span data-stu-id="95cb4-2380">貯蓄口座＃</span></span> 
- <span data-ttu-id="95cb4-2381">貯蓄勘定の数</span><span class="sxs-lookup"><span data-stu-id="95cb4-2381">貯蓄勘定の数</span></span> 
- <span data-ttu-id="95cb4-2382">貯蓄勘定 #</span><span class="sxs-lookup"><span data-stu-id="95cb4-2382">貯蓄勘定＃</span></span> 
- <span data-ttu-id="95cb4-2383">貯蓄勘定番号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2383">貯蓄勘定番号</span></span> 
- <span data-ttu-id="95cb4-2384">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2384">普通預金口座番号</span></span> 
- <span data-ttu-id="95cb4-2385">引き落とし口座番号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2385">引き落とし口座番号</span></span> 
- <span data-ttu-id="95cb4-2386">口座番号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2386">口座番号</span></span> 
- <span data-ttu-id="95cb4-2387">口座番号 #</span><span class="sxs-lookup"><span data-stu-id="95cb4-2387">口座番号＃</span></span> 
- <span data-ttu-id="95cb4-2388">デビットのacct番号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2388">デビットのacct番号</span></span> 
- <span data-ttu-id="95cb4-2389">デビット勘定 #</span><span class="sxs-lookup"><span data-stu-id="95cb4-2389">デビット勘定＃</span></span> 
- <span data-ttu-id="95cb4-2390">デビットACCTの番号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2390">デビットACCTの番号</span></span> 
- <span data-ttu-id="95cb4-2391">デビット口座番号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2391">デビット口座番号</span></span> 

#### <a name="keywordjpbankbranchcode"></a><span data-ttu-id="95cb4-2392">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="95cb4-2392">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="95cb4-2393">Otemachi</span><span class="sxs-lookup"><span data-stu-id="95cb4-2393">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="95cb4-2394">日本驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-2394">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2395">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2395">Format</span></span>

<span data-ttu-id="95cb4-2396">12 个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2396">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2397">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2397">Pattern</span></span>

<span data-ttu-id="95cb4-2398">12 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2398">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2399">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2399">Checksum</span></span>

<span data-ttu-id="95cb4-2400">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-2400">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2401">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2401">Definition</span></span>

<span data-ttu-id="95cb4-2402">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2402">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2403">函数 Func_jp_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2403">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2404">找到 Keyword_jp_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2404">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2405">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2405">Keywords</span></span>

#### <a name="keywordjpdriverslicensenumber"></a><span data-ttu-id="95cb4-2406">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2406">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="95cb4-2407">通讯</span><span class="sxs-lookup"><span data-stu-id="95cb4-2407">dl#</span></span> 
- <span data-ttu-id="95cb4-2408">通讯</span><span class="sxs-lookup"><span data-stu-id="95cb4-2408">DL＃</span></span> 
- <span data-ttu-id="95cb4-2409">dls</span><span class="sxs-lookup"><span data-stu-id="95cb4-2409">dls#</span></span> 
- <span data-ttu-id="95cb4-2410">DLS</span><span class="sxs-lookup"><span data-stu-id="95cb4-2410">DLS＃</span></span> 
- <span data-ttu-id="95cb4-2411">driver license</span><span class="sxs-lookup"><span data-stu-id="95cb4-2411">driver license</span></span> 
- <span data-ttu-id="95cb4-2412">driver licenses</span><span class="sxs-lookup"><span data-stu-id="95cb4-2412">driver licenses</span></span> 
- <span data-ttu-id="95cb4-2413">drivers license</span><span class="sxs-lookup"><span data-stu-id="95cb4-2413">drivers license</span></span> 
- <span data-ttu-id="95cb4-2414">driver's license</span><span class="sxs-lookup"><span data-stu-id="95cb4-2414">driver's license</span></span> 
- <span data-ttu-id="95cb4-2415">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="95cb4-2415">drivers licenses</span></span> 
- <span data-ttu-id="95cb4-2416">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="95cb4-2416">driver's licenses</span></span> 
- <span data-ttu-id="95cb4-2417">driving licence</span><span class="sxs-lookup"><span data-stu-id="95cb4-2417">driving licence</span></span> 
- <span data-ttu-id="95cb4-2418">.lic</span><span class="sxs-lookup"><span data-stu-id="95cb4-2418">lic#</span></span> 
- <span data-ttu-id="95cb4-2419">.lic</span><span class="sxs-lookup"><span data-stu-id="95cb4-2419">LIC＃</span></span> 
- <span data-ttu-id="95cb4-2420">driver'lics</span><span class="sxs-lookup"><span data-stu-id="95cb4-2420">lics#</span></span> 
- <span data-ttu-id="95cb4-2421">state id</span><span class="sxs-lookup"><span data-stu-id="95cb4-2421">state id</span></span> 
- <span data-ttu-id="95cb4-2422">state identification</span><span class="sxs-lookup"><span data-stu-id="95cb4-2422">state identification</span></span> 
- <span data-ttu-id="95cb4-2423">state identification number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2423">state identification number</span></span> 
- <span data-ttu-id="95cb4-2424">低所得国 #</span><span class="sxs-lookup"><span data-stu-id="95cb4-2424">低所得国＃</span></span> 
- <span data-ttu-id="95cb4-2425">免許証</span><span class="sxs-lookup"><span data-stu-id="95cb4-2425">免許証</span></span> 
- <span data-ttu-id="95cb4-2426">状態ID</span><span class="sxs-lookup"><span data-stu-id="95cb4-2426">状態ID</span></span>
- <span data-ttu-id="95cb4-2427">状態の識別</span><span class="sxs-lookup"><span data-stu-id="95cb4-2427">状態の識別</span></span> 
- <span data-ttu-id="95cb4-2428">状態の識別番号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2428">状態の識別番号</span></span> 
- <span data-ttu-id="95cb4-2429">運転免許</span><span class="sxs-lookup"><span data-stu-id="95cb4-2429">運転免許</span></span> 
- <span data-ttu-id="95cb4-2430">運転免許証</span><span class="sxs-lookup"><span data-stu-id="95cb4-2430">運転免許証</span></span> 
- <span data-ttu-id="95cb4-2431">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2431">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="95cb4-2432">日本护照号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-2432">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2433">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2433">Format</span></span>

<span data-ttu-id="95cb4-2434">两个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2434">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2435">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2435">Pattern</span></span>

<span data-ttu-id="95cb4-2436">两个字母（不区分大小写）后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2436">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2437">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2437">Checksum</span></span>

<span data-ttu-id="95cb4-2438">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-2438">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2439">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2439">Definition</span></span>

<span data-ttu-id="95cb4-2440">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2441">函数 Func_jp_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2441">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2442">找到 Keyword_jp_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2442">A keyword from Keyword_jp_passport is found.</span></span>

```
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2443">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2443">Keywords</span></span>

#### <a name="keywordjppassport"></a><span data-ttu-id="95cb4-2444">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="95cb4-2444">Keyword_jp_passport</span></span>

- <span data-ttu-id="95cb4-2445">パスポート</span><span class="sxs-lookup"><span data-stu-id="95cb4-2445">パスポート</span></span> 
- <span data-ttu-id="95cb4-2446">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2446">パスポート番号</span></span> 
- <span data-ttu-id="95cb4-2447">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="95cb4-2447">パスポートのNum</span></span> 
- <span data-ttu-id="95cb4-2448">パスポート #</span><span class="sxs-lookup"><span data-stu-id="95cb4-2448">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="95cb4-2449">日本居民登记号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-2449">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2450">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2450">Format</span></span>

<span data-ttu-id="95cb4-2451">11 个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2451">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2452">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2452">Pattern</span></span>

<span data-ttu-id="95cb4-2453">11 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2453">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2454">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2454">Checksum</span></span>

<span data-ttu-id="95cb4-2455">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-2455">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2456">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2456">Definition</span></span>

<span data-ttu-id="95cb4-2457">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2458">函数 Func_jp_resident_registration_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2458">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2459">找到 Keyword_jp_resident_registration_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2459">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2460">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2460">Keywords</span></span>

#### <a name="keywordjpresidentregistrationnumber"></a><span data-ttu-id="95cb4-2461">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2461">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="95cb4-2462">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2462">Resident Registration Number</span></span>
- <span data-ttu-id="95cb4-2463">Resident Register Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2463">Resident Register Number</span></span> 
- <span data-ttu-id="95cb4-2464">Residents Basic Registry Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2464">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="95cb4-2465">Resident Registration No.</span><span class="sxs-lookup"><span data-stu-id="95cb4-2465">Resident Registration No.</span></span> 
- <span data-ttu-id="95cb4-2466">Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="95cb4-2466">Resident Register No.</span></span> 
- <span data-ttu-id="95cb4-2467">Residents Basic Registry No.</span><span class="sxs-lookup"><span data-stu-id="95cb4-2467">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="95cb4-2468">Basic Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="95cb4-2468">Basic Resident Register No.</span></span> 
- <span data-ttu-id="95cb4-2469">住民登録番号、登録番号をレジデント</span><span class="sxs-lookup"><span data-stu-id="95cb4-2469">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="95cb4-2470">住民基本登録番号、登録番号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2470">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="95cb4-2471">住民基本レジストリ番号を常駐</span><span class="sxs-lookup"><span data-stu-id="95cb4-2471">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="95cb4-2472">登録番号を常駐住民基本台帳登録番号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2472">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="95cb4-2473">日本社会保险号码 (SIN)</span><span class="sxs-lookup"><span data-stu-id="95cb4-2473">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2474">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2474">Format</span></span>

<span data-ttu-id="95cb4-2475">7-12 个数字 </span><span class="sxs-lookup"><span data-stu-id="95cb4-2475">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2476">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2476">Pattern</span></span>

<span data-ttu-id="95cb4-2477">7-12 位数字：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2477">7-12 digits:</span></span>
- <span data-ttu-id="95cb4-2478">四位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2478">Four digits</span></span> 
- <span data-ttu-id="95cb4-2479">一个连字符（可选）</span><span class="sxs-lookup"><span data-stu-id="95cb4-2479">A hyphen (optional)</span></span> 
- <span data-ttu-id="95cb4-2480">六位数字或</span><span class="sxs-lookup"><span data-stu-id="95cb4-2480">Six digits OR</span></span>
- <span data-ttu-id="95cb4-2481">7-12 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2481">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2482">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2482">Checksum</span></span>

<span data-ttu-id="95cb4-2483">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-2483">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2484">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2484">Definition</span></span>

<span data-ttu-id="95cb4-2485">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2485">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2486">函数 Func_jp_sin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2486">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2487">找到 Keyword_jp_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2487">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="95cb4-2488">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2488">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2489">函数 Func_jp_sin_pre_1997 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2489">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2490">找到 Keyword_jp_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2490">A keyword from Keyword_jp_sin is found.</span></span>

```
<!-- Japan Social Insurance Number -->
<Entity id="c840e719-0896-45bb-84fd-1ed5c95e45ff" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_jp_sin" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_sin_pre_1997" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2491">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2491">Keywords</span></span>

#### <a name="keywordjpsin"></a><span data-ttu-id="95cb4-2492">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="95cb4-2492">Keyword_jp_sin</span></span>

- <span data-ttu-id="95cb4-2493">Social Insurance No.</span><span class="sxs-lookup"><span data-stu-id="95cb4-2493">Social Insurance No.</span></span> 
- <span data-ttu-id="95cb4-2494">Social Insurance Num</span><span class="sxs-lookup"><span data-stu-id="95cb4-2494">Social Insurance Num</span></span> 
- <span data-ttu-id="95cb4-2495">Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2495">Social Insurance Number</span></span> 
- <span data-ttu-id="95cb4-2496">社会保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="95cb4-2496">社会保険のテンキー</span></span> 
- <span data-ttu-id="95cb4-2497">社会保険番号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2497">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="95cb4-2498">日本住宅电话卡号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2498">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2499">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2499">Format</span></span>

<span data-ttu-id="95cb4-2500">12个字母和数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2500">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2501">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2501">Pattern</span></span>

<span data-ttu-id="95cb4-2502">12个字母和数字:</span><span class="sxs-lookup"><span data-stu-id="95cb4-2502">12 letters and digits:</span></span>
- <span data-ttu-id="95cb4-2503">两个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="95cb4-2503">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="95cb4-2504">八个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2504">Eight digits</span></span> 
- <span data-ttu-id="95cb4-2505">两个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="95cb4-2505">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2506">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2506">Checksum</span></span>

<span data-ttu-id="95cb4-2507">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-2507">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2508">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2508">Definition</span></span>

<span data-ttu-id="95cb4-2509">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2509">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2510">正则表达式 Regex_jp_residence_card_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2510">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2511">找到 Keyword_jp_residence_card_number 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2511">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2512">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2512">Keywords</span></span>

#### <a name="keywordjpresidencecardnumber"></a><span data-ttu-id="95cb4-2513">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2513">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="95cb4-2514">住宅电话卡号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2514">Residence card number</span></span>
- <span data-ttu-id="95cb4-2515">住宅卡编号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2515">Residence card no</span></span>
- <span data-ttu-id="95cb4-2516">住宅卡片 #</span><span class="sxs-lookup"><span data-stu-id="95cb4-2516">Residence card #</span></span>
- <span data-ttu-id="95cb4-2517">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2517">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="95cb4-2518">马拉西亚身份证号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-2518">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2519">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2519">Format</span></span>

<span data-ttu-id="95cb4-2520">12 个数字（包含可选连字符）</span><span class="sxs-lookup"><span data-stu-id="95cb4-2520">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2521">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2521">Pattern</span></span>

<span data-ttu-id="95cb4-2522">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2522">12 digits:</span></span>
- <span data-ttu-id="95cb4-2523">六个数字，采用  YYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="95cb4-2523">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="95cb4-2524">一个短划线（可选） </span><span class="sxs-lookup"><span data-stu-id="95cb4-2524">A dash (optional)</span></span> 
- <span data-ttu-id="95cb4-2525">两个字母的出生地代码 </span><span class="sxs-lookup"><span data-stu-id="95cb4-2525">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="95cb4-2526">一个短划线（可选） </span><span class="sxs-lookup"><span data-stu-id="95cb4-2526">A dash (optional)</span></span> 
- <span data-ttu-id="95cb4-2527">三个随机数字 </span><span class="sxs-lookup"><span data-stu-id="95cb4-2527">Three random digits</span></span> 
- <span data-ttu-id="95cb4-2528">一位性别代码</span><span class="sxs-lookup"><span data-stu-id="95cb4-2528">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2529">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2529">Checksum</span></span>

<span data-ttu-id="95cb4-2530">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-2530">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2531">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2531">Definition</span></span>

<span data-ttu-id="95cb4-2532">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2532">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2533">正则表达式 Regex_malaysia_id_card_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2533">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2534">找到 Keyword_malaysia_id_card_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2534">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

```
<!-- Malaysia ID Card Number -->
</Entity>
      <Entity id="7f0e921c-9677-435b-aba2-bb8f1013c749" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_malaysia_id_card_number" />
            <Match idRef="Keyword_malaysia_id_card_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2535">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2535">Keywords</span></span>
   
#### <a name="keywordmalaysiaidcardnumber"></a><span data-ttu-id="95cb4-2536">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2536">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="95cb4-2537">数字应用程序卡</span><span class="sxs-lookup"><span data-stu-id="95cb4-2537">digital application card</span></span>
- <span data-ttu-id="95cb4-2538">i/c</span><span class="sxs-lookup"><span data-stu-id="95cb4-2538">i/c</span></span>
- <span data-ttu-id="95cb4-2539">i/c 否</span><span class="sxs-lookup"><span data-stu-id="95cb4-2539">i/c no</span></span>
- <span data-ttu-id="95cb4-2540">ic</span><span class="sxs-lookup"><span data-stu-id="95cb4-2540">ic</span></span>
- <span data-ttu-id="95cb4-2541">内部公司编号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2541">ic no</span></span>
- <span data-ttu-id="95cb4-2542">id card</span><span class="sxs-lookup"><span data-stu-id="95cb4-2542">id card</span></span>
- <span data-ttu-id="95cb4-2543">标识卡</span><span class="sxs-lookup"><span data-stu-id="95cb4-2543">identification Card</span></span>
- <span data-ttu-id="95cb4-2544">identity card</span><span class="sxs-lookup"><span data-stu-id="95cb4-2544">identity card</span></span>
- <span data-ttu-id="95cb4-2545">k/p</span><span class="sxs-lookup"><span data-stu-id="95cb4-2545">k/p</span></span>
- <span data-ttu-id="95cb4-2546">k/p no</span><span class="sxs-lookup"><span data-stu-id="95cb4-2546">k/p no</span></span>
- <span data-ttu-id="95cb4-2547">kad akuan diri</span><span class="sxs-lookup"><span data-stu-id="95cb4-2547">kad akuan diri</span></span>
- <span data-ttu-id="95cb4-2548">kad aplikasi 数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2548">kad aplikasi digital</span></span>
- <span data-ttu-id="95cb4-2549">kad pengenalan 马来西亚</span><span class="sxs-lookup"><span data-stu-id="95cb4-2549">kad pengenalan malaysia</span></span>
- <span data-ttu-id="95cb4-2550">kp</span><span class="sxs-lookup"><span data-stu-id="95cb4-2550">kp</span></span>
- <span data-ttu-id="95cb4-2551">kp no</span><span class="sxs-lookup"><span data-stu-id="95cb4-2551">kp no</span></span>
- <span data-ttu-id="95cb4-2552">mykad</span><span class="sxs-lookup"><span data-stu-id="95cb4-2552">mykad</span></span>
- <span data-ttu-id="95cb4-2553">mykas</span><span class="sxs-lookup"><span data-stu-id="95cb4-2553">mykas</span></span>
- <span data-ttu-id="95cb4-2554">mykid</span><span class="sxs-lookup"><span data-stu-id="95cb4-2554">mykid</span></span>
- <span data-ttu-id="95cb4-2555">mypr</span><span class="sxs-lookup"><span data-stu-id="95cb4-2555">mypr</span></span>
- <span data-ttu-id="95cb4-2556">mytentera</span><span class="sxs-lookup"><span data-stu-id="95cb4-2556">mytentera</span></span>
- <span data-ttu-id="95cb4-2557">马来西亚身份卡片</span><span class="sxs-lookup"><span data-stu-id="95cb4-2557">malaysia identity card</span></span>
- <span data-ttu-id="95cb4-2558">马来西亚身份卡片</span><span class="sxs-lookup"><span data-stu-id="95cb4-2558">malaysian identity card</span></span>
- <span data-ttu-id="95cb4-2559">nric</span><span class="sxs-lookup"><span data-stu-id="95cb4-2559">nric</span></span>
- <span data-ttu-id="95cb4-2560">个人标识卡</span><span class="sxs-lookup"><span data-stu-id="95cb4-2560">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="95cb4-2561">荷兰公民服务 (BSN) 号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-2561">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2562">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2562">Format</span></span>

<span data-ttu-id="95cb4-2563">8-9 个数字（包含可选空格）</span><span class="sxs-lookup"><span data-stu-id="95cb4-2563">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2564">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2564">Pattern</span></span>

<span data-ttu-id="95cb4-2565">8-9 个数字：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2565">8-9 digits:</span></span>
- <span data-ttu-id="95cb4-2566">三个数字 </span><span class="sxs-lookup"><span data-stu-id="95cb4-2566">Three digits</span></span> 
- <span data-ttu-id="95cb4-2567">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="95cb4-2567">A space (optional)</span></span> 
- <span data-ttu-id="95cb4-2568">三个数字 </span><span class="sxs-lookup"><span data-stu-id="95cb4-2568">Three digits</span></span> 
- <span data-ttu-id="95cb4-2569">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="95cb4-2569">A space (optional)</span></span> 
- <span data-ttu-id="95cb4-2570">2-3 个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2570">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2571">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2571">Checksum</span></span>

<span data-ttu-id="95cb4-2572">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-2572">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2573">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2573">Definition</span></span>

<span data-ttu-id="95cb4-2574">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2574">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2575">函数 Func_netherlands_bsn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2575">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2576">找到 Keyword_netherlands_bsn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2576">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="95cb4-2577">函数 Func_eu_date2 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2577">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="95cb4-2578">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2578">The checksum passes.</span></span>

```
<!-- Netherlands Citizen's Service (BSN) Number -->
<Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="Func_netherlands_bsn" /> 
       <Match idRef="Keyword_netherlands_bsn" /> 
       <Match idRef="Func_eu_date2" /> 
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2579">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2579">Keywords</span></span>

#### <a name="keywordnetherlandsbsn"></a><span data-ttu-id="95cb4-2580">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="95cb4-2580">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="95cb4-2581">Citizen service number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2581">Citizen service number</span></span> 
- <span data-ttu-id="95cb4-2582">BSN</span><span class="sxs-lookup"><span data-stu-id="95cb4-2582">BSN</span></span> 
- <span data-ttu-id="95cb4-2583">Burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="95cb4-2583">Burgerservicenummer</span></span> 
- <span data-ttu-id="95cb4-2584">Sofinummer</span><span class="sxs-lookup"><span data-stu-id="95cb4-2584">Sofinummer</span></span> 
- <span data-ttu-id="95cb4-2585">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="95cb4-2585">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="95cb4-2586">Persoonsnummer</span><span class="sxs-lookup"><span data-stu-id="95cb4-2586">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="95cb4-2587">新西兰卫生部号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-2587">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2588">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2588">Format</span></span>

<span data-ttu-id="95cb4-2589">三个字母、一个空格（可选）以及四个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2589">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2590">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2590">Pattern</span></span>

<span data-ttu-id="95cb4-2591">三个字母 (不区分大小写) 一个空格 (可选) 四个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2591">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2592">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2592">Checksum</span></span>

<span data-ttu-id="95cb4-2593">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-2593">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2594">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2594">Definition</span></span>

<span data-ttu-id="95cb4-2595">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2595">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2596">函数 Func_new_zealand_ministry_of_health_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2596">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2597">找到 Keyword_nz_terms 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2597">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="95cb4-2598">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2598">The checksum passes.</span></span>

```
<!-- New Zealand Health Number -->
<Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_nz_terms" />
        </Any>
    </Pattern>
</Entity>
```

<span data-ttu-id="95cb4-2599">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2599">Keywords</span></span>

<span data-ttu-id="95cb4-2600">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="95cb4-2600">Keyword_nz_terms</span></span>

- <span data-ttu-id="95cb4-2601">NHI</span><span class="sxs-lookup"><span data-stu-id="95cb4-2601">NHI</span></span> 
- <span data-ttu-id="95cb4-2602">New Zealand</span><span class="sxs-lookup"><span data-stu-id="95cb4-2602">New Zealand</span></span> 
- <span data-ttu-id="95cb4-2603">运行状况</span><span class="sxs-lookup"><span data-stu-id="95cb4-2603">Health</span></span> 
- <span data-ttu-id="95cb4-2604">治疗</span><span class="sxs-lookup"><span data-stu-id="95cb4-2604">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="95cb4-2605">挪威身份证号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2605">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2606">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2606">Format</span></span>

<span data-ttu-id="95cb4-2607">11 个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2607">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2608">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2608">Pattern</span></span>

<span data-ttu-id="95cb4-2609">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2609">11 digits:</span></span>
- <span data-ttu-id="95cb4-2610">六个数字，采用  DDMMYY 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="95cb4-2610">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="95cb4-2611">三位个人号码 </span><span class="sxs-lookup"><span data-stu-id="95cb4-2611">Three-digit individual number</span></span> 
- <span data-ttu-id="95cb4-2612">两个校验位</span><span class="sxs-lookup"><span data-stu-id="95cb4-2612">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2613">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2613">Checksum</span></span>

<span data-ttu-id="95cb4-2614">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-2614">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2615">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2615">Definition</span></span>

<span data-ttu-id="95cb4-2616">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2616">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2617">函数 Func_norway_id_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2617">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2618">找到 Keyword_norway_id_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2618">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="95cb4-2619">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2619">The checksum passes.</span></span>
- <span data-ttu-id="95cb4-2620">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2620">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2621">函数 Func_norway_id_numbe 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2621">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2622">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2622">The checksum passes.</span></span>

```
<!-- Norway Identification Number -->
<Entity id="d4c8a798-e9f2-4bd3-9652-500d24080fc3" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_norway_id_number"/>
     <Match idRef="Keyword_norway_id_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_norway_id_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2623">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2623">Keywords</span></span>

#### <a name="keywordnorwayidnumber"></a><span data-ttu-id="95cb4-2624">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2624">Keyword_norway_id_number</span></span>

- <span data-ttu-id="95cb4-2625">Personal identification number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2625">Personal identification number</span></span>
- <span data-ttu-id="95cb4-2626">Norwegian ID Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2626">Norwegian ID Number</span></span>
- <span data-ttu-id="95cb4-2627">ID Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2627">ID Number</span></span>
- <span data-ttu-id="95cb4-2628">id</span><span class="sxs-lookup"><span data-stu-id="95cb4-2628">Identification</span></span>
- <span data-ttu-id="95cb4-2629">Personnummer</span><span class="sxs-lookup"><span data-stu-id="95cb4-2629">Personnummer</span></span>
- <span data-ttu-id="95cb4-2630">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="95cb4-2630">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="95cb4-2631">菲律宾统一多用途身份证号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-2631">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2632">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2632">Format</span></span>

<span data-ttu-id="95cb4-2633">12 个数字，通过连字符分隔 </span><span class="sxs-lookup"><span data-stu-id="95cb4-2633">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2634">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2634">Pattern</span></span>

<span data-ttu-id="95cb4-2635">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2635">12 digits:</span></span>
- <span data-ttu-id="95cb4-2636">四个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2636">Four digits</span></span> 
- <span data-ttu-id="95cb4-2637">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="95cb4-2637">A hyphen</span></span> 
- <span data-ttu-id="95cb4-2638">七个数字 </span><span class="sxs-lookup"><span data-stu-id="95cb4-2638">Seven digits</span></span> 
- <span data-ttu-id="95cb4-2639">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="95cb4-2639">A hyphen</span></span> 
- <span data-ttu-id="95cb4-2640">一个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2640">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2641">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2641">Checksum</span></span>

<span data-ttu-id="95cb4-2642">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-2642">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2643">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2643">Definition</span></span>

<span data-ttu-id="95cb4-2644">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2644">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2645">正则表达式 Regex_philippines_unified_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2645">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2646">找到 Keyword_philippines_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2646">A keyword from Keyword_philippines_id is found.</span></span>

```
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2647">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2647">Keywords</span></span>
   
#### <a name="keywordphilippinesid"></a><span data-ttu-id="95cb4-2648">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="95cb4-2648">Keyword_philippines_id</span></span>

- <span data-ttu-id="95cb4-2649">Unified Multi-Purpose ID</span><span class="sxs-lookup"><span data-stu-id="95cb4-2649">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="95cb4-2650">UMID</span><span class="sxs-lookup"><span data-stu-id="95cb4-2650">UMID</span></span> 
- <span data-ttu-id="95cb4-2651">Identity Card</span><span class="sxs-lookup"><span data-stu-id="95cb4-2651">Identity Card</span></span> 
- <span data-ttu-id="95cb4-2652">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="95cb4-2652">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="95cb4-2653">波兰身份证</span><span class="sxs-lookup"><span data-stu-id="95cb4-2653">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2654">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2654">Format</span></span>

<span data-ttu-id="95cb4-2655">三个字母和六个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2655">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2656">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2656">Pattern</span></span>

<span data-ttu-id="95cb4-2657">三个字母（不区分大小写）后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2657">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2658">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2658">Checksum</span></span>

<span data-ttu-id="95cb4-2659">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-2659">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2660">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2660">Definition</span></span>

<span data-ttu-id="95cb4-2661">DLP 策略 75% 确信在300个字符的邻近度内检测到此类型的敏感信息: 函数 Func_polish_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2661">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="95cb4-2662">找到 Keyword_polish_national_id_passport_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2662">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="95cb4-2663">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2663">The checksum passes.</span></span>

```
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2664">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2664">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="95cb4-2665">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2665">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="95cb4-2666">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="95cb4-2666">Dowód osobisty</span></span>
- <span data-ttu-id="95cb4-2667">器 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="95cb4-2667">Numer dowodu osobistego</span></span>
- <span data-ttu-id="95cb4-2668">Nazwa i 器 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="95cb4-2668">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="95cb4-2669">Nazwa i nr dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="95cb4-2669">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="95cb4-2670">Nazwa i nr dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="95cb4-2670">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="95cb4-2671">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="95cb4-2671">Dowód Tożsamości</span></span>
- <span data-ttu-id="95cb4-2672">dow.</span><span class="sxs-lookup"><span data-stu-id="95cb4-2672">dow.</span></span> <span data-ttu-id="95cb4-2673">os.</span><span class="sxs-lookup"><span data-stu-id="95cb4-2673">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="95cb4-2674">波兰国家/地区 ID (PESEL)</span><span class="sxs-lookup"><span data-stu-id="95cb4-2674">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2675">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2675">Format</span></span>

<span data-ttu-id="95cb4-2676">11 个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2676">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2677">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2677">Pattern</span></span>

<span data-ttu-id="95cb4-2678">11 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2678">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2679">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2679">Checksum</span></span>

<span data-ttu-id="95cb4-2680">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-2680">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2681">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2681">Definition</span></span>

<span data-ttu-id="95cb4-2682">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2682">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2683">函数 Func_pesel_identification_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2683">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2684">找到 Keyword_pesel_identification_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2684">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="95cb4-2685">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2685">The checksum passes.</span></span>

```
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2686">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2686">Keywords</span></span>

#### <a name="keywordpeselidentificationnumber"></a><span data-ttu-id="95cb4-2687">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2687">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="95cb4-2688">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="95cb4-2688">Nr PESEL</span></span>
- <span data-ttu-id="95cb4-2689">PESEL</span><span class="sxs-lookup"><span data-stu-id="95cb4-2689">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="95cb4-2690">波兰护照</span><span class="sxs-lookup"><span data-stu-id="95cb4-2690">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2691">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2691">Format</span></span>

<span data-ttu-id="95cb4-2692">两个字母和七个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2692">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2693">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2693">Pattern</span></span>

<span data-ttu-id="95cb4-2694">两个字母（不区分大小写）后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2694">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2695">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2695">Checksum</span></span>

<span data-ttu-id="95cb4-2696">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-2696">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2697">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2697">Definition</span></span>

<span data-ttu-id="95cb4-2698">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2698">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2699">函数 Func_polish_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2699">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2700">找到 Keyword_polish_national_id_passport_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2700">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="95cb4-2701">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2701">The checksum passes.</span></span>

```
<!-- Poland Passport Number -->
<Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
</Version>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2702">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2702">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="95cb4-2703">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2703">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="95cb4-2704">器 paszportu</span><span class="sxs-lookup"><span data-stu-id="95cb4-2704">Numer paszportu</span></span>
- <span data-ttu-id="95cb4-2705">führerschein-nr.</span><span class="sxs-lookup"><span data-stu-id="95cb4-2705">Nr.</span></span> <span data-ttu-id="95cb4-2706">Paszportu</span><span class="sxs-lookup"><span data-stu-id="95cb4-2706">Paszportu</span></span>
- <span data-ttu-id="95cb4-2707">Paszport</span><span class="sxs-lookup"><span data-stu-id="95cb4-2707">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="95cb4-2708">葡萄牙公民身份证号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2708">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2709">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2709">Format</span></span>

<span data-ttu-id="95cb4-2710">八个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2710">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2711">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2711">Pattern</span></span>

<span data-ttu-id="95cb4-2712">八个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2712">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2713">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2713">Checksum</span></span>

<span data-ttu-id="95cb4-2714">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-2714">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2715">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2715">Definition</span></span>

<span data-ttu-id="95cb4-2716">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2716">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2717">正则表达式 Regex_portugal_citizen_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2717">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2718">找到 Keyword_portugal_citizen_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2718">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2719">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2719">Keywords</span></span>

#### <a name="keywordportugalcitizencard"></a><span data-ttu-id="95cb4-2720">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="95cb4-2720">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="95cb4-2721">Citizen Card</span><span class="sxs-lookup"><span data-stu-id="95cb4-2721">Citizen Card</span></span>
- <span data-ttu-id="95cb4-2722">National ID Card</span><span class="sxs-lookup"><span data-stu-id="95cb4-2722">National ID Card</span></span>
- <span data-ttu-id="95cb4-2723">CC</span><span class="sxs-lookup"><span data-stu-id="95cb4-2723">CC</span></span>
- <span data-ttu-id="95cb4-2724">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="95cb4-2724">Cartão de Cidadão</span></span>
- <span data-ttu-id="95cb4-2725">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="95cb4-2725">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="95cb4-2726">沙特阿拉伯国家 ID</span><span class="sxs-lookup"><span data-stu-id="95cb4-2726">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2727">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2727">Format</span></span>

<span data-ttu-id="95cb4-2728">10 个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2728">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2729">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2729">Pattern</span></span>

<span data-ttu-id="95cb4-2730">10 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2730">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2731">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2731">Checksum</span></span>

<span data-ttu-id="95cb4-2732">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-2732">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2733">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2733">Definition</span></span>

<span data-ttu-id="95cb4-2734">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2734">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2735">正则表达式 Regex_saudi_arabia_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2735">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2736">找到 Keyword_saudi_arabia_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2736">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

```
<!-- Saudi Arabia National ID -->
<Entity id="8c5a0ba8-404a-41a3-8871-746aa21ee6c0" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_saudi_arabia_national_id" />
        <Any minMatches="1">
          <Match idRef="Keyword_saudi_arabia_national_id" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2737">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2737">Keywords</span></span>

#### <a name="keywordsaudiarabianationalid"></a><span data-ttu-id="95cb4-2738">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="95cb4-2738">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="95cb4-2739">Identification Card</span><span class="sxs-lookup"><span data-stu-id="95cb4-2739">Identification Card</span></span> 
- <span data-ttu-id="95cb4-2740">I card number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2740">I card number</span></span> 
- <span data-ttu-id="95cb4-2741">ID number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2741">ID number</span></span> 
- <span data-ttu-id="95cb4-2742">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="95cb4-2742">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="95cb4-2743">新加坡国家登记身份证 (NRIC) 号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2743">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2744">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2744">Format</span></span>

<span data-ttu-id="95cb4-2745">九个字母和数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2745">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2746">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2746">Pattern</span></span>

- <span data-ttu-id="95cb4-2747">九个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2747">Nine letters and digits:</span></span>
- <span data-ttu-id="95cb4-2748">字母“F”、“G”、“S”或“T”（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="95cb4-2748">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="95cb4-2749">七个数字 </span><span class="sxs-lookup"><span data-stu-id="95cb4-2749">Seven digits</span></span> 
- <span data-ttu-id="95cb4-2750">一个字母校验位</span><span class="sxs-lookup"><span data-stu-id="95cb4-2750">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2751">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2751">Checksum</span></span>

<span data-ttu-id="95cb4-2752">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-2752">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2753">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2753">Definition</span></span>

<span data-ttu-id="95cb4-2754">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2754">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2755">正则表达式 Regex_singapore_nric 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2755">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2756">找到 Keyword_singapore_nric 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2756">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="95cb4-2757">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2757">The checksum passes.</span></span>

<span data-ttu-id="95cb4-2758">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2758">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2759">正则表达式 Regex_singapore_nric 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2759">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2760">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2760">The checksum passes.</span></span>

```
<!-- Singapore National Registration Identity Card (NRIC) Number -->
<Entity id="cead390a-dd83-4856-9751-fb6dc98c34da" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_singapore_nric"/>
     <Match idRef="Keyword_singapore_nric"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_singapore_nric"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2761">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2761">Keywords</span></span>
   
#### <a name="keywordsingaporenric"></a><span data-ttu-id="95cb4-2762">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="95cb4-2762">Keyword_singapore_nric</span></span>

- <span data-ttu-id="95cb4-2763">National Registration Identity Card</span><span class="sxs-lookup"><span data-stu-id="95cb4-2763">National Registration Identity Card</span></span> 
- <span data-ttu-id="95cb4-2764">Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2764">Identity Card Number</span></span> 
- <span data-ttu-id="95cb4-2765">NRIC</span><span class="sxs-lookup"><span data-stu-id="95cb4-2765">NRIC</span></span> 
- <span data-ttu-id="95cb4-2766">IC</span><span class="sxs-lookup"><span data-stu-id="95cb4-2766">IC</span></span> 
- <span data-ttu-id="95cb4-2767">Foreign Identification Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2767">Foreign Identification Number</span></span> 
- <span data-ttu-id="95cb4-2768">FIN</span><span class="sxs-lookup"><span data-stu-id="95cb4-2768">FIN</span></span> 
- <span data-ttu-id="95cb4-2769">身份证</span><span class="sxs-lookup"><span data-stu-id="95cb4-2769">身份证</span></span> 
- <span data-ttu-id="95cb4-2770">證</span><span class="sxs-lookup"><span data-stu-id="95cb4-2770">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="95cb4-2771">南非身份证号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2771">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2772">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2772">Format</span></span>

<span data-ttu-id="95cb4-2773">13 个数字（可能包含空格）</span><span class="sxs-lookup"><span data-stu-id="95cb4-2773">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2774">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2774">Pattern</span></span>

<span data-ttu-id="95cb4-2775">13 个数字：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2775">13 digits:</span></span>
- <span data-ttu-id="95cb4-2776">六个数字，采用  YYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="95cb4-2776">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="95cb4-2777">四个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2777">Four digits</span></span> 
- <span data-ttu-id="95cb4-2778">一位公民指示码 </span><span class="sxs-lookup"><span data-stu-id="95cb4-2778">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="95cb4-2779">数字“8”或“9” </span><span class="sxs-lookup"><span data-stu-id="95cb4-2779">The digit "8" or "9"</span></span> 
- <span data-ttu-id="95cb4-2780">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="95cb4-2780">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2781">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2781">Checksum</span></span>

<span data-ttu-id="95cb4-2782">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-2782">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2783">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2783">Definition</span></span>

<span data-ttu-id="95cb4-2784">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2784">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2785">函数 Func_south_africa_identification_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2785">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2786">找到 Keyword_south_africa_identification_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2786">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="95cb4-2787">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2787">The checksum passes.</span></span>

```
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2788">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2788">Keywords</span></span>
   
#### <a name="keywordsouthafricaidentificationnumber"></a><span data-ttu-id="95cb4-2789">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2789">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="95cb4-2790">Identity card</span><span class="sxs-lookup"><span data-stu-id="95cb4-2790">Identity card</span></span>
- <span data-ttu-id="95cb4-2791">ID</span><span class="sxs-lookup"><span data-stu-id="95cb4-2791">ID</span></span>
- <span data-ttu-id="95cb4-2792">id</span><span class="sxs-lookup"><span data-stu-id="95cb4-2792">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="95cb4-2793">韩国居民注册号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-2793">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2794">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2794">Format</span></span>

<span data-ttu-id="95cb4-2795">13 个数字（包含连字符）</span><span class="sxs-lookup"><span data-stu-id="95cb4-2795">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2796">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2796">Pattern</span></span>

<span data-ttu-id="95cb4-2797">13 个数字：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2797">13 digits:</span></span>
- <span data-ttu-id="95cb4-2798">六个数字，采用  YYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="95cb4-2798">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="95cb4-2799">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="95cb4-2799">A hyphen</span></span> 
- <span data-ttu-id="95cb4-2800">一个数字，由世纪和性别 </span><span class="sxs-lookup"><span data-stu-id="95cb4-2800">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="95cb4-2801">四位数字的出生地区代码 </span><span class="sxs-lookup"><span data-stu-id="95cb4-2801">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="95cb4-2802">一个数字，用于区分前面数字均相同的人 </span><span class="sxs-lookup"><span data-stu-id="95cb4-2802">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="95cb4-2803">一个校验位。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2803">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2804">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2804">Checksum</span></span>

<span data-ttu-id="95cb4-2805">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-2805">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2806">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2806">Definition</span></span>

<span data-ttu-id="95cb4-2807">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2807">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2808">函数 Func_south_korea_resident_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2808">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2809">找到 Keyword_south_korea_resident_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2809">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="95cb4-2810">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2810">The checksum passes.</span></span>

<span data-ttu-id="95cb4-2811">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2811">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2812">函数 Func_south_korea_resident_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2812">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2813">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2813">The checksum passes.</span></span>

```
<!-- South Korea Resident Registration Number -->
<Entity id="5b802e18-ba80-44c4-bc83-bf2ad36ae36a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_korea_resident_number"/>
     <Match idRef="Keyword_south_korea_resident_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_south_korea_resident_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2814">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2814">Keywords</span></span>
   
#### <a name="keywordsouthkorearesidentnumber"></a><span data-ttu-id="95cb4-2815">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2815">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="95cb4-2816">National ID card</span><span class="sxs-lookup"><span data-stu-id="95cb4-2816">National ID card</span></span> 
- <span data-ttu-id="95cb4-2817">Citizen's Registration Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2817">Citizen's Registration Number</span></span> 
- <span data-ttu-id="95cb4-2818">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="95cb4-2818">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="95cb4-2819">RRN</span><span class="sxs-lookup"><span data-stu-id="95cb4-2819">RRN</span></span> 
- <span data-ttu-id="95cb4-2820">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="95cb4-2820">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="95cb4-2821">西班牙社会保险号码 (SSN)</span><span class="sxs-lookup"><span data-stu-id="95cb4-2821">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2822">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2822">Format</span></span>

<span data-ttu-id="95cb4-2823">11-12 个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2823">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2824">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2824">Pattern</span></span>

<span data-ttu-id="95cb4-2825">11-12 位数:</span><span class="sxs-lookup"><span data-stu-id="95cb4-2825">11-12 digits:</span></span>
- <span data-ttu-id="95cb4-2826">两位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2826">Two digits</span></span> 
- <span data-ttu-id="95cb4-2827">正斜杠（可选）</span><span class="sxs-lookup"><span data-stu-id="95cb4-2827">A forward slash (optional)</span></span> 
- <span data-ttu-id="95cb4-2828">7-8 位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2828">7-8 digits</span></span> 
- <span data-ttu-id="95cb4-2829">正斜杠（可选）</span><span class="sxs-lookup"><span data-stu-id="95cb4-2829">A forward slash (optional)</span></span> 
- <span data-ttu-id="95cb4-2830">两位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2830">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2831">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2831">Checksum</span></span>

<span data-ttu-id="95cb4-2832">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-2832">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2833">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2833">Definition</span></span>

<span data-ttu-id="95cb4-2834">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2834">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2835">函数 Func_spanish_social_security_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2835">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2836">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2836">The checksum passes.</span></span>

```
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2837">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2837">Keywords</span></span>

<span data-ttu-id="95cb4-2838">None</span><span class="sxs-lookup"><span data-stu-id="95cb4-2838">None</span></span>
   
## <a name="sweden-national-id"></a><span data-ttu-id="95cb4-2839">瑞典国家 ID</span><span class="sxs-lookup"><span data-stu-id="95cb4-2839">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2840">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2840">Format</span></span>

<span data-ttu-id="95cb4-2841">10 个或 12 个数字和一个可选分隔符</span><span class="sxs-lookup"><span data-stu-id="95cb4-2841">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2842">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2842">Pattern</span></span>

<span data-ttu-id="95cb4-2843">10 或 12 位数字和可选的分隔符：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2843">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="95cb4-2844">2-4 位数字（可选）</span><span class="sxs-lookup"><span data-stu-id="95cb4-2844">2-4 digits (optional)</span></span> 
- <span data-ttu-id="95cb4-2845">采用日期格式 YYMMDD 的六位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2845">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="95cb4-2846">“-”或“+”（可选）的分隔符，加</span><span class="sxs-lookup"><span data-stu-id="95cb4-2846">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="95cb4-2847">四个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2847">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2848">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2848">Checksum</span></span>

<span data-ttu-id="95cb4-2849">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-2849">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2850">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2850">Definition</span></span>

<span data-ttu-id="95cb4-2851">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2851">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2852">函数 Func_swedish_national_identifier 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2852">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2853">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2853">The checksum passes.</span></span>

```
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2854">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2854">Keywords</span></span>

<span data-ttu-id="95cb4-2855">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-2855">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="95cb4-2856">瑞典护照号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-2856">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2857">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2857">Format</span></span>

<span data-ttu-id="95cb4-2858">八个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2858">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2859">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2859">Pattern</span></span>

<span data-ttu-id="95cb4-2860">八个连续的数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2860">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2861">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2861">Checksum</span></span>

<span data-ttu-id="95cb4-2862">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-2862">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2863">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2863">Definition</span></span>

<span data-ttu-id="95cb4-2864">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2864">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2865">正则表达式 Regex_sweden_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2865">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2866">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2866">One of the following is true:</span></span>
    - <span data-ttu-id="95cb4-2867">找到 Keyword_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2867">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="95cb4-2868">找到 Keyword_sweden_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2868">A keyword from Keyword_sweden_passport is found.</span></span>

```
<!-- Sweden Passport Number -->
<Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_sweden_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_sweden_passport" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2869">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2869">Keywords</span></span>
   
#### <a name="keywordswedenpassport"></a><span data-ttu-id="95cb4-2870">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="95cb4-2870">Keyword_sweden_passport</span></span>

- <span data-ttu-id="95cb4-2871">visa requirements</span><span class="sxs-lookup"><span data-stu-id="95cb4-2871">visa requirements</span></span> 
- <span data-ttu-id="95cb4-2872">Alien Registration Card</span><span class="sxs-lookup"><span data-stu-id="95cb4-2872">Alien Registration Card</span></span> 
- <span data-ttu-id="95cb4-2873">Schengen visas</span><span class="sxs-lookup"><span data-stu-id="95cb4-2873">Schengen visas</span></span> 
- <span data-ttu-id="95cb4-2874">Schengen visa</span><span class="sxs-lookup"><span data-stu-id="95cb4-2874">Schengen visa</span></span> 
- <span data-ttu-id="95cb4-2875">Visa Processing</span><span class="sxs-lookup"><span data-stu-id="95cb4-2875">Visa Processing</span></span> 
- <span data-ttu-id="95cb4-2876">Visa Type</span><span class="sxs-lookup"><span data-stu-id="95cb4-2876">Visa Type</span></span> 
- <span data-ttu-id="95cb4-2877">Single Entry</span><span class="sxs-lookup"><span data-stu-id="95cb4-2877">Single Entry</span></span> 
- <span data-ttu-id="95cb4-2878">Multiple Entry</span><span class="sxs-lookup"><span data-stu-id="95cb4-2878">Multiple Entry</span></span> 
- <span data-ttu-id="95cb4-2879">G3 Processing Fees</span><span class="sxs-lookup"><span data-stu-id="95cb4-2879">G3 Processing Fees</span></span> 

#### <a name="keywordpassport"></a><span data-ttu-id="95cb4-2880">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="95cb4-2880">Keyword_passport</span></span>

- <span data-ttu-id="95cb4-2881">Passport Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2881">Passport Number</span></span> 
- <span data-ttu-id="95cb4-2882">Passport No</span><span class="sxs-lookup"><span data-stu-id="95cb4-2882">Passport No</span></span> 
- <span data-ttu-id="95cb4-2883">Passport #</span><span class="sxs-lookup"><span data-stu-id="95cb4-2883">Passport #</span></span> 
- <span data-ttu-id="95cb4-2884">登记卡</span><span class="sxs-lookup"><span data-stu-id="95cb4-2884">Passport#</span></span> 
- <span data-ttu-id="95cb4-2885">PassportID</span><span class="sxs-lookup"><span data-stu-id="95cb4-2885">PassportID</span></span> 
- <span data-ttu-id="95cb4-2886">Passportno</span><span class="sxs-lookup"><span data-stu-id="95cb4-2886">Passportno</span></span> 
- <span data-ttu-id="95cb4-2887">passportnumber</span><span class="sxs-lookup"><span data-stu-id="95cb4-2887">passportnumber</span></span> 
- <span data-ttu-id="95cb4-2888">パスポート</span><span class="sxs-lookup"><span data-stu-id="95cb4-2888">パスポート</span></span> 
- <span data-ttu-id="95cb4-2889">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2889">パスポート番号</span></span> 
- <span data-ttu-id="95cb4-2890">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="95cb4-2890">パスポートのNum</span></span> 
- <span data-ttu-id="95cb4-2891">パスポート #</span><span class="sxs-lookup"><span data-stu-id="95cb4-2891">パスポート＃</span></span> 
- <span data-ttu-id="95cb4-2892">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="95cb4-2892">Numéro de passeport</span></span> 
- <span data-ttu-id="95cb4-2893">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="95cb4-2893">Passeport n °</span></span> 
- <span data-ttu-id="95cb4-2894">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="95cb4-2894">Passeport Non</span></span> 
- <span data-ttu-id="95cb4-2895">Passeport #</span><span class="sxs-lookup"><span data-stu-id="95cb4-2895">Passeport #</span></span> 
- <span data-ttu-id="95cb4-2896">Passeport #</span><span class="sxs-lookup"><span data-stu-id="95cb4-2896">Passeport#</span></span> 
- <span data-ttu-id="95cb4-2897">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="95cb4-2897">PasseportNon</span></span> 
- <span data-ttu-id="95cb4-2898">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="95cb4-2898">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="95cb4-2899">SWIFT 代码</span><span class="sxs-lookup"><span data-stu-id="95cb4-2899">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2900">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2900">Format</span></span>

<span data-ttu-id="95cb4-2901">四个字母后跟 5-31 个字母或数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2901">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2902">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2902">Pattern</span></span>

<span data-ttu-id="95cb4-2903">四个字母后跟 5-31 个字母或数字：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2903">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="95cb4-2904">四个字母的银行代码（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="95cb4-2904">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="95cb4-2905">可选空格</span><span class="sxs-lookup"><span data-stu-id="95cb4-2905">An optional space</span></span> 
- <span data-ttu-id="95cb4-2906">4-28 个字母或数字（基本银行账号 (BBAN)）</span><span class="sxs-lookup"><span data-stu-id="95cb4-2906">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="95cb4-2907">可选空格</span><span class="sxs-lookup"><span data-stu-id="95cb4-2907">An optional space</span></span> 
- <span data-ttu-id="95cb4-2908">1-3 个字母或数字（BBAN 的剩余内容）</span><span class="sxs-lookup"><span data-stu-id="95cb4-2908">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2909">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2909">Checksum</span></span>

<span data-ttu-id="95cb4-2910">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-2910">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2911">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2911">Definition</span></span>

<span data-ttu-id="95cb4-2912">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2912">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2913">正则表达式 Regex_swift 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2913">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2914">找到 Keyword_swift 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2914">A keyword from Keyword_swift is found.</span></span>

```
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2915">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2915">Keywords</span></span>
   
#### <a name="keywordswift"></a><span data-ttu-id="95cb4-2916">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="95cb4-2916">Keyword_swift</span></span>

- <span data-ttu-id="95cb4-2917">international organization for standardization 9362</span><span class="sxs-lookup"><span data-stu-id="95cb4-2917">international organization for standardization 9362</span></span> 
- <span data-ttu-id="95cb4-2918">iso 9362</span><span class="sxs-lookup"><span data-stu-id="95cb4-2918">iso 9362</span></span> 
- <span data-ttu-id="95cb4-2919">iso9362</span><span class="sxs-lookup"><span data-stu-id="95cb4-2919">iso9362</span></span> 
- <span data-ttu-id="95cb4-2920">反应\#</span><span class="sxs-lookup"><span data-stu-id="95cb4-2920">swift\#</span></span> 
- <span data-ttu-id="95cb4-2921">swiftcode</span><span class="sxs-lookup"><span data-stu-id="95cb4-2921">swiftcode</span></span> 
- <span data-ttu-id="95cb4-2922">swiftnumber</span><span class="sxs-lookup"><span data-stu-id="95cb4-2922">swiftnumber</span></span> 
- <span data-ttu-id="95cb4-2923">swiftroutingnumber</span><span class="sxs-lookup"><span data-stu-id="95cb4-2923">swiftroutingnumber</span></span> 
- <span data-ttu-id="95cb4-2924">swift code</span><span class="sxs-lookup"><span data-stu-id="95cb4-2924">swift code</span></span> 
- <span data-ttu-id="95cb4-2925">swift number #</span><span class="sxs-lookup"><span data-stu-id="95cb4-2925">swift number #</span></span> 
- <span data-ttu-id="95cb4-2926">swift routing number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2926">swift routing number</span></span> 
- <span data-ttu-id="95cb4-2927">bic number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2927">bic number</span></span> 
- <span data-ttu-id="95cb4-2928">bic code</span><span class="sxs-lookup"><span data-stu-id="95cb4-2928">bic code</span></span> 
- <span data-ttu-id="95cb4-2929">numéro\#</span><span class="sxs-lookup"><span data-stu-id="95cb4-2929">bic \#</span></span> 
- <span data-ttu-id="95cb4-2930">numéro\#</span><span class="sxs-lookup"><span data-stu-id="95cb4-2930">bic\#</span></span> 
- <span data-ttu-id="95cb4-2931">bank identifier code</span><span class="sxs-lookup"><span data-stu-id="95cb4-2931">bank identifier code</span></span> 
- <span data-ttu-id="95cb4-2932">標準化9362</span><span class="sxs-lookup"><span data-stu-id="95cb4-2932">標準化9362</span></span> 
- <span data-ttu-id="95cb4-2933">迅速 #</span><span class="sxs-lookup"><span data-stu-id="95cb4-2933">迅速＃</span></span> 
- <span data-ttu-id="95cb4-2934">SWIFTコード</span><span class="sxs-lookup"><span data-stu-id="95cb4-2934">SWIFTコード</span></span> 
- <span data-ttu-id="95cb4-2935">SWIFT番号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2935">SWIFT番号</span></span> 
- <span data-ttu-id="95cb4-2936">迅速なルーティング番号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2936">迅速なルーティング番号</span></span> 
- <span data-ttu-id="95cb4-2937">BIC番号</span><span class="sxs-lookup"><span data-stu-id="95cb4-2937">BIC番号</span></span> 
- <span data-ttu-id="95cb4-2938">BICコード</span><span class="sxs-lookup"><span data-stu-id="95cb4-2938">BICコード</span></span> 
- <span data-ttu-id="95cb4-2939">銀行識別コードのための国際組織</span><span class="sxs-lookup"><span data-stu-id="95cb4-2939">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="95cb4-2940">Organisation internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="95cb4-2940">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="95cb4-2941">rapide\#</span><span class="sxs-lookup"><span data-stu-id="95cb4-2941">rapide \#</span></span> 
- <span data-ttu-id="95cb4-2942">code SWIFT</span><span class="sxs-lookup"><span data-stu-id="95cb4-2942">code SWIFT</span></span> 
- <span data-ttu-id="95cb4-2943">le numéro de swift</span><span class="sxs-lookup"><span data-stu-id="95cb4-2943">le numéro de swift</span></span> 
- <span data-ttu-id="95cb4-2944">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="95cb4-2944">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="95cb4-2945">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="95cb4-2945">le numéro BIC</span></span> 
- <span data-ttu-id="95cb4-2946">\#numéro</span><span class="sxs-lookup"><span data-stu-id="95cb4-2946">\# BIC</span></span> 
- <span data-ttu-id="95cb4-2947">code identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="95cb4-2947">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="95cb4-2948">台湾国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="95cb4-2948">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2949">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2949">Format</span></span>

<span data-ttu-id="95cb4-2950">一个字母后跟九个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2950">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2951">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2951">Pattern</span></span>

<span data-ttu-id="95cb4-2952">一个字母后跟 9 位数字：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2952">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="95cb4-2953">一个字母（英文，不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="95cb4-2953">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="95cb4-2954">数字“1”或“2”</span><span class="sxs-lookup"><span data-stu-id="95cb4-2954">The digit "1" or "2"</span></span> 
- <span data-ttu-id="95cb4-2955">八位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2955">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2956">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2956">Checksum</span></span>

<span data-ttu-id="95cb4-2957">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-2957">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2958">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2958">Definition</span></span>

<span data-ttu-id="95cb4-2959">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2959">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2960">函数 Func_taiwanese_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2960">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2961">找到 Keyword_taiwanese_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2961">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="95cb4-2962">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2962">The checksum passes.</span></span>

```
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2963">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2963">Keywords</span></span>

#### <a name="keywordtaiwanesenationalid"></a><span data-ttu-id="95cb4-2964">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="95cb4-2964">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="95cb4-2965">身份證字號</span><span class="sxs-lookup"><span data-stu-id="95cb4-2965">身份證字號</span></span> 
- <span data-ttu-id="95cb4-2966">證</span><span class="sxs-lookup"><span data-stu-id="95cb4-2966">身份證</span></span> 
- <span data-ttu-id="95cb4-2967">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="95cb4-2967">身份證號碼</span></span> 
- <span data-ttu-id="95cb4-2968">身份證號</span><span class="sxs-lookup"><span data-stu-id="95cb4-2968">身份證號</span></span> 
- <span data-ttu-id="95cb4-2969">身分證字號</span><span class="sxs-lookup"><span data-stu-id="95cb4-2969">身分證字號</span></span> 
- <span data-ttu-id="95cb4-2970">身分證</span><span class="sxs-lookup"><span data-stu-id="95cb4-2970">身分證</span></span> 
- <span data-ttu-id="95cb4-2971">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="95cb4-2971">身分證號碼</span></span> 
- <span data-ttu-id="95cb4-2972">身份證號</span><span class="sxs-lookup"><span data-stu-id="95cb4-2972">身份證號</span></span> 
- <span data-ttu-id="95cb4-2973">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="95cb4-2973">身分證統一編號</span></span> 
- <span data-ttu-id="95cb4-2974">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="95cb4-2974">國民身分證統一編號</span></span> 
- <span data-ttu-id="95cb4-2975">簽名</span><span class="sxs-lookup"><span data-stu-id="95cb4-2975">簽名</span></span> 
- <span data-ttu-id="95cb4-2976">蓋章</span><span class="sxs-lookup"><span data-stu-id="95cb4-2976">蓋章</span></span> 
- <span data-ttu-id="95cb4-2977">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="95cb4-2977">簽名或蓋章</span></span> 
- <span data-ttu-id="95cb4-2978">簽章</span><span class="sxs-lookup"><span data-stu-id="95cb4-2978">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="95cb4-2979">	台湾护照号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-2979">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-2980">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-2980">Format</span></span>

- <span data-ttu-id="95cb4-2981">生物识别护照号码: 9 个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2981">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="95cb4-2982">不带生物的护照号码: 9 个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2982">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-2983">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-2983">Pattern</span></span>
<span data-ttu-id="95cb4-2984">生物识别护照号码:</span><span class="sxs-lookup"><span data-stu-id="95cb4-2984">Biometric passport number:</span></span>
- <span data-ttu-id="95cb4-2985">数字“3” </span><span class="sxs-lookup"><span data-stu-id="95cb4-2985">The digit "3"</span></span> 
- <span data-ttu-id="95cb4-2986">八个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2986">Eight digits</span></span>

<span data-ttu-id="95cb4-2987">不带生物的护照号码:</span><span class="sxs-lookup"><span data-stu-id="95cb4-2987">Non-biometric passport number:</span></span>
- <span data-ttu-id="95cb4-2988">九个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2988">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-2989">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-2989">Checksum</span></span>

<span data-ttu-id="95cb4-2990">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-2990">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-2991">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-2991">Definition</span></span>

<span data-ttu-id="95cb4-2992">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-2992">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-2993">正则表达式 Regex_taiwan_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2993">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-2994">找到 Keyword_taiwan_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-2994">A keyword from Keyword_taiwan_passport is found.</span></span>

```
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-2995">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-2995">Keywords</span></span>

#### <a name="keywordtaiwanpassport"></a><span data-ttu-id="95cb4-2996">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="95cb4-2996">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="95cb4-2997">ROC passport number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2997">ROC passport number</span></span> 
- <span data-ttu-id="95cb4-2998">Passport number</span><span class="sxs-lookup"><span data-stu-id="95cb4-2998">Passport number</span></span> 
- <span data-ttu-id="95cb4-2999">Passport no</span><span class="sxs-lookup"><span data-stu-id="95cb4-2999">Passport no</span></span> 
- <span data-ttu-id="95cb4-3000">Passport Num</span><span class="sxs-lookup"><span data-stu-id="95cb4-3000">Passport Num</span></span> 
- <span data-ttu-id="95cb4-3001">Passport #</span><span class="sxs-lookup"><span data-stu-id="95cb4-3001">Passport #</span></span> 
- <span data-ttu-id="95cb4-3002">护照</span><span class="sxs-lookup"><span data-stu-id="95cb4-3002">护照</span></span> 
- <span data-ttu-id="95cb4-3003">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="95cb4-3003">中華民國護照</span></span> 
- <span data-ttu-id="95cb4-3004">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="95cb4-3004">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="95cb4-3005">台湾居民证 (ARC/TARC) 号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-3005">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-3006">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-3006">Format</span></span>

<span data-ttu-id="95cb4-3007">10 letters and digits</span><span class="sxs-lookup"><span data-stu-id="95cb4-3007">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-3008">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-3008">Pattern</span></span>

<span data-ttu-id="95cb4-3009">10 个字母和数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3009">10 letters and digits:</span></span>
- <span data-ttu-id="95cb4-3010">两个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="95cb4-3010">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="95cb4-3011">八个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3011">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-3012">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-3012">Checksum</span></span>

<span data-ttu-id="95cb4-3013">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-3013">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-3014">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-3014">Definition</span></span>

<span data-ttu-id="95cb4-3015">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-3015">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-3016">正则表达式 Regex_taiwan_resident_certificate 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3016">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-3017">找到 Keyword_taiwan_resident_certificate 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3017">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-3018">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3018">Keywords</span></span>

#### <a name="keywordtaiwanresidentcertificate"></a><span data-ttu-id="95cb4-3019">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="95cb4-3019">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="95cb4-3020">Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="95cb4-3020">Resident Certificate</span></span> 
- <span data-ttu-id="95cb4-3021">Resident Cert</span><span class="sxs-lookup"><span data-stu-id="95cb4-3021">Resident Cert</span></span> 
- <span data-ttu-id="95cb4-3022">Resident Cert.</span><span class="sxs-lookup"><span data-stu-id="95cb4-3022">Resident Cert.</span></span> 
- <span data-ttu-id="95cb4-3023">Identification card</span><span class="sxs-lookup"><span data-stu-id="95cb4-3023">Identification card</span></span> 
- <span data-ttu-id="95cb4-3024">Alien Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="95cb4-3024">Alien Resident Certificate</span></span> 
- <span data-ttu-id="95cb4-3025">ARC</span><span class="sxs-lookup"><span data-stu-id="95cb4-3025">ARC</span></span> 
- <span data-ttu-id="95cb4-3026">Taiwan Area Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="95cb4-3026">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="95cb4-3027">TARC</span><span class="sxs-lookup"><span data-stu-id="95cb4-3027">TARC</span></span> 
- <span data-ttu-id="95cb4-3028">居留證</span><span class="sxs-lookup"><span data-stu-id="95cb4-3028">居留證</span></span> 
- <span data-ttu-id="95cb4-3029">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="95cb4-3029">外僑居留證</span></span> 
- <span data-ttu-id="95cb4-3030">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="95cb4-3030">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="95cb4-3031">泰语填充标识代码</span><span class="sxs-lookup"><span data-stu-id="95cb4-3031">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-3032">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-3032">Format</span></span>

<span data-ttu-id="95cb4-3033">13 位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3033">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-3034">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-3034">Pattern</span></span>

<span data-ttu-id="95cb4-3035">13 个数字：</span><span class="sxs-lookup"><span data-stu-id="95cb4-3035">13 digits:</span></span>
- <span data-ttu-id="95cb4-3036">第一个数字不是0或9</span><span class="sxs-lookup"><span data-stu-id="95cb4-3036">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="95cb4-3037">12 个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3037">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-3038">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-3038">Checksum</span></span>

<span data-ttu-id="95cb4-3039">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-3039">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-3040">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-3040">Definition</span></span>

<span data-ttu-id="95cb4-3041">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-3041">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-3042">函数 Func_Thai_Citizen_Id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3042">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-3043">找到 Keyword_Thai_Citizen_Id 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3043">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="95cb4-3044">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-3044">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-3045">函数 Func_Thai_Citizen_Id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3045">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

```
<!-- Thai Citizen ID -->
-<Entity id="44ca9e86-ead7-4c5d-884a-e2eaa401515e" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
      <Match idRef="Keyword_Thai_Citizen_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-3046">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3046">Keywords</span></span>

#### <a name="keywordthaicitizenid"></a><span data-ttu-id="95cb4-3047">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="95cb4-3047">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="95cb4-3048">ID Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-3048">ID Number</span></span>
- <span data-ttu-id="95cb4-3049">标识号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-3049">Identification Number</span></span>
- <span data-ttu-id="95cb4-3050">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="95cb4-3050">บัตรประชาชน</span></span>
- <span data-ttu-id="95cb4-3051">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="95cb4-3051">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="95cb4-3052">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="95cb4-3052">บัตรประชาชน</span></span>
- <span data-ttu-id="95cb4-3053">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="95cb4-3053">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="95cb4-3054">土耳其国家标识号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-3054">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-3055">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-3055">Format</span></span>

<span data-ttu-id="95cb4-3056">11 个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3056">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-3057">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-3057">Pattern</span></span>

<span data-ttu-id="95cb4-3058">11 个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3058">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-3059">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-3059">Checksum</span></span>

<span data-ttu-id="95cb4-3060">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-3060">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-3061">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-3061">Definition</span></span>

<span data-ttu-id="95cb4-3062">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-3062">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-3063">函数 Func_Turkish_National_Id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3063">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-3064">找到 Keyword_Turkish_National_Id 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3064">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="95cb4-3065">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-3065">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-3066">函数 Func_Turkish_National_Id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3066">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

```
<!-- Turkish National Identity -->
-<Entity id="fb621f20-3876-4cfc-acec-8c8e73ca32c7" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Turkish_National_Id"/>
      <Match idRef="Keyword_Turkish_National_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Turkish_National_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-3067">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3067">Keywords</span></span>

#### <a name="keywordturkishnationalid"></a><span data-ttu-id="95cb4-3068">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="95cb4-3068">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="95cb4-3069">TC Kimlik No</span><span class="sxs-lookup"><span data-stu-id="95cb4-3069">TC Kimlik No</span></span>
- <span data-ttu-id="95cb4-3070">TC Kimlik numarası</span><span class="sxs-lookup"><span data-stu-id="95cb4-3070">TC Kimlik numarası</span></span>
- <span data-ttu-id="95cb4-3071">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="95cb4-3071">Vatandaşlık numarası</span></span>
- <span data-ttu-id="95cb4-3072">Vatandaşlık no</span><span class="sxs-lookup"><span data-stu-id="95cb4-3072">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="95cb4-p141">英国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-p141">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-3075">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-3075">Format</span></span>

<span data-ttu-id="95cb4-3076">特定格式的 18 个字母和数字组合</span><span class="sxs-lookup"><span data-stu-id="95cb4-3076">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-3077">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-3077">Pattern</span></span>

<span data-ttu-id="95cb4-3078">18 个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="95cb4-3078">18 letters and digits:</span></span>
- <span data-ttu-id="95cb4-3079">用五个字母（不区分大小写）或数字“9”来代替一个字母</span><span class="sxs-lookup"><span data-stu-id="95cb4-3079">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="95cb4-3080">一位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3080">One digit</span></span> 
- <span data-ttu-id="95cb4-3081">采用日期格式 DDMMY 的五位数字，表示出生日期</span><span class="sxs-lookup"><span data-stu-id="95cb4-3081">Five digits in the date format DDMMY for date of birth</span></span> 
- <span data-ttu-id="95cb4-3082">用两个字母（不区分大小写）或数字“9”来代替一个字母</span><span class="sxs-lookup"><span data-stu-id="95cb4-3082">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="95cb4-3083">五位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3083">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-3084">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-3084">Checksum</span></span>

<span data-ttu-id="95cb4-3085">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-3085">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-3086">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-3086">Definition</span></span>

<span data-ttu-id="95cb4-3087">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-3087">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-3088">函数 Func_uk_drivers_license 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3088">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-3089">找到 Keyword_uk_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3089">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="95cb4-3090">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3090">The checksum passes.</span></span>

```
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-3091">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3091">Keywords</span></span>

#### <a name="keywordukdriverslicense"></a><span data-ttu-id="95cb4-3092">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="95cb4-3092">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="95cb4-3093">DVLA</span><span class="sxs-lookup"><span data-stu-id="95cb4-3093">DVLA</span></span> 
- <span data-ttu-id="95cb4-3094">light vans</span><span class="sxs-lookup"><span data-stu-id="95cb4-3094">light vans</span></span> 
- <span data-ttu-id="95cb4-3095">quadbikes</span><span class="sxs-lookup"><span data-stu-id="95cb4-3095">quadbikes</span></span> 
- <span data-ttu-id="95cb4-3096">motor cars</span><span class="sxs-lookup"><span data-stu-id="95cb4-3096">motor cars</span></span> 
- <span data-ttu-id="95cb4-3097">125cc</span><span class="sxs-lookup"><span data-stu-id="95cb4-3097">125cc</span></span> 
- <span data-ttu-id="95cb4-3098">sidecar</span><span class="sxs-lookup"><span data-stu-id="95cb4-3098">sidecar</span></span> 
- <span data-ttu-id="95cb4-3099">tricycles</span><span class="sxs-lookup"><span data-stu-id="95cb4-3099">tricycles</span></span> 
- <span data-ttu-id="95cb4-3100">motorcycles</span><span class="sxs-lookup"><span data-stu-id="95cb4-3100">motorcycles</span></span> 
- <span data-ttu-id="95cb4-3101">photocard licence</span><span class="sxs-lookup"><span data-stu-id="95cb4-3101">photocard licence</span></span> 
- <span data-ttu-id="95cb4-3102">learner drivers</span><span class="sxs-lookup"><span data-stu-id="95cb4-3102">learner drivers</span></span> 
- <span data-ttu-id="95cb4-3103">licence holder</span><span class="sxs-lookup"><span data-stu-id="95cb4-3103">licence holder</span></span> 
- <span data-ttu-id="95cb4-3104">licence holders</span><span class="sxs-lookup"><span data-stu-id="95cb4-3104">licence holders</span></span> 
- <span data-ttu-id="95cb4-3105">driving licences</span><span class="sxs-lookup"><span data-stu-id="95cb4-3105">driving licences</span></span> 
- <span data-ttu-id="95cb4-3106">driving licence</span><span class="sxs-lookup"><span data-stu-id="95cb4-3106">driving licence</span></span> 
- <span data-ttu-id="95cb4-3107">dual control car</span><span class="sxs-lookup"><span data-stu-id="95cb4-3107">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="95cb4-p142">英国选民名册号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-p142">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-3110">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-3110">Format</span></span>

<span data-ttu-id="95cb4-3111">两个字母后跟 1-4 个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3111">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-3112">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-3112">Pattern</span></span>

<span data-ttu-id="95cb4-3113">两个字母（不区分大小写）后跟 1-4 个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3113">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-3114">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-3114">Checksum</span></span>

<span data-ttu-id="95cb4-3115">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-3115">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-3116">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-3116">Definition</span></span>

<span data-ttu-id="95cb4-3117">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-3117">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-3118">正则表达式 Regex_uk_electoral 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3118">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-3119">找到 Keyword_uk_electoral 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3119">A keyword from Keyword_uk_electoral is found.</span></span>

```
<!-- U.K. Electoral Number -->
<Entity id="a3eea206-dc0c-4f06-9e22-aa1be3059963" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_uk_electoral" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_electoral" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-3120">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3120">Keywords</span></span>

#### <a name="keywordukelectoral"></a><span data-ttu-id="95cb4-3121">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="95cb4-3121">Keyword_uk_electoral</span></span>

- <span data-ttu-id="95cb4-3122">council nomination</span><span class="sxs-lookup"><span data-stu-id="95cb4-3122">council nomination</span></span> 
- <span data-ttu-id="95cb4-3123">nomination form</span><span class="sxs-lookup"><span data-stu-id="95cb4-3123">nomination form</span></span> 
- <span data-ttu-id="95cb4-3124">electoral register</span><span class="sxs-lookup"><span data-stu-id="95cb4-3124">electoral register</span></span> 
- <span data-ttu-id="95cb4-3125">electoral roll</span><span class="sxs-lookup"><span data-stu-id="95cb4-3125">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="95cb4-p143">英国国家卫生服务号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-p143">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-3128">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-3128">Format</span></span>

<span data-ttu-id="95cb4-3129">10-17 个数字，通过空格分隔 </span><span class="sxs-lookup"><span data-stu-id="95cb4-3129">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-3130">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-3130">Pattern</span></span>

<span data-ttu-id="95cb4-3131">10-17 位数字：</span><span class="sxs-lookup"><span data-stu-id="95cb4-3131">10-17 digits:</span></span>
- <span data-ttu-id="95cb4-3132">3 或 10 位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3132">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="95cb4-3133">一个空格</span><span class="sxs-lookup"><span data-stu-id="95cb4-3133">A space</span></span> 
- <span data-ttu-id="95cb4-3134">三位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3134">Three digits</span></span> 
- <span data-ttu-id="95cb4-3135">一个空格</span><span class="sxs-lookup"><span data-stu-id="95cb4-3135">A space</span></span> 
- <span data-ttu-id="95cb4-3136">四位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3136">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-3137">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-3137">Checksum</span></span>

<span data-ttu-id="95cb4-3138">是</span><span class="sxs-lookup"><span data-stu-id="95cb4-3138">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-3139">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-3139">Definition</span></span>

<span data-ttu-id="95cb4-3140">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-3140">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-3141">函数 Func_uk_nhs_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3141">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-3142">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="95cb4-3142">One of the following is true:</span></span>
    - <span data-ttu-id="95cb4-3143">找到 Keyword_uk_nhs_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3143">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="95cb4-3144">找到 Keyword_uk_nhs_number1 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3144">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="95cb4-3145">找到 Keyword_uk_nhs_number_dob 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3145">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="95cb4-3146">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3146">The checksum passes.</span></span>

```
<!-- U.K. NHS Number -->
<Entity id="3192014e-2a16-44e9-aa69-4b20375c9a78" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nhs_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nhs_number" />
          <Match idRef="Keyword_uk_nhs_number1" />
          <Match idRef="Keyword_uk_nhs_number_dob" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-3147">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3147">Keywords</span></span>
   
#### <a name="keyworduknhsnumber"></a><span data-ttu-id="95cb4-3148">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="95cb4-3148">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="95cb4-3149">national health service</span><span class="sxs-lookup"><span data-stu-id="95cb4-3149">national health service</span></span> 
- <span data-ttu-id="95cb4-3150">nhs</span><span class="sxs-lookup"><span data-stu-id="95cb4-3150">nhs</span></span> 
- <span data-ttu-id="95cb4-3151">health services authority</span><span class="sxs-lookup"><span data-stu-id="95cb4-3151">health services authority</span></span> 
- <span data-ttu-id="95cb4-3152">health authority</span><span class="sxs-lookup"><span data-stu-id="95cb4-3152">health authority</span></span>

#### <a name="keyworduknhsnumber1"></a><span data-ttu-id="95cb4-3153">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="95cb4-3153">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="95cb4-3154">patient id</span><span class="sxs-lookup"><span data-stu-id="95cb4-3154">patient id</span></span> 
- <span data-ttu-id="95cb4-3155">patient identification</span><span class="sxs-lookup"><span data-stu-id="95cb4-3155">patient identification</span></span> 
- <span data-ttu-id="95cb4-3156">patient no</span><span class="sxs-lookup"><span data-stu-id="95cb4-3156">patient no</span></span> 
- <span data-ttu-id="95cb4-3157">patient number</span><span class="sxs-lookup"><span data-stu-id="95cb4-3157">patient number</span></span>

#### <a name="keyworduknhsnumberdob"></a><span data-ttu-id="95cb4-3158">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="95cb4-3158">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="95cb4-3159">GP</span><span class="sxs-lookup"><span data-stu-id="95cb4-3159">GP</span></span> 
- <span data-ttu-id="95cb4-3160">DOB</span><span class="sxs-lookup"><span data-stu-id="95cb4-3160">DOB</span></span> 
- <span data-ttu-id="95cb4-3161">D. B。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3161">D.O.B</span></span> 
- <span data-ttu-id="95cb4-3162">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="95cb4-3162">Date of Birth</span></span> 
- <span data-ttu-id="95cb4-3163">Birth Date</span><span class="sxs-lookup"><span data-stu-id="95cb4-3163">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="95cb4-p144">英国国家保险号码 (NINO)</span><span class="sxs-lookup"><span data-stu-id="95cb4-p144">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-3166">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-3166">Format</span></span>

<span data-ttu-id="95cb4-3167">由空格或短划线分隔的7个字符或9个字符</span><span class="sxs-lookup"><span data-stu-id="95cb4-3167">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-3168">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-3168">Pattern</span></span>

<span data-ttu-id="95cb4-3169">两种可能的模式:</span><span class="sxs-lookup"><span data-stu-id="95cb4-3169">Two possible patterns:</span></span>

- <span data-ttu-id="95cb4-3170">两个字母 (有效 NINOs 仅使用此前缀中的特定字符, 此格式将对此进行验证; 不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="95cb4-3170">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="95cb4-3171">六位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3171">Six digits</span></span>
- <span data-ttu-id="95cb4-3172">"A"、"B"、"C" 或 "d" (与前缀一样, 后缀中只允许有某些字符; 不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="95cb4-3172">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="95cb4-3173">或者</span><span class="sxs-lookup"><span data-stu-id="95cb4-3173">OR</span></span>

- <span data-ttu-id="95cb4-3174">两个字母</span><span class="sxs-lookup"><span data-stu-id="95cb4-3174">Two letters</span></span>
- <span data-ttu-id="95cb4-3175">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="95cb4-3175">A space or dash</span></span>
- <span data-ttu-id="95cb4-3176">两位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3176">Two digits</span></span>
- <span data-ttu-id="95cb4-3177">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="95cb4-3177">A space or dash</span></span>
- <span data-ttu-id="95cb4-3178">两位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3178">Two digits</span></span>
- <span data-ttu-id="95cb4-3179">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="95cb4-3179">A space or dash</span></span>
- <span data-ttu-id="95cb4-3180">两位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3180">Two digits</span></span>
- <span data-ttu-id="95cb4-3181">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="95cb4-3181">A space or dash</span></span>
- <span data-ttu-id="95cb4-3182">要么是 "A"、"B"、"C", 要么 ' d '</span><span class="sxs-lookup"><span data-stu-id="95cb4-3182">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-3183">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-3183">Checksum</span></span>

<span data-ttu-id="95cb4-3184">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-3184">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-3185">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-3185">Definition</span></span>

<span data-ttu-id="95cb4-3186">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-3186">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-3187">函数 Func_uk_nino 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3187">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-3188">找到 Keyword_uk_nino 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3188">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="95cb4-3189">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-3189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-3190">函数 Func_uk_nino 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3190">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-3191">未找到 Keyword_uk_nino 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3191">No keyword from Keyword_uk_nino is found.</span></span>

```
<!-- U.K. NINO -->
<Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-3192">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3192">Keywords</span></span>

#### <a name="keyworduknino"></a><span data-ttu-id="95cb4-3193">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="95cb4-3193">Keyword_uk_nino</span></span>

- <span data-ttu-id="95cb4-3194">national insurance number</span><span class="sxs-lookup"><span data-stu-id="95cb4-3194">national insurance number</span></span> 
- <span data-ttu-id="95cb4-3195">national insurance contributions</span><span class="sxs-lookup"><span data-stu-id="95cb4-3195">national insurance contributions</span></span> 
- <span data-ttu-id="95cb4-3196">protection act</span><span class="sxs-lookup"><span data-stu-id="95cb4-3196">protection act</span></span> 
- <span data-ttu-id="95cb4-3197">方面</span><span class="sxs-lookup"><span data-stu-id="95cb4-3197">insurance</span></span> 
- <span data-ttu-id="95cb4-3198">social security number</span><span class="sxs-lookup"><span data-stu-id="95cb4-3198">social security number</span></span> 
- <span data-ttu-id="95cb4-3199">insurance application</span><span class="sxs-lookup"><span data-stu-id="95cb4-3199">insurance application</span></span> 
- <span data-ttu-id="95cb4-3200">medical application</span><span class="sxs-lookup"><span data-stu-id="95cb4-3200">medical application</span></span> 
- <span data-ttu-id="95cb4-3201">social insurance</span><span class="sxs-lookup"><span data-stu-id="95cb4-3201">social insurance</span></span> 
- <span data-ttu-id="95cb4-3202">medical attention</span><span class="sxs-lookup"><span data-stu-id="95cb4-3202">medical attention</span></span> 
- <span data-ttu-id="95cb4-3203">social security</span><span class="sxs-lookup"><span data-stu-id="95cb4-3203">social security</span></span> 
- <span data-ttu-id="95cb4-3204">great britain</span><span class="sxs-lookup"><span data-stu-id="95cb4-3204">great britain</span></span> 
- <span data-ttu-id="95cb4-3205">方面</span><span class="sxs-lookup"><span data-stu-id="95cb4-3205">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="95cb4-p145">美国/英国护照号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-p145">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-3208">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-3208">Format</span></span>

<span data-ttu-id="95cb4-3209">九个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3209">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-3210">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-3210">Pattern</span></span>

<span data-ttu-id="95cb4-3211">九个连续的数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3211">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-3212">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-3212">Checksum</span></span>

<span data-ttu-id="95cb4-3213">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-3213">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-3214">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-3214">Definition</span></span>

<span data-ttu-id="95cb4-3215">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-3215">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-3216">函数 Func_usa_uk_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3216">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-3217">找到 Keyword_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3217">A keyword from Keyword_passport is found.</span></span>

```
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-3218">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3218">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="95cb4-3219">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="95cb4-3219">Keyword_passport</span></span>

- <span data-ttu-id="95cb4-3220">Passport Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-3220">Passport Number</span></span> 
- <span data-ttu-id="95cb4-3221">Passport No</span><span class="sxs-lookup"><span data-stu-id="95cb4-3221">Passport No</span></span> 
- <span data-ttu-id="95cb4-3222">Passport #</span><span class="sxs-lookup"><span data-stu-id="95cb4-3222">Passport #</span></span> 
- <span data-ttu-id="95cb4-3223">登记卡</span><span class="sxs-lookup"><span data-stu-id="95cb4-3223">Passport#</span></span> 
- <span data-ttu-id="95cb4-3224">PassportID</span><span class="sxs-lookup"><span data-stu-id="95cb4-3224">PassportID</span></span> 
- <span data-ttu-id="95cb4-3225">Passportno</span><span class="sxs-lookup"><span data-stu-id="95cb4-3225">Passportno</span></span> 
- <span data-ttu-id="95cb4-3226">passportnumber</span><span class="sxs-lookup"><span data-stu-id="95cb4-3226">passportnumber</span></span> 
- <span data-ttu-id="95cb4-3227">パスポート</span><span class="sxs-lookup"><span data-stu-id="95cb4-3227">パスポート</span></span> 
- <span data-ttu-id="95cb4-3228">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="95cb4-3228">パスポート番号</span></span> 
- <span data-ttu-id="95cb4-3229">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="95cb4-3229">パスポートのNum</span></span> 
- <span data-ttu-id="95cb4-3230">パスポート #</span><span class="sxs-lookup"><span data-stu-id="95cb4-3230">パスポート＃</span></span> 
- <span data-ttu-id="95cb4-3231">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="95cb4-3231">Numéro de passeport</span></span> 
- <span data-ttu-id="95cb4-3232">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="95cb4-3232">Passeport n °</span></span> 
- <span data-ttu-id="95cb4-3233">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="95cb4-3233">Passeport Non</span></span> 
- <span data-ttu-id="95cb4-3234">Passeport #</span><span class="sxs-lookup"><span data-stu-id="95cb4-3234">Passeport #</span></span> 
- <span data-ttu-id="95cb4-3235">Passeport #</span><span class="sxs-lookup"><span data-stu-id="95cb4-3235">Passeport#</span></span> 
- <span data-ttu-id="95cb4-3236">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="95cb4-3236">PasseportNon</span></span> 
- <span data-ttu-id="95cb4-3237">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="95cb4-3237">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="95cb4-3238">美国银行帐号</span><span class="sxs-lookup"><span data-stu-id="95cb4-3238">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-3239">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-3239">Format</span></span>

<span data-ttu-id="95cb4-3240">8-17 个数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3240">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-3241">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-3241">Pattern</span></span>

<span data-ttu-id="95cb4-3242">8-17 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3242">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-3243">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-3243">Checksum</span></span>

<span data-ttu-id="95cb4-3244">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-3244">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-3245">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-3245">Definition</span></span>

<span data-ttu-id="95cb4-3246">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-3246">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-3247">正则表达式 Regex_usa_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3247">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-3248">找到 Keyword_usa_Bank_Account 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3248">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-3249">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3249">Keywords</span></span>

#### <a name="keywordusabankaccount"></a><span data-ttu-id="95cb4-3250">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="95cb4-3250">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="95cb4-3251">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-3251">Checking Account Number</span></span> 
- <span data-ttu-id="95cb4-3252">Checking Account</span><span class="sxs-lookup"><span data-stu-id="95cb4-3252">Checking Account</span></span> 
- <span data-ttu-id="95cb4-3253">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="95cb4-3253">Checking Account #</span></span> 
- <span data-ttu-id="95cb4-3254">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-3254">Checking Acct Number</span></span> 
- <span data-ttu-id="95cb4-3255">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="95cb4-3255">Checking Acct #</span></span> 
- <span data-ttu-id="95cb4-3256">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="95cb4-3256">Checking Acct No.</span></span> 
- <span data-ttu-id="95cb4-3257">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="95cb4-3257">Checking Account No.</span></span> 
- <span data-ttu-id="95cb4-3258">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-3258">Bank Account Number</span></span> 
- <span data-ttu-id="95cb4-3259">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="95cb4-3259">Bank Account #</span></span> 
- <span data-ttu-id="95cb4-3260">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-3260">Bank Acct Number</span></span> 
- <span data-ttu-id="95cb4-3261">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="95cb4-3261">Bank Acct #</span></span> 
- <span data-ttu-id="95cb4-3262">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="95cb4-3262">Bank Acct No.</span></span> 
- <span data-ttu-id="95cb4-3263">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="95cb4-3263">Bank Account No.</span></span> 
- <span data-ttu-id="95cb4-3264">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-3264">Savings Account Number</span></span> 
- <span data-ttu-id="95cb4-3265">Savings Account.</span><span class="sxs-lookup"><span data-stu-id="95cb4-3265">Savings Account.</span></span> 
- <span data-ttu-id="95cb4-3266">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="95cb4-3266">Savings Account #</span></span> 
- <span data-ttu-id="95cb4-3267">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-3267">Savings Acct Number</span></span> 
- <span data-ttu-id="95cb4-3268">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="95cb4-3268">Savings Acct #</span></span> 
- <span data-ttu-id="95cb4-3269">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="95cb4-3269">Savings Acct No.</span></span> 
- <span data-ttu-id="95cb4-3270">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="95cb4-3270">Savings Account No.</span></span> 
- <span data-ttu-id="95cb4-3271">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-3271">Debit Account Number</span></span> 
- <span data-ttu-id="95cb4-3272">Debit Account</span><span class="sxs-lookup"><span data-stu-id="95cb4-3272">Debit Account</span></span> 
- <span data-ttu-id="95cb4-3273">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="95cb4-3273">Debit Account #</span></span> 
- <span data-ttu-id="95cb4-3274">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="95cb4-3274">Debit Acct Number</span></span> 
- <span data-ttu-id="95cb4-3275">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="95cb4-3275">Debit Acct #</span></span> 
- <span data-ttu-id="95cb4-3276">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="95cb4-3276">Debit Acct No.</span></span> 
- <span data-ttu-id="95cb4-3277">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="95cb4-3277">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="95cb4-3278">美国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="95cb4-3278">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-3279">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-3279">Format</span></span>

<span data-ttu-id="95cb4-3280">取决于州</span><span class="sxs-lookup"><span data-stu-id="95cb4-3280">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-3281">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-3281">Pattern</span></span>

<span data-ttu-id="95cb4-3282">取决于州 — 例如，纽约：</span><span class="sxs-lookup"><span data-stu-id="95cb4-3282">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="95cb4-3283">与 ddd ddd ddd 相匹配的9个数字的格式将会匹配。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3283">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="95cb4-3284">诸如 dddddddd 的 9 个数字将不匹配。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3284">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-3285">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-3285">Checksum</span></span>

<span data-ttu-id="95cb4-3286">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-3286">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-3287">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-3287">Definition</span></span>

<span data-ttu-id="95cb4-3288">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-3288">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-3289">函数 Func_new_york_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3289">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-3290">找到 Keyword_[state_name]_drivers_license_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3290">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="95cb4-3291">找到 Keyword_us_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3291">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="95cb4-3292">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-3292">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-3293">函数 Func_new_york_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3293">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-3294">找到 Keyword_[state_name]_drivers_license_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3294">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="95cb4-3295">找到 Keyword_us_drivers_license_abbreviations 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3295">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="95cb4-3296">未找到 Keyword_us_drivers_license 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3296">No keyword from Keyword_us_drivers_license is found.</span></span>

```
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license" />
    </Pattern>
    <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license_abbreviations" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_us_drivers_license" />
        </Any>
    </Pattern>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-3297">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3297">Keywords</span></span>

#### <a name="keywordusdriverslicenseabbreviations"></a><span data-ttu-id="95cb4-3298">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="95cb4-3298">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="95cb4-3299">通讯</span><span class="sxs-lookup"><span data-stu-id="95cb4-3299">DL</span></span> 
- <span data-ttu-id="95cb4-3300">DLS</span><span class="sxs-lookup"><span data-stu-id="95cb4-3300">DLS</span></span> 
- <span data-ttu-id="95cb4-3301">采用</span><span class="sxs-lookup"><span data-stu-id="95cb4-3301">CDL</span></span> 
- <span data-ttu-id="95cb4-3302">CDLS</span><span class="sxs-lookup"><span data-stu-id="95cb4-3302">CDLS</span></span> 
- <span data-ttu-id="95cb4-3303">ID</span><span class="sxs-lookup"><span data-stu-id="95cb4-3303">ID</span></span> 
- <span data-ttu-id="95cb4-3304">id</span><span class="sxs-lookup"><span data-stu-id="95cb4-3304">IDs</span></span> 
- <span data-ttu-id="95cb4-3305">通讯</span><span class="sxs-lookup"><span data-stu-id="95cb4-3305">DL#</span></span> 
- <span data-ttu-id="95cb4-3306">DLS</span><span class="sxs-lookup"><span data-stu-id="95cb4-3306">DLS#</span></span> 
- <span data-ttu-id="95cb4-3307">采用</span><span class="sxs-lookup"><span data-stu-id="95cb4-3307">CDL#</span></span> 
- <span data-ttu-id="95cb4-3308">CDLS #</span><span class="sxs-lookup"><span data-stu-id="95cb4-3308">CDLS#</span></span> 
- <span data-ttu-id="95cb4-3309">号</span><span class="sxs-lookup"><span data-stu-id="95cb4-3309">ID#</span></span>
- <span data-ttu-id="95cb4-3310">id</span><span class="sxs-lookup"><span data-stu-id="95cb4-3310">IDs#</span></span> 
- <span data-ttu-id="95cb4-3311">ID number</span><span class="sxs-lookup"><span data-stu-id="95cb4-3311">ID number</span></span> 
- <span data-ttu-id="95cb4-3312">ID numbers</span><span class="sxs-lookup"><span data-stu-id="95cb4-3312">ID numbers</span></span> 
- <span data-ttu-id="95cb4-3313">.lic</span><span class="sxs-lookup"><span data-stu-id="95cb4-3313">LIC</span></span> 
- <span data-ttu-id="95cb4-3314">.lic</span><span class="sxs-lookup"><span data-stu-id="95cb4-3314">LIC#</span></span> 

#### <a name="keywordusdriverslicense"></a><span data-ttu-id="95cb4-3315">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="95cb4-3315">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="95cb4-3316">DriverLic</span><span class="sxs-lookup"><span data-stu-id="95cb4-3316">DriverLic</span></span> 
- <span data-ttu-id="95cb4-3317">DriverLics</span><span class="sxs-lookup"><span data-stu-id="95cb4-3317">DriverLics</span></span> 
- <span data-ttu-id="95cb4-3318">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="95cb4-3318">DriverLicense</span></span> 
- <span data-ttu-id="95cb4-3319">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="95cb4-3319">DriverLicenses</span></span> 
- <span data-ttu-id="95cb4-3320">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="95cb4-3320">Driver Lic</span></span> 
- <span data-ttu-id="95cb4-3321">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="95cb4-3321">Driver Lics</span></span> 
- <span data-ttu-id="95cb4-3322">Driver License</span><span class="sxs-lookup"><span data-stu-id="95cb4-3322">Driver License</span></span> 
- <span data-ttu-id="95cb4-3323">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="95cb4-3323">Driver Licenses</span></span> 
- <span data-ttu-id="95cb4-3324">DriversLic</span><span class="sxs-lookup"><span data-stu-id="95cb4-3324">DriversLic</span></span> 
- <span data-ttu-id="95cb4-3325">DriversLics</span><span class="sxs-lookup"><span data-stu-id="95cb4-3325">DriversLics</span></span> 
- <span data-ttu-id="95cb4-3326">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="95cb4-3326">DriversLicense</span></span> 
- <span data-ttu-id="95cb4-3327">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="95cb4-3327">DriversLicenses</span></span> 
- <span data-ttu-id="95cb4-3328">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="95cb4-3328">Drivers Lic</span></span> 
- <span data-ttu-id="95cb4-3329">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="95cb4-3329">Drivers Lics</span></span> 
- <span data-ttu-id="95cb4-3330">Drivers License</span><span class="sxs-lookup"><span data-stu-id="95cb4-3330">Drivers License</span></span> 
- <span data-ttu-id="95cb4-3331">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="95cb4-3331">Drivers Licenses</span></span> 
- <span data-ttu-id="95cb4-3332">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="95cb4-3332">Driver'Lic</span></span> 
- <span data-ttu-id="95cb4-3333">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="95cb4-3333">Driver'Lics</span></span> 
- <span data-ttu-id="95cb4-3334">Driver'License</span><span class="sxs-lookup"><span data-stu-id="95cb4-3334">Driver'License</span></span> 
- <span data-ttu-id="95cb4-3335">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="95cb4-3335">Driver'Licenses</span></span> 
- <span data-ttu-id="95cb4-3336">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="95cb4-3336">Driver' Lic</span></span> 
- <span data-ttu-id="95cb4-3337">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="95cb4-3337">Driver' Lics</span></span> 
- <span data-ttu-id="95cb4-3338">Driver' License</span><span class="sxs-lookup"><span data-stu-id="95cb4-3338">Driver' License</span></span> 
- <span data-ttu-id="95cb4-3339">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="95cb4-3339">Driver' Licenses</span></span>
- <span data-ttu-id="95cb4-3340">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="95cb4-3340">Driver'sLic</span></span> 
- <span data-ttu-id="95cb4-3341">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="95cb4-3341">Driver'sLics</span></span> 
- <span data-ttu-id="95cb4-3342">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="95cb4-3342">Driver'sLicense</span></span> 
- <span data-ttu-id="95cb4-3343">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="95cb4-3343">Driver'sLicenses</span></span> 
- <span data-ttu-id="95cb4-3344">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="95cb4-3344">Driver's Lic</span></span> 
- <span data-ttu-id="95cb4-3345">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="95cb4-3345">Driver's Lics</span></span> 
- <span data-ttu-id="95cb4-3346">Driver's License</span><span class="sxs-lookup"><span data-stu-id="95cb4-3346">Driver's License</span></span> 
- <span data-ttu-id="95cb4-3347">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="95cb4-3347">Driver's Licenses</span></span> 
- <span data-ttu-id="95cb4-3348">identification number</span><span class="sxs-lookup"><span data-stu-id="95cb4-3348">identification number</span></span> 
- <span data-ttu-id="95cb4-3349">identification numbers</span><span class="sxs-lookup"><span data-stu-id="95cb4-3349">identification numbers</span></span> 
- <span data-ttu-id="95cb4-3350">identification #</span><span class="sxs-lookup"><span data-stu-id="95cb4-3350">identification #</span></span> 
- <span data-ttu-id="95cb4-3351">id card</span><span class="sxs-lookup"><span data-stu-id="95cb4-3351">id card</span></span> 
- <span data-ttu-id="95cb4-3352">id cards</span><span class="sxs-lookup"><span data-stu-id="95cb4-3352">id cards</span></span> 
- <span data-ttu-id="95cb4-3353">identification card</span><span class="sxs-lookup"><span data-stu-id="95cb4-3353">identification card</span></span> 
- <span data-ttu-id="95cb4-3354">identification cards</span><span class="sxs-lookup"><span data-stu-id="95cb4-3354">identification cards</span></span> 
- <span data-ttu-id="95cb4-3355">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="95cb4-3355">DriverLic#</span></span> 
- <span data-ttu-id="95cb4-3356">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="95cb4-3356">DriverLics#</span></span> 
- <span data-ttu-id="95cb4-3357">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="95cb4-3357">DriverLicense#</span></span> 
- <span data-ttu-id="95cb4-3358">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="95cb4-3358">DriverLicenses#</span></span> 
- <span data-ttu-id="95cb4-3359">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="95cb4-3359">Driver Lic#</span></span> 
- <span data-ttu-id="95cb4-3360">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="95cb4-3360">Driver Lics#</span></span> 
- <span data-ttu-id="95cb4-3361">Driver License#</span><span class="sxs-lookup"><span data-stu-id="95cb4-3361">Driver License#</span></span> 
- <span data-ttu-id="95cb4-3362">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="95cb4-3362">Driver Licenses#</span></span> 
- <span data-ttu-id="95cb4-3363">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="95cb4-3363">DriversLic#</span></span> 
- <span data-ttu-id="95cb4-3364">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="95cb4-3364">DriversLics#</span></span> 
- <span data-ttu-id="95cb4-3365">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="95cb4-3365">DriversLicense#</span></span> 
- <span data-ttu-id="95cb4-3366">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="95cb4-3366">DriversLicenses#</span></span> 
- <span data-ttu-id="95cb4-3367">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="95cb4-3367">Drivers Lic#</span></span> 
- <span data-ttu-id="95cb4-3368">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="95cb4-3368">Drivers Lics#</span></span> 
- <span data-ttu-id="95cb4-3369">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="95cb4-3369">Drivers License#</span></span> 
- <span data-ttu-id="95cb4-3370">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="95cb4-3370">Drivers Licenses#</span></span> 
- <span data-ttu-id="95cb4-3371">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="95cb4-3371">Driver'Lic#</span></span> 
- <span data-ttu-id="95cb4-3372">Driver'Lics #</span><span class="sxs-lookup"><span data-stu-id="95cb4-3372">Driver'Lics#</span></span> 
- <span data-ttu-id="95cb4-3373">Driver'License #</span><span class="sxs-lookup"><span data-stu-id="95cb4-3373">Driver'License#</span></span> 
- <span data-ttu-id="95cb4-3374">Driver'Licenses #</span><span class="sxs-lookup"><span data-stu-id="95cb4-3374">Driver'Licenses#</span></span> 
- <span data-ttu-id="95cb4-3375">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="95cb4-3375">Driver' Lic#</span></span> 
- <span data-ttu-id="95cb4-3376">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="95cb4-3376">Driver' Lics#</span></span> 
- <span data-ttu-id="95cb4-3377">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="95cb4-3377">Driver' License#</span></span> 
- <span data-ttu-id="95cb4-3378">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="95cb4-3378">Driver' Licenses#</span></span> 
- <span data-ttu-id="95cb4-3379">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="95cb4-3379">Driver'sLic#</span></span> 
- <span data-ttu-id="95cb4-3380">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="95cb4-3380">Driver'sLics#</span></span> 
- <span data-ttu-id="95cb4-3381">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="95cb4-3381">Driver'sLicense#</span></span> 
- <span data-ttu-id="95cb4-3382">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="95cb4-3382">Driver'sLicenses#</span></span> 
- <span data-ttu-id="95cb4-3383">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="95cb4-3383">Driver's Lic#</span></span> 
- <span data-ttu-id="95cb4-3384">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="95cb4-3384">Driver's Lics#</span></span> 
- <span data-ttu-id="95cb4-3385">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="95cb4-3385">Driver's License#</span></span> 
- <span data-ttu-id="95cb4-3386">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="95cb4-3386">Driver's Licenses#</span></span> 
- <span data-ttu-id="95cb4-3387">id card#</span><span class="sxs-lookup"><span data-stu-id="95cb4-3387">id card#</span></span> 
- <span data-ttu-id="95cb4-3388">id cards#</span><span class="sxs-lookup"><span data-stu-id="95cb4-3388">id cards#</span></span> 
- <span data-ttu-id="95cb4-3389">identification card#</span><span class="sxs-lookup"><span data-stu-id="95cb4-3389">identification card#</span></span> 
- <span data-ttu-id="95cb4-3390">identification cards#</span><span class="sxs-lookup"><span data-stu-id="95cb4-3390">identification cards#</span></span> 


#### <a name="keywordstatenamedriverslicensename"></a><span data-ttu-id="95cb4-3391">Keyword_ [state_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="95cb4-3391">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="95cb4-3392">州缩写（例如，“NY”）</span><span class="sxs-lookup"><span data-stu-id="95cb4-3392">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="95cb4-3393">州名称（例如，“New York”）</span><span class="sxs-lookup"><span data-stu-id="95cb4-3393">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="95cb4-3394">美国单独的纳税人标识号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="95cb4-3394">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-3395">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-3395">Format</span></span>

<span data-ttu-id="95cb4-3396">九个数字，以“9”开头，“7”或“8”作为第四个数字，可以采用空格或短划线格式</span><span class="sxs-lookup"><span data-stu-id="95cb4-3396">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-3397">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-3397">Pattern</span></span>

<span data-ttu-id="95cb4-3398">格式</span><span class="sxs-lookup"><span data-stu-id="95cb4-3398">Formatted:</span></span>
- <span data-ttu-id="95cb4-3399">数字“9”</span><span class="sxs-lookup"><span data-stu-id="95cb4-3399">The digit "9"</span></span> 
- <span data-ttu-id="95cb4-3400">两位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3400">Two digits</span></span> 
- <span data-ttu-id="95cb4-3401">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="95cb4-3401">A space or dash</span></span> 
- <span data-ttu-id="95cb4-3402">“7”或“8”</span><span class="sxs-lookup"><span data-stu-id="95cb4-3402">A "7" or "8"</span></span> 
- <span data-ttu-id="95cb4-3403">一位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3403">A digit</span></span> 
- <span data-ttu-id="95cb4-3404">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="95cb4-3404">A space, or dash</span></span> 
- <span data-ttu-id="95cb4-3405">四位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3405">Four digits</span></span>

<span data-ttu-id="95cb4-3406">纯</span><span class="sxs-lookup"><span data-stu-id="95cb4-3406">Unformatted:</span></span>
- <span data-ttu-id="95cb4-3407">数字“9”</span><span class="sxs-lookup"><span data-stu-id="95cb4-3407">The digit "9"</span></span> 
- <span data-ttu-id="95cb4-3408">两位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3408">Two digits</span></span> 
- <span data-ttu-id="95cb4-3409">“7”或“8”</span><span class="sxs-lookup"><span data-stu-id="95cb4-3409">A "7" or "8"</span></span> 
- <span data-ttu-id="95cb4-3410">五位数字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3410">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-3411">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-3411">Checksum</span></span>

<span data-ttu-id="95cb4-3412">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-3412">No</span></span>

### <a name="definition"></a><span data-ttu-id="95cb4-3413">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-3413">Definition</span></span>

<span data-ttu-id="95cb4-3414">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-3414">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-3415">函数 Func_formatted_itin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3415">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-3416">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="95cb4-3416">At least one of the following is true:</span></span>
    - <span data-ttu-id="95cb4-3417">找到 Keyword_itin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3417">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="95cb4-3418">函数 Func_us_address 找到正确日期格式的地址。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3418">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="95cb4-3419">函数 Func_us_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3419">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="95cb4-3420">找到 Keyword_itin_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3420">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="95cb4-3421">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-3421">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-3422">函数 Func_unformatted_itin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3422">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-3423">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="95cb4-3423">At least one of the following is true:</span></span>
    - <span data-ttu-id="95cb4-3424">找到 Keyword_itin_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3424">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="95cb4-3425">函数 Func_us_address 找到正确日期格式的地址。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3425">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="95cb4-3426">函数 Func_us_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3426">The function Func_us_date finds a date in the right date format.</span></span>

```
<!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
<Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
          <Match idRef="Keyword_itin_collaborative" />
        </Any>
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin_collaborative" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-3427">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3427">Keywords</span></span>

#### <a name="keyworditin"></a><span data-ttu-id="95cb4-3428">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="95cb4-3428">Keyword_itin</span></span>

- <span data-ttu-id="95cb4-3429">报税</span><span class="sxs-lookup"><span data-stu-id="95cb4-3429">taxpayer</span></span> 
- <span data-ttu-id="95cb4-3430">tax id</span><span class="sxs-lookup"><span data-stu-id="95cb4-3430">tax id</span></span> 
- <span data-ttu-id="95cb4-3431">tax identification</span><span class="sxs-lookup"><span data-stu-id="95cb4-3431">tax identification</span></span> 
- <span data-ttu-id="95cb4-3432">itin</span><span class="sxs-lookup"><span data-stu-id="95cb4-3432">itin</span></span> 
- <span data-ttu-id="95cb4-3433">ssn</span><span class="sxs-lookup"><span data-stu-id="95cb4-3433">ssn</span></span> 
- <span data-ttu-id="95cb4-3434">锡</span><span class="sxs-lookup"><span data-stu-id="95cb4-3434">tin</span></span> 
- <span data-ttu-id="95cb4-3435">social security</span><span class="sxs-lookup"><span data-stu-id="95cb4-3435">social security</span></span> 
- <span data-ttu-id="95cb4-3436">tax payer</span><span class="sxs-lookup"><span data-stu-id="95cb4-3436">tax payer</span></span> 
- <span data-ttu-id="95cb4-3437">itins</span><span class="sxs-lookup"><span data-stu-id="95cb4-3437">itins</span></span> 
- <span data-ttu-id="95cb4-3438">taxid</span><span class="sxs-lookup"><span data-stu-id="95cb4-3438">taxid</span></span> 
- <span data-ttu-id="95cb4-3439">individual taxpayer</span><span class="sxs-lookup"><span data-stu-id="95cb4-3439">individual taxpayer</span></span> 

#### <a name="keyworditincollaborative"></a><span data-ttu-id="95cb4-3440">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="95cb4-3440">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="95cb4-3441">License</span><span class="sxs-lookup"><span data-stu-id="95cb4-3441">License</span></span> 
- <span data-ttu-id="95cb4-3442">通讯</span><span class="sxs-lookup"><span data-stu-id="95cb4-3442">DL</span></span> 
- <span data-ttu-id="95cb4-3443">DOB</span><span class="sxs-lookup"><span data-stu-id="95cb4-3443">DOB</span></span> 
- <span data-ttu-id="95cb4-3444">出生日期</span><span class="sxs-lookup"><span data-stu-id="95cb4-3444">Birthdate</span></span> 
- <span data-ttu-id="95cb4-3445">生日</span><span class="sxs-lookup"><span data-stu-id="95cb4-3445">Birthday</span></span> 
- <span data-ttu-id="95cb4-3446">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="95cb4-3446">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="95cb4-3447">美国社会保险号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="95cb4-3447">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="95cb4-3448">Format</span><span class="sxs-lookup"><span data-stu-id="95cb4-3448">Format</span></span>

<span data-ttu-id="95cb4-3449">9 个数字，可以是格式化模式，也可以是非格式化模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-3449">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="95cb4-3450">如果在 2011 年中旬前发布，则 SSN 具有强格式，即数字的某部分必须介于某个有效的范围中（但是没有校验和）。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3450">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="95cb4-3451">模式</span><span class="sxs-lookup"><span data-stu-id="95cb4-3451">Pattern</span></span>

<span data-ttu-id="95cb4-3452">四种不同模式中的 SSN 的四种函数外观：</span><span class="sxs-lookup"><span data-stu-id="95cb4-3452">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="95cb4-3453">Func_ssn 查找具有 2011 年以前使用短划线或空格格式化的强格式的 SSN（ddd-dd-dddd 或 ddd dd dddd）</span><span class="sxs-lookup"><span data-stu-id="95cb4-3453">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="95cb4-3454">Func_unformatted_ssn 查找具有 2011 年以前未格式化为 9 个连续数字的强格式的 SSN (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="95cb4-3454">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="95cb4-3455">Func_randomized_formatted_ssn 查找 2011 年后使用短划线或空格（ddd-dd-dddd 或 ddd dd dddd）格式化的 SSN</span><span class="sxs-lookup"><span data-stu-id="95cb4-3455">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="95cb4-3456">Func_randomized_unformatted_ssn 查找 2011 年后未格式化为 9 个连续数字 (ddddddddd) 的 SSN</span><span class="sxs-lookup"><span data-stu-id="95cb4-3456">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="95cb4-3457">校验和</span><span class="sxs-lookup"><span data-stu-id="95cb4-3457">Checksum</span></span>

<span data-ttu-id="95cb4-3458">否</span><span class="sxs-lookup"><span data-stu-id="95cb4-3458">No</span></span>


### <a name="definition"></a><span data-ttu-id="95cb4-3459">定义</span><span class="sxs-lookup"><span data-stu-id="95cb4-3459">Definition</span></span>

<span data-ttu-id="95cb4-3460">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-3460">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-3461">函数 Func_ssn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3461">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-3462">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3462">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="95cb4-3463">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-3463">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-3464">函数 Func_unformatted_ssn 查找与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3464">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-3465">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3465">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="95cb4-3466">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-3466">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-3467">函数 Func_randomized_formatted_ssn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3467">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-3468">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3468">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="95cb4-3469">函数 Func_ssn 未找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3469">The function Func_ssn does not find content that matches the pattern.</span></span>

<span data-ttu-id="95cb4-3470">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 55% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="95cb4-3470">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="95cb4-3471">函数 Func_randomized_unformatted_ssn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3471">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="95cb4-3472">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3472">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="95cb4-3473">函数 Func_unformatted_ssn 未找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="95cb4-3473">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>

```
<!-- U.S. Social Security Number (SSN) -->
    <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Match idRef="Keyword_ssn" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Func_ssn" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Func_unformatted_ssn" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cb4-3474">关键字</span><span class="sxs-lookup"><span data-stu-id="95cb4-3474">Keywords</span></span>

#### <a name="keywordssn"></a><span data-ttu-id="95cb4-3475">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="95cb4-3475">Keyword_ssn</span></span>

- <span data-ttu-id="95cb4-3476">Social Security</span><span class="sxs-lookup"><span data-stu-id="95cb4-3476">Social Security</span></span> 
- <span data-ttu-id="95cb4-3477">Social Security#</span><span class="sxs-lookup"><span data-stu-id="95cb4-3477">Social Security#</span></span> 
- <span data-ttu-id="95cb4-3478">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="95cb4-3478">Soc Sec</span></span> 
- <span data-ttu-id="95cb4-3479">SSN</span><span class="sxs-lookup"><span data-stu-id="95cb4-3479">SSN</span></span> 
- <span data-ttu-id="95cb4-3480">ssn</span><span class="sxs-lookup"><span data-stu-id="95cb4-3480">SSNS</span></span> 
- <span data-ttu-id="95cb4-3481">SSN</span><span class="sxs-lookup"><span data-stu-id="95cb4-3481">SSN#</span></span> 
- <span data-ttu-id="95cb4-3482">SS</span><span class="sxs-lookup"><span data-stu-id="95cb4-3482">SS#</span></span> 
- <span data-ttu-id="95cb4-3483">SSID</span><span class="sxs-lookup"><span data-stu-id="95cb4-3483">SSID</span></span> 
   

