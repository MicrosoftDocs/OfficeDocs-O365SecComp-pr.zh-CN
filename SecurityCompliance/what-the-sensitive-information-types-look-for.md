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
ms.openlocfilehash: e9811b285e98a791570dc91e275cb5cead4f8bc9
ms.sourcegitcommit: 6e8e2b43a4bea31c1e835c5b050824651c6a0094
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2019
ms.locfileid: "30537639"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="888cb-104">使用敏感信息类型查找什么</span><span class="sxs-lookup"><span data-stu-id="888cb-104">What the sensitive information types look for</span></span>

<span data-ttu-id="888cb-105">Office 365 安全&amp;合规中心中的数据丢失防护 (DLP) 包括许多可供您在 DLP 策略中使用的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="888cb-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="888cb-106">本主题列出了所有这些敏感信息类型，并显示 DLP 策略在检测到每种类型时查找的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="888cb-107">敏感信息类型通过正则表达式或函数可以识别的模式定义。</span><span class="sxs-lookup"><span data-stu-id="888cb-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="888cb-108">此外，关键字和校验和等确凿的证据可用于识别敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="888cb-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="888cb-109">可信度和相似度也会在评估过程中使用。</span><span class="sxs-lookup"><span data-stu-id="888cb-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="888cb-110">ABA 银行代号</span><span class="sxs-lookup"><span data-stu-id="888cb-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-111">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-111">Format</span></span>

<span data-ttu-id="888cb-112">9 个数字，可以是格式化模式，也可以是非格式化模式 </span><span class="sxs-lookup"><span data-stu-id="888cb-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-113">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-113">Pattern</span></span>

<span data-ttu-id="888cb-114">格式</span><span class="sxs-lookup"><span data-stu-id="888cb-114">Formatted:</span></span>
- <span data-ttu-id="888cb-115">四个数字，以 0、 1、 2、 3、 6、 7 或 8 开头</span><span class="sxs-lookup"><span data-stu-id="888cb-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="888cb-116">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="888cb-116">A hyphen</span></span>
- <span data-ttu-id="888cb-117">四个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-117">Four digits</span></span>
- <span data-ttu-id="888cb-118">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="888cb-118">A hyphen</span></span>
- <span data-ttu-id="888cb-119">一个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-119">A digit</span></span>

<span data-ttu-id="888cb-120">无格式: 9 个连续的数字, 以0、1、2、3、6、7或8开头</span><span class="sxs-lookup"><span data-stu-id="888cb-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="888cb-121">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-121">Checksum</span></span>

<span data-ttu-id="888cb-122">否</span><span class="sxs-lookup"><span data-stu-id="888cb-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-123">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-123">Definition</span></span>

<span data-ttu-id="888cb-124">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-125">函数 Func_aba_routing 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-126">找到 Keyword_ABA_Routing 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="888cb-127">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-127">Keywords</span></span>

#### <a name="keywordabarouting"></a><span data-ttu-id="888cb-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="888cb-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="888cb-129">aba</span><span class="sxs-lookup"><span data-stu-id="888cb-129">aba</span></span>
- <span data-ttu-id="888cb-130">aba #</span><span class="sxs-lookup"><span data-stu-id="888cb-130">aba #</span></span>
- <span data-ttu-id="888cb-131">aba routing #</span><span class="sxs-lookup"><span data-stu-id="888cb-131">aba routing #</span></span>
- <span data-ttu-id="888cb-132">aba routing number</span><span class="sxs-lookup"><span data-stu-id="888cb-132">aba routing number</span></span>
- <span data-ttu-id="888cb-133">aba</span><span class="sxs-lookup"><span data-stu-id="888cb-133">aba#</span></span>
- <span data-ttu-id="888cb-134">abarouting #</span><span class="sxs-lookup"><span data-stu-id="888cb-134">abarouting#</span></span>
- <span data-ttu-id="888cb-135">aba number</span><span class="sxs-lookup"><span data-stu-id="888cb-135">aba number</span></span>
- <span data-ttu-id="888cb-136">abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="888cb-136">abaroutingnumber</span></span>
- <span data-ttu-id="888cb-137">american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="888cb-137">american bank association routing #</span></span>
- <span data-ttu-id="888cb-138">american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="888cb-138">american bank association routing number</span></span>
- <span data-ttu-id="888cb-139">americanbankassociationrouting #</span><span class="sxs-lookup"><span data-stu-id="888cb-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="888cb-140">americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="888cb-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="888cb-141">bank routing number</span><span class="sxs-lookup"><span data-stu-id="888cb-141">bank routing number</span></span>
- <span data-ttu-id="888cb-142">bankrouting #</span><span class="sxs-lookup"><span data-stu-id="888cb-142">bankrouting#</span></span>
- <span data-ttu-id="888cb-143">bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="888cb-143">bankroutingnumber</span></span>
- <span data-ttu-id="888cb-144">routing transit number</span><span class="sxs-lookup"><span data-stu-id="888cb-144">routing transit number</span></span>
- <span data-ttu-id="888cb-145">RTN</span><span class="sxs-lookup"><span data-stu-id="888cb-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="888cb-146">阿根廷国家身份证 (DNI) 号</span><span class="sxs-lookup"><span data-stu-id="888cb-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-147">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-147">Format</span></span>

<span data-ttu-id="888cb-148">八个数字，用点分隔</span><span class="sxs-lookup"><span data-stu-id="888cb-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-149">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-149">Pattern</span></span>

<span data-ttu-id="888cb-150">八个数字：</span><span class="sxs-lookup"><span data-stu-id="888cb-150">Eight digits:</span></span>
- <span data-ttu-id="888cb-151">两个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-151">Two digits</span></span>
- <span data-ttu-id="888cb-152">一个点 </span><span class="sxs-lookup"><span data-stu-id="888cb-152">A period</span></span>
- <span data-ttu-id="888cb-153">三个数字 </span><span class="sxs-lookup"><span data-stu-id="888cb-153">Three digits</span></span>
- <span data-ttu-id="888cb-154">一个点 </span><span class="sxs-lookup"><span data-stu-id="888cb-154">A period</span></span>
- <span data-ttu-id="888cb-155">三位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-156">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-156">Checksum</span></span>

<span data-ttu-id="888cb-157">否</span><span class="sxs-lookup"><span data-stu-id="888cb-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-158">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-158">Definition</span></span>

<span data-ttu-id="888cb-159">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-160">正则表达式 Regex_argentina_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-161">找到 Keyword_argentina_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-162">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-162">Keywords</span></span>

#### <a name="keywordargentinanationalid"></a><span data-ttu-id="888cb-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="888cb-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="888cb-164">Argentina National Identity number</span><span class="sxs-lookup"><span data-stu-id="888cb-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="888cb-165">标识</span><span class="sxs-lookup"><span data-stu-id="888cb-165">Identity</span></span> 
- <span data-ttu-id="888cb-166">标识国家/地区身份卡片</span><span class="sxs-lookup"><span data-stu-id="888cb-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="888cb-167">DNI</span><span class="sxs-lookup"><span data-stu-id="888cb-167">DNI</span></span> 
- <span data-ttu-id="888cb-168">个人的网络国家注册表</span><span class="sxs-lookup"><span data-stu-id="888cb-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="888cb-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="888cb-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="888cb-170">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="888cb-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="888cb-171">Identidad</span><span class="sxs-lookup"><span data-stu-id="888cb-171">Identidad</span></span> 
- <span data-ttu-id="888cb-172">Identificación</span><span class="sxs-lookup"><span data-stu-id="888cb-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="888cb-173">澳大利亚银行帐号</span><span class="sxs-lookup"><span data-stu-id="888cb-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-174">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-174">Format</span></span>

<span data-ttu-id="888cb-175">6-10 个数字，带或不带 BSB 号码 </span><span class="sxs-lookup"><span data-stu-id="888cb-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-176">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-176">Pattern</span></span>

<span data-ttu-id="888cb-177">帐号为 6-10 个数字。</span><span class="sxs-lookup"><span data-stu-id="888cb-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="888cb-178">澳大利亚银行州级分部编号：</span><span class="sxs-lookup"><span data-stu-id="888cb-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="888cb-179">三个数字 </span><span class="sxs-lookup"><span data-stu-id="888cb-179">Three digits</span></span> 
- <span data-ttu-id="888cb-180">连字符</span><span class="sxs-lookup"><span data-stu-id="888cb-180">A hyphen</span></span> 
- <span data-ttu-id="888cb-181">三位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-182">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-182">Checksum</span></span>

<span data-ttu-id="888cb-183">否</span><span class="sxs-lookup"><span data-stu-id="888cb-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-184">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-184">Definition</span></span>

<span data-ttu-id="888cb-185">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-186">正则表达式 Regex_australia_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="888cb-187">找到 Keyword_australia_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="888cb-188">正则表达式 Regex_australia_bank_account_number_bsb 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="888cb-189">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-190">正则表达式 Regex_australia_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="888cb-191">找到 Keyword_australia_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-192">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-192">Keywords</span></span>

#### <a name="keywordaustraliabankaccountnumber"></a><span data-ttu-id="888cb-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="888cb-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="888cb-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="888cb-194">swift bank code</span></span>
- <span data-ttu-id="888cb-195">correspondent bank</span><span class="sxs-lookup"><span data-stu-id="888cb-195">correspondent bank</span></span>
- <span data-ttu-id="888cb-196">base currency</span><span class="sxs-lookup"><span data-stu-id="888cb-196">base currency</span></span>
- <span data-ttu-id="888cb-197">usa account</span><span class="sxs-lookup"><span data-stu-id="888cb-197">usa account</span></span>
- <span data-ttu-id="888cb-198">holder address</span><span class="sxs-lookup"><span data-stu-id="888cb-198">holder address</span></span>
- <span data-ttu-id="888cb-199">bank address</span><span class="sxs-lookup"><span data-stu-id="888cb-199">bank address</span></span>
- <span data-ttu-id="888cb-200">information account</span><span class="sxs-lookup"><span data-stu-id="888cb-200">information account</span></span>
- <span data-ttu-id="888cb-201">fund transfers</span><span class="sxs-lookup"><span data-stu-id="888cb-201">fund transfers</span></span>
- <span data-ttu-id="888cb-202">bank charges</span><span class="sxs-lookup"><span data-stu-id="888cb-202">bank charges</span></span>
- <span data-ttu-id="888cb-203">bank details</span><span class="sxs-lookup"><span data-stu-id="888cb-203">bank details</span></span>
- <span data-ttu-id="888cb-204">banking information</span><span class="sxs-lookup"><span data-stu-id="888cb-204">banking information</span></span>
- <span data-ttu-id="888cb-205">full names</span><span class="sxs-lookup"><span data-stu-id="888cb-205">full names</span></span>
- <span data-ttu-id="888cb-206">iaea</span><span class="sxs-lookup"><span data-stu-id="888cb-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="888cb-207">澳大利亚驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="888cb-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-208">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-208">Format</span></span>

<span data-ttu-id="888cb-209">九个字母和数字</span><span class="sxs-lookup"><span data-stu-id="888cb-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-210">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-210">Pattern</span></span>

<span data-ttu-id="888cb-211">九个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="888cb-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="888cb-212">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="888cb-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="888cb-213">两位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-213">Two digits</span></span> 
- <span data-ttu-id="888cb-214">五位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="888cb-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="888cb-215">OR</span><span class="sxs-lookup"><span data-stu-id="888cb-215">OR</span></span>

- <span data-ttu-id="888cb-216">1-2 个可选字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="888cb-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="888cb-217">4-9 位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-217">4-9 digits</span></span>

<span data-ttu-id="888cb-218">OR</span><span class="sxs-lookup"><span data-stu-id="888cb-218">OR</span></span>

- <span data-ttu-id="888cb-219">九个数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="888cb-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-220">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-220">Checksum</span></span>

<span data-ttu-id="888cb-221">否</span><span class="sxs-lookup"><span data-stu-id="888cb-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-222">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-222">Definition</span></span>

<span data-ttu-id="888cb-223">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-224">正则表达式 Regex_australia_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-225">找到 Keyword_australia_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="888cb-226">未找到 Keyword_australia_drivers_license_number_exclusions 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-227">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-227">Keywords</span></span>

#### <a name="keywordaustraliadriverslicensenumber"></a><span data-ttu-id="888cb-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="888cb-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="888cb-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="888cb-229">international driving permits</span></span>
- <span data-ttu-id="888cb-230">australian automobile association</span><span class="sxs-lookup"><span data-stu-id="888cb-230">australian automobile association</span></span>
- <span data-ttu-id="888cb-231">international driving permit</span><span class="sxs-lookup"><span data-stu-id="888cb-231">international driving permit</span></span>
- <span data-ttu-id="888cb-232">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="888cb-232">DriverLicence</span></span>
- <span data-ttu-id="888cb-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="888cb-233">DriverLicences</span></span>
- <span data-ttu-id="888cb-234">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="888cb-234">Driver Lic</span></span>
- <span data-ttu-id="888cb-235">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="888cb-235">Driver Licence</span></span>
- <span data-ttu-id="888cb-236">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="888cb-236">Driver Licences</span></span>
- <span data-ttu-id="888cb-237">DriversLic</span><span class="sxs-lookup"><span data-stu-id="888cb-237">DriversLic</span></span>
- <span data-ttu-id="888cb-238">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="888cb-238">DriversLicence</span></span>
- <span data-ttu-id="888cb-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="888cb-239">DriversLicences</span></span>
- <span data-ttu-id="888cb-240">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="888cb-240">Drivers Lic</span></span>
- <span data-ttu-id="888cb-241">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="888cb-241">Drivers Lics</span></span>
- <span data-ttu-id="888cb-242">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="888cb-242">Drivers Licence</span></span>
- <span data-ttu-id="888cb-243">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="888cb-243">Drivers Licences</span></span>
- <span data-ttu-id="888cb-244">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="888cb-244">Driver'Lic</span></span>
- <span data-ttu-id="888cb-245">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="888cb-245">Driver'Lics</span></span>
- <span data-ttu-id="888cb-246">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="888cb-246">Driver'Licence</span></span>
- <span data-ttu-id="888cb-247">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="888cb-247">Driver'Licences</span></span>
- <span data-ttu-id="888cb-248">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="888cb-248">Driver' Lic</span></span>
- <span data-ttu-id="888cb-249">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="888cb-249">Driver' Lics</span></span>
- <span data-ttu-id="888cb-250">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="888cb-250">Driver' Licence</span></span>
- <span data-ttu-id="888cb-251">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="888cb-251">Driver' Licences</span></span>
- <span data-ttu-id="888cb-252">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="888cb-252">Driver'sLic</span></span>
- <span data-ttu-id="888cb-253">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="888cb-253">Driver'sLics</span></span>
- <span data-ttu-id="888cb-254">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="888cb-254">Driver'sLicence</span></span>
- <span data-ttu-id="888cb-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="888cb-255">Driver'sLicences</span></span>
- <span data-ttu-id="888cb-256">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="888cb-256">Driver's Lic</span></span>
- <span data-ttu-id="888cb-257">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="888cb-257">Driver's Lics</span></span>
- <span data-ttu-id="888cb-258">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="888cb-258">Driver's Licence</span></span>
- <span data-ttu-id="888cb-259">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="888cb-259">Driver's Licences</span></span>
- <span data-ttu-id="888cb-260">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="888cb-260">DriverLic#</span></span>
- <span data-ttu-id="888cb-261">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="888cb-261">DriverLics#</span></span>
- <span data-ttu-id="888cb-262">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="888cb-262">DriverLicence#</span></span>
- <span data-ttu-id="888cb-263">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="888cb-263">DriverLicences#</span></span>
- <span data-ttu-id="888cb-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="888cb-264">Driver Lic#</span></span>
- <span data-ttu-id="888cb-265">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="888cb-265">Driver Lics#</span></span>
- <span data-ttu-id="888cb-266">Driver Licence#</span><span class="sxs-lookup"><span data-stu-id="888cb-266">Driver Licence#</span></span>
- <span data-ttu-id="888cb-267">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="888cb-267">Driver Licences#</span></span>
- <span data-ttu-id="888cb-268">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="888cb-268">DriversLic#</span></span>
- <span data-ttu-id="888cb-269">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="888cb-269">DriversLics#</span></span>
- <span data-ttu-id="888cb-270">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="888cb-270">DriversLicence#</span></span>
- <span data-ttu-id="888cb-271">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="888cb-271">DriversLicences#</span></span>
- <span data-ttu-id="888cb-272">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="888cb-272">Drivers Lic#</span></span>
- <span data-ttu-id="888cb-273">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="888cb-273">Drivers Lics#</span></span>
- <span data-ttu-id="888cb-274">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="888cb-274">Drivers Licence#</span></span>
- <span data-ttu-id="888cb-275">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="888cb-275">Drivers Licences#</span></span>
- <span data-ttu-id="888cb-276">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="888cb-276">Driver'Lic#</span></span>
- <span data-ttu-id="888cb-277">Driver'Lics #</span><span class="sxs-lookup"><span data-stu-id="888cb-277">Driver'Lics#</span></span>
- <span data-ttu-id="888cb-278">Driver'Licence #</span><span class="sxs-lookup"><span data-stu-id="888cb-278">Driver'Licence#</span></span>
- <span data-ttu-id="888cb-279">Driver'Licences #</span><span class="sxs-lookup"><span data-stu-id="888cb-279">Driver'Licences#</span></span>
- <span data-ttu-id="888cb-280">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="888cb-280">Driver' Lic#</span></span>
- <span data-ttu-id="888cb-281">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="888cb-281">Driver' Lics#</span></span>
- <span data-ttu-id="888cb-282">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="888cb-282">Driver' Licence#</span></span>
- <span data-ttu-id="888cb-283">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="888cb-283">Driver' Licences#</span></span>
- <span data-ttu-id="888cb-284">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="888cb-284">Driver'sLic#</span></span>
- <span data-ttu-id="888cb-285">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="888cb-285">Driver'sLics#</span></span>
- <span data-ttu-id="888cb-286">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="888cb-286">Driver'sLicence#</span></span>
- <span data-ttu-id="888cb-287">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="888cb-287">Driver'sLicences#</span></span>
- <span data-ttu-id="888cb-288">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="888cb-288">Driver's Lic#</span></span>
- <span data-ttu-id="888cb-289">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="888cb-289">Driver's Lics#</span></span>
- <span data-ttu-id="888cb-290">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="888cb-290">Driver's Licence#</span></span>
- <span data-ttu-id="888cb-291">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="888cb-291">Driver's Licences#</span></span> 

#### <a name="keywordaustraliadriverslicensenumberexclusions"></a><span data-ttu-id="888cb-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="888cb-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="888cb-293">aaa</span><span class="sxs-lookup"><span data-stu-id="888cb-293">aaa</span></span>
- <span data-ttu-id="888cb-294">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="888cb-294">DriverLicense</span></span>
- <span data-ttu-id="888cb-295">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="888cb-295">DriverLicenses</span></span>
- <span data-ttu-id="888cb-296">Driver License</span><span class="sxs-lookup"><span data-stu-id="888cb-296">Driver License</span></span>
- <span data-ttu-id="888cb-297">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="888cb-297">Driver Licenses</span></span>
- <span data-ttu-id="888cb-298">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="888cb-298">DriversLicense</span></span>
- <span data-ttu-id="888cb-299">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="888cb-299">DriversLicenses</span></span>
- <span data-ttu-id="888cb-300">Drivers License</span><span class="sxs-lookup"><span data-stu-id="888cb-300">Drivers License</span></span>
- <span data-ttu-id="888cb-301">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="888cb-301">Drivers Licenses</span></span>
- <span data-ttu-id="888cb-302">Driver'License</span><span class="sxs-lookup"><span data-stu-id="888cb-302">Driver'License</span></span>
- <span data-ttu-id="888cb-303">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="888cb-303">Driver'Licenses</span></span>
- <span data-ttu-id="888cb-304">Driver' License</span><span class="sxs-lookup"><span data-stu-id="888cb-304">Driver' License</span></span>
- <span data-ttu-id="888cb-305">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="888cb-305">Driver' Licenses</span></span>
- <span data-ttu-id="888cb-306">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="888cb-306">Driver'sLicense</span></span>
- <span data-ttu-id="888cb-307">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="888cb-307">Driver'sLicenses</span></span>
- <span data-ttu-id="888cb-308">Driver's License</span><span class="sxs-lookup"><span data-stu-id="888cb-308">Driver's License</span></span>
- <span data-ttu-id="888cb-309">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="888cb-309">Driver's Licenses</span></span>
- <span data-ttu-id="888cb-310">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="888cb-310">DriverLicense#</span></span>
- <span data-ttu-id="888cb-311">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="888cb-311">DriverLicenses#</span></span>
- <span data-ttu-id="888cb-312">Driver License#</span><span class="sxs-lookup"><span data-stu-id="888cb-312">Driver License#</span></span>
- <span data-ttu-id="888cb-313">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="888cb-313">Driver Licenses#</span></span>
- <span data-ttu-id="888cb-314">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="888cb-314">DriversLicense#</span></span>
- <span data-ttu-id="888cb-315">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="888cb-315">DriversLicenses#</span></span>
- <span data-ttu-id="888cb-316">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="888cb-316">Drivers License#</span></span>
- <span data-ttu-id="888cb-317">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="888cb-317">Drivers Licenses#</span></span>
- <span data-ttu-id="888cb-318">Driver'License #</span><span class="sxs-lookup"><span data-stu-id="888cb-318">Driver'License#</span></span>
- <span data-ttu-id="888cb-319">Driver'Licenses #</span><span class="sxs-lookup"><span data-stu-id="888cb-319">Driver'Licenses#</span></span>
- <span data-ttu-id="888cb-320">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="888cb-320">Driver' License#</span></span>
- <span data-ttu-id="888cb-321">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="888cb-321">Driver' Licenses#</span></span>
- <span data-ttu-id="888cb-322">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="888cb-322">Driver'sLicense#</span></span>
- <span data-ttu-id="888cb-323">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="888cb-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="888cb-324">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="888cb-324">Driver's License#</span></span>
- <span data-ttu-id="888cb-325">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="888cb-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="888cb-326">澳大利亚医疗帐号</span><span class="sxs-lookup"><span data-stu-id="888cb-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-327">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-327">Format</span></span>

<span data-ttu-id="888cb-328">10-11 个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-329">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-329">Pattern</span></span>

<span data-ttu-id="888cb-330">10-11 个数字：</span><span class="sxs-lookup"><span data-stu-id="888cb-330">10-11 digits:</span></span>
- <span data-ttu-id="888cb-331">第一个数字范围为 2-6</span><span class="sxs-lookup"><span data-stu-id="888cb-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="888cb-332">第九个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="888cb-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="888cb-333">第十个数字是问题数字</span><span class="sxs-lookup"><span data-stu-id="888cb-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="888cb-334">第十一个数字（可选）是个人号码</span><span class="sxs-lookup"><span data-stu-id="888cb-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-335">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-335">Checksum</span></span>

<span data-ttu-id="888cb-336">是</span><span class="sxs-lookup"><span data-stu-id="888cb-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-337">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-337">Definition</span></span>

<span data-ttu-id="888cb-338">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-339">函数 Func_australian_medical_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-340">找到 Keyword_Australia_Medical_Account_Number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="888cb-341">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-341">The checksum passes.</span></span>

<span data-ttu-id="888cb-342">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-343">函数 Func_australian_medical_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-344">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-344">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-345">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-345">Keywords</span></span>

#### <a name="keywordaustraliamedicalaccountnumber"></a><span data-ttu-id="888cb-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="888cb-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="888cb-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="888cb-347">bank account details</span></span>
- <span data-ttu-id="888cb-348">medicare payments</span><span class="sxs-lookup"><span data-stu-id="888cb-348">medicare payments</span></span>
- <span data-ttu-id="888cb-349">mortgage account</span><span class="sxs-lookup"><span data-stu-id="888cb-349">mortgage account</span></span>
- <span data-ttu-id="888cb-350">bank payments</span><span class="sxs-lookup"><span data-stu-id="888cb-350">bank payments</span></span>
- <span data-ttu-id="888cb-351">information branch</span><span class="sxs-lookup"><span data-stu-id="888cb-351">information branch</span></span>
- <span data-ttu-id="888cb-352">credit card loan</span><span class="sxs-lookup"><span data-stu-id="888cb-352">credit card loan</span></span>
- <span data-ttu-id="888cb-353">department of human services</span><span class="sxs-lookup"><span data-stu-id="888cb-353">department of human services</span></span>
- <span data-ttu-id="888cb-354">local service</span><span class="sxs-lookup"><span data-stu-id="888cb-354">local service</span></span>
- <span data-ttu-id="888cb-355">medicare</span><span class="sxs-lookup"><span data-stu-id="888cb-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="888cb-356">澳大利亚护照号</span><span class="sxs-lookup"><span data-stu-id="888cb-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-357">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-357">Format</span></span>

<span data-ttu-id="888cb-358">一个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-359">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-359">Pattern</span></span>

<span data-ttu-id="888cb-360">一个字母（不区分大小写）后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-361">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-361">Checksum</span></span>

<span data-ttu-id="888cb-362">否</span><span class="sxs-lookup"><span data-stu-id="888cb-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-363">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-363">Definition</span></span>

<span data-ttu-id="888cb-364">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-365">正则表达式 Regex_australia_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-366">找到来自 Keyword_passport 或 Keyword_australia_passport_number 的关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-367">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-367">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="888cb-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="888cb-368">Keyword_passport</span></span>

- <span data-ttu-id="888cb-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="888cb-369">Passport Number</span></span>
- <span data-ttu-id="888cb-370">Passport No</span><span class="sxs-lookup"><span data-stu-id="888cb-370">Passport No</span></span>
- <span data-ttu-id="888cb-371">Passport #</span><span class="sxs-lookup"><span data-stu-id="888cb-371">Passport #</span></span>
- <span data-ttu-id="888cb-372">登记卡</span><span class="sxs-lookup"><span data-stu-id="888cb-372">Passport#</span></span>
- <span data-ttu-id="888cb-373">PassportID</span><span class="sxs-lookup"><span data-stu-id="888cb-373">PassportID</span></span>
- <span data-ttu-id="888cb-374">Passportno</span><span class="sxs-lookup"><span data-stu-id="888cb-374">Passportno</span></span>
- <span data-ttu-id="888cb-375">passportnumber</span><span class="sxs-lookup"><span data-stu-id="888cb-375">passportnumber</span></span>
- <span data-ttu-id="888cb-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="888cb-376">パスポート</span></span>
- <span data-ttu-id="888cb-377">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="888cb-377">パスポート番号</span></span>
- <span data-ttu-id="888cb-378">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="888cb-378">パスポートのNum</span></span>
- <span data-ttu-id="888cb-379">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="888cb-379">パスポート ＃</span></span> 
- <span data-ttu-id="888cb-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="888cb-380">Numéro de passeport</span></span>
- <span data-ttu-id="888cb-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="888cb-381">Passeport n °</span></span>
- <span data-ttu-id="888cb-382">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="888cb-382">Passeport Non</span></span>
- <span data-ttu-id="888cb-383">Passeport #</span><span class="sxs-lookup"><span data-stu-id="888cb-383">Passeport #</span></span>
- <span data-ttu-id="888cb-384">Passeport #</span><span class="sxs-lookup"><span data-stu-id="888cb-384">Passeport#</span></span>
- <span data-ttu-id="888cb-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="888cb-385">PasseportNon</span></span>
- <span data-ttu-id="888cb-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="888cb-386">Passeportn °</span></span>

#### <a name="keywordaustraliapassportnumber"></a><span data-ttu-id="888cb-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="888cb-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="888cb-388">登记卡</span><span class="sxs-lookup"><span data-stu-id="888cb-388">passport</span></span>
- <span data-ttu-id="888cb-389">passport details</span><span class="sxs-lookup"><span data-stu-id="888cb-389">passport details</span></span>
- <span data-ttu-id="888cb-390">immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="888cb-390">immigration and citizenship</span></span>
- <span data-ttu-id="888cb-391">commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="888cb-391">commonwealth of australia</span></span>
- <span data-ttu-id="888cb-392">department of immigration</span><span class="sxs-lookup"><span data-stu-id="888cb-392">department of immigration</span></span>
- <span data-ttu-id="888cb-393">residential address</span><span class="sxs-lookup"><span data-stu-id="888cb-393">residential address</span></span>
- <span data-ttu-id="888cb-394">department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="888cb-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="888cb-395">反之</span><span class="sxs-lookup"><span data-stu-id="888cb-395">visa</span></span>
- <span data-ttu-id="888cb-396">national identity card</span><span class="sxs-lookup"><span data-stu-id="888cb-396">national identity card</span></span>
- <span data-ttu-id="888cb-397">passport number</span><span class="sxs-lookup"><span data-stu-id="888cb-397">passport number</span></span>
- <span data-ttu-id="888cb-398">travel document</span><span class="sxs-lookup"><span data-stu-id="888cb-398">travel document</span></span>
- <span data-ttu-id="888cb-399">issuing authority</span><span class="sxs-lookup"><span data-stu-id="888cb-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="888cb-400">澳大利亚税号</span><span class="sxs-lookup"><span data-stu-id="888cb-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-401">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-401">Format</span></span>

<span data-ttu-id="888cb-402">8-9 个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-403">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-403">Pattern</span></span>

<span data-ttu-id="888cb-404">通常 8-9 位数字，显示中包含空格，如下所示：</span><span class="sxs-lookup"><span data-stu-id="888cb-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="888cb-405">三位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-405">Three digits</span></span> 
- <span data-ttu-id="888cb-406">可选空格</span><span class="sxs-lookup"><span data-stu-id="888cb-406">An optional space</span></span> 
- <span data-ttu-id="888cb-407">三位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-407">Three digits</span></span> 
- <span data-ttu-id="888cb-408">可选空格</span><span class="sxs-lookup"><span data-stu-id="888cb-408">An optional space</span></span> 
- <span data-ttu-id="888cb-409">2-3 位数字，最后一位数字是校验位</span><span class="sxs-lookup"><span data-stu-id="888cb-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-410">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-410">Checksum</span></span>

<span data-ttu-id="888cb-411">是</span><span class="sxs-lookup"><span data-stu-id="888cb-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-412">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-412">Definition</span></span>

<span data-ttu-id="888cb-413">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-414">函数 Func_australian_tax_file_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-415">未找到 Keyword_Australia_Tax_File_Number 或 Keyword_number_exclusions 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="888cb-416">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-416">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-417">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-417">Keywords</span></span>

#### <a name="keywordaustraliataxfilenumber"></a><span data-ttu-id="888cb-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="888cb-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="888cb-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="888cb-419">australian business number</span></span>
- <span data-ttu-id="888cb-420">marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="888cb-420">marginal tax rate</span></span>
- <span data-ttu-id="888cb-421">medicare levy</span><span class="sxs-lookup"><span data-stu-id="888cb-421">medicare levy</span></span>
- <span data-ttu-id="888cb-422">portfolio number</span><span class="sxs-lookup"><span data-stu-id="888cb-422">portfolio number</span></span>
- <span data-ttu-id="888cb-423">service veterans</span><span class="sxs-lookup"><span data-stu-id="888cb-423">service veterans</span></span>
- <span data-ttu-id="888cb-424">withholding tax</span><span class="sxs-lookup"><span data-stu-id="888cb-424">withholding tax</span></span>
- <span data-ttu-id="888cb-425">individual tax return</span><span class="sxs-lookup"><span data-stu-id="888cb-425">individual tax return</span></span>
- <span data-ttu-id="888cb-426">tax file number</span><span class="sxs-lookup"><span data-stu-id="888cb-426">tax file number</span></span>

#### <a name="keywordnumberexclusions"></a><span data-ttu-id="888cb-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="888cb-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="888cb-428">00000000</span><span class="sxs-lookup"><span data-stu-id="888cb-428">00000000</span></span>
- <span data-ttu-id="888cb-429">11111111</span><span class="sxs-lookup"><span data-stu-id="888cb-429">11111111</span></span>
- <span data-ttu-id="888cb-430">22222222</span><span class="sxs-lookup"><span data-stu-id="888cb-430">22222222</span></span>
- <span data-ttu-id="888cb-431">33333333</span><span class="sxs-lookup"><span data-stu-id="888cb-431">33333333</span></span>
- <span data-ttu-id="888cb-432">44444444</span><span class="sxs-lookup"><span data-stu-id="888cb-432">44444444</span></span>
- <span data-ttu-id="888cb-433">55555555</span><span class="sxs-lookup"><span data-stu-id="888cb-433">55555555</span></span>
- <span data-ttu-id="888cb-434">66666666</span><span class="sxs-lookup"><span data-stu-id="888cb-434">66666666</span></span>
- <span data-ttu-id="888cb-435">77777777</span><span class="sxs-lookup"><span data-stu-id="888cb-435">77777777</span></span>
- <span data-ttu-id="888cb-436">88888888</span><span class="sxs-lookup"><span data-stu-id="888cb-436">88888888</span></span>
- <span data-ttu-id="888cb-437">99999999</span><span class="sxs-lookup"><span data-stu-id="888cb-437">99999999</span></span>
- <span data-ttu-id="888cb-438">000000000</span><span class="sxs-lookup"><span data-stu-id="888cb-438">000000000</span></span>
- <span data-ttu-id="888cb-439">111111111</span><span class="sxs-lookup"><span data-stu-id="888cb-439">111111111</span></span>
- <span data-ttu-id="888cb-440">222222222</span><span class="sxs-lookup"><span data-stu-id="888cb-440">222222222</span></span>
- <span data-ttu-id="888cb-441">333333333</span><span class="sxs-lookup"><span data-stu-id="888cb-441">333333333</span></span>
- <span data-ttu-id="888cb-442">444444444</span><span class="sxs-lookup"><span data-stu-id="888cb-442">444444444</span></span>
- <span data-ttu-id="888cb-443">555555555</span><span class="sxs-lookup"><span data-stu-id="888cb-443">555555555</span></span>
- <span data-ttu-id="888cb-444">666666666</span><span class="sxs-lookup"><span data-stu-id="888cb-444">666666666</span></span>
- <span data-ttu-id="888cb-445">777777777</span><span class="sxs-lookup"><span data-stu-id="888cb-445">777777777</span></span>
- <span data-ttu-id="888cb-446">888888888</span><span class="sxs-lookup"><span data-stu-id="888cb-446">888888888</span></span>
- <span data-ttu-id="888cb-447">999999999</span><span class="sxs-lookup"><span data-stu-id="888cb-447">999999999</span></span>
- <span data-ttu-id="888cb-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="888cb-448">0000000000</span></span>
- <span data-ttu-id="888cb-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="888cb-449">1111111111</span></span>
- <span data-ttu-id="888cb-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="888cb-450">2222222222</span></span>
- <span data-ttu-id="888cb-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="888cb-451">3333333333</span></span>
- <span data-ttu-id="888cb-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="888cb-452">4444444444</span></span>
- <span data-ttu-id="888cb-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="888cb-453">5555555555</span></span>
- <span data-ttu-id="888cb-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="888cb-454">6666666666</span></span>
- <span data-ttu-id="888cb-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="888cb-455">7777777777</span></span>
- <span data-ttu-id="888cb-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="888cb-456">8888888888</span></span>
- <span data-ttu-id="888cb-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="888cb-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="888cb-458">Azure DocumentDB 身份验证密钥</span><span class="sxs-lookup"><span data-stu-id="888cb-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="888cb-459">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-459">Format</span></span>

<span data-ttu-id="888cb-460">字符串 "DocumentDb", 后跟下面模式中所示的字符和字符串。</span><span class="sxs-lookup"><span data-stu-id="888cb-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-461">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-461">Pattern</span></span>

- <span data-ttu-id="888cb-462">字符串 "DocumentDb"</span><span class="sxs-lookup"><span data-stu-id="888cb-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="888cb-463">介于3-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="888cb-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="888cb-464">大于号 (>)、等号 (=)、引号 (") 或撇号 (')</span><span class="sxs-lookup"><span data-stu-id="888cb-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="888cb-465">86字母、数字、数字、正斜杠 (/) 或加号 (+) 的任意组合</span><span class="sxs-lookup"><span data-stu-id="888cb-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="888cb-466">两个等号 (=)</span><span class="sxs-lookup"><span data-stu-id="888cb-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-467">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-467">Checksum</span></span>

<span data-ttu-id="888cb-468">否</span><span class="sxs-lookup"><span data-stu-id="888cb-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-469">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-469">Definition</span></span>

<span data-ttu-id="888cb-470">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-471">正则表达式 CEP_Regex_AzureDocumentDBAuthKey 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-472">正则表达式 CEP_CommonExampleKeywords**未**找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```
<!-- Azure Document DB Auth Key -->
<Entity id="0f587d92-eb28-44a9-bd1c-90f2892b47aa" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureDocumentDBAuthKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
          </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-473">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-473">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="888cb-474">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="888cb-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="888cb-475">(请注意, 从技术上讲, 此敏感信息类型通过使用正则表达式 (而不是关键字列表) 来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="888cb-476">尚未</span><span class="sxs-lookup"><span data-stu-id="888cb-476">contoso</span></span>
- <span data-ttu-id="888cb-477">送交</span><span class="sxs-lookup"><span data-stu-id="888cb-477">fabrikam</span></span>
- <span data-ttu-id="888cb-478">罗斯</span><span class="sxs-lookup"><span data-stu-id="888cb-478">northwind</span></span>
- <span data-ttu-id="888cb-479">沙盒</span><span class="sxs-lookup"><span data-stu-id="888cb-479">sandbox</span></span>
- <span data-ttu-id="888cb-480">onebox</span><span class="sxs-lookup"><span data-stu-id="888cb-480">onebox</span></span>
- <span data-ttu-id="888cb-481">localhost</span><span class="sxs-lookup"><span data-stu-id="888cb-481">localhost</span></span>
- <span data-ttu-id="888cb-482">127.0.0。1</span><span class="sxs-lookup"><span data-stu-id="888cb-482">127.0.0.1</span></span>
- <span data-ttu-id="888cb-483">testacs。<!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="888cb-483">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="888cb-484">s-int.<!--no-hyperlink-->net</span><span class="sxs-lookup"><span data-stu-id="888cb-484">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="888cb-485">azure IAAS 数据库连接字符串和 azure SQL 连接字符串</span><span class="sxs-lookup"><span data-stu-id="888cb-485">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="888cb-486">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-486">Format</span></span>

<span data-ttu-id="888cb-487">字符串 "server"、"server" 或 "data source", 后跟下面模式中所述的字符和字符串, 包括字符串 "cloudapp"。<!--no-hyperlink-->com "或" cloudapp "。<!--no-hyperlink-->net "或" database。<!--no-hyperlink-->net "和字符串" password "或" password "或" pwd "。</span><span class="sxs-lookup"><span data-stu-id="888cb-487">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.<!--no-hyperlink-->com" or "cloudapp.azure.<!--no-hyperlink-->net" or "database.windows.<!--no-hyperlink-->net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-488">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-488">Pattern</span></span>

- <span data-ttu-id="888cb-489">字符串 "server"、"server" 或 "data source"</span><span class="sxs-lookup"><span data-stu-id="888cb-489">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="888cb-490">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="888cb-490">0-2 whitespace characters</span></span>
- <span data-ttu-id="888cb-491">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="888cb-491">An equal sign (=)</span></span>
- <span data-ttu-id="888cb-492">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="888cb-492">0-2 whitespace characters</span></span>
- <span data-ttu-id="888cb-493">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="888cb-493">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="888cb-494">字符串 "cloudapp"。<!--no-hyperlink-->com "," cloudapp。<!--no-hyperlink-->net "或" database。<!--no-hyperlink-->net "</span><span class="sxs-lookup"><span data-stu-id="888cb-494">The string "cloudapp.azure.<!--no-hyperlink-->com", "cloudapp.azure.<!--no-hyperlink-->net", or "database.windows.<!--no-hyperlink-->net"</span></span>
- <span data-ttu-id="888cb-495">介于1-300 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="888cb-495">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="888cb-496">字符串 "password"、"password" 或 "pwd"</span><span class="sxs-lookup"><span data-stu-id="888cb-496">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="888cb-497">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="888cb-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="888cb-498">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="888cb-498">An equal sign (=)</span></span>
- <span data-ttu-id="888cb-499">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="888cb-499">0-2 whitespace characters</span></span>
- <span data-ttu-id="888cb-500">一个或多个不是分号 (;)、引号 (") 或撇号 (') 的字符</span><span class="sxs-lookup"><span data-stu-id="888cb-500">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="888cb-501">分号 (;)、引号 (") 或撇号 (')</span><span class="sxs-lookup"><span data-stu-id="888cb-501">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-502">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-502">Checksum</span></span>

<span data-ttu-id="888cb-503">否</span><span class="sxs-lookup"><span data-stu-id="888cb-503">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-504">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-504">Definition</span></span>

<span data-ttu-id="888cb-505">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-505">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-506">正则表达式 CEP_Regex_AzureConnectionString 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-506">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-507">正则表达式 CEP_CommonExampleKeywords**未**找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-507">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```
<!--Azure IAAS Database Connection String and Azure SQL Connection String-->
<Entity id="ce1a126d-186f-4700-8c0c-486157b953fd" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-508">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-508">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="888cb-509">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="888cb-509">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="888cb-510">(请注意, 从技术上讲, 此敏感信息类型通过使用正则表达式 (而不是关键字列表) 来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-510">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="888cb-511">尚未</span><span class="sxs-lookup"><span data-stu-id="888cb-511">contoso</span></span>
- <span data-ttu-id="888cb-512">送交</span><span class="sxs-lookup"><span data-stu-id="888cb-512">fabrikam</span></span>
- <span data-ttu-id="888cb-513">罗斯</span><span class="sxs-lookup"><span data-stu-id="888cb-513">northwind</span></span>
- <span data-ttu-id="888cb-514">沙盒</span><span class="sxs-lookup"><span data-stu-id="888cb-514">sandbox</span></span>
- <span data-ttu-id="888cb-515">onebox</span><span class="sxs-lookup"><span data-stu-id="888cb-515">onebox</span></span>
- <span data-ttu-id="888cb-516">localhost</span><span class="sxs-lookup"><span data-stu-id="888cb-516">localhost</span></span>
- <span data-ttu-id="888cb-517">127.0.0。1</span><span class="sxs-lookup"><span data-stu-id="888cb-517">127.0.0.1</span></span>
- <span data-ttu-id="888cb-518">testacs。<!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="888cb-518">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="888cb-519">s-int.<!--no-hyperlink-->net</span><span class="sxs-lookup"><span data-stu-id="888cb-519">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="888cb-520">Azure IoT 连接字符串</span><span class="sxs-lookup"><span data-stu-id="888cb-520">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="888cb-521">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-521">Format</span></span>

<span data-ttu-id="888cb-522">字符串 "HostName", 后跟下面模式中所示的字符和字符串, 包括字符串 "azure 设备"。<!--no-hyperlink-->net "和" SharedAccessKey "。</span><span class="sxs-lookup"><span data-stu-id="888cb-522">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.<!--no-hyperlink-->net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-523">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-523">Pattern</span></span>

- <span data-ttu-id="888cb-524">字符串 "HostName"</span><span class="sxs-lookup"><span data-stu-id="888cb-524">The string "HostName"</span></span>
- <span data-ttu-id="888cb-525">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="888cb-525">0-2 whitespace characters</span></span>
- <span data-ttu-id="888cb-526">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="888cb-526">An equal sign (=)</span></span>
- <span data-ttu-id="888cb-527">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="888cb-527">0-2 whitespace characters</span></span>
- <span data-ttu-id="888cb-528">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="888cb-528">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="888cb-529">字符串 "azure 设备。<!--no-hyperlink-->net "</span><span class="sxs-lookup"><span data-stu-id="888cb-529">The string "azure-devices.<!--no-hyperlink-->net"</span></span>
- <span data-ttu-id="888cb-530">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="888cb-530">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="888cb-531">字符串 "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="888cb-531">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="888cb-532">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="888cb-532">0-2 whitespace characters</span></span>
- <span data-ttu-id="888cb-533">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="888cb-533">An equal sign (=)</span></span>
- <span data-ttu-id="888cb-534">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="888cb-534">0-2 whitespace characters</span></span>
- <span data-ttu-id="888cb-535">43字母、数字、数字、正斜杠 (/) 或加号 (+) 的任意组合</span><span class="sxs-lookup"><span data-stu-id="888cb-535">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="888cb-536">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="888cb-536">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-537">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-537">Checksum</span></span>

<span data-ttu-id="888cb-538">否</span><span class="sxs-lookup"><span data-stu-id="888cb-538">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-539">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-539">Definition</span></span>

<span data-ttu-id="888cb-540">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-540">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-541">正则表达式 CEP_Regex_AzureIoTConnectionString 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-541">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-542">正则表达式 CEP_CommonExampleKeywords**未**找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-542">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```
<!--Azure IoT Connection String-->
<Entity id="0b34bec3-d5d6-4974-b7b0-dcdb5c90c29d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureIoTConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-543">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-543">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="888cb-544">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="888cb-544">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="888cb-545">(请注意, 从技术上讲, 此敏感信息类型通过使用正则表达式 (而不是关键字列表) 来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-545">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="888cb-546">尚未</span><span class="sxs-lookup"><span data-stu-id="888cb-546">contoso</span></span>
- <span data-ttu-id="888cb-547">送交</span><span class="sxs-lookup"><span data-stu-id="888cb-547">fabrikam</span></span>
- <span data-ttu-id="888cb-548">罗斯</span><span class="sxs-lookup"><span data-stu-id="888cb-548">northwind</span></span>
- <span data-ttu-id="888cb-549">沙盒</span><span class="sxs-lookup"><span data-stu-id="888cb-549">sandbox</span></span>
- <span data-ttu-id="888cb-550">onebox</span><span class="sxs-lookup"><span data-stu-id="888cb-550">onebox</span></span>
- <span data-ttu-id="888cb-551">localhost</span><span class="sxs-lookup"><span data-stu-id="888cb-551">localhost</span></span>
- <span data-ttu-id="888cb-552">127.0.0。1</span><span class="sxs-lookup"><span data-stu-id="888cb-552">127.0.0.1</span></span>
- <span data-ttu-id="888cb-553">testacs。<!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="888cb-553">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="888cb-554">s-int.<!--no-hyperlink-->net</span><span class="sxs-lookup"><span data-stu-id="888cb-554">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="888cb-555">Azure 发布设置密码</span><span class="sxs-lookup"><span data-stu-id="888cb-555">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="888cb-556">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-556">Format</span></span>

<span data-ttu-id="888cb-557">字符串 "userpwd =", 后跟一个字母数字字符串。</span><span class="sxs-lookup"><span data-stu-id="888cb-557">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-558">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-558">Pattern</span></span>

- <span data-ttu-id="888cb-559">字符串 "userpwd ="</span><span class="sxs-lookup"><span data-stu-id="888cb-559">The string "userpwd="</span></span>
- <span data-ttu-id="888cb-560">任何60小写字母或数字的组合</span><span class="sxs-lookup"><span data-stu-id="888cb-560">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="888cb-561">一个引号 (")</span><span class="sxs-lookup"><span data-stu-id="888cb-561">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-562">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-562">Checksum</span></span>

<span data-ttu-id="888cb-563">否</span><span class="sxs-lookup"><span data-stu-id="888cb-563">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-564">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-564">Definition</span></span>

<span data-ttu-id="888cb-565">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-565">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-566">正则表达式 CEP_Regex_AzurePublishSettingPasswords 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-566">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-567">正则表达式 CEP_CommonExampleKeywords**未**找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-567">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


```
<!--Azure Publish Setting Password-->
<Entity id="75f4cc8a-a68e-49e5-89ce-fa8f03d286a5" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="CEP_Regex_AzurePublishSettingPasswords" />
       <Any minMatches="0" maxMatches="0">
           <Match idRef="CEP_CommonExampleKeywords" />
       </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-568">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-568">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="888cb-569">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="888cb-569">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="888cb-570">(请注意, 从技术上讲, 此敏感信息类型通过使用正则表达式 (而不是关键字列表) 来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-570">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="888cb-571">尚未</span><span class="sxs-lookup"><span data-stu-id="888cb-571">contoso</span></span>
- <span data-ttu-id="888cb-572">送交</span><span class="sxs-lookup"><span data-stu-id="888cb-572">fabrikam</span></span>
- <span data-ttu-id="888cb-573">罗斯</span><span class="sxs-lookup"><span data-stu-id="888cb-573">northwind</span></span>
- <span data-ttu-id="888cb-574">沙盒</span><span class="sxs-lookup"><span data-stu-id="888cb-574">sandbox</span></span>
- <span data-ttu-id="888cb-575">onebox</span><span class="sxs-lookup"><span data-stu-id="888cb-575">onebox</span></span>
- <span data-ttu-id="888cb-576">localhost</span><span class="sxs-lookup"><span data-stu-id="888cb-576">localhost</span></span>
- <span data-ttu-id="888cb-577">127.0.0。1</span><span class="sxs-lookup"><span data-stu-id="888cb-577">127.0.0.1</span></span>
- <span data-ttu-id="888cb-578">testacs。<!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="888cb-578">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="888cb-579">s-int.<!--no-hyperlink-->net</span><span class="sxs-lookup"><span data-stu-id="888cb-579">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="888cb-580">Azure Redis 缓存连接字符串</span><span class="sxs-lookup"><span data-stu-id="888cb-580">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="888cb-581">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-581">Format</span></span>

<span data-ttu-id="888cb-582">字符串 "redis"。<!--no-hyperlink-->net ", 后跟下面的模式中所述的字符和字符串, 包括字符串" password "或" pwd "。</span><span class="sxs-lookup"><span data-stu-id="888cb-582">The string "redis.cache.windows.<!--no-hyperlink-->net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-583">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-583">Pattern</span></span>

- <span data-ttu-id="888cb-584">字符串 "redis"。<!--no-hyperlink-->net "</span><span class="sxs-lookup"><span data-stu-id="888cb-584">The string "redis.cache.windows.<!--no-hyperlink-->net"</span></span>
- <span data-ttu-id="888cb-585">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="888cb-585">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="888cb-586">字符串 "password" 或 "pwd"</span><span class="sxs-lookup"><span data-stu-id="888cb-586">The string "password" or "pwd"</span></span>
- <span data-ttu-id="888cb-587">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="888cb-587">0-2 whitespace characters</span></span>
- <span data-ttu-id="888cb-588">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="888cb-588">An equal sign (=)</span></span>
- <span data-ttu-id="888cb-589">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="888cb-589">0-2 whitespace characters</span></span>
- <span data-ttu-id="888cb-590">43个字符的任意组合, 这些字符为小写字母、数字、斜杠 (/) 或加号 (+)</span><span class="sxs-lookup"><span data-stu-id="888cb-590">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="888cb-591">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="888cb-591">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-592">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-592">Checksum</span></span>

<span data-ttu-id="888cb-593">否</span><span class="sxs-lookup"><span data-stu-id="888cb-593">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-594">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-594">Definition</span></span>

<span data-ttu-id="888cb-595">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-595">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-596">正则表达式 CEP_Regex_AzureRedisCacheConnectionString 找到与该模式匹配的内容。。</span><span class="sxs-lookup"><span data-stu-id="888cb-596">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="888cb-597">正则表达式 CEP_CommonExampleKeywords**未**找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-597">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```
<!--Azure Redis Cache Connection String-->
<Entity id="095a7e6c-efd8-46d5-af7b-5298d53a49fc" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureRedisCacheConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-598">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-598">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="888cb-599">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="888cb-599">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="888cb-600">(请注意, 从技术上讲, 此敏感信息类型通过使用正则表达式 (而不是关键字列表) 来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-600">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="888cb-601">尚未</span><span class="sxs-lookup"><span data-stu-id="888cb-601">contoso</span></span>
- <span data-ttu-id="888cb-602">送交</span><span class="sxs-lookup"><span data-stu-id="888cb-602">fabrikam</span></span>
- <span data-ttu-id="888cb-603">罗斯</span><span class="sxs-lookup"><span data-stu-id="888cb-603">northwind</span></span>
- <span data-ttu-id="888cb-604">沙盒</span><span class="sxs-lookup"><span data-stu-id="888cb-604">sandbox</span></span>
- <span data-ttu-id="888cb-605">onebox</span><span class="sxs-lookup"><span data-stu-id="888cb-605">onebox</span></span>
- <span data-ttu-id="888cb-606">localhost</span><span class="sxs-lookup"><span data-stu-id="888cb-606">localhost</span></span>
- <span data-ttu-id="888cb-607">127.0.0。1</span><span class="sxs-lookup"><span data-stu-id="888cb-607">127.0.0.1</span></span>
- <span data-ttu-id="888cb-608">testacs。<!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="888cb-608">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="888cb-609">s-int.<!--no-hyperlink-->net</span><span class="sxs-lookup"><span data-stu-id="888cb-609">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="888cb-610">Azure sa</span><span class="sxs-lookup"><span data-stu-id="888cb-610">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="888cb-611">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-611">Format</span></span>

<span data-ttu-id="888cb-612">字符串 "sig", 后跟下面模式中所示的字符和字符串。</span><span class="sxs-lookup"><span data-stu-id="888cb-612">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-613">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-613">Pattern</span></span>

- <span data-ttu-id="888cb-614">字符串 "sig"</span><span class="sxs-lookup"><span data-stu-id="888cb-614">The string "sig"</span></span>
- <span data-ttu-id="888cb-615">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="888cb-615">0-2 whitespace characters</span></span>
- <span data-ttu-id="888cb-616">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="888cb-616">An equal sign (=)</span></span>
- <span data-ttu-id="888cb-617">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="888cb-617">0-2 whitespace characters</span></span>
- <span data-ttu-id="888cb-618">介于43-53 个字符和小写字母、数字或百分比符号 (%) 之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="888cb-618">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="888cb-619">字符串 "% 3d"</span><span class="sxs-lookup"><span data-stu-id="888cb-619">The string "%3d"</span></span>
- <span data-ttu-id="888cb-620">不是字母或大写字符、数字或百分号 (%) 的任何字符</span><span class="sxs-lookup"><span data-stu-id="888cb-620">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-621">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-621">Checksum</span></span>

<span data-ttu-id="888cb-622">否</span><span class="sxs-lookup"><span data-stu-id="888cb-622">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-623">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-623">Definition</span></span>

<span data-ttu-id="888cb-624">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-624">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-625">正则表达式 CEP_Regex_AzureSAS 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-625">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="888cb-626">Azure 服务总线连接字符串</span><span class="sxs-lookup"><span data-stu-id="888cb-626">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="888cb-627">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-627">Format</span></span>

<span data-ttu-id="888cb-628">字符串 "终结点", 后跟下面模式中所示的字符和字符串, 包括字符串 "<!--no-hyperlink-->net "和" SharedAccesKey "。</span><span class="sxs-lookup"><span data-stu-id="888cb-628">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.<!--no-hyperlink-->net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-629">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-629">Pattern</span></span>

- <span data-ttu-id="888cb-630">字符串 "EndPoint"</span><span class="sxs-lookup"><span data-stu-id="888cb-630">The string "EndPoint"</span></span>
- <span data-ttu-id="888cb-631">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="888cb-631">0-2 whitespace characters</span></span>
- <span data-ttu-id="888cb-632">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="888cb-632">An equal sign (=)</span></span>
- <span data-ttu-id="888cb-633">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="888cb-633">0-2 whitespace characters</span></span>
- <span data-ttu-id="888cb-634">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="888cb-634">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="888cb-635">字符串 "<!--no-hyperlink-->net "</span><span class="sxs-lookup"><span data-stu-id="888cb-635">The string "servicebus.windows.<!--no-hyperlink-->net"</span></span>
- <span data-ttu-id="888cb-636">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="888cb-636">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="888cb-637">字符串 "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="888cb-637">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="888cb-638">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="888cb-638">0-2 whitespace characters</span></span>
- <span data-ttu-id="888cb-639">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="888cb-639">An equal sign (=)</span></span>
- <span data-ttu-id="888cb-640">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="888cb-640">0-2 whitespace characters</span></span>
- <span data-ttu-id="888cb-641">43个字符的任意组合, 这些字符为小写字母、数字、斜杠 (/) 或加号 (+)</span><span class="sxs-lookup"><span data-stu-id="888cb-641">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="888cb-642">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="888cb-642">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-643">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-643">Checksum</span></span>

<span data-ttu-id="888cb-644">否</span><span class="sxs-lookup"><span data-stu-id="888cb-644">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-645">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-645">Definition</span></span>

<span data-ttu-id="888cb-646">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-646">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-647">正则表达式 CEP_Regex_AzureServiceBusConnectionString 找到与该模式匹配的内容。。</span><span class="sxs-lookup"><span data-stu-id="888cb-647">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="888cb-648">正则表达式 CEP_CommonExampleKeywords**未**找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-648">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```
<!--Azure Service Bus Connection String-->
<Entity id="b9a6578f-a83f-4fcd-bf44-2130bae49a6f" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureServiceBusConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-649">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-649">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="888cb-650">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="888cb-650">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="888cb-651">(请注意, 从技术上讲, 此敏感信息类型通过使用正则表达式 (而不是关键字列表) 来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-651">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="888cb-652">尚未</span><span class="sxs-lookup"><span data-stu-id="888cb-652">contoso</span></span>
- <span data-ttu-id="888cb-653">送交</span><span class="sxs-lookup"><span data-stu-id="888cb-653">fabrikam</span></span>
- <span data-ttu-id="888cb-654">罗斯</span><span class="sxs-lookup"><span data-stu-id="888cb-654">northwind</span></span>
- <span data-ttu-id="888cb-655">沙盒</span><span class="sxs-lookup"><span data-stu-id="888cb-655">sandbox</span></span>
- <span data-ttu-id="888cb-656">onebox</span><span class="sxs-lookup"><span data-stu-id="888cb-656">onebox</span></span>
- <span data-ttu-id="888cb-657">localhost</span><span class="sxs-lookup"><span data-stu-id="888cb-657">localhost</span></span>
- <span data-ttu-id="888cb-658">127.0.0。1</span><span class="sxs-lookup"><span data-stu-id="888cb-658">127.0.0.1</span></span>
- <span data-ttu-id="888cb-659">testacs。<!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="888cb-659">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="888cb-660">s-int.<!--no-hyperlink-->net</span><span class="sxs-lookup"><span data-stu-id="888cb-660">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="888cb-661">Azure 存储帐户密钥</span><span class="sxs-lookup"><span data-stu-id="888cb-661">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="888cb-662">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-662">Format</span></span>

<span data-ttu-id="888cb-663">字符串 "DefaultEndpointsProtocol", 后跟下面模式中所述的字符和字符串, 包括字符串 "AccountKey"。</span><span class="sxs-lookup"><span data-stu-id="888cb-663">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-664">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-664">Pattern</span></span>

- <span data-ttu-id="888cb-665">字符串 "DefaultEndpointsProtocol"</span><span class="sxs-lookup"><span data-stu-id="888cb-665">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="888cb-666">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="888cb-666">0-2 whitespace characters</span></span>
- <span data-ttu-id="888cb-667">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="888cb-667">An equal sign (=)</span></span>
- <span data-ttu-id="888cb-668">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="888cb-668">0-2 whitespace characters</span></span>
- <span data-ttu-id="888cb-669">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="888cb-669">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="888cb-670">字符串 "AccountKey"</span><span class="sxs-lookup"><span data-stu-id="888cb-670">The string "AccountKey"</span></span>
- <span data-ttu-id="888cb-671">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="888cb-671">0-2 whitespace characters</span></span>
- <span data-ttu-id="888cb-672">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="888cb-672">An equal sign (=)</span></span>
- <span data-ttu-id="888cb-673">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="888cb-673">0-2 whitespace characters</span></span>
- <span data-ttu-id="888cb-674">86个字符的任意组合, 这些字符为小写字母、数字、斜杠 (/) 或加号 (+)</span><span class="sxs-lookup"><span data-stu-id="888cb-674">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="888cb-675">两个等号 (=)</span><span class="sxs-lookup"><span data-stu-id="888cb-675">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-676">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-676">Checksum</span></span>

<span data-ttu-id="888cb-677">否</span><span class="sxs-lookup"><span data-stu-id="888cb-677">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-678">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-678">Definition</span></span>

<span data-ttu-id="888cb-679">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-679">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-680">正则表达式 CEP_Regex_AzureStorageAccountKey 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-680">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-681">正则表达式 CEP_AzureEmulatorStorageAccountFilter**未**找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-681">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-682">正则表达式 CEP_CommonExampleKeywords**未**找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-682">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```
<!--Azure Storage Account Key-->
<Entity id="c7bc98e8-551a-4c35-a92d-d2c8cda714a7" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_AzureEmulatorStorageAccountFilter" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-683">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-683">Keywords</span></span>

#### <a name="cepazureemulatorstorageaccountfilter"></a><span data-ttu-id="888cb-684">CEP_AzureEmulatorStorageAccountFilter</span><span class="sxs-lookup"><span data-stu-id="888cb-684">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="888cb-685">(请注意, 从技术上讲, 此敏感信息类型通过使用正则表达式 (而不是关键字列表) 来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-685">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="888cb-686">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =</span><span class="sxs-lookup"><span data-stu-id="888cb-686">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="888cb-687">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="888cb-687">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="888cb-688">(请注意, 从技术上讲, 此敏感信息类型通过使用正则表达式 (而不是关键字列表) 来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-688">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="888cb-689">尚未</span><span class="sxs-lookup"><span data-stu-id="888cb-689">contoso</span></span>
- <span data-ttu-id="888cb-690">送交</span><span class="sxs-lookup"><span data-stu-id="888cb-690">fabrikam</span></span>
- <span data-ttu-id="888cb-691">罗斯</span><span class="sxs-lookup"><span data-stu-id="888cb-691">northwind</span></span>
- <span data-ttu-id="888cb-692">沙盒</span><span class="sxs-lookup"><span data-stu-id="888cb-692">sandbox</span></span>
- <span data-ttu-id="888cb-693">onebox</span><span class="sxs-lookup"><span data-stu-id="888cb-693">onebox</span></span>
- <span data-ttu-id="888cb-694">localhost</span><span class="sxs-lookup"><span data-stu-id="888cb-694">localhost</span></span>
- <span data-ttu-id="888cb-695">127.0.0。1</span><span class="sxs-lookup"><span data-stu-id="888cb-695">127.0.0.1</span></span>
- <span data-ttu-id="888cb-696">testacs。<!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="888cb-696">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="888cb-697">s-int.<!--no-hyperlink-->net</span><span class="sxs-lookup"><span data-stu-id="888cb-697">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="888cb-698">Azure 存储帐户密钥 (常规)</span><span class="sxs-lookup"><span data-stu-id="888cb-698">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="888cb-699">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-699">Format</span></span>

<span data-ttu-id="888cb-700">任何86位或大写字母、数字、正斜杠 (/) 或加号 (+) 的任意组合, 前面或后面是下面模式中所述的字符。</span><span class="sxs-lookup"><span data-stu-id="888cb-700">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-701">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-701">Pattern</span></span>

- <span data-ttu-id="888cb-702">大于号 (>)、撇号 (')、等号 (=)、引号 (") 或数字符号 (#) 的0-1</span><span class="sxs-lookup"><span data-stu-id="888cb-702">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="888cb-703">86个字符的任意组合, 这些字符为小写字母、数字、斜杠 (/) 或加号 (+)</span><span class="sxs-lookup"><span data-stu-id="888cb-703">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="888cb-704">两个等号 (=)</span><span class="sxs-lookup"><span data-stu-id="888cb-704">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="888cb-705">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-705">Checksum</span></span>

<span data-ttu-id="888cb-706">否</span><span class="sxs-lookup"><span data-stu-id="888cb-706">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-707">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-707">Definition</span></span>

<span data-ttu-id="888cb-708">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-708">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-709">正则表达式 CEP_Regex_AzureStorageAccountKeyGeneric 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-709">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="888cb-710">比利时国家号码</span><span class="sxs-lookup"><span data-stu-id="888cb-710">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-711">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-711">Format</span></span>

<span data-ttu-id="888cb-712">11 个数字加分隔符</span><span class="sxs-lookup"><span data-stu-id="888cb-712">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-713">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-713">Pattern</span></span>

<span data-ttu-id="888cb-714">11 个数字加分隔符：</span><span class="sxs-lookup"><span data-stu-id="888cb-714">11 digits plus delimiters:</span></span>
- <span data-ttu-id="888cb-715">六个数字加两个点，采用格式  YY.MM.DD，代表出生日期  </span><span class="sxs-lookup"><span data-stu-id="888cb-715">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="888cb-716">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="888cb-716">A hyphen</span></span> 
- <span data-ttu-id="888cb-717">三个连续的数字（男性用奇数，女性用偶数） </span><span class="sxs-lookup"><span data-stu-id="888cb-717">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="888cb-718">一个点</span><span class="sxs-lookup"><span data-stu-id="888cb-718">A period</span></span> 
- <span data-ttu-id="888cb-719">两个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="888cb-719">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-720">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-720">Checksum</span></span>

<span data-ttu-id="888cb-721">是</span><span class="sxs-lookup"><span data-stu-id="888cb-721">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-722">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-722">Definition</span></span>

<span data-ttu-id="888cb-723">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-723">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-724">函数 Func_belgium_national_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-724">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-725">找到 Keyword_belgium_national_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-725">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="888cb-726">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-726">The checksum passes.</span></span>

```
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-727">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-727">Keywords</span></span>

#### <a name="keywordbelgiumnationalnumber"></a><span data-ttu-id="888cb-728">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="888cb-728">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="888cb-729">标识</span><span class="sxs-lookup"><span data-stu-id="888cb-729">Identity</span></span>
- <span data-ttu-id="888cb-730">注册</span><span class="sxs-lookup"><span data-stu-id="888cb-730">Registration</span></span>
- <span data-ttu-id="888cb-731">id</span><span class="sxs-lookup"><span data-stu-id="888cb-731">Identification</span></span> 
- <span data-ttu-id="888cb-732">ID</span><span class="sxs-lookup"><span data-stu-id="888cb-732">ID</span></span> 
- <span data-ttu-id="888cb-733">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="888cb-733">Identiteitskaart</span></span>
- <span data-ttu-id="888cb-734">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="888cb-734">Registratie nummer</span></span> 
- <span data-ttu-id="888cb-735">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="888cb-735">Identificatie nummer</span></span> 
- <span data-ttu-id="888cb-736">Identiteit</span><span class="sxs-lookup"><span data-stu-id="888cb-736">Identiteit</span></span>
- <span data-ttu-id="888cb-737">Registratie</span><span class="sxs-lookup"><span data-stu-id="888cb-737">Registratie</span></span>
- <span data-ttu-id="888cb-738">Identificatie</span><span class="sxs-lookup"><span data-stu-id="888cb-738">Identificatie</span></span> 
- <span data-ttu-id="888cb-739">Carte d’identité</span><span class="sxs-lookup"><span data-stu-id="888cb-739">Carte d’identité</span></span> 
- <span data-ttu-id="888cb-740">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="888cb-740">numéro d'immatriculation</span></span>
- <span data-ttu-id="888cb-741">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="888cb-741">numéro d'identification</span></span>
- <span data-ttu-id="888cb-742">identité</span><span class="sxs-lookup"><span data-stu-id="888cb-742">identité</span></span> 
- <span data-ttu-id="888cb-743">inscription</span><span class="sxs-lookup"><span data-stu-id="888cb-743">inscription</span></span> 
- <span data-ttu-id="888cb-744">Identifikation</span><span class="sxs-lookup"><span data-stu-id="888cb-744">Identifikation</span></span>
- <span data-ttu-id="888cb-745">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="888cb-745">Identifizierung</span></span>
- <span data-ttu-id="888cb-746">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="888cb-746">Identifikationsnummer</span></span>
- <span data-ttu-id="888cb-747">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="888cb-747">Personalausweis</span></span>
- <span data-ttu-id="888cb-748">Registrierung</span><span class="sxs-lookup"><span data-stu-id="888cb-748">Registrierung</span></span>
- <span data-ttu-id="888cb-749">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="888cb-749">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="888cb-750">巴西 CPF 号码</span><span class="sxs-lookup"><span data-stu-id="888cb-750">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-751">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-751">Format</span></span>

<span data-ttu-id="888cb-752">11 个数字（包括校验位），可以格式化，也可以非格式化</span><span class="sxs-lookup"><span data-stu-id="888cb-752">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-753">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-753">Pattern</span></span>

<span data-ttu-id="888cb-754">格式</span><span class="sxs-lookup"><span data-stu-id="888cb-754">Formatted:</span></span>
- <span data-ttu-id="888cb-755">三位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-755">Three digits</span></span> 
- <span data-ttu-id="888cb-756">一个点 </span><span class="sxs-lookup"><span data-stu-id="888cb-756">A period</span></span> 
- <span data-ttu-id="888cb-757">三位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-757">Three digits</span></span> 
- <span data-ttu-id="888cb-758">一个点 </span><span class="sxs-lookup"><span data-stu-id="888cb-758">A period</span></span> 
- <span data-ttu-id="888cb-759">三位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-759">Three digits</span></span> 
- <span data-ttu-id="888cb-760">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="888cb-760">A hyphen</span></span> 
- <span data-ttu-id="888cb-761">两个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="888cb-761">Two digits which are check digits</span></span>

<span data-ttu-id="888cb-762">纯</span><span class="sxs-lookup"><span data-stu-id="888cb-762">Unformatted:</span></span>
- <span data-ttu-id="888cb-763">11 个数字，其中最后两个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="888cb-763">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-764">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-764">Checksum</span></span>

<span data-ttu-id="888cb-765">是</span><span class="sxs-lookup"><span data-stu-id="888cb-765">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-766">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-766">Definition</span></span>

<span data-ttu-id="888cb-767">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-767">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-768">函数 Func_brazil_cpf 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-768">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-769">找到 Keyword_brazil_cpf 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-769">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="888cb-770">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-770">The checksum passes.</span></span>

<span data-ttu-id="888cb-771">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-772">函数 Func_brazil_cpf 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-772">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-773">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-773">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-774">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-774">Keywords</span></span>

#### <a name="keywordbrazilcpf"></a><span data-ttu-id="888cb-775">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="888cb-775">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="888cb-776">CPF</span><span class="sxs-lookup"><span data-stu-id="888cb-776">CPF</span></span>
- <span data-ttu-id="888cb-777">id</span><span class="sxs-lookup"><span data-stu-id="888cb-777">Identification</span></span>
- <span data-ttu-id="888cb-778">注册</span><span class="sxs-lookup"><span data-stu-id="888cb-778">Registration</span></span>
- <span data-ttu-id="888cb-779">营业</span><span class="sxs-lookup"><span data-stu-id="888cb-779">Revenue</span></span>
- <span data-ttu-id="888cb-780">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="888cb-780">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="888cb-781">Imposto</span><span class="sxs-lookup"><span data-stu-id="888cb-781">Imposto</span></span> 
- <span data-ttu-id="888cb-782">Identificação</span><span class="sxs-lookup"><span data-stu-id="888cb-782">Identificação</span></span> 
- <span data-ttu-id="888cb-783">Inscrição</span><span class="sxs-lookup"><span data-stu-id="888cb-783">Inscrição</span></span> 
- <span data-ttu-id="888cb-784">Receita</span><span class="sxs-lookup"><span data-stu-id="888cb-784">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="888cb-785">巴西法律实体编号 (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="888cb-785">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="888cb-786">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-786">Format</span></span>

<span data-ttu-id="888cb-787">14 个数字（包括注册号、分行号码和校验位），再加上分隔符</span><span class="sxs-lookup"><span data-stu-id="888cb-787">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-788">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-788">Pattern</span></span>
<span data-ttu-id="888cb-789">14 个数字，再加上分隔符：</span><span class="sxs-lookup"><span data-stu-id="888cb-789">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="888cb-790">两个数字 </span><span class="sxs-lookup"><span data-stu-id="888cb-790">Two digits</span></span> 
- <span data-ttu-id="888cb-791">一个点 </span><span class="sxs-lookup"><span data-stu-id="888cb-791">A period</span></span> 
- <span data-ttu-id="888cb-792">三位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-792">Three digits</span></span> 
- <span data-ttu-id="888cb-793">一个点 </span><span class="sxs-lookup"><span data-stu-id="888cb-793">A period</span></span> 
- <span data-ttu-id="888cb-794">三个数字（前 8 位数是注册号） </span><span class="sxs-lookup"><span data-stu-id="888cb-794">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="888cb-795">正斜杠 </span><span class="sxs-lookup"><span data-stu-id="888cb-795">A forward slash</span></span> 
- <span data-ttu-id="888cb-796">四位分行号码 </span><span class="sxs-lookup"><span data-stu-id="888cb-796">Four-digit branch number</span></span> 
- <span data-ttu-id="888cb-797">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="888cb-797">A hyphen</span></span> 
- <span data-ttu-id="888cb-798">两个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="888cb-798">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-799">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-799">Checksum</span></span>

<span data-ttu-id="888cb-800">是</span><span class="sxs-lookup"><span data-stu-id="888cb-800">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-801">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-801">Definition</span></span>

<span data-ttu-id="888cb-802">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-802">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-803">函数 Func_brazil_cnpj 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-803">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-804">找到 Keyword_brazil_cnpj 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-804">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="888cb-805">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-805">The checksum passes.</span></span>

<span data-ttu-id="888cb-806">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-806">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-807">函数 Func_brazil_cnpj 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-807">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-808">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-808">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-809">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-809">Keywords</span></span>

#### <a name="keywordbrazilcnpj"></a><span data-ttu-id="888cb-810">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="888cb-810">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="888cb-811">CNPJ</span><span class="sxs-lookup"><span data-stu-id="888cb-811">CNPJ</span></span> 
- <span data-ttu-id="888cb-812">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="888cb-812">CNPJ/MF</span></span> 
- <span data-ttu-id="888cb-813">CNPJ-MF</span><span class="sxs-lookup"><span data-stu-id="888cb-813">CNPJ-MF</span></span> 
- <span data-ttu-id="888cb-814">National Registry of Legal Entities</span><span class="sxs-lookup"><span data-stu-id="888cb-814">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="888cb-815">Taxpayers Registry</span><span class="sxs-lookup"><span data-stu-id="888cb-815">Taxpayers Registry</span></span> 
- <span data-ttu-id="888cb-816">Legal entity</span><span class="sxs-lookup"><span data-stu-id="888cb-816">Legal entity</span></span> 
- <span data-ttu-id="888cb-817">Legal entities</span><span class="sxs-lookup"><span data-stu-id="888cb-817">Legal entities</span></span> 
- <span data-ttu-id="888cb-818">Registration Status</span><span class="sxs-lookup"><span data-stu-id="888cb-818">Registration Status</span></span> 
- <span data-ttu-id="888cb-819">商业版</span><span class="sxs-lookup"><span data-stu-id="888cb-819">Business</span></span> 
- <span data-ttu-id="888cb-820">Company</span><span class="sxs-lookup"><span data-stu-id="888cb-820">Company</span></span>
- <span data-ttu-id="888cb-821">CNPJ</span><span class="sxs-lookup"><span data-stu-id="888cb-821">CNPJ</span></span> 
- <span data-ttu-id="888cb-822">Cadastro Nacional da Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="888cb-822">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="888cb-823">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="888cb-823">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="888cb-824">CGC</span><span class="sxs-lookup"><span data-stu-id="888cb-824">CGC</span></span> 
- <span data-ttu-id="888cb-825">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="888cb-825">Pessoa jurídica</span></span> 
- <span data-ttu-id="888cb-826">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="888cb-826">Pessoas jurídicas</span></span> 
- <span data-ttu-id="888cb-827">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="888cb-827">Situação cadastral</span></span> 
- <span data-ttu-id="888cb-828">Inscrição</span><span class="sxs-lookup"><span data-stu-id="888cb-828">Inscrição</span></span> 
- <span data-ttu-id="888cb-829">Empresa</span><span class="sxs-lookup"><span data-stu-id="888cb-829">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="888cb-830">	巴西国家身份证 (RG)</span><span class="sxs-lookup"><span data-stu-id="888cb-830">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="888cb-831">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-831">Format</span></span>

<span data-ttu-id="888cb-832">Registro Geral (旧格式): 9 个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-832">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="888cb-833">Registro de Identidade (RIC) (新格式):11 个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-833">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-834">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-834">Pattern</span></span>

<span data-ttu-id="888cb-835">Registro Geral（旧格式）：</span><span class="sxs-lookup"><span data-stu-id="888cb-835">Registro Geral (old format):</span></span>
- <span data-ttu-id="888cb-836">两个数字 </span><span class="sxs-lookup"><span data-stu-id="888cb-836">Two digits</span></span> 
- <span data-ttu-id="888cb-837">一个点 </span><span class="sxs-lookup"><span data-stu-id="888cb-837">A period</span></span> 
- <span data-ttu-id="888cb-838">三个数字 </span><span class="sxs-lookup"><span data-stu-id="888cb-838">Three digits</span></span> 
- <span data-ttu-id="888cb-839">一个点 </span><span class="sxs-lookup"><span data-stu-id="888cb-839">A period</span></span> 
- <span data-ttu-id="888cb-840">三个数字 </span><span class="sxs-lookup"><span data-stu-id="888cb-840">Three digits</span></span> 
- <span data-ttu-id="888cb-841">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="888cb-841">A hyphen</span></span> 
- <span data-ttu-id="888cb-842">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="888cb-842">One digit which is a check digit</span></span>

<span data-ttu-id="888cb-843">Registro de Identidade (RIC) (新格式):</span><span class="sxs-lookup"><span data-stu-id="888cb-843">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="888cb-844">10 个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-844">10 digits</span></span> 
- <span data-ttu-id="888cb-845">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="888cb-845">A hyphen</span></span> 
- <span data-ttu-id="888cb-846">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="888cb-846">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-847">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-847">Checksum</span></span>

<span data-ttu-id="888cb-848">是</span><span class="sxs-lookup"><span data-stu-id="888cb-848">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-849">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-849">Definition</span></span>

<span data-ttu-id="888cb-850">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-850">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-851">函数 Func_brazil_rg 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-851">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-852">找到 Keyword_brazil_rg 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-852">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="888cb-853">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-853">The checksum passes.</span></span>

<span data-ttu-id="888cb-854">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-854">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-855">函数 Func_brazil_rg 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-855">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-856">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-856">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-857">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-857">Keywords</span></span>

#### <a name="keywordbrazilrg"></a><span data-ttu-id="888cb-858">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="888cb-858">Keyword_brazil_rg</span></span>

<span data-ttu-id="888cb-859">Cédula de identidade identity 卡片国家 id número de rregistro registro de Iidentidade registro geral RG (此关键字区分大小写) RIC (此关键字区分大小写)</span><span class="sxs-lookup"><span data-stu-id="888cb-859">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="888cb-860">加拿大银行帐号</span><span class="sxs-lookup"><span data-stu-id="888cb-860">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-861">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-861">Format</span></span>

<span data-ttu-id="888cb-862">七个或十二个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-862">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-863">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-863">Pattern</span></span>

<span data-ttu-id="888cb-864">加拿大银行帐号是七个或十二个数字。</span><span class="sxs-lookup"><span data-stu-id="888cb-864">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="888cb-865">加拿大银行帐户的银行代号是：</span><span class="sxs-lookup"><span data-stu-id="888cb-865">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="888cb-866">五位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-866">Five digits</span></span> 
- <span data-ttu-id="888cb-867">连字符</span><span class="sxs-lookup"><span data-stu-id="888cb-867">A hyphen</span></span> 
- <span data-ttu-id="888cb-868">三位数字或</span><span class="sxs-lookup"><span data-stu-id="888cb-868">Three digits OR</span></span>
- <span data-ttu-id="888cb-869">一个零“0” </span><span class="sxs-lookup"><span data-stu-id="888cb-869">A zero "0"</span></span> 
- <span data-ttu-id="888cb-870">八位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-870">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-871">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-871">Checksum</span></span>

<span data-ttu-id="888cb-872">否</span><span class="sxs-lookup"><span data-stu-id="888cb-872">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-873">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-873">Definition</span></span>

<span data-ttu-id="888cb-874">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-874">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-875">正则表达式 Regex_canada_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-875">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-876">找到 Keyword_canada_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-876">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="888cb-877">正则表达式 Regex_canada_bank_account_transit_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-877">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="888cb-878">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-878">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-879">正则表达式 Regex_canada_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-879">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-880">找到 Keyword_canada_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-880">A keyword from Keyword_canada_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-881">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-881">Keywords</span></span>

#### <a name="keywordcanadabankaccountnumber"></a><span data-ttu-id="888cb-882">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="888cb-882">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="888cb-883">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="888cb-883">canada savings bonds</span></span>
- <span data-ttu-id="888cb-884">canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="888cb-884">canada revenue agency</span></span>
- <span data-ttu-id="888cb-885">canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="888cb-885">canadian financial institution</span></span>
- <span data-ttu-id="888cb-886">direct deposit form</span><span class="sxs-lookup"><span data-stu-id="888cb-886">direct deposit form</span></span>
- <span data-ttu-id="888cb-887">canadian citizen</span><span class="sxs-lookup"><span data-stu-id="888cb-887">canadian citizen</span></span>
- <span data-ttu-id="888cb-888">legal representative</span><span class="sxs-lookup"><span data-stu-id="888cb-888">legal representative</span></span>
- <span data-ttu-id="888cb-889">notary public</span><span class="sxs-lookup"><span data-stu-id="888cb-889">notary public</span></span>
- <span data-ttu-id="888cb-890">commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="888cb-890">commissioner for oaths</span></span>
- <span data-ttu-id="888cb-891">child care benefit</span><span class="sxs-lookup"><span data-stu-id="888cb-891">child care benefit</span></span>
- <span data-ttu-id="888cb-892">universal child care</span><span class="sxs-lookup"><span data-stu-id="888cb-892">universal child care</span></span>
- <span data-ttu-id="888cb-893">canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="888cb-893">canada child tax benefit</span></span>
- <span data-ttu-id="888cb-894">income tax benefit</span><span class="sxs-lookup"><span data-stu-id="888cb-894">income tax benefit</span></span>
- <span data-ttu-id="888cb-895">harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="888cb-895">harmonized sales tax</span></span>
- <span data-ttu-id="888cb-896">social insurance number</span><span class="sxs-lookup"><span data-stu-id="888cb-896">social insurance number</span></span>
- <span data-ttu-id="888cb-897">income tax refund</span><span class="sxs-lookup"><span data-stu-id="888cb-897">income tax refund</span></span>
- <span data-ttu-id="888cb-898">child tax benefit</span><span class="sxs-lookup"><span data-stu-id="888cb-898">child tax benefit</span></span>
- <span data-ttu-id="888cb-899">territorial payments</span><span class="sxs-lookup"><span data-stu-id="888cb-899">territorial payments</span></span>
- <span data-ttu-id="888cb-900">institution number</span><span class="sxs-lookup"><span data-stu-id="888cb-900">institution number</span></span>
- <span data-ttu-id="888cb-901">deposit request</span><span class="sxs-lookup"><span data-stu-id="888cb-901">deposit request</span></span>
- <span data-ttu-id="888cb-902">banking information</span><span class="sxs-lookup"><span data-stu-id="888cb-902">banking information</span></span>
- <span data-ttu-id="888cb-903">direct deposit</span><span class="sxs-lookup"><span data-stu-id="888cb-903">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="888cb-904">加拿大驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="888cb-904">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-905">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-905">Format</span></span>

<span data-ttu-id="888cb-906">因省而异</span><span class="sxs-lookup"><span data-stu-id="888cb-906">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-907">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-907">Pattern</span></span>

<span data-ttu-id="888cb-908">各种模式，涵盖艾伯塔、 不列颠哥伦比亚、 马尼托巴、 新不伦瑞克、 纽芬兰/拉布拉多、 新斯科舍、 安大略、 爱德华王子岛，魁北克和萨斯喀彻温</span><span class="sxs-lookup"><span data-stu-id="888cb-908">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-909">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-909">Checksum</span></span>

<span data-ttu-id="888cb-910">否</span><span class="sxs-lookup"><span data-stu-id="888cb-910">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-911">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-911">Definition</span></span>

<span data-ttu-id="888cb-912">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-912">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-913">函数 Func_[province_name]_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-913">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-914">找到 Keyword_[province_name]_drivers_license_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-914">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="888cb-915">找到 Keyword_canada_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-915">A keyword from Keyword_canada_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-916">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-916">Keywords</span></span>

#### <a name="keywordprovincenamedriverslicensename"></a><span data-ttu-id="888cb-917">Keyword_ [province_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="888cb-917">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="888cb-918">省/市/自治区的缩写，例如 AB</span><span class="sxs-lookup"><span data-stu-id="888cb-918">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="888cb-919">省名称，例如 Alberta</span><span class="sxs-lookup"><span data-stu-id="888cb-919">The province name, for example Alberta</span></span>

#### <a name="keywordcanadadriverslicense"></a><span data-ttu-id="888cb-920">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="888cb-920">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="888cb-921">通讯</span><span class="sxs-lookup"><span data-stu-id="888cb-921">DL</span></span>
- <span data-ttu-id="888cb-922">DLS</span><span class="sxs-lookup"><span data-stu-id="888cb-922">DLS</span></span>
- <span data-ttu-id="888cb-923">采用</span><span class="sxs-lookup"><span data-stu-id="888cb-923">CDL</span></span>
- <span data-ttu-id="888cb-924">CDLS</span><span class="sxs-lookup"><span data-stu-id="888cb-924">CDLS</span></span>
- <span data-ttu-id="888cb-925">DriverLic</span><span class="sxs-lookup"><span data-stu-id="888cb-925">DriverLic</span></span>
- <span data-ttu-id="888cb-926">DriverLics</span><span class="sxs-lookup"><span data-stu-id="888cb-926">DriverLics</span></span>
- <span data-ttu-id="888cb-927">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="888cb-927">DriverLicense</span></span>
- <span data-ttu-id="888cb-928">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="888cb-928">DriverLicenses</span></span>
- <span data-ttu-id="888cb-929">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="888cb-929">DriverLicence</span></span>
- <span data-ttu-id="888cb-930">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="888cb-930">DriverLicences</span></span>
- <span data-ttu-id="888cb-931">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="888cb-931">Driver Lic</span></span>
- <span data-ttu-id="888cb-932">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="888cb-932">Driver Lics</span></span>
- <span data-ttu-id="888cb-933">Driver License</span><span class="sxs-lookup"><span data-stu-id="888cb-933">Driver License</span></span>
- <span data-ttu-id="888cb-934">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="888cb-934">Driver Licenses</span></span>
- <span data-ttu-id="888cb-935">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="888cb-935">Driver Licence</span></span>
- <span data-ttu-id="888cb-936">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="888cb-936">Driver Licences</span></span>
- <span data-ttu-id="888cb-937">DriversLic</span><span class="sxs-lookup"><span data-stu-id="888cb-937">DriversLic</span></span>
- <span data-ttu-id="888cb-938">DriversLics</span><span class="sxs-lookup"><span data-stu-id="888cb-938">DriversLics</span></span>
- <span data-ttu-id="888cb-939">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="888cb-939">DriversLicence</span></span>
- <span data-ttu-id="888cb-940">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="888cb-940">DriversLicences</span></span>
- <span data-ttu-id="888cb-941">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="888cb-941">DriversLicense</span></span>
- <span data-ttu-id="888cb-942">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="888cb-942">DriversLicenses</span></span>
- <span data-ttu-id="888cb-943">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="888cb-943">Drivers Lic</span></span>
- <span data-ttu-id="888cb-944">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="888cb-944">Drivers Lics</span></span>
- <span data-ttu-id="888cb-945">Drivers License</span><span class="sxs-lookup"><span data-stu-id="888cb-945">Drivers License</span></span>
- <span data-ttu-id="888cb-946">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="888cb-946">Drivers Licenses</span></span>
- <span data-ttu-id="888cb-947">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="888cb-947">Drivers Licence</span></span>
- <span data-ttu-id="888cb-948">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="888cb-948">Drivers Licences</span></span>
- <span data-ttu-id="888cb-949">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="888cb-949">Driver'Lic</span></span>
- <span data-ttu-id="888cb-950">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="888cb-950">Driver'Lics</span></span>
- <span data-ttu-id="888cb-951">Driver'License</span><span class="sxs-lookup"><span data-stu-id="888cb-951">Driver'License</span></span>
- <span data-ttu-id="888cb-952">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="888cb-952">Driver'Licenses</span></span>
- <span data-ttu-id="888cb-953">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="888cb-953">Driver'Licence</span></span>
- <span data-ttu-id="888cb-954">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="888cb-954">Driver'Licences</span></span>
- <span data-ttu-id="888cb-955">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="888cb-955">Driver' Lic</span></span>
- <span data-ttu-id="888cb-956">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="888cb-956">Driver' Lics</span></span>
- <span data-ttu-id="888cb-957">Driver' License</span><span class="sxs-lookup"><span data-stu-id="888cb-957">Driver' License</span></span>
- <span data-ttu-id="888cb-958">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="888cb-958">Driver' Licenses</span></span>
- <span data-ttu-id="888cb-959">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="888cb-959">Driver' Licence</span></span>
- <span data-ttu-id="888cb-960">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="888cb-960">Driver' Licences</span></span>
- <span data-ttu-id="888cb-961">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="888cb-961">Driver'sLic</span></span>
- <span data-ttu-id="888cb-962">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="888cb-962">Driver'sLics</span></span>
- <span data-ttu-id="888cb-963">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="888cb-963">Driver'sLicense</span></span>
- <span data-ttu-id="888cb-964">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="888cb-964">Driver'sLicenses</span></span>
- <span data-ttu-id="888cb-965">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="888cb-965">Driver'sLicence</span></span>
- <span data-ttu-id="888cb-966">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="888cb-966">Driver'sLicences</span></span>
- <span data-ttu-id="888cb-967">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="888cb-967">Driver's Lic</span></span>
- <span data-ttu-id="888cb-968">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="888cb-968">Driver's Lics</span></span>
- <span data-ttu-id="888cb-969">Driver's License</span><span class="sxs-lookup"><span data-stu-id="888cb-969">Driver's License</span></span>
- <span data-ttu-id="888cb-970">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="888cb-970">Driver's Licenses</span></span>
- <span data-ttu-id="888cb-971">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="888cb-971">Driver's Licence</span></span>
- <span data-ttu-id="888cb-972">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="888cb-972">Driver's Licences</span></span>
- <span data-ttu-id="888cb-973">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="888cb-973">Permis de Conduire</span></span>
- <span data-ttu-id="888cb-974">id</span><span class="sxs-lookup"><span data-stu-id="888cb-974">id</span></span>
- <span data-ttu-id="888cb-975">ids</span><span class="sxs-lookup"><span data-stu-id="888cb-975">ids</span></span>
- <span data-ttu-id="888cb-976">idcard number</span><span class="sxs-lookup"><span data-stu-id="888cb-976">idcard number</span></span>
- <span data-ttu-id="888cb-977">idcard numbers</span><span class="sxs-lookup"><span data-stu-id="888cb-977">idcard numbers</span></span>
- <span data-ttu-id="888cb-978">idcard #</span><span class="sxs-lookup"><span data-stu-id="888cb-978">idcard #</span></span>
- <span data-ttu-id="888cb-979">idcard #s</span><span class="sxs-lookup"><span data-stu-id="888cb-979">idcard #s</span></span>
- <span data-ttu-id="888cb-980">idcard card</span><span class="sxs-lookup"><span data-stu-id="888cb-980">idcard card</span></span>
- <span data-ttu-id="888cb-981">idcard cards</span><span class="sxs-lookup"><span data-stu-id="888cb-981">idcard cards</span></span>
- <span data-ttu-id="888cb-982">idcard</span><span class="sxs-lookup"><span data-stu-id="888cb-982">idcard</span></span>
- <span data-ttu-id="888cb-983">identification number</span><span class="sxs-lookup"><span data-stu-id="888cb-983">identification number</span></span>
- <span data-ttu-id="888cb-984">identification numbers</span><span class="sxs-lookup"><span data-stu-id="888cb-984">identification numbers</span></span>
- <span data-ttu-id="888cb-985">identification #</span><span class="sxs-lookup"><span data-stu-id="888cb-985">identification #</span></span>
- <span data-ttu-id="888cb-986">identification #s</span><span class="sxs-lookup"><span data-stu-id="888cb-986">identification #s</span></span>
- <span data-ttu-id="888cb-987">identification card</span><span class="sxs-lookup"><span data-stu-id="888cb-987">identification card</span></span>
- <span data-ttu-id="888cb-988">identification cards</span><span class="sxs-lookup"><span data-stu-id="888cb-988">identification cards</span></span>
- <span data-ttu-id="888cb-989">id</span><span class="sxs-lookup"><span data-stu-id="888cb-989">identification</span></span> 
- <span data-ttu-id="888cb-990">通讯</span><span class="sxs-lookup"><span data-stu-id="888cb-990">DL#</span></span>
- <span data-ttu-id="888cb-991">DLS</span><span class="sxs-lookup"><span data-stu-id="888cb-991">DLS#</span></span> 
- <span data-ttu-id="888cb-992">采用</span><span class="sxs-lookup"><span data-stu-id="888cb-992">CDL#</span></span> 
- <span data-ttu-id="888cb-993">CDLS #</span><span class="sxs-lookup"><span data-stu-id="888cb-993">CDLS#</span></span> 
- <span data-ttu-id="888cb-994">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="888cb-994">DriverLic#</span></span> 
- <span data-ttu-id="888cb-995">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="888cb-995">DriverLics#</span></span> 
- <span data-ttu-id="888cb-996">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="888cb-996">DriverLicense#</span></span> 
- <span data-ttu-id="888cb-997">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="888cb-997">DriverLicenses#</span></span> 
- <span data-ttu-id="888cb-998">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="888cb-998">DriverLicence#</span></span> 
- <span data-ttu-id="888cb-999">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="888cb-999">DriverLicences#</span></span> 
- <span data-ttu-id="888cb-1000">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="888cb-1000">Driver Lic#</span></span>
- <span data-ttu-id="888cb-1001">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="888cb-1001">Driver Lics#</span></span> 
- <span data-ttu-id="888cb-1002">Driver License#</span><span class="sxs-lookup"><span data-stu-id="888cb-1002">Driver License#</span></span> 
- <span data-ttu-id="888cb-1003">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="888cb-1003">Driver Licenses#</span></span> 
- <span data-ttu-id="888cb-1004">Driver License#</span><span class="sxs-lookup"><span data-stu-id="888cb-1004">Driver License#</span></span> 
- <span data-ttu-id="888cb-1005">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="888cb-1005">Driver Licences#</span></span> 
- <span data-ttu-id="888cb-1006">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="888cb-1006">DriversLic#</span></span> 
- <span data-ttu-id="888cb-1007">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="888cb-1007">DriversLics#</span></span> 
- <span data-ttu-id="888cb-1008">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="888cb-1008">DriversLicense#</span></span> 
- <span data-ttu-id="888cb-1009">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="888cb-1009">DriversLicenses#</span></span> 
- <span data-ttu-id="888cb-1010">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="888cb-1010">DriversLicence#</span></span> 
- <span data-ttu-id="888cb-1011">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="888cb-1011">DriversLicences#</span></span> 
- <span data-ttu-id="888cb-1012">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="888cb-1012">Drivers Lic#</span></span> 
- <span data-ttu-id="888cb-1013">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="888cb-1013">Drivers Lics#</span></span> 
- <span data-ttu-id="888cb-1014">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="888cb-1014">Drivers License#</span></span> 
- <span data-ttu-id="888cb-1015">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="888cb-1015">Drivers Licenses#</span></span> 
- <span data-ttu-id="888cb-1016">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="888cb-1016">Drivers Licence#</span></span> 
- <span data-ttu-id="888cb-1017">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="888cb-1017">Drivers Licences#</span></span> 
- <span data-ttu-id="888cb-1018">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="888cb-1018">Driver'Lic#</span></span> 
- <span data-ttu-id="888cb-1019">Driver'Lics #</span><span class="sxs-lookup"><span data-stu-id="888cb-1019">Driver'Lics#</span></span> 
- <span data-ttu-id="888cb-1020">Driver'License #</span><span class="sxs-lookup"><span data-stu-id="888cb-1020">Driver'License#</span></span> 
- <span data-ttu-id="888cb-1021">Driver'Licenses #</span><span class="sxs-lookup"><span data-stu-id="888cb-1021">Driver'Licenses#</span></span> 
- <span data-ttu-id="888cb-1022">Driver'Licence #</span><span class="sxs-lookup"><span data-stu-id="888cb-1022">Driver'Licence#</span></span> 
- <span data-ttu-id="888cb-1023">Driver'Licences #</span><span class="sxs-lookup"><span data-stu-id="888cb-1023">Driver'Licences#</span></span> 
- <span data-ttu-id="888cb-1024">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="888cb-1024">Driver' Lic#</span></span> 
- <span data-ttu-id="888cb-1025">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="888cb-1025">Driver' Lics#</span></span> 
- <span data-ttu-id="888cb-1026">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="888cb-1026">Driver' License#</span></span> 
- <span data-ttu-id="888cb-1027">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="888cb-1027">Driver' Licenses#</span></span> 
- <span data-ttu-id="888cb-1028">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="888cb-1028">Driver' Licence#</span></span> 
- <span data-ttu-id="888cb-1029">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="888cb-1029">Driver' Licences#</span></span> 
- <span data-ttu-id="888cb-1030">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="888cb-1030">Driver'sLic#</span></span> 
- <span data-ttu-id="888cb-1031">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="888cb-1031">Driver'sLics#</span></span> 
- <span data-ttu-id="888cb-1032">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="888cb-1032">Driver'sLicense#</span></span> 
- <span data-ttu-id="888cb-1033">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="888cb-1033">Driver'sLicenses#</span></span> 
- <span data-ttu-id="888cb-1034">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="888cb-1034">Driver'sLicence#</span></span> 
- <span data-ttu-id="888cb-1035">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="888cb-1035">Driver'sLicences#</span></span> 
- <span data-ttu-id="888cb-1036">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="888cb-1036">Driver's Lic#</span></span> 
- <span data-ttu-id="888cb-1037">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="888cb-1037">Driver's Lics#</span></span> 
- <span data-ttu-id="888cb-1038">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="888cb-1038">Driver's License#</span></span> 
- <span data-ttu-id="888cb-1039">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="888cb-1039">Driver's Licenses#</span></span> 
- <span data-ttu-id="888cb-1040">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="888cb-1040">Driver's Licence#</span></span> 
- <span data-ttu-id="888cb-1041">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="888cb-1041">Driver's Licences#</span></span> 
- <span data-ttu-id="888cb-1042">Permis de Conduire#</span><span class="sxs-lookup"><span data-stu-id="888cb-1042">Permis de Conduire#</span></span> 
- <span data-ttu-id="888cb-1043">号</span><span class="sxs-lookup"><span data-stu-id="888cb-1043">id#</span></span> 
- <span data-ttu-id="888cb-1044">id</span><span class="sxs-lookup"><span data-stu-id="888cb-1044">ids#</span></span> 
- <span data-ttu-id="888cb-1045">idcard card#</span><span class="sxs-lookup"><span data-stu-id="888cb-1045">idcard card#</span></span> 
- <span data-ttu-id="888cb-1046">idcard cards#</span><span class="sxs-lookup"><span data-stu-id="888cb-1046">idcard cards#</span></span> 
- <span data-ttu-id="888cb-1047">idcard #</span><span class="sxs-lookup"><span data-stu-id="888cb-1047">idcard#</span></span> 
- <span data-ttu-id="888cb-1048">identification card#</span><span class="sxs-lookup"><span data-stu-id="888cb-1048">identification card#</span></span> 
- <span data-ttu-id="888cb-1049">identification cards#</span><span class="sxs-lookup"><span data-stu-id="888cb-1049">identification cards#</span></span> 
- <span data-ttu-id="888cb-1050">id</span><span class="sxs-lookup"><span data-stu-id="888cb-1050">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="888cb-1051">加拿大卫生服务号</span><span class="sxs-lookup"><span data-stu-id="888cb-1051">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-1052">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-1052">Format</span></span>

<span data-ttu-id="888cb-1053">10 个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-1053">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-1054">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-1054">Pattern</span></span>

<span data-ttu-id="888cb-1055">10 个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-1055">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-1056">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-1056">Checksum</span></span>

<span data-ttu-id="888cb-1057">否</span><span class="sxs-lookup"><span data-stu-id="888cb-1057">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-1058">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-1058">Definition</span></span>

<span data-ttu-id="888cb-1059">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-1059">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-1060">正则表达式 Regex_canada_health_service_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-1060">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-1061">找到 Keyword_canada_health_service_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-1061">A keyword from Keyword_canada_health_service_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-1062">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-1062">Keywords</span></span>

#### <a name="keywordcanadahealthservicenumber"></a><span data-ttu-id="888cb-1063">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="888cb-1063">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="888cb-1064">personal health number</span><span class="sxs-lookup"><span data-stu-id="888cb-1064">personal health number</span></span>
- <span data-ttu-id="888cb-1065">patient information</span><span class="sxs-lookup"><span data-stu-id="888cb-1065">patient information</span></span>
- <span data-ttu-id="888cb-1066">health services</span><span class="sxs-lookup"><span data-stu-id="888cb-1066">health services</span></span>
- <span data-ttu-id="888cb-1067">speciality services</span><span class="sxs-lookup"><span data-stu-id="888cb-1067">speciality services</span></span>
- <span data-ttu-id="888cb-1068">automobile accident</span><span class="sxs-lookup"><span data-stu-id="888cb-1068">automobile accident</span></span>
- <span data-ttu-id="888cb-1069">patient hospital</span><span class="sxs-lookup"><span data-stu-id="888cb-1069">patient hospital</span></span>
- <span data-ttu-id="888cb-1070">psychiatrist</span><span class="sxs-lookup"><span data-stu-id="888cb-1070">psychiatrist</span></span>
- <span data-ttu-id="888cb-1071">workers compensation</span><span class="sxs-lookup"><span data-stu-id="888cb-1071">workers compensation</span></span>
- <span data-ttu-id="888cb-1072">障碍</span><span class="sxs-lookup"><span data-stu-id="888cb-1072">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="888cb-1073">加拿大护照号码</span><span class="sxs-lookup"><span data-stu-id="888cb-1073">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-1074">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-1074">Format</span></span>

<span data-ttu-id="888cb-1075">两个大写字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-1075">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-1076">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-1076">Pattern</span></span>

<span data-ttu-id="888cb-1077">两个大写字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-1077">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-1078">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-1078">Checksum</span></span>

<span data-ttu-id="888cb-1079">否</span><span class="sxs-lookup"><span data-stu-id="888cb-1079">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-1080">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-1080">Definition</span></span>

<span data-ttu-id="888cb-1081">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-1081">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-1082">正则表达式 Regex_canada_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-1082">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-1083">找到来自 Keyword_canada_passport_number 或 Keyword_passport 的关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-1083">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-1084">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-1084">Keywords</span></span>

#### <a name="keywordcanadapassportnumber"></a><span data-ttu-id="888cb-1085">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="888cb-1085">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="888cb-1086">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="888cb-1086">canadian citizenship</span></span>
- <span data-ttu-id="888cb-1087">canadian passport</span><span class="sxs-lookup"><span data-stu-id="888cb-1087">canadian passport</span></span>
- <span data-ttu-id="888cb-1088">passport application</span><span class="sxs-lookup"><span data-stu-id="888cb-1088">passport application</span></span>
- <span data-ttu-id="888cb-1089">passport photos</span><span class="sxs-lookup"><span data-stu-id="888cb-1089">passport photos</span></span>
- <span data-ttu-id="888cb-1090">certified translator</span><span class="sxs-lookup"><span data-stu-id="888cb-1090">certified translator</span></span>
- <span data-ttu-id="888cb-1091">canadian citizens</span><span class="sxs-lookup"><span data-stu-id="888cb-1091">canadian citizens</span></span>
- <span data-ttu-id="888cb-1092">processing times</span><span class="sxs-lookup"><span data-stu-id="888cb-1092">processing times</span></span>
- <span data-ttu-id="888cb-1093">renewal application</span><span class="sxs-lookup"><span data-stu-id="888cb-1093">renewal application</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="888cb-1094">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="888cb-1094">Keyword_passport</span></span>

- <span data-ttu-id="888cb-1095">Passport Number</span><span class="sxs-lookup"><span data-stu-id="888cb-1095">Passport Number</span></span>
- <span data-ttu-id="888cb-1096">Passport No</span><span class="sxs-lookup"><span data-stu-id="888cb-1096">Passport No</span></span>
- <span data-ttu-id="888cb-1097">Passport #</span><span class="sxs-lookup"><span data-stu-id="888cb-1097">Passport #</span></span>
- <span data-ttu-id="888cb-1098">登记卡</span><span class="sxs-lookup"><span data-stu-id="888cb-1098">Passport#</span></span>
- <span data-ttu-id="888cb-1099">PassportID</span><span class="sxs-lookup"><span data-stu-id="888cb-1099">PassportID</span></span>
- <span data-ttu-id="888cb-1100">Passportno</span><span class="sxs-lookup"><span data-stu-id="888cb-1100">Passportno</span></span>
- <span data-ttu-id="888cb-1101">passportnumber</span><span class="sxs-lookup"><span data-stu-id="888cb-1101">passportnumber</span></span>
- <span data-ttu-id="888cb-1102">パスポート</span><span class="sxs-lookup"><span data-stu-id="888cb-1102">パスポート</span></span>
- <span data-ttu-id="888cb-1103">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="888cb-1103">パスポート番号</span></span>
- <span data-ttu-id="888cb-1104">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="888cb-1104">パスポートのNum</span></span>
- <span data-ttu-id="888cb-1105">パスポート #</span><span class="sxs-lookup"><span data-stu-id="888cb-1105">パスポート＃</span></span>
- <span data-ttu-id="888cb-1106">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="888cb-1106">Numéro de passeport</span></span>
- <span data-ttu-id="888cb-1107">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="888cb-1107">Passeport n °</span></span>
- <span data-ttu-id="888cb-1108">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="888cb-1108">Passeport Non</span></span>
- <span data-ttu-id="888cb-1109">Passeport #</span><span class="sxs-lookup"><span data-stu-id="888cb-1109">Passeport #</span></span>
- <span data-ttu-id="888cb-1110">Passeport #</span><span class="sxs-lookup"><span data-stu-id="888cb-1110">Passeport#</span></span>
- <span data-ttu-id="888cb-1111">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="888cb-1111">PasseportNon</span></span>
- <span data-ttu-id="888cb-1112">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="888cb-1112">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="888cb-1113">加拿大个人健康标识号 (PHIN)</span><span class="sxs-lookup"><span data-stu-id="888cb-1113">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="888cb-1114">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-1114">Format</span></span>

<span data-ttu-id="888cb-1115">九个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-1115">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-1116">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-1116">Pattern</span></span>

<span data-ttu-id="888cb-1117">九个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-1117">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-1118">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-1118">Checksum</span></span>

<span data-ttu-id="888cb-1119">否</span><span class="sxs-lookup"><span data-stu-id="888cb-1119">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-1120">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-1120">Definition</span></span>

<span data-ttu-id="888cb-1121">DLP 策略 75% 确信在300个字符的邻近度内检测到此类型的敏感信息: 正则表达式 Regex_canada_phin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-1121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="888cb-1122">找到 Keyword_canada_phin 或 Keyword_canada_provinces 中至少有两个关键字。。</span><span class="sxs-lookup"><span data-stu-id="888cb-1122">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-1123">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-1123">Keywords</span></span>

#### <a name="keywordcanadaphin"></a><span data-ttu-id="888cb-1124">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="888cb-1124">Keyword_canada_phin</span></span>

- <span data-ttu-id="888cb-1125">social insurance number</span><span class="sxs-lookup"><span data-stu-id="888cb-1125">social insurance number</span></span>
- <span data-ttu-id="888cb-1126">health information act</span><span class="sxs-lookup"><span data-stu-id="888cb-1126">health information act</span></span>
- <span data-ttu-id="888cb-1127">income tax information</span><span class="sxs-lookup"><span data-stu-id="888cb-1127">income tax information</span></span>
- <span data-ttu-id="888cb-1128">manitoba health</span><span class="sxs-lookup"><span data-stu-id="888cb-1128">manitoba health</span></span>
- <span data-ttu-id="888cb-1129">health registration</span><span class="sxs-lookup"><span data-stu-id="888cb-1129">health registration</span></span>
- <span data-ttu-id="888cb-1130">prescription purchases</span><span class="sxs-lookup"><span data-stu-id="888cb-1130">prescription purchases</span></span>
- <span data-ttu-id="888cb-1131">benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="888cb-1131">benefit eligibility</span></span>
- <span data-ttu-id="888cb-1132">personal health</span><span class="sxs-lookup"><span data-stu-id="888cb-1132">personal health</span></span>
- <span data-ttu-id="888cb-1133">power of attorney</span><span class="sxs-lookup"><span data-stu-id="888cb-1133">power of attorney</span></span>
- <span data-ttu-id="888cb-1134">registration number</span><span class="sxs-lookup"><span data-stu-id="888cb-1134">registration number</span></span>
- <span data-ttu-id="888cb-1135">personal health number</span><span class="sxs-lookup"><span data-stu-id="888cb-1135">personal health number</span></span>
- <span data-ttu-id="888cb-1136">practitioner referral</span><span class="sxs-lookup"><span data-stu-id="888cb-1136">practitioner referral</span></span>
- <span data-ttu-id="888cb-1137">wellness professional</span><span class="sxs-lookup"><span data-stu-id="888cb-1137">wellness professional</span></span>
- <span data-ttu-id="888cb-1138">patient referral</span><span class="sxs-lookup"><span data-stu-id="888cb-1138">patient referral</span></span>
- <span data-ttu-id="888cb-1139">health and wellness</span><span class="sxs-lookup"><span data-stu-id="888cb-1139">health and wellness</span></span>

#### <a name="keywordcanadaprovinces"></a><span data-ttu-id="888cb-1140">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="888cb-1140">Keyword_canada_provinces</span></span>

- <span data-ttu-id="888cb-1141">Nunavut</span><span class="sxs-lookup"><span data-stu-id="888cb-1141">Nunavut</span></span>
- <span data-ttu-id="888cb-1142">省</span><span class="sxs-lookup"><span data-stu-id="888cb-1142">Quebec</span></span>
- <span data-ttu-id="888cb-1143">Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="888cb-1143">Northwest Territories</span></span>
- <span data-ttu-id="888cb-1144">省</span><span class="sxs-lookup"><span data-stu-id="888cb-1144">Ontario</span></span>
- <span data-ttu-id="888cb-1145">British Columbia</span><span class="sxs-lookup"><span data-stu-id="888cb-1145">British Columbia</span></span>
- <span data-ttu-id="888cb-1146">Alberta</span><span class="sxs-lookup"><span data-stu-id="888cb-1146">Alberta</span></span>
- <span data-ttu-id="888cb-1147">彻</span><span class="sxs-lookup"><span data-stu-id="888cb-1147">Saskatchewan</span></span>
- <span data-ttu-id="888cb-1148">Manitoba</span><span class="sxs-lookup"><span data-stu-id="888cb-1148">Manitoba</span></span>
- <span data-ttu-id="888cb-1149">Yukon</span><span class="sxs-lookup"><span data-stu-id="888cb-1149">Yukon</span></span>
- <span data-ttu-id="888cb-1150">Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="888cb-1150">Newfoundland and Labrador</span></span>
- <span data-ttu-id="888cb-1151">New Brunswick</span><span class="sxs-lookup"><span data-stu-id="888cb-1151">New Brunswick</span></span>
- <span data-ttu-id="888cb-1152">Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="888cb-1152">Nova Scotia</span></span>
- <span data-ttu-id="888cb-1153">Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="888cb-1153">Prince Edward Island</span></span>
- <span data-ttu-id="888cb-1154">加拿大</span><span class="sxs-lookup"><span data-stu-id="888cb-1154">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="888cb-1155">加拿大社会保险号码</span><span class="sxs-lookup"><span data-stu-id="888cb-1155">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-1156">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-1156">Format</span></span>

<span data-ttu-id="888cb-1157">九个数字，包含可选连字符或空格</span><span class="sxs-lookup"><span data-stu-id="888cb-1157">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-1158">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-1158">Pattern</span></span>

<span data-ttu-id="888cb-1159">格式</span><span class="sxs-lookup"><span data-stu-id="888cb-1159">Formatted:</span></span>
- <span data-ttu-id="888cb-1160">三位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-1160">Three digits</span></span> 
- <span data-ttu-id="888cb-1161">连字符或空格</span><span class="sxs-lookup"><span data-stu-id="888cb-1161">A hyphen or space</span></span> 
- <span data-ttu-id="888cb-1162">三位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-1162">Three digits</span></span> 
- <span data-ttu-id="888cb-1163">连字符或空格</span><span class="sxs-lookup"><span data-stu-id="888cb-1163">A hyphen or space</span></span> 
- <span data-ttu-id="888cb-1164">三位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-1164">Three digits</span></span>

<span data-ttu-id="888cb-1165">未格式化: 9 个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-1165">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-1166">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-1166">Checksum</span></span>

<span data-ttu-id="888cb-1167">是</span><span class="sxs-lookup"><span data-stu-id="888cb-1167">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-1168">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-1168">Definition</span></span>

<span data-ttu-id="888cb-1169">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-1169">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-1170">函数 Func_canadian_sin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-1170">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-1171">至少两个以下任意组合：</span><span class="sxs-lookup"><span data-stu-id="888cb-1171">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="888cb-1172">找到 Keyword_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-1172">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="888cb-1173">找到 Keyword_sin_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-1173">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="888cb-1174">函数 Func_eu_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="888cb-1174">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="888cb-1175">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-1175">The checksum passes.</span></span>

<span data-ttu-id="888cb-1176">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-1176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-1177">函数 Func_unformatted_canadian_sin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-1177">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-1178">找到 Keyword_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-1178">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="888cb-1179">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-1179">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-1180">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-1180">Keywords</span></span>

#### <a name="keywordsin"></a><span data-ttu-id="888cb-1181">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="888cb-1181">Keyword_sin</span></span>

- <span data-ttu-id="888cb-1182">sin</span><span class="sxs-lookup"><span data-stu-id="888cb-1182">sin</span></span> 
- <span data-ttu-id="888cb-1183">social insurance</span><span class="sxs-lookup"><span data-stu-id="888cb-1183">social insurance</span></span> 
- <span data-ttu-id="888cb-1184">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="888cb-1184">numero d'assurance sociale</span></span> 
- <span data-ttu-id="888cb-1185">罪</span><span class="sxs-lookup"><span data-stu-id="888cb-1185">sins</span></span> 
- <span data-ttu-id="888cb-1186">ssn</span><span class="sxs-lookup"><span data-stu-id="888cb-1186">ssn</span></span> 
- <span data-ttu-id="888cb-1187">ssn</span><span class="sxs-lookup"><span data-stu-id="888cb-1187">ssns</span></span> 
- <span data-ttu-id="888cb-1188">social security</span><span class="sxs-lookup"><span data-stu-id="888cb-1188">social security</span></span> 
- <span data-ttu-id="888cb-1189">numero d'assurance social</span><span class="sxs-lookup"><span data-stu-id="888cb-1189">numero d'assurance social</span></span> 
- <span data-ttu-id="888cb-1190">national identification number</span><span class="sxs-lookup"><span data-stu-id="888cb-1190">national identification number</span></span> 
- <span data-ttu-id="888cb-1191">national id</span><span class="sxs-lookup"><span data-stu-id="888cb-1191">national id</span></span> 
- <span data-ttu-id="888cb-1192">sin</span><span class="sxs-lookup"><span data-stu-id="888cb-1192">sin#</span></span> 
- <span data-ttu-id="888cb-1193">soc ins</span><span class="sxs-lookup"><span data-stu-id="888cb-1193">soc ins</span></span> 
- <span data-ttu-id="888cb-1194">social ins</span><span class="sxs-lookup"><span data-stu-id="888cb-1194">social ins</span></span> 

#### <a name="keywordsincollaborative"></a><span data-ttu-id="888cb-1195">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="888cb-1195">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="888cb-1196">driver's license</span><span class="sxs-lookup"><span data-stu-id="888cb-1196">driver's license</span></span> 
- <span data-ttu-id="888cb-1197">drivers license</span><span class="sxs-lookup"><span data-stu-id="888cb-1197">drivers license</span></span> 
- <span data-ttu-id="888cb-1198">driver's licence</span><span class="sxs-lookup"><span data-stu-id="888cb-1198">driver's licence</span></span> 
- <span data-ttu-id="888cb-1199">drivers licence</span><span class="sxs-lookup"><span data-stu-id="888cb-1199">drivers licence</span></span> 
- <span data-ttu-id="888cb-1200">DOB</span><span class="sxs-lookup"><span data-stu-id="888cb-1200">DOB</span></span> 
- <span data-ttu-id="888cb-1201">出生日期</span><span class="sxs-lookup"><span data-stu-id="888cb-1201">Birthdate</span></span> 
- <span data-ttu-id="888cb-1202">生日</span><span class="sxs-lookup"><span data-stu-id="888cb-1202">Birthday</span></span> 
- <span data-ttu-id="888cb-1203">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="888cb-1203">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="888cb-1204">	智利身份证号</span><span class="sxs-lookup"><span data-stu-id="888cb-1204">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-1205">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-1205">Format</span></span>

<span data-ttu-id="888cb-1206">7-8 位数加上分隔符一个校验位或字母</span><span class="sxs-lookup"><span data-stu-id="888cb-1206">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-1207">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-1207">Pattern</span></span>

<span data-ttu-id="888cb-1208">7-8 个数字加分隔符：</span><span class="sxs-lookup"><span data-stu-id="888cb-1208">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="888cb-1209">1-2 个数字 </span><span class="sxs-lookup"><span data-stu-id="888cb-1209">1-2 digits</span></span> 
- <span data-ttu-id="888cb-1210">一个点 </span><span class="sxs-lookup"><span data-stu-id="888cb-1210">A period</span></span> 
- <span data-ttu-id="888cb-1211">三个数字 </span><span class="sxs-lookup"><span data-stu-id="888cb-1211">Three digits</span></span> 
- <span data-ttu-id="888cb-1212">一个点 </span><span class="sxs-lookup"><span data-stu-id="888cb-1212">A period</span></span> 
- <span data-ttu-id="888cb-1213">三个数字 </span><span class="sxs-lookup"><span data-stu-id="888cb-1213">Three digits</span></span> 
- <span data-ttu-id="888cb-1214">一个短划线 </span><span class="sxs-lookup"><span data-stu-id="888cb-1214">A dash</span></span> 
- <span data-ttu-id="888cb-1215">一个数字或字母（不区分大小写），是校验位</span><span class="sxs-lookup"><span data-stu-id="888cb-1215">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-1216">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-1216">Checksum</span></span>

<span data-ttu-id="888cb-1217">是</span><span class="sxs-lookup"><span data-stu-id="888cb-1217">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-1218">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-1218">Definition</span></span>

<span data-ttu-id="888cb-1219">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-1219">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-1220">函数 Func_chile_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-1220">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-1221">找到 Keyword_chile_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-1221">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="888cb-1222">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-1222">The checksum passes.</span></span>

<span data-ttu-id="888cb-1223">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-1223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-1224">函数 Func_chile_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-1224">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-1225">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-1225">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-1226">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-1226">Keywords</span></span>

#### <a name="keywordchileidcard"></a><span data-ttu-id="888cb-1227">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="888cb-1227">Keyword_chile_id_card</span></span>

- <span data-ttu-id="888cb-1228">National Identification Number</span><span class="sxs-lookup"><span data-stu-id="888cb-1228">National Identification Number</span></span> 
- <span data-ttu-id="888cb-1229">Identity card</span><span class="sxs-lookup"><span data-stu-id="888cb-1229">Identity card</span></span> 
- <span data-ttu-id="888cb-1230">ID</span><span class="sxs-lookup"><span data-stu-id="888cb-1230">ID</span></span> 
- <span data-ttu-id="888cb-1231">id</span><span class="sxs-lookup"><span data-stu-id="888cb-1231">Identification</span></span> 
- <span data-ttu-id="888cb-1232">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="888cb-1232">Rol Único Nacional</span></span> 
- <span data-ttu-id="888cb-1233">以</span><span class="sxs-lookup"><span data-stu-id="888cb-1233">RUN</span></span> 
- <span data-ttu-id="888cb-1234">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="888cb-1234">Rol Único Tributario</span></span> 
- <span data-ttu-id="888cb-1235">墨守成规</span><span class="sxs-lookup"><span data-stu-id="888cb-1235">RUT</span></span> 
- <span data-ttu-id="888cb-1236">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="888cb-1236">Cédula de Identidad</span></span> 
- <span data-ttu-id="888cb-1237">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="888cb-1237">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="888cb-1238">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="888cb-1238">Tarjeta de identificación</span></span> 
- <span data-ttu-id="888cb-1239">Identificación</span><span class="sxs-lookup"><span data-stu-id="888cb-1239">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="888cb-1240">	中国居民身份证号</span><span class="sxs-lookup"><span data-stu-id="888cb-1240">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-1241">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-1241">Format</span></span>

<span data-ttu-id="888cb-1242">18 个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-1242">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-1243">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-1243">Pattern</span></span>

<span data-ttu-id="888cb-1244">18 个数字：</span><span class="sxs-lookup"><span data-stu-id="888cb-1244">18 digits:</span></span>
- <span data-ttu-id="888cb-1245">其中六个数字是地址代码 </span><span class="sxs-lookup"><span data-stu-id="888cb-1245">Six digits which are an address code</span></span> 
- <span data-ttu-id="888cb-1246">八个数字，采用  YYYYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="888cb-1246">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="888cb-1247">三个数字，是顺序代码 </span><span class="sxs-lookup"><span data-stu-id="888cb-1247">Three digits which are an order code</span></span> 
- <span data-ttu-id="888cb-1248">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="888cb-1248">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-1249">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-1249">Checksum</span></span>

<span data-ttu-id="888cb-1250">是</span><span class="sxs-lookup"><span data-stu-id="888cb-1250">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-1251">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-1251">Definition</span></span>

<span data-ttu-id="888cb-1252">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-1252">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-1253">函数 Func_china_resident_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-1253">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-1254">找到 Keyword_china_resident_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-1254">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="888cb-1255">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-1255">The checksum passes.</span></span>

<span data-ttu-id="888cb-1256">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-1256">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-1257">函数 Func_china_resident_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-1257">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-1258">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-1258">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-1259">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-1259">Keywords</span></span>

### <a name="keywordchinaresidentid"></a><span data-ttu-id="888cb-1260">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="888cb-1260">Keyword_china_resident_id</span></span>

- <span data-ttu-id="888cb-1261">Resident Identity Card</span><span class="sxs-lookup"><span data-stu-id="888cb-1261">Resident Identity Card</span></span> 
- <span data-ttu-id="888cb-1262">台湾</span><span class="sxs-lookup"><span data-stu-id="888cb-1262">PRC</span></span> 
- <span data-ttu-id="888cb-1263">National Identification Card</span><span class="sxs-lookup"><span data-stu-id="888cb-1263">National Identification Card</span></span> 
- <span data-ttu-id="888cb-1264">身份证</span><span class="sxs-lookup"><span data-stu-id="888cb-1264">身份证</span></span> 
- <span data-ttu-id="888cb-1265">居民 身份证</span><span class="sxs-lookup"><span data-stu-id="888cb-1265">居民 身份证</span></span> 
- <span data-ttu-id="888cb-1266">居民身份证</span><span class="sxs-lookup"><span data-stu-id="888cb-1266">居民身份证</span></span> 
- <span data-ttu-id="888cb-1267">鉴定</span><span class="sxs-lookup"><span data-stu-id="888cb-1267">鉴定</span></span> 
- <span data-ttu-id="888cb-1268">身分證</span><span class="sxs-lookup"><span data-stu-id="888cb-1268">身分證</span></span> 
- <span data-ttu-id="888cb-1269">居民身份證</span><span class="sxs-lookup"><span data-stu-id="888cb-1269">居民 身份證</span></span>
- <span data-ttu-id="888cb-1270">鑑定</span><span class="sxs-lookup"><span data-stu-id="888cb-1270">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="888cb-1271">信用卡号</span><span class="sxs-lookup"><span data-stu-id="888cb-1271">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-1272">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-1272">Format</span></span>

<span data-ttu-id="888cb-1273">16个数字, 可以是格式化或无格式 (dddddddddddddddd), 并且必须通过 Luhn 测试。</span><span class="sxs-lookup"><span data-stu-id="888cb-1273">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-1274">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-1274">Pattern</span></span>

<span data-ttu-id="888cb-1275">非常复杂且强大的模式，检测到来自世界各地所有重要品牌的卡，包括 Visa、万事达卡、发现卡、JCB卡、美国运通卡、礼品卡以及大莱卡。</span><span class="sxs-lookup"><span data-stu-id="888cb-1275">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-1276">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-1276">Checksum</span></span>

<span data-ttu-id="888cb-1277">是，Luhn 校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-1277">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-1278">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-1278">Definition</span></span>

<span data-ttu-id="888cb-1279">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-1279">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-1280">函数 Func_credit_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-1280">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-1281">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="888cb-1281">One of the following is true:</span></span>
    - <span data-ttu-id="888cb-1282">找到 Keyword_cc_verification 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-1282">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="888cb-1283">找到 Keyword_cc_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-1283">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="888cb-1284">函数 Func_expiration_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="888cb-1284">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="888cb-1285">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-1285">The checksum passes.</span></span>

<span data-ttu-id="888cb-1286">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-1286">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-1287">函数 Func_credit_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-1287">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-1288">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-1288">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-1289">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-1289">Keywords</span></span>

#### <a name="keywordccverification"></a><span data-ttu-id="888cb-1290">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="888cb-1290">Keyword_cc_verification</span></span>

- <span data-ttu-id="888cb-1291">card verification</span><span class="sxs-lookup"><span data-stu-id="888cb-1291">card verification</span></span>
- <span data-ttu-id="888cb-1292">card identification number</span><span class="sxs-lookup"><span data-stu-id="888cb-1292">card identification number</span></span>
- <span data-ttu-id="888cb-1293">cvn</span><span class="sxs-lookup"><span data-stu-id="888cb-1293">cvn</span></span>
- <span data-ttu-id="888cb-1294">cid</span><span class="sxs-lookup"><span data-stu-id="888cb-1294">cid</span></span>
- <span data-ttu-id="888cb-1295">cvc2</span><span class="sxs-lookup"><span data-stu-id="888cb-1295">cvc2</span></span>
- <span data-ttu-id="888cb-1296">cvv2</span><span class="sxs-lookup"><span data-stu-id="888cb-1296">cvv2</span></span>
- <span data-ttu-id="888cb-1297">pin block</span><span class="sxs-lookup"><span data-stu-id="888cb-1297">pin block</span></span>
- <span data-ttu-id="888cb-1298">security code</span><span class="sxs-lookup"><span data-stu-id="888cb-1298">security code</span></span>
- <span data-ttu-id="888cb-1299">security number</span><span class="sxs-lookup"><span data-stu-id="888cb-1299">security number</span></span>
- <span data-ttu-id="888cb-1300">security no</span><span class="sxs-lookup"><span data-stu-id="888cb-1300">security no</span></span>
- <span data-ttu-id="888cb-1301">issue number</span><span class="sxs-lookup"><span data-stu-id="888cb-1301">issue number</span></span>
- <span data-ttu-id="888cb-1302">issue no</span><span class="sxs-lookup"><span data-stu-id="888cb-1302">issue no</span></span>
- <span data-ttu-id="888cb-1303">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="888cb-1303">cryptogramme</span></span>
- <span data-ttu-id="888cb-1304">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="888cb-1304">numéro de sécurité</span></span>
- <span data-ttu-id="888cb-1305">numero de securite</span><span class="sxs-lookup"><span data-stu-id="888cb-1305">numero de securite</span></span>
- <span data-ttu-id="888cb-1306">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="888cb-1306">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="888cb-1307">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="888cb-1307">kreditkartenprufnummer</span></span>
- <span data-ttu-id="888cb-1308">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="888cb-1308">prüfziffer</span></span>
- <span data-ttu-id="888cb-1309">prufziffer</span><span class="sxs-lookup"><span data-stu-id="888cb-1309">prufziffer</span></span>
- <span data-ttu-id="888cb-1310">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="888cb-1310">sicherheits Kode</span></span>
- <span data-ttu-id="888cb-1311">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="888cb-1311">sicherheitscode</span></span>
- <span data-ttu-id="888cb-1312">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="888cb-1312">sicherheitsnummer</span></span>
- <span data-ttu-id="888cb-1313">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="888cb-1313">verfalldatum</span></span>
- <span data-ttu-id="888cb-1314">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="888cb-1314">codice di verifica</span></span>
- <span data-ttu-id="888cb-1315">货.</span><span class="sxs-lookup"><span data-stu-id="888cb-1315">cod.</span></span> <span data-ttu-id="888cb-1316">sicurezza</span><span class="sxs-lookup"><span data-stu-id="888cb-1316">sicurezza</span></span>
- <span data-ttu-id="888cb-1317">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="888cb-1317">cod sicurezza</span></span>
- <span data-ttu-id="888cb-1318">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="888cb-1318">n autorizzazione</span></span>
- <span data-ttu-id="888cb-1319">código</span><span class="sxs-lookup"><span data-stu-id="888cb-1319">código</span></span>
- <span data-ttu-id="888cb-1320">codigo</span><span class="sxs-lookup"><span data-stu-id="888cb-1320">codigo</span></span>
- <span data-ttu-id="888cb-1321">货.</span><span class="sxs-lookup"><span data-stu-id="888cb-1321">cod.</span></span> <span data-ttu-id="888cb-1322">seg</span><span class="sxs-lookup"><span data-stu-id="888cb-1322">seg</span></span>
- <span data-ttu-id="888cb-1323">cod seg</span><span class="sxs-lookup"><span data-stu-id="888cb-1323">cod seg</span></span>
- <span data-ttu-id="888cb-1324">código de segurança</span><span class="sxs-lookup"><span data-stu-id="888cb-1324">código de segurança</span></span>
- <span data-ttu-id="888cb-1325">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="888cb-1325">codigo de seguranca</span></span>
- <span data-ttu-id="888cb-1326">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="888cb-1326">codigo de segurança</span></span>
- <span data-ttu-id="888cb-1327">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="888cb-1327">código de seguranca</span></span>
- <span data-ttu-id="888cb-1328">cód。</span><span class="sxs-lookup"><span data-stu-id="888cb-1328">cód.</span></span> <span data-ttu-id="888cb-1329">segurança</span><span class="sxs-lookup"><span data-stu-id="888cb-1329">segurança</span></span>
- <span data-ttu-id="888cb-1330">货.</span><span class="sxs-lookup"><span data-stu-id="888cb-1330">cod.</span></span> <span data-ttu-id="888cb-1331">seguranca 货到付款。</span><span class="sxs-lookup"><span data-stu-id="888cb-1331">seguranca cod.</span></span> <span data-ttu-id="888cb-1332">segurança</span><span class="sxs-lookup"><span data-stu-id="888cb-1332">segurança</span></span>
- <span data-ttu-id="888cb-1333">cód。</span><span class="sxs-lookup"><span data-stu-id="888cb-1333">cód.</span></span> <span data-ttu-id="888cb-1334">seguranca</span><span class="sxs-lookup"><span data-stu-id="888cb-1334">seguranca</span></span>
- <span data-ttu-id="888cb-1335">cód segurança</span><span class="sxs-lookup"><span data-stu-id="888cb-1335">cód segurança</span></span>
- <span data-ttu-id="888cb-1336">货到付款 seguranca 货到付款 segurança</span><span class="sxs-lookup"><span data-stu-id="888cb-1336">cod seguranca cod segurança</span></span>
- <span data-ttu-id="888cb-1337">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="888cb-1337">cód seguranca</span></span>
- <span data-ttu-id="888cb-1338">número de verificação</span><span class="sxs-lookup"><span data-stu-id="888cb-1338">número de verificação</span></span>
- <span data-ttu-id="888cb-1339">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="888cb-1339">numero de verificacao</span></span>
- <span data-ttu-id="888cb-1340">ablauf</span><span class="sxs-lookup"><span data-stu-id="888cb-1340">ablauf</span></span>
- <span data-ttu-id="888cb-1341">gültig bis</span><span class="sxs-lookup"><span data-stu-id="888cb-1341">gültig bis</span></span>
- <span data-ttu-id="888cb-1342">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="888cb-1342">gültigkeitsdatum</span></span>
- <span data-ttu-id="888cb-1343">gultig bis</span><span class="sxs-lookup"><span data-stu-id="888cb-1343">gultig bis</span></span>
- <span data-ttu-id="888cb-1344">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="888cb-1344">gultigkeitsdatum</span></span>
- <span data-ttu-id="888cb-1345">scadenza</span><span class="sxs-lookup"><span data-stu-id="888cb-1345">scadenza</span></span>
- <span data-ttu-id="888cb-1346">data scad</span><span class="sxs-lookup"><span data-stu-id="888cb-1346">data scad</span></span>
- <span data-ttu-id="888cb-1347">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="888cb-1347">fecha de expiracion</span></span>
- <span data-ttu-id="888cb-1348">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="888cb-1348">fecha de venc</span></span>
- <span data-ttu-id="888cb-1349">vencimiento</span><span class="sxs-lookup"><span data-stu-id="888cb-1349">vencimiento</span></span>
- <span data-ttu-id="888cb-1350">válido hasta</span><span class="sxs-lookup"><span data-stu-id="888cb-1350">válido hasta</span></span>
- <span data-ttu-id="888cb-1351">valido hasta</span><span class="sxs-lookup"><span data-stu-id="888cb-1351">valido hasta</span></span>
- <span data-ttu-id="888cb-1352">vto</span><span class="sxs-lookup"><span data-stu-id="888cb-1352">vto</span></span>
- <span data-ttu-id="888cb-1353">data de expiração</span><span class="sxs-lookup"><span data-stu-id="888cb-1353">data de expiração</span></span>
- <span data-ttu-id="888cb-1354">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="888cb-1354">data de expiracao</span></span>
- <span data-ttu-id="888cb-1355">data em que expira</span><span class="sxs-lookup"><span data-stu-id="888cb-1355">data em que expira</span></span>
- <span data-ttu-id="888cb-1356">validade</span><span class="sxs-lookup"><span data-stu-id="888cb-1356">validade</span></span>
- <span data-ttu-id="888cb-1357">valor</span><span class="sxs-lookup"><span data-stu-id="888cb-1357">valor</span></span>
- <span data-ttu-id="888cb-1358">vencimento</span><span class="sxs-lookup"><span data-stu-id="888cb-1358">vencimento</span></span>
- <span data-ttu-id="888cb-1359">Venc</span><span class="sxs-lookup"><span data-stu-id="888cb-1359">Venc</span></span> 

#### <a name="keywordccname"></a><span data-ttu-id="888cb-1360">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="888cb-1360">Keyword_cc_name</span></span>

- <span data-ttu-id="888cb-1361">amex</span><span class="sxs-lookup"><span data-stu-id="888cb-1361">amex</span></span>
- <span data-ttu-id="888cb-1362">american express</span><span class="sxs-lookup"><span data-stu-id="888cb-1362">american express</span></span>
- <span data-ttu-id="888cb-1363">americanexpress</span><span class="sxs-lookup"><span data-stu-id="888cb-1363">americanexpress</span></span>
- <span data-ttu-id="888cb-1364">反之</span><span class="sxs-lookup"><span data-stu-id="888cb-1364">Visa</span></span>
- <span data-ttu-id="888cb-1365">mastercard</span><span class="sxs-lookup"><span data-stu-id="888cb-1365">mastercard</span></span>
- <span data-ttu-id="888cb-1366">Master Card</span><span class="sxs-lookup"><span data-stu-id="888cb-1366">master card</span></span>
- <span data-ttu-id="888cb-1367">emc</span><span class="sxs-lookup"><span data-stu-id="888cb-1367">mc</span></span> 
- <span data-ttu-id="888cb-1368">mastercards</span><span class="sxs-lookup"><span data-stu-id="888cb-1368">mastercards</span></span>
- <span data-ttu-id="888cb-1369">master cards</span><span class="sxs-lookup"><span data-stu-id="888cb-1369">master cards</span></span>
- <span data-ttu-id="888cb-1370">diner's Club</span><span class="sxs-lookup"><span data-stu-id="888cb-1370">diner's Club</span></span>
- <span data-ttu-id="888cb-1371">diners club</span><span class="sxs-lookup"><span data-stu-id="888cb-1371">diners club</span></span>
- <span data-ttu-id="888cb-1372">dinersclub</span><span class="sxs-lookup"><span data-stu-id="888cb-1372">dinersclub</span></span>
- <span data-ttu-id="888cb-1373">discover card</span><span class="sxs-lookup"><span data-stu-id="888cb-1373">discover card</span></span>
- <span data-ttu-id="888cb-1374">discovercard</span><span class="sxs-lookup"><span data-stu-id="888cb-1374">discovercard</span></span>
- <span data-ttu-id="888cb-1375">discover cards</span><span class="sxs-lookup"><span data-stu-id="888cb-1375">discover cards</span></span>
- <span data-ttu-id="888cb-1376">JCB</span><span class="sxs-lookup"><span data-stu-id="888cb-1376">JCB</span></span>
- <span data-ttu-id="888cb-1377">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="888cb-1377">japanese card bureau</span></span>
- <span data-ttu-id="888cb-1378">carte blanche</span><span class="sxs-lookup"><span data-stu-id="888cb-1378">carte blanche</span></span>
- <span data-ttu-id="888cb-1379">carteblanche</span><span class="sxs-lookup"><span data-stu-id="888cb-1379">carteblanche</span></span>
- <span data-ttu-id="888cb-1380">credit card</span><span class="sxs-lookup"><span data-stu-id="888cb-1380">credit card</span></span>
- <span data-ttu-id="888cb-1381">收件人</span><span class="sxs-lookup"><span data-stu-id="888cb-1381">cc#</span></span>
- <span data-ttu-id="888cb-1382">cc #:</span><span class="sxs-lookup"><span data-stu-id="888cb-1382">cc#:</span></span>
- <span data-ttu-id="888cb-1383">expiration date</span><span class="sxs-lookup"><span data-stu-id="888cb-1383">expiration date</span></span>
- <span data-ttu-id="888cb-1384">exp date</span><span class="sxs-lookup"><span data-stu-id="888cb-1384">exp date</span></span>
- <span data-ttu-id="888cb-1385">expiry date</span><span class="sxs-lookup"><span data-stu-id="888cb-1385">expiry date</span></span>
- <span data-ttu-id="888cb-1386">date d’expiration</span><span class="sxs-lookup"><span data-stu-id="888cb-1386">date d’expiration</span></span>
- <span data-ttu-id="888cb-1387">date d'exp</span><span class="sxs-lookup"><span data-stu-id="888cb-1387">date d'exp</span></span>
- <span data-ttu-id="888cb-1388">date expiration</span><span class="sxs-lookup"><span data-stu-id="888cb-1388">date expiration</span></span>
- <span data-ttu-id="888cb-1389">bank card</span><span class="sxs-lookup"><span data-stu-id="888cb-1389">bank card</span></span>
- <span data-ttu-id="888cb-1390">bankcard</span><span class="sxs-lookup"><span data-stu-id="888cb-1390">bankcard</span></span>
- <span data-ttu-id="888cb-1391">card number</span><span class="sxs-lookup"><span data-stu-id="888cb-1391">card number</span></span>
- <span data-ttu-id="888cb-1392">card num</span><span class="sxs-lookup"><span data-stu-id="888cb-1392">card num</span></span>
- <span data-ttu-id="888cb-1393">cardnumber</span><span class="sxs-lookup"><span data-stu-id="888cb-1393">cardnumber</span></span>
- <span data-ttu-id="888cb-1394">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="888cb-1394">cardnumbers</span></span>
- <span data-ttu-id="888cb-1395">card numbers</span><span class="sxs-lookup"><span data-stu-id="888cb-1395">card numbers</span></span>
- <span data-ttu-id="888cb-1396">creditcard</span><span class="sxs-lookup"><span data-stu-id="888cb-1396">creditcard</span></span>
- <span data-ttu-id="888cb-1397">credit cards</span><span class="sxs-lookup"><span data-stu-id="888cb-1397">credit cards</span></span>
- <span data-ttu-id="888cb-1398">creditcards</span><span class="sxs-lookup"><span data-stu-id="888cb-1398">creditcards</span></span>
- <span data-ttu-id="888cb-1399">ccn</span><span class="sxs-lookup"><span data-stu-id="888cb-1399">ccn</span></span>
- <span data-ttu-id="888cb-1400">card holder</span><span class="sxs-lookup"><span data-stu-id="888cb-1400">card holder</span></span>
- <span data-ttu-id="888cb-1401">持卡人</span><span class="sxs-lookup"><span data-stu-id="888cb-1401">cardholder</span></span>
- <span data-ttu-id="888cb-1402">card holders</span><span class="sxs-lookup"><span data-stu-id="888cb-1402">card holders</span></span>
- <span data-ttu-id="888cb-1403">cardholders</span><span class="sxs-lookup"><span data-stu-id="888cb-1403">cardholders</span></span>
- <span data-ttu-id="888cb-1404">check card</span><span class="sxs-lookup"><span data-stu-id="888cb-1404">check card</span></span>
- <span data-ttu-id="888cb-1405">checkcard</span><span class="sxs-lookup"><span data-stu-id="888cb-1405">checkcard</span></span>
- <span data-ttu-id="888cb-1406">check cards</span><span class="sxs-lookup"><span data-stu-id="888cb-1406">check cards</span></span>
- <span data-ttu-id="888cb-1407">checkcards</span><span class="sxs-lookup"><span data-stu-id="888cb-1407">checkcards</span></span>
- <span data-ttu-id="888cb-1408">debit card</span><span class="sxs-lookup"><span data-stu-id="888cb-1408">debit card</span></span>
- <span data-ttu-id="888cb-1409">debitcard</span><span class="sxs-lookup"><span data-stu-id="888cb-1409">debitcard</span></span>
- <span data-ttu-id="888cb-1410">debit cards</span><span class="sxs-lookup"><span data-stu-id="888cb-1410">debit cards</span></span>
- <span data-ttu-id="888cb-1411">debitcards</span><span class="sxs-lookup"><span data-stu-id="888cb-1411">debitcards</span></span>
- <span data-ttu-id="888cb-1412">atm card</span><span class="sxs-lookup"><span data-stu-id="888cb-1412">atm card</span></span>
- <span data-ttu-id="888cb-1413">atmcard</span><span class="sxs-lookup"><span data-stu-id="888cb-1413">atmcard</span></span>
- <span data-ttu-id="888cb-1414">atm cards</span><span class="sxs-lookup"><span data-stu-id="888cb-1414">atm cards</span></span>
- <span data-ttu-id="888cb-1415">atmcards</span><span class="sxs-lookup"><span data-stu-id="888cb-1415">atmcards</span></span>
- <span data-ttu-id="888cb-1416">enroute</span><span class="sxs-lookup"><span data-stu-id="888cb-1416">enroute</span></span>
- <span data-ttu-id="888cb-1417">en route</span><span class="sxs-lookup"><span data-stu-id="888cb-1417">en route</span></span>
- <span data-ttu-id="888cb-1418">card type</span><span class="sxs-lookup"><span data-stu-id="888cb-1418">card type</span></span>
- <span data-ttu-id="888cb-1419">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="888cb-1419">carte bancaire</span></span>
- <span data-ttu-id="888cb-1420">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="888cb-1420">carte de crédit</span></span>
- <span data-ttu-id="888cb-1421">carte de credit</span><span class="sxs-lookup"><span data-stu-id="888cb-1421">carte de credit</span></span>
- <span data-ttu-id="888cb-1422">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="888cb-1422">numéro de carte</span></span>
- <span data-ttu-id="888cb-1423">numero de carte</span><span class="sxs-lookup"><span data-stu-id="888cb-1423">numero de carte</span></span>
- <span data-ttu-id="888cb-1424">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="888cb-1424">nº de la carte</span></span>
- <span data-ttu-id="888cb-1425">nº de carte</span><span class="sxs-lookup"><span data-stu-id="888cb-1425">nº de carte</span></span>
- <span data-ttu-id="888cb-1426">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="888cb-1426">kreditkarte</span></span>
- <span data-ttu-id="888cb-1427">karte</span><span class="sxs-lookup"><span data-stu-id="888cb-1427">karte</span></span>
- <span data-ttu-id="888cb-1428">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="888cb-1428">karteninhaber</span></span>
- <span data-ttu-id="888cb-1429">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="888cb-1429">karteninhabers</span></span>
- <span data-ttu-id="888cb-1430">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="888cb-1430">kreditkarteninhaber</span></span>
- <span data-ttu-id="888cb-1431">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="888cb-1431">kreditkarteninstitut</span></span>
- <span data-ttu-id="888cb-1432">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="888cb-1432">kreditkartentyp</span></span>
- <span data-ttu-id="888cb-1433">eigentümername</span><span class="sxs-lookup"><span data-stu-id="888cb-1433">eigentümername</span></span>
- <span data-ttu-id="888cb-1434">kartennr</span><span class="sxs-lookup"><span data-stu-id="888cb-1434">kartennr</span></span> 
- <span data-ttu-id="888cb-1435">kartennummer</span><span class="sxs-lookup"><span data-stu-id="888cb-1435">kartennummer</span></span>
- <span data-ttu-id="888cb-1436">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="888cb-1436">kreditkartennummer</span></span>
- <span data-ttu-id="888cb-1437">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="888cb-1437">kreditkarten-nummer</span></span>
- <span data-ttu-id="888cb-1438">carta di credito</span><span class="sxs-lookup"><span data-stu-id="888cb-1438">carta di credito</span></span>
- <span data-ttu-id="888cb-1439">carta credito</span><span class="sxs-lookup"><span data-stu-id="888cb-1439">carta credito</span></span>
- <span data-ttu-id="888cb-1440">carta</span><span class="sxs-lookup"><span data-stu-id="888cb-1440">carta</span></span>
- <span data-ttu-id="888cb-1441">n carta</span><span class="sxs-lookup"><span data-stu-id="888cb-1441">n carta</span></span>
- <span data-ttu-id="888cb-1442">führerschein-nr.</span><span class="sxs-lookup"><span data-stu-id="888cb-1442">nr.</span></span> <span data-ttu-id="888cb-1443">carta</span><span class="sxs-lookup"><span data-stu-id="888cb-1443">carta</span></span>
- <span data-ttu-id="888cb-1444">nr carta</span><span class="sxs-lookup"><span data-stu-id="888cb-1444">nr carta</span></span>
- <span data-ttu-id="888cb-1445">numero carta</span><span class="sxs-lookup"><span data-stu-id="888cb-1445">numero carta</span></span>
- <span data-ttu-id="888cb-1446">numero della carta</span><span class="sxs-lookup"><span data-stu-id="888cb-1446">numero della carta</span></span>
- <span data-ttu-id="888cb-1447">numero di carta</span><span class="sxs-lookup"><span data-stu-id="888cb-1447">numero di carta</span></span>
- <span data-ttu-id="888cb-1448">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="888cb-1448">tarjeta credito</span></span>
- <span data-ttu-id="888cb-1449">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="888cb-1449">tarjeta de credito</span></span>
- <span data-ttu-id="888cb-1450">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="888cb-1450">tarjeta crédito</span></span>
- <span data-ttu-id="888cb-1451">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="888cb-1451">tarjeta de crédito</span></span>
- <span data-ttu-id="888cb-1452">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="888cb-1452">tarjeta de atm</span></span>
- <span data-ttu-id="888cb-1453">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="888cb-1453">tarjeta atm</span></span>
- <span data-ttu-id="888cb-1454">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="888cb-1454">tarjeta debito</span></span>
- <span data-ttu-id="888cb-1455">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="888cb-1455">tarjeta de debito</span></span>
- <span data-ttu-id="888cb-1456">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="888cb-1456">tarjeta débito</span></span>
- <span data-ttu-id="888cb-1457">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="888cb-1457">tarjeta de débito</span></span>
- <span data-ttu-id="888cb-1458">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="888cb-1458">nº de tarjeta</span></span>
- <span data-ttu-id="888cb-1459">不。</span><span class="sxs-lookup"><span data-stu-id="888cb-1459">no.</span></span> <span data-ttu-id="888cb-1460">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="888cb-1460">de tarjeta</span></span>
- <span data-ttu-id="888cb-1461">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="888cb-1461">no de tarjeta</span></span>
- <span data-ttu-id="888cb-1462">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="888cb-1462">numero de tarjeta</span></span>
- <span data-ttu-id="888cb-1463">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="888cb-1463">número de tarjeta</span></span>
- <span data-ttu-id="888cb-1464">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="888cb-1464">tarjeta no</span></span>
- <span data-ttu-id="888cb-1465">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="888cb-1465">tarjetahabiente</span></span>
- <span data-ttu-id="888cb-1466">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="888cb-1466">cartão de crédito</span></span>
- <span data-ttu-id="888cb-1467">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="888cb-1467">cartão de credito</span></span>
- <span data-ttu-id="888cb-1468">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="888cb-1468">cartao de crédito</span></span>
- <span data-ttu-id="888cb-1469">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="888cb-1469">cartao de credito</span></span>
- <span data-ttu-id="888cb-1470">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="888cb-1470">cartão de débito</span></span>
- <span data-ttu-id="888cb-1471">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="888cb-1471">cartao de débito</span></span>
- <span data-ttu-id="888cb-1472">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="888cb-1472">cartão de debito</span></span>
- <span data-ttu-id="888cb-1473">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="888cb-1473">cartao de debito</span></span>
- <span data-ttu-id="888cb-1474">débito automático</span><span class="sxs-lookup"><span data-stu-id="888cb-1474">débito automático</span></span>
- <span data-ttu-id="888cb-1475">debito automatico</span><span class="sxs-lookup"><span data-stu-id="888cb-1475">debito automatico</span></span>
- <span data-ttu-id="888cb-1476">número do cartão</span><span class="sxs-lookup"><span data-stu-id="888cb-1476">número do cartão</span></span>
- <span data-ttu-id="888cb-1477">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="888cb-1477">numero do cartão</span></span> 
- <span data-ttu-id="888cb-1478">número do cartao</span><span class="sxs-lookup"><span data-stu-id="888cb-1478">número do cartao</span></span>
- <span data-ttu-id="888cb-1479">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="888cb-1479">numero do cartao</span></span>
- <span data-ttu-id="888cb-1480">número de cartão</span><span class="sxs-lookup"><span data-stu-id="888cb-1480">número de cartão</span></span>
- <span data-ttu-id="888cb-1481">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="888cb-1481">numero de cartão</span></span>
- <span data-ttu-id="888cb-1482">número de cartao</span><span class="sxs-lookup"><span data-stu-id="888cb-1482">número de cartao</span></span>
- <span data-ttu-id="888cb-1483">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="888cb-1483">numero de cartao</span></span>
- <span data-ttu-id="888cb-1484">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="888cb-1484">nº do cartão</span></span>
- <span data-ttu-id="888cb-1485">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="888cb-1485">nº do cartao</span></span>
- <span data-ttu-id="888cb-1486">n º。</span><span class="sxs-lookup"><span data-stu-id="888cb-1486">nº.</span></span> <span data-ttu-id="888cb-1487">do cartão</span><span class="sxs-lookup"><span data-stu-id="888cb-1487">do cartão</span></span>
- <span data-ttu-id="888cb-1488">no do cartão</span><span class="sxs-lookup"><span data-stu-id="888cb-1488">no do cartão</span></span>
- <span data-ttu-id="888cb-1489">no do cartao</span><span class="sxs-lookup"><span data-stu-id="888cb-1489">no do cartao</span></span>
- <span data-ttu-id="888cb-1490">不。</span><span class="sxs-lookup"><span data-stu-id="888cb-1490">no.</span></span> <span data-ttu-id="888cb-1491">do cartão</span><span class="sxs-lookup"><span data-stu-id="888cb-1491">do cartão</span></span>
- <span data-ttu-id="888cb-1492">不。</span><span class="sxs-lookup"><span data-stu-id="888cb-1492">no.</span></span> <span data-ttu-id="888cb-1493">do cartao</span><span class="sxs-lookup"><span data-stu-id="888cb-1493">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="888cb-1494">	克罗地亚身份证号</span><span class="sxs-lookup"><span data-stu-id="888cb-1494">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-1495">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-1495">Format</span></span>

<span data-ttu-id="888cb-1496">九个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-1496">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-1497">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-1497">Pattern</span></span>

<span data-ttu-id="888cb-1498">九个连续的数字</span><span class="sxs-lookup"><span data-stu-id="888cb-1498">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-1499">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-1499">Checksum</span></span>

<span data-ttu-id="888cb-1500">否</span><span class="sxs-lookup"><span data-stu-id="888cb-1500">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-1501">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-1501">Definition</span></span>

<span data-ttu-id="888cb-1502">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-1502">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-1503">函数 Func_croatia_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-1503">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-1504">找到 Keyword_croatia_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-1504">A keyword from Keyword_croatia_id_card is found.</span></span>

```
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-1505">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-1505">Keywords</span></span>

#### <a name="keywordcroatiaidcard"></a><span data-ttu-id="888cb-1506">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="888cb-1506">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="888cb-1507">Croatian identity card</span><span class="sxs-lookup"><span data-stu-id="888cb-1507">Croatian identity card</span></span>
- <span data-ttu-id="888cb-1508">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="888cb-1508">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="888cb-1509">	Croatia Personal Identification (OIB) Number</span><span class="sxs-lookup"><span data-stu-id="888cb-1509">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-1510">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-1510">Format</span></span>

<span data-ttu-id="888cb-1511">11 个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-1511">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-1512">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-1512">Pattern</span></span>

<span data-ttu-id="888cb-1513">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="888cb-1513">11 digits:</span></span>
- <span data-ttu-id="888cb-1514">10 个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-1514">10 digits</span></span> 
- <span data-ttu-id="888cb-1515">最后一个数字是用于国际数据交换目的的校验位, 字母 HR 将加上11位数字。</span><span class="sxs-lookup"><span data-stu-id="888cb-1515">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-1516">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-1516">Checksum</span></span>

<span data-ttu-id="888cb-1517">是</span><span class="sxs-lookup"><span data-stu-id="888cb-1517">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-1518">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-1518">Definition</span></span>

<span data-ttu-id="888cb-1519">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-1519">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-1520">函数 Func_croatia_oib_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-1520">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-1521">找到 Keyword_croatia_oib_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-1521">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="888cb-1522">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-1522">The checksum passes.</span></span>

<span data-ttu-id="888cb-1523">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-1523">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-1524">函数 Func_croatia_oib_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-1524">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-1525">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-1525">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-1526">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-1526">Keywords</span></span>

#### <a name="keywordcroatiaoibnumber"></a><span data-ttu-id="888cb-1527">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="888cb-1527">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="888cb-1528">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="888cb-1528">Personal Identification Number</span></span>
- <span data-ttu-id="888cb-1529">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="888cb-1529">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="888cb-1530">OIB</span><span class="sxs-lookup"><span data-stu-id="888cb-1530">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="888cb-1531">捷克个人识别码</span><span class="sxs-lookup"><span data-stu-id="888cb-1531">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-1532">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-1532">Format</span></span>

<span data-ttu-id="888cb-1533">9个带可选正斜杠 (旧格式) 的数字, 带可选正斜杠的10个数字 (新的格式)</span><span class="sxs-lookup"><span data-stu-id="888cb-1533">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-1534">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-1534">Pattern</span></span>

<span data-ttu-id="888cb-1535">9个数字 (旧格式):</span><span class="sxs-lookup"><span data-stu-id="888cb-1535">Nine digits (old format):</span></span>
- <span data-ttu-id="888cb-1536">九个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-1536">Nine digits</span></span>

<span data-ttu-id="888cb-1537">OR</span><span class="sxs-lookup"><span data-stu-id="888cb-1537">OR</span></span>

- <span data-ttu-id="888cb-1538">代表出生日期的六个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-1538">Six digits that represent date of birth</span></span>
- <span data-ttu-id="888cb-1539">一个正斜杠 </span><span class="sxs-lookup"><span data-stu-id="888cb-1539">A forward slash</span></span>
- <span data-ttu-id="888cb-1540">三位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-1540">Three digits</span></span>

<span data-ttu-id="888cb-1541">10个数字 (新格式):</span><span class="sxs-lookup"><span data-stu-id="888cb-1541">10 digits (new format):</span></span>
- <span data-ttu-id="888cb-1542">10 个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-1542">10 digits</span></span>

<span data-ttu-id="888cb-1543">OR</span><span class="sxs-lookup"><span data-stu-id="888cb-1543">OR</span></span>

- <span data-ttu-id="888cb-1544">代表出生日期的六个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-1544">Six digits that represent date of birth</span></span>
- <span data-ttu-id="888cb-1545">一个正斜杠 </span><span class="sxs-lookup"><span data-stu-id="888cb-1545">A forward slash</span></span> 
- <span data-ttu-id="888cb-1546">四个数字, 其中最后一个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="888cb-1546">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-1547">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-1547">Checksum</span></span>

<span data-ttu-id="888cb-1548">是</span><span class="sxs-lookup"><span data-stu-id="888cb-1548">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-1549">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-1549">Definition</span></span>

<span data-ttu-id="888cb-1550">DLP 策略 85% 确信在300个字符的邻近度内检测到此类型的敏感信息: 函数 Func_czech_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-1550">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="888cb-1551">找到 Keyword_czech_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-1551">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="888cb-1552">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-1552">The checksum passes.</span></span>

```
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="888cb-1553">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-1553">Keywords</span></span>

- <span data-ttu-id="888cb-1554">捷克个人识别码</span><span class="sxs-lookup"><span data-stu-id="888cb-1554">czech personal identity number</span></span>
- <span data-ttu-id="888cb-1555">Rodnéčíslo</span><span class="sxs-lookup"><span data-stu-id="888cb-1555">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="888cb-1556">	丹麦个人身份号码</span><span class="sxs-lookup"><span data-stu-id="888cb-1556">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-1557">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-1557">Format</span></span>

<span data-ttu-id="888cb-1558">10 个数字，包含连字符</span><span class="sxs-lookup"><span data-stu-id="888cb-1558">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-1559">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-1559">Pattern</span></span>

<span data-ttu-id="888cb-1560">10 个数字：</span><span class="sxs-lookup"><span data-stu-id="888cb-1560">10 digits:</span></span>
- <span data-ttu-id="888cb-1561">六个数字，采用  DDMMYY 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="888cb-1561">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="888cb-1562">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="888cb-1562">A hyphen</span></span> 
- <span data-ttu-id="888cb-1563">四个数字，最后一位数字是校验位</span><span class="sxs-lookup"><span data-stu-id="888cb-1563">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-1564">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-1564">Checksum</span></span>

<span data-ttu-id="888cb-1565">是</span><span class="sxs-lookup"><span data-stu-id="888cb-1565">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-1566">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-1566">Definition</span></span>

<span data-ttu-id="888cb-1567">DLP 策略 75% 确信在300个字符的邻近度内检测到此类型的敏感信息: 正则表达式 Regex_denmark_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-1567">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="888cb-1568">找到 Keyword_denmark_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-1568">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="888cb-1569">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-1569">The checksum passes.</span></span>

```
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-1570">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-1570">Keywords</span></span>

#### <a name="keyworddenmarkid"></a><span data-ttu-id="888cb-1571">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="888cb-1571">Keyword_denmark_id</span></span>

- <span data-ttu-id="888cb-1572">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="888cb-1572">Personal Identification Number</span></span>
- <span data-ttu-id="888cb-1573">CPR</span><span class="sxs-lookup"><span data-stu-id="888cb-1573">CPR</span></span>
- <span data-ttu-id="888cb-1574">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="888cb-1574">Det Centrale Personregister</span></span>
- <span data-ttu-id="888cb-1575">Personnummer</span><span class="sxs-lookup"><span data-stu-id="888cb-1575">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="888cb-1576">药品管制局 (DEA) 号码</span><span class="sxs-lookup"><span data-stu-id="888cb-1576">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-1577">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-1577">Format</span></span>

<span data-ttu-id="888cb-1578">两个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-1578">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-1579">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-1579">Pattern</span></span>

<span data-ttu-id="888cb-1580">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="888cb-1580">Pattern must include all of the following:</span></span>
- <span data-ttu-id="888cb-1581">这一组可能的字母（不区分大小写）中的一个字母：abcdefghjklmnprstux，这是注册人代码</span><span class="sxs-lookup"><span data-stu-id="888cb-1581">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="888cb-1582">一个字母（不区分大小写），这是注册人姓氏的第一个字母</span><span class="sxs-lookup"><span data-stu-id="888cb-1582">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="888cb-1583">七位数字，最后一个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="888cb-1583">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-1584">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-1584">Checksum</span></span>

<span data-ttu-id="888cb-1585">是</span><span class="sxs-lookup"><span data-stu-id="888cb-1585">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-1586">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-1586">Definition</span></span>

<span data-ttu-id="888cb-1587">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-1587">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-1588">函数 Func_dea_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-1588">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-1589">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-1589">The checksum passes.</span></span>

```
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-1590">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-1590">Keywords</span></span>

<span data-ttu-id="888cb-1591">None</span><span class="sxs-lookup"><span data-stu-id="888cb-1591">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="888cb-1592">欧盟借记卡号</span><span class="sxs-lookup"><span data-stu-id="888cb-1592">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-1593">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-1593">Format</span></span>

<span data-ttu-id="888cb-1594">16 个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-1594">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-1595">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-1595">Pattern</span></span>

<span data-ttu-id="888cb-1596">非常复杂且强大的模式</span><span class="sxs-lookup"><span data-stu-id="888cb-1596">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-1597">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-1597">Checksum</span></span>

<span data-ttu-id="888cb-1598">是</span><span class="sxs-lookup"><span data-stu-id="888cb-1598">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-1599">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-1599">Definition</span></span>

<span data-ttu-id="888cb-1600">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-1600">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-1601">函数 Func_eu_debit_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-1601">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-1602">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="888cb-1602">At least one of the following is true:</span></span>
    - <span data-ttu-id="888cb-1603">找到 Keyword_eu_debit_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-1603">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="888cb-1604">找到 Keyword_card_terms_dict 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-1604">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="888cb-1605">找到 Keyword_card_security_terms_dict 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-1605">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="888cb-1606">找到 Keyword_card_expiration_terms_dict 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-1606">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="888cb-1607">函数 Func_expiration_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="888cb-1607">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="888cb-1608">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-1608">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-1609">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-1609">Keywords</span></span>

#### <a name="keywordeudebitcard"></a><span data-ttu-id="888cb-1610">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="888cb-1610">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="888cb-1611">account number</span><span class="sxs-lookup"><span data-stu-id="888cb-1611">account number</span></span> 
- <span data-ttu-id="888cb-1612">card number</span><span class="sxs-lookup"><span data-stu-id="888cb-1612">card number</span></span> 
- <span data-ttu-id="888cb-1613">card no.</span><span class="sxs-lookup"><span data-stu-id="888cb-1613">card no.</span></span> 
- <span data-ttu-id="888cb-1614">security number</span><span class="sxs-lookup"><span data-stu-id="888cb-1614">security number</span></span> 
- <span data-ttu-id="888cb-1615">收件人</span><span class="sxs-lookup"><span data-stu-id="888cb-1615">cc#</span></span> 

#### <a name="keywordcardtermsdict"></a><span data-ttu-id="888cb-1616">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="888cb-1616">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="888cb-1617">acct nbr</span><span class="sxs-lookup"><span data-stu-id="888cb-1617">acct nbr</span></span> 
- <span data-ttu-id="888cb-1618">acct num</span><span class="sxs-lookup"><span data-stu-id="888cb-1618">acct num</span></span> 
- <span data-ttu-id="888cb-1619">acct no</span><span class="sxs-lookup"><span data-stu-id="888cb-1619">acct no</span></span> 
- <span data-ttu-id="888cb-1620">american express</span><span class="sxs-lookup"><span data-stu-id="888cb-1620">american express</span></span> 
- <span data-ttu-id="888cb-1621">americanexpress</span><span class="sxs-lookup"><span data-stu-id="888cb-1621">americanexpress</span></span> 
- <span data-ttu-id="888cb-1622">americano espresso</span><span class="sxs-lookup"><span data-stu-id="888cb-1622">americano espresso</span></span> 
- <span data-ttu-id="888cb-1623">amex</span><span class="sxs-lookup"><span data-stu-id="888cb-1623">amex</span></span> 
- <span data-ttu-id="888cb-1624">atm card</span><span class="sxs-lookup"><span data-stu-id="888cb-1624">atm card</span></span> 
- <span data-ttu-id="888cb-1625">atm cards</span><span class="sxs-lookup"><span data-stu-id="888cb-1625">atm cards</span></span> 
- <span data-ttu-id="888cb-1626">atm kaart</span><span class="sxs-lookup"><span data-stu-id="888cb-1626">atm kaart</span></span> 
- <span data-ttu-id="888cb-1627">atmcard</span><span class="sxs-lookup"><span data-stu-id="888cb-1627">atmcard</span></span> 
- <span data-ttu-id="888cb-1628">atmcards</span><span class="sxs-lookup"><span data-stu-id="888cb-1628">atmcards</span></span> 
- <span data-ttu-id="888cb-1629">atmkaart</span><span class="sxs-lookup"><span data-stu-id="888cb-1629">atmkaart</span></span> 
- <span data-ttu-id="888cb-1630">atmkaarten</span><span class="sxs-lookup"><span data-stu-id="888cb-1630">atmkaarten</span></span> 
- <span data-ttu-id="888cb-1631">bancontact</span><span class="sxs-lookup"><span data-stu-id="888cb-1631">bancontact</span></span> 
- <span data-ttu-id="888cb-1632">bank card</span><span class="sxs-lookup"><span data-stu-id="888cb-1632">bank card</span></span> 
- <span data-ttu-id="888cb-1633">bankkaart</span><span class="sxs-lookup"><span data-stu-id="888cb-1633">bankkaart</span></span> 
- <span data-ttu-id="888cb-1634">card holder</span><span class="sxs-lookup"><span data-stu-id="888cb-1634">card holder</span></span> 
- <span data-ttu-id="888cb-1635">card holders</span><span class="sxs-lookup"><span data-stu-id="888cb-1635">card holders</span></span> 
- <span data-ttu-id="888cb-1636">card num</span><span class="sxs-lookup"><span data-stu-id="888cb-1636">card num</span></span> 
- <span data-ttu-id="888cb-1637">card number</span><span class="sxs-lookup"><span data-stu-id="888cb-1637">card number</span></span> 
- <span data-ttu-id="888cb-1638">card numbers</span><span class="sxs-lookup"><span data-stu-id="888cb-1638">card numbers</span></span> 
- <span data-ttu-id="888cb-1639">card type</span><span class="sxs-lookup"><span data-stu-id="888cb-1639">card type</span></span> 
- <span data-ttu-id="888cb-1640">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="888cb-1640">cardano numerico</span></span> 
- <span data-ttu-id="888cb-1641">持卡人</span><span class="sxs-lookup"><span data-stu-id="888cb-1641">cardholder</span></span> 
- <span data-ttu-id="888cb-1642">cardholders</span><span class="sxs-lookup"><span data-stu-id="888cb-1642">cardholders</span></span> 
- <span data-ttu-id="888cb-1643">cardnumber</span><span class="sxs-lookup"><span data-stu-id="888cb-1643">cardnumber</span></span> 
- <span data-ttu-id="888cb-1644">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="888cb-1644">cardnumbers</span></span> 
- <span data-ttu-id="888cb-1645">carta bianca</span><span class="sxs-lookup"><span data-stu-id="888cb-1645">carta bianca</span></span> 
- <span data-ttu-id="888cb-1646">carta credito</span><span class="sxs-lookup"><span data-stu-id="888cb-1646">carta credito</span></span> 
- <span data-ttu-id="888cb-1647">carta di credito</span><span class="sxs-lookup"><span data-stu-id="888cb-1647">carta di credito</span></span> 
- <span data-ttu-id="888cb-1648">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="888cb-1648">cartao de credito</span></span> 
- <span data-ttu-id="888cb-1649">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="888cb-1649">cartao de crédito</span></span> 
- <span data-ttu-id="888cb-1650">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="888cb-1650">cartao de debito</span></span> 
- <span data-ttu-id="888cb-1651">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="888cb-1651">cartao de débito</span></span> 
- <span data-ttu-id="888cb-1652">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="888cb-1652">carte bancaire</span></span> 
- <span data-ttu-id="888cb-1653">carte blanche</span><span class="sxs-lookup"><span data-stu-id="888cb-1653">carte blanche</span></span> 
- <span data-ttu-id="888cb-1654">carte bleue</span><span class="sxs-lookup"><span data-stu-id="888cb-1654">carte bleue</span></span> 
- <span data-ttu-id="888cb-1655">carte de credit</span><span class="sxs-lookup"><span data-stu-id="888cb-1655">carte de credit</span></span> 
- <span data-ttu-id="888cb-1656">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="888cb-1656">carte de crédit</span></span> 
- <span data-ttu-id="888cb-1657">carte di credito</span><span class="sxs-lookup"><span data-stu-id="888cb-1657">carte di credito</span></span> 
- <span data-ttu-id="888cb-1658">carteblanche</span><span class="sxs-lookup"><span data-stu-id="888cb-1658">carteblanche</span></span> 
- <span data-ttu-id="888cb-1659">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="888cb-1659">cartão de credito</span></span> 
- <span data-ttu-id="888cb-1660">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="888cb-1660">cartão de crédito</span></span> 
- <span data-ttu-id="888cb-1661">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="888cb-1661">cartão de debito</span></span> 
- <span data-ttu-id="888cb-1662">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="888cb-1662">cartão de débito</span></span> 
- <span data-ttu-id="888cb-1663">cb</span><span class="sxs-lookup"><span data-stu-id="888cb-1663">cb</span></span> 
- <span data-ttu-id="888cb-1664">ccn</span><span class="sxs-lookup"><span data-stu-id="888cb-1664">ccn</span></span> 
- <span data-ttu-id="888cb-1665">check card</span><span class="sxs-lookup"><span data-stu-id="888cb-1665">check card</span></span> 
- <span data-ttu-id="888cb-1666">check cards</span><span class="sxs-lookup"><span data-stu-id="888cb-1666">check cards</span></span> 
- <span data-ttu-id="888cb-1667">checkcard</span><span class="sxs-lookup"><span data-stu-id="888cb-1667">checkcard</span></span>
- <span data-ttu-id="888cb-1668">checkcards</span><span class="sxs-lookup"><span data-stu-id="888cb-1668">checkcards</span></span> 
- <span data-ttu-id="888cb-1669">chequekaart</span><span class="sxs-lookup"><span data-stu-id="888cb-1669">chequekaart</span></span> 
- <span data-ttu-id="888cb-1670">cirrus</span><span class="sxs-lookup"><span data-stu-id="888cb-1670">cirrus</span></span> 
- <span data-ttu-id="888cb-1671">cirrus-edc-maestro</span><span class="sxs-lookup"><span data-stu-id="888cb-1671">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="888cb-1672">controlekaart</span><span class="sxs-lookup"><span data-stu-id="888cb-1672">controlekaart</span></span> 
- <span data-ttu-id="888cb-1673">controlekaarten</span><span class="sxs-lookup"><span data-stu-id="888cb-1673">controlekaarten</span></span> 
- <span data-ttu-id="888cb-1674">credit card</span><span class="sxs-lookup"><span data-stu-id="888cb-1674">credit card</span></span> 
- <span data-ttu-id="888cb-1675">credit cards</span><span class="sxs-lookup"><span data-stu-id="888cb-1675">credit cards</span></span> 
- <span data-ttu-id="888cb-1676">creditcard</span><span class="sxs-lookup"><span data-stu-id="888cb-1676">creditcard</span></span> 
- <span data-ttu-id="888cb-1677">creditcards</span><span class="sxs-lookup"><span data-stu-id="888cb-1677">creditcards</span></span> 
- <span data-ttu-id="888cb-1678">debetkaart</span><span class="sxs-lookup"><span data-stu-id="888cb-1678">debetkaart</span></span> 
- <span data-ttu-id="888cb-1679">debetkaarten</span><span class="sxs-lookup"><span data-stu-id="888cb-1679">debetkaarten</span></span> 
- <span data-ttu-id="888cb-1680">debit card</span><span class="sxs-lookup"><span data-stu-id="888cb-1680">debit card</span></span> 
- <span data-ttu-id="888cb-1681">debit cards</span><span class="sxs-lookup"><span data-stu-id="888cb-1681">debit cards</span></span> 
- <span data-ttu-id="888cb-1682">debitcard</span><span class="sxs-lookup"><span data-stu-id="888cb-1682">debitcard</span></span> 
- <span data-ttu-id="888cb-1683">debitcards</span><span class="sxs-lookup"><span data-stu-id="888cb-1683">debitcards</span></span> 
- <span data-ttu-id="888cb-1684">debito automatico</span><span class="sxs-lookup"><span data-stu-id="888cb-1684">debito automatico</span></span> 
- <span data-ttu-id="888cb-1685">diners club</span><span class="sxs-lookup"><span data-stu-id="888cb-1685">diners club</span></span> 
- <span data-ttu-id="888cb-1686">dinersclub</span><span class="sxs-lookup"><span data-stu-id="888cb-1686">dinersclub</span></span> 
- <span data-ttu-id="888cb-1687">确定</span><span class="sxs-lookup"><span data-stu-id="888cb-1687">discover</span></span> 
- <span data-ttu-id="888cb-1688">discover card</span><span class="sxs-lookup"><span data-stu-id="888cb-1688">discover card</span></span> 
- <span data-ttu-id="888cb-1689">discover cards</span><span class="sxs-lookup"><span data-stu-id="888cb-1689">discover cards</span></span> 
- <span data-ttu-id="888cb-1690">discovercard</span><span class="sxs-lookup"><span data-stu-id="888cb-1690">discovercard</span></span> 
- <span data-ttu-id="888cb-1691">discovercards</span><span class="sxs-lookup"><span data-stu-id="888cb-1691">discovercards</span></span> 
- <span data-ttu-id="888cb-1692">débito automático</span><span class="sxs-lookup"><span data-stu-id="888cb-1692">débito automático</span></span>
- <span data-ttu-id="888cb-1693">edc</span><span class="sxs-lookup"><span data-stu-id="888cb-1693">edc</span></span> 
- <span data-ttu-id="888cb-1694">eigentümername</span><span class="sxs-lookup"><span data-stu-id="888cb-1694">eigentümername</span></span> 
- <span data-ttu-id="888cb-1695">european debit card</span><span class="sxs-lookup"><span data-stu-id="888cb-1695">european debit card</span></span> 
- <span data-ttu-id="888cb-1696">hoofdkaart</span><span class="sxs-lookup"><span data-stu-id="888cb-1696">hoofdkaart</span></span> 
- <span data-ttu-id="888cb-1697">hoofdkaarten</span><span class="sxs-lookup"><span data-stu-id="888cb-1697">hoofdkaarten</span></span> 
- <span data-ttu-id="888cb-1698">in viaggio</span><span class="sxs-lookup"><span data-stu-id="888cb-1698">in viaggio</span></span> 
- <span data-ttu-id="888cb-1699">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="888cb-1699">japanese card bureau</span></span> 
- <span data-ttu-id="888cb-1700">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="888cb-1700">japanse kaartdienst</span></span> 
- <span data-ttu-id="888cb-1701">jcb</span><span class="sxs-lookup"><span data-stu-id="888cb-1701">jcb</span></span> 
- <span data-ttu-id="888cb-1702">kaart</span><span class="sxs-lookup"><span data-stu-id="888cb-1702">kaart</span></span> 
- <span data-ttu-id="888cb-1703">kaart num</span><span class="sxs-lookup"><span data-stu-id="888cb-1703">kaart num</span></span> 
- <span data-ttu-id="888cb-1704">kaartaantal</span><span class="sxs-lookup"><span data-stu-id="888cb-1704">kaartaantal</span></span> 
- <span data-ttu-id="888cb-1705">kaartaantallen</span><span class="sxs-lookup"><span data-stu-id="888cb-1705">kaartaantallen</span></span> 
- <span data-ttu-id="888cb-1706">kaarthouder</span><span class="sxs-lookup"><span data-stu-id="888cb-1706">kaarthouder</span></span> 
- <span data-ttu-id="888cb-1707">kaarthouders</span><span class="sxs-lookup"><span data-stu-id="888cb-1707">kaarthouders</span></span> 
- <span data-ttu-id="888cb-1708">karte</span><span class="sxs-lookup"><span data-stu-id="888cb-1708">karte</span></span>  
- <span data-ttu-id="888cb-1709">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="888cb-1709">karteninhaber</span></span> 
- <span data-ttu-id="888cb-1710">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="888cb-1710">karteninhabers</span></span>
- <span data-ttu-id="888cb-1711">kartennr</span><span class="sxs-lookup"><span data-stu-id="888cb-1711">kartennr</span></span> 
- <span data-ttu-id="888cb-1712">kartennummer</span><span class="sxs-lookup"><span data-stu-id="888cb-1712">kartennummer</span></span> 
- <span data-ttu-id="888cb-1713">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="888cb-1713">kreditkarte</span></span> 
- <span data-ttu-id="888cb-1714">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="888cb-1714">kreditkarten-nummer</span></span> 
- <span data-ttu-id="888cb-1715">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="888cb-1715">kreditkarteninhaber</span></span> 
- <span data-ttu-id="888cb-1716">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="888cb-1716">kreditkarteninstitut</span></span> 
- <span data-ttu-id="888cb-1717">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="888cb-1717">kreditkartennummer</span></span> 
- <span data-ttu-id="888cb-1718">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="888cb-1718">kreditkartentyp</span></span> 
- <span data-ttu-id="888cb-1719">maestro</span><span class="sxs-lookup"><span data-stu-id="888cb-1719">maestro</span></span> 
- <span data-ttu-id="888cb-1720">Master Card</span><span class="sxs-lookup"><span data-stu-id="888cb-1720">master card</span></span> 
- <span data-ttu-id="888cb-1721">master cards</span><span class="sxs-lookup"><span data-stu-id="888cb-1721">master cards</span></span> 
- <span data-ttu-id="888cb-1722">mastercard</span><span class="sxs-lookup"><span data-stu-id="888cb-1722">mastercard</span></span> 
- <span data-ttu-id="888cb-1723">mastercards</span><span class="sxs-lookup"><span data-stu-id="888cb-1723">mastercards</span></span> 
- <span data-ttu-id="888cb-1724">emc</span><span class="sxs-lookup"><span data-stu-id="888cb-1724">mc</span></span> 
- <span data-ttu-id="888cb-1725">mister cash</span><span class="sxs-lookup"><span data-stu-id="888cb-1725">mister cash</span></span> 
- <span data-ttu-id="888cb-1726">n carta</span><span class="sxs-lookup"><span data-stu-id="888cb-1726">n carta</span></span> 
- <span data-ttu-id="888cb-1727">carta</span><span class="sxs-lookup"><span data-stu-id="888cb-1727">carta</span></span> 
- <span data-ttu-id="888cb-1728">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="888cb-1728">no de tarjeta</span></span> 
- <span data-ttu-id="888cb-1729">no do cartao</span><span class="sxs-lookup"><span data-stu-id="888cb-1729">no do cartao</span></span> 
- <span data-ttu-id="888cb-1730">no do cartão</span><span class="sxs-lookup"><span data-stu-id="888cb-1730">no do cartão</span></span> 
- <span data-ttu-id="888cb-1731">不。</span><span class="sxs-lookup"><span data-stu-id="888cb-1731">no.</span></span> <span data-ttu-id="888cb-1732">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="888cb-1732">de tarjeta</span></span> 
- <span data-ttu-id="888cb-1733">不。</span><span class="sxs-lookup"><span data-stu-id="888cb-1733">no.</span></span> <span data-ttu-id="888cb-1734">do cartao</span><span class="sxs-lookup"><span data-stu-id="888cb-1734">do cartao</span></span> 
- <span data-ttu-id="888cb-1735">不。</span><span class="sxs-lookup"><span data-stu-id="888cb-1735">no.</span></span> <span data-ttu-id="888cb-1736">do cartão</span><span class="sxs-lookup"><span data-stu-id="888cb-1736">do cartão</span></span> 
- <span data-ttu-id="888cb-1737">nr carta</span><span class="sxs-lookup"><span data-stu-id="888cb-1737">nr carta</span></span> 
- <span data-ttu-id="888cb-1738">führerschein-nr.</span><span class="sxs-lookup"><span data-stu-id="888cb-1738">nr.</span></span> <span data-ttu-id="888cb-1739">carta</span><span class="sxs-lookup"><span data-stu-id="888cb-1739">carta</span></span> 
- <span data-ttu-id="888cb-1740">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="888cb-1740">numeri di scheda</span></span> 
- <span data-ttu-id="888cb-1741">numero carta</span><span class="sxs-lookup"><span data-stu-id="888cb-1741">numero carta</span></span> 
- <span data-ttu-id="888cb-1742">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="888cb-1742">numero de cartao</span></span> 
- <span data-ttu-id="888cb-1743">numero de carte</span><span class="sxs-lookup"><span data-stu-id="888cb-1743">numero de carte</span></span> 
- <span data-ttu-id="888cb-1744">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="888cb-1744">numero de cartão</span></span> 
- <span data-ttu-id="888cb-1745">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="888cb-1745">numero de tarjeta</span></span>
- <span data-ttu-id="888cb-1746">numero della carta</span><span class="sxs-lookup"><span data-stu-id="888cb-1746">numero della carta</span></span> 
- <span data-ttu-id="888cb-1747">numero di carta</span><span class="sxs-lookup"><span data-stu-id="888cb-1747">numero di carta</span></span> 
- <span data-ttu-id="888cb-1748">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="888cb-1748">numero di scheda</span></span> 
- <span data-ttu-id="888cb-1749">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="888cb-1749">numero do cartao</span></span> 
- <span data-ttu-id="888cb-1750">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="888cb-1750">numero do cartão</span></span> 
- <span data-ttu-id="888cb-1751">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="888cb-1751">numéro de carte</span></span> 
- <span data-ttu-id="888cb-1752">nº carta</span><span class="sxs-lookup"><span data-stu-id="888cb-1752">nº carta</span></span> 
- <span data-ttu-id="888cb-1753">nº de carte</span><span class="sxs-lookup"><span data-stu-id="888cb-1753">nº de carte</span></span> 
- <span data-ttu-id="888cb-1754">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="888cb-1754">nº de la carte</span></span> 
- <span data-ttu-id="888cb-1755">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="888cb-1755">nº de tarjeta</span></span> 
- <span data-ttu-id="888cb-1756">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="888cb-1756">nº do cartao</span></span> 
- <span data-ttu-id="888cb-1757">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="888cb-1757">nº do cartão</span></span> 
- <span data-ttu-id="888cb-1758">n º。</span><span class="sxs-lookup"><span data-stu-id="888cb-1758">nº.</span></span> <span data-ttu-id="888cb-1759">do cartão</span><span class="sxs-lookup"><span data-stu-id="888cb-1759">do cartão</span></span> 
- <span data-ttu-id="888cb-1760">número de cartao</span><span class="sxs-lookup"><span data-stu-id="888cb-1760">número de cartao</span></span> 
- <span data-ttu-id="888cb-1761">número de cartão</span><span class="sxs-lookup"><span data-stu-id="888cb-1761">número de cartão</span></span> 
- <span data-ttu-id="888cb-1762">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="888cb-1762">número de tarjeta</span></span> 
- <span data-ttu-id="888cb-1763">número do cartao</span><span class="sxs-lookup"><span data-stu-id="888cb-1763">número do cartao</span></span> 
- <span data-ttu-id="888cb-1764">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="888cb-1764">scheda dell'assegno</span></span> 
- <span data-ttu-id="888cb-1765">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="888cb-1765">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="888cb-1766">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="888cb-1766">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="888cb-1767">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="888cb-1767">scheda della banca</span></span> 
- <span data-ttu-id="888cb-1768">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="888cb-1768">scheda di controllo</span></span> 
- <span data-ttu-id="888cb-1769">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="888cb-1769">scheda di debito</span></span> 
- <span data-ttu-id="888cb-1770">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="888cb-1770">scheda matrice</span></span> 
- <span data-ttu-id="888cb-1771">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="888cb-1771">schede dell'atmosfera</span></span> 
- <span data-ttu-id="888cb-1772">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="888cb-1772">schede di controllo</span></span> 
- <span data-ttu-id="888cb-1773">schede di debito</span><span class="sxs-lookup"><span data-stu-id="888cb-1773">schede di debito</span></span> 
- <span data-ttu-id="888cb-1774">schede matrici</span><span class="sxs-lookup"><span data-stu-id="888cb-1774">schede matrici</span></span> 
- <span data-ttu-id="888cb-1775">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="888cb-1775">scoprono la scheda</span></span> 
- <span data-ttu-id="888cb-1776">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="888cb-1776">scoprono le schede</span></span> 
- <span data-ttu-id="888cb-1777">solo</span><span class="sxs-lookup"><span data-stu-id="888cb-1777">solo</span></span> 
- <span data-ttu-id="888cb-1778">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="888cb-1778">supporti di scheda</span></span> 
- <span data-ttu-id="888cb-1779">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="888cb-1779">supporto di scheda</span></span> 
- <span data-ttu-id="888cb-1780">器</span><span class="sxs-lookup"><span data-stu-id="888cb-1780">switch</span></span> 
- <span data-ttu-id="888cb-1781">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="888cb-1781">tarjeta atm</span></span> 
- <span data-ttu-id="888cb-1782">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="888cb-1782">tarjeta credito</span></span> 
- <span data-ttu-id="888cb-1783">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="888cb-1783">tarjeta de atm</span></span> 
- <span data-ttu-id="888cb-1784">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="888cb-1784">tarjeta de credito</span></span> 
- <span data-ttu-id="888cb-1785">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="888cb-1785">tarjeta de debito</span></span> 
- <span data-ttu-id="888cb-1786">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="888cb-1786">tarjeta debito</span></span> 
- <span data-ttu-id="888cb-1787">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="888cb-1787">tarjeta no</span></span>
- <span data-ttu-id="888cb-1788">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="888cb-1788">tarjetahabiente</span></span> 
- <span data-ttu-id="888cb-1789">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="888cb-1789">tipo della scheda</span></span> 
- <span data-ttu-id="888cb-1790">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="888cb-1790">ufficio giapponese della</span></span> 
- <span data-ttu-id="888cb-1791">scheda</span><span class="sxs-lookup"><span data-stu-id="888cb-1791">scheda</span></span> 
- <span data-ttu-id="888cb-1792">v pay</span><span class="sxs-lookup"><span data-stu-id="888cb-1792">v pay</span></span> 
- <span data-ttu-id="888cb-1793">v-支付</span><span class="sxs-lookup"><span data-stu-id="888cb-1793">v-pay</span></span> 
- <span data-ttu-id="888cb-1794">反之</span><span class="sxs-lookup"><span data-stu-id="888cb-1794">visa</span></span> 
- <span data-ttu-id="888cb-1795">visa plus</span><span class="sxs-lookup"><span data-stu-id="888cb-1795">visa plus</span></span> 
- <span data-ttu-id="888cb-1796">visa electron</span><span class="sxs-lookup"><span data-stu-id="888cb-1796">visa electron</span></span> 
- <span data-ttu-id="888cb-1797">visto</span><span class="sxs-lookup"><span data-stu-id="888cb-1797">visto</span></span> 
- <span data-ttu-id="888cb-1798">visum</span><span class="sxs-lookup"><span data-stu-id="888cb-1798">visum</span></span> 
- <span data-ttu-id="888cb-1799">vpay</span><span class="sxs-lookup"><span data-stu-id="888cb-1799">vpay</span></span>   

#### <a name="keywordcardsecuritytermsdict"></a><span data-ttu-id="888cb-1800">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="888cb-1800">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="888cb-1801">card identification number</span><span class="sxs-lookup"><span data-stu-id="888cb-1801">card identification number</span></span>
- <span data-ttu-id="888cb-1802">card verification</span><span class="sxs-lookup"><span data-stu-id="888cb-1802">card verification</span></span> 
- <span data-ttu-id="888cb-1803">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="888cb-1803">cardi la verifica</span></span> 
- <span data-ttu-id="888cb-1804">cid</span><span class="sxs-lookup"><span data-stu-id="888cb-1804">cid</span></span> 
- <span data-ttu-id="888cb-1805">cod seg</span><span class="sxs-lookup"><span data-stu-id="888cb-1805">cod seg</span></span> 
- <span data-ttu-id="888cb-1806">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="888cb-1806">cod seguranca</span></span> 
- <span data-ttu-id="888cb-1807">cod segurança</span><span class="sxs-lookup"><span data-stu-id="888cb-1807">cod segurança</span></span> 
- <span data-ttu-id="888cb-1808">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="888cb-1808">cod sicurezza</span></span> 
- <span data-ttu-id="888cb-1809">货.</span><span class="sxs-lookup"><span data-stu-id="888cb-1809">cod.</span></span> <span data-ttu-id="888cb-1810">seg</span><span class="sxs-lookup"><span data-stu-id="888cb-1810">seg</span></span> 
- <span data-ttu-id="888cb-1811">货.</span><span class="sxs-lookup"><span data-stu-id="888cb-1811">cod.</span></span> <span data-ttu-id="888cb-1812">seguranca</span><span class="sxs-lookup"><span data-stu-id="888cb-1812">seguranca</span></span> 
- <span data-ttu-id="888cb-1813">货.</span><span class="sxs-lookup"><span data-stu-id="888cb-1813">cod.</span></span> <span data-ttu-id="888cb-1814">segurança</span><span class="sxs-lookup"><span data-stu-id="888cb-1814">segurança</span></span> 
- <span data-ttu-id="888cb-1815">货.</span><span class="sxs-lookup"><span data-stu-id="888cb-1815">cod.</span></span> <span data-ttu-id="888cb-1816">sicurezza</span><span class="sxs-lookup"><span data-stu-id="888cb-1816">sicurezza</span></span> 
- <span data-ttu-id="888cb-1817">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="888cb-1817">codice di sicurezza</span></span> 
- <span data-ttu-id="888cb-1818">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="888cb-1818">codice di verifica</span></span> 
- <span data-ttu-id="888cb-1819">codigo</span><span class="sxs-lookup"><span data-stu-id="888cb-1819">codigo</span></span> 
- <span data-ttu-id="888cb-1820">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="888cb-1820">codigo de seguranca</span></span> 
- <span data-ttu-id="888cb-1821">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="888cb-1821">codigo de segurança</span></span> 
- <span data-ttu-id="888cb-1822">crittogramma</span><span class="sxs-lookup"><span data-stu-id="888cb-1822">crittogramma</span></span> 
- <span data-ttu-id="888cb-1823">cryptogram</span><span class="sxs-lookup"><span data-stu-id="888cb-1823">cryptogram</span></span> 
- <span data-ttu-id="888cb-1824">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="888cb-1824">cryptogramme</span></span> 
- <span data-ttu-id="888cb-1825">cv2</span><span class="sxs-lookup"><span data-stu-id="888cb-1825">cv2</span></span> 
- <span data-ttu-id="888cb-1826">cvc</span><span class="sxs-lookup"><span data-stu-id="888cb-1826">cvc</span></span> 
- <span data-ttu-id="888cb-1827">cvc2</span><span class="sxs-lookup"><span data-stu-id="888cb-1827">cvc2</span></span> 
- <span data-ttu-id="888cb-1828">cvn</span><span class="sxs-lookup"><span data-stu-id="888cb-1828">cvn</span></span> 
- <span data-ttu-id="888cb-1829">cvv</span><span class="sxs-lookup"><span data-stu-id="888cb-1829">cvv</span></span> 
- <span data-ttu-id="888cb-1830">cvv2</span><span class="sxs-lookup"><span data-stu-id="888cb-1830">cvv2</span></span> 
- <span data-ttu-id="888cb-1831">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="888cb-1831">cód seguranca</span></span> 
- <span data-ttu-id="888cb-1832">cód segurança</span><span class="sxs-lookup"><span data-stu-id="888cb-1832">cód segurança</span></span> 
- <span data-ttu-id="888cb-1833">cód。</span><span class="sxs-lookup"><span data-stu-id="888cb-1833">cód.</span></span> <span data-ttu-id="888cb-1834">seguranca</span><span class="sxs-lookup"><span data-stu-id="888cb-1834">seguranca</span></span> 
- <span data-ttu-id="888cb-1835">cód。</span><span class="sxs-lookup"><span data-stu-id="888cb-1835">cód.</span></span> <span data-ttu-id="888cb-1836">segurança</span><span class="sxs-lookup"><span data-stu-id="888cb-1836">segurança</span></span> 
- <span data-ttu-id="888cb-1837">código</span><span class="sxs-lookup"><span data-stu-id="888cb-1837">código</span></span> 
- <span data-ttu-id="888cb-1838">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="888cb-1838">código de seguranca</span></span> 
- <span data-ttu-id="888cb-1839">código de segurança</span><span class="sxs-lookup"><span data-stu-id="888cb-1839">código de segurança</span></span> 
- <span data-ttu-id="888cb-1840">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="888cb-1840">de kaart controle</span></span> 
- <span data-ttu-id="888cb-1841">geeft nr uit</span><span class="sxs-lookup"><span data-stu-id="888cb-1841">geeft nr uit</span></span> 
- <span data-ttu-id="888cb-1842">issue no</span><span class="sxs-lookup"><span data-stu-id="888cb-1842">issue no</span></span> 
- <span data-ttu-id="888cb-1843">issue number</span><span class="sxs-lookup"><span data-stu-id="888cb-1843">issue number</span></span> 
- <span data-ttu-id="888cb-1844">kaartidentificatienummer</span><span class="sxs-lookup"><span data-stu-id="888cb-1844">kaartidentificatienummer</span></span> 
- <span data-ttu-id="888cb-1845">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="888cb-1845">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="888cb-1846">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="888cb-1846">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="888cb-1847">kwestieaantal</span><span class="sxs-lookup"><span data-stu-id="888cb-1847">kwestieaantal</span></span> 
- <span data-ttu-id="888cb-1848">不。</span><span class="sxs-lookup"><span data-stu-id="888cb-1848">no.</span></span> <span data-ttu-id="888cb-1849">dell'edizione</span><span class="sxs-lookup"><span data-stu-id="888cb-1849">dell'edizione</span></span> 
- <span data-ttu-id="888cb-1850">不。</span><span class="sxs-lookup"><span data-stu-id="888cb-1850">no.</span></span> <span data-ttu-id="888cb-1851">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="888cb-1851">di sicurezza</span></span> 
- <span data-ttu-id="888cb-1852">numero de securite</span><span class="sxs-lookup"><span data-stu-id="888cb-1852">numero de securite</span></span> 
- <span data-ttu-id="888cb-1853">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="888cb-1853">numero de verificacao</span></span> 
- <span data-ttu-id="888cb-1854">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="888cb-1854">numero dell'edizione</span></span> 
- <span data-ttu-id="888cb-1855">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="888cb-1855">numero di identificazione della</span></span> 
- <span data-ttu-id="888cb-1856">scheda</span><span class="sxs-lookup"><span data-stu-id="888cb-1856">scheda</span></span> 
- <span data-ttu-id="888cb-1857">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="888cb-1857">numero di sicurezza</span></span> 
- <span data-ttu-id="888cb-1858">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="888cb-1858">numero van veiligheid</span></span> 
- <span data-ttu-id="888cb-1859">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="888cb-1859">numéro de sécurité</span></span> 
- <span data-ttu-id="888cb-1860">nº autorizzazione</span><span class="sxs-lookup"><span data-stu-id="888cb-1860">nº autorizzazione</span></span> 
- <span data-ttu-id="888cb-1861">número de verificação</span><span class="sxs-lookup"><span data-stu-id="888cb-1861">número de verificação</span></span> 
- <span data-ttu-id="888cb-1862">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="888cb-1862">perno il blocco</span></span> 
- <span data-ttu-id="888cb-1863">pin block</span><span class="sxs-lookup"><span data-stu-id="888cb-1863">pin block</span></span> 
- <span data-ttu-id="888cb-1864">prufziffer</span><span class="sxs-lookup"><span data-stu-id="888cb-1864">prufziffer</span></span> 
- <span data-ttu-id="888cb-1865">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="888cb-1865">prüfziffer</span></span> 
- <span data-ttu-id="888cb-1866">security code</span><span class="sxs-lookup"><span data-stu-id="888cb-1866">security code</span></span> 
- <span data-ttu-id="888cb-1867">security no</span><span class="sxs-lookup"><span data-stu-id="888cb-1867">security no</span></span> 
- <span data-ttu-id="888cb-1868">security number</span><span class="sxs-lookup"><span data-stu-id="888cb-1868">security number</span></span> 
- <span data-ttu-id="888cb-1869">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="888cb-1869">sicherheits kode</span></span> 
- <span data-ttu-id="888cb-1870">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="888cb-1870">sicherheitscode</span></span> 
- <span data-ttu-id="888cb-1871">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="888cb-1871">sicherheitsnummer</span></span> 
- <span data-ttu-id="888cb-1872">speldblok</span><span class="sxs-lookup"><span data-stu-id="888cb-1872">speldblok</span></span> 
- <span data-ttu-id="888cb-1873">veiligheid nr</span><span class="sxs-lookup"><span data-stu-id="888cb-1873">veiligheid nr</span></span> 
- <span data-ttu-id="888cb-1874">veiligheidsaantal</span><span class="sxs-lookup"><span data-stu-id="888cb-1874">veiligheidsaantal</span></span> 
- <span data-ttu-id="888cb-1875">veiligheidscode</span><span class="sxs-lookup"><span data-stu-id="888cb-1875">veiligheidscode</span></span> 
- <span data-ttu-id="888cb-1876">veiligheidsnummer</span><span class="sxs-lookup"><span data-stu-id="888cb-1876">veiligheidsnummer</span></span> 
- <span data-ttu-id="888cb-1877">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="888cb-1877">verfalldatum</span></span> 

#### <a name="keywordcardexpirationtermsdict"></a><span data-ttu-id="888cb-1878">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="888cb-1878">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="888cb-1879">ablauf</span><span class="sxs-lookup"><span data-stu-id="888cb-1879">ablauf</span></span> 
- <span data-ttu-id="888cb-1880">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="888cb-1880">data de expiracao</span></span> 
- <span data-ttu-id="888cb-1881">data de expiração</span><span class="sxs-lookup"><span data-stu-id="888cb-1881">data de expiração</span></span> 
- <span data-ttu-id="888cb-1882">data del exp</span><span class="sxs-lookup"><span data-stu-id="888cb-1882">data del exp</span></span> 
- <span data-ttu-id="888cb-1883">data di exp</span><span class="sxs-lookup"><span data-stu-id="888cb-1883">data di exp</span></span> 
- <span data-ttu-id="888cb-1884">data di scadenza</span><span class="sxs-lookup"><span data-stu-id="888cb-1884">data di scadenza</span></span> 
- <span data-ttu-id="888cb-1885">data em que expira</span><span class="sxs-lookup"><span data-stu-id="888cb-1885">data em que expira</span></span> 
- <span data-ttu-id="888cb-1886">data scad</span><span class="sxs-lookup"><span data-stu-id="888cb-1886">data scad</span></span> 
- <span data-ttu-id="888cb-1887">data scadenza</span><span class="sxs-lookup"><span data-stu-id="888cb-1887">data scadenza</span></span> 
- <span data-ttu-id="888cb-1888">date de validité</span><span class="sxs-lookup"><span data-stu-id="888cb-1888">date de validité</span></span> 
- <span data-ttu-id="888cb-1889">datum afloop</span><span class="sxs-lookup"><span data-stu-id="888cb-1889">datum afloop</span></span> 
- <span data-ttu-id="888cb-1890">datum van exp</span><span class="sxs-lookup"><span data-stu-id="888cb-1890">datum van exp</span></span> 
- <span data-ttu-id="888cb-1891">de afloop</span><span class="sxs-lookup"><span data-stu-id="888cb-1891">de afloop</span></span> 
- <span data-ttu-id="888cb-1892">espira</span><span class="sxs-lookup"><span data-stu-id="888cb-1892">espira</span></span> 
- <span data-ttu-id="888cb-1893">espira</span><span class="sxs-lookup"><span data-stu-id="888cb-1893">espira</span></span> 
- <span data-ttu-id="888cb-1894">exp date</span><span class="sxs-lookup"><span data-stu-id="888cb-1894">exp date</span></span> 
- <span data-ttu-id="888cb-1895">exp datum</span><span class="sxs-lookup"><span data-stu-id="888cb-1895">exp datum</span></span> 
- <span data-ttu-id="888cb-1896">时间</span><span class="sxs-lookup"><span data-stu-id="888cb-1896">expiration</span></span> 
- <span data-ttu-id="888cb-1897">何时</span><span class="sxs-lookup"><span data-stu-id="888cb-1897">expire</span></span> 
- <span data-ttu-id="888cb-1898">不久</span><span class="sxs-lookup"><span data-stu-id="888cb-1898">expires</span></span> 
- <span data-ttu-id="888cb-1899">过期</span><span class="sxs-lookup"><span data-stu-id="888cb-1899">expiry</span></span> 
- <span data-ttu-id="888cb-1900">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="888cb-1900">fecha de expiracion</span></span> 
- <span data-ttu-id="888cb-1901">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="888cb-1901">fecha de venc</span></span> 
- <span data-ttu-id="888cb-1902">gultig bis</span><span class="sxs-lookup"><span data-stu-id="888cb-1902">gultig bis</span></span> 
- <span data-ttu-id="888cb-1903">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="888cb-1903">gultigkeitsdatum</span></span> 
- <span data-ttu-id="888cb-1904">gültig bis</span><span class="sxs-lookup"><span data-stu-id="888cb-1904">gültig bis</span></span> 
- <span data-ttu-id="888cb-1905">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="888cb-1905">gültigkeitsdatum</span></span> 
- <span data-ttu-id="888cb-1906">la scadenza</span><span class="sxs-lookup"><span data-stu-id="888cb-1906">la scadenza</span></span> 
- <span data-ttu-id="888cb-1907">scadenza</span><span class="sxs-lookup"><span data-stu-id="888cb-1907">scadenza</span></span> 
- <span data-ttu-id="888cb-1908">valable</span><span class="sxs-lookup"><span data-stu-id="888cb-1908">valable</span></span> 
- <span data-ttu-id="888cb-1909">validade</span><span class="sxs-lookup"><span data-stu-id="888cb-1909">validade</span></span> 
- <span data-ttu-id="888cb-1910">valido hasta</span><span class="sxs-lookup"><span data-stu-id="888cb-1910">valido hasta</span></span> 
- <span data-ttu-id="888cb-1911">valor</span><span class="sxs-lookup"><span data-stu-id="888cb-1911">valor</span></span> 
- <span data-ttu-id="888cb-1912">venc</span><span class="sxs-lookup"><span data-stu-id="888cb-1912">venc</span></span> 
- <span data-ttu-id="888cb-1913">vencimento</span><span class="sxs-lookup"><span data-stu-id="888cb-1913">vencimento</span></span> 
- <span data-ttu-id="888cb-1914">vencimiento</span><span class="sxs-lookup"><span data-stu-id="888cb-1914">vencimiento</span></span> 
- <span data-ttu-id="888cb-1915">verloopt</span><span class="sxs-lookup"><span data-stu-id="888cb-1915">verloopt</span></span> 
- <span data-ttu-id="888cb-1916">vervaldag</span><span class="sxs-lookup"><span data-stu-id="888cb-1916">vervaldag</span></span> 
- <span data-ttu-id="888cb-1917">vervaldatum</span><span class="sxs-lookup"><span data-stu-id="888cb-1917">vervaldatum</span></span> 
- <span data-ttu-id="888cb-1918">vto</span><span class="sxs-lookup"><span data-stu-id="888cb-1918">vto</span></span> 
- <span data-ttu-id="888cb-1919">válido hasta</span><span class="sxs-lookup"><span data-stu-id="888cb-1919">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="888cb-1920">欧盟驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="888cb-1920">EU Driver's License Number</span></span>

<span data-ttu-id="888cb-1921">若要了解详细信息, 请参阅[EU 驱动程序的许可号敏感信息类型](eu-driver-s-license-number.md)。</span><span class="sxs-lookup"><span data-stu-id="888cb-1921">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="888cb-1922">欧盟国家身份证号</span><span class="sxs-lookup"><span data-stu-id="888cb-1922">EU National Identification Number</span></span>

<span data-ttu-id="888cb-1923">若要了解详细信息, 请参阅[EU 国家身份证号敏感信息类型](eu-national-identification-number.md)。</span><span class="sxs-lookup"><span data-stu-id="888cb-1923">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="888cb-1924">EU 护照号码</span><span class="sxs-lookup"><span data-stu-id="888cb-1924">EU Passport Number</span></span>

<span data-ttu-id="888cb-1925">若要了解详细信息, 请参阅[EU 护照号敏感信息类型](eu-passport-number.md)。</span><span class="sxs-lookup"><span data-stu-id="888cb-1925">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="888cb-1926">欧盟社会安全号码或等效 ID</span><span class="sxs-lookup"><span data-stu-id="888cb-1926">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="888cb-1927">若要了解详细信息, 请参阅[EU 社会保险号或等效 ID 敏感信息类型](eu-social-security-number-or-equivalent-id.md)。</span><span class="sxs-lookup"><span data-stu-id="888cb-1927">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="888cb-1928">EU 税标识号</span><span class="sxs-lookup"><span data-stu-id="888cb-1928">EU Tax Identification Number</span></span>

<span data-ttu-id="888cb-1929">若要了解详细信息, 请参阅[EU 纳税识别号敏感信息类型](eu-tax-identification-number.md)。</span><span class="sxs-lookup"><span data-stu-id="888cb-1929">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="888cb-1930">芬兰国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="888cb-1930">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="888cb-1931">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-1931">Format</span></span>

<span data-ttu-id="888cb-1932">六个数字加一个字符（表示一个世纪），加三个数字再加一个校验位</span><span class="sxs-lookup"><span data-stu-id="888cb-1932">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-1933">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-1933">Pattern</span></span>

<span data-ttu-id="888cb-1934">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="888cb-1934">Pattern must include all of the following:</span></span>
- <span data-ttu-id="888cb-1935">采用 DDMMYY 格式的六位数字，表示出生日期</span><span class="sxs-lookup"><span data-stu-id="888cb-1935">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="888cb-1936">世纪标记（“-”、“+”或“a”）</span><span class="sxs-lookup"><span data-stu-id="888cb-1936">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="888cb-1937">三位个人标识号</span><span class="sxs-lookup"><span data-stu-id="888cb-1937">Three-digit personal identification number</span></span> 
- <span data-ttu-id="888cb-1938">一个数字或字母（区分大小写），是校验位</span><span class="sxs-lookup"><span data-stu-id="888cb-1938">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-1939">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-1939">Checksum</span></span>

<span data-ttu-id="888cb-1940">是</span><span class="sxs-lookup"><span data-stu-id="888cb-1940">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-1941">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-1941">Definition</span></span>

<span data-ttu-id="888cb-1942">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-1942">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-1943">函数 Func_finnish_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-1943">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-1944">找到 Keyword_finnish_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-1944">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="888cb-1945">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-1945">The checksum passes.</span></span>

```
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-1946">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-1946">Keywords</span></span>

- <span data-ttu-id="888cb-1947">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="888cb-1947">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="888cb-1948">Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="888cb-1948">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="888cb-1949">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="888cb-1949">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="888cb-1950">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="888cb-1950">Personbeteckning</span></span>
- <span data-ttu-id="888cb-1951">Personnummer</span><span class="sxs-lookup"><span data-stu-id="888cb-1951">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="888cb-1952">芬兰护照号</span><span class="sxs-lookup"><span data-stu-id="888cb-1952">Finland Passport Number</span></span>

<span data-ttu-id="888cb-1953">设置九个字母和数字的组合的组合九个字母和数字的组合: 两个字母 (不区分大小写) 七个数字校验和无定义 DLP 策略是 75% 确信它检测到这种类型的敏感信息, 如果在300个字符的邻近性: 正则表达式 Regex_finland_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-1953">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
<span data-ttu-id="888cb-1954">找到 Keyword_finland_passport_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-1954">A keyword from Keyword_finland_passport_number is found.</span></span>
<span data-ttu-id="888cb-1955"><!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="888cb-1955"></span></span>
<span data-ttu-id="888cb-1956">关键字 Keyword_finland_passport_number passport Passi</span><span class="sxs-lookup"><span data-stu-id="888cb-1956">Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="888cb-1957">法国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="888cb-1957">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-1958">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-1958">Format</span></span>

<span data-ttu-id="888cb-1959">12 个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-1959">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-1960">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-1960">Pattern</span></span>

<span data-ttu-id="888cb-1961">12 个数字，会对类似模式（如法国电话号码）进行验证</span><span class="sxs-lookup"><span data-stu-id="888cb-1961">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-1962">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-1962">Checksum</span></span>

<span data-ttu-id="888cb-1963">否</span><span class="sxs-lookup"><span data-stu-id="888cb-1963">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-1964">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-1964">Definition</span></span>

<span data-ttu-id="888cb-1965">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-1965">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-1966">函数 Func_french_drivers_license 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-1966">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-1967">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="888cb-1967">At least one of the following is true:</span></span>
- <span data-ttu-id="888cb-1968">找到 Keyword_french_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-1968">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="888cb-1969">函数 Func_eu_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="888cb-1969">The function Func_eu_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-1970">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-1970">Keywords</span></span>

#### <a name="keywordfrenchdriverslicense"></a><span data-ttu-id="888cb-1971">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="888cb-1971">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="888cb-1972">drivers licence</span><span class="sxs-lookup"><span data-stu-id="888cb-1972">drivers licence</span></span>
- <span data-ttu-id="888cb-1973">drivers license</span><span class="sxs-lookup"><span data-stu-id="888cb-1973">drivers license</span></span>
- <span data-ttu-id="888cb-1974">driving licence</span><span class="sxs-lookup"><span data-stu-id="888cb-1974">driving licence</span></span>
- <span data-ttu-id="888cb-1975">driving license</span><span class="sxs-lookup"><span data-stu-id="888cb-1975">driving license</span></span>
- <span data-ttu-id="888cb-1976">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="888cb-1976">permis de conduire</span></span>
- <span data-ttu-id="888cb-1977">licence number</span><span class="sxs-lookup"><span data-stu-id="888cb-1977">licence number</span></span>
- <span data-ttu-id="888cb-1978">license number</span><span class="sxs-lookup"><span data-stu-id="888cb-1978">license number</span></span>
- <span data-ttu-id="888cb-1979">licence numbers</span><span class="sxs-lookup"><span data-stu-id="888cb-1979">licence numbers</span></span>
- <span data-ttu-id="888cb-1980">license numbers</span><span class="sxs-lookup"><span data-stu-id="888cb-1980">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="888cb-1981">法国国家/地区 ID 卡 (CNI)</span><span class="sxs-lookup"><span data-stu-id="888cb-1981">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="888cb-1982">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-1982">Format</span></span>

<span data-ttu-id="888cb-1983">12 个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-1983">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-1984">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-1984">Pattern</span></span>

<span data-ttu-id="888cb-1985">12 个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-1985">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-1986">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-1986">Checksum</span></span>

<span data-ttu-id="888cb-1987">否</span><span class="sxs-lookup"><span data-stu-id="888cb-1987">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-1988">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-1988">Definition</span></span>

<span data-ttu-id="888cb-1989">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-1989">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-1990">正则表达式 Regex_france_cni 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-1990">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-1991">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-1991">Keywords</span></span>

<span data-ttu-id="888cb-1992">None</span><span class="sxs-lookup"><span data-stu-id="888cb-1992">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="888cb-1993">法国护照号码</span><span class="sxs-lookup"><span data-stu-id="888cb-1993">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-1994">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-1994">Format</span></span>

<span data-ttu-id="888cb-1995">9 个数字和字母</span><span class="sxs-lookup"><span data-stu-id="888cb-1995">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-1996">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-1996">Pattern</span></span>

<span data-ttu-id="888cb-1997">九位数字和字母：</span><span class="sxs-lookup"><span data-stu-id="888cb-1997">Nine digits and letters:</span></span>
- <span data-ttu-id="888cb-1998">两位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-1998">Two digits</span></span> 
- <span data-ttu-id="888cb-1999">两个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="888cb-1999">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="888cb-2000">五位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2000">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-2001">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-2001">Checksum</span></span>

<span data-ttu-id="888cb-2002">否</span><span class="sxs-lookup"><span data-stu-id="888cb-2002">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-2003">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-2003">Definition</span></span>

<span data-ttu-id="888cb-2004">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2004">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2005">函数 Func_fr_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2005">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2006">找到 Keyword_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2006">A keyword from Keyword_passport is found.</span></span>

```
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-2007">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2007">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="888cb-2008">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="888cb-2008">Keyword_passport</span></span>

- <span data-ttu-id="888cb-2009">Passport Number</span><span class="sxs-lookup"><span data-stu-id="888cb-2009">Passport Number</span></span>
- <span data-ttu-id="888cb-2010">Passport No</span><span class="sxs-lookup"><span data-stu-id="888cb-2010">Passport No</span></span>
- <span data-ttu-id="888cb-2011">Passport #</span><span class="sxs-lookup"><span data-stu-id="888cb-2011">Passport #</span></span>
- <span data-ttu-id="888cb-2012">登记卡</span><span class="sxs-lookup"><span data-stu-id="888cb-2012">Passport#</span></span>
- <span data-ttu-id="888cb-2013">PassportID</span><span class="sxs-lookup"><span data-stu-id="888cb-2013">PassportID</span></span>
- <span data-ttu-id="888cb-2014">Passportno</span><span class="sxs-lookup"><span data-stu-id="888cb-2014">Passportno</span></span>
- <span data-ttu-id="888cb-2015">passportnumber</span><span class="sxs-lookup"><span data-stu-id="888cb-2015">passportnumber</span></span>
- <span data-ttu-id="888cb-2016">パスポート</span><span class="sxs-lookup"><span data-stu-id="888cb-2016">パスポート</span></span>
- <span data-ttu-id="888cb-2017">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="888cb-2017">パスポート番号</span></span>
- <span data-ttu-id="888cb-2018">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="888cb-2018">パスポートのNum</span></span>
- <span data-ttu-id="888cb-2019">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="888cb-2019">パスポート ＃</span></span> 
- <span data-ttu-id="888cb-2020">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="888cb-2020">Numéro de passeport</span></span>
- <span data-ttu-id="888cb-2021">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="888cb-2021">Passeport n °</span></span>
- <span data-ttu-id="888cb-2022">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="888cb-2022">Passeport Non</span></span>
- <span data-ttu-id="888cb-2023">Passeport #</span><span class="sxs-lookup"><span data-stu-id="888cb-2023">Passeport #</span></span>
- <span data-ttu-id="888cb-2024">Passeport #</span><span class="sxs-lookup"><span data-stu-id="888cb-2024">Passeport#</span></span>
- <span data-ttu-id="888cb-2025">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="888cb-2025">PasseportNon</span></span>
- <span data-ttu-id="888cb-2026">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="888cb-2026">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="888cb-2027">法国社会保险号 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="888cb-2027">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="888cb-2028">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-2028">Format</span></span>

<span data-ttu-id="888cb-2029">15 个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2029">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-2030">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2030">Pattern</span></span>

<span data-ttu-id="888cb-2031">必须匹配两种模式之一：</span><span class="sxs-lookup"><span data-stu-id="888cb-2031">Must match one of two patterns:</span></span>
- <span data-ttu-id="888cb-2032">13位数, 后跟一个空格, 后跟两个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2032">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="888cb-2033">或者</span><span class="sxs-lookup"><span data-stu-id="888cb-2033">or</span></span>
- <span data-ttu-id="888cb-2034">15 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2034">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-2035">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-2035">Checksum</span></span>

<span data-ttu-id="888cb-2036">是</span><span class="sxs-lookup"><span data-stu-id="888cb-2036">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-2037">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-2037">Definition</span></span>

<span data-ttu-id="888cb-2038">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2038">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2039">函数 Func_french_insee 或 Func_fr_insee 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2039">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2040">找到 Keyword_fr_insee 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2040">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="888cb-2041">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-2041">The checksum passes.</span></span>

<span data-ttu-id="888cb-2042">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2042">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2043">函数 Func_french_insee 或 Func_fr_insee 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2043">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2044">未找到 Keyword_fr_insee 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2044">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="888cb-2045">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-2045">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-2046">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2046">Keywords</span></span>

#### <a name="keywordfrinsee"></a><span data-ttu-id="888cb-2047">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="888cb-2047">Keyword_fr_insee</span></span>

- <span data-ttu-id="888cb-2048">insee</span><span class="sxs-lookup"><span data-stu-id="888cb-2048">insee</span></span>
- <span data-ttu-id="888cb-2049">securité sociale</span><span class="sxs-lookup"><span data-stu-id="888cb-2049">securité sociale</span></span>
- <span data-ttu-id="888cb-2050">securite sociale</span><span class="sxs-lookup"><span data-stu-id="888cb-2050">securite sociale</span></span>
- <span data-ttu-id="888cb-2051">national id</span><span class="sxs-lookup"><span data-stu-id="888cb-2051">national id</span></span>
- <span data-ttu-id="888cb-2052">national identification</span><span class="sxs-lookup"><span data-stu-id="888cb-2052">national identification</span></span>
- <span data-ttu-id="888cb-2053">numéro d identité</span><span class="sxs-lookup"><span data-stu-id="888cb-2053">numéro d'identité</span></span>
- <span data-ttu-id="888cb-2054">no d'identité</span><span class="sxs-lookup"><span data-stu-id="888cb-2054">no d'identité</span></span>
- <span data-ttu-id="888cb-2055">不。</span><span class="sxs-lookup"><span data-stu-id="888cb-2055">no.</span></span> <span data-ttu-id="888cb-2056">d'identité</span><span class="sxs-lookup"><span data-stu-id="888cb-2056">d'identité</span></span>
- <span data-ttu-id="888cb-2057">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="888cb-2057">numero d'identite</span></span>
- <span data-ttu-id="888cb-2058">no d'identite</span><span class="sxs-lookup"><span data-stu-id="888cb-2058">no d'identite</span></span>
- <span data-ttu-id="888cb-2059">不。</span><span class="sxs-lookup"><span data-stu-id="888cb-2059">no.</span></span> <span data-ttu-id="888cb-2060">d'identite</span><span class="sxs-lookup"><span data-stu-id="888cb-2060">d'identite</span></span>
- <span data-ttu-id="888cb-2061">social security number</span><span class="sxs-lookup"><span data-stu-id="888cb-2061">social security number</span></span>
- <span data-ttu-id="888cb-2062">social security code</span><span class="sxs-lookup"><span data-stu-id="888cb-2062">social security code</span></span>
- <span data-ttu-id="888cb-2063">social insurance number</span><span class="sxs-lookup"><span data-stu-id="888cb-2063">social insurance number</span></span>
- <span data-ttu-id="888cb-2064">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="888cb-2064">le numéro d'identification nationale</span></span>
- <span data-ttu-id="888cb-2065">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="888cb-2065">d'identité nationale</span></span>
- <span data-ttu-id="888cb-2066">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="888cb-2066">numéro de sécurité sociale</span></span>
- <span data-ttu-id="888cb-2067">le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="888cb-2067">le code de la sécurité sociale</span></span>
- <span data-ttu-id="888cb-2068">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="888cb-2068">numéro d'assurance sociale</span></span>
- <span data-ttu-id="888cb-2069">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="888cb-2069">numéro de sécu</span></span>
- <span data-ttu-id="888cb-2070">code sécu</span><span class="sxs-lookup"><span data-stu-id="888cb-2070">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="888cb-2071">德国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="888cb-2071">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-2072">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-2072">Format</span></span>

<span data-ttu-id="888cb-2073">11 个数字和字母组合</span><span class="sxs-lookup"><span data-stu-id="888cb-2073">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-2074">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2074">Pattern</span></span>

<span data-ttu-id="888cb-2075">11 位数字和字母（不区分大小写）：</span><span class="sxs-lookup"><span data-stu-id="888cb-2075">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="888cb-2076">一个数字或字母</span><span class="sxs-lookup"><span data-stu-id="888cb-2076">A digit or letter</span></span> 
- <span data-ttu-id="888cb-2077">两位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2077">Two digits</span></span> 
- <span data-ttu-id="888cb-2078">六位数字或字母</span><span class="sxs-lookup"><span data-stu-id="888cb-2078">Six digits or letters</span></span> 
- <span data-ttu-id="888cb-2079">一位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2079">A digit</span></span> 
- <span data-ttu-id="888cb-2080">一个数字或字母</span><span class="sxs-lookup"><span data-stu-id="888cb-2080">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-2081">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-2081">Checksum</span></span>

<span data-ttu-id="888cb-2082">是</span><span class="sxs-lookup"><span data-stu-id="888cb-2082">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-2083">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-2083">Definition</span></span>

<span data-ttu-id="888cb-2084">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2084">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2085">函数 Func_german_drivers_license 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2085">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2086">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="888cb-2086">At least one of the following is true:</span></span>
    - <span data-ttu-id="888cb-2087">找到 Keyword_german_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2087">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="888cb-2088">找到 Keyword_german_drivers_license_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2088">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="888cb-2089">找到 Keyword_german_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2089">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="888cb-2090">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-2090">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-2091">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2091">Keywords</span></span>

#### <a name="keywordgermandriverslicensenumber"></a><span data-ttu-id="888cb-2092">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="888cb-2092">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="888cb-2093">führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="888cb-2093">Führerschein</span></span>
- <span data-ttu-id="888cb-2094">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="888cb-2094">Fuhrerschein</span></span>
- <span data-ttu-id="888cb-2095">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="888cb-2095">Fuehrerschein</span></span>
- <span data-ttu-id="888cb-2096">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="888cb-2096">Führerscheinnummer</span></span>
- <span data-ttu-id="888cb-2097">Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="888cb-2097">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="888cb-2098">Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="888cb-2098">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="888cb-2099">führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="888cb-2099">Führerschein-</span></span> 
- <span data-ttu-id="888cb-2100">Fuhrerschein-</span><span class="sxs-lookup"><span data-stu-id="888cb-2100">Fuhrerschein-</span></span> 
- <span data-ttu-id="888cb-2101">Fuehrerschein-</span><span class="sxs-lookup"><span data-stu-id="888cb-2101">Fuehrerschein-</span></span> 
- <span data-ttu-id="888cb-2102">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="888cb-2102">FührerscheinnummerNr</span></span>
- <span data-ttu-id="888cb-2103">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="888cb-2103">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="888cb-2104">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="888cb-2104">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="888cb-2105">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="888cb-2105">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="888cb-2106">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="888cb-2106">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="888cb-2107">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="888cb-2107">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="888cb-2108">Führerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="888cb-2108">Führerschein- Nr</span></span>
- <span data-ttu-id="888cb-2109">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="888cb-2109">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="888cb-2110">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="888cb-2110">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="888cb-2111">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="888cb-2111">Führerschein- Klasse</span></span> 
- <span data-ttu-id="888cb-2112">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="888cb-2112">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="888cb-2113">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="888cb-2113">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="888cb-2114">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="888cb-2114">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="888cb-2115">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="888cb-2115">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="888cb-2116">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="888cb-2116">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="888cb-2117">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="888cb-2117">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="888cb-2118">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="888cb-2118">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="888cb-2119">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="888cb-2119">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="888cb-2120">Führerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="888cb-2120">Führerschein- Nr</span></span> 
- <span data-ttu-id="888cb-2121">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="888cb-2121">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="888cb-2122">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="888cb-2122">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="888cb-2123">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="888cb-2123">Führerschein- Klasse</span></span> 
- <span data-ttu-id="888cb-2124">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="888cb-2124">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="888cb-2125">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="888cb-2125">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="888cb-2126">通讯</span><span class="sxs-lookup"><span data-stu-id="888cb-2126">DL</span></span> 
- <span data-ttu-id="888cb-2127">DLS</span><span class="sxs-lookup"><span data-stu-id="888cb-2127">DLS</span></span>
- <span data-ttu-id="888cb-2128">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="888cb-2128">Driv Lic</span></span> 
- <span data-ttu-id="888cb-2129">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="888cb-2129">Driv Licen</span></span> 
- <span data-ttu-id="888cb-2130">Driv License</span><span class="sxs-lookup"><span data-stu-id="888cb-2130">Driv License</span></span>
- <span data-ttu-id="888cb-2131">Driv Licenses</span><span class="sxs-lookup"><span data-stu-id="888cb-2131">Driv Licenses</span></span> 
- <span data-ttu-id="888cb-2132">Driv Licence</span><span class="sxs-lookup"><span data-stu-id="888cb-2132">Driv Licence</span></span> 
- <span data-ttu-id="888cb-2133">Driv Licences</span><span class="sxs-lookup"><span data-stu-id="888cb-2133">Driv Licences</span></span> 
- <span data-ttu-id="888cb-2134">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="888cb-2134">Driv Lic</span></span> 
- <span data-ttu-id="888cb-2135">Driver Licen</span><span class="sxs-lookup"><span data-stu-id="888cb-2135">Driver Licen</span></span> 
- <span data-ttu-id="888cb-2136">Driver License</span><span class="sxs-lookup"><span data-stu-id="888cb-2136">Driver License</span></span> 
- <span data-ttu-id="888cb-2137">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="888cb-2137">Driver Licenses</span></span> 
- <span data-ttu-id="888cb-2138">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="888cb-2138">Driver Licence</span></span> 
- <span data-ttu-id="888cb-2139">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="888cb-2139">Driver Licences</span></span> 
- <span data-ttu-id="888cb-2140">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="888cb-2140">Drivers Lic</span></span> 
- <span data-ttu-id="888cb-2141">Drivers Licen</span><span class="sxs-lookup"><span data-stu-id="888cb-2141">Drivers Licen</span></span> 
- <span data-ttu-id="888cb-2142">Drivers License</span><span class="sxs-lookup"><span data-stu-id="888cb-2142">Drivers License</span></span> 
- <span data-ttu-id="888cb-2143">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="888cb-2143">Drivers Licenses</span></span> 
- <span data-ttu-id="888cb-2144">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="888cb-2144">Drivers Licence</span></span> 
- <span data-ttu-id="888cb-2145">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="888cb-2145">Drivers Licences</span></span> 
- <span data-ttu-id="888cb-2146">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="888cb-2146">Driver's Lic</span></span> 
- <span data-ttu-id="888cb-2147">Driver's Licen</span><span class="sxs-lookup"><span data-stu-id="888cb-2147">Driver's Licen</span></span> 
- <span data-ttu-id="888cb-2148">Driver's License</span><span class="sxs-lookup"><span data-stu-id="888cb-2148">Driver's License</span></span> 
- <span data-ttu-id="888cb-2149">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="888cb-2149">Driver's Licenses</span></span> 
- <span data-ttu-id="888cb-2150">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="888cb-2150">Driver's Licence</span></span> 
- <span data-ttu-id="888cb-2151">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="888cb-2151">Driver's Licences</span></span> 
- <span data-ttu-id="888cb-2152">Driving Lic</span><span class="sxs-lookup"><span data-stu-id="888cb-2152">Driving Lic</span></span> 
- <span data-ttu-id="888cb-2153">Driving Licen</span><span class="sxs-lookup"><span data-stu-id="888cb-2153">Driving Licen</span></span> 
- <span data-ttu-id="888cb-2154">Driving License</span><span class="sxs-lookup"><span data-stu-id="888cb-2154">Driving License</span></span> 
- <span data-ttu-id="888cb-2155">Driving Licenses</span><span class="sxs-lookup"><span data-stu-id="888cb-2155">Driving Licenses</span></span> 
- <span data-ttu-id="888cb-2156">Driving Licence</span><span class="sxs-lookup"><span data-stu-id="888cb-2156">Driving Licence</span></span> 
- <span data-ttu-id="888cb-2157">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="888cb-2157">Driving Licences</span></span>

#### <a name="keywordgermandriverslicensecollaborative"></a><span data-ttu-id="888cb-2158">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="888cb-2158">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="888cb-2159">Nr-führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="888cb-2159">Nr-Führerschein</span></span> 
- <span data-ttu-id="888cb-2160">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="888cb-2160">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="888cb-2161">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="888cb-2161">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="888cb-2162">führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="888cb-2162">No-Führerschein</span></span> 
- <span data-ttu-id="888cb-2163">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="888cb-2163">No-Fuhrerschein</span></span> 
- <span data-ttu-id="888cb-2164">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="888cb-2164">No-Fuehrerschein</span></span> 
- <span data-ttu-id="888cb-2165">N-führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="888cb-2165">N-Führerschein</span></span> 
- <span data-ttu-id="888cb-2166">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="888cb-2166">N-Fuhrerschein</span></span> 
- <span data-ttu-id="888cb-2167">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="888cb-2167">N-Fuehrerschein</span></span>
- <span data-ttu-id="888cb-2168">Nr-führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="888cb-2168">Nr-Führerschein</span></span> 
- <span data-ttu-id="888cb-2169">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="888cb-2169">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="888cb-2170">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="888cb-2170">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="888cb-2171">führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="888cb-2171">No-Führerschein</span></span> 
- <span data-ttu-id="888cb-2172">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="888cb-2172">No-Fuhrerschein</span></span> 
- <span data-ttu-id="888cb-2173">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="888cb-2173">No-Fuehrerschein</span></span> 
- <span data-ttu-id="888cb-2174">N-führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="888cb-2174">N-Führerschein</span></span> 
- <span data-ttu-id="888cb-2175">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="888cb-2175">N-Fuhrerschein</span></span> 
- <span data-ttu-id="888cb-2176">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="888cb-2176">N-Fuehrerschein</span></span> 

#### <a name="keywordgermandriverslicense"></a><span data-ttu-id="888cb-2177">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="888cb-2177">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="888cb-2178">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="888cb-2178">ausstellungsdatum</span></span>
- <span data-ttu-id="888cb-2179">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="888cb-2179">ausstellungsort</span></span>
- <span data-ttu-id="888cb-2180">ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="888cb-2180">ausstellende behöde</span></span>
- <span data-ttu-id="888cb-2181">ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="888cb-2181">ausstellende behorde</span></span>
- <span data-ttu-id="888cb-2182">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="888cb-2182">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="888cb-2183">德国护照号码</span><span class="sxs-lookup"><span data-stu-id="888cb-2183">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-2184">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-2184">Format</span></span>

<span data-ttu-id="888cb-2185">10 个数字或字母</span><span class="sxs-lookup"><span data-stu-id="888cb-2185">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-2186">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2186">Pattern</span></span>

<span data-ttu-id="888cb-2187">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="888cb-2187">Pattern must include all of the following:</span></span>
- <span data-ttu-id="888cb-2188">第一个字符是这一组（C、F、G、H、J、K）中的数字或字母</span><span class="sxs-lookup"><span data-stu-id="888cb-2188">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="888cb-2189">三位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2189">Three digits</span></span> 
- <span data-ttu-id="888cb-2190">五位数字或字母都来源于这一组（C、-H、J-N、P、R、T，V-Z）</span><span class="sxs-lookup"><span data-stu-id="888cb-2190">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="888cb-2191">一位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2191">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-2192">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-2192">Checksum</span></span>

<span data-ttu-id="888cb-2193">是</span><span class="sxs-lookup"><span data-stu-id="888cb-2193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-2194">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-2194">Definition</span></span>

<span data-ttu-id="888cb-2195">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2196">函数 Func_german_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2196">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2197">找到以下任意五个关键字列表中的关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2197">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="888cb-2198">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-2198">The checksum passes.</span></span>

<span data-ttu-id="888cb-2199">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2199">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2200">函数 Func_german_passport_data 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2200">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2201">找到以下任意五个关键字列表中的关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2201">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="888cb-2202">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-2202">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-2203">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2203">Keywords</span></span>

#### <a name="keywordgermanpassport"></a><span data-ttu-id="888cb-2204">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="888cb-2204">Keyword_german_passport</span></span>

- <span data-ttu-id="888cb-2205">reisepass</span><span class="sxs-lookup"><span data-stu-id="888cb-2205">reisepass</span></span>
- <span data-ttu-id="888cb-2206">reisepasse</span><span class="sxs-lookup"><span data-stu-id="888cb-2206">reisepasse</span></span>
- <span data-ttu-id="888cb-2207">reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="888cb-2207">reisepassnummer</span></span>
- <span data-ttu-id="888cb-2208">登记卡</span><span class="sxs-lookup"><span data-stu-id="888cb-2208">passport</span></span>
- <span data-ttu-id="888cb-2209">passports</span><span class="sxs-lookup"><span data-stu-id="888cb-2209">passports</span></span>

#### <a name="keywordgermanpassportcollaborative"></a><span data-ttu-id="888cb-2210">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="888cb-2210">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="888cb-2211">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="888cb-2211">geburtsdatum</span></span>
- <span data-ttu-id="888cb-2212">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="888cb-2212">ausstellungsdatum</span></span>
- <span data-ttu-id="888cb-2213">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="888cb-2213">ausstellungsort</span></span>

#### <a name="keywordgermanpassportnumber"></a><span data-ttu-id="888cb-2214">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="888cb-2214">Keyword_german_passport_number</span></span>

<span data-ttu-id="888cb-2215">Reisepass Nr-Reisepass</span><span class="sxs-lookup"><span data-stu-id="888cb-2215">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keywordgermanpassport1"></a><span data-ttu-id="888cb-2216">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="888cb-2216">Keyword_german_passport1</span></span>

<span data-ttu-id="888cb-2217">Reisepass-Nr</span><span class="sxs-lookup"><span data-stu-id="888cb-2217">Reisepass-Nr</span></span>

#### <a name="keywordgermanpassport2"></a><span data-ttu-id="888cb-2218">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="888cb-2218">Keyword_german_passport2</span></span>

<span data-ttu-id="888cb-2219">bnationalit</span><span class="sxs-lookup"><span data-stu-id="888cb-2219">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="888cb-2220">德国身份证号码</span><span class="sxs-lookup"><span data-stu-id="888cb-2220">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-2221">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-2221">Format</span></span>

<span data-ttu-id="888cb-2222">自2010年11月1日起: 九个字母和数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2222">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="888cb-2223">从1年4月1987至31年10月 2010:10 位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2223">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-2224">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2224">Pattern</span></span>

<span data-ttu-id="888cb-2225">自 2010 年 11 月 1 日起：</span><span class="sxs-lookup"><span data-stu-id="888cb-2225">Since 1 November 2010:</span></span>
- <span data-ttu-id="888cb-2226">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="888cb-2226">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="888cb-2227">八个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2227">Eight digits</span></span>

<span data-ttu-id="888cb-2228">介于1年4月1987至 31 10 月 2010:</span><span class="sxs-lookup"><span data-stu-id="888cb-2228">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="888cb-2229">10 个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2229">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-2230">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-2230">Checksum</span></span>

<span data-ttu-id="888cb-2231">否</span><span class="sxs-lookup"><span data-stu-id="888cb-2231">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-2232">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-2232">Definition</span></span>

<span data-ttu-id="888cb-2233">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2233">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2234">正则表达式 Regex_germany_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2234">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2235">找到 Keyword_germany_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2235">A keyword from Keyword_germany_id_card is found.</span></span>

```
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-2236">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2236">Keywords</span></span>

#### <a name="keywordgermanyidcard"></a><span data-ttu-id="888cb-2237">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="888cb-2237">Keyword_germany_id_card</span></span>

- <span data-ttu-id="888cb-2238">Identity Card</span><span class="sxs-lookup"><span data-stu-id="888cb-2238">Identity Card</span></span>
- <span data-ttu-id="888cb-2239">ID</span><span class="sxs-lookup"><span data-stu-id="888cb-2239">ID</span></span>
- <span data-ttu-id="888cb-2240">id</span><span class="sxs-lookup"><span data-stu-id="888cb-2240">Identification</span></span>
- <span data-ttu-id="888cb-2241">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="888cb-2241">Personalausweis</span></span>
- <span data-ttu-id="888cb-2242">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="888cb-2242">Identifizierungsnummer</span></span>
- <span data-ttu-id="888cb-2243">Ausweis</span><span class="sxs-lookup"><span data-stu-id="888cb-2243">Ausweis</span></span>
- <span data-ttu-id="888cb-2244">Identifikation</span><span class="sxs-lookup"><span data-stu-id="888cb-2244">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="888cb-2245">希腊国家 ID 卡</span><span class="sxs-lookup"><span data-stu-id="888cb-2245">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="888cb-2246">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-2246">Format</span></span>

<span data-ttu-id="888cb-2247">7-8 个字母和数字组合加一个短划线</span><span class="sxs-lookup"><span data-stu-id="888cb-2247">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-2248">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2248">Pattern</span></span>

<span data-ttu-id="888cb-2249">七个字母和数字（旧格式）：</span><span class="sxs-lookup"><span data-stu-id="888cb-2249">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="888cb-2250">一个字母（希腊字母表中的任一字母） </span><span class="sxs-lookup"><span data-stu-id="888cb-2250">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="888cb-2251">一个短划线 </span><span class="sxs-lookup"><span data-stu-id="888cb-2251">A dash</span></span> 
- <span data-ttu-id="888cb-2252">六位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2252">Six digits</span></span>

<span data-ttu-id="888cb-2253">八个字母和数字（新格式）：</span><span class="sxs-lookup"><span data-stu-id="888cb-2253">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="888cb-2254">大写字符同时出现在希腊和拉丁字母表中的两个字母 (ABEZHIKMNOPTYX) </span><span class="sxs-lookup"><span data-stu-id="888cb-2254">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="888cb-2255">一个短划线 </span><span class="sxs-lookup"><span data-stu-id="888cb-2255">A dash</span></span> 
- <span data-ttu-id="888cb-2256">六位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2256">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-2257">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-2257">Checksum</span></span>

<span data-ttu-id="888cb-2258">否</span><span class="sxs-lookup"><span data-stu-id="888cb-2258">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-2259">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-2259">Definition</span></span>

<span data-ttu-id="888cb-2260">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2260">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2261">正则表达式 Regex_greece_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2261">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2262">找到 Keyword_greece_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2262">A keyword from Keyword_greece_id_card is found.</span></span>

```
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-2263">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2263">Keywords</span></span>

#### <a name="keywordgreeceidcard"></a><span data-ttu-id="888cb-2264">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="888cb-2264">Keyword_greece_id_card</span></span>

- <span data-ttu-id="888cb-2265">Greek identity Card</span><span class="sxs-lookup"><span data-stu-id="888cb-2265">Greek identity Card</span></span>
- <span data-ttu-id="888cb-2266">Tautotita</span><span class="sxs-lookup"><span data-stu-id="888cb-2266">Tautotita</span></span>
- <span data-ttu-id="888cb-2267">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="888cb-2267">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="888cb-2268">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="888cb-2268">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="888cb-2269">香港身份证 (HKID) 号</span><span class="sxs-lookup"><span data-stu-id="888cb-2269">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-2270">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-2270">Format</span></span>

<span data-ttu-id="888cb-2271">8-9 个字母和数字组合，最后一个字符两边可选择加括号</span><span class="sxs-lookup"><span data-stu-id="888cb-2271">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-2272">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2272">Pattern</span></span>

<span data-ttu-id="888cb-2273">8-9 个字母组合：</span><span class="sxs-lookup"><span data-stu-id="888cb-2273">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="888cb-2274">1-2 个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="888cb-2274">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="888cb-2275">六个数字 </span><span class="sxs-lookup"><span data-stu-id="888cb-2275">Six digits</span></span> 
- <span data-ttu-id="888cb-2276">最后一个字符（任意数字或字母 A）是校验位，两边可以选择加括号。</span><span class="sxs-lookup"><span data-stu-id="888cb-2276">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-2277">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-2277">Checksum</span></span>

<span data-ttu-id="888cb-2278">是</span><span class="sxs-lookup"><span data-stu-id="888cb-2278">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-2279">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-2279">Definition</span></span>

<span data-ttu-id="888cb-2280">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2281">函数 Func_hong_kong_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2281">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2282">找到 Keyword_hong_kong_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2282">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="888cb-2283">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-2283">The checksum passes.</span></span>

<span data-ttu-id="888cb-2284">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2284">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2285">函数 Func_hong_kong_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2285">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2286">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-2286">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-2287">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2287">Keywords</span></span>

#### <a name="keywordhongkongidcard"></a><span data-ttu-id="888cb-2288">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="888cb-2288">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="888cb-2289">中国香港恒等卡片</span><span class="sxs-lookup"><span data-stu-id="888cb-2289">hong kong identity card</span></span>
- <span data-ttu-id="888cb-2290">HKIDC</span><span class="sxs-lookup"><span data-stu-id="888cb-2290">HKIDC</span></span>
- <span data-ttu-id="888cb-2291">id card</span><span class="sxs-lookup"><span data-stu-id="888cb-2291">id card</span></span>
- <span data-ttu-id="888cb-2292">identity card</span><span class="sxs-lookup"><span data-stu-id="888cb-2292">identity card</span></span>
- <span data-ttu-id="888cb-2293">hk identity 卡片</span><span class="sxs-lookup"><span data-stu-id="888cb-2293">hk identity card</span></span>
- <span data-ttu-id="888cb-2294">香港 id</span><span class="sxs-lookup"><span data-stu-id="888cb-2294">hong kong id</span></span>
- <span data-ttu-id="888cb-2295">香港身份證</span><span class="sxs-lookup"><span data-stu-id="888cb-2295">香港身份證</span></span>
- <span data-ttu-id="888cb-2296">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="888cb-2296">香港永久性居民身份證</span></span>
- <span data-ttu-id="888cb-2297">證</span><span class="sxs-lookup"><span data-stu-id="888cb-2297">身份證</span></span>
- <span data-ttu-id="888cb-2298">身份証</span><span class="sxs-lookup"><span data-stu-id="888cb-2298">身份証</span></span>
- <span data-ttu-id="888cb-2299">身分證</span><span class="sxs-lookup"><span data-stu-id="888cb-2299">身分證</span></span>
- <span data-ttu-id="888cb-2300">身分証</span><span class="sxs-lookup"><span data-stu-id="888cb-2300">身分証</span></span>
- <span data-ttu-id="888cb-2301">香港身份証</span><span class="sxs-lookup"><span data-stu-id="888cb-2301">香港身份証</span></span>
- <span data-ttu-id="888cb-2302">香港身分證</span><span class="sxs-lookup"><span data-stu-id="888cb-2302">香港身分證</span></span>
- <span data-ttu-id="888cb-2303">香港身分証</span><span class="sxs-lookup"><span data-stu-id="888cb-2303">香港身分証</span></span>
- <span data-ttu-id="888cb-2304">香港身份證</span><span class="sxs-lookup"><span data-stu-id="888cb-2304">香港身份證</span></span>
- <span data-ttu-id="888cb-2305">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="888cb-2305">香港居民身份證</span></span>
- <span data-ttu-id="888cb-2306">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="888cb-2306">香港居民身份証</span></span>
- <span data-ttu-id="888cb-2307">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="888cb-2307">香港居民身分證</span></span>
- <span data-ttu-id="888cb-2308">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="888cb-2308">香港居民身分証</span></span>
- <span data-ttu-id="888cb-2309">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="888cb-2309">香港永久性居民身份証</span></span>
- <span data-ttu-id="888cb-2310">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="888cb-2310">香港永久性居民身分證</span></span>
- <span data-ttu-id="888cb-2311">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="888cb-2311">香港永久性居民身分証</span></span>
- <span data-ttu-id="888cb-2312">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="888cb-2312">香港永久性居民身份證</span></span>
- <span data-ttu-id="888cb-2313">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="888cb-2313">香港非永久性居民身份證</span></span>
- <span data-ttu-id="888cb-2314">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="888cb-2314">香港非永久性居民身份証</span></span>
- <span data-ttu-id="888cb-2315">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="888cb-2315">香港非永久性居民身分證</span></span>
- <span data-ttu-id="888cb-2316">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="888cb-2316">香港非永久性居民身分証</span></span>
- <span data-ttu-id="888cb-2317">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="888cb-2317">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="888cb-2318">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="888cb-2318">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="888cb-2319">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="888cb-2319">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="888cb-2320">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="888cb-2320">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="888cb-2321">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="888cb-2321">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="888cb-2322">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="888cb-2322">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="888cb-2323">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="888cb-2323">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="888cb-2324">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="888cb-2324">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="888cb-2325">印度永久帐号 (PAN)</span><span class="sxs-lookup"><span data-stu-id="888cb-2325">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="888cb-2326">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-2326">Format</span></span>

<span data-ttu-id="888cb-2327">10 个字母或数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2327">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-2328">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2328">Pattern</span></span>

<span data-ttu-id="888cb-2329">10 个字母或数字：</span><span class="sxs-lookup"><span data-stu-id="888cb-2329">10 letters or digits:</span></span>
- <span data-ttu-id="888cb-2330">五个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="888cb-2330">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="888cb-2331">四位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2331">Four digits</span></span> 
- <span data-ttu-id="888cb-2332">一个字母，是字母校验位</span><span class="sxs-lookup"><span data-stu-id="888cb-2332">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-2333">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-2333">Checksum</span></span>

<span data-ttu-id="888cb-2334">是</span><span class="sxs-lookup"><span data-stu-id="888cb-2334">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-2335">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-2335">Definition</span></span>

<span data-ttu-id="888cb-2336">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2336">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2337">正则表达式 Regex_india_permanent_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2337">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2338">找到 Keyword_india_permanent_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2338">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="888cb-2339">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-2339">The checksum passes.</span></span>

```
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-2340">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2340">Keywords</span></span>

#### <a name="keywordindiapermanentaccountnumber"></a><span data-ttu-id="888cb-2341">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="888cb-2341">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="888cb-2342">Permanent Account Number</span><span class="sxs-lookup"><span data-stu-id="888cb-2342">Permanent Account Number</span></span> 
- <span data-ttu-id="888cb-2343">蛋糕</span><span class="sxs-lookup"><span data-stu-id="888cb-2343">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="888cb-2344">India Unique Identification (Aadhaar) Number</span><span class="sxs-lookup"><span data-stu-id="888cb-2344">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-2345">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-2345">Format</span></span>

<span data-ttu-id="888cb-2346">12 个数字（包含可选空格或短划线）</span><span class="sxs-lookup"><span data-stu-id="888cb-2346">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-2347">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2347">Pattern</span></span>

<span data-ttu-id="888cb-2348">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="888cb-2348">12 digits:</span></span>
- <span data-ttu-id="888cb-2349">四个数字 </span><span class="sxs-lookup"><span data-stu-id="888cb-2349">Four digits</span></span> 
- <span data-ttu-id="888cb-2350">一个可选空格或短划线 </span><span class="sxs-lookup"><span data-stu-id="888cb-2350">An optional space or dash</span></span> 
- <span data-ttu-id="888cb-2351">四个数字 </span><span class="sxs-lookup"><span data-stu-id="888cb-2351">Four digits</span></span> 
- <span data-ttu-id="888cb-2352">一个可选空格或短划线 </span><span class="sxs-lookup"><span data-stu-id="888cb-2352">An optional space or dash</span></span> 
- <span data-ttu-id="888cb-2353">最后一个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="888cb-2353">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-2354">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-2354">Checksum</span></span>

<span data-ttu-id="888cb-2355">是</span><span class="sxs-lookup"><span data-stu-id="888cb-2355">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-2356">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-2356">Definition</span></span>

<span data-ttu-id="888cb-2357">DLP 策略 85% 确信在300个字符的邻近度内检测到此类型的敏感信息: 函数 Func_india_aadhaar 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2357">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="888cb-2358">找到 Keyword_india_aadhar 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2358">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="888cb-2359">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-2359">The checksum passes.</span></span>
<span data-ttu-id="888cb-2360">DLP 策略 75% 确信在300个字符的邻近度内检测到此类型的敏感信息: 函数 Func_india_aadhaar 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="888cb-2361">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-2361">The checksum passes.</span></span>
<span data-ttu-id="888cb-2362"><!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="888cb-2362"></span></span>

### <a name="keywords"></a><span data-ttu-id="888cb-2363">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2363">Keywords</span></span>
   
#### <a name="keywordindiaaadhar"></a><span data-ttu-id="888cb-2364">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="888cb-2364">Keyword_india_aadhar</span></span>
- <span data-ttu-id="888cb-2365">Aadhar</span><span class="sxs-lookup"><span data-stu-id="888cb-2365">Aadhar</span></span>
- <span data-ttu-id="888cb-2366">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="888cb-2366">Aadhaar</span></span>
- <span data-ttu-id="888cb-2367">UID</span><span class="sxs-lookup"><span data-stu-id="888cb-2367">UID</span></span>
- <span data-ttu-id="888cb-2368">आधार</span><span class="sxs-lookup"><span data-stu-id="888cb-2368">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="888cb-2369">印度尼西亚身份证 (KTP) 号</span><span class="sxs-lookup"><span data-stu-id="888cb-2369">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-2370">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-2370">Format</span></span>

<span data-ttu-id="888cb-2371">16 个数字（包含可选点）</span><span class="sxs-lookup"><span data-stu-id="888cb-2371">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-2372">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2372">Pattern</span></span>

<span data-ttu-id="888cb-2373">16 个数字：</span><span class="sxs-lookup"><span data-stu-id="888cb-2373">16 digits:</span></span>
- <span data-ttu-id="888cb-2374">两位省代码 </span><span class="sxs-lookup"><span data-stu-id="888cb-2374">Two-digit province code</span></span> 
- <span data-ttu-id="888cb-2375">一个点（可选） </span><span class="sxs-lookup"><span data-stu-id="888cb-2375">A period (optional)</span></span> 
- <span data-ttu-id="888cb-2376">两位摄政统治区或城市代码 </span><span class="sxs-lookup"><span data-stu-id="888cb-2376">Two-digit regency or city code</span></span> 
- <span data-ttu-id="888cb-2377">两位住宅小区代码 </span><span class="sxs-lookup"><span data-stu-id="888cb-2377">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="888cb-2378">一个点（可选） </span><span class="sxs-lookup"><span data-stu-id="888cb-2378">A period (optional)</span></span> 
- <span data-ttu-id="888cb-2379">六个数字，采用  DDMMYY 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="888cb-2379">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="888cb-2380">一个点（可选） </span><span class="sxs-lookup"><span data-stu-id="888cb-2380">A period (optional)</span></span> 
- <span data-ttu-id="888cb-2381">四位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2381">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-2382">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-2382">Checksum</span></span>

<span data-ttu-id="888cb-2383">否</span><span class="sxs-lookup"><span data-stu-id="888cb-2383">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-2384">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-2384">Definition</span></span>

<span data-ttu-id="888cb-2385">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2386">正则表达式 Regex_indonesia_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2386">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2387">找到 Keyword_indonesia_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2387">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="888cb-2388">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2388">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2389">正则表达式 Regex_indonesia_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2389">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-2390">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2390">Keywords</span></span>
   
#### <a name="keywordindonesiaidcard"></a><span data-ttu-id="888cb-2391">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="888cb-2391">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="888cb-2392">KTP</span><span class="sxs-lookup"><span data-stu-id="888cb-2392">KTP</span></span>
- <span data-ttu-id="888cb-2393">Kartu Tanda Penduduk</span><span class="sxs-lookup"><span data-stu-id="888cb-2393">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="888cb-2394">Nomor Induk Kependudukan</span><span class="sxs-lookup"><span data-stu-id="888cb-2394">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="888cb-2395">国际银行帐号 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="888cb-2395">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="888cb-2396">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-2396">Format</span></span>

<span data-ttu-id="888cb-2397">国家/地区代码（两个字母）加校验位（两个数字）以及 bban 号码（最多 30 个字符）</span><span class="sxs-lookup"><span data-stu-id="888cb-2397">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-2398">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2398">Pattern</span></span>

<span data-ttu-id="888cb-2399">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="888cb-2399">Pattern must include all of the following:</span></span>

- <span data-ttu-id="888cb-2400">两个字母的国家/地区代码</span><span class="sxs-lookup"><span data-stu-id="888cb-2400">Two-letter country code</span></span>
- <span data-ttu-id="888cb-2401">两个校验位（后跟一个可选空间） </span><span class="sxs-lookup"><span data-stu-id="888cb-2401">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="888cb-2402">1-7 个包含 4 个字母或数字的组（可以使用空格进行分隔）</span><span class="sxs-lookup"><span data-stu-id="888cb-2402">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="888cb-2403">1-3 个字母或数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2403">1-3 letters or digits</span></span>

<span data-ttu-id="888cb-p134">每个国家/地区的格式稍有不同。IBAN 敏感信息类型涵盖这 60 个国家/地区：</span><span class="sxs-lookup"><span data-stu-id="888cb-p134">The format for each country is slightly different. The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="888cb-2406">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span><span class="sxs-lookup"><span data-stu-id="888cb-2406">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-2407">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-2407">Checksum</span></span>

<span data-ttu-id="888cb-2408">是</span><span class="sxs-lookup"><span data-stu-id="888cb-2408">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-2409">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-2409">Definition</span></span>

<span data-ttu-id="888cb-2410">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2410">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2411">函数 Func_iban 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2411">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2412">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-2412">The checksum passes.</span></span>

```
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-2413">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2413">Keywords</span></span>

<span data-ttu-id="888cb-2414">None</span><span class="sxs-lookup"><span data-stu-id="888cb-2414">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="888cb-2415">IP 地址</span><span class="sxs-lookup"><span data-stu-id="888cb-2415">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="888cb-2416">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-2416">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="888cb-2417">IPv4</span><span class="sxs-lookup"><span data-stu-id="888cb-2417">IPv4:</span></span>
<span data-ttu-id="888cb-2418">解释 IPv4 地址格式化（点）版本或非格式化（没有点）版本的复杂模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2418">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="888cb-2419">ipv4</span><span class="sxs-lookup"><span data-stu-id="888cb-2419">IPv6:</span></span>
<span data-ttu-id="888cb-2420"> 解释格式化 IPv6 号码（包含冒号）的复杂模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2420">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-2421">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2421">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-2422">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-2422">Checksum</span></span>

<span data-ttu-id="888cb-2423">否</span><span class="sxs-lookup"><span data-stu-id="888cb-2423">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-2424">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-2424">Definition</span></span>

<span data-ttu-id="888cb-2425">对于 IPv6，在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2425">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2426">正则表达式 Regex_ipv6_address 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2426">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2427">未找到 Keyword_ipaddress 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2427">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="888cb-2428">对于 IPv4，在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2428">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2429">正则表达式 Regex_ipv4_address 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2429">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2430">找到 Keyword_ipaddress 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2430">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="888cb-2431">对于 IPv6，在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2431">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2432">正则表达式 Regex_ipv6_address 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2432">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2433">未找到 Keyword_ipaddress 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2433">No keyword from Keyword_ipaddress is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-2434">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2434">Keywords</span></span>

#### <a name="keywordipaddress"></a><span data-ttu-id="888cb-2435">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="888cb-2435">Keyword_ipaddress</span></span>

- <span data-ttu-id="888cb-2436">IP（此关键字区分大小写）</span><span class="sxs-lookup"><span data-stu-id="888cb-2436">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="888cb-2437">ip address</span><span class="sxs-lookup"><span data-stu-id="888cb-2437">ip address</span></span> 
- <span data-ttu-id="888cb-2438">ip addresses</span><span class="sxs-lookup"><span data-stu-id="888cb-2438">ip addresses</span></span>
- <span data-ttu-id="888cb-2439">internet protocol</span><span class="sxs-lookup"><span data-stu-id="888cb-2439">internet protocol</span></span>
- <span data-ttu-id="888cb-2440">IP-כתובת ה</span><span class="sxs-lookup"><span data-stu-id="888cb-2440">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="888cb-2441">国际分类的 Diseases (ICD-10 CM)</span><span class="sxs-lookup"><span data-stu-id="888cb-2441">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="888cb-2442">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-2442">Format</span></span>

<span data-ttu-id="888cb-2443">Dictionary</span><span class="sxs-lookup"><span data-stu-id="888cb-2443">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-2444">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2444">Pattern</span></span>

<span data-ttu-id="888cb-2445">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2445">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-2446">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-2446">Checksum</span></span>

<span data-ttu-id="888cb-2447">否</span><span class="sxs-lookup"><span data-stu-id="888cb-2447">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-2448">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-2448">Definition</span></span>

<span data-ttu-id="888cb-2449">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2449">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2450">找到 Dictionary_icd_10_cm 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2450">A keyword from Dictionary_icd_10_cm is found.</span></span>

```
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

<span data-ttu-id="888cb-2451">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2451">Keywords</span></span>

<span data-ttu-id="888cb-2452">Dictionary_icd_10_cm 关键字词典中的任何术语, 它基于[Diseases 的国际分类、第十个修订、临床修改 (icd-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604)。</span><span class="sxs-lookup"><span data-stu-id="888cb-2452">Any term from the Dictionary_icd_10_cm keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="888cb-2453">此类型仅查找术语, 而不是保险代码。</span><span class="sxs-lookup"><span data-stu-id="888cb-2453">This type looks only for the term, not the insurance codes.</span></span>

   
## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="888cb-2454">国际分类的 Diseases (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="888cb-2454">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="888cb-2455">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-2455">Format</span></span>

<span data-ttu-id="888cb-2456">Dictionary</span><span class="sxs-lookup"><span data-stu-id="888cb-2456">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-2457">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2457">Pattern</span></span>

<span data-ttu-id="888cb-2458">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2458">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-2459">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-2459">Checksum</span></span>

<span data-ttu-id="888cb-2460">否</span><span class="sxs-lookup"><span data-stu-id="888cb-2460">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-2461">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-2461">Definition</span></span>

<span data-ttu-id="888cb-2462">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2462">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2463">找到 Dictionary_icd_9_cm 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2463">A keyword from Dictionary_icd_9_cm is found.</span></span>

```
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-2464">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2464">Keywords</span></span>

<span data-ttu-id="888cb-2465">Dictionary_icd_9_cm 关键字词典中的任何术语, 基于[Diseases 的国际分类、第九修订版、临床修改 (icd-9 cm)](https://go.microsoft.com/fwlink/?linkid=852605)。</span><span class="sxs-lookup"><span data-stu-id="888cb-2465">Any term from the Dictionary_icd_9_cm keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="888cb-2466">此类型仅查找术语, 而不是保险代码。</span><span class="sxs-lookup"><span data-stu-id="888cb-2466">This type looks only for the term, not the insurance codes.</span></span>
   
## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="888cb-2467">爱尔兰个人公共服务 (PPS) 号码</span><span class="sxs-lookup"><span data-stu-id="888cb-2467">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-2468">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-2468">Format</span></span>

<span data-ttu-id="888cb-2469">旧格式 (到 31 Dec 2012):</span><span class="sxs-lookup"><span data-stu-id="888cb-2469">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="888cb-2470">七位数字后跟 1-2  个字母 </span><span class="sxs-lookup"><span data-stu-id="888cb-2470">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="888cb-2471">新格式 (2013 年1月1日和之后):</span><span class="sxs-lookup"><span data-stu-id="888cb-2471">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="888cb-2472">七位数字后跟两个字母</span><span class="sxs-lookup"><span data-stu-id="888cb-2472">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-2473">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2473">Pattern</span></span>

<span data-ttu-id="888cb-2474">旧格式 (到 31 Dec 2012):</span><span class="sxs-lookup"><span data-stu-id="888cb-2474">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="888cb-2475">七个数字 </span><span class="sxs-lookup"><span data-stu-id="888cb-2475">Seven digits</span></span> 
- <span data-ttu-id="888cb-2476">1-2 个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="888cb-2476">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="888cb-2477">新格式 (2013 年1月1日和之后):</span><span class="sxs-lookup"><span data-stu-id="888cb-2477">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="888cb-2478">七个数字 </span><span class="sxs-lookup"><span data-stu-id="888cb-2478">Seven digits</span></span> 
- <span data-ttu-id="888cb-2479">一个字母（不区分大小写），是字母校验位 </span><span class="sxs-lookup"><span data-stu-id="888cb-2479">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="888cb-2480">字母“A”或“H”（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="888cb-2480">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-2481">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-2481">Checksum</span></span>

<span data-ttu-id="888cb-2482">是</span><span class="sxs-lookup"><span data-stu-id="888cb-2482">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-2483">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-2483">Definition</span></span>

<span data-ttu-id="888cb-2484">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2484">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2485">函数 Func_ireland_pps 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2485">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2486">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="888cb-2486">One of the following is true:</span></span>
    - <span data-ttu-id="888cb-2487">找到 Keyword_ireland_pps 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2487">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="888cb-2488">函数 Func_eu_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="888cb-2488">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="888cb-2489">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-2489">The checksum passes.</span></span>

<span data-ttu-id="888cb-2490">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2490">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2491">函数 Func_ireland_pps 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2491">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2492">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-2492">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-2493">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2493">Keywords</span></span>

#### <a name="keywordirelandpps"></a><span data-ttu-id="888cb-2494">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="888cb-2494">Keyword_ireland_pps</span></span>

- <span data-ttu-id="888cb-2495">Personal Public Service Number</span><span class="sxs-lookup"><span data-stu-id="888cb-2495">Personal Public Service Number</span></span> 
- <span data-ttu-id="888cb-2496">PPS Number</span><span class="sxs-lookup"><span data-stu-id="888cb-2496">PPS Number</span></span> 
- <span data-ttu-id="888cb-2497">PPS Num</span><span class="sxs-lookup"><span data-stu-id="888cb-2497">PPS Num</span></span> 
- <span data-ttu-id="888cb-2498">PPS No.</span><span class="sxs-lookup"><span data-stu-id="888cb-2498">PPS No.</span></span> 
- <span data-ttu-id="888cb-2499">PPS #</span><span class="sxs-lookup"><span data-stu-id="888cb-2499">PPS #</span></span> 
- <span data-ttu-id="888cb-2500">.pps</span><span class="sxs-lookup"><span data-stu-id="888cb-2500">PPS#</span></span> 
- <span data-ttu-id="888cb-2501">PPSN</span><span class="sxs-lookup"><span data-stu-id="888cb-2501">PPSN</span></span> 
- <span data-ttu-id="888cb-2502">Public Services Card</span><span class="sxs-lookup"><span data-stu-id="888cb-2502">Public Services Card</span></span> 
- <span data-ttu-id="888cb-2503">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="888cb-2503">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="888cb-2504">Uimh。</span><span class="sxs-lookup"><span data-stu-id="888cb-2504">Uimh.</span></span> <span data-ttu-id="888cb-2505">PSP</span><span class="sxs-lookup"><span data-stu-id="888cb-2505">PSP</span></span> 
- <span data-ttu-id="888cb-2506">PSP</span><span class="sxs-lookup"><span data-stu-id="888cb-2506">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="888cb-2507">以色列银行帐号</span><span class="sxs-lookup"><span data-stu-id="888cb-2507">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-2508">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-2508">Format</span></span>

<span data-ttu-id="888cb-2509">13 位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2509">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-2510">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2510">Pattern</span></span>

<span data-ttu-id="888cb-2511">格式</span><span class="sxs-lookup"><span data-stu-id="888cb-2511">Formatted:</span></span>
- <span data-ttu-id="888cb-2512">两位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2512">Two digits</span></span> 
- <span data-ttu-id="888cb-2513">破折号</span><span class="sxs-lookup"><span data-stu-id="888cb-2513">A dash</span></span> 
- <span data-ttu-id="888cb-2514">三位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2514">Three digits</span></span> 
- <span data-ttu-id="888cb-2515">破折号</span><span class="sxs-lookup"><span data-stu-id="888cb-2515">A dash</span></span> 
- <span data-ttu-id="888cb-2516">八位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2516">Eight digits</span></span>

<span data-ttu-id="888cb-2517">纯</span><span class="sxs-lookup"><span data-stu-id="888cb-2517">Unformatted:</span></span>
- <span data-ttu-id="888cb-2518">	13 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2518">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-2519">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-2519">Checksum</span></span>

<span data-ttu-id="888cb-2520">否</span><span class="sxs-lookup"><span data-stu-id="888cb-2520">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-2521">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-2521">Definition</span></span>

<span data-ttu-id="888cb-2522">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2522">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2523">正则表达式 Regex_israel_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2523">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2524">找到 Keyword_israel_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2524">A keyword from Keyword_israel_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-2525">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2525">Keywords</span></span>

#### <a name="keywordisraelbankaccountnumber"></a><span data-ttu-id="888cb-2526">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="888cb-2526">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="888cb-2527">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="888cb-2527">Bank Account Number</span></span> 
- <span data-ttu-id="888cb-2528">Bank Account</span><span class="sxs-lookup"><span data-stu-id="888cb-2528">Bank Account</span></span> 
- <span data-ttu-id="888cb-2529">Account Number</span><span class="sxs-lookup"><span data-stu-id="888cb-2529">Account Number</span></span> 
- <span data-ttu-id="888cb-2530">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="888cb-2530">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="888cb-2531">以色列国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="888cb-2531">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="888cb-2532">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-2532">Format</span></span>

<span data-ttu-id="888cb-2533">九个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2533">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-2534">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2534">Pattern</span></span>

<span data-ttu-id="888cb-2535">九个连续的数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2535">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-2536">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-2536">Checksum</span></span>

<span data-ttu-id="888cb-2537">是</span><span class="sxs-lookup"><span data-stu-id="888cb-2537">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-2538">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-2538">Definition</span></span>

<span data-ttu-id="888cb-2539">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2539">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2540">函数 Func_israeli_national_id_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2540">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2541">找到 Keyword_Israel_National_ID 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2541">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="888cb-2542">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-2542">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-2543">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2543">Keywords</span></span>

#### <a name="keywordisraelnationalid"></a><span data-ttu-id="888cb-2544">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="888cb-2544">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="888cb-2545">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="888cb-2545">מספר זהות</span></span> 
- <span data-ttu-id="888cb-2546">National ID Number</span><span class="sxs-lookup"><span data-stu-id="888cb-2546">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="888cb-2547">意大利驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="888cb-2547">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-2548">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-2548">Format</span></span>

<span data-ttu-id="888cb-2549">10 个字母和数字的组合</span><span class="sxs-lookup"><span data-stu-id="888cb-2549">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-2550">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2550">Pattern</span></span>

- <span data-ttu-id="888cb-2551">10 个字母和数字的组合：</span><span class="sxs-lookup"><span data-stu-id="888cb-2551">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="888cb-2552">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="888cb-2552">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="888cb-2553">字母“A”或者“V”（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="888cb-2553">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="888cb-2554">七个字母（不区分大小写）、数字或下划线字符</span><span class="sxs-lookup"><span data-stu-id="888cb-2554">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="888cb-2555">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="888cb-2555">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-2556">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-2556">Checksum</span></span>

<span data-ttu-id="888cb-2557">否</span><span class="sxs-lookup"><span data-stu-id="888cb-2557">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-2558">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-2558">Definition</span></span>

<span data-ttu-id="888cb-2559">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2559">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2560">正则表达式 Regex_italy_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2560">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2561">找到 Keyword_italy_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2561">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-2562">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2562">Keywords</span></span>

#### <a name="keyworditalydriverslicensenumber"></a><span data-ttu-id="888cb-2563">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="888cb-2563">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="888cb-2564">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="888cb-2564">numero di patente di guida</span></span> 
- <span data-ttu-id="888cb-2565">patente di guida</span><span class="sxs-lookup"><span data-stu-id="888cb-2565">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="888cb-2566">日本银行帐号</span><span class="sxs-lookup"><span data-stu-id="888cb-2566">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-2567">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-2567">Format</span></span>

<span data-ttu-id="888cb-2568">七个或八个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2568">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-2569">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2569">Pattern</span></span>

<span data-ttu-id="888cb-2570">银行帐号：</span><span class="sxs-lookup"><span data-stu-id="888cb-2570">Bank account number:</span></span>
- <span data-ttu-id="888cb-2571">七个或八个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2571">Seven or eight digits</span></span>
- <span data-ttu-id="888cb-2572">银行帐户分支代码：</span><span class="sxs-lookup"><span data-stu-id="888cb-2572">Bank account branch code:</span></span>
- <span data-ttu-id="888cb-2573">四位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2573">Four digits</span></span> 
- <span data-ttu-id="888cb-2574">空格或破折号（可选）</span><span class="sxs-lookup"><span data-stu-id="888cb-2574">A space or dash (optional)</span></span> 
- <span data-ttu-id="888cb-2575">三位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2575">Three digits</span></span>

<span data-ttu-id="888cb-2576">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-2576">Checksum</span></span>

<span data-ttu-id="888cb-2577">否</span><span class="sxs-lookup"><span data-stu-id="888cb-2577">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-2578">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-2578">Definition</span></span>

<span data-ttu-id="888cb-2579">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2580">函数 Func_jp_bank_account 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2580">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2581">找到 Keyword_jp_bank_account 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2581">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="888cb-2582">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="888cb-2582">One of the following is true:</span></span>
- <span data-ttu-id="888cb-2583">函数 Func_jp_bank_account_branch_code 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2583">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2584">找到 Keyword_jp_bank_branch_code 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2584">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="888cb-2585">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2585">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2586">函数 Func_jp_bank_account 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2586">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2587">找到 Keyword_jp_bank_account 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2587">A keyword from Keyword_jp_bank_account is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-2588">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2588">Keywords</span></span>

#### <a name="keywordjpbankaccount"></a><span data-ttu-id="888cb-2589">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="888cb-2589">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="888cb-2590">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="888cb-2590">Checking Account Number</span></span> 
- <span data-ttu-id="888cb-2591">Checking Account</span><span class="sxs-lookup"><span data-stu-id="888cb-2591">Checking Account</span></span> 
- <span data-ttu-id="888cb-2592">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="888cb-2592">Checking Account #</span></span> 
- <span data-ttu-id="888cb-2593">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="888cb-2593">Checking Acct Number</span></span> 
- <span data-ttu-id="888cb-2594">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="888cb-2594">Checking Acct #</span></span> 
- <span data-ttu-id="888cb-2595">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="888cb-2595">Checking Acct No.</span></span> 
- <span data-ttu-id="888cb-2596">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="888cb-2596">Checking Account No.</span></span> 
- <span data-ttu-id="888cb-2597">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="888cb-2597">Bank Account Number</span></span> 
- <span data-ttu-id="888cb-2598">Bank Account</span><span class="sxs-lookup"><span data-stu-id="888cb-2598">Bank Account</span></span> 
- <span data-ttu-id="888cb-2599">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="888cb-2599">Bank Account #</span></span> 
- <span data-ttu-id="888cb-2600">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="888cb-2600">Bank Acct Number</span></span> 
- <span data-ttu-id="888cb-2601">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="888cb-2601">Bank Acct #</span></span> 
- <span data-ttu-id="888cb-2602">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="888cb-2602">Bank Acct No.</span></span> 
- <span data-ttu-id="888cb-2603">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="888cb-2603">Bank Account No.</span></span> 
- <span data-ttu-id="888cb-2604">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="888cb-2604">Savings Account Number</span></span> 
- <span data-ttu-id="888cb-2605">Savings Account</span><span class="sxs-lookup"><span data-stu-id="888cb-2605">Savings Account</span></span> 
- <span data-ttu-id="888cb-2606">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="888cb-2606">Savings Account #</span></span> 
- <span data-ttu-id="888cb-2607">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="888cb-2607">Savings Acct Number</span></span> 
- <span data-ttu-id="888cb-2608">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="888cb-2608">Savings Acct #</span></span> 
- <span data-ttu-id="888cb-2609">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="888cb-2609">Savings Acct No.</span></span> 
- <span data-ttu-id="888cb-2610">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="888cb-2610">Savings Account No.</span></span> 
- <span data-ttu-id="888cb-2611">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="888cb-2611">Debit Account Number</span></span> 
- <span data-ttu-id="888cb-2612">Debit Account</span><span class="sxs-lookup"><span data-stu-id="888cb-2612">Debit Account</span></span> 
- <span data-ttu-id="888cb-2613">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="888cb-2613">Debit Account #</span></span> 
- <span data-ttu-id="888cb-2614">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="888cb-2614">Debit Acct Number</span></span> 
- <span data-ttu-id="888cb-2615">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="888cb-2615">Debit Acct #</span></span> 
- <span data-ttu-id="888cb-2616">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="888cb-2616">Debit Acct No.</span></span> 
- <span data-ttu-id="888cb-2617">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="888cb-2617">Debit Account No.</span></span> 
- <span data-ttu-id="888cb-2618">口座番号を当座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="888cb-2618">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="888cb-2619">#アカウントの確認、勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="888cb-2619">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="888cb-2620">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="888cb-2620">＃勘定の確認</span></span> 
- <span data-ttu-id="888cb-2621">勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="888cb-2621">勘定番号の確認</span></span> 
- <span data-ttu-id="888cb-2622">口座番号の確認</span><span class="sxs-lookup"><span data-stu-id="888cb-2622">口座番号の確認</span></span> 
- <span data-ttu-id="888cb-2623">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="888cb-2623">銀行口座番号</span></span> 
- <span data-ttu-id="888cb-2624">銀行口座</span><span class="sxs-lookup"><span data-stu-id="888cb-2624">銀行口座</span></span> 
- <span data-ttu-id="888cb-2625">銀行口座 #</span><span class="sxs-lookup"><span data-stu-id="888cb-2625">銀行口座＃</span></span> 
- <span data-ttu-id="888cb-2626">銀行の勘定番号</span><span class="sxs-lookup"><span data-stu-id="888cb-2626">銀行の勘定番号</span></span> 
- <span data-ttu-id="888cb-2627">銀行のacct #</span><span class="sxs-lookup"><span data-stu-id="888cb-2627">銀行のacct＃</span></span> 
- <span data-ttu-id="888cb-2628">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="888cb-2628">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="888cb-2629">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="888cb-2629">銀行口座番号</span></span>
- <span data-ttu-id="888cb-2630">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="888cb-2630">普通預金口座番号</span></span> 
- <span data-ttu-id="888cb-2631">預金口座</span><span class="sxs-lookup"><span data-stu-id="888cb-2631">預金口座</span></span> 
- <span data-ttu-id="888cb-2632">貯蓄口座 #</span><span class="sxs-lookup"><span data-stu-id="888cb-2632">貯蓄口座＃</span></span> 
- <span data-ttu-id="888cb-2633">貯蓄勘定の数</span><span class="sxs-lookup"><span data-stu-id="888cb-2633">貯蓄勘定の数</span></span> 
- <span data-ttu-id="888cb-2634">貯蓄勘定 #</span><span class="sxs-lookup"><span data-stu-id="888cb-2634">貯蓄勘定＃</span></span> 
- <span data-ttu-id="888cb-2635">貯蓄勘定番号</span><span class="sxs-lookup"><span data-stu-id="888cb-2635">貯蓄勘定番号</span></span> 
- <span data-ttu-id="888cb-2636">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="888cb-2636">普通預金口座番号</span></span> 
- <span data-ttu-id="888cb-2637">引き落とし口座番号</span><span class="sxs-lookup"><span data-stu-id="888cb-2637">引き落とし口座番号</span></span> 
- <span data-ttu-id="888cb-2638">口座番号</span><span class="sxs-lookup"><span data-stu-id="888cb-2638">口座番号</span></span> 
- <span data-ttu-id="888cb-2639">口座番号 #</span><span class="sxs-lookup"><span data-stu-id="888cb-2639">口座番号＃</span></span> 
- <span data-ttu-id="888cb-2640">デビットのacct番号</span><span class="sxs-lookup"><span data-stu-id="888cb-2640">デビットのacct番号</span></span> 
- <span data-ttu-id="888cb-2641">デビット勘定 #</span><span class="sxs-lookup"><span data-stu-id="888cb-2641">デビット勘定＃</span></span> 
- <span data-ttu-id="888cb-2642">デビットACCTの番号</span><span class="sxs-lookup"><span data-stu-id="888cb-2642">デビットACCTの番号</span></span> 
- <span data-ttu-id="888cb-2643">デビット口座番号</span><span class="sxs-lookup"><span data-stu-id="888cb-2643">デビット口座番号</span></span> 

#### <a name="keywordjpbankbranchcode"></a><span data-ttu-id="888cb-2644">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="888cb-2644">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="888cb-2645">Otemachi</span><span class="sxs-lookup"><span data-stu-id="888cb-2645">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="888cb-2646">日本驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="888cb-2646">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-2647">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-2647">Format</span></span>

<span data-ttu-id="888cb-2648">12 个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2648">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-2649">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2649">Pattern</span></span>

<span data-ttu-id="888cb-2650">12 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2650">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-2651">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-2651">Checksum</span></span>

<span data-ttu-id="888cb-2652">否</span><span class="sxs-lookup"><span data-stu-id="888cb-2652">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-2653">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-2653">Definition</span></span>

<span data-ttu-id="888cb-2654">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2654">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2655">函数 Func_jp_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2655">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2656">找到 Keyword_jp_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2656">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-2657">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2657">Keywords</span></span>

#### <a name="keywordjpdriverslicensenumber"></a><span data-ttu-id="888cb-2658">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="888cb-2658">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="888cb-2659">通讯</span><span class="sxs-lookup"><span data-stu-id="888cb-2659">dl#</span></span> 
- <span data-ttu-id="888cb-2660">通讯</span><span class="sxs-lookup"><span data-stu-id="888cb-2660">DL＃</span></span> 
- <span data-ttu-id="888cb-2661">dls</span><span class="sxs-lookup"><span data-stu-id="888cb-2661">dls#</span></span> 
- <span data-ttu-id="888cb-2662">DLS</span><span class="sxs-lookup"><span data-stu-id="888cb-2662">DLS＃</span></span> 
- <span data-ttu-id="888cb-2663">driver license</span><span class="sxs-lookup"><span data-stu-id="888cb-2663">driver license</span></span> 
- <span data-ttu-id="888cb-2664">driver licenses</span><span class="sxs-lookup"><span data-stu-id="888cb-2664">driver licenses</span></span> 
- <span data-ttu-id="888cb-2665">drivers license</span><span class="sxs-lookup"><span data-stu-id="888cb-2665">drivers license</span></span> 
- <span data-ttu-id="888cb-2666">driver's license</span><span class="sxs-lookup"><span data-stu-id="888cb-2666">driver's license</span></span> 
- <span data-ttu-id="888cb-2667">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="888cb-2667">drivers licenses</span></span> 
- <span data-ttu-id="888cb-2668">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="888cb-2668">driver's licenses</span></span> 
- <span data-ttu-id="888cb-2669">driving licence</span><span class="sxs-lookup"><span data-stu-id="888cb-2669">driving licence</span></span> 
- <span data-ttu-id="888cb-2670">.lic</span><span class="sxs-lookup"><span data-stu-id="888cb-2670">lic#</span></span> 
- <span data-ttu-id="888cb-2671">.lic</span><span class="sxs-lookup"><span data-stu-id="888cb-2671">LIC＃</span></span> 
- <span data-ttu-id="888cb-2672">driver'lics</span><span class="sxs-lookup"><span data-stu-id="888cb-2672">lics#</span></span> 
- <span data-ttu-id="888cb-2673">state id</span><span class="sxs-lookup"><span data-stu-id="888cb-2673">state id</span></span> 
- <span data-ttu-id="888cb-2674">state identification</span><span class="sxs-lookup"><span data-stu-id="888cb-2674">state identification</span></span> 
- <span data-ttu-id="888cb-2675">state identification number</span><span class="sxs-lookup"><span data-stu-id="888cb-2675">state identification number</span></span> 
- <span data-ttu-id="888cb-2676">低所得国 #</span><span class="sxs-lookup"><span data-stu-id="888cb-2676">低所得国＃</span></span> 
- <span data-ttu-id="888cb-2677">免許証</span><span class="sxs-lookup"><span data-stu-id="888cb-2677">免許証</span></span> 
- <span data-ttu-id="888cb-2678">状態ID</span><span class="sxs-lookup"><span data-stu-id="888cb-2678">状態ID</span></span>
- <span data-ttu-id="888cb-2679">状態の識別</span><span class="sxs-lookup"><span data-stu-id="888cb-2679">状態の識別</span></span> 
- <span data-ttu-id="888cb-2680">状態の識別番号</span><span class="sxs-lookup"><span data-stu-id="888cb-2680">状態の識別番号</span></span> 
- <span data-ttu-id="888cb-2681">運転免許</span><span class="sxs-lookup"><span data-stu-id="888cb-2681">運転免許</span></span> 
- <span data-ttu-id="888cb-2682">運転免許証</span><span class="sxs-lookup"><span data-stu-id="888cb-2682">運転免許証</span></span> 
- <span data-ttu-id="888cb-2683">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="888cb-2683">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="888cb-2684">日本护照号码</span><span class="sxs-lookup"><span data-stu-id="888cb-2684">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-2685">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-2685">Format</span></span>

<span data-ttu-id="888cb-2686">两个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2686">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-2687">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2687">Pattern</span></span>

<span data-ttu-id="888cb-2688">两个字母（不区分大小写）后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2688">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-2689">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-2689">Checksum</span></span>

<span data-ttu-id="888cb-2690">否</span><span class="sxs-lookup"><span data-stu-id="888cb-2690">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-2691">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-2691">Definition</span></span>

<span data-ttu-id="888cb-2692">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2692">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2693">函数 Func_jp_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2693">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2694">找到 Keyword_jp_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2694">A keyword from Keyword_jp_passport is found.</span></span>

```
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-2695">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2695">Keywords</span></span>

#### <a name="keywordjppassport"></a><span data-ttu-id="888cb-2696">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="888cb-2696">Keyword_jp_passport</span></span>

- <span data-ttu-id="888cb-2697">パスポート</span><span class="sxs-lookup"><span data-stu-id="888cb-2697">パスポート</span></span> 
- <span data-ttu-id="888cb-2698">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="888cb-2698">パスポート番号</span></span> 
- <span data-ttu-id="888cb-2699">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="888cb-2699">パスポートのNum</span></span> 
- <span data-ttu-id="888cb-2700">パスポート #</span><span class="sxs-lookup"><span data-stu-id="888cb-2700">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="888cb-2701">日本居民登记号码</span><span class="sxs-lookup"><span data-stu-id="888cb-2701">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-2702">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-2702">Format</span></span>

<span data-ttu-id="888cb-2703">11 个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2703">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-2704">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2704">Pattern</span></span>

<span data-ttu-id="888cb-2705">11 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2705">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-2706">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-2706">Checksum</span></span>

<span data-ttu-id="888cb-2707">否</span><span class="sxs-lookup"><span data-stu-id="888cb-2707">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-2708">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-2708">Definition</span></span>

<span data-ttu-id="888cb-2709">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2709">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2710">函数 Func_jp_resident_registration_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2710">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2711">找到 Keyword_jp_resident_registration_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2711">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-2712">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2712">Keywords</span></span>

#### <a name="keywordjpresidentregistrationnumber"></a><span data-ttu-id="888cb-2713">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="888cb-2713">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="888cb-2714">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="888cb-2714">Resident Registration Number</span></span>
- <span data-ttu-id="888cb-2715">Resident Register Number</span><span class="sxs-lookup"><span data-stu-id="888cb-2715">Resident Register Number</span></span> 
- <span data-ttu-id="888cb-2716">Residents Basic Registry Number</span><span class="sxs-lookup"><span data-stu-id="888cb-2716">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="888cb-2717">Resident Registration No.</span><span class="sxs-lookup"><span data-stu-id="888cb-2717">Resident Registration No.</span></span> 
- <span data-ttu-id="888cb-2718">Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="888cb-2718">Resident Register No.</span></span> 
- <span data-ttu-id="888cb-2719">Residents Basic Registry No.</span><span class="sxs-lookup"><span data-stu-id="888cb-2719">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="888cb-2720">Basic Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="888cb-2720">Basic Resident Register No.</span></span> 
- <span data-ttu-id="888cb-2721">住民登録番号、登録番号をレジデント</span><span class="sxs-lookup"><span data-stu-id="888cb-2721">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="888cb-2722">住民基本登録番号、登録番号</span><span class="sxs-lookup"><span data-stu-id="888cb-2722">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="888cb-2723">住民基本レジストリ番号を常駐</span><span class="sxs-lookup"><span data-stu-id="888cb-2723">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="888cb-2724">登録番号を常駐住民基本台帳登録番号</span><span class="sxs-lookup"><span data-stu-id="888cb-2724">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="888cb-2725">日本社会保险号码 (SIN)</span><span class="sxs-lookup"><span data-stu-id="888cb-2725">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="888cb-2726">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-2726">Format</span></span>

<span data-ttu-id="888cb-2727">7-12 个数字 </span><span class="sxs-lookup"><span data-stu-id="888cb-2727">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-2728">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2728">Pattern</span></span>

<span data-ttu-id="888cb-2729">7-12 位数字：</span><span class="sxs-lookup"><span data-stu-id="888cb-2729">7-12 digits:</span></span>
- <span data-ttu-id="888cb-2730">四位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2730">Four digits</span></span> 
- <span data-ttu-id="888cb-2731">一个连字符（可选）</span><span class="sxs-lookup"><span data-stu-id="888cb-2731">A hyphen (optional)</span></span> 
- <span data-ttu-id="888cb-2732">六位数字或</span><span class="sxs-lookup"><span data-stu-id="888cb-2732">Six digits OR</span></span>
- <span data-ttu-id="888cb-2733">7-12 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2733">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-2734">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-2734">Checksum</span></span>

<span data-ttu-id="888cb-2735">否</span><span class="sxs-lookup"><span data-stu-id="888cb-2735">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-2736">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-2736">Definition</span></span>

<span data-ttu-id="888cb-2737">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2737">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2738">函数 Func_jp_sin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2738">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2739">找到 Keyword_jp_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2739">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="888cb-2740">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2740">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2741">函数 Func_jp_sin_pre_1997 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2741">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2742">找到 Keyword_jp_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2742">A keyword from Keyword_jp_sin is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-2743">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2743">Keywords</span></span>

#### <a name="keywordjpsin"></a><span data-ttu-id="888cb-2744">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="888cb-2744">Keyword_jp_sin</span></span>

- <span data-ttu-id="888cb-2745">Social Insurance No.</span><span class="sxs-lookup"><span data-stu-id="888cb-2745">Social Insurance No.</span></span> 
- <span data-ttu-id="888cb-2746">Social Insurance Num</span><span class="sxs-lookup"><span data-stu-id="888cb-2746">Social Insurance Num</span></span> 
- <span data-ttu-id="888cb-2747">Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="888cb-2747">Social Insurance Number</span></span> 
- <span data-ttu-id="888cb-2748">社会保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="888cb-2748">社会保険のテンキー</span></span> 
- <span data-ttu-id="888cb-2749">社会保険番号</span><span class="sxs-lookup"><span data-stu-id="888cb-2749">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="888cb-2750">日本住宅电话卡号</span><span class="sxs-lookup"><span data-stu-id="888cb-2750">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-2751">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-2751">Format</span></span>

<span data-ttu-id="888cb-2752">12个字母和数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2752">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-2753">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2753">Pattern</span></span>

<span data-ttu-id="888cb-2754">12个字母和数字:</span><span class="sxs-lookup"><span data-stu-id="888cb-2754">12 letters and digits:</span></span>
- <span data-ttu-id="888cb-2755">两个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="888cb-2755">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="888cb-2756">八个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2756">Eight digits</span></span> 
- <span data-ttu-id="888cb-2757">两个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="888cb-2757">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-2758">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-2758">Checksum</span></span>

<span data-ttu-id="888cb-2759">否</span><span class="sxs-lookup"><span data-stu-id="888cb-2759">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-2760">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-2760">Definition</span></span>

<span data-ttu-id="888cb-2761">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2761">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2762">正则表达式 Regex_jp_residence_card_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2762">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2763">找到 Keyword_jp_residence_card_number 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2763">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-2764">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2764">Keywords</span></span>

#### <a name="keywordjpresidencecardnumber"></a><span data-ttu-id="888cb-2765">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="888cb-2765">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="888cb-2766">住宅电话卡号</span><span class="sxs-lookup"><span data-stu-id="888cb-2766">Residence card number</span></span>
- <span data-ttu-id="888cb-2767">住宅卡编号</span><span class="sxs-lookup"><span data-stu-id="888cb-2767">Residence card no</span></span>
- <span data-ttu-id="888cb-2768">住宅卡片 #</span><span class="sxs-lookup"><span data-stu-id="888cb-2768">Residence card #</span></span>
- <span data-ttu-id="888cb-2769">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="888cb-2769">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="888cb-2770">马拉西亚身份证号码</span><span class="sxs-lookup"><span data-stu-id="888cb-2770">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-2771">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-2771">Format</span></span>

<span data-ttu-id="888cb-2772">12 个数字（包含可选连字符）</span><span class="sxs-lookup"><span data-stu-id="888cb-2772">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-2773">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2773">Pattern</span></span>

<span data-ttu-id="888cb-2774">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="888cb-2774">12 digits:</span></span>
- <span data-ttu-id="888cb-2775">六个数字，采用  YYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="888cb-2775">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="888cb-2776">一个短划线（可选） </span><span class="sxs-lookup"><span data-stu-id="888cb-2776">A dash (optional)</span></span> 
- <span data-ttu-id="888cb-2777">两个字母的出生地代码 </span><span class="sxs-lookup"><span data-stu-id="888cb-2777">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="888cb-2778">一个短划线（可选） </span><span class="sxs-lookup"><span data-stu-id="888cb-2778">A dash (optional)</span></span> 
- <span data-ttu-id="888cb-2779">三个随机数字 </span><span class="sxs-lookup"><span data-stu-id="888cb-2779">Three random digits</span></span> 
- <span data-ttu-id="888cb-2780">一位性别代码</span><span class="sxs-lookup"><span data-stu-id="888cb-2780">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-2781">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-2781">Checksum</span></span>

<span data-ttu-id="888cb-2782">否</span><span class="sxs-lookup"><span data-stu-id="888cb-2782">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-2783">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-2783">Definition</span></span>

<span data-ttu-id="888cb-2784">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2784">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2785">正则表达式 Regex_malaysia_id_card_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2785">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2786">找到 Keyword_malaysia_id_card_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2786">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-2787">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2787">Keywords</span></span>
   
#### <a name="keywordmalaysiaidcardnumber"></a><span data-ttu-id="888cb-2788">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="888cb-2788">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="888cb-2789">数字应用程序卡</span><span class="sxs-lookup"><span data-stu-id="888cb-2789">digital application card</span></span>
- <span data-ttu-id="888cb-2790">i/c</span><span class="sxs-lookup"><span data-stu-id="888cb-2790">i/c</span></span>
- <span data-ttu-id="888cb-2791">i/c 否</span><span class="sxs-lookup"><span data-stu-id="888cb-2791">i/c no</span></span>
- <span data-ttu-id="888cb-2792">ic</span><span class="sxs-lookup"><span data-stu-id="888cb-2792">ic</span></span>
- <span data-ttu-id="888cb-2793">内部公司编号</span><span class="sxs-lookup"><span data-stu-id="888cb-2793">ic no</span></span>
- <span data-ttu-id="888cb-2794">id card</span><span class="sxs-lookup"><span data-stu-id="888cb-2794">id card</span></span>
- <span data-ttu-id="888cb-2795">标识卡</span><span class="sxs-lookup"><span data-stu-id="888cb-2795">identification Card</span></span>
- <span data-ttu-id="888cb-2796">identity card</span><span class="sxs-lookup"><span data-stu-id="888cb-2796">identity card</span></span>
- <span data-ttu-id="888cb-2797">k/p</span><span class="sxs-lookup"><span data-stu-id="888cb-2797">k/p</span></span>
- <span data-ttu-id="888cb-2798">k/p no</span><span class="sxs-lookup"><span data-stu-id="888cb-2798">k/p no</span></span>
- <span data-ttu-id="888cb-2799">kad akuan diri</span><span class="sxs-lookup"><span data-stu-id="888cb-2799">kad akuan diri</span></span>
- <span data-ttu-id="888cb-2800">kad aplikasi 数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2800">kad aplikasi digital</span></span>
- <span data-ttu-id="888cb-2801">kad pengenalan 马来西亚</span><span class="sxs-lookup"><span data-stu-id="888cb-2801">kad pengenalan malaysia</span></span>
- <span data-ttu-id="888cb-2802">kp</span><span class="sxs-lookup"><span data-stu-id="888cb-2802">kp</span></span>
- <span data-ttu-id="888cb-2803">kp no</span><span class="sxs-lookup"><span data-stu-id="888cb-2803">kp no</span></span>
- <span data-ttu-id="888cb-2804">mykad</span><span class="sxs-lookup"><span data-stu-id="888cb-2804">mykad</span></span>
- <span data-ttu-id="888cb-2805">mykas</span><span class="sxs-lookup"><span data-stu-id="888cb-2805">mykas</span></span>
- <span data-ttu-id="888cb-2806">mykid</span><span class="sxs-lookup"><span data-stu-id="888cb-2806">mykid</span></span>
- <span data-ttu-id="888cb-2807">mypr</span><span class="sxs-lookup"><span data-stu-id="888cb-2807">mypr</span></span>
- <span data-ttu-id="888cb-2808">mytentera</span><span class="sxs-lookup"><span data-stu-id="888cb-2808">mytentera</span></span>
- <span data-ttu-id="888cb-2809">马来西亚身份卡片</span><span class="sxs-lookup"><span data-stu-id="888cb-2809">malaysia identity card</span></span>
- <span data-ttu-id="888cb-2810">马来西亚身份卡片</span><span class="sxs-lookup"><span data-stu-id="888cb-2810">malaysian identity card</span></span>
- <span data-ttu-id="888cb-2811">nric</span><span class="sxs-lookup"><span data-stu-id="888cb-2811">nric</span></span>
- <span data-ttu-id="888cb-2812">个人标识卡</span><span class="sxs-lookup"><span data-stu-id="888cb-2812">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="888cb-2813">荷兰公民服务 (BSN) 号码</span><span class="sxs-lookup"><span data-stu-id="888cb-2813">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-2814">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-2814">Format</span></span>

<span data-ttu-id="888cb-2815">8-9 个数字（包含可选空格）</span><span class="sxs-lookup"><span data-stu-id="888cb-2815">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-2816">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2816">Pattern</span></span>

<span data-ttu-id="888cb-2817">8-9 个数字：</span><span class="sxs-lookup"><span data-stu-id="888cb-2817">8-9 digits:</span></span>
- <span data-ttu-id="888cb-2818">三个数字 </span><span class="sxs-lookup"><span data-stu-id="888cb-2818">Three digits</span></span> 
- <span data-ttu-id="888cb-2819">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="888cb-2819">A space (optional)</span></span> 
- <span data-ttu-id="888cb-2820">三个数字 </span><span class="sxs-lookup"><span data-stu-id="888cb-2820">Three digits</span></span> 
- <span data-ttu-id="888cb-2821">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="888cb-2821">A space (optional)</span></span> 
- <span data-ttu-id="888cb-2822">2-3 个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2822">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-2823">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-2823">Checksum</span></span>

<span data-ttu-id="888cb-2824">是</span><span class="sxs-lookup"><span data-stu-id="888cb-2824">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-2825">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-2825">Definition</span></span>

<span data-ttu-id="888cb-2826">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2826">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2827">函数 Func_netherlands_bsn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2827">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2828">找到 Keyword_netherlands_bsn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2828">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="888cb-2829">函数 Func_eu_date2 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="888cb-2829">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="888cb-2830">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-2830">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-2831">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2831">Keywords</span></span>

#### <a name="keywordnetherlandsbsn"></a><span data-ttu-id="888cb-2832">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="888cb-2832">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="888cb-2833">Citizen service number</span><span class="sxs-lookup"><span data-stu-id="888cb-2833">Citizen service number</span></span> 
- <span data-ttu-id="888cb-2834">BSN</span><span class="sxs-lookup"><span data-stu-id="888cb-2834">BSN</span></span> 
- <span data-ttu-id="888cb-2835">Burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="888cb-2835">Burgerservicenummer</span></span> 
- <span data-ttu-id="888cb-2836">Sofinummer</span><span class="sxs-lookup"><span data-stu-id="888cb-2836">Sofinummer</span></span> 
- <span data-ttu-id="888cb-2837">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="888cb-2837">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="888cb-2838">Persoonsnummer</span><span class="sxs-lookup"><span data-stu-id="888cb-2838">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="888cb-2839">新西兰卫生部号码</span><span class="sxs-lookup"><span data-stu-id="888cb-2839">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-2840">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-2840">Format</span></span>

<span data-ttu-id="888cb-2841">三个字母、一个空格（可选）以及四个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2841">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-2842">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2842">Pattern</span></span>

<span data-ttu-id="888cb-2843">三个字母 (不区分大小写) 一个空格 (可选) 四个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2843">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-2844">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-2844">Checksum</span></span>

<span data-ttu-id="888cb-2845">是</span><span class="sxs-lookup"><span data-stu-id="888cb-2845">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-2846">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-2846">Definition</span></span>

<span data-ttu-id="888cb-2847">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2848">函数 Func_new_zealand_ministry_of_health_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2848">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2849">找到 Keyword_nz_terms 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2849">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="888cb-2850">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-2850">The checksum passes.</span></span>

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

<span data-ttu-id="888cb-2851">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2851">Keywords</span></span>

<span data-ttu-id="888cb-2852">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="888cb-2852">Keyword_nz_terms</span></span>

- <span data-ttu-id="888cb-2853">NHI</span><span class="sxs-lookup"><span data-stu-id="888cb-2853">NHI</span></span> 
- <span data-ttu-id="888cb-2854">New Zealand</span><span class="sxs-lookup"><span data-stu-id="888cb-2854">New Zealand</span></span> 
- <span data-ttu-id="888cb-2855">运行状况</span><span class="sxs-lookup"><span data-stu-id="888cb-2855">Health</span></span> 
- <span data-ttu-id="888cb-2856">治疗</span><span class="sxs-lookup"><span data-stu-id="888cb-2856">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="888cb-2857">挪威身份证号</span><span class="sxs-lookup"><span data-stu-id="888cb-2857">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-2858">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-2858">Format</span></span>

<span data-ttu-id="888cb-2859">11 个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2859">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-2860">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2860">Pattern</span></span>

<span data-ttu-id="888cb-2861">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="888cb-2861">11 digits:</span></span>
- <span data-ttu-id="888cb-2862">六个数字，采用  DDMMYY 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="888cb-2862">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="888cb-2863">三位个人号码 </span><span class="sxs-lookup"><span data-stu-id="888cb-2863">Three-digit individual number</span></span> 
- <span data-ttu-id="888cb-2864">两个校验位</span><span class="sxs-lookup"><span data-stu-id="888cb-2864">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-2865">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-2865">Checksum</span></span>

<span data-ttu-id="888cb-2866">是</span><span class="sxs-lookup"><span data-stu-id="888cb-2866">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-2867">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-2867">Definition</span></span>

<span data-ttu-id="888cb-2868">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2868">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2869">函数 Func_norway_id_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2869">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2870">找到 Keyword_norway_id_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2870">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="888cb-2871">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-2871">The checksum passes.</span></span>
- <span data-ttu-id="888cb-2872">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2872">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2873">函数 Func_norway_id_numbe 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2873">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2874">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-2874">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-2875">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2875">Keywords</span></span>

#### <a name="keywordnorwayidnumber"></a><span data-ttu-id="888cb-2876">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="888cb-2876">Keyword_norway_id_number</span></span>

- <span data-ttu-id="888cb-2877">Personal identification number</span><span class="sxs-lookup"><span data-stu-id="888cb-2877">Personal identification number</span></span>
- <span data-ttu-id="888cb-2878">Norwegian ID Number</span><span class="sxs-lookup"><span data-stu-id="888cb-2878">Norwegian ID Number</span></span>
- <span data-ttu-id="888cb-2879">ID Number</span><span class="sxs-lookup"><span data-stu-id="888cb-2879">ID Number</span></span>
- <span data-ttu-id="888cb-2880">id</span><span class="sxs-lookup"><span data-stu-id="888cb-2880">Identification</span></span>
- <span data-ttu-id="888cb-2881">Personnummer</span><span class="sxs-lookup"><span data-stu-id="888cb-2881">Personnummer</span></span>
- <span data-ttu-id="888cb-2882">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="888cb-2882">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="888cb-2883">菲律宾统一多用途身份证号码</span><span class="sxs-lookup"><span data-stu-id="888cb-2883">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-2884">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-2884">Format</span></span>

<span data-ttu-id="888cb-2885">12 个数字，通过连字符分隔 </span><span class="sxs-lookup"><span data-stu-id="888cb-2885">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-2886">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2886">Pattern</span></span>

<span data-ttu-id="888cb-2887">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="888cb-2887">12 digits:</span></span>
- <span data-ttu-id="888cb-2888">四个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2888">Four digits</span></span> 
- <span data-ttu-id="888cb-2889">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="888cb-2889">A hyphen</span></span> 
- <span data-ttu-id="888cb-2890">七个数字 </span><span class="sxs-lookup"><span data-stu-id="888cb-2890">Seven digits</span></span> 
- <span data-ttu-id="888cb-2891">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="888cb-2891">A hyphen</span></span> 
- <span data-ttu-id="888cb-2892">一个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2892">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-2893">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-2893">Checksum</span></span>

<span data-ttu-id="888cb-2894">否</span><span class="sxs-lookup"><span data-stu-id="888cb-2894">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-2895">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-2895">Definition</span></span>

<span data-ttu-id="888cb-2896">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2896">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2897">正则表达式 Regex_philippines_unified_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2897">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2898">找到 Keyword_philippines_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2898">A keyword from Keyword_philippines_id is found.</span></span>

```
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-2899">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2899">Keywords</span></span>
   
#### <a name="keywordphilippinesid"></a><span data-ttu-id="888cb-2900">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="888cb-2900">Keyword_philippines_id</span></span>

- <span data-ttu-id="888cb-2901">Unified Multi-Purpose ID</span><span class="sxs-lookup"><span data-stu-id="888cb-2901">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="888cb-2902">UMID</span><span class="sxs-lookup"><span data-stu-id="888cb-2902">UMID</span></span> 
- <span data-ttu-id="888cb-2903">Identity Card</span><span class="sxs-lookup"><span data-stu-id="888cb-2903">Identity Card</span></span> 
- <span data-ttu-id="888cb-2904">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="888cb-2904">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="888cb-2905">波兰身份证</span><span class="sxs-lookup"><span data-stu-id="888cb-2905">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="888cb-2906">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-2906">Format</span></span>

<span data-ttu-id="888cb-2907">三个字母和六个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2907">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-2908">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2908">Pattern</span></span>

<span data-ttu-id="888cb-2909">三个字母（不区分大小写）后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2909">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-2910">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-2910">Checksum</span></span>

<span data-ttu-id="888cb-2911">是</span><span class="sxs-lookup"><span data-stu-id="888cb-2911">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-2912">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-2912">Definition</span></span>

<span data-ttu-id="888cb-2913">DLP 策略 75% 确信在300个字符的邻近度内检测到此类型的敏感信息: 函数 Func_polish_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2913">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="888cb-2914">找到 Keyword_polish_national_id_passport_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2914">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="888cb-2915">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-2915">The checksum passes.</span></span>

```
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-2916">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2916">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="888cb-2917">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="888cb-2917">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="888cb-2918">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="888cb-2918">Dowód osobisty</span></span>
- <span data-ttu-id="888cb-2919">器 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="888cb-2919">Numer dowodu osobistego</span></span>
- <span data-ttu-id="888cb-2920">Nazwa i 器 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="888cb-2920">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="888cb-2921">Nazwa i nr dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="888cb-2921">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="888cb-2922">Nazwa i nr dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="888cb-2922">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="888cb-2923">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="888cb-2923">Dowód Tożsamości</span></span>
- <span data-ttu-id="888cb-2924">dow.</span><span class="sxs-lookup"><span data-stu-id="888cb-2924">dow.</span></span> <span data-ttu-id="888cb-2925">os.</span><span class="sxs-lookup"><span data-stu-id="888cb-2925">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="888cb-2926">波兰国家/地区 ID (PESEL)</span><span class="sxs-lookup"><span data-stu-id="888cb-2926">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="888cb-2927">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-2927">Format</span></span>

<span data-ttu-id="888cb-2928">11 个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2928">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-2929">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2929">Pattern</span></span>

<span data-ttu-id="888cb-2930">11 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2930">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-2931">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-2931">Checksum</span></span>

<span data-ttu-id="888cb-2932">是</span><span class="sxs-lookup"><span data-stu-id="888cb-2932">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-2933">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-2933">Definition</span></span>

<span data-ttu-id="888cb-2934">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2934">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2935">函数 Func_pesel_identification_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2935">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2936">找到 Keyword_pesel_identification_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2936">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="888cb-2937">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-2937">The checksum passes.</span></span>

```
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-2938">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2938">Keywords</span></span>

#### <a name="keywordpeselidentificationnumber"></a><span data-ttu-id="888cb-2939">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="888cb-2939">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="888cb-2940">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="888cb-2940">Nr PESEL</span></span>
- <span data-ttu-id="888cb-2941">PESEL</span><span class="sxs-lookup"><span data-stu-id="888cb-2941">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="888cb-2942">波兰护照</span><span class="sxs-lookup"><span data-stu-id="888cb-2942">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="888cb-2943">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-2943">Format</span></span>

<span data-ttu-id="888cb-2944">两个字母和七个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2944">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-2945">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2945">Pattern</span></span>

<span data-ttu-id="888cb-2946">两个字母（不区分大小写）后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2946">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-2947">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-2947">Checksum</span></span>

<span data-ttu-id="888cb-2948">是</span><span class="sxs-lookup"><span data-stu-id="888cb-2948">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-2949">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-2949">Definition</span></span>

<span data-ttu-id="888cb-2950">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2950">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2951">函数 Func_polish_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2951">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2952">找到 Keyword_polish_national_id_passport_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2952">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="888cb-2953">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-2953">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-2954">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2954">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="888cb-2955">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="888cb-2955">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="888cb-2956">器 paszportu</span><span class="sxs-lookup"><span data-stu-id="888cb-2956">Numer paszportu</span></span>
- <span data-ttu-id="888cb-2957">führerschein-nr.</span><span class="sxs-lookup"><span data-stu-id="888cb-2957">Nr.</span></span> <span data-ttu-id="888cb-2958">Paszportu</span><span class="sxs-lookup"><span data-stu-id="888cb-2958">Paszportu</span></span>
- <span data-ttu-id="888cb-2959">Paszport</span><span class="sxs-lookup"><span data-stu-id="888cb-2959">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="888cb-2960">葡萄牙公民身份证号</span><span class="sxs-lookup"><span data-stu-id="888cb-2960">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-2961">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-2961">Format</span></span>

<span data-ttu-id="888cb-2962">八个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2962">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-2963">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2963">Pattern</span></span>

<span data-ttu-id="888cb-2964">八个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2964">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-2965">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-2965">Checksum</span></span>

<span data-ttu-id="888cb-2966">否</span><span class="sxs-lookup"><span data-stu-id="888cb-2966">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-2967">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-2967">Definition</span></span>

<span data-ttu-id="888cb-2968">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2969">正则表达式 Regex_portugal_citizen_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2969">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2970">找到 Keyword_portugal_citizen_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2970">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-2971">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2971">Keywords</span></span>

#### <a name="keywordportugalcitizencard"></a><span data-ttu-id="888cb-2972">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="888cb-2972">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="888cb-2973">Citizen Card</span><span class="sxs-lookup"><span data-stu-id="888cb-2973">Citizen Card</span></span>
- <span data-ttu-id="888cb-2974">National ID Card</span><span class="sxs-lookup"><span data-stu-id="888cb-2974">National ID Card</span></span>
- <span data-ttu-id="888cb-2975">CC</span><span class="sxs-lookup"><span data-stu-id="888cb-2975">CC</span></span>
- <span data-ttu-id="888cb-2976">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="888cb-2976">Cartão de Cidadão</span></span>
- <span data-ttu-id="888cb-2977">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="888cb-2977">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="888cb-2978">沙特阿拉伯国家 ID</span><span class="sxs-lookup"><span data-stu-id="888cb-2978">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="888cb-2979">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-2979">Format</span></span>

<span data-ttu-id="888cb-2980">10 个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2980">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-2981">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2981">Pattern</span></span>

<span data-ttu-id="888cb-2982">10 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2982">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-2983">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-2983">Checksum</span></span>

<span data-ttu-id="888cb-2984">否</span><span class="sxs-lookup"><span data-stu-id="888cb-2984">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-2985">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-2985">Definition</span></span>

<span data-ttu-id="888cb-2986">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-2986">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-2987">正则表达式 Regex_saudi_arabia_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-2987">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-2988">找到 Keyword_saudi_arabia_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-2988">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-2989">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-2989">Keywords</span></span>

#### <a name="keywordsaudiarabianationalid"></a><span data-ttu-id="888cb-2990">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="888cb-2990">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="888cb-2991">Identification Card</span><span class="sxs-lookup"><span data-stu-id="888cb-2991">Identification Card</span></span> 
- <span data-ttu-id="888cb-2992">I card number</span><span class="sxs-lookup"><span data-stu-id="888cb-2992">I card number</span></span> 
- <span data-ttu-id="888cb-2993">ID number</span><span class="sxs-lookup"><span data-stu-id="888cb-2993">ID number</span></span> 
- <span data-ttu-id="888cb-2994">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="888cb-2994">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="888cb-2995">新加坡国家登记身份证 (NRIC) 号</span><span class="sxs-lookup"><span data-stu-id="888cb-2995">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-2996">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-2996">Format</span></span>

<span data-ttu-id="888cb-2997">九个字母和数字</span><span class="sxs-lookup"><span data-stu-id="888cb-2997">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-2998">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-2998">Pattern</span></span>

- <span data-ttu-id="888cb-2999">九个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="888cb-2999">Nine letters and digits:</span></span>
- <span data-ttu-id="888cb-3000">字母“F”、“G”、“S”或“T”（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="888cb-3000">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="888cb-3001">七个数字 </span><span class="sxs-lookup"><span data-stu-id="888cb-3001">Seven digits</span></span> 
- <span data-ttu-id="888cb-3002">一个字母校验位</span><span class="sxs-lookup"><span data-stu-id="888cb-3002">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-3003">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-3003">Checksum</span></span>

<span data-ttu-id="888cb-3004">是</span><span class="sxs-lookup"><span data-stu-id="888cb-3004">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-3005">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-3005">Definition</span></span>

<span data-ttu-id="888cb-3006">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-3006">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-3007">正则表达式 Regex_singapore_nric 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3007">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-3008">找到 Keyword_singapore_nric 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3008">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="888cb-3009">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-3009">The checksum passes.</span></span>

<span data-ttu-id="888cb-3010">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-3010">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-3011">正则表达式 Regex_singapore_nric 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3011">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-3012">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-3012">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-3013">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-3013">Keywords</span></span>
   
#### <a name="keywordsingaporenric"></a><span data-ttu-id="888cb-3014">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="888cb-3014">Keyword_singapore_nric</span></span>

- <span data-ttu-id="888cb-3015">National Registration Identity Card</span><span class="sxs-lookup"><span data-stu-id="888cb-3015">National Registration Identity Card</span></span> 
- <span data-ttu-id="888cb-3016">Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="888cb-3016">Identity Card Number</span></span> 
- <span data-ttu-id="888cb-3017">NRIC</span><span class="sxs-lookup"><span data-stu-id="888cb-3017">NRIC</span></span> 
- <span data-ttu-id="888cb-3018">IC</span><span class="sxs-lookup"><span data-stu-id="888cb-3018">IC</span></span> 
- <span data-ttu-id="888cb-3019">Foreign Identification Number</span><span class="sxs-lookup"><span data-stu-id="888cb-3019">Foreign Identification Number</span></span> 
- <span data-ttu-id="888cb-3020">FIN</span><span class="sxs-lookup"><span data-stu-id="888cb-3020">FIN</span></span> 
- <span data-ttu-id="888cb-3021">身份证</span><span class="sxs-lookup"><span data-stu-id="888cb-3021">身份证</span></span> 
- <span data-ttu-id="888cb-3022">證</span><span class="sxs-lookup"><span data-stu-id="888cb-3022">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="888cb-3023">南非身份证号</span><span class="sxs-lookup"><span data-stu-id="888cb-3023">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-3024">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-3024">Format</span></span>

<span data-ttu-id="888cb-3025">13 个数字（可能包含空格）</span><span class="sxs-lookup"><span data-stu-id="888cb-3025">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-3026">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-3026">Pattern</span></span>

<span data-ttu-id="888cb-3027">13 个数字：</span><span class="sxs-lookup"><span data-stu-id="888cb-3027">13 digits:</span></span>
- <span data-ttu-id="888cb-3028">六个数字，采用  YYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="888cb-3028">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="888cb-3029">四个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3029">Four digits</span></span> 
- <span data-ttu-id="888cb-3030">一位公民指示码 </span><span class="sxs-lookup"><span data-stu-id="888cb-3030">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="888cb-3031">数字“8”或“9” </span><span class="sxs-lookup"><span data-stu-id="888cb-3031">The digit "8" or "9"</span></span> 
- <span data-ttu-id="888cb-3032">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="888cb-3032">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-3033">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-3033">Checksum</span></span>

<span data-ttu-id="888cb-3034">是</span><span class="sxs-lookup"><span data-stu-id="888cb-3034">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-3035">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-3035">Definition</span></span>

<span data-ttu-id="888cb-3036">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-3036">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-3037">函数 Func_south_africa_identification_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3037">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-3038">找到 Keyword_south_africa_identification_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3038">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="888cb-3039">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-3039">The checksum passes.</span></span>

```
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-3040">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-3040">Keywords</span></span>
   
#### <a name="keywordsouthafricaidentificationnumber"></a><span data-ttu-id="888cb-3041">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="888cb-3041">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="888cb-3042">Identity card</span><span class="sxs-lookup"><span data-stu-id="888cb-3042">Identity card</span></span>
- <span data-ttu-id="888cb-3043">ID</span><span class="sxs-lookup"><span data-stu-id="888cb-3043">ID</span></span>
- <span data-ttu-id="888cb-3044">id</span><span class="sxs-lookup"><span data-stu-id="888cb-3044">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="888cb-3045">韩国居民注册号码</span><span class="sxs-lookup"><span data-stu-id="888cb-3045">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-3046">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-3046">Format</span></span>

<span data-ttu-id="888cb-3047">13 个数字（包含连字符）</span><span class="sxs-lookup"><span data-stu-id="888cb-3047">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-3048">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-3048">Pattern</span></span>

<span data-ttu-id="888cb-3049">13 个数字：</span><span class="sxs-lookup"><span data-stu-id="888cb-3049">13 digits:</span></span>
- <span data-ttu-id="888cb-3050">六个数字，采用  YYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="888cb-3050">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="888cb-3051">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="888cb-3051">A hyphen</span></span> 
- <span data-ttu-id="888cb-3052">一个数字，由世纪和性别 </span><span class="sxs-lookup"><span data-stu-id="888cb-3052">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="888cb-3053">四位数字的出生地区代码 </span><span class="sxs-lookup"><span data-stu-id="888cb-3053">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="888cb-3054">一个数字，用于区分前面数字均相同的人 </span><span class="sxs-lookup"><span data-stu-id="888cb-3054">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="888cb-3055">一个校验位。</span><span class="sxs-lookup"><span data-stu-id="888cb-3055">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-3056">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-3056">Checksum</span></span>

<span data-ttu-id="888cb-3057">是</span><span class="sxs-lookup"><span data-stu-id="888cb-3057">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-3058">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-3058">Definition</span></span>

<span data-ttu-id="888cb-3059">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-3059">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-3060">函数 Func_south_korea_resident_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3060">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-3061">找到 Keyword_south_korea_resident_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3061">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="888cb-3062">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-3062">The checksum passes.</span></span>

<span data-ttu-id="888cb-3063">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-3063">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-3064">函数 Func_south_korea_resident_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3064">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-3065">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-3065">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-3066">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-3066">Keywords</span></span>
   
#### <a name="keywordsouthkorearesidentnumber"></a><span data-ttu-id="888cb-3067">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="888cb-3067">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="888cb-3068">National ID card</span><span class="sxs-lookup"><span data-stu-id="888cb-3068">National ID card</span></span> 
- <span data-ttu-id="888cb-3069">Citizen's Registration Number</span><span class="sxs-lookup"><span data-stu-id="888cb-3069">Citizen's Registration Number</span></span> 
- <span data-ttu-id="888cb-3070">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="888cb-3070">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="888cb-3071">RRN</span><span class="sxs-lookup"><span data-stu-id="888cb-3071">RRN</span></span> 
- <span data-ttu-id="888cb-3072">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="888cb-3072">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="888cb-3073">西班牙社会保险号码 (SSN)</span><span class="sxs-lookup"><span data-stu-id="888cb-3073">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="888cb-3074">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-3074">Format</span></span>

<span data-ttu-id="888cb-3075">11-12 个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3075">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-3076">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-3076">Pattern</span></span>

<span data-ttu-id="888cb-3077">11-12 位数:</span><span class="sxs-lookup"><span data-stu-id="888cb-3077">11-12 digits:</span></span>
- <span data-ttu-id="888cb-3078">两位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3078">Two digits</span></span> 
- <span data-ttu-id="888cb-3079">正斜杠（可选）</span><span class="sxs-lookup"><span data-stu-id="888cb-3079">A forward slash (optional)</span></span> 
- <span data-ttu-id="888cb-3080">7-8 位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3080">7-8 digits</span></span> 
- <span data-ttu-id="888cb-3081">正斜杠（可选）</span><span class="sxs-lookup"><span data-stu-id="888cb-3081">A forward slash (optional)</span></span> 
- <span data-ttu-id="888cb-3082">两位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3082">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-3083">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-3083">Checksum</span></span>

<span data-ttu-id="888cb-3084">是</span><span class="sxs-lookup"><span data-stu-id="888cb-3084">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-3085">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-3085">Definition</span></span>

<span data-ttu-id="888cb-3086">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-3086">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-3087">函数 Func_spanish_social_security_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3087">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-3088">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-3088">The checksum passes.</span></span>

```
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-3089">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-3089">Keywords</span></span>

<span data-ttu-id="888cb-3090">None</span><span class="sxs-lookup"><span data-stu-id="888cb-3090">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="888cb-3091">SQL Server 连接字符串</span><span class="sxs-lookup"><span data-stu-id="888cb-3091">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="888cb-3092">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-3092">Format</span></span>

<span data-ttu-id="888cb-3093">字符串 "user id"、"user id"、"uid" 或 "UserId", 后跟下面模式中所述的字符和字符串。</span><span class="sxs-lookup"><span data-stu-id="888cb-3093">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-3094">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-3094">Pattern</span></span>

- <span data-ttu-id="888cb-3095">字符串 "user id"、"user id"、"uid" 或 "UserId"</span><span class="sxs-lookup"><span data-stu-id="888cb-3095">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="888cb-3096">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="888cb-3096">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="888cb-3097">字符串 "Password" 或 "pwd", 其中 "pwd" 不以小写字母开头</span><span class="sxs-lookup"><span data-stu-id="888cb-3097">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="888cb-3098">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="888cb-3098">An equal sign (=)</span></span>
- <span data-ttu-id="888cb-3099">任何不是美元符号 ($)、百分号 (%)、大于号 (>)、符号 (@)、引号 (")、分号 (;)、左大括号 ([) 或左中括号 ({) 的任何字符</span><span class="sxs-lookup"><span data-stu-id="888cb-3099">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="888cb-3100">7-128 个字符的任意组合, 不是分号 (;)、正斜杠 (/) 或引号 (")</span><span class="sxs-lookup"><span data-stu-id="888cb-3100">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="888cb-3101">一个分号 (;)或引号 (")</span><span class="sxs-lookup"><span data-stu-id="888cb-3101">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-3102">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-3102">Checksum</span></span>

<span data-ttu-id="888cb-3103">否</span><span class="sxs-lookup"><span data-stu-id="888cb-3103">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-3104">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-3104">Definition</span></span>

<span data-ttu-id="888cb-3105">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-3105">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-3106">正则表达式 CEP_Regex_SQLServerConnectionString 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3106">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-3107">找**不**到 CEP_GlobalFilter 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3107">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="888cb-3108">正则表达式 CEP_PasswordPlaceHolder**未**找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3108">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-3109">正则表达式 CEP_CommonExampleKeywords**未**找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3109">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```
<!---SQL Server Connection String>
<Entity id="e76b6205-d3cb-46f2-bd63-c90153f2f97d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_SQLServerConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_GlobalFilter" />
            <Match idRef="CEP_PasswordPlaceHolder" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-3110">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-3110">Keywords</span></span>

#### <a name="cepglobalfilter"></a><span data-ttu-id="888cb-3111">CEP_GlobalFilter</span><span class="sxs-lookup"><span data-stu-id="888cb-3111">CEP_GlobalFilter</span></span>

- <span data-ttu-id="888cb-3112">部分密码</span><span class="sxs-lookup"><span data-stu-id="888cb-3112">some-password</span></span>
- <span data-ttu-id="888cb-3113">somepassword</span><span class="sxs-lookup"><span data-stu-id="888cb-3113">somepassword</span></span>
- <span data-ttu-id="888cb-3114">secretPassword</span><span class="sxs-lookup"><span data-stu-id="888cb-3114">secretPassword</span></span>
- <span data-ttu-id="888cb-3115">采用</span><span class="sxs-lookup"><span data-stu-id="888cb-3115">sample</span></span>

#### <a name="ceppasswordplaceholder"></a><span data-ttu-id="888cb-3116">CEP_PasswordPlaceHolder</span><span class="sxs-lookup"><span data-stu-id="888cb-3116">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="888cb-3117">(请注意, 从技术上讲, 此敏感信息类型通过使用正则表达式 (而不是关键字列表) 来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3117">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="888cb-3118">密码或密码后跟0-2 个空格、一个等号 (=)、0-2 个空格和一个星号 (\*)--或--</span><span class="sxs-lookup"><span data-stu-id="888cb-3118">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="888cb-3119">密码或密码后跟:</span><span class="sxs-lookup"><span data-stu-id="888cb-3119">Password or pwd followed by:</span></span>
    - <span data-ttu-id="888cb-3120">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="888cb-3120">Equal sign (=)</span></span>
    - <span data-ttu-id="888cb-3121">小于号 (<)</span><span class="sxs-lookup"><span data-stu-id="888cb-3121">Less than symbol (<)</span></span>
    - <span data-ttu-id="888cb-3122">1-200 个字符的任意组合, 这些字符为大写或小写字母、数字、星号 (\*)、连字符 (-)、下划线 (_) 或空白字符</span><span class="sxs-lookup"><span data-stu-id="888cb-3122">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="888cb-3123">大于号 (>)</span><span class="sxs-lookup"><span data-stu-id="888cb-3123">Greater than symbol (>)</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="888cb-3124">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="888cb-3124">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="888cb-3125">(请注意, 从技术上讲, 此敏感信息类型通过使用正则表达式 (而不是关键字列表) 来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3125">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="888cb-3126">尚未</span><span class="sxs-lookup"><span data-stu-id="888cb-3126">contoso</span></span>
- <span data-ttu-id="888cb-3127">送交</span><span class="sxs-lookup"><span data-stu-id="888cb-3127">fabrikam</span></span>
- <span data-ttu-id="888cb-3128">罗斯</span><span class="sxs-lookup"><span data-stu-id="888cb-3128">northwind</span></span>
- <span data-ttu-id="888cb-3129">沙盒</span><span class="sxs-lookup"><span data-stu-id="888cb-3129">sandbox</span></span>
- <span data-ttu-id="888cb-3130">onebox</span><span class="sxs-lookup"><span data-stu-id="888cb-3130">onebox</span></span>
- <span data-ttu-id="888cb-3131">localhost</span><span class="sxs-lookup"><span data-stu-id="888cb-3131">localhost</span></span>
- <span data-ttu-id="888cb-3132">127.0.0。1</span><span class="sxs-lookup"><span data-stu-id="888cb-3132">127.0.0.1</span></span>
- <span data-ttu-id="888cb-3133">testacs。<!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="888cb-3133">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="888cb-3134">s-int.<!--no-hyperlink-->net</span><span class="sxs-lookup"><span data-stu-id="888cb-3134">s-int.<!--no-hyperlink-->net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="888cb-3135">瑞典国家 ID</span><span class="sxs-lookup"><span data-stu-id="888cb-3135">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="888cb-3136">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-3136">Format</span></span>

<span data-ttu-id="888cb-3137">10 个或 12 个数字和一个可选分隔符</span><span class="sxs-lookup"><span data-stu-id="888cb-3137">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-3138">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-3138">Pattern</span></span>

<span data-ttu-id="888cb-3139">10 或 12 位数字和可选的分隔符：</span><span class="sxs-lookup"><span data-stu-id="888cb-3139">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="888cb-3140">2-4 位数字（可选）</span><span class="sxs-lookup"><span data-stu-id="888cb-3140">2-4 digits (optional)</span></span> 
- <span data-ttu-id="888cb-3141">采用日期格式 YYMMDD 的六位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3141">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="888cb-3142">“-”或“+”（可选）的分隔符，加</span><span class="sxs-lookup"><span data-stu-id="888cb-3142">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="888cb-3143">四个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3143">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-3144">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-3144">Checksum</span></span>

<span data-ttu-id="888cb-3145">是</span><span class="sxs-lookup"><span data-stu-id="888cb-3145">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-3146">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-3146">Definition</span></span>

<span data-ttu-id="888cb-3147">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-3147">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-3148">函数 Func_swedish_national_identifier 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3148">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-3149">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-3149">The checksum passes.</span></span>

```
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-3150">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-3150">Keywords</span></span>

<span data-ttu-id="888cb-3151">否</span><span class="sxs-lookup"><span data-stu-id="888cb-3151">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="888cb-3152">瑞典护照号码</span><span class="sxs-lookup"><span data-stu-id="888cb-3152">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-3153">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-3153">Format</span></span>

<span data-ttu-id="888cb-3154">八个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3154">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-3155">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-3155">Pattern</span></span>

<span data-ttu-id="888cb-3156">八个连续的数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3156">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-3157">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-3157">Checksum</span></span>

<span data-ttu-id="888cb-3158">否</span><span class="sxs-lookup"><span data-stu-id="888cb-3158">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-3159">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-3159">Definition</span></span>

<span data-ttu-id="888cb-3160">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-3160">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-3161">正则表达式 Regex_sweden_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3161">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-3162">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="888cb-3162">One of the following is true:</span></span>
    - <span data-ttu-id="888cb-3163">找到 Keyword_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3163">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="888cb-3164">找到 Keyword_sweden_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3164">A keyword from Keyword_sweden_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-3165">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-3165">Keywords</span></span>
   
#### <a name="keywordswedenpassport"></a><span data-ttu-id="888cb-3166">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="888cb-3166">Keyword_sweden_passport</span></span>

- <span data-ttu-id="888cb-3167">visa requirements</span><span class="sxs-lookup"><span data-stu-id="888cb-3167">visa requirements</span></span> 
- <span data-ttu-id="888cb-3168">Alien Registration Card</span><span class="sxs-lookup"><span data-stu-id="888cb-3168">Alien Registration Card</span></span> 
- <span data-ttu-id="888cb-3169">Schengen visas</span><span class="sxs-lookup"><span data-stu-id="888cb-3169">Schengen visas</span></span> 
- <span data-ttu-id="888cb-3170">Schengen visa</span><span class="sxs-lookup"><span data-stu-id="888cb-3170">Schengen visa</span></span> 
- <span data-ttu-id="888cb-3171">Visa Processing</span><span class="sxs-lookup"><span data-stu-id="888cb-3171">Visa Processing</span></span> 
- <span data-ttu-id="888cb-3172">Visa Type</span><span class="sxs-lookup"><span data-stu-id="888cb-3172">Visa Type</span></span> 
- <span data-ttu-id="888cb-3173">Single Entry</span><span class="sxs-lookup"><span data-stu-id="888cb-3173">Single Entry</span></span> 
- <span data-ttu-id="888cb-3174">Multiple Entry</span><span class="sxs-lookup"><span data-stu-id="888cb-3174">Multiple Entry</span></span> 
- <span data-ttu-id="888cb-3175">G3 Processing Fees</span><span class="sxs-lookup"><span data-stu-id="888cb-3175">G3 Processing Fees</span></span> 

#### <a name="keywordpassport"></a><span data-ttu-id="888cb-3176">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="888cb-3176">Keyword_passport</span></span>

- <span data-ttu-id="888cb-3177">Passport Number</span><span class="sxs-lookup"><span data-stu-id="888cb-3177">Passport Number</span></span> 
- <span data-ttu-id="888cb-3178">Passport No</span><span class="sxs-lookup"><span data-stu-id="888cb-3178">Passport No</span></span> 
- <span data-ttu-id="888cb-3179">Passport #</span><span class="sxs-lookup"><span data-stu-id="888cb-3179">Passport #</span></span> 
- <span data-ttu-id="888cb-3180">登记卡</span><span class="sxs-lookup"><span data-stu-id="888cb-3180">Passport#</span></span> 
- <span data-ttu-id="888cb-3181">PassportID</span><span class="sxs-lookup"><span data-stu-id="888cb-3181">PassportID</span></span> 
- <span data-ttu-id="888cb-3182">Passportno</span><span class="sxs-lookup"><span data-stu-id="888cb-3182">Passportno</span></span> 
- <span data-ttu-id="888cb-3183">passportnumber</span><span class="sxs-lookup"><span data-stu-id="888cb-3183">passportnumber</span></span> 
- <span data-ttu-id="888cb-3184">パスポート</span><span class="sxs-lookup"><span data-stu-id="888cb-3184">パスポート</span></span> 
- <span data-ttu-id="888cb-3185">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="888cb-3185">パスポート番号</span></span> 
- <span data-ttu-id="888cb-3186">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="888cb-3186">パスポートのNum</span></span> 
- <span data-ttu-id="888cb-3187">パスポート #</span><span class="sxs-lookup"><span data-stu-id="888cb-3187">パスポート＃</span></span> 
- <span data-ttu-id="888cb-3188">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="888cb-3188">Numéro de passeport</span></span> 
- <span data-ttu-id="888cb-3189">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="888cb-3189">Passeport n °</span></span> 
- <span data-ttu-id="888cb-3190">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="888cb-3190">Passeport Non</span></span> 
- <span data-ttu-id="888cb-3191">Passeport #</span><span class="sxs-lookup"><span data-stu-id="888cb-3191">Passeport #</span></span> 
- <span data-ttu-id="888cb-3192">Passeport #</span><span class="sxs-lookup"><span data-stu-id="888cb-3192">Passeport#</span></span> 
- <span data-ttu-id="888cb-3193">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="888cb-3193">PasseportNon</span></span> 
- <span data-ttu-id="888cb-3194">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="888cb-3194">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="888cb-3195">SWIFT 代码</span><span class="sxs-lookup"><span data-stu-id="888cb-3195">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="888cb-3196">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-3196">Format</span></span>

<span data-ttu-id="888cb-3197">四个字母后跟 5-31 个字母或数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3197">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-3198">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-3198">Pattern</span></span>

<span data-ttu-id="888cb-3199">四个字母后跟 5-31 个字母或数字：</span><span class="sxs-lookup"><span data-stu-id="888cb-3199">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="888cb-3200">四个字母的银行代码（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="888cb-3200">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="888cb-3201">可选空格</span><span class="sxs-lookup"><span data-stu-id="888cb-3201">An optional space</span></span> 
- <span data-ttu-id="888cb-3202">4-28 个字母或数字（基本银行账号 (BBAN)）</span><span class="sxs-lookup"><span data-stu-id="888cb-3202">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="888cb-3203">可选空格</span><span class="sxs-lookup"><span data-stu-id="888cb-3203">An optional space</span></span> 
- <span data-ttu-id="888cb-3204">1-3 个字母或数字（BBAN 的剩余内容）</span><span class="sxs-lookup"><span data-stu-id="888cb-3204">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-3205">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-3205">Checksum</span></span>

<span data-ttu-id="888cb-3206">否</span><span class="sxs-lookup"><span data-stu-id="888cb-3206">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-3207">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-3207">Definition</span></span>

<span data-ttu-id="888cb-3208">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-3208">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-3209">正则表达式 Regex_swift 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3209">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-3210">找到 Keyword_swift 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3210">A keyword from Keyword_swift is found.</span></span>

```
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-3211">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-3211">Keywords</span></span>
   
#### <a name="keywordswift"></a><span data-ttu-id="888cb-3212">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="888cb-3212">Keyword_swift</span></span>

- <span data-ttu-id="888cb-3213">international organization for standardization 9362</span><span class="sxs-lookup"><span data-stu-id="888cb-3213">international organization for standardization 9362</span></span> 
- <span data-ttu-id="888cb-3214">iso 9362</span><span class="sxs-lookup"><span data-stu-id="888cb-3214">iso 9362</span></span> 
- <span data-ttu-id="888cb-3215">iso9362</span><span class="sxs-lookup"><span data-stu-id="888cb-3215">iso9362</span></span> 
- <span data-ttu-id="888cb-3216">反应\#</span><span class="sxs-lookup"><span data-stu-id="888cb-3216">swift\#</span></span> 
- <span data-ttu-id="888cb-3217">swiftcode</span><span class="sxs-lookup"><span data-stu-id="888cb-3217">swiftcode</span></span> 
- <span data-ttu-id="888cb-3218">swiftnumber</span><span class="sxs-lookup"><span data-stu-id="888cb-3218">swiftnumber</span></span> 
- <span data-ttu-id="888cb-3219">swiftroutingnumber</span><span class="sxs-lookup"><span data-stu-id="888cb-3219">swiftroutingnumber</span></span> 
- <span data-ttu-id="888cb-3220">swift code</span><span class="sxs-lookup"><span data-stu-id="888cb-3220">swift code</span></span> 
- <span data-ttu-id="888cb-3221">swift number #</span><span class="sxs-lookup"><span data-stu-id="888cb-3221">swift number #</span></span> 
- <span data-ttu-id="888cb-3222">swift routing number</span><span class="sxs-lookup"><span data-stu-id="888cb-3222">swift routing number</span></span> 
- <span data-ttu-id="888cb-3223">bic number</span><span class="sxs-lookup"><span data-stu-id="888cb-3223">bic number</span></span> 
- <span data-ttu-id="888cb-3224">bic code</span><span class="sxs-lookup"><span data-stu-id="888cb-3224">bic code</span></span> 
- <span data-ttu-id="888cb-3225">numéro\#</span><span class="sxs-lookup"><span data-stu-id="888cb-3225">bic \#</span></span> 
- <span data-ttu-id="888cb-3226">numéro\#</span><span class="sxs-lookup"><span data-stu-id="888cb-3226">bic\#</span></span> 
- <span data-ttu-id="888cb-3227">bank identifier code</span><span class="sxs-lookup"><span data-stu-id="888cb-3227">bank identifier code</span></span> 
- <span data-ttu-id="888cb-3228">標準化9362</span><span class="sxs-lookup"><span data-stu-id="888cb-3228">標準化9362</span></span> 
- <span data-ttu-id="888cb-3229">迅速 #</span><span class="sxs-lookup"><span data-stu-id="888cb-3229">迅速＃</span></span> 
- <span data-ttu-id="888cb-3230">SWIFTコード</span><span class="sxs-lookup"><span data-stu-id="888cb-3230">SWIFTコード</span></span> 
- <span data-ttu-id="888cb-3231">SWIFT番号</span><span class="sxs-lookup"><span data-stu-id="888cb-3231">SWIFT番号</span></span> 
- <span data-ttu-id="888cb-3232">迅速なルーティング番号</span><span class="sxs-lookup"><span data-stu-id="888cb-3232">迅速なルーティング番号</span></span> 
- <span data-ttu-id="888cb-3233">BIC番号</span><span class="sxs-lookup"><span data-stu-id="888cb-3233">BIC番号</span></span> 
- <span data-ttu-id="888cb-3234">BICコード</span><span class="sxs-lookup"><span data-stu-id="888cb-3234">BICコード</span></span> 
- <span data-ttu-id="888cb-3235">銀行識別コードのための国際組織</span><span class="sxs-lookup"><span data-stu-id="888cb-3235">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="888cb-3236">Organisation internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="888cb-3236">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="888cb-3237">rapide\#</span><span class="sxs-lookup"><span data-stu-id="888cb-3237">rapide \#</span></span> 
- <span data-ttu-id="888cb-3238">code SWIFT</span><span class="sxs-lookup"><span data-stu-id="888cb-3238">code SWIFT</span></span> 
- <span data-ttu-id="888cb-3239">le numéro de swift</span><span class="sxs-lookup"><span data-stu-id="888cb-3239">le numéro de swift</span></span> 
- <span data-ttu-id="888cb-3240">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="888cb-3240">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="888cb-3241">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="888cb-3241">le numéro BIC</span></span> 
- <span data-ttu-id="888cb-3242">\#numéro</span><span class="sxs-lookup"><span data-stu-id="888cb-3242">\# BIC</span></span> 
- <span data-ttu-id="888cb-3243">code identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="888cb-3243">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="888cb-3244">台湾国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="888cb-3244">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="888cb-3245">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-3245">Format</span></span>

<span data-ttu-id="888cb-3246">一个字母后跟九个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3246">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-3247">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-3247">Pattern</span></span>

<span data-ttu-id="888cb-3248">一个字母后跟 9 位数字：</span><span class="sxs-lookup"><span data-stu-id="888cb-3248">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="888cb-3249">一个字母（英文，不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="888cb-3249">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="888cb-3250">数字“1”或“2”</span><span class="sxs-lookup"><span data-stu-id="888cb-3250">The digit "1" or "2"</span></span> 
- <span data-ttu-id="888cb-3251">八位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3251">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-3252">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-3252">Checksum</span></span>

<span data-ttu-id="888cb-3253">是</span><span class="sxs-lookup"><span data-stu-id="888cb-3253">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-3254">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-3254">Definition</span></span>

<span data-ttu-id="888cb-3255">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-3255">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-3256">函数 Func_taiwanese_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3256">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-3257">找到 Keyword_taiwanese_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3257">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="888cb-3258">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-3258">The checksum passes.</span></span>

```
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-3259">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-3259">Keywords</span></span>

#### <a name="keywordtaiwanesenationalid"></a><span data-ttu-id="888cb-3260">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="888cb-3260">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="888cb-3261">身份證字號</span><span class="sxs-lookup"><span data-stu-id="888cb-3261">身份證字號</span></span> 
- <span data-ttu-id="888cb-3262">證</span><span class="sxs-lookup"><span data-stu-id="888cb-3262">身份證</span></span> 
- <span data-ttu-id="888cb-3263">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="888cb-3263">身份證號碼</span></span> 
- <span data-ttu-id="888cb-3264">身份證號</span><span class="sxs-lookup"><span data-stu-id="888cb-3264">身份證號</span></span> 
- <span data-ttu-id="888cb-3265">身分證字號</span><span class="sxs-lookup"><span data-stu-id="888cb-3265">身分證字號</span></span> 
- <span data-ttu-id="888cb-3266">身分證</span><span class="sxs-lookup"><span data-stu-id="888cb-3266">身分證</span></span> 
- <span data-ttu-id="888cb-3267">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="888cb-3267">身分證號碼</span></span> 
- <span data-ttu-id="888cb-3268">身份證號</span><span class="sxs-lookup"><span data-stu-id="888cb-3268">身份證號</span></span> 
- <span data-ttu-id="888cb-3269">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="888cb-3269">身分證統一編號</span></span> 
- <span data-ttu-id="888cb-3270">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="888cb-3270">國民身分證統一編號</span></span> 
- <span data-ttu-id="888cb-3271">簽名</span><span class="sxs-lookup"><span data-stu-id="888cb-3271">簽名</span></span> 
- <span data-ttu-id="888cb-3272">蓋章</span><span class="sxs-lookup"><span data-stu-id="888cb-3272">蓋章</span></span> 
- <span data-ttu-id="888cb-3273">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="888cb-3273">簽名或蓋章</span></span> 
- <span data-ttu-id="888cb-3274">簽章</span><span class="sxs-lookup"><span data-stu-id="888cb-3274">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="888cb-3275">	台湾护照号码</span><span class="sxs-lookup"><span data-stu-id="888cb-3275">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-3276">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-3276">Format</span></span>

- <span data-ttu-id="888cb-3277">生物识别护照号码: 9 个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3277">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="888cb-3278">不带生物的护照号码: 9 个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3278">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-3279">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-3279">Pattern</span></span>
<span data-ttu-id="888cb-3280">生物识别护照号码:</span><span class="sxs-lookup"><span data-stu-id="888cb-3280">Biometric passport number:</span></span>
- <span data-ttu-id="888cb-3281">数字“3” </span><span class="sxs-lookup"><span data-stu-id="888cb-3281">The digit "3"</span></span> 
- <span data-ttu-id="888cb-3282">八个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3282">Eight digits</span></span>

<span data-ttu-id="888cb-3283">不带生物的护照号码:</span><span class="sxs-lookup"><span data-stu-id="888cb-3283">Non-biometric passport number:</span></span>
- <span data-ttu-id="888cb-3284">九个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3284">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-3285">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-3285">Checksum</span></span>

<span data-ttu-id="888cb-3286">否</span><span class="sxs-lookup"><span data-stu-id="888cb-3286">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-3287">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-3287">Definition</span></span>

<span data-ttu-id="888cb-3288">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-3288">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-3289">正则表达式 Regex_taiwan_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3289">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-3290">找到 Keyword_taiwan_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3290">A keyword from Keyword_taiwan_passport is found.</span></span>

```
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-3291">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-3291">Keywords</span></span>

#### <a name="keywordtaiwanpassport"></a><span data-ttu-id="888cb-3292">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="888cb-3292">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="888cb-3293">ROC passport number</span><span class="sxs-lookup"><span data-stu-id="888cb-3293">ROC passport number</span></span> 
- <span data-ttu-id="888cb-3294">Passport number</span><span class="sxs-lookup"><span data-stu-id="888cb-3294">Passport number</span></span> 
- <span data-ttu-id="888cb-3295">Passport no</span><span class="sxs-lookup"><span data-stu-id="888cb-3295">Passport no</span></span> 
- <span data-ttu-id="888cb-3296">Passport Num</span><span class="sxs-lookup"><span data-stu-id="888cb-3296">Passport Num</span></span> 
- <span data-ttu-id="888cb-3297">Passport #</span><span class="sxs-lookup"><span data-stu-id="888cb-3297">Passport #</span></span> 
- <span data-ttu-id="888cb-3298">护照</span><span class="sxs-lookup"><span data-stu-id="888cb-3298">护照</span></span> 
- <span data-ttu-id="888cb-3299">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="888cb-3299">中華民國護照</span></span> 
- <span data-ttu-id="888cb-3300">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="888cb-3300">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="888cb-3301">台湾居民证 (ARC/TARC) 号码</span><span class="sxs-lookup"><span data-stu-id="888cb-3301">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-3302">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-3302">Format</span></span>

<span data-ttu-id="888cb-3303">10 letters and digits</span><span class="sxs-lookup"><span data-stu-id="888cb-3303">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-3304">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-3304">Pattern</span></span>

<span data-ttu-id="888cb-3305">10 个字母和数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3305">10 letters and digits:</span></span>
- <span data-ttu-id="888cb-3306">两个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="888cb-3306">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="888cb-3307">八个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3307">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-3308">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-3308">Checksum</span></span>

<span data-ttu-id="888cb-3309">否</span><span class="sxs-lookup"><span data-stu-id="888cb-3309">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-3310">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-3310">Definition</span></span>

<span data-ttu-id="888cb-3311">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-3311">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-3312">正则表达式 Regex_taiwan_resident_certificate 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3312">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-3313">找到 Keyword_taiwan_resident_certificate 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3313">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-3314">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-3314">Keywords</span></span>

#### <a name="keywordtaiwanresidentcertificate"></a><span data-ttu-id="888cb-3315">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="888cb-3315">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="888cb-3316">Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="888cb-3316">Resident Certificate</span></span> 
- <span data-ttu-id="888cb-3317">Resident Cert</span><span class="sxs-lookup"><span data-stu-id="888cb-3317">Resident Cert</span></span> 
- <span data-ttu-id="888cb-3318">Resident Cert.</span><span class="sxs-lookup"><span data-stu-id="888cb-3318">Resident Cert.</span></span> 
- <span data-ttu-id="888cb-3319">Identification card</span><span class="sxs-lookup"><span data-stu-id="888cb-3319">Identification card</span></span> 
- <span data-ttu-id="888cb-3320">Alien Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="888cb-3320">Alien Resident Certificate</span></span> 
- <span data-ttu-id="888cb-3321">ARC</span><span class="sxs-lookup"><span data-stu-id="888cb-3321">ARC</span></span> 
- <span data-ttu-id="888cb-3322">Taiwan Area Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="888cb-3322">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="888cb-3323">TARC</span><span class="sxs-lookup"><span data-stu-id="888cb-3323">TARC</span></span> 
- <span data-ttu-id="888cb-3324">居留證</span><span class="sxs-lookup"><span data-stu-id="888cb-3324">居留證</span></span> 
- <span data-ttu-id="888cb-3325">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="888cb-3325">外僑居留證</span></span> 
- <span data-ttu-id="888cb-3326">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="888cb-3326">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="888cb-3327">泰语填充标识代码</span><span class="sxs-lookup"><span data-stu-id="888cb-3327">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="888cb-3328">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-3328">Format</span></span>

<span data-ttu-id="888cb-3329">13 位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3329">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-3330">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-3330">Pattern</span></span>

<span data-ttu-id="888cb-3331">13 个数字：</span><span class="sxs-lookup"><span data-stu-id="888cb-3331">13 digits:</span></span>
- <span data-ttu-id="888cb-3332">第一个数字不是0或9</span><span class="sxs-lookup"><span data-stu-id="888cb-3332">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="888cb-3333">12 个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3333">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-3334">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-3334">Checksum</span></span>

<span data-ttu-id="888cb-3335">是</span><span class="sxs-lookup"><span data-stu-id="888cb-3335">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-3336">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-3336">Definition</span></span>

<span data-ttu-id="888cb-3337">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-3337">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-3338">函数 Func_Thai_Citizen_Id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3338">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-3339">找到 Keyword_Thai_Citizen_Id 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3339">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="888cb-3340">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-3340">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-3341">函数 Func_Thai_Citizen_Id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3341">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-3342">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-3342">Keywords</span></span>

#### <a name="keywordthaicitizenid"></a><span data-ttu-id="888cb-3343">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="888cb-3343">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="888cb-3344">ID Number</span><span class="sxs-lookup"><span data-stu-id="888cb-3344">ID Number</span></span>
- <span data-ttu-id="888cb-3345">标识号码</span><span class="sxs-lookup"><span data-stu-id="888cb-3345">Identification Number</span></span>
- <span data-ttu-id="888cb-3346">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="888cb-3346">บัตรประชาชน</span></span>
- <span data-ttu-id="888cb-3347">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="888cb-3347">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="888cb-3348">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="888cb-3348">บัตรประชาชน</span></span>
- <span data-ttu-id="888cb-3349">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="888cb-3349">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="888cb-3350">土耳其国家标识号码</span><span class="sxs-lookup"><span data-stu-id="888cb-3350">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-3351">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-3351">Format</span></span>

<span data-ttu-id="888cb-3352">11 个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3352">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-3353">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-3353">Pattern</span></span>

<span data-ttu-id="888cb-3354">11 个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3354">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-3355">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-3355">Checksum</span></span>

<span data-ttu-id="888cb-3356">是</span><span class="sxs-lookup"><span data-stu-id="888cb-3356">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-3357">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-3357">Definition</span></span>

<span data-ttu-id="888cb-3358">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-3358">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-3359">函数 Func_Turkish_National_Id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3359">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-3360">找到 Keyword_Turkish_National_Id 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3360">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="888cb-3361">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-3361">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-3362">函数 Func_Turkish_National_Id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3362">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-3363">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-3363">Keywords</span></span>

#### <a name="keywordturkishnationalid"></a><span data-ttu-id="888cb-3364">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="888cb-3364">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="888cb-3365">TC Kimlik No</span><span class="sxs-lookup"><span data-stu-id="888cb-3365">TC Kimlik No</span></span>
- <span data-ttu-id="888cb-3366">TC Kimlik numarası</span><span class="sxs-lookup"><span data-stu-id="888cb-3366">TC Kimlik numarası</span></span>
- <span data-ttu-id="888cb-3367">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="888cb-3367">Vatandaşlık numarası</span></span>
- <span data-ttu-id="888cb-3368">Vatandaşlık no</span><span class="sxs-lookup"><span data-stu-id="888cb-3368">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="888cb-p141">英国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="888cb-p141">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-3371">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-3371">Format</span></span>

<span data-ttu-id="888cb-3372">特定格式的 18 个字母和数字组合</span><span class="sxs-lookup"><span data-stu-id="888cb-3372">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-3373">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-3373">Pattern</span></span>

<span data-ttu-id="888cb-3374">18 个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="888cb-3374">18 letters and digits:</span></span>
- <span data-ttu-id="888cb-3375">用五个字母（不区分大小写）或数字“9”来代替一个字母</span><span class="sxs-lookup"><span data-stu-id="888cb-3375">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="888cb-3376">一位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3376">One digit</span></span> 
- <span data-ttu-id="888cb-3377">采用日期格式 DDMMY 的五位数字，表示出生日期</span><span class="sxs-lookup"><span data-stu-id="888cb-3377">Five digits in the date format DDMMY for date of birth</span></span> 
- <span data-ttu-id="888cb-3378">用两个字母（不区分大小写）或数字“9”来代替一个字母</span><span class="sxs-lookup"><span data-stu-id="888cb-3378">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="888cb-3379">五位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3379">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-3380">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-3380">Checksum</span></span>

<span data-ttu-id="888cb-3381">是</span><span class="sxs-lookup"><span data-stu-id="888cb-3381">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-3382">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-3382">Definition</span></span>

<span data-ttu-id="888cb-3383">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-3383">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-3384">函数 Func_uk_drivers_license 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3384">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-3385">找到 Keyword_uk_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3385">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="888cb-3386">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-3386">The checksum passes.</span></span>

```
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-3387">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-3387">Keywords</span></span>

#### <a name="keywordukdriverslicense"></a><span data-ttu-id="888cb-3388">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="888cb-3388">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="888cb-3389">DVLA</span><span class="sxs-lookup"><span data-stu-id="888cb-3389">DVLA</span></span> 
- <span data-ttu-id="888cb-3390">light vans</span><span class="sxs-lookup"><span data-stu-id="888cb-3390">light vans</span></span> 
- <span data-ttu-id="888cb-3391">quadbikes</span><span class="sxs-lookup"><span data-stu-id="888cb-3391">quadbikes</span></span> 
- <span data-ttu-id="888cb-3392">motor cars</span><span class="sxs-lookup"><span data-stu-id="888cb-3392">motor cars</span></span> 
- <span data-ttu-id="888cb-3393">125cc</span><span class="sxs-lookup"><span data-stu-id="888cb-3393">125cc</span></span> 
- <span data-ttu-id="888cb-3394">sidecar</span><span class="sxs-lookup"><span data-stu-id="888cb-3394">sidecar</span></span> 
- <span data-ttu-id="888cb-3395">tricycles</span><span class="sxs-lookup"><span data-stu-id="888cb-3395">tricycles</span></span> 
- <span data-ttu-id="888cb-3396">motorcycles</span><span class="sxs-lookup"><span data-stu-id="888cb-3396">motorcycles</span></span> 
- <span data-ttu-id="888cb-3397">photocard licence</span><span class="sxs-lookup"><span data-stu-id="888cb-3397">photocard licence</span></span> 
- <span data-ttu-id="888cb-3398">learner drivers</span><span class="sxs-lookup"><span data-stu-id="888cb-3398">learner drivers</span></span> 
- <span data-ttu-id="888cb-3399">licence holder</span><span class="sxs-lookup"><span data-stu-id="888cb-3399">licence holder</span></span> 
- <span data-ttu-id="888cb-3400">licence holders</span><span class="sxs-lookup"><span data-stu-id="888cb-3400">licence holders</span></span> 
- <span data-ttu-id="888cb-3401">driving licences</span><span class="sxs-lookup"><span data-stu-id="888cb-3401">driving licences</span></span> 
- <span data-ttu-id="888cb-3402">driving licence</span><span class="sxs-lookup"><span data-stu-id="888cb-3402">driving licence</span></span> 
- <span data-ttu-id="888cb-3403">dual control car</span><span class="sxs-lookup"><span data-stu-id="888cb-3403">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="888cb-p142">英国选民名册号码</span><span class="sxs-lookup"><span data-stu-id="888cb-p142">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-3406">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-3406">Format</span></span>

<span data-ttu-id="888cb-3407">两个字母后跟 1-4 个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3407">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-3408">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-3408">Pattern</span></span>

<span data-ttu-id="888cb-3409">两个字母（不区分大小写）后跟 1-4 个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3409">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-3410">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-3410">Checksum</span></span>

<span data-ttu-id="888cb-3411">否</span><span class="sxs-lookup"><span data-stu-id="888cb-3411">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-3412">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-3412">Definition</span></span>

<span data-ttu-id="888cb-3413">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-3413">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-3414">正则表达式 Regex_uk_electoral 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3414">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-3415">找到 Keyword_uk_electoral 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3415">A keyword from Keyword_uk_electoral is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-3416">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-3416">Keywords</span></span>

#### <a name="keywordukelectoral"></a><span data-ttu-id="888cb-3417">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="888cb-3417">Keyword_uk_electoral</span></span>

- <span data-ttu-id="888cb-3418">council nomination</span><span class="sxs-lookup"><span data-stu-id="888cb-3418">council nomination</span></span> 
- <span data-ttu-id="888cb-3419">nomination form</span><span class="sxs-lookup"><span data-stu-id="888cb-3419">nomination form</span></span> 
- <span data-ttu-id="888cb-3420">electoral register</span><span class="sxs-lookup"><span data-stu-id="888cb-3420">electoral register</span></span> 
- <span data-ttu-id="888cb-3421">electoral roll</span><span class="sxs-lookup"><span data-stu-id="888cb-3421">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="888cb-p143">英国国家卫生服务号码</span><span class="sxs-lookup"><span data-stu-id="888cb-p143">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-3424">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-3424">Format</span></span>

<span data-ttu-id="888cb-3425">10-17 个数字，通过空格分隔 </span><span class="sxs-lookup"><span data-stu-id="888cb-3425">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-3426">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-3426">Pattern</span></span>

<span data-ttu-id="888cb-3427">10-17 位数字：</span><span class="sxs-lookup"><span data-stu-id="888cb-3427">10-17 digits:</span></span>
- <span data-ttu-id="888cb-3428">3 或 10 位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3428">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="888cb-3429">一个空格</span><span class="sxs-lookup"><span data-stu-id="888cb-3429">A space</span></span> 
- <span data-ttu-id="888cb-3430">三位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3430">Three digits</span></span> 
- <span data-ttu-id="888cb-3431">一个空格</span><span class="sxs-lookup"><span data-stu-id="888cb-3431">A space</span></span> 
- <span data-ttu-id="888cb-3432">四位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3432">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-3433">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-3433">Checksum</span></span>

<span data-ttu-id="888cb-3434">是</span><span class="sxs-lookup"><span data-stu-id="888cb-3434">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-3435">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-3435">Definition</span></span>

<span data-ttu-id="888cb-3436">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-3436">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-3437">函数 Func_uk_nhs_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3437">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-3438">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="888cb-3438">One of the following is true:</span></span>
    - <span data-ttu-id="888cb-3439">找到 Keyword_uk_nhs_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3439">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="888cb-3440">找到 Keyword_uk_nhs_number1 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3440">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="888cb-3441">找到 Keyword_uk_nhs_number_dob 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3441">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="888cb-3442">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="888cb-3442">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-3443">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-3443">Keywords</span></span>
   
#### <a name="keyworduknhsnumber"></a><span data-ttu-id="888cb-3444">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="888cb-3444">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="888cb-3445">national health service</span><span class="sxs-lookup"><span data-stu-id="888cb-3445">national health service</span></span> 
- <span data-ttu-id="888cb-3446">nhs</span><span class="sxs-lookup"><span data-stu-id="888cb-3446">nhs</span></span> 
- <span data-ttu-id="888cb-3447">health services authority</span><span class="sxs-lookup"><span data-stu-id="888cb-3447">health services authority</span></span> 
- <span data-ttu-id="888cb-3448">health authority</span><span class="sxs-lookup"><span data-stu-id="888cb-3448">health authority</span></span>

#### <a name="keyworduknhsnumber1"></a><span data-ttu-id="888cb-3449">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="888cb-3449">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="888cb-3450">patient id</span><span class="sxs-lookup"><span data-stu-id="888cb-3450">patient id</span></span> 
- <span data-ttu-id="888cb-3451">patient identification</span><span class="sxs-lookup"><span data-stu-id="888cb-3451">patient identification</span></span> 
- <span data-ttu-id="888cb-3452">patient no</span><span class="sxs-lookup"><span data-stu-id="888cb-3452">patient no</span></span> 
- <span data-ttu-id="888cb-3453">patient number</span><span class="sxs-lookup"><span data-stu-id="888cb-3453">patient number</span></span>

#### <a name="keyworduknhsnumberdob"></a><span data-ttu-id="888cb-3454">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="888cb-3454">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="888cb-3455">GP</span><span class="sxs-lookup"><span data-stu-id="888cb-3455">GP</span></span> 
- <span data-ttu-id="888cb-3456">DOB</span><span class="sxs-lookup"><span data-stu-id="888cb-3456">DOB</span></span> 
- <span data-ttu-id="888cb-3457">D. B。</span><span class="sxs-lookup"><span data-stu-id="888cb-3457">D.O.B</span></span> 
- <span data-ttu-id="888cb-3458">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="888cb-3458">Date of Birth</span></span> 
- <span data-ttu-id="888cb-3459">Birth Date</span><span class="sxs-lookup"><span data-stu-id="888cb-3459">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="888cb-p144">英国国家保险号码 (NINO)</span><span class="sxs-lookup"><span data-stu-id="888cb-p144">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="888cb-3462">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-3462">Format</span></span>

<span data-ttu-id="888cb-3463">由空格或短划线分隔的7个字符或9个字符</span><span class="sxs-lookup"><span data-stu-id="888cb-3463">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-3464">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-3464">Pattern</span></span>

<span data-ttu-id="888cb-3465">两种可能的模式:</span><span class="sxs-lookup"><span data-stu-id="888cb-3465">Two possible patterns:</span></span>

- <span data-ttu-id="888cb-3466">两个字母 (有效 NINOs 仅使用此前缀中的特定字符, 此格式将对此进行验证; 不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="888cb-3466">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="888cb-3467">六位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3467">Six digits</span></span>
- <span data-ttu-id="888cb-3468">"A"、"B"、"C" 或 "d" (与前缀一样, 后缀中只允许有某些字符; 不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="888cb-3468">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="888cb-3469">OR</span><span class="sxs-lookup"><span data-stu-id="888cb-3469">OR</span></span>

- <span data-ttu-id="888cb-3470">两个字母</span><span class="sxs-lookup"><span data-stu-id="888cb-3470">Two letters</span></span>
- <span data-ttu-id="888cb-3471">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="888cb-3471">A space or dash</span></span>
- <span data-ttu-id="888cb-3472">两位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3472">Two digits</span></span>
- <span data-ttu-id="888cb-3473">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="888cb-3473">A space or dash</span></span>
- <span data-ttu-id="888cb-3474">两位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3474">Two digits</span></span>
- <span data-ttu-id="888cb-3475">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="888cb-3475">A space or dash</span></span>
- <span data-ttu-id="888cb-3476">两位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3476">Two digits</span></span>
- <span data-ttu-id="888cb-3477">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="888cb-3477">A space or dash</span></span>
- <span data-ttu-id="888cb-3478">要么是 "A"、"B"、"C", 要么 ' d '</span><span class="sxs-lookup"><span data-stu-id="888cb-3478">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-3479">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-3479">Checksum</span></span>

<span data-ttu-id="888cb-3480">否</span><span class="sxs-lookup"><span data-stu-id="888cb-3480">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-3481">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-3481">Definition</span></span>

<span data-ttu-id="888cb-3482">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-3482">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-3483">函数 Func_uk_nino 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3483">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-3484">找到 Keyword_uk_nino 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3484">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="888cb-3485">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-3485">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-3486">函数 Func_uk_nino 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3486">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-3487">未找到 Keyword_uk_nino 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3487">No keyword from Keyword_uk_nino is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-3488">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-3488">Keywords</span></span>

#### <a name="keyworduknino"></a><span data-ttu-id="888cb-3489">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="888cb-3489">Keyword_uk_nino</span></span>

- <span data-ttu-id="888cb-3490">national insurance number</span><span class="sxs-lookup"><span data-stu-id="888cb-3490">national insurance number</span></span> 
- <span data-ttu-id="888cb-3491">national insurance contributions</span><span class="sxs-lookup"><span data-stu-id="888cb-3491">national insurance contributions</span></span> 
- <span data-ttu-id="888cb-3492">protection act</span><span class="sxs-lookup"><span data-stu-id="888cb-3492">protection act</span></span> 
- <span data-ttu-id="888cb-3493">方面</span><span class="sxs-lookup"><span data-stu-id="888cb-3493">insurance</span></span> 
- <span data-ttu-id="888cb-3494">social security number</span><span class="sxs-lookup"><span data-stu-id="888cb-3494">social security number</span></span> 
- <span data-ttu-id="888cb-3495">insurance application</span><span class="sxs-lookup"><span data-stu-id="888cb-3495">insurance application</span></span> 
- <span data-ttu-id="888cb-3496">medical application</span><span class="sxs-lookup"><span data-stu-id="888cb-3496">medical application</span></span> 
- <span data-ttu-id="888cb-3497">social insurance</span><span class="sxs-lookup"><span data-stu-id="888cb-3497">social insurance</span></span> 
- <span data-ttu-id="888cb-3498">medical attention</span><span class="sxs-lookup"><span data-stu-id="888cb-3498">medical attention</span></span> 
- <span data-ttu-id="888cb-3499">social security</span><span class="sxs-lookup"><span data-stu-id="888cb-3499">social security</span></span> 
- <span data-ttu-id="888cb-3500">great britain</span><span class="sxs-lookup"><span data-stu-id="888cb-3500">great britain</span></span> 
- <span data-ttu-id="888cb-3501">方面</span><span class="sxs-lookup"><span data-stu-id="888cb-3501">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="888cb-p145">美国/英国护照号码</span><span class="sxs-lookup"><span data-stu-id="888cb-p145">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-3504">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-3504">Format</span></span>

<span data-ttu-id="888cb-3505">九个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3505">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-3506">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-3506">Pattern</span></span>

<span data-ttu-id="888cb-3507">九个连续的数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3507">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-3508">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-3508">Checksum</span></span>

<span data-ttu-id="888cb-3509">否</span><span class="sxs-lookup"><span data-stu-id="888cb-3509">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-3510">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-3510">Definition</span></span>

<span data-ttu-id="888cb-3511">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-3511">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-3512">函数 Func_usa_uk_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3512">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-3513">找到 Keyword_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3513">A keyword from Keyword_passport is found.</span></span>

```
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-3514">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-3514">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="888cb-3515">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="888cb-3515">Keyword_passport</span></span>

- <span data-ttu-id="888cb-3516">Passport Number</span><span class="sxs-lookup"><span data-stu-id="888cb-3516">Passport Number</span></span> 
- <span data-ttu-id="888cb-3517">Passport No</span><span class="sxs-lookup"><span data-stu-id="888cb-3517">Passport No</span></span> 
- <span data-ttu-id="888cb-3518">Passport #</span><span class="sxs-lookup"><span data-stu-id="888cb-3518">Passport #</span></span> 
- <span data-ttu-id="888cb-3519">登记卡</span><span class="sxs-lookup"><span data-stu-id="888cb-3519">Passport#</span></span> 
- <span data-ttu-id="888cb-3520">PassportID</span><span class="sxs-lookup"><span data-stu-id="888cb-3520">PassportID</span></span> 
- <span data-ttu-id="888cb-3521">Passportno</span><span class="sxs-lookup"><span data-stu-id="888cb-3521">Passportno</span></span> 
- <span data-ttu-id="888cb-3522">passportnumber</span><span class="sxs-lookup"><span data-stu-id="888cb-3522">passportnumber</span></span> 
- <span data-ttu-id="888cb-3523">パスポート</span><span class="sxs-lookup"><span data-stu-id="888cb-3523">パスポート</span></span> 
- <span data-ttu-id="888cb-3524">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="888cb-3524">パスポート番号</span></span> 
- <span data-ttu-id="888cb-3525">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="888cb-3525">パスポートのNum</span></span> 
- <span data-ttu-id="888cb-3526">パスポート #</span><span class="sxs-lookup"><span data-stu-id="888cb-3526">パスポート＃</span></span> 
- <span data-ttu-id="888cb-3527">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="888cb-3527">Numéro de passeport</span></span> 
- <span data-ttu-id="888cb-3528">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="888cb-3528">Passeport n °</span></span> 
- <span data-ttu-id="888cb-3529">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="888cb-3529">Passeport Non</span></span> 
- <span data-ttu-id="888cb-3530">Passeport #</span><span class="sxs-lookup"><span data-stu-id="888cb-3530">Passeport #</span></span> 
- <span data-ttu-id="888cb-3531">Passeport #</span><span class="sxs-lookup"><span data-stu-id="888cb-3531">Passeport#</span></span> 
- <span data-ttu-id="888cb-3532">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="888cb-3532">PasseportNon</span></span> 
- <span data-ttu-id="888cb-3533">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="888cb-3533">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="888cb-3534">美国银行帐号</span><span class="sxs-lookup"><span data-stu-id="888cb-3534">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-3535">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-3535">Format</span></span>

<span data-ttu-id="888cb-3536">8-17 个数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3536">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-3537">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-3537">Pattern</span></span>

<span data-ttu-id="888cb-3538">8-17 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3538">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-3539">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-3539">Checksum</span></span>

<span data-ttu-id="888cb-3540">否</span><span class="sxs-lookup"><span data-stu-id="888cb-3540">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-3541">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-3541">Definition</span></span>

<span data-ttu-id="888cb-3542">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-3542">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-3543">正则表达式 Regex_usa_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3543">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-3544">找到 Keyword_usa_Bank_Account 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3544">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="888cb-3545">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-3545">Keywords</span></span>

#### <a name="keywordusabankaccount"></a><span data-ttu-id="888cb-3546">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="888cb-3546">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="888cb-3547">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="888cb-3547">Checking Account Number</span></span> 
- <span data-ttu-id="888cb-3548">Checking Account</span><span class="sxs-lookup"><span data-stu-id="888cb-3548">Checking Account</span></span> 
- <span data-ttu-id="888cb-3549">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="888cb-3549">Checking Account #</span></span> 
- <span data-ttu-id="888cb-3550">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="888cb-3550">Checking Acct Number</span></span> 
- <span data-ttu-id="888cb-3551">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="888cb-3551">Checking Acct #</span></span> 
- <span data-ttu-id="888cb-3552">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="888cb-3552">Checking Acct No.</span></span> 
- <span data-ttu-id="888cb-3553">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="888cb-3553">Checking Account No.</span></span> 
- <span data-ttu-id="888cb-3554">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="888cb-3554">Bank Account Number</span></span> 
- <span data-ttu-id="888cb-3555">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="888cb-3555">Bank Account #</span></span> 
- <span data-ttu-id="888cb-3556">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="888cb-3556">Bank Acct Number</span></span> 
- <span data-ttu-id="888cb-3557">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="888cb-3557">Bank Acct #</span></span> 
- <span data-ttu-id="888cb-3558">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="888cb-3558">Bank Acct No.</span></span> 
- <span data-ttu-id="888cb-3559">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="888cb-3559">Bank Account No.</span></span> 
- <span data-ttu-id="888cb-3560">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="888cb-3560">Savings Account Number</span></span> 
- <span data-ttu-id="888cb-3561">Savings Account.</span><span class="sxs-lookup"><span data-stu-id="888cb-3561">Savings Account.</span></span> 
- <span data-ttu-id="888cb-3562">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="888cb-3562">Savings Account #</span></span> 
- <span data-ttu-id="888cb-3563">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="888cb-3563">Savings Acct Number</span></span> 
- <span data-ttu-id="888cb-3564">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="888cb-3564">Savings Acct #</span></span> 
- <span data-ttu-id="888cb-3565">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="888cb-3565">Savings Acct No.</span></span> 
- <span data-ttu-id="888cb-3566">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="888cb-3566">Savings Account No.</span></span> 
- <span data-ttu-id="888cb-3567">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="888cb-3567">Debit Account Number</span></span> 
- <span data-ttu-id="888cb-3568">Debit Account</span><span class="sxs-lookup"><span data-stu-id="888cb-3568">Debit Account</span></span> 
- <span data-ttu-id="888cb-3569">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="888cb-3569">Debit Account #</span></span> 
- <span data-ttu-id="888cb-3570">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="888cb-3570">Debit Acct Number</span></span> 
- <span data-ttu-id="888cb-3571">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="888cb-3571">Debit Acct #</span></span> 
- <span data-ttu-id="888cb-3572">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="888cb-3572">Debit Acct No.</span></span> 
- <span data-ttu-id="888cb-3573">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="888cb-3573">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="888cb-3574">美国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="888cb-3574">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="888cb-3575">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-3575">Format</span></span>

<span data-ttu-id="888cb-3576">取决于州</span><span class="sxs-lookup"><span data-stu-id="888cb-3576">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-3577">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-3577">Pattern</span></span>

<span data-ttu-id="888cb-3578">取决于州 — 例如，纽约：</span><span class="sxs-lookup"><span data-stu-id="888cb-3578">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="888cb-3579">与 ddd ddd ddd 相匹配的9个数字的格式将会匹配。</span><span class="sxs-lookup"><span data-stu-id="888cb-3579">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="888cb-3580">诸如 dddddddd 的 9 个数字将不匹配。</span><span class="sxs-lookup"><span data-stu-id="888cb-3580">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-3581">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-3581">Checksum</span></span>

<span data-ttu-id="888cb-3582">否</span><span class="sxs-lookup"><span data-stu-id="888cb-3582">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-3583">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-3583">Definition</span></span>

<span data-ttu-id="888cb-3584">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-3584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-3585">函数 Func_new_york_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3585">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-3586">找到 Keyword_[state_name]_drivers_license_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3586">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="888cb-3587">找到 Keyword_us_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3587">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="888cb-3588">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-3588">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-3589">函数 Func_new_york_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3589">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-3590">找到 Keyword_[state_name]_drivers_license_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3590">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="888cb-3591">找到 Keyword_us_drivers_license_abbreviations 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3591">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="888cb-3592">未找到 Keyword_us_drivers_license 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3592">No keyword from Keyword_us_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-3593">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-3593">Keywords</span></span>

#### <a name="keywordusdriverslicenseabbreviations"></a><span data-ttu-id="888cb-3594">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="888cb-3594">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="888cb-3595">通讯</span><span class="sxs-lookup"><span data-stu-id="888cb-3595">DL</span></span> 
- <span data-ttu-id="888cb-3596">DLS</span><span class="sxs-lookup"><span data-stu-id="888cb-3596">DLS</span></span> 
- <span data-ttu-id="888cb-3597">采用</span><span class="sxs-lookup"><span data-stu-id="888cb-3597">CDL</span></span> 
- <span data-ttu-id="888cb-3598">CDLS</span><span class="sxs-lookup"><span data-stu-id="888cb-3598">CDLS</span></span> 
- <span data-ttu-id="888cb-3599">ID</span><span class="sxs-lookup"><span data-stu-id="888cb-3599">ID</span></span> 
- <span data-ttu-id="888cb-3600">id</span><span class="sxs-lookup"><span data-stu-id="888cb-3600">IDs</span></span> 
- <span data-ttu-id="888cb-3601">通讯</span><span class="sxs-lookup"><span data-stu-id="888cb-3601">DL#</span></span> 
- <span data-ttu-id="888cb-3602">DLS</span><span class="sxs-lookup"><span data-stu-id="888cb-3602">DLS#</span></span> 
- <span data-ttu-id="888cb-3603">采用</span><span class="sxs-lookup"><span data-stu-id="888cb-3603">CDL#</span></span> 
- <span data-ttu-id="888cb-3604">CDLS #</span><span class="sxs-lookup"><span data-stu-id="888cb-3604">CDLS#</span></span> 
- <span data-ttu-id="888cb-3605">号</span><span class="sxs-lookup"><span data-stu-id="888cb-3605">ID#</span></span>
- <span data-ttu-id="888cb-3606">id</span><span class="sxs-lookup"><span data-stu-id="888cb-3606">IDs#</span></span> 
- <span data-ttu-id="888cb-3607">ID number</span><span class="sxs-lookup"><span data-stu-id="888cb-3607">ID number</span></span> 
- <span data-ttu-id="888cb-3608">ID numbers</span><span class="sxs-lookup"><span data-stu-id="888cb-3608">ID numbers</span></span> 
- <span data-ttu-id="888cb-3609">.lic</span><span class="sxs-lookup"><span data-stu-id="888cb-3609">LIC</span></span> 
- <span data-ttu-id="888cb-3610">.lic</span><span class="sxs-lookup"><span data-stu-id="888cb-3610">LIC#</span></span> 

#### <a name="keywordusdriverslicense"></a><span data-ttu-id="888cb-3611">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="888cb-3611">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="888cb-3612">DriverLic</span><span class="sxs-lookup"><span data-stu-id="888cb-3612">DriverLic</span></span> 
- <span data-ttu-id="888cb-3613">DriverLics</span><span class="sxs-lookup"><span data-stu-id="888cb-3613">DriverLics</span></span> 
- <span data-ttu-id="888cb-3614">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="888cb-3614">DriverLicense</span></span> 
- <span data-ttu-id="888cb-3615">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="888cb-3615">DriverLicenses</span></span> 
- <span data-ttu-id="888cb-3616">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="888cb-3616">Driver Lic</span></span> 
- <span data-ttu-id="888cb-3617">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="888cb-3617">Driver Lics</span></span> 
- <span data-ttu-id="888cb-3618">Driver License</span><span class="sxs-lookup"><span data-stu-id="888cb-3618">Driver License</span></span> 
- <span data-ttu-id="888cb-3619">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="888cb-3619">Driver Licenses</span></span> 
- <span data-ttu-id="888cb-3620">DriversLic</span><span class="sxs-lookup"><span data-stu-id="888cb-3620">DriversLic</span></span> 
- <span data-ttu-id="888cb-3621">DriversLics</span><span class="sxs-lookup"><span data-stu-id="888cb-3621">DriversLics</span></span> 
- <span data-ttu-id="888cb-3622">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="888cb-3622">DriversLicense</span></span> 
- <span data-ttu-id="888cb-3623">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="888cb-3623">DriversLicenses</span></span> 
- <span data-ttu-id="888cb-3624">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="888cb-3624">Drivers Lic</span></span> 
- <span data-ttu-id="888cb-3625">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="888cb-3625">Drivers Lics</span></span> 
- <span data-ttu-id="888cb-3626">Drivers License</span><span class="sxs-lookup"><span data-stu-id="888cb-3626">Drivers License</span></span> 
- <span data-ttu-id="888cb-3627">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="888cb-3627">Drivers Licenses</span></span> 
- <span data-ttu-id="888cb-3628">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="888cb-3628">Driver'Lic</span></span> 
- <span data-ttu-id="888cb-3629">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="888cb-3629">Driver'Lics</span></span> 
- <span data-ttu-id="888cb-3630">Driver'License</span><span class="sxs-lookup"><span data-stu-id="888cb-3630">Driver'License</span></span> 
- <span data-ttu-id="888cb-3631">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="888cb-3631">Driver'Licenses</span></span> 
- <span data-ttu-id="888cb-3632">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="888cb-3632">Driver' Lic</span></span> 
- <span data-ttu-id="888cb-3633">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="888cb-3633">Driver' Lics</span></span> 
- <span data-ttu-id="888cb-3634">Driver' License</span><span class="sxs-lookup"><span data-stu-id="888cb-3634">Driver' License</span></span> 
- <span data-ttu-id="888cb-3635">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="888cb-3635">Driver' Licenses</span></span>
- <span data-ttu-id="888cb-3636">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="888cb-3636">Driver'sLic</span></span> 
- <span data-ttu-id="888cb-3637">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="888cb-3637">Driver'sLics</span></span> 
- <span data-ttu-id="888cb-3638">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="888cb-3638">Driver'sLicense</span></span> 
- <span data-ttu-id="888cb-3639">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="888cb-3639">Driver'sLicenses</span></span> 
- <span data-ttu-id="888cb-3640">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="888cb-3640">Driver's Lic</span></span> 
- <span data-ttu-id="888cb-3641">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="888cb-3641">Driver's Lics</span></span> 
- <span data-ttu-id="888cb-3642">Driver's License</span><span class="sxs-lookup"><span data-stu-id="888cb-3642">Driver's License</span></span> 
- <span data-ttu-id="888cb-3643">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="888cb-3643">Driver's Licenses</span></span> 
- <span data-ttu-id="888cb-3644">identification number</span><span class="sxs-lookup"><span data-stu-id="888cb-3644">identification number</span></span> 
- <span data-ttu-id="888cb-3645">identification numbers</span><span class="sxs-lookup"><span data-stu-id="888cb-3645">identification numbers</span></span> 
- <span data-ttu-id="888cb-3646">identification #</span><span class="sxs-lookup"><span data-stu-id="888cb-3646">identification #</span></span> 
- <span data-ttu-id="888cb-3647">id card</span><span class="sxs-lookup"><span data-stu-id="888cb-3647">id card</span></span> 
- <span data-ttu-id="888cb-3648">id cards</span><span class="sxs-lookup"><span data-stu-id="888cb-3648">id cards</span></span> 
- <span data-ttu-id="888cb-3649">identification card</span><span class="sxs-lookup"><span data-stu-id="888cb-3649">identification card</span></span> 
- <span data-ttu-id="888cb-3650">identification cards</span><span class="sxs-lookup"><span data-stu-id="888cb-3650">identification cards</span></span> 
- <span data-ttu-id="888cb-3651">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="888cb-3651">DriverLic#</span></span> 
- <span data-ttu-id="888cb-3652">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="888cb-3652">DriverLics#</span></span> 
- <span data-ttu-id="888cb-3653">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="888cb-3653">DriverLicense#</span></span> 
- <span data-ttu-id="888cb-3654">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="888cb-3654">DriverLicenses#</span></span> 
- <span data-ttu-id="888cb-3655">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="888cb-3655">Driver Lic#</span></span> 
- <span data-ttu-id="888cb-3656">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="888cb-3656">Driver Lics#</span></span> 
- <span data-ttu-id="888cb-3657">Driver License#</span><span class="sxs-lookup"><span data-stu-id="888cb-3657">Driver License#</span></span> 
- <span data-ttu-id="888cb-3658">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="888cb-3658">Driver Licenses#</span></span> 
- <span data-ttu-id="888cb-3659">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="888cb-3659">DriversLic#</span></span> 
- <span data-ttu-id="888cb-3660">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="888cb-3660">DriversLics#</span></span> 
- <span data-ttu-id="888cb-3661">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="888cb-3661">DriversLicense#</span></span> 
- <span data-ttu-id="888cb-3662">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="888cb-3662">DriversLicenses#</span></span> 
- <span data-ttu-id="888cb-3663">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="888cb-3663">Drivers Lic#</span></span> 
- <span data-ttu-id="888cb-3664">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="888cb-3664">Drivers Lics#</span></span> 
- <span data-ttu-id="888cb-3665">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="888cb-3665">Drivers License#</span></span> 
- <span data-ttu-id="888cb-3666">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="888cb-3666">Drivers Licenses#</span></span> 
- <span data-ttu-id="888cb-3667">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="888cb-3667">Driver'Lic#</span></span> 
- <span data-ttu-id="888cb-3668">Driver'Lics #</span><span class="sxs-lookup"><span data-stu-id="888cb-3668">Driver'Lics#</span></span> 
- <span data-ttu-id="888cb-3669">Driver'License #</span><span class="sxs-lookup"><span data-stu-id="888cb-3669">Driver'License#</span></span> 
- <span data-ttu-id="888cb-3670">Driver'Licenses #</span><span class="sxs-lookup"><span data-stu-id="888cb-3670">Driver'Licenses#</span></span> 
- <span data-ttu-id="888cb-3671">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="888cb-3671">Driver' Lic#</span></span> 
- <span data-ttu-id="888cb-3672">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="888cb-3672">Driver' Lics#</span></span> 
- <span data-ttu-id="888cb-3673">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="888cb-3673">Driver' License#</span></span> 
- <span data-ttu-id="888cb-3674">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="888cb-3674">Driver' Licenses#</span></span> 
- <span data-ttu-id="888cb-3675">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="888cb-3675">Driver'sLic#</span></span> 
- <span data-ttu-id="888cb-3676">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="888cb-3676">Driver'sLics#</span></span> 
- <span data-ttu-id="888cb-3677">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="888cb-3677">Driver'sLicense#</span></span> 
- <span data-ttu-id="888cb-3678">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="888cb-3678">Driver'sLicenses#</span></span> 
- <span data-ttu-id="888cb-3679">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="888cb-3679">Driver's Lic#</span></span> 
- <span data-ttu-id="888cb-3680">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="888cb-3680">Driver's Lics#</span></span> 
- <span data-ttu-id="888cb-3681">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="888cb-3681">Driver's License#</span></span> 
- <span data-ttu-id="888cb-3682">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="888cb-3682">Driver's Licenses#</span></span> 
- <span data-ttu-id="888cb-3683">id card#</span><span class="sxs-lookup"><span data-stu-id="888cb-3683">id card#</span></span> 
- <span data-ttu-id="888cb-3684">id cards#</span><span class="sxs-lookup"><span data-stu-id="888cb-3684">id cards#</span></span> 
- <span data-ttu-id="888cb-3685">identification card#</span><span class="sxs-lookup"><span data-stu-id="888cb-3685">identification card#</span></span> 
- <span data-ttu-id="888cb-3686">identification cards#</span><span class="sxs-lookup"><span data-stu-id="888cb-3686">identification cards#</span></span> 


#### <a name="keywordstatenamedriverslicensename"></a><span data-ttu-id="888cb-3687">Keyword_ [state_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="888cb-3687">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="888cb-3688">州缩写（例如，“NY”）</span><span class="sxs-lookup"><span data-stu-id="888cb-3688">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="888cb-3689">州名称（例如，“New York”）</span><span class="sxs-lookup"><span data-stu-id="888cb-3689">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="888cb-3690">美国单独的纳税人标识号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="888cb-3690">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="888cb-3691">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-3691">Format</span></span>

<span data-ttu-id="888cb-3692">九个数字，以“9”开头，“7”或“8”作为第四个数字，可以采用空格或短划线格式</span><span class="sxs-lookup"><span data-stu-id="888cb-3692">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-3693">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-3693">Pattern</span></span>

<span data-ttu-id="888cb-3694">格式</span><span class="sxs-lookup"><span data-stu-id="888cb-3694">Formatted:</span></span>
- <span data-ttu-id="888cb-3695">数字“9”</span><span class="sxs-lookup"><span data-stu-id="888cb-3695">The digit "9"</span></span> 
- <span data-ttu-id="888cb-3696">两位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3696">Two digits</span></span> 
- <span data-ttu-id="888cb-3697">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="888cb-3697">A space or dash</span></span> 
- <span data-ttu-id="888cb-3698">“7”或“8”</span><span class="sxs-lookup"><span data-stu-id="888cb-3698">A "7" or "8"</span></span> 
- <span data-ttu-id="888cb-3699">一位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3699">A digit</span></span> 
- <span data-ttu-id="888cb-3700">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="888cb-3700">A space, or dash</span></span> 
- <span data-ttu-id="888cb-3701">四位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3701">Four digits</span></span>

<span data-ttu-id="888cb-3702">纯</span><span class="sxs-lookup"><span data-stu-id="888cb-3702">Unformatted:</span></span>
- <span data-ttu-id="888cb-3703">数字“9”</span><span class="sxs-lookup"><span data-stu-id="888cb-3703">The digit "9"</span></span> 
- <span data-ttu-id="888cb-3704">两位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3704">Two digits</span></span> 
- <span data-ttu-id="888cb-3705">“7”或“8”</span><span class="sxs-lookup"><span data-stu-id="888cb-3705">A "7" or "8"</span></span> 
- <span data-ttu-id="888cb-3706">五位数字</span><span class="sxs-lookup"><span data-stu-id="888cb-3706">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-3707">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-3707">Checksum</span></span>

<span data-ttu-id="888cb-3708">否</span><span class="sxs-lookup"><span data-stu-id="888cb-3708">No</span></span>

### <a name="definition"></a><span data-ttu-id="888cb-3709">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-3709">Definition</span></span>

<span data-ttu-id="888cb-3710">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-3710">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-3711">函数 Func_formatted_itin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3711">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-3712">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="888cb-3712">At least one of the following is true:</span></span>
    - <span data-ttu-id="888cb-3713">找到 Keyword_itin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3713">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="888cb-3714">函数 Func_us_address 找到正确日期格式的地址。</span><span class="sxs-lookup"><span data-stu-id="888cb-3714">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="888cb-3715">函数 Func_us_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="888cb-3715">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="888cb-3716">找到 Keyword_itin_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3716">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="888cb-3717">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-3717">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-3718">函数 Func_unformatted_itin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3718">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-3719">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="888cb-3719">At least one of the following is true:</span></span>
    - <span data-ttu-id="888cb-3720">找到 Keyword_itin_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3720">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="888cb-3721">函数 Func_us_address 找到正确日期格式的地址。</span><span class="sxs-lookup"><span data-stu-id="888cb-3721">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="888cb-3722">函数 Func_us_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="888cb-3722">The function Func_us_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-3723">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-3723">Keywords</span></span>

#### <a name="keyworditin"></a><span data-ttu-id="888cb-3724">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="888cb-3724">Keyword_itin</span></span>

- <span data-ttu-id="888cb-3725">报税</span><span class="sxs-lookup"><span data-stu-id="888cb-3725">taxpayer</span></span> 
- <span data-ttu-id="888cb-3726">tax id</span><span class="sxs-lookup"><span data-stu-id="888cb-3726">tax id</span></span> 
- <span data-ttu-id="888cb-3727">tax identification</span><span class="sxs-lookup"><span data-stu-id="888cb-3727">tax identification</span></span> 
- <span data-ttu-id="888cb-3728">itin</span><span class="sxs-lookup"><span data-stu-id="888cb-3728">itin</span></span> 
- <span data-ttu-id="888cb-3729">ssn</span><span class="sxs-lookup"><span data-stu-id="888cb-3729">ssn</span></span> 
- <span data-ttu-id="888cb-3730">锡</span><span class="sxs-lookup"><span data-stu-id="888cb-3730">tin</span></span> 
- <span data-ttu-id="888cb-3731">social security</span><span class="sxs-lookup"><span data-stu-id="888cb-3731">social security</span></span> 
- <span data-ttu-id="888cb-3732">tax payer</span><span class="sxs-lookup"><span data-stu-id="888cb-3732">tax payer</span></span> 
- <span data-ttu-id="888cb-3733">itins</span><span class="sxs-lookup"><span data-stu-id="888cb-3733">itins</span></span> 
- <span data-ttu-id="888cb-3734">taxid</span><span class="sxs-lookup"><span data-stu-id="888cb-3734">taxid</span></span> 
- <span data-ttu-id="888cb-3735">individual taxpayer</span><span class="sxs-lookup"><span data-stu-id="888cb-3735">individual taxpayer</span></span> 

#### <a name="keyworditincollaborative"></a><span data-ttu-id="888cb-3736">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="888cb-3736">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="888cb-3737">License</span><span class="sxs-lookup"><span data-stu-id="888cb-3737">License</span></span> 
- <span data-ttu-id="888cb-3738">通讯</span><span class="sxs-lookup"><span data-stu-id="888cb-3738">DL</span></span> 
- <span data-ttu-id="888cb-3739">DOB</span><span class="sxs-lookup"><span data-stu-id="888cb-3739">DOB</span></span> 
- <span data-ttu-id="888cb-3740">出生日期</span><span class="sxs-lookup"><span data-stu-id="888cb-3740">Birthdate</span></span> 
- <span data-ttu-id="888cb-3741">生日</span><span class="sxs-lookup"><span data-stu-id="888cb-3741">Birthday</span></span> 
- <span data-ttu-id="888cb-3742">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="888cb-3742">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="888cb-3743">美国社会保险号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="888cb-3743">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="888cb-3744">Format</span><span class="sxs-lookup"><span data-stu-id="888cb-3744">Format</span></span>

<span data-ttu-id="888cb-3745">9 个数字，可以是格式化模式，也可以是非格式化模式</span><span class="sxs-lookup"><span data-stu-id="888cb-3745">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="888cb-3746">如果在 2011 年中旬前发布，则 SSN 具有强格式，即数字的某部分必须介于某个有效的范围中（但是没有校验和）。</span><span class="sxs-lookup"><span data-stu-id="888cb-3746">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="888cb-3747">模式</span><span class="sxs-lookup"><span data-stu-id="888cb-3747">Pattern</span></span>

<span data-ttu-id="888cb-3748">四种不同模式中的 SSN 的四种函数外观：</span><span class="sxs-lookup"><span data-stu-id="888cb-3748">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="888cb-3749">Func_ssn 查找具有 2011 年以前使用短划线或空格格式化的强格式的 SSN（ddd-dd-dddd 或 ddd dd dddd）</span><span class="sxs-lookup"><span data-stu-id="888cb-3749">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="888cb-3750">Func_unformatted_ssn 查找具有 2011 年以前未格式化为 9 个连续数字的强格式的 SSN (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="888cb-3750">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="888cb-3751">Func_randomized_formatted_ssn 查找 2011 年后使用短划线或空格（ddd-dd-dddd 或 ddd dd dddd）格式化的 SSN</span><span class="sxs-lookup"><span data-stu-id="888cb-3751">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="888cb-3752">Func_randomized_unformatted_ssn 查找 2011 年后未格式化为 9 个连续数字 (ddddddddd) 的 SSN</span><span class="sxs-lookup"><span data-stu-id="888cb-3752">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="888cb-3753">校验和</span><span class="sxs-lookup"><span data-stu-id="888cb-3753">Checksum</span></span>

<span data-ttu-id="888cb-3754">否</span><span class="sxs-lookup"><span data-stu-id="888cb-3754">No</span></span>


### <a name="definition"></a><span data-ttu-id="888cb-3755">定义</span><span class="sxs-lookup"><span data-stu-id="888cb-3755">Definition</span></span>

<span data-ttu-id="888cb-3756">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-3756">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-3757">函数 Func_ssn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3757">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-3758">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3758">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="888cb-3759">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-3759">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-3760">函数 Func_unformatted_ssn 查找与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3760">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-3761">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3761">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="888cb-3762">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-3762">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-3763">函数 Func_randomized_formatted_ssn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3763">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-3764">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3764">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="888cb-3765">函数 Func_ssn 未找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3765">The function Func_ssn does not find content that matches the pattern.</span></span>

<span data-ttu-id="888cb-3766">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 55% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="888cb-3766">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="888cb-3767">函数 Func_randomized_unformatted_ssn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3767">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="888cb-3768">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="888cb-3768">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="888cb-3769">函数 Func_unformatted_ssn 未找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="888cb-3769">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="888cb-3770">关键字</span><span class="sxs-lookup"><span data-stu-id="888cb-3770">Keywords</span></span>

#### <a name="keywordssn"></a><span data-ttu-id="888cb-3771">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="888cb-3771">Keyword_ssn</span></span>

- <span data-ttu-id="888cb-3772">Social Security</span><span class="sxs-lookup"><span data-stu-id="888cb-3772">Social Security</span></span> 
- <span data-ttu-id="888cb-3773">Social Security#</span><span class="sxs-lookup"><span data-stu-id="888cb-3773">Social Security#</span></span> 
- <span data-ttu-id="888cb-3774">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="888cb-3774">Soc Sec</span></span> 
- <span data-ttu-id="888cb-3775">SSN</span><span class="sxs-lookup"><span data-stu-id="888cb-3775">SSN</span></span> 
- <span data-ttu-id="888cb-3776">ssn</span><span class="sxs-lookup"><span data-stu-id="888cb-3776">SSNS</span></span> 
- <span data-ttu-id="888cb-3777">SSN</span><span class="sxs-lookup"><span data-stu-id="888cb-3777">SSN#</span></span> 
- <span data-ttu-id="888cb-3778">SS</span><span class="sxs-lookup"><span data-stu-id="888cb-3778">SS#</span></span> 
- <span data-ttu-id="888cb-3779">SSID</span><span class="sxs-lookup"><span data-stu-id="888cb-3779">SSID</span></span> 
   

