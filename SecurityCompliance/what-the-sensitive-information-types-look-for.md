---
title: 使用敏感信息类型查找什么
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
ms.assetid: fd505979-76be-4d9f-b459-abef3fc9e86b
description: Office 365 安全性的数据丢失防护 (DLP)&amp;合规性中心包括可供您可以使用 DLP 策略中的 80 敏感信息类型。本主题列出了所有这些敏感信息类型，并显示 DLP 策略时检测到每种类型的寻找。
ms.openlocfilehash: 064606085363ba9de972511642993277451c8ce3
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525778"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="6a857-104">使用敏感信息类型查找什么</span><span class="sxs-lookup"><span data-stu-id="6a857-104">What the sensitive information types look for</span></span>

<span data-ttu-id="6a857-p102">Office 365 安全性的数据丢失防护 (DLP)&amp;合规性中心包括许多可供您可以使用 DLP 策略中的敏感信息类型。本主题列出了所有这些敏感信息类型，并显示 DLP 策略时检测到每种类型的寻找。敏感信息类型定义的正则表达式或函数可以识别的模式。此外，如关键字和校验和确定证据可以用于标识的敏感信息类型。在评估过程还使用可信度和接近度。</span><span class="sxs-lookup"><span data-stu-id="6a857-p102">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies. This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type. A sensitive information type is defined by a pattern that can be identified by a regular expression or a function. In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type. Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="6a857-110">ABA 银行代号</span><span class="sxs-lookup"><span data-stu-id="6a857-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-111">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-111">Format</span></span>

<span data-ttu-id="6a857-112">9 个数字，可以是格式化模式，也可以是非格式化模式 </span><span class="sxs-lookup"><span data-stu-id="6a857-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-113">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-113">Pattern</span></span>

<span data-ttu-id="6a857-114">有格式模式：</span><span class="sxs-lookup"><span data-stu-id="6a857-114">Formatted:</span></span>
- <span data-ttu-id="6a857-115">四个数字，以 0、 1、 2、 3、 6、 7 或 8 开头</span><span class="sxs-lookup"><span data-stu-id="6a857-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="6a857-116">连字符</span><span class="sxs-lookup"><span data-stu-id="6a857-116">A hyphen</span></span>
- <span data-ttu-id="6a857-117">四位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-117">Four digits</span></span>
- <span data-ttu-id="6a857-118">连字符</span><span class="sxs-lookup"><span data-stu-id="6a857-118">A hyphen</span></span>
- <span data-ttu-id="6a857-119">一位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-119">A digit</span></span>

<span data-ttu-id="6a857-120">未格式化： 9 连续的数字开头 0、 1、 2、 3、 6、 7 或 8</span><span class="sxs-lookup"><span data-stu-id="6a857-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="6a857-121">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-121">Checksum</span></span>

<span data-ttu-id="6a857-122">否</span><span class="sxs-lookup"><span data-stu-id="6a857-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-123">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-123">Definition</span></span>

<span data-ttu-id="6a857-124">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-125">函数 Func_aba_routing 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-126">找到 Keyword_ABA_Routing 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="6a857-127">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-127">Keywords</span></span>

#### <a name="keywordabarouting"></a><span data-ttu-id="6a857-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="6a857-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="6a857-129">aba</span><span class="sxs-lookup"><span data-stu-id="6a857-129">aba</span></span>
- <span data-ttu-id="6a857-130">
aba #</span><span class="sxs-lookup"><span data-stu-id="6a857-130">aba #</span></span>
- <span data-ttu-id="6a857-131">
aba routing #</span><span class="sxs-lookup"><span data-stu-id="6a857-131">aba routing #</span></span>
- <span data-ttu-id="6a857-132">aba 银行代号</span><span class="sxs-lookup"><span data-stu-id="6a857-132">aba routing number</span></span>
- <span data-ttu-id="6a857-133">
aba#</span><span class="sxs-lookup"><span data-stu-id="6a857-133">aba#</span></span>
- <span data-ttu-id="6a857-134">
abarouting#</span><span class="sxs-lookup"><span data-stu-id="6a857-134">abarouting#</span></span>
- <span data-ttu-id="6a857-135">
aba number</span><span class="sxs-lookup"><span data-stu-id="6a857-135">aba number</span></span>
- <span data-ttu-id="6a857-136">
abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="6a857-136">abaroutingnumber</span></span>
- <span data-ttu-id="6a857-137">
american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="6a857-137">american bank association routing #</span></span>
- <span data-ttu-id="6a857-138">
american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="6a857-138">american bank association routing number</span></span>
- <span data-ttu-id="6a857-139">
americanbankassociationrouting#</span><span class="sxs-lookup"><span data-stu-id="6a857-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="6a857-140">
americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="6a857-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="6a857-141">
bank routing number</span><span class="sxs-lookup"><span data-stu-id="6a857-141">bank routing number</span></span>
- <span data-ttu-id="6a857-142">
bankrouting#</span><span class="sxs-lookup"><span data-stu-id="6a857-142">bankrouting#</span></span>
- <span data-ttu-id="6a857-143">
bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="6a857-143">bankroutingnumber</span></span>
- <span data-ttu-id="6a857-144">
routing transit number</span><span class="sxs-lookup"><span data-stu-id="6a857-144">routing transit number</span></span>
- <span data-ttu-id="6a857-145">
RTN
</span><span class="sxs-lookup"><span data-stu-id="6a857-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="6a857-146">阿根廷国家身份证 (DNI) 号</span><span class="sxs-lookup"><span data-stu-id="6a857-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-147">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-147">Format</span></span>

<span data-ttu-id="6a857-148">八个数字，用点分隔</span><span class="sxs-lookup"><span data-stu-id="6a857-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-149">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-149">Pattern</span></span>

<span data-ttu-id="6a857-150">八个数字：</span><span class="sxs-lookup"><span data-stu-id="6a857-150">Eight digits:</span></span>
- <span data-ttu-id="6a857-151">两个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-151">Two digits</span></span>
- <span data-ttu-id="6a857-152">一个点 </span><span class="sxs-lookup"><span data-stu-id="6a857-152">A period</span></span>
- <span data-ttu-id="6a857-153">三个数字 </span><span class="sxs-lookup"><span data-stu-id="6a857-153">Three digits</span></span>
- <span data-ttu-id="6a857-154">一个点 </span><span class="sxs-lookup"><span data-stu-id="6a857-154">A period</span></span>
- <span data-ttu-id="6a857-155">三个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-156">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-156">Checksum</span></span>

<span data-ttu-id="6a857-157">否</span><span class="sxs-lookup"><span data-stu-id="6a857-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-158">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-158">Definition</span></span>

<span data-ttu-id="6a857-159">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-160">正则表达式 Regex_argentina_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-161">找到 Keyword_argentina_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a857-162">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-162">Keywords</span></span>

#### <a name="keywordargentinanationalid"></a><span data-ttu-id="6a857-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="6a857-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="6a857-164">Argentina National Identity number
</span><span class="sxs-lookup"><span data-stu-id="6a857-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="6a857-165">标识</span><span class="sxs-lookup"><span data-stu-id="6a857-165">Identity</span></span> 
- <span data-ttu-id="6a857-166">标识国家/地区身份证</span><span class="sxs-lookup"><span data-stu-id="6a857-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="6a857-167">DNI
</span><span class="sxs-lookup"><span data-stu-id="6a857-167">DNI</span></span> 
- <span data-ttu-id="6a857-168">NIC 的人员的国家/地区注册表</span><span class="sxs-lookup"><span data-stu-id="6a857-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="6a857-169">Documento Nacional de Identidad
</span><span class="sxs-lookup"><span data-stu-id="6a857-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="6a857-170">Registro Nacional de las Personas
</span><span class="sxs-lookup"><span data-stu-id="6a857-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="6a857-171">Identidad
</span><span class="sxs-lookup"><span data-stu-id="6a857-171">Identidad</span></span> 
- <span data-ttu-id="6a857-172">Identificación
</span><span class="sxs-lookup"><span data-stu-id="6a857-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="6a857-173">澳大利亚银行帐号</span><span class="sxs-lookup"><span data-stu-id="6a857-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-174">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-174">Format</span></span>

<span data-ttu-id="6a857-175">6-10 个数字，带或不带 BSB 号码 </span><span class="sxs-lookup"><span data-stu-id="6a857-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-176">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-176">Pattern</span></span>

<span data-ttu-id="6a857-p103">帐号是 6-10 位数字。澳大利亚银行状态分支编号：</span><span class="sxs-lookup"><span data-stu-id="6a857-p103">Account number is 6-10 digits. Australia bank state branch number:</span></span>
- <span data-ttu-id="6a857-179">三位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-179">Three digits</span></span> 
- <span data-ttu-id="6a857-180">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="6a857-180">A hyphen</span></span> 
- <span data-ttu-id="6a857-181">三位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-182">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-182">Checksum</span></span>

<span data-ttu-id="6a857-183">否</span><span class="sxs-lookup"><span data-stu-id="6a857-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-184">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-184">Definition</span></span>

<span data-ttu-id="6a857-185">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-186">正则表达式 Regex_australia_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="6a857-187">找到 Keyword_australia_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="6a857-188">正则表达式 Regex_australia_bank_account_number_bsb 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="6a857-189">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-190">正则表达式 Regex_australia_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="6a857-191">找到 Keyword_australia_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-192">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-192">Keywords</span></span>

#### <a name="keywordaustraliabankaccountnumber"></a><span data-ttu-id="6a857-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="6a857-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="6a857-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="6a857-194">swift bank code</span></span>
- <span data-ttu-id="6a857-195">
correspondent bank</span><span class="sxs-lookup"><span data-stu-id="6a857-195">correspondent bank</span></span>
- <span data-ttu-id="6a857-196">
base currency</span><span class="sxs-lookup"><span data-stu-id="6a857-196">base currency</span></span>
- <span data-ttu-id="6a857-197">
usa account</span><span class="sxs-lookup"><span data-stu-id="6a857-197">usa account</span></span>
- <span data-ttu-id="6a857-198">
holder address</span><span class="sxs-lookup"><span data-stu-id="6a857-198">holder address</span></span>
- <span data-ttu-id="6a857-199">
bank address</span><span class="sxs-lookup"><span data-stu-id="6a857-199">bank address</span></span>
- <span data-ttu-id="6a857-200">
information account</span><span class="sxs-lookup"><span data-stu-id="6a857-200">information account</span></span>
- <span data-ttu-id="6a857-201">
fund transfers</span><span class="sxs-lookup"><span data-stu-id="6a857-201">fund transfers</span></span>
- <span data-ttu-id="6a857-202">
bank charges</span><span class="sxs-lookup"><span data-stu-id="6a857-202">bank charges</span></span>
- <span data-ttu-id="6a857-203">
bank details</span><span class="sxs-lookup"><span data-stu-id="6a857-203">bank details</span></span>
- <span data-ttu-id="6a857-204">
banking information</span><span class="sxs-lookup"><span data-stu-id="6a857-204">banking information</span></span>
- <span data-ttu-id="6a857-205">
full names</span><span class="sxs-lookup"><span data-stu-id="6a857-205">full names</span></span>
- <span data-ttu-id="6a857-206">

iaea</span><span class="sxs-lookup"><span data-stu-id="6a857-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="6a857-207">澳大利亚驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="6a857-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-208">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-208">Format</span></span>

<span data-ttu-id="6a857-209">九个字母和数字</span><span class="sxs-lookup"><span data-stu-id="6a857-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-210">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-210">Pattern</span></span>

<span data-ttu-id="6a857-211">九个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="6a857-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="6a857-212">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="6a857-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="6a857-213">两位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-213">Two digits</span></span> 
- <span data-ttu-id="6a857-214">五位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="6a857-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="6a857-215">或者</span><span class="sxs-lookup"><span data-stu-id="6a857-215">OR</span></span>

- <span data-ttu-id="6a857-216">1-2 个可选字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="6a857-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="6a857-217">4-9 位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-217">4-9 digits</span></span>

<span data-ttu-id="6a857-218">或者</span><span class="sxs-lookup"><span data-stu-id="6a857-218">OR</span></span>

- <span data-ttu-id="6a857-219">九个数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="6a857-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-220">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-220">Checksum</span></span>

<span data-ttu-id="6a857-221">否</span><span class="sxs-lookup"><span data-stu-id="6a857-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-222">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-222">Definition</span></span>

<span data-ttu-id="6a857-223">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-224">正则表达式 Regex_australia_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-225">找到 Keyword_australia_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="6a857-226">未找到 Keyword_australia_drivers_license_number_exclusions 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-227">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-227">Keywords</span></span>

#### <a name="keywordaustraliadriverslicensenumber"></a><span data-ttu-id="6a857-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="6a857-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="6a857-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="6a857-229">international driving permits</span></span>
- <span data-ttu-id="6a857-230">
australian automobile association</span><span class="sxs-lookup"><span data-stu-id="6a857-230">australian automobile association</span></span>
- <span data-ttu-id="6a857-231">
sydney nsw</span><span class="sxs-lookup"><span data-stu-id="6a857-231">sydney nsw</span></span>
- <span data-ttu-id="6a857-232">
international driving permit</span><span class="sxs-lookup"><span data-stu-id="6a857-232">international driving permit</span></span>
- <span data-ttu-id="6a857-233">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="6a857-233">DriverLicence</span></span>
- <span data-ttu-id="6a857-234">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="6a857-234">DriverLicences</span></span>
- <span data-ttu-id="6a857-235">驱动程序 Lic</span><span class="sxs-lookup"><span data-stu-id="6a857-235">Driver Lic</span></span>
- <span data-ttu-id="6a857-236">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="6a857-236">Driver Licence</span></span>
- <span data-ttu-id="6a857-237">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="6a857-237">Driver Licences</span></span>
- <span data-ttu-id="6a857-238">DriversLic</span><span class="sxs-lookup"><span data-stu-id="6a857-238">DriversLic</span></span>
- <span data-ttu-id="6a857-239">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="6a857-239">DriversLicence</span></span>
- <span data-ttu-id="6a857-240">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="6a857-240">DriversLicences</span></span>
- <span data-ttu-id="6a857-241">驱动因素 Lic</span><span class="sxs-lookup"><span data-stu-id="6a857-241">Drivers Lic</span></span>
- <span data-ttu-id="6a857-242">驱动因素 Lics</span><span class="sxs-lookup"><span data-stu-id="6a857-242">Drivers Lics</span></span>
- <span data-ttu-id="6a857-243">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="6a857-243">Drivers Licence</span></span>
- <span data-ttu-id="6a857-244">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="6a857-244">Drivers Licences</span></span>
- <span data-ttu-id="6a857-245">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="6a857-245">Driver'Lic</span></span>
- <span data-ttu-id="6a857-246">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="6a857-246">Driver'Lics</span></span>
- <span data-ttu-id="6a857-247">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="6a857-247">Driver'Licence</span></span>
- <span data-ttu-id="6a857-248">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="6a857-248">Driver'Licences</span></span>
- <span data-ttu-id="6a857-249">驱动因素 Lic</span><span class="sxs-lookup"><span data-stu-id="6a857-249">Driver' Lic</span></span>
- <span data-ttu-id="6a857-250">驱动因素 Lics</span><span class="sxs-lookup"><span data-stu-id="6a857-250">Driver' Lics</span></span>
- <span data-ttu-id="6a857-251">驱动因素许可</span><span class="sxs-lookup"><span data-stu-id="6a857-251">Driver' Licence</span></span>
- <span data-ttu-id="6a857-252">驱动因素许可</span><span class="sxs-lookup"><span data-stu-id="6a857-252">Driver' Licences</span></span>
- <span data-ttu-id="6a857-253">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="6a857-253">Driver'sLic</span></span>
- <span data-ttu-id="6a857-254">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="6a857-254">Driver'sLics</span></span>
- <span data-ttu-id="6a857-255">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="6a857-255">Driver'sLicence</span></span>
- <span data-ttu-id="6a857-256">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="6a857-256">Driver'sLicences</span></span>
- <span data-ttu-id="6a857-257">驱动因素的 Lic</span><span class="sxs-lookup"><span data-stu-id="6a857-257">Driver's Lic</span></span>
- <span data-ttu-id="6a857-258">驱动因素的 Lics</span><span class="sxs-lookup"><span data-stu-id="6a857-258">Driver's Lics</span></span>
- <span data-ttu-id="6a857-259">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="6a857-259">Driver's Licence</span></span>
- <span data-ttu-id="6a857-260">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="6a857-260">Driver's Licences</span></span>
- <span data-ttu-id="6a857-261">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="6a857-261">DriverLic#</span></span>
- <span data-ttu-id="6a857-262">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="6a857-262">DriverLics#</span></span>
- <span data-ttu-id="6a857-263">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="6a857-263">DriverLicence#</span></span>
- <span data-ttu-id="6a857-264">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="6a857-264">DriverLicences#</span></span>
- <span data-ttu-id="6a857-265">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="6a857-265">Driver Lic#</span></span>
- <span data-ttu-id="6a857-266">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="6a857-266">Driver Lics#</span></span>
- <span data-ttu-id="6a857-267">驱动程序许可 #</span><span class="sxs-lookup"><span data-stu-id="6a857-267">Driver Licence#</span></span>
- <span data-ttu-id="6a857-268">驱动程序许可 #</span><span class="sxs-lookup"><span data-stu-id="6a857-268">Driver Licences#</span></span>
- <span data-ttu-id="6a857-269">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="6a857-269">DriversLic#</span></span>
- <span data-ttu-id="6a857-270">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="6a857-270">DriversLics#</span></span>
- <span data-ttu-id="6a857-271">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="6a857-271">DriversLicence#</span></span>
- <span data-ttu-id="6a857-272">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="6a857-272">DriversLicences#</span></span>
- <span data-ttu-id="6a857-273">驱动因素 Lic #</span><span class="sxs-lookup"><span data-stu-id="6a857-273">Drivers Lic#</span></span>
- <span data-ttu-id="6a857-274">驱动因素 Lics #</span><span class="sxs-lookup"><span data-stu-id="6a857-274">Drivers Lics#</span></span>
- <span data-ttu-id="6a857-275">驱动因素许可 #</span><span class="sxs-lookup"><span data-stu-id="6a857-275">Drivers Licence#</span></span>
- <span data-ttu-id="6a857-276">驱动因素许可 #</span><span class="sxs-lookup"><span data-stu-id="6a857-276">Drivers Licences#</span></span>
- <span data-ttu-id="6a857-277">Driver'Lic#
</span><span class="sxs-lookup"><span data-stu-id="6a857-277">Driver'Lic#</span></span>
- <span data-ttu-id="6a857-278">Driver'Lics#
</span><span class="sxs-lookup"><span data-stu-id="6a857-278">Driver'Lics#</span></span>
- <span data-ttu-id="6a857-279">Driver'Licence#
</span><span class="sxs-lookup"><span data-stu-id="6a857-279">Driver'Licence#</span></span>
- <span data-ttu-id="6a857-280">Driver'Licences#
</span><span class="sxs-lookup"><span data-stu-id="6a857-280">Driver'Licences#</span></span>
- <span data-ttu-id="6a857-281">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="6a857-281">Driver' Lic#</span></span>
- <span data-ttu-id="6a857-282">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="6a857-282">Driver' Lics#</span></span>
- <span data-ttu-id="6a857-283">驱动因素许可 #</span><span class="sxs-lookup"><span data-stu-id="6a857-283">Driver' Licence#</span></span>
- <span data-ttu-id="6a857-284">驱动因素许可 #</span><span class="sxs-lookup"><span data-stu-id="6a857-284">Driver' Licences#</span></span>
- <span data-ttu-id="6a857-285">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="6a857-285">Driver'sLic#</span></span>
- <span data-ttu-id="6a857-286">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="6a857-286">Driver'sLics#</span></span>
- <span data-ttu-id="6a857-287">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="6a857-287">Driver'sLicence#</span></span>
- <span data-ttu-id="6a857-288">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="6a857-288">Driver'sLicences#</span></span>
- <span data-ttu-id="6a857-289">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="6a857-289">Driver's Lic#</span></span>
- <span data-ttu-id="6a857-290">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="6a857-290">Driver's Lics#</span></span>
- <span data-ttu-id="6a857-291">驱动程序的许可 #</span><span class="sxs-lookup"><span data-stu-id="6a857-291">Driver's Licence#</span></span>
- <span data-ttu-id="6a857-292">驱动程序的许可 #</span><span class="sxs-lookup"><span data-stu-id="6a857-292">Driver's Licences#</span></span> 

#### <a name="keywordaustraliadriverslicensenumberexclusions"></a><span data-ttu-id="6a857-293">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="6a857-293">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="6a857-294">aaa</span><span class="sxs-lookup"><span data-stu-id="6a857-294">aaa</span></span>
- <span data-ttu-id="6a857-295">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="6a857-295">DriverLicense</span></span>
- <span data-ttu-id="6a857-296">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="6a857-296">DriverLicenses</span></span>
- <span data-ttu-id="6a857-297">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="6a857-297">Driver License</span></span>
- <span data-ttu-id="6a857-298">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="6a857-298">Driver Licenses</span></span>
- <span data-ttu-id="6a857-299">驾驶员</span><span class="sxs-lookup"><span data-stu-id="6a857-299">DriversLicense</span></span>
- <span data-ttu-id="6a857-300">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="6a857-300">DriversLicenses</span></span>
- <span data-ttu-id="6a857-301">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="6a857-301">Drivers License</span></span>
- <span data-ttu-id="6a857-302">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="6a857-302">Drivers Licenses</span></span>
- <span data-ttu-id="6a857-303">Driver'License</span><span class="sxs-lookup"><span data-stu-id="6a857-303">Driver'License</span></span>
- <span data-ttu-id="6a857-304">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="6a857-304">Driver'Licenses</span></span>
- <span data-ttu-id="6a857-305">驱动因素许可证</span><span class="sxs-lookup"><span data-stu-id="6a857-305">Driver' License</span></span>
- <span data-ttu-id="6a857-306">驱动因素许可证</span><span class="sxs-lookup"><span data-stu-id="6a857-306">Driver' Licenses</span></span>
- <span data-ttu-id="6a857-307">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="6a857-307">Driver'sLicense</span></span>
- <span data-ttu-id="6a857-308">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="6a857-308">Driver'sLicenses</span></span>
- <span data-ttu-id="6a857-309">驱动程序的许可证</span><span class="sxs-lookup"><span data-stu-id="6a857-309">Driver's License</span></span>
- <span data-ttu-id="6a857-310">驱动程序的许可证</span><span class="sxs-lookup"><span data-stu-id="6a857-310">Driver's Licenses</span></span>
- <span data-ttu-id="6a857-311">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="6a857-311">DriverLicense#</span></span>
- <span data-ttu-id="6a857-312">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="6a857-312">DriverLicenses#</span></span>
- <span data-ttu-id="6a857-313">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="6a857-313">Driver License#</span></span>
- <span data-ttu-id="6a857-314">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="6a857-314">Driver Licenses#</span></span>
- <span data-ttu-id="6a857-315">驾驶员 #</span><span class="sxs-lookup"><span data-stu-id="6a857-315">DriversLicense#</span></span>
- <span data-ttu-id="6a857-316">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="6a857-316">DriversLicenses#</span></span>
- <span data-ttu-id="6a857-317">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="6a857-317">Drivers License#</span></span>
- <span data-ttu-id="6a857-318">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="6a857-318">Drivers Licenses#</span></span>
- <span data-ttu-id="6a857-319">Driver'License#
</span><span class="sxs-lookup"><span data-stu-id="6a857-319">Driver'License#</span></span>
- <span data-ttu-id="6a857-320">Driver'Licenses#
</span><span class="sxs-lookup"><span data-stu-id="6a857-320">Driver'Licenses#</span></span>
- <span data-ttu-id="6a857-321">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="6a857-321">Driver' License#</span></span>
- <span data-ttu-id="6a857-322">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="6a857-322">Driver' Licenses#</span></span>
- <span data-ttu-id="6a857-323">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="6a857-323">Driver'sLicense#</span></span>
- <span data-ttu-id="6a857-324">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="6a857-324">Driver'sLicenses#</span></span>
- <span data-ttu-id="6a857-325">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="6a857-325">Driver's License#</span></span>
- <span data-ttu-id="6a857-326">

Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="6a857-326">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="6a857-327">澳大利亚医疗帐号</span><span class="sxs-lookup"><span data-stu-id="6a857-327">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-328">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-328">Format</span></span>

<span data-ttu-id="6a857-329">10-11 个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-329">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-330">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-330">Pattern</span></span>

<span data-ttu-id="6a857-331">10-11 个数字：</span><span class="sxs-lookup"><span data-stu-id="6a857-331">10-11 digits:</span></span>
- <span data-ttu-id="6a857-332">第一个数字范围为 2-6</span><span class="sxs-lookup"><span data-stu-id="6a857-332">First digit is in the range 2-6</span></span>
- <span data-ttu-id="6a857-333">第九个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="6a857-333">Ninth digit is a check digit</span></span>
- <span data-ttu-id="6a857-334">第十个数字是问题数字</span><span class="sxs-lookup"><span data-stu-id="6a857-334">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="6a857-335">第十一个数字（可选）是个人号码</span><span class="sxs-lookup"><span data-stu-id="6a857-335">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-336">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-336">Checksum</span></span>

<span data-ttu-id="6a857-337">是</span><span class="sxs-lookup"><span data-stu-id="6a857-337">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-338">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-338">Definition</span></span>

<span data-ttu-id="6a857-339">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-339">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-340">函数 Func_australian_medical_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-340">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-341">找到 Keyword_Australia_Medical_Account_Number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-341">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="6a857-342">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-342">The checksum passes.</span></span>

<span data-ttu-id="6a857-343">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-343">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-344">函数 Func_australian_medical_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-344">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-345">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-345">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-346">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-346">Keywords</span></span>

#### <a name="keywordaustraliamedicalaccountnumber"></a><span data-ttu-id="6a857-347">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="6a857-347">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="6a857-348">bank account details</span><span class="sxs-lookup"><span data-stu-id="6a857-348">bank account details</span></span>
- <span data-ttu-id="6a857-349">
medicare payments</span><span class="sxs-lookup"><span data-stu-id="6a857-349">medicare payments</span></span>
- <span data-ttu-id="6a857-350">
mortgage account</span><span class="sxs-lookup"><span data-stu-id="6a857-350">mortgage account</span></span>
- <span data-ttu-id="6a857-351">
bank payments</span><span class="sxs-lookup"><span data-stu-id="6a857-351">bank payments</span></span>
- <span data-ttu-id="6a857-352">
information branch</span><span class="sxs-lookup"><span data-stu-id="6a857-352">information branch</span></span>
- <span data-ttu-id="6a857-353">
credit card loan</span><span class="sxs-lookup"><span data-stu-id="6a857-353">credit card loan</span></span>
- <span data-ttu-id="6a857-354">
department of human services</span><span class="sxs-lookup"><span data-stu-id="6a857-354">department of human services</span></span>
- <span data-ttu-id="6a857-355">本地服务</span><span class="sxs-lookup"><span data-stu-id="6a857-355">local service</span></span>
- <span data-ttu-id="6a857-356">

medicare</span><span class="sxs-lookup"><span data-stu-id="6a857-356">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="6a857-357">澳大利亚护照号</span><span class="sxs-lookup"><span data-stu-id="6a857-357">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-358">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-358">Format</span></span>

<span data-ttu-id="6a857-359">一个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-359">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-360">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-360">Pattern</span></span>

<span data-ttu-id="6a857-361">一个字母（不区分大小写）后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-361">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-362">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-362">Checksum</span></span>

<span data-ttu-id="6a857-363">否</span><span class="sxs-lookup"><span data-stu-id="6a857-363">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-364">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-364">Definition</span></span>

<span data-ttu-id="6a857-365">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-365">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-366">正则表达式 Regex_australia_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-366">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-367">找到从 Keyword_passport 或 Keyword_australia_passport_number 关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-367">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-368">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-368">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="6a857-369">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="6a857-369">Keyword_passport</span></span>

- <span data-ttu-id="6a857-370">Passport Number</span><span class="sxs-lookup"><span data-stu-id="6a857-370">Passport Number</span></span>
- <span data-ttu-id="6a857-371">
Passport No</span><span class="sxs-lookup"><span data-stu-id="6a857-371">Passport No</span></span>
- <span data-ttu-id="6a857-372">Passport #
</span><span class="sxs-lookup"><span data-stu-id="6a857-372">Passport #</span></span>
- <span data-ttu-id="6a857-373">Passport#
</span><span class="sxs-lookup"><span data-stu-id="6a857-373">Passport#</span></span>
- <span data-ttu-id="6a857-374">PassportID</span><span class="sxs-lookup"><span data-stu-id="6a857-374">PassportID</span></span>
- <span data-ttu-id="6a857-375">Passportno
</span><span class="sxs-lookup"><span data-stu-id="6a857-375">Passportno</span></span>
- <span data-ttu-id="6a857-376">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="6a857-376">passportnumber</span></span>
- <span data-ttu-id="6a857-377">パスポート</span><span class="sxs-lookup"><span data-stu-id="6a857-377">パスポート</span></span>
- <span data-ttu-id="6a857-378">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="6a857-378">パスポート番号</span></span>
- <span data-ttu-id="6a857-379">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="6a857-379">パスポートのNum</span></span>
- <span data-ttu-id="6a857-380">
パスポート ＃
</span><span class="sxs-lookup"><span data-stu-id="6a857-380">パスポート ＃</span></span> 
- <span data-ttu-id="6a857-381">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="6a857-381">Numéro de passeport</span></span>
- <span data-ttu-id="6a857-382">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="6a857-382">Passeport n °</span></span>
- <span data-ttu-id="6a857-383">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="6a857-383">Passeport Non</span></span>
- <span data-ttu-id="6a857-384">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="6a857-384">Passeport #</span></span>
- <span data-ttu-id="6a857-385">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="6a857-385">Passeport#</span></span>
- <span data-ttu-id="6a857-386">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="6a857-386">PasseportNon</span></span>
- <span data-ttu-id="6a857-387">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="6a857-387">Passeportn °</span></span>

#### <a name="keywordaustraliapassportnumber"></a><span data-ttu-id="6a857-388">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="6a857-388">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="6a857-389">passport</span><span class="sxs-lookup"><span data-stu-id="6a857-389">passport</span></span>
- <span data-ttu-id="6a857-390">
passport details</span><span class="sxs-lookup"><span data-stu-id="6a857-390">passport details</span></span>
- <span data-ttu-id="6a857-391">
immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="6a857-391">immigration and citizenship</span></span>
- <span data-ttu-id="6a857-392">
commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="6a857-392">commonwealth of australia</span></span>
- <span data-ttu-id="6a857-393">
department of immigration</span><span class="sxs-lookup"><span data-stu-id="6a857-393">department of immigration</span></span>
- <span data-ttu-id="6a857-394">
residential address</span><span class="sxs-lookup"><span data-stu-id="6a857-394">residential address</span></span>
- <span data-ttu-id="6a857-395">
department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="6a857-395">department of immigration and citizenship</span></span>
- <span data-ttu-id="6a857-396">visa
</span><span class="sxs-lookup"><span data-stu-id="6a857-396">visa</span></span>
- <span data-ttu-id="6a857-397">
national identity card</span><span class="sxs-lookup"><span data-stu-id="6a857-397">national identity card</span></span>
- <span data-ttu-id="6a857-398">护照号码</span><span class="sxs-lookup"><span data-stu-id="6a857-398">passport number</span></span>
- <span data-ttu-id="6a857-399">
travel document</span><span class="sxs-lookup"><span data-stu-id="6a857-399">travel document</span></span>
- <span data-ttu-id="6a857-400">

issuing authority</span><span class="sxs-lookup"><span data-stu-id="6a857-400">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="6a857-401">澳大利亚税号</span><span class="sxs-lookup"><span data-stu-id="6a857-401">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-402">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-402">Format</span></span>

<span data-ttu-id="6a857-403">8-9 个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-403">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-404">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-404">Pattern</span></span>

<span data-ttu-id="6a857-405">通常 8-9 位数字，显示中包含空格，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6a857-405">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="6a857-406">三位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-406">Three digits</span></span> 
- <span data-ttu-id="6a857-407">可选空格</span><span class="sxs-lookup"><span data-stu-id="6a857-407">An optional space</span></span> 
- <span data-ttu-id="6a857-408">三位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-408">Three digits</span></span> 
- <span data-ttu-id="6a857-409">可选空格</span><span class="sxs-lookup"><span data-stu-id="6a857-409">An optional space</span></span> 
- <span data-ttu-id="6a857-410">2-3 位数字，最后一位数字是校验位</span><span class="sxs-lookup"><span data-stu-id="6a857-410">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-411">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-411">Checksum</span></span>

<span data-ttu-id="6a857-412">是</span><span class="sxs-lookup"><span data-stu-id="6a857-412">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-413">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-413">Definition</span></span>

<span data-ttu-id="6a857-414">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-414">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-415">函数 Func_australian_tax_file_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-415">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-416">未找到 Keyword_Australia_Tax_File_Number 或 Keyword_number_exclusions 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-416">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="6a857-417">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-417">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-418">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-418">Keywords</span></span>

#### <a name="keywordaustraliataxfilenumber"></a><span data-ttu-id="6a857-419">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="6a857-419">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="6a857-420">australian business number</span><span class="sxs-lookup"><span data-stu-id="6a857-420">australian business number</span></span>
- <span data-ttu-id="6a857-421">
marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="6a857-421">marginal tax rate</span></span>
- <span data-ttu-id="6a857-422">
medicare levy</span><span class="sxs-lookup"><span data-stu-id="6a857-422">medicare levy</span></span>
- <span data-ttu-id="6a857-423">
portfolio number</span><span class="sxs-lookup"><span data-stu-id="6a857-423">portfolio number</span></span>
- <span data-ttu-id="6a857-424">
service veterans</span><span class="sxs-lookup"><span data-stu-id="6a857-424">service veterans</span></span>
- <span data-ttu-id="6a857-425">
withholding tax</span><span class="sxs-lookup"><span data-stu-id="6a857-425">withholding tax</span></span>
- <span data-ttu-id="6a857-426">
individual tax return</span><span class="sxs-lookup"><span data-stu-id="6a857-426">individual tax return</span></span>
- <span data-ttu-id="6a857-427">

tax file number</span><span class="sxs-lookup"><span data-stu-id="6a857-427">tax file number</span></span>

#### <a name="keywordnumberexclusions"></a><span data-ttu-id="6a857-428">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="6a857-428">Keyword_number_exclusions</span></span>

- <span data-ttu-id="6a857-429">00000000</span><span class="sxs-lookup"><span data-stu-id="6a857-429">00000000</span></span>
- <span data-ttu-id="6a857-430">11111111</span><span class="sxs-lookup"><span data-stu-id="6a857-430">11111111</span></span>
- <span data-ttu-id="6a857-431">22222222</span><span class="sxs-lookup"><span data-stu-id="6a857-431">22222222</span></span>
- <span data-ttu-id="6a857-432">33333333</span><span class="sxs-lookup"><span data-stu-id="6a857-432">33333333</span></span>
- <span data-ttu-id="6a857-433">44444444</span><span class="sxs-lookup"><span data-stu-id="6a857-433">44444444</span></span>
- <span data-ttu-id="6a857-434">55555555</span><span class="sxs-lookup"><span data-stu-id="6a857-434">55555555</span></span>
- <span data-ttu-id="6a857-435">66666666</span><span class="sxs-lookup"><span data-stu-id="6a857-435">66666666</span></span>
- <span data-ttu-id="6a857-436">77777777</span><span class="sxs-lookup"><span data-stu-id="6a857-436">77777777</span></span>
- <span data-ttu-id="6a857-437">88888888</span><span class="sxs-lookup"><span data-stu-id="6a857-437">88888888</span></span>
- <span data-ttu-id="6a857-438">99999999</span><span class="sxs-lookup"><span data-stu-id="6a857-438">99999999</span></span>
- <span data-ttu-id="6a857-439">000000000</span><span class="sxs-lookup"><span data-stu-id="6a857-439">000000000</span></span>
- <span data-ttu-id="6a857-440">111111111</span><span class="sxs-lookup"><span data-stu-id="6a857-440">111111111</span></span>
- <span data-ttu-id="6a857-441">222222222</span><span class="sxs-lookup"><span data-stu-id="6a857-441">222222222</span></span>
- <span data-ttu-id="6a857-442">333333333</span><span class="sxs-lookup"><span data-stu-id="6a857-442">333333333</span></span>
- <span data-ttu-id="6a857-443">444444444</span><span class="sxs-lookup"><span data-stu-id="6a857-443">444444444</span></span>
- <span data-ttu-id="6a857-444">555555555</span><span class="sxs-lookup"><span data-stu-id="6a857-444">555555555</span></span>
- <span data-ttu-id="6a857-445">666666666</span><span class="sxs-lookup"><span data-stu-id="6a857-445">666666666</span></span>
- <span data-ttu-id="6a857-446">777777777</span><span class="sxs-lookup"><span data-stu-id="6a857-446">777777777</span></span>
- <span data-ttu-id="6a857-447">888888888</span><span class="sxs-lookup"><span data-stu-id="6a857-447">888888888</span></span>
- <span data-ttu-id="6a857-448">999999999</span><span class="sxs-lookup"><span data-stu-id="6a857-448">999999999</span></span>
- <span data-ttu-id="6a857-449">0000000000</span><span class="sxs-lookup"><span data-stu-id="6a857-449">0000000000</span></span>
- <span data-ttu-id="6a857-450">1111111111</span><span class="sxs-lookup"><span data-stu-id="6a857-450">1111111111</span></span>
- <span data-ttu-id="6a857-451">2222222222</span><span class="sxs-lookup"><span data-stu-id="6a857-451">2222222222</span></span>
- <span data-ttu-id="6a857-452">3333333333</span><span class="sxs-lookup"><span data-stu-id="6a857-452">3333333333</span></span>
- <span data-ttu-id="6a857-453">4444444444</span><span class="sxs-lookup"><span data-stu-id="6a857-453">4444444444</span></span>
- <span data-ttu-id="6a857-454">5555555555</span><span class="sxs-lookup"><span data-stu-id="6a857-454">5555555555</span></span>
- <span data-ttu-id="6a857-455">6666666666</span><span class="sxs-lookup"><span data-stu-id="6a857-455">6666666666</span></span>
- <span data-ttu-id="6a857-456">7777777777</span><span class="sxs-lookup"><span data-stu-id="6a857-456">7777777777</span></span>
- <span data-ttu-id="6a857-457">8888888888</span><span class="sxs-lookup"><span data-stu-id="6a857-457">8888888888</span></span>
- <span data-ttu-id="6a857-458">9999999999</span><span class="sxs-lookup"><span data-stu-id="6a857-458">9999999999</span></span>
   
## <a name="belgium-national-number"></a><span data-ttu-id="6a857-459">比利时国家号码</span><span class="sxs-lookup"><span data-stu-id="6a857-459">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-460">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-460">Format</span></span>

<span data-ttu-id="6a857-461">11 个数字加分隔符</span><span class="sxs-lookup"><span data-stu-id="6a857-461">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-462">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-462">Pattern</span></span>

<span data-ttu-id="6a857-463">11 个数字加分隔符：</span><span class="sxs-lookup"><span data-stu-id="6a857-463">11 digits plus delimiters:</span></span>
- <span data-ttu-id="6a857-464">六个数字加两个点，采用格式  YY.MM.DD，代表出生日期  </span><span class="sxs-lookup"><span data-stu-id="6a857-464">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="6a857-465">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="6a857-465">A hyphen</span></span> 
- <span data-ttu-id="6a857-466">三个连续的数字（男性用奇数，女性用偶数） </span><span class="sxs-lookup"><span data-stu-id="6a857-466">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="6a857-467">一个点 </span><span class="sxs-lookup"><span data-stu-id="6a857-467">A period</span></span> 
- <span data-ttu-id="6a857-468">两个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="6a857-468">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-469">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-469">Checksum</span></span>

<span data-ttu-id="6a857-470">是</span><span class="sxs-lookup"><span data-stu-id="6a857-470">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-471">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-471">Definition</span></span>

<span data-ttu-id="6a857-472">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-472">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-473">函数 Func_belgium_national_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-473">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-474">找到 Keyword_belgium_national_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-474">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="6a857-475">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-475">The checksum passes.</span></span>

```
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a857-476">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-476">Keywords</span></span>

#### <a name="keywordbelgiumnationalnumber"></a><span data-ttu-id="6a857-477">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="6a857-477">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="6a857-478">Identity</span><span class="sxs-lookup"><span data-stu-id="6a857-478">Identity</span></span>
- <span data-ttu-id="6a857-479">Registration</span><span class="sxs-lookup"><span data-stu-id="6a857-479">Registration</span></span>
- <span data-ttu-id="6a857-480">Identification</span><span class="sxs-lookup"><span data-stu-id="6a857-480">Identification</span></span> 
- <span data-ttu-id="6a857-481">ID</span><span class="sxs-lookup"><span data-stu-id="6a857-481">ID</span></span> 
- <span data-ttu-id="6a857-482">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="6a857-482">Identiteitskaart</span></span>
- <span data-ttu-id="6a857-483">Registratie nummer 
</span><span class="sxs-lookup"><span data-stu-id="6a857-483">Registratie nummer</span></span> 
- <span data-ttu-id="6a857-484">Identificatie nummer
</span><span class="sxs-lookup"><span data-stu-id="6a857-484">Identificatie nummer</span></span> 
- <span data-ttu-id="6a857-485">Identiteit</span><span class="sxs-lookup"><span data-stu-id="6a857-485">Identiteit</span></span>
- <span data-ttu-id="6a857-486">Registratie</span><span class="sxs-lookup"><span data-stu-id="6a857-486">Registratie</span></span>
- <span data-ttu-id="6a857-487">Identificatie

</span><span class="sxs-lookup"><span data-stu-id="6a857-487">Identificatie</span></span> 
- <span data-ttu-id="6a857-488">Carte d’identité
</span><span class="sxs-lookup"><span data-stu-id="6a857-488">Carte d’identité</span></span> 
- <span data-ttu-id="6a857-489">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="6a857-489">numéro d'immatriculation</span></span>
- <span data-ttu-id="6a857-490">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="6a857-490">numéro d'identification</span></span>
- <span data-ttu-id="6a857-491">
identité
</span><span class="sxs-lookup"><span data-stu-id="6a857-491">identité</span></span> 
- <span data-ttu-id="6a857-492">inscription
</span><span class="sxs-lookup"><span data-stu-id="6a857-492">inscription</span></span> 
- <span data-ttu-id="6a857-493">Identifikation</span><span class="sxs-lookup"><span data-stu-id="6a857-493">Identifikation</span></span>
- <span data-ttu-id="6a857-494">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="6a857-494">Identifizierung</span></span>
- <span data-ttu-id="6a857-495">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="6a857-495">Identifikationsnummer</span></span>
- <span data-ttu-id="6a857-496">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="6a857-496">Personalausweis</span></span>
- <span data-ttu-id="6a857-497">Registrierung</span><span class="sxs-lookup"><span data-stu-id="6a857-497">Registrierung</span></span>
- <span data-ttu-id="6a857-498">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="6a857-498">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="6a857-499">巴西 CPF 号码</span><span class="sxs-lookup"><span data-stu-id="6a857-499">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-500">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-500">Format</span></span>

<span data-ttu-id="6a857-501">11 个数字（包括校验位），可以格式化，也可以非格式化</span><span class="sxs-lookup"><span data-stu-id="6a857-501">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-502">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-502">Pattern</span></span>

<span data-ttu-id="6a857-503">有格式模式：</span><span class="sxs-lookup"><span data-stu-id="6a857-503">Formatted:</span></span>
- <span data-ttu-id="6a857-504">三个数字 </span><span class="sxs-lookup"><span data-stu-id="6a857-504">Three digits</span></span> 
- <span data-ttu-id="6a857-505">一个点 </span><span class="sxs-lookup"><span data-stu-id="6a857-505">A period</span></span> 
- <span data-ttu-id="6a857-506">三个数字 </span><span class="sxs-lookup"><span data-stu-id="6a857-506">Three digits</span></span> 
- <span data-ttu-id="6a857-507">一个点 </span><span class="sxs-lookup"><span data-stu-id="6a857-507">A period</span></span> 
- <span data-ttu-id="6a857-508">三个数字 </span><span class="sxs-lookup"><span data-stu-id="6a857-508">Three digits</span></span> 
- <span data-ttu-id="6a857-509">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="6a857-509">A hyphen</span></span> 
- <span data-ttu-id="6a857-510">两个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="6a857-510">Two digits which are check digits</span></span>

<span data-ttu-id="6a857-511">非格式化：</span><span class="sxs-lookup"><span data-stu-id="6a857-511">Unformatted:</span></span>
- <span data-ttu-id="6a857-512">11 个数字，其中最后两个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="6a857-512">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-513">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-513">Checksum</span></span>

<span data-ttu-id="6a857-514">是</span><span class="sxs-lookup"><span data-stu-id="6a857-514">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-515">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-515">Definition</span></span>

<span data-ttu-id="6a857-516">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-516">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-517">函数 Func_brazil_cpf 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-517">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-518">找到 Keyword_brazil_cpf 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-518">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="6a857-519">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-519">The checksum passes.</span></span>

<span data-ttu-id="6a857-520">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-520">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-521">函数 Func_brazil_cpf 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-521">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-522">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-522">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-523">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-523">Keywords</span></span>

#### <a name="keywordbrazilcpf"></a><span data-ttu-id="6a857-524">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="6a857-524">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="6a857-525">CPF</span><span class="sxs-lookup"><span data-stu-id="6a857-525">CPF</span></span>
- <span data-ttu-id="6a857-526">Identification</span><span class="sxs-lookup"><span data-stu-id="6a857-526">Identification</span></span>
- <span data-ttu-id="6a857-527">Registration</span><span class="sxs-lookup"><span data-stu-id="6a857-527">Registration</span></span>
- <span data-ttu-id="6a857-528">Revenue</span><span class="sxs-lookup"><span data-stu-id="6a857-528">Revenue</span></span>
- <span data-ttu-id="6a857-529">Cadastro de Pessoas Físicas
</span><span class="sxs-lookup"><span data-stu-id="6a857-529">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="6a857-530">Imposto
</span><span class="sxs-lookup"><span data-stu-id="6a857-530">Imposto</span></span> 
- <span data-ttu-id="6a857-531">Identificação
</span><span class="sxs-lookup"><span data-stu-id="6a857-531">Identificação</span></span> 
- <span data-ttu-id="6a857-532">Inscrição
</span><span class="sxs-lookup"><span data-stu-id="6a857-532">Inscrição</span></span> 
- <span data-ttu-id="6a857-533">Receita

</span><span class="sxs-lookup"><span data-stu-id="6a857-533">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="6a857-534">巴西法律实体编号 (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="6a857-534">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="6a857-535">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-535">Format</span></span>

<span data-ttu-id="6a857-536">14 个数字（包括注册号、分行号码和校验位），再加上分隔符</span><span class="sxs-lookup"><span data-stu-id="6a857-536">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-537">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-537">Pattern</span></span>
<span data-ttu-id="6a857-538">14 个数字，再加上分隔符：</span><span class="sxs-lookup"><span data-stu-id="6a857-538">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="6a857-539">两个数字 </span><span class="sxs-lookup"><span data-stu-id="6a857-539">Two digits</span></span> 
- <span data-ttu-id="6a857-540">一个点 </span><span class="sxs-lookup"><span data-stu-id="6a857-540">A period</span></span> 
- <span data-ttu-id="6a857-541">三个数字 </span><span class="sxs-lookup"><span data-stu-id="6a857-541">Three digits</span></span> 
- <span data-ttu-id="6a857-542">一个点 </span><span class="sxs-lookup"><span data-stu-id="6a857-542">A period</span></span> 
- <span data-ttu-id="6a857-543">三个数字（前 8 位数是注册号） </span><span class="sxs-lookup"><span data-stu-id="6a857-543">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="6a857-544">正斜杠 </span><span class="sxs-lookup"><span data-stu-id="6a857-544">A forward slash</span></span> 
- <span data-ttu-id="6a857-545">四位分行号码 </span><span class="sxs-lookup"><span data-stu-id="6a857-545">Four-digit branch number</span></span> 
- <span data-ttu-id="6a857-546">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="6a857-546">A hyphen</span></span> 
- <span data-ttu-id="6a857-547">两个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="6a857-547">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-548">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-548">Checksum</span></span>

<span data-ttu-id="6a857-549">是</span><span class="sxs-lookup"><span data-stu-id="6a857-549">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-550">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-550">Definition</span></span>

<span data-ttu-id="6a857-551">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-551">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-552">函数 Func_brazil_cnpj 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-552">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-553">找到 Keyword_brazil_cnpj 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-553">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="6a857-554">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-554">The checksum passes.</span></span>

<span data-ttu-id="6a857-555">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-555">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-556">函数 Func_brazil_cnpj 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-556">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-557">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-557">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-558">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-558">Keywords</span></span>

#### <a name="keywordbrazilcnpj"></a><span data-ttu-id="6a857-559">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="6a857-559">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="6a857-560">CNPJ
</span><span class="sxs-lookup"><span data-stu-id="6a857-560">CNPJ</span></span> 
- <span data-ttu-id="6a857-561">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="6a857-561">CNPJ/MF</span></span> 
- <span data-ttu-id="6a857-562">CNPJ-MF
</span><span class="sxs-lookup"><span data-stu-id="6a857-562">CNPJ-MF</span></span> 
- <span data-ttu-id="6a857-563">National Registry of Legal Entities
</span><span class="sxs-lookup"><span data-stu-id="6a857-563">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="6a857-564">Taxpayers Registry
</span><span class="sxs-lookup"><span data-stu-id="6a857-564">Taxpayers Registry</span></span> 
- <span data-ttu-id="6a857-565">Legal entity
</span><span class="sxs-lookup"><span data-stu-id="6a857-565">Legal entity</span></span> 
- <span data-ttu-id="6a857-566">Legal entities
</span><span class="sxs-lookup"><span data-stu-id="6a857-566">Legal entities</span></span> 
- <span data-ttu-id="6a857-567">Registration Status
</span><span class="sxs-lookup"><span data-stu-id="6a857-567">Registration Status</span></span> 
- <span data-ttu-id="6a857-568">Business
</span><span class="sxs-lookup"><span data-stu-id="6a857-568">Business</span></span> 
- <span data-ttu-id="6a857-569">Company</span><span class="sxs-lookup"><span data-stu-id="6a857-569">Company</span></span>
- <span data-ttu-id="6a857-570">CNPJ
</span><span class="sxs-lookup"><span data-stu-id="6a857-570">CNPJ</span></span> 
- <span data-ttu-id="6a857-571">Cadastro Nacional da Pessoa Jurídica
</span><span class="sxs-lookup"><span data-stu-id="6a857-571">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="6a857-572">Cadastro Geral de Contribuintes
</span><span class="sxs-lookup"><span data-stu-id="6a857-572">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="6a857-573">CGC
</span><span class="sxs-lookup"><span data-stu-id="6a857-573">CGC</span></span> 
- <span data-ttu-id="6a857-574">Pessoa jurídica
</span><span class="sxs-lookup"><span data-stu-id="6a857-574">Pessoa jurídica</span></span> 
- <span data-ttu-id="6a857-575">Pessoas jurídicas
</span><span class="sxs-lookup"><span data-stu-id="6a857-575">Pessoas jurídicas</span></span> 
- <span data-ttu-id="6a857-576">Situação cadastral
</span><span class="sxs-lookup"><span data-stu-id="6a857-576">Situação cadastral</span></span> 
- <span data-ttu-id="6a857-577">Inscrição
</span><span class="sxs-lookup"><span data-stu-id="6a857-577">Inscrição</span></span> 
- <span data-ttu-id="6a857-578">Empresa
</span><span class="sxs-lookup"><span data-stu-id="6a857-578">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="6a857-579">巴西国家身份证 (RG)</span><span class="sxs-lookup"><span data-stu-id="6a857-579">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="6a857-580">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-580">Format</span></span>

<span data-ttu-id="6a857-581">Registro Geral （旧格式）： 九个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-581">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="6a857-582">Registro de Identidade (RIC) （新格式）： 11 位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-582">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-583">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-583">Pattern</span></span>

<span data-ttu-id="6a857-584">Registro Geral（旧格式）：</span><span class="sxs-lookup"><span data-stu-id="6a857-584">Registro Geral (old format):</span></span>
- <span data-ttu-id="6a857-585">两个数字 </span><span class="sxs-lookup"><span data-stu-id="6a857-585">Two digits</span></span> 
- <span data-ttu-id="6a857-586">一个点 </span><span class="sxs-lookup"><span data-stu-id="6a857-586">A period</span></span> 
- <span data-ttu-id="6a857-587">三个数字 </span><span class="sxs-lookup"><span data-stu-id="6a857-587">Three digits</span></span> 
- <span data-ttu-id="6a857-588">一个点 </span><span class="sxs-lookup"><span data-stu-id="6a857-588">A period</span></span> 
- <span data-ttu-id="6a857-589">三个数字 </span><span class="sxs-lookup"><span data-stu-id="6a857-589">Three digits</span></span> 
- <span data-ttu-id="6a857-590">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="6a857-590">A hyphen</span></span> 
- <span data-ttu-id="6a857-591">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="6a857-591">One digit which is a check digit</span></span>

<span data-ttu-id="6a857-592">Registro de Identidade (RIC) （新格式）：</span><span class="sxs-lookup"><span data-stu-id="6a857-592">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="6a857-593">10 个数字 </span><span class="sxs-lookup"><span data-stu-id="6a857-593">10 digits</span></span> 
- <span data-ttu-id="6a857-594">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="6a857-594">A hyphen</span></span> 
- <span data-ttu-id="6a857-595">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="6a857-595">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-596">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-596">Checksum</span></span>

<span data-ttu-id="6a857-597">是</span><span class="sxs-lookup"><span data-stu-id="6a857-597">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-598">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-598">Definition</span></span>

<span data-ttu-id="6a857-599">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-599">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-600">函数 Func_brazil_rg 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-600">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-601">找到 Keyword_brazil_rg 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-601">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="6a857-602">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-602">The checksum passes.</span></span>

<span data-ttu-id="6a857-603">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-603">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-604">函数 Func_brazil_rg 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-604">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-605">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-605">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-606">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-606">Keywords</span></span>

#### <a name="keywordbrazilrg"></a><span data-ttu-id="6a857-607">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="6a857-607">Keyword_brazil_rg</span></span>

<span data-ttu-id="6a857-608">Cédula de identidade 身份证国家/地区 id número de rregistro registro de Iidentidade registro geral RG （此关键字是区分大小写） RIC （此关键字是区分大小写）</span><span class="sxs-lookup"><span data-stu-id="6a857-608">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="6a857-609">加拿大银行帐号</span><span class="sxs-lookup"><span data-stu-id="6a857-609">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-610">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-610">Format</span></span>

<span data-ttu-id="6a857-611">七个或十二个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-611">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-612">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-612">Pattern</span></span>

<span data-ttu-id="6a857-613">加拿大银行帐号是七个或十二个数字。</span><span class="sxs-lookup"><span data-stu-id="6a857-613">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="6a857-614">加拿大银行帐户的银行代号是：</span><span class="sxs-lookup"><span data-stu-id="6a857-614">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="6a857-615">五位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-615">Five digits</span></span> 
- <span data-ttu-id="6a857-616">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="6a857-616">A hyphen</span></span> 
- <span data-ttu-id="6a857-617">三个数字或</span><span class="sxs-lookup"><span data-stu-id="6a857-617">Three digits OR</span></span>
- <span data-ttu-id="6a857-618">一个零“0” </span><span class="sxs-lookup"><span data-stu-id="6a857-618">A zero "0"</span></span> 
- <span data-ttu-id="6a857-619">八个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-619">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-620">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-620">Checksum</span></span>

<span data-ttu-id="6a857-621">否</span><span class="sxs-lookup"><span data-stu-id="6a857-621">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-622">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-622">Definition</span></span>

<span data-ttu-id="6a857-623">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-623">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-624">正则表达式 Regex_canada_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-624">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-625">找到 Keyword_canada_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-625">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="6a857-626">正则表达式 Regex_canada_bank_account_transit_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-626">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="6a857-627">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-627">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-628">正则表达式 Regex_canada_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-628">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-629">找到 Keyword_canada_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-629">A keyword from Keyword_canada_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-630">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-630">Keywords</span></span>

#### <a name="keywordcanadabankaccountnumber"></a><span data-ttu-id="6a857-631">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="6a857-631">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="6a857-632">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="6a857-632">canada savings bonds</span></span>
- <span data-ttu-id="6a857-633">
canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="6a857-633">canada revenue agency</span></span>
- <span data-ttu-id="6a857-634">
canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="6a857-634">canadian financial institution</span></span>
- <span data-ttu-id="6a857-635">
direct deposit form</span><span class="sxs-lookup"><span data-stu-id="6a857-635">direct deposit form</span></span>
- <span data-ttu-id="6a857-636">
canadian citizen</span><span class="sxs-lookup"><span data-stu-id="6a857-636">canadian citizen</span></span>
- <span data-ttu-id="6a857-637">
legal representative</span><span class="sxs-lookup"><span data-stu-id="6a857-637">legal representative</span></span>
- <span data-ttu-id="6a857-638">
notary public</span><span class="sxs-lookup"><span data-stu-id="6a857-638">notary public</span></span>
- <span data-ttu-id="6a857-639">
commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="6a857-639">commissioner for oaths</span></span>
- <span data-ttu-id="6a857-640">
child care benefit</span><span class="sxs-lookup"><span data-stu-id="6a857-640">child care benefit</span></span>
- <span data-ttu-id="6a857-641">
universal child care</span><span class="sxs-lookup"><span data-stu-id="6a857-641">universal child care</span></span>
- <span data-ttu-id="6a857-642">
canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="6a857-642">canada child tax benefit</span></span>
- <span data-ttu-id="6a857-643">
income tax benefit</span><span class="sxs-lookup"><span data-stu-id="6a857-643">income tax benefit</span></span>
- <span data-ttu-id="6a857-644">
harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="6a857-644">harmonized sales tax</span></span>
- <span data-ttu-id="6a857-645">social insurance number</span><span class="sxs-lookup"><span data-stu-id="6a857-645">social insurance number</span></span>
- <span data-ttu-id="6a857-646">
income tax refund</span><span class="sxs-lookup"><span data-stu-id="6a857-646">income tax refund</span></span>
- <span data-ttu-id="6a857-647">
child tax benefit</span><span class="sxs-lookup"><span data-stu-id="6a857-647">child tax benefit</span></span>
- <span data-ttu-id="6a857-648">
territorial payments</span><span class="sxs-lookup"><span data-stu-id="6a857-648">territorial payments</span></span>
- <span data-ttu-id="6a857-649">
institution number</span><span class="sxs-lookup"><span data-stu-id="6a857-649">institution number</span></span>
- <span data-ttu-id="6a857-650">
deposit request</span><span class="sxs-lookup"><span data-stu-id="6a857-650">deposit request</span></span>
- <span data-ttu-id="6a857-651">
banking information</span><span class="sxs-lookup"><span data-stu-id="6a857-651">banking information</span></span>
- <span data-ttu-id="6a857-652">

direct deposit</span><span class="sxs-lookup"><span data-stu-id="6a857-652">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="6a857-653">加拿大驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="6a857-653">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-654">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-654">Format</span></span>

<span data-ttu-id="6a857-655">因省而异</span><span class="sxs-lookup"><span data-stu-id="6a857-655">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-656">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-656">Pattern</span></span>

<span data-ttu-id="6a857-657">各种模式，涵盖艾伯塔、 不列颠哥伦比亚、 马尼托巴、 新不伦瑞克、 纽芬兰/拉布拉多、 新斯科舍、 安大略、 爱德华王子岛，魁北克和萨斯喀彻温</span><span class="sxs-lookup"><span data-stu-id="6a857-657">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-658">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-658">Checksum</span></span>

<span data-ttu-id="6a857-659">否</span><span class="sxs-lookup"><span data-stu-id="6a857-659">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-660">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-660">Definition</span></span>

<span data-ttu-id="6a857-661">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-661">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-662">函数 Func_[province_name]_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-662">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-663">找到 Keyword_[province_name]_drivers_license_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-663">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="6a857-664">找到 Keyword_canada_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-664">A keyword from Keyword_canada_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-665">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-665">Keywords</span></span>

#### <a name="keywordprovincenamedriverslicensename"></a><span data-ttu-id="6a857-666">Keyword_[province_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="6a857-666">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="6a857-667">省/市/自治区的缩写，例如 AB</span><span class="sxs-lookup"><span data-stu-id="6a857-667">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="6a857-668">
省名称，例如 Alberta</span><span class="sxs-lookup"><span data-stu-id="6a857-668">The province name, for example Alberta</span></span>

#### <a name="keywordcanadadriverslicense"></a><span data-ttu-id="6a857-669">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="6a857-669">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="6a857-670">DL</span><span class="sxs-lookup"><span data-stu-id="6a857-670">DL</span></span>
- <span data-ttu-id="6a857-671">DLS</span><span class="sxs-lookup"><span data-stu-id="6a857-671">DLS</span></span>
- <span data-ttu-id="6a857-672">CDL</span><span class="sxs-lookup"><span data-stu-id="6a857-672">CDL</span></span>
- <span data-ttu-id="6a857-673">CDL</span><span class="sxs-lookup"><span data-stu-id="6a857-673">CDLS</span></span>
- <span data-ttu-id="6a857-674">DriverLic</span><span class="sxs-lookup"><span data-stu-id="6a857-674">DriverLic</span></span>
- <span data-ttu-id="6a857-675">DriverLics</span><span class="sxs-lookup"><span data-stu-id="6a857-675">DriverLics</span></span>
- <span data-ttu-id="6a857-676">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="6a857-676">DriverLicense</span></span>
- <span data-ttu-id="6a857-677">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="6a857-677">DriverLicenses</span></span>
- <span data-ttu-id="6a857-678">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="6a857-678">DriverLicence</span></span>
- <span data-ttu-id="6a857-679">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="6a857-679">DriverLicences</span></span>
- <span data-ttu-id="6a857-680">驱动程序 Lic</span><span class="sxs-lookup"><span data-stu-id="6a857-680">Driver Lic</span></span>
- <span data-ttu-id="6a857-681">驱动程序 Lics</span><span class="sxs-lookup"><span data-stu-id="6a857-681">Driver Lics</span></span>
- <span data-ttu-id="6a857-682">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="6a857-682">Driver License</span></span>
- <span data-ttu-id="6a857-683">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="6a857-683">Driver Licenses</span></span>
- <span data-ttu-id="6a857-684">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="6a857-684">Driver Licence</span></span>
- <span data-ttu-id="6a857-685">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="6a857-685">Driver Licences</span></span>
- <span data-ttu-id="6a857-686">DriversLic</span><span class="sxs-lookup"><span data-stu-id="6a857-686">DriversLic</span></span>
- <span data-ttu-id="6a857-687">DriversLics</span><span class="sxs-lookup"><span data-stu-id="6a857-687">DriversLics</span></span>
- <span data-ttu-id="6a857-688">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="6a857-688">DriversLicence</span></span>
- <span data-ttu-id="6a857-689">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="6a857-689">DriversLicences</span></span>
- <span data-ttu-id="6a857-690">驾驶员</span><span class="sxs-lookup"><span data-stu-id="6a857-690">DriversLicense</span></span>
- <span data-ttu-id="6a857-691">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="6a857-691">DriversLicenses</span></span>
- <span data-ttu-id="6a857-692">驱动因素 Lic</span><span class="sxs-lookup"><span data-stu-id="6a857-692">Drivers Lic</span></span>
- <span data-ttu-id="6a857-693">驱动因素 Lics</span><span class="sxs-lookup"><span data-stu-id="6a857-693">Drivers Lics</span></span>
- <span data-ttu-id="6a857-694">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="6a857-694">Drivers License</span></span>
- <span data-ttu-id="6a857-695">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="6a857-695">Drivers Licenses</span></span>
- <span data-ttu-id="6a857-696">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="6a857-696">Drivers Licence</span></span>
- <span data-ttu-id="6a857-697">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="6a857-697">Drivers Licences</span></span>
- <span data-ttu-id="6a857-698">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="6a857-698">Driver'Lic</span></span>
- <span data-ttu-id="6a857-699">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="6a857-699">Driver'Lics</span></span>
- <span data-ttu-id="6a857-700">Driver'License</span><span class="sxs-lookup"><span data-stu-id="6a857-700">Driver'License</span></span>
- <span data-ttu-id="6a857-701">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="6a857-701">Driver'Licenses</span></span>
- <span data-ttu-id="6a857-702">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="6a857-702">Driver'Licence</span></span>
- <span data-ttu-id="6a857-703">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="6a857-703">Driver'Licences</span></span>
- <span data-ttu-id="6a857-704">驱动因素 Lic</span><span class="sxs-lookup"><span data-stu-id="6a857-704">Driver' Lic</span></span>
- <span data-ttu-id="6a857-705">驱动因素 Lics</span><span class="sxs-lookup"><span data-stu-id="6a857-705">Driver' Lics</span></span>
- <span data-ttu-id="6a857-706">驱动因素许可证</span><span class="sxs-lookup"><span data-stu-id="6a857-706">Driver' License</span></span>
- <span data-ttu-id="6a857-707">驱动因素许可证</span><span class="sxs-lookup"><span data-stu-id="6a857-707">Driver' Licenses</span></span>
- <span data-ttu-id="6a857-708">驱动因素许可</span><span class="sxs-lookup"><span data-stu-id="6a857-708">Driver' Licence</span></span>
- <span data-ttu-id="6a857-709">驱动因素许可</span><span class="sxs-lookup"><span data-stu-id="6a857-709">Driver' Licences</span></span>
- <span data-ttu-id="6a857-710">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="6a857-710">Driver'sLic</span></span>
- <span data-ttu-id="6a857-711">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="6a857-711">Driver'sLics</span></span>
- <span data-ttu-id="6a857-712">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="6a857-712">Driver'sLicense</span></span>
- <span data-ttu-id="6a857-713">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="6a857-713">Driver'sLicenses</span></span>
- <span data-ttu-id="6a857-714">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="6a857-714">Driver'sLicence</span></span>
- <span data-ttu-id="6a857-715">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="6a857-715">Driver'sLicences</span></span>
- <span data-ttu-id="6a857-716">驱动因素的 Lic</span><span class="sxs-lookup"><span data-stu-id="6a857-716">Driver's Lic</span></span>
- <span data-ttu-id="6a857-717">驱动因素的 Lics</span><span class="sxs-lookup"><span data-stu-id="6a857-717">Driver's Lics</span></span>
- <span data-ttu-id="6a857-718">驱动程序的许可证</span><span class="sxs-lookup"><span data-stu-id="6a857-718">Driver's License</span></span>
- <span data-ttu-id="6a857-719">驱动程序的许可证</span><span class="sxs-lookup"><span data-stu-id="6a857-719">Driver's Licenses</span></span>
- <span data-ttu-id="6a857-720">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="6a857-720">Driver's Licence</span></span>
- <span data-ttu-id="6a857-721">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="6a857-721">Driver's Licences</span></span>
- <span data-ttu-id="6a857-722">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="6a857-722">Permis de Conduire</span></span>
- <span data-ttu-id="6a857-723">id</span><span class="sxs-lookup"><span data-stu-id="6a857-723">id</span></span>
- <span data-ttu-id="6a857-724">id</span><span class="sxs-lookup"><span data-stu-id="6a857-724">ids</span></span>
- <span data-ttu-id="6a857-725">
idcard number</span><span class="sxs-lookup"><span data-stu-id="6a857-725">idcard number</span></span>
- <span data-ttu-id="6a857-726">
idcard numbers</span><span class="sxs-lookup"><span data-stu-id="6a857-726">idcard numbers</span></span>
- <span data-ttu-id="6a857-727">
idcard #</span><span class="sxs-lookup"><span data-stu-id="6a857-727">idcard #</span></span>
- <span data-ttu-id="6a857-728">
idcard #s</span><span class="sxs-lookup"><span data-stu-id="6a857-728">idcard #s</span></span>
- <span data-ttu-id="6a857-729">idcard 卡片</span><span class="sxs-lookup"><span data-stu-id="6a857-729">idcard card</span></span>
- <span data-ttu-id="6a857-730">idcard 卡</span><span class="sxs-lookup"><span data-stu-id="6a857-730">idcard cards</span></span>
- <span data-ttu-id="6a857-731">idcard</span><span class="sxs-lookup"><span data-stu-id="6a857-731">idcard</span></span>
- <span data-ttu-id="6a857-732">identification number
</span><span class="sxs-lookup"><span data-stu-id="6a857-732">identification number</span></span>
- <span data-ttu-id="6a857-733">identification numbers
</span><span class="sxs-lookup"><span data-stu-id="6a857-733">identification numbers</span></span>
- <span data-ttu-id="6a857-734">identification #
</span><span class="sxs-lookup"><span data-stu-id="6a857-734">identification #</span></span>
- <span data-ttu-id="6a857-735">
identification #s</span><span class="sxs-lookup"><span data-stu-id="6a857-735">identification #s</span></span>
- <span data-ttu-id="6a857-736">身份证</span><span class="sxs-lookup"><span data-stu-id="6a857-736">identification card</span></span>
- <span data-ttu-id="6a857-737">身份证</span><span class="sxs-lookup"><span data-stu-id="6a857-737">identification cards</span></span>
- <span data-ttu-id="6a857-738">
identification
</span><span class="sxs-lookup"><span data-stu-id="6a857-738">identification</span></span> 
- <span data-ttu-id="6a857-739">DL#</span><span class="sxs-lookup"><span data-stu-id="6a857-739">DL#</span></span>
- <span data-ttu-id="6a857-740">
DLS#
</span><span class="sxs-lookup"><span data-stu-id="6a857-740">DLS#</span></span> 
- <span data-ttu-id="6a857-741">CDL#
</span><span class="sxs-lookup"><span data-stu-id="6a857-741">CDL#</span></span> 
- <span data-ttu-id="6a857-742">CDLS#
</span><span class="sxs-lookup"><span data-stu-id="6a857-742">CDLS#</span></span> 
- <span data-ttu-id="6a857-743">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="6a857-743">DriverLic#</span></span> 
- <span data-ttu-id="6a857-744">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="6a857-744">DriverLics#</span></span> 
- <span data-ttu-id="6a857-745">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="6a857-745">DriverLicense#</span></span> 
- <span data-ttu-id="6a857-746">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="6a857-746">DriverLicenses#</span></span> 
- <span data-ttu-id="6a857-747">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="6a857-747">DriverLicence#</span></span> 
- <span data-ttu-id="6a857-748">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="6a857-748">DriverLicences#</span></span> 
- <span data-ttu-id="6a857-749">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="6a857-749">Driver Lic#</span></span>
- <span data-ttu-id="6a857-750">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="6a857-750">Driver Lics#</span></span> 
- <span data-ttu-id="6a857-751">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="6a857-751">Driver License#</span></span> 
- <span data-ttu-id="6a857-752">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="6a857-752">Driver Licenses#</span></span> 
- <span data-ttu-id="6a857-753">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="6a857-753">Driver License#</span></span> 
- <span data-ttu-id="6a857-754">驱动程序许可 #</span><span class="sxs-lookup"><span data-stu-id="6a857-754">Driver Licences#</span></span> 
- <span data-ttu-id="6a857-755">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="6a857-755">DriversLic#</span></span> 
- <span data-ttu-id="6a857-756">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="6a857-756">DriversLics#</span></span> 
- <span data-ttu-id="6a857-757">驾驶员 #</span><span class="sxs-lookup"><span data-stu-id="6a857-757">DriversLicense#</span></span> 
- <span data-ttu-id="6a857-758">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="6a857-758">DriversLicenses#</span></span> 
- <span data-ttu-id="6a857-759">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="6a857-759">DriversLicence#</span></span> 
- <span data-ttu-id="6a857-760">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="6a857-760">DriversLicences#</span></span> 
- <span data-ttu-id="6a857-761">驱动因素 Lic #</span><span class="sxs-lookup"><span data-stu-id="6a857-761">Drivers Lic#</span></span> 
- <span data-ttu-id="6a857-762">驱动因素 Lics #</span><span class="sxs-lookup"><span data-stu-id="6a857-762">Drivers Lics#</span></span> 
- <span data-ttu-id="6a857-763">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="6a857-763">Drivers License#</span></span> 
- <span data-ttu-id="6a857-764">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="6a857-764">Drivers Licenses#</span></span> 
- <span data-ttu-id="6a857-765">驱动因素许可 #</span><span class="sxs-lookup"><span data-stu-id="6a857-765">Drivers Licence#</span></span> 
- <span data-ttu-id="6a857-766">驱动因素许可 #</span><span class="sxs-lookup"><span data-stu-id="6a857-766">Drivers Licences#</span></span> 
- <span data-ttu-id="6a857-767">Driver'Lic#
</span><span class="sxs-lookup"><span data-stu-id="6a857-767">Driver'Lic#</span></span> 
- <span data-ttu-id="6a857-768">Driver'Lics#
</span><span class="sxs-lookup"><span data-stu-id="6a857-768">Driver'Lics#</span></span> 
- <span data-ttu-id="6a857-769">Driver'License#
</span><span class="sxs-lookup"><span data-stu-id="6a857-769">Driver'License#</span></span> 
- <span data-ttu-id="6a857-770">Driver'Licenses#
</span><span class="sxs-lookup"><span data-stu-id="6a857-770">Driver'Licenses#</span></span> 
- <span data-ttu-id="6a857-771">Driver'Licence#
</span><span class="sxs-lookup"><span data-stu-id="6a857-771">Driver'Licence#</span></span> 
- <span data-ttu-id="6a857-772">Driver'Licences#
</span><span class="sxs-lookup"><span data-stu-id="6a857-772">Driver'Licences#</span></span> 
- <span data-ttu-id="6a857-773">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="6a857-773">Driver' Lic#</span></span> 
- <span data-ttu-id="6a857-774">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="6a857-774">Driver' Lics#</span></span> 
- <span data-ttu-id="6a857-775">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="6a857-775">Driver' License#</span></span> 
- <span data-ttu-id="6a857-776">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="6a857-776">Driver' Licenses#</span></span> 
- <span data-ttu-id="6a857-777">驱动因素许可 #</span><span class="sxs-lookup"><span data-stu-id="6a857-777">Driver' Licence#</span></span> 
- <span data-ttu-id="6a857-778">驱动因素许可 #</span><span class="sxs-lookup"><span data-stu-id="6a857-778">Driver' Licences#</span></span> 
- <span data-ttu-id="6a857-779">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="6a857-779">Driver'sLic#</span></span> 
- <span data-ttu-id="6a857-780">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="6a857-780">Driver'sLics#</span></span> 
- <span data-ttu-id="6a857-781">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="6a857-781">Driver'sLicense#</span></span> 
- <span data-ttu-id="6a857-782">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="6a857-782">Driver'sLicenses#</span></span> 
- <span data-ttu-id="6a857-783">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="6a857-783">Driver'sLicence#</span></span> 
- <span data-ttu-id="6a857-784">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="6a857-784">Driver'sLicences#</span></span> 
- <span data-ttu-id="6a857-785">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="6a857-785">Driver's Lic#</span></span> 
- <span data-ttu-id="6a857-786">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="6a857-786">Driver's Lics#</span></span> 
- <span data-ttu-id="6a857-787">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="6a857-787">Driver's License#</span></span> 
- <span data-ttu-id="6a857-788">Driver's Licenses#
</span><span class="sxs-lookup"><span data-stu-id="6a857-788">Driver's Licenses#</span></span> 
- <span data-ttu-id="6a857-789">驱动程序的许可 #</span><span class="sxs-lookup"><span data-stu-id="6a857-789">Driver's Licence#</span></span> 
- <span data-ttu-id="6a857-790">驱动程序的许可 #</span><span class="sxs-lookup"><span data-stu-id="6a857-790">Driver's Licences#</span></span> 
- <span data-ttu-id="6a857-791">Permis de Conduire #</span><span class="sxs-lookup"><span data-stu-id="6a857-791">Permis de Conduire#</span></span> 
- <span data-ttu-id="6a857-792">id #</span><span class="sxs-lookup"><span data-stu-id="6a857-792">id#</span></span> 
- <span data-ttu-id="6a857-793">id #</span><span class="sxs-lookup"><span data-stu-id="6a857-793">ids#</span></span> 
- <span data-ttu-id="6a857-794">idcard card#
</span><span class="sxs-lookup"><span data-stu-id="6a857-794">idcard card#</span></span> 
- <span data-ttu-id="6a857-795">idcard cards#
</span><span class="sxs-lookup"><span data-stu-id="6a857-795">idcard cards#</span></span> 
- <span data-ttu-id="6a857-796">idcard#
</span><span class="sxs-lookup"><span data-stu-id="6a857-796">idcard#</span></span> 
- <span data-ttu-id="6a857-797">identification card#
</span><span class="sxs-lookup"><span data-stu-id="6a857-797">identification card#</span></span> 
- <span data-ttu-id="6a857-798">identification cards#
</span><span class="sxs-lookup"><span data-stu-id="6a857-798">identification cards#</span></span> 
- <span data-ttu-id="6a857-799">identification#
</span><span class="sxs-lookup"><span data-stu-id="6a857-799">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="6a857-800">加拿大卫生服务号</span><span class="sxs-lookup"><span data-stu-id="6a857-800">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-801">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-801">Format</span></span>

<span data-ttu-id="6a857-802">10 个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-802">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-803">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-803">Pattern</span></span>

<span data-ttu-id="6a857-804">10 个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-804">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-805">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-805">Checksum</span></span>

<span data-ttu-id="6a857-806">否</span><span class="sxs-lookup"><span data-stu-id="6a857-806">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-807">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-807">Definition</span></span>

<span data-ttu-id="6a857-808">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-808">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-809">正则表达式 Regex_canada_health_service_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-809">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-810">找到 Keyword_canada_health_service_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-810">A keyword from Keyword_canada_health_service_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-811">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-811">Keywords</span></span>

#### <a name="keywordcanadahealthservicenumber"></a><span data-ttu-id="6a857-812">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="6a857-812">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="6a857-813">personal health number</span><span class="sxs-lookup"><span data-stu-id="6a857-813">personal health number</span></span>
- <span data-ttu-id="6a857-814">
patient information</span><span class="sxs-lookup"><span data-stu-id="6a857-814">patient information</span></span>
- <span data-ttu-id="6a857-815">运行状况服务</span><span class="sxs-lookup"><span data-stu-id="6a857-815">health services</span></span>
- <span data-ttu-id="6a857-816">
speciality services</span><span class="sxs-lookup"><span data-stu-id="6a857-816">speciality services</span></span>
- <span data-ttu-id="6a857-817">
automobile accident</span><span class="sxs-lookup"><span data-stu-id="6a857-817">automobile accident</span></span>
- <span data-ttu-id="6a857-818">
patient hospital</span><span class="sxs-lookup"><span data-stu-id="6a857-818">patient hospital</span></span>
- <span data-ttu-id="6a857-819">
psychiatrist</span><span class="sxs-lookup"><span data-stu-id="6a857-819">psychiatrist</span></span>
- <span data-ttu-id="6a857-820">
workers compensation</span><span class="sxs-lookup"><span data-stu-id="6a857-820">workers compensation</span></span>
- <span data-ttu-id="6a857-821">
disability</span><span class="sxs-lookup"><span data-stu-id="6a857-821">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="6a857-822">加拿大护照号码</span><span class="sxs-lookup"><span data-stu-id="6a857-822">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-823">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-823">Format</span></span>

<span data-ttu-id="6a857-824">两个大写字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-824">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-825">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-825">Pattern</span></span>

<span data-ttu-id="6a857-826">两个大写字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-826">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-827">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-827">Checksum</span></span>

<span data-ttu-id="6a857-828">否</span><span class="sxs-lookup"><span data-stu-id="6a857-828">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-829">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-829">Definition</span></span>

<span data-ttu-id="6a857-830">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-830">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-831">正则表达式 Regex_canada_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-831">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-832">找到从 Keyword_canada_passport_number 或 Keyword_passport 关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-832">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-833">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-833">Keywords</span></span>

#### <a name="keywordcanadapassportnumber"></a><span data-ttu-id="6a857-834">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="6a857-834">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="6a857-835">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="6a857-835">canadian citizenship</span></span>
- <span data-ttu-id="6a857-836">
canadian passport</span><span class="sxs-lookup"><span data-stu-id="6a857-836">canadian passport</span></span>
- <span data-ttu-id="6a857-837">
passport application</span><span class="sxs-lookup"><span data-stu-id="6a857-837">passport application</span></span>
- <span data-ttu-id="6a857-838">
passport photos</span><span class="sxs-lookup"><span data-stu-id="6a857-838">passport photos</span></span>
- <span data-ttu-id="6a857-839">
certified translator</span><span class="sxs-lookup"><span data-stu-id="6a857-839">certified translator</span></span>
- <span data-ttu-id="6a857-840">
canadian citizens</span><span class="sxs-lookup"><span data-stu-id="6a857-840">canadian citizens</span></span>
- <span data-ttu-id="6a857-841">
processing times</span><span class="sxs-lookup"><span data-stu-id="6a857-841">processing times</span></span>
- <span data-ttu-id="6a857-842">

renewal application</span><span class="sxs-lookup"><span data-stu-id="6a857-842">renewal application</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="6a857-843">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="6a857-843">Keyword_passport</span></span>

- <span data-ttu-id="6a857-844">Passport Number</span><span class="sxs-lookup"><span data-stu-id="6a857-844">Passport Number</span></span>
- <span data-ttu-id="6a857-845">
Passport No</span><span class="sxs-lookup"><span data-stu-id="6a857-845">Passport No</span></span>
- <span data-ttu-id="6a857-846">Passport #
</span><span class="sxs-lookup"><span data-stu-id="6a857-846">Passport #</span></span>
- <span data-ttu-id="6a857-847">Passport#
</span><span class="sxs-lookup"><span data-stu-id="6a857-847">Passport#</span></span>
- <span data-ttu-id="6a857-848">PassportID</span><span class="sxs-lookup"><span data-stu-id="6a857-848">PassportID</span></span>
- <span data-ttu-id="6a857-849">Passportno
</span><span class="sxs-lookup"><span data-stu-id="6a857-849">Passportno</span></span>
- <span data-ttu-id="6a857-850">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="6a857-850">passportnumber</span></span>
- <span data-ttu-id="6a857-851">パスポート</span><span class="sxs-lookup"><span data-stu-id="6a857-851">パスポート</span></span>
- <span data-ttu-id="6a857-852">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="6a857-852">パスポート番号</span></span>
- <span data-ttu-id="6a857-853">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="6a857-853">パスポートのNum</span></span>
- <span data-ttu-id="6a857-854">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="6a857-854">パスポート＃</span></span>
- <span data-ttu-id="6a857-855">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="6a857-855">Numéro de passeport</span></span>
- <span data-ttu-id="6a857-856">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="6a857-856">Passeport n °</span></span>
- <span data-ttu-id="6a857-857">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="6a857-857">Passeport Non</span></span>
- <span data-ttu-id="6a857-858">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="6a857-858">Passeport #</span></span>
- <span data-ttu-id="6a857-859">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="6a857-859">Passeport#</span></span>
- <span data-ttu-id="6a857-860">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="6a857-860">PasseportNon</span></span>
- <span data-ttu-id="6a857-861">

Passeportn °</span><span class="sxs-lookup"><span data-stu-id="6a857-861">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="6a857-862">加拿大个人健康标识号 (PHIN)</span><span class="sxs-lookup"><span data-stu-id="6a857-862">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="6a857-863">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-863">Format</span></span>

<span data-ttu-id="6a857-864">九个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-864">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-865">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-865">Pattern</span></span>

<span data-ttu-id="6a857-866">九个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-866">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-867">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-867">Checksum</span></span>

<span data-ttu-id="6a857-868">否</span><span class="sxs-lookup"><span data-stu-id="6a857-868">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-869">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-869">Definition</span></span>

<span data-ttu-id="6a857-p104">DLP 策略是相信它已检测到此类型的敏感信息的 75 %if、 内 300 个字符的邻近度： 正则表达式 Regex_canada_phin 找到与模式匹配的内容。找到来自 Keyword_canada_phin 或 Keyword_canada_provinces 至少两个关键字正在</span><span class="sxs-lookup"><span data-stu-id="6a857-p104">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern. At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-872">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-872">Keywords</span></span>

#### <a name="keywordcanadaphin"></a><span data-ttu-id="6a857-873">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="6a857-873">Keyword_canada_phin</span></span>

- <span data-ttu-id="6a857-874">social insurance number</span><span class="sxs-lookup"><span data-stu-id="6a857-874">social insurance number</span></span>
- <span data-ttu-id="6a857-875">
health information act</span><span class="sxs-lookup"><span data-stu-id="6a857-875">health information act</span></span>
- <span data-ttu-id="6a857-876">
income tax information</span><span class="sxs-lookup"><span data-stu-id="6a857-876">income tax information</span></span>
- <span data-ttu-id="6a857-877">
manitoba health</span><span class="sxs-lookup"><span data-stu-id="6a857-877">manitoba health</span></span>
- <span data-ttu-id="6a857-878">
health registration</span><span class="sxs-lookup"><span data-stu-id="6a857-878">health registration</span></span>
- <span data-ttu-id="6a857-879">
prescription purchases</span><span class="sxs-lookup"><span data-stu-id="6a857-879">prescription purchases</span></span>
- <span data-ttu-id="6a857-880">
benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="6a857-880">benefit eligibility</span></span>
- <span data-ttu-id="6a857-881">
personal health</span><span class="sxs-lookup"><span data-stu-id="6a857-881">personal health</span></span>
- <span data-ttu-id="6a857-882">
power of attorney</span><span class="sxs-lookup"><span data-stu-id="6a857-882">power of attorney</span></span>
- <span data-ttu-id="6a857-883">
registration number</span><span class="sxs-lookup"><span data-stu-id="6a857-883">registration number</span></span>
- <span data-ttu-id="6a857-884">personal health number</span><span class="sxs-lookup"><span data-stu-id="6a857-884">personal health number</span></span>
- <span data-ttu-id="6a857-885">
practitioner referral</span><span class="sxs-lookup"><span data-stu-id="6a857-885">practitioner referral</span></span>
- <span data-ttu-id="6a857-886">
wellness professional</span><span class="sxs-lookup"><span data-stu-id="6a857-886">wellness professional</span></span>
- <span data-ttu-id="6a857-887">
patient referral</span><span class="sxs-lookup"><span data-stu-id="6a857-887">patient referral</span></span>
- <span data-ttu-id="6a857-888">

health and wellness</span><span class="sxs-lookup"><span data-stu-id="6a857-888">health and wellness</span></span>

#### <a name="keywordcanadaprovinces"></a><span data-ttu-id="6a857-889">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="6a857-889">Keyword_canada_provinces</span></span>

- <span data-ttu-id="6a857-890">Nunavut</span><span class="sxs-lookup"><span data-stu-id="6a857-890">Nunavut</span></span>
- <span data-ttu-id="6a857-891">
Quebec</span><span class="sxs-lookup"><span data-stu-id="6a857-891">Quebec</span></span>
- <span data-ttu-id="6a857-892">
Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="6a857-892">Northwest Territories</span></span>
- <span data-ttu-id="6a857-893">
Ontario</span><span class="sxs-lookup"><span data-stu-id="6a857-893">Ontario</span></span>
- <span data-ttu-id="6a857-894">
British Columbia</span><span class="sxs-lookup"><span data-stu-id="6a857-894">British Columbia</span></span>
- <span data-ttu-id="6a857-895">
Alberta</span><span class="sxs-lookup"><span data-stu-id="6a857-895">Alberta</span></span>
- <span data-ttu-id="6a857-896">
Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="6a857-896">Saskatchewan</span></span>
- <span data-ttu-id="6a857-897">
Manitoba</span><span class="sxs-lookup"><span data-stu-id="6a857-897">Manitoba</span></span>
- <span data-ttu-id="6a857-898">
Yukon</span><span class="sxs-lookup"><span data-stu-id="6a857-898">Yukon</span></span>
- <span data-ttu-id="6a857-899">
Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="6a857-899">Newfoundland and Labrador</span></span>
- <span data-ttu-id="6a857-900">
New Brunswick</span><span class="sxs-lookup"><span data-stu-id="6a857-900">New Brunswick</span></span>
- <span data-ttu-id="6a857-901">
Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="6a857-901">Nova Scotia</span></span>
- <span data-ttu-id="6a857-902">
Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="6a857-902">Prince Edward Island</span></span>
- <span data-ttu-id="6a857-903">加拿大</span><span class="sxs-lookup"><span data-stu-id="6a857-903">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="6a857-904">加拿大社会保险号码</span><span class="sxs-lookup"><span data-stu-id="6a857-904">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-905">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-905">Format</span></span>

<span data-ttu-id="6a857-906">九个数字，包含可选连字符或空格</span><span class="sxs-lookup"><span data-stu-id="6a857-906">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-907">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-907">Pattern</span></span>

<span data-ttu-id="6a857-908">有格式模式：</span><span class="sxs-lookup"><span data-stu-id="6a857-908">Formatted:</span></span>
- <span data-ttu-id="6a857-909">三位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-909">Three digits</span></span> 
- <span data-ttu-id="6a857-910">连字符或空格</span><span class="sxs-lookup"><span data-stu-id="6a857-910">A hyphen or space</span></span> 
- <span data-ttu-id="6a857-911">三位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-911">Three digits</span></span> 
- <span data-ttu-id="6a857-912">连字符或空格</span><span class="sxs-lookup"><span data-stu-id="6a857-912">A hyphen or space</span></span> 
- <span data-ttu-id="6a857-913">三位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-913">Three digits</span></span>

<span data-ttu-id="6a857-914">未格式化： 九个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-914">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-915">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-915">Checksum</span></span>

<span data-ttu-id="6a857-916">是</span><span class="sxs-lookup"><span data-stu-id="6a857-916">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-917">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-917">Definition</span></span>

<span data-ttu-id="6a857-918">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-918">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-919">函数 Func_canadian_sin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-919">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-920">至少两个以下任意组合：</span><span class="sxs-lookup"><span data-stu-id="6a857-920">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="6a857-921">找到 Keyword_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-921">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="6a857-922">找到 Keyword_sin_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-922">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="6a857-923">函数 Func_eu_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="6a857-923">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="6a857-924">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-924">The checksum passes.</span></span>

<span data-ttu-id="6a857-925">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-925">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-926">函数 Func_unformatted_canadian_sin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-926">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-927">找到 Keyword_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-927">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="6a857-928">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-928">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-929">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-929">Keywords</span></span>

#### <a name="keywordsin"></a><span data-ttu-id="6a857-930">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="6a857-930">Keyword_sin</span></span>

- <span data-ttu-id="6a857-931">sin</span><span class="sxs-lookup"><span data-stu-id="6a857-931">sin</span></span> 
- <span data-ttu-id="6a857-932">social insurance
</span><span class="sxs-lookup"><span data-stu-id="6a857-932">social insurance</span></span> 
- <span data-ttu-id="6a857-933">numero d'assurance sociale
</span><span class="sxs-lookup"><span data-stu-id="6a857-933">numero d'assurance sociale</span></span> 
- <span data-ttu-id="6a857-934">sins
</span><span class="sxs-lookup"><span data-stu-id="6a857-934">sins</span></span> 
- <span data-ttu-id="6a857-935">ssn</span><span class="sxs-lookup"><span data-stu-id="6a857-935">ssn</span></span> 
- <span data-ttu-id="6a857-936">ssn</span><span class="sxs-lookup"><span data-stu-id="6a857-936">ssns</span></span> 
- <span data-ttu-id="6a857-937">社会安全</span><span class="sxs-lookup"><span data-stu-id="6a857-937">social security</span></span> 
- <span data-ttu-id="6a857-938">numero d'assurance social
</span><span class="sxs-lookup"><span data-stu-id="6a857-938">numero d'assurance social</span></span> 
- <span data-ttu-id="6a857-939">国家/地区标识号</span><span class="sxs-lookup"><span data-stu-id="6a857-939">national identification number</span></span> 
- <span data-ttu-id="6a857-940">
national id</span><span class="sxs-lookup"><span data-stu-id="6a857-940">national id</span></span> 
- <span data-ttu-id="6a857-941">sin#
</span><span class="sxs-lookup"><span data-stu-id="6a857-941">sin#</span></span> 
- <span data-ttu-id="6a857-942">soc ins
</span><span class="sxs-lookup"><span data-stu-id="6a857-942">soc ins</span></span> 
- <span data-ttu-id="6a857-943">social ins
</span><span class="sxs-lookup"><span data-stu-id="6a857-943">social ins</span></span> 

#### <a name="keywordsincollaborative"></a><span data-ttu-id="6a857-944">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="6a857-944">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="6a857-945">driver's license</span><span class="sxs-lookup"><span data-stu-id="6a857-945">driver's license</span></span> 
- <span data-ttu-id="6a857-946">drivers license</span><span class="sxs-lookup"><span data-stu-id="6a857-946">drivers license</span></span> 
- <span data-ttu-id="6a857-947">驱动程序的许可</span><span class="sxs-lookup"><span data-stu-id="6a857-947">driver's licence</span></span> 
- <span data-ttu-id="6a857-948">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6a857-948">drivers licence</span></span> 
- <span data-ttu-id="6a857-949">DOB
</span><span class="sxs-lookup"><span data-stu-id="6a857-949">DOB</span></span> 
- <span data-ttu-id="6a857-950">出生日期</span><span class="sxs-lookup"><span data-stu-id="6a857-950">Birthdate</span></span> 
- <span data-ttu-id="6a857-951">生日 </span><span class="sxs-lookup"><span data-stu-id="6a857-951">Birthday</span></span> 
- <span data-ttu-id="6a857-952">Date of Birth
</span><span class="sxs-lookup"><span data-stu-id="6a857-952">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="6a857-953">	智利身份证号</span><span class="sxs-lookup"><span data-stu-id="6a857-953">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-954">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-954">Format</span></span>

<span data-ttu-id="6a857-955">7-8 数字以及定界符复选数字或字母</span><span class="sxs-lookup"><span data-stu-id="6a857-955">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-956">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-956">Pattern</span></span>

<span data-ttu-id="6a857-957">7-8 个数字加分隔符：</span><span class="sxs-lookup"><span data-stu-id="6a857-957">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="6a857-958">1-2 个数字 </span><span class="sxs-lookup"><span data-stu-id="6a857-958">1-2 digits</span></span> 
- <span data-ttu-id="6a857-959">一个点 </span><span class="sxs-lookup"><span data-stu-id="6a857-959">A period</span></span> 
- <span data-ttu-id="6a857-960">三个数字 </span><span class="sxs-lookup"><span data-stu-id="6a857-960">Three digits</span></span> 
- <span data-ttu-id="6a857-961">一个点 </span><span class="sxs-lookup"><span data-stu-id="6a857-961">A period</span></span> 
- <span data-ttu-id="6a857-962">三个数字 </span><span class="sxs-lookup"><span data-stu-id="6a857-962">Three digits</span></span> 
- <span data-ttu-id="6a857-963">一个短划线 </span><span class="sxs-lookup"><span data-stu-id="6a857-963">A dash</span></span> 
- <span data-ttu-id="6a857-964">一个数字或字母（不区分大小写），是校验位</span><span class="sxs-lookup"><span data-stu-id="6a857-964">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-965">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-965">Checksum</span></span>

<span data-ttu-id="6a857-966">是</span><span class="sxs-lookup"><span data-stu-id="6a857-966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-967">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-967">Definition</span></span>

<span data-ttu-id="6a857-968">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-969">函数 Func_chile_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-969">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-970">找到 Keyword_chile_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-970">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="6a857-971">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-971">The checksum passes.</span></span>

<span data-ttu-id="6a857-972">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-972">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-973">函数 Func_chile_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-973">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-974">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-974">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-975">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-975">Keywords</span></span>

#### <a name="keywordchileidcard"></a><span data-ttu-id="6a857-976">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="6a857-976">Keyword_chile_id_card</span></span>

- <span data-ttu-id="6a857-977">National Identification Number
</span><span class="sxs-lookup"><span data-stu-id="6a857-977">National Identification Number</span></span> 
- <span data-ttu-id="6a857-978">Identity card</span><span class="sxs-lookup"><span data-stu-id="6a857-978">Identity card</span></span> 
- <span data-ttu-id="6a857-979">ID</span><span class="sxs-lookup"><span data-stu-id="6a857-979">ID</span></span> 
- <span data-ttu-id="6a857-980">Identification</span><span class="sxs-lookup"><span data-stu-id="6a857-980">Identification</span></span> 
- <span data-ttu-id="6a857-981">Rol Único Nacional
</span><span class="sxs-lookup"><span data-stu-id="6a857-981">Rol Único Nacional</span></span> 
- <span data-ttu-id="6a857-982">运行</span><span class="sxs-lookup"><span data-stu-id="6a857-982">RUN</span></span> 
- <span data-ttu-id="6a857-983">Rol Único Tributario
</span><span class="sxs-lookup"><span data-stu-id="6a857-983">Rol Único Tributario</span></span> 
- <span data-ttu-id="6a857-984">RUT
</span><span class="sxs-lookup"><span data-stu-id="6a857-984">RUT</span></span> 
- <span data-ttu-id="6a857-985">Cédula de Identidad
</span><span class="sxs-lookup"><span data-stu-id="6a857-985">Cédula de Identidad</span></span> 
- <span data-ttu-id="6a857-986">Número De Identificación Nacional
</span><span class="sxs-lookup"><span data-stu-id="6a857-986">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="6a857-987">Tarjeta de identificación
</span><span class="sxs-lookup"><span data-stu-id="6a857-987">Tarjeta de identificación</span></span> 
- <span data-ttu-id="6a857-988">Identificación
</span><span class="sxs-lookup"><span data-stu-id="6a857-988">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="6a857-989">	中国居民身份证号</span><span class="sxs-lookup"><span data-stu-id="6a857-989">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-990">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-990">Format</span></span>

<span data-ttu-id="6a857-991">18 个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-991">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-992">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-992">Pattern</span></span>

<span data-ttu-id="6a857-993">18 个数字：</span><span class="sxs-lookup"><span data-stu-id="6a857-993">18 digits:</span></span>
- <span data-ttu-id="6a857-994">其中六个数字是地址代码 </span><span class="sxs-lookup"><span data-stu-id="6a857-994">Six digits which are an address code</span></span> 
- <span data-ttu-id="6a857-995">八个数字，采用  YYYYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="6a857-995">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="6a857-996">三个数字，是顺序代码 </span><span class="sxs-lookup"><span data-stu-id="6a857-996">Three digits which are an order code</span></span> 
- <span data-ttu-id="6a857-997">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="6a857-997">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-998">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-998">Checksum</span></span>

<span data-ttu-id="6a857-999">是</span><span class="sxs-lookup"><span data-stu-id="6a857-999">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-1000">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-1000">Definition</span></span>

<span data-ttu-id="6a857-1001">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-1001">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-1002">函数 Func_china_resident_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-1002">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-1003">找到 Keyword_china_resident_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-1003">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="6a857-1004">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-1004">The checksum passes.</span></span>

<span data-ttu-id="6a857-1005">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-1005">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-1006">函数 Func_china_resident_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-1006">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-1007">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-1007">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-1008">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-1008">Keywords</span></span>

### <a name="keywordchinaresidentid"></a><span data-ttu-id="6a857-1009">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="6a857-1009">Keyword_china_resident_id</span></span>

- <span data-ttu-id="6a857-1010">Resident Identity Card
</span><span class="sxs-lookup"><span data-stu-id="6a857-1010">Resident Identity Card</span></span> 
- <span data-ttu-id="6a857-1011">PRC
</span><span class="sxs-lookup"><span data-stu-id="6a857-1011">PRC</span></span> 
- <span data-ttu-id="6a857-1012">National Identification Card
</span><span class="sxs-lookup"><span data-stu-id="6a857-1012">National Identification Card</span></span> 
- <span data-ttu-id="6a857-1013">身份证 </span><span class="sxs-lookup"><span data-stu-id="6a857-1013">身份证</span></span> 
- <span data-ttu-id="6a857-1014">居民 身份证 </span><span class="sxs-lookup"><span data-stu-id="6a857-1014">居民 身份证</span></span> 
- <span data-ttu-id="6a857-1015">居民身份证
</span><span class="sxs-lookup"><span data-stu-id="6a857-1015">居民身份证</span></span> 
- <span data-ttu-id="6a857-1016">鉴定

</span><span class="sxs-lookup"><span data-stu-id="6a857-1016">鉴定</span></span> 
- <span data-ttu-id="6a857-1017">身分證 </span><span class="sxs-lookup"><span data-stu-id="6a857-1017">身分證</span></span> 
- <span data-ttu-id="6a857-1018">居民身份證</span><span class="sxs-lookup"><span data-stu-id="6a857-1018">居民 身份證</span></span>
- <span data-ttu-id="6a857-1019">鑑定 </span><span class="sxs-lookup"><span data-stu-id="6a857-1019">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="6a857-1020">信用卡号</span><span class="sxs-lookup"><span data-stu-id="6a857-1020">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-1021">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-1021">Format</span></span>

<span data-ttu-id="6a857-1022">16 位数字格式化或无格式 (dddddddddddddddd)，必须将传递 Luhn 测试。</span><span class="sxs-lookup"><span data-stu-id="6a857-1022">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-1023">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-1023">Pattern</span></span>

<span data-ttu-id="6a857-1024">非常复杂且强大的模式，检测到来自世界各地所有重要品牌的卡，包括 Visa、万事达卡、发现卡、JCB卡、美国运通卡、礼品卡以及大莱卡。</span><span class="sxs-lookup"><span data-stu-id="6a857-1024">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-1025">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-1025">Checksum</span></span>

<span data-ttu-id="6a857-1026">是，Luhn 校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-1026">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-1027">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-1027">Definition</span></span>

<span data-ttu-id="6a857-1028">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-1028">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-1029">函数 Func_credit_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-1029">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-1030">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="6a857-1030">One of the following is true:</span></span>
    - <span data-ttu-id="6a857-1031">找到 Keyword_cc_verification 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-1031">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="6a857-1032">找到 Keyword_cc_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-1032">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="6a857-1033">函数 Func_expiration_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="6a857-1033">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="6a857-1034">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-1034">The checksum passes.</span></span>

<span data-ttu-id="6a857-1035">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-1035">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-1036">函数 Func_credit_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-1036">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-1037">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-1037">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-1038">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-1038">Keywords</span></span>

#### <a name="keywordccverification"></a><span data-ttu-id="6a857-1039">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="6a857-1039">Keyword_cc_verification</span></span>

- <span data-ttu-id="6a857-1040">card verification</span><span class="sxs-lookup"><span data-stu-id="6a857-1040">card verification</span></span>
- <span data-ttu-id="6a857-1041">card identification number</span><span class="sxs-lookup"><span data-stu-id="6a857-1041">card identification number</span></span>
- <span data-ttu-id="6a857-1042">cvn
</span><span class="sxs-lookup"><span data-stu-id="6a857-1042">cvn</span></span>
- <span data-ttu-id="6a857-1043">cid
</span><span class="sxs-lookup"><span data-stu-id="6a857-1043">cid</span></span>
- <span data-ttu-id="6a857-1044">cvc2</span><span class="sxs-lookup"><span data-stu-id="6a857-1044">cvc2</span></span>
- <span data-ttu-id="6a857-1045">cvv2</span><span class="sxs-lookup"><span data-stu-id="6a857-1045">cvv2</span></span>
- <span data-ttu-id="6a857-1046">pin block
</span><span class="sxs-lookup"><span data-stu-id="6a857-1046">pin block</span></span>
- <span data-ttu-id="6a857-1047">security code
</span><span class="sxs-lookup"><span data-stu-id="6a857-1047">security code</span></span>
- <span data-ttu-id="6a857-1048">security number
</span><span class="sxs-lookup"><span data-stu-id="6a857-1048">security number</span></span>
- <span data-ttu-id="6a857-1049">security no
</span><span class="sxs-lookup"><span data-stu-id="6a857-1049">security no</span></span>
- <span data-ttu-id="6a857-1050">issue number
</span><span class="sxs-lookup"><span data-stu-id="6a857-1050">issue number</span></span>
- <span data-ttu-id="6a857-1051">issue no
</span><span class="sxs-lookup"><span data-stu-id="6a857-1051">issue no</span></span>
- <span data-ttu-id="6a857-1052">cryptogramme
</span><span class="sxs-lookup"><span data-stu-id="6a857-1052">cryptogramme</span></span>
- <span data-ttu-id="6a857-1053">numéro de sécurité
</span><span class="sxs-lookup"><span data-stu-id="6a857-1053">numéro de sécurité</span></span>
- <span data-ttu-id="6a857-1054">numero de securite
</span><span class="sxs-lookup"><span data-stu-id="6a857-1054">numero de securite</span></span>
- <span data-ttu-id="6a857-1055">kreditkartenprüfnummer
</span><span class="sxs-lookup"><span data-stu-id="6a857-1055">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="6a857-1056">kreditkartenprufnummer
</span><span class="sxs-lookup"><span data-stu-id="6a857-1056">kreditkartenprufnummer</span></span>
- <span data-ttu-id="6a857-1057">prüfziffer
</span><span class="sxs-lookup"><span data-stu-id="6a857-1057">prüfziffer</span></span>
- <span data-ttu-id="6a857-1058">prufziffer
</span><span class="sxs-lookup"><span data-stu-id="6a857-1058">prufziffer</span></span>
- <span data-ttu-id="6a857-1059">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="6a857-1059">sicherheits Kode</span></span>
- <span data-ttu-id="6a857-1060">sicherheitscode
</span><span class="sxs-lookup"><span data-stu-id="6a857-1060">sicherheitscode</span></span>
- <span data-ttu-id="6a857-1061">sicherheitsnummer
</span><span class="sxs-lookup"><span data-stu-id="6a857-1061">sicherheitsnummer</span></span>
- <span data-ttu-id="6a857-1062">verfalldatum
</span><span class="sxs-lookup"><span data-stu-id="6a857-1062">verfalldatum</span></span>
- <span data-ttu-id="6a857-1063">codice di verifica
</span><span class="sxs-lookup"><span data-stu-id="6a857-1063">codice di verifica</span></span>
- <span data-ttu-id="6a857-p105">cod. sicurezza
</span><span class="sxs-lookup"><span data-stu-id="6a857-p105">cod. sicurezza</span></span>
- <span data-ttu-id="6a857-1066">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="6a857-1066">cod sicurezza</span></span>
- <span data-ttu-id="6a857-1067">
n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="6a857-1067">n autorizzazione</span></span>
- <span data-ttu-id="6a857-1068">código
</span><span class="sxs-lookup"><span data-stu-id="6a857-1068">código</span></span>
- <span data-ttu-id="6a857-1069">codigo
</span><span class="sxs-lookup"><span data-stu-id="6a857-1069">codigo</span></span>
- <span data-ttu-id="6a857-p106">cod. seg
</span><span class="sxs-lookup"><span data-stu-id="6a857-p106">cod. seg</span></span>
- <span data-ttu-id="6a857-1072">cod seg</span><span class="sxs-lookup"><span data-stu-id="6a857-1072">cod seg</span></span>
- <span data-ttu-id="6a857-1073">código de segurança
</span><span class="sxs-lookup"><span data-stu-id="6a857-1073">código de segurança</span></span>
- <span data-ttu-id="6a857-1074">codigo de seguranca
</span><span class="sxs-lookup"><span data-stu-id="6a857-1074">codigo de seguranca</span></span>
- <span data-ttu-id="6a857-1075">codigo de segurança
</span><span class="sxs-lookup"><span data-stu-id="6a857-1075">codigo de segurança</span></span>
- <span data-ttu-id="6a857-1076">código de seguranca
</span><span class="sxs-lookup"><span data-stu-id="6a857-1076">código de seguranca</span></span>
- <span data-ttu-id="6a857-p107">cód. segurança
</span><span class="sxs-lookup"><span data-stu-id="6a857-p107">cód. segurança</span></span>
- <span data-ttu-id="6a857-p108">cod。seguranca cod。segurança</span><span class="sxs-lookup"><span data-stu-id="6a857-p108">cod. seguranca cod. segurança</span></span>
- <span data-ttu-id="6a857-p109">cód. seguranca
</span><span class="sxs-lookup"><span data-stu-id="6a857-p109">cód. seguranca</span></span>
- <span data-ttu-id="6a857-1084">cód segurança</span><span class="sxs-lookup"><span data-stu-id="6a857-1084">cód segurança</span></span>
- <span data-ttu-id="6a857-1085">货 seguranca cod segurança 到付款</span><span class="sxs-lookup"><span data-stu-id="6a857-1085">cod seguranca cod segurança</span></span>
- <span data-ttu-id="6a857-1086">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="6a857-1086">cód seguranca</span></span>
- <span data-ttu-id="6a857-1087">número de verificação
</span><span class="sxs-lookup"><span data-stu-id="6a857-1087">número de verificação</span></span>
- <span data-ttu-id="6a857-1088">numero de verificacao
</span><span class="sxs-lookup"><span data-stu-id="6a857-1088">numero de verificacao</span></span>
- <span data-ttu-id="6a857-1089">ablauf
</span><span class="sxs-lookup"><span data-stu-id="6a857-1089">ablauf</span></span>
- <span data-ttu-id="6a857-1090">gültig bis
</span><span class="sxs-lookup"><span data-stu-id="6a857-1090">gültig bis</span></span>
- <span data-ttu-id="6a857-1091">gültigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="6a857-1091">gültigkeitsdatum</span></span>
- <span data-ttu-id="6a857-1092">gultig bis
</span><span class="sxs-lookup"><span data-stu-id="6a857-1092">gultig bis</span></span>
- <span data-ttu-id="6a857-1093">gultigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="6a857-1093">gultigkeitsdatum</span></span>
- <span data-ttu-id="6a857-1094">scadenza
</span><span class="sxs-lookup"><span data-stu-id="6a857-1094">scadenza</span></span>
- <span data-ttu-id="6a857-1095">data scad
</span><span class="sxs-lookup"><span data-stu-id="6a857-1095">data scad</span></span>
- <span data-ttu-id="6a857-1096">fecha de expiracion
</span><span class="sxs-lookup"><span data-stu-id="6a857-1096">fecha de expiracion</span></span>
- <span data-ttu-id="6a857-1097">fecha de venc
</span><span class="sxs-lookup"><span data-stu-id="6a857-1097">fecha de venc</span></span>
- <span data-ttu-id="6a857-1098">vencimiento
</span><span class="sxs-lookup"><span data-stu-id="6a857-1098">vencimiento</span></span>
- <span data-ttu-id="6a857-1099">válido hasta
</span><span class="sxs-lookup"><span data-stu-id="6a857-1099">válido hasta</span></span>
- <span data-ttu-id="6a857-1100">valido hasta
</span><span class="sxs-lookup"><span data-stu-id="6a857-1100">valido hasta</span></span>
- <span data-ttu-id="6a857-1101">vto
</span><span class="sxs-lookup"><span data-stu-id="6a857-1101">vto</span></span>
- <span data-ttu-id="6a857-1102">data de expiração
</span><span class="sxs-lookup"><span data-stu-id="6a857-1102">data de expiração</span></span>
- <span data-ttu-id="6a857-1103">data de expiracao
</span><span class="sxs-lookup"><span data-stu-id="6a857-1103">data de expiracao</span></span>
- <span data-ttu-id="6a857-1104">data em que expira
</span><span class="sxs-lookup"><span data-stu-id="6a857-1104">data em que expira</span></span>
- <span data-ttu-id="6a857-1105">validade
</span><span class="sxs-lookup"><span data-stu-id="6a857-1105">validade</span></span>
- <span data-ttu-id="6a857-1106">valor
</span><span class="sxs-lookup"><span data-stu-id="6a857-1106">valor</span></span>
- <span data-ttu-id="6a857-1107">vencimento
</span><span class="sxs-lookup"><span data-stu-id="6a857-1107">vencimento</span></span>
- <span data-ttu-id="6a857-1108">Venc</span><span class="sxs-lookup"><span data-stu-id="6a857-1108">Venc</span></span> 

#### <a name="keywordccname"></a><span data-ttu-id="6a857-1109">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="6a857-1109">Keyword_cc_name</span></span>

- <span data-ttu-id="6a857-1110">amex</span><span class="sxs-lookup"><span data-stu-id="6a857-1110">amex</span></span>
- <span data-ttu-id="6a857-1111">
american express</span><span class="sxs-lookup"><span data-stu-id="6a857-1111">american express</span></span>
- <span data-ttu-id="6a857-1112">americanexpress
</span><span class="sxs-lookup"><span data-stu-id="6a857-1112">americanexpress</span></span>
- <span data-ttu-id="6a857-1113">Visa</span><span class="sxs-lookup"><span data-stu-id="6a857-1113">Visa</span></span>
- <span data-ttu-id="6a857-1114">mastercard
</span><span class="sxs-lookup"><span data-stu-id="6a857-1114">mastercard</span></span>
- <span data-ttu-id="6a857-1115">Master Card
</span><span class="sxs-lookup"><span data-stu-id="6a857-1115">master card</span></span>
- <span data-ttu-id="6a857-1116">
mc
</span><span class="sxs-lookup"><span data-stu-id="6a857-1116">mc</span></span> 
- <span data-ttu-id="6a857-1117">mastercards</span><span class="sxs-lookup"><span data-stu-id="6a857-1117">mastercards</span></span>
- <span data-ttu-id="6a857-1118">
master cards</span><span class="sxs-lookup"><span data-stu-id="6a857-1118">master cards</span></span>
- <span data-ttu-id="6a857-1119">进餐的俱乐部</span><span class="sxs-lookup"><span data-stu-id="6a857-1119">diner's Club</span></span>
- <span data-ttu-id="6a857-1120">diners club
</span><span class="sxs-lookup"><span data-stu-id="6a857-1120">diners club</span></span>
- <span data-ttu-id="6a857-1121">dinersclub
</span><span class="sxs-lookup"><span data-stu-id="6a857-1121">dinersclub</span></span>
- <span data-ttu-id="6a857-1122">discover card
</span><span class="sxs-lookup"><span data-stu-id="6a857-1122">discover card</span></span>
- <span data-ttu-id="6a857-1123">discovercard
</span><span class="sxs-lookup"><span data-stu-id="6a857-1123">discovercard</span></span>
- <span data-ttu-id="6a857-1124">discover cards
</span><span class="sxs-lookup"><span data-stu-id="6a857-1124">discover cards</span></span>
- <span data-ttu-id="6a857-1125">JCB</span><span class="sxs-lookup"><span data-stu-id="6a857-1125">JCB</span></span>
- <span data-ttu-id="6a857-1126">japanese card bureau
</span><span class="sxs-lookup"><span data-stu-id="6a857-1126">japanese card bureau</span></span>
- <span data-ttu-id="6a857-1127">carte blanche
</span><span class="sxs-lookup"><span data-stu-id="6a857-1127">carte blanche</span></span>
- <span data-ttu-id="6a857-1128">carteblanche
</span><span class="sxs-lookup"><span data-stu-id="6a857-1128">carteblanche</span></span>
- <span data-ttu-id="6a857-1129">credit card
</span><span class="sxs-lookup"><span data-stu-id="6a857-1129">credit card</span></span>
- <span data-ttu-id="6a857-1130">抄送 #</span><span class="sxs-lookup"><span data-stu-id="6a857-1130">cc#</span></span>
- <span data-ttu-id="6a857-1131">抄送 # 中：</span><span class="sxs-lookup"><span data-stu-id="6a857-1131">cc#:</span></span>
- <span data-ttu-id="6a857-1132">
expiration date</span><span class="sxs-lookup"><span data-stu-id="6a857-1132">expiration date</span></span>
- <span data-ttu-id="6a857-1133">exp date
</span><span class="sxs-lookup"><span data-stu-id="6a857-1133">exp date</span></span>
- <span data-ttu-id="6a857-1134">
expiry date</span><span class="sxs-lookup"><span data-stu-id="6a857-1134">expiry date</span></span>
- <span data-ttu-id="6a857-1135">
date d’expiration</span><span class="sxs-lookup"><span data-stu-id="6a857-1135">date d’expiration</span></span>
- <span data-ttu-id="6a857-1136">
date d'exp</span><span class="sxs-lookup"><span data-stu-id="6a857-1136">date d'exp</span></span>
- <span data-ttu-id="6a857-1137">
date expiration</span><span class="sxs-lookup"><span data-stu-id="6a857-1137">date expiration</span></span>
- <span data-ttu-id="6a857-1138">bank card
</span><span class="sxs-lookup"><span data-stu-id="6a857-1138">bank card</span></span>
- <span data-ttu-id="6a857-1139">
bankcard</span><span class="sxs-lookup"><span data-stu-id="6a857-1139">bankcard</span></span>
- <span data-ttu-id="6a857-1140">card number
</span><span class="sxs-lookup"><span data-stu-id="6a857-1140">card number</span></span>
- <span data-ttu-id="6a857-1141">card num
</span><span class="sxs-lookup"><span data-stu-id="6a857-1141">card num</span></span>
- <span data-ttu-id="6a857-1142">cardnumber
</span><span class="sxs-lookup"><span data-stu-id="6a857-1142">cardnumber</span></span>
- <span data-ttu-id="6a857-1143">cardnumbers
</span><span class="sxs-lookup"><span data-stu-id="6a857-1143">cardnumbers</span></span>
- <span data-ttu-id="6a857-1144">card numbers
</span><span class="sxs-lookup"><span data-stu-id="6a857-1144">card numbers</span></span>
- <span data-ttu-id="6a857-1145">creditcard
</span><span class="sxs-lookup"><span data-stu-id="6a857-1145">creditcard</span></span>
- <span data-ttu-id="6a857-1146">credit cards
</span><span class="sxs-lookup"><span data-stu-id="6a857-1146">credit cards</span></span>
- <span data-ttu-id="6a857-1147">creditcards
</span><span class="sxs-lookup"><span data-stu-id="6a857-1147">creditcards</span></span>
- <span data-ttu-id="6a857-1148">ccn
</span><span class="sxs-lookup"><span data-stu-id="6a857-1148">ccn</span></span>
- <span data-ttu-id="6a857-1149">card holder
</span><span class="sxs-lookup"><span data-stu-id="6a857-1149">card holder</span></span>
- <span data-ttu-id="6a857-1150">cardholder
</span><span class="sxs-lookup"><span data-stu-id="6a857-1150">cardholder</span></span>
- <span data-ttu-id="6a857-1151">card holders
</span><span class="sxs-lookup"><span data-stu-id="6a857-1151">card holders</span></span>
- <span data-ttu-id="6a857-1152">cardholders
</span><span class="sxs-lookup"><span data-stu-id="6a857-1152">cardholders</span></span>
- <span data-ttu-id="6a857-1153">check card
</span><span class="sxs-lookup"><span data-stu-id="6a857-1153">check card</span></span>
- <span data-ttu-id="6a857-1154">checkcard
</span><span class="sxs-lookup"><span data-stu-id="6a857-1154">checkcard</span></span>
- <span data-ttu-id="6a857-1155">check cards
</span><span class="sxs-lookup"><span data-stu-id="6a857-1155">check cards</span></span>
- <span data-ttu-id="6a857-1156">checkcards
</span><span class="sxs-lookup"><span data-stu-id="6a857-1156">checkcards</span></span>
- <span data-ttu-id="6a857-1157">debit card
</span><span class="sxs-lookup"><span data-stu-id="6a857-1157">debit card</span></span>
- <span data-ttu-id="6a857-1158">debitcard
</span><span class="sxs-lookup"><span data-stu-id="6a857-1158">debitcard</span></span>
- <span data-ttu-id="6a857-1159">debit cards
</span><span class="sxs-lookup"><span data-stu-id="6a857-1159">debit cards</span></span>
- <span data-ttu-id="6a857-1160">debitcards
</span><span class="sxs-lookup"><span data-stu-id="6a857-1160">debitcards</span></span>
- <span data-ttu-id="6a857-1161">atm card
</span><span class="sxs-lookup"><span data-stu-id="6a857-1161">atm card</span></span>
- <span data-ttu-id="6a857-1162">atmcard
</span><span class="sxs-lookup"><span data-stu-id="6a857-1162">atmcard</span></span>
- <span data-ttu-id="6a857-1163">atm cards
</span><span class="sxs-lookup"><span data-stu-id="6a857-1163">atm cards</span></span>
- <span data-ttu-id="6a857-1164">atmcards
</span><span class="sxs-lookup"><span data-stu-id="6a857-1164">atmcards</span></span>
- <span data-ttu-id="6a857-1165">
enroute</span><span class="sxs-lookup"><span data-stu-id="6a857-1165">enroute</span></span>
- <span data-ttu-id="6a857-1166">
en route</span><span class="sxs-lookup"><span data-stu-id="6a857-1166">en route</span></span>
- <span data-ttu-id="6a857-1167">card type
</span><span class="sxs-lookup"><span data-stu-id="6a857-1167">card type</span></span>
- <span data-ttu-id="6a857-1168">carte bancaire
</span><span class="sxs-lookup"><span data-stu-id="6a857-1168">carte bancaire</span></span>
- <span data-ttu-id="6a857-1169">carte de crédit
</span><span class="sxs-lookup"><span data-stu-id="6a857-1169">carte de crédit</span></span>
- <span data-ttu-id="6a857-1170">carte de credit
</span><span class="sxs-lookup"><span data-stu-id="6a857-1170">carte de credit</span></span>
- <span data-ttu-id="6a857-1171">numéro de carte
</span><span class="sxs-lookup"><span data-stu-id="6a857-1171">numéro de carte</span></span>
- <span data-ttu-id="6a857-1172">numero de carte
</span><span class="sxs-lookup"><span data-stu-id="6a857-1172">numero de carte</span></span>
- <span data-ttu-id="6a857-1173">nº de la carte
</span><span class="sxs-lookup"><span data-stu-id="6a857-1173">nº de la carte</span></span>
- <span data-ttu-id="6a857-1174">nº de carte
</span><span class="sxs-lookup"><span data-stu-id="6a857-1174">nº de carte</span></span>
- <span data-ttu-id="6a857-1175">kreditkarte
</span><span class="sxs-lookup"><span data-stu-id="6a857-1175">kreditkarte</span></span>
- <span data-ttu-id="6a857-1176">karte
</span><span class="sxs-lookup"><span data-stu-id="6a857-1176">karte</span></span>
- <span data-ttu-id="6a857-1177">karteninhaber
</span><span class="sxs-lookup"><span data-stu-id="6a857-1177">karteninhaber</span></span>
- <span data-ttu-id="6a857-1178">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="6a857-1178">karteninhabers</span></span>
- <span data-ttu-id="6a857-1179">kreditkarteninhaber
</span><span class="sxs-lookup"><span data-stu-id="6a857-1179">kreditkarteninhaber</span></span>
- <span data-ttu-id="6a857-1180">kreditkarteninstitut
</span><span class="sxs-lookup"><span data-stu-id="6a857-1180">kreditkarteninstitut</span></span>
- <span data-ttu-id="6a857-1181">kreditkartentyp
</span><span class="sxs-lookup"><span data-stu-id="6a857-1181">kreditkartentyp</span></span>
- <span data-ttu-id="6a857-1182">eigentümername
</span><span class="sxs-lookup"><span data-stu-id="6a857-1182">eigentümername</span></span>
- <span data-ttu-id="6a857-1183">
kartennr
</span><span class="sxs-lookup"><span data-stu-id="6a857-1183">kartennr</span></span> 
- <span data-ttu-id="6a857-1184">kartennummer</span><span class="sxs-lookup"><span data-stu-id="6a857-1184">kartennummer</span></span>
- <span data-ttu-id="6a857-1185">
kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="6a857-1185">kreditkartennummer</span></span>
- <span data-ttu-id="6a857-1186">kreditkarten nummer</span><span class="sxs-lookup"><span data-stu-id="6a857-1186">kreditkarten-nummer</span></span>
- <span data-ttu-id="6a857-1187">carta di credito
</span><span class="sxs-lookup"><span data-stu-id="6a857-1187">carta di credito</span></span>
- <span data-ttu-id="6a857-1188">carta credito
</span><span class="sxs-lookup"><span data-stu-id="6a857-1188">carta credito</span></span>
- <span data-ttu-id="6a857-1189">carta</span><span class="sxs-lookup"><span data-stu-id="6a857-1189">carta</span></span>
- <span data-ttu-id="6a857-1190">n carta</span><span class="sxs-lookup"><span data-stu-id="6a857-1190">n carta</span></span>
- <span data-ttu-id="6a857-p110">nr. carta
</span><span class="sxs-lookup"><span data-stu-id="6a857-p110">nr. carta</span></span>
- <span data-ttu-id="6a857-1193">nr carta</span><span class="sxs-lookup"><span data-stu-id="6a857-1193">nr carta</span></span>
- <span data-ttu-id="6a857-1194">numero carta
</span><span class="sxs-lookup"><span data-stu-id="6a857-1194">numero carta</span></span>
- <span data-ttu-id="6a857-1195">numero della carta
</span><span class="sxs-lookup"><span data-stu-id="6a857-1195">numero della carta</span></span>
- <span data-ttu-id="6a857-1196">numero di carta
</span><span class="sxs-lookup"><span data-stu-id="6a857-1196">numero di carta</span></span>
- <span data-ttu-id="6a857-1197">tarjeta credito
</span><span class="sxs-lookup"><span data-stu-id="6a857-1197">tarjeta credito</span></span>
- <span data-ttu-id="6a857-1198">tarjeta de credito
</span><span class="sxs-lookup"><span data-stu-id="6a857-1198">tarjeta de credito</span></span>
- <span data-ttu-id="6a857-1199">
tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="6a857-1199">tarjeta crédito</span></span>
- <span data-ttu-id="6a857-1200">
tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="6a857-1200">tarjeta de crédito</span></span>
- <span data-ttu-id="6a857-1201">tarjeta de atm
</span><span class="sxs-lookup"><span data-stu-id="6a857-1201">tarjeta de atm</span></span>
- <span data-ttu-id="6a857-1202">tarjeta atm
</span><span class="sxs-lookup"><span data-stu-id="6a857-1202">tarjeta atm</span></span>
- <span data-ttu-id="6a857-1203">tarjeta debito
</span><span class="sxs-lookup"><span data-stu-id="6a857-1203">tarjeta debito</span></span>
- <span data-ttu-id="6a857-1204">tarjeta de debito
</span><span class="sxs-lookup"><span data-stu-id="6a857-1204">tarjeta de debito</span></span>
- <span data-ttu-id="6a857-1205">
tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="6a857-1205">tarjeta débito</span></span>
- <span data-ttu-id="6a857-1206">
tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="6a857-1206">tarjeta de débito</span></span>
- <span data-ttu-id="6a857-1207">nº de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="6a857-1207">nº de tarjeta</span></span>
- <span data-ttu-id="6a857-p111">no. de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="6a857-p111">no. de tarjeta</span></span>
- <span data-ttu-id="6a857-1210">没有 de tarjeta</span><span class="sxs-lookup"><span data-stu-id="6a857-1210">no de tarjeta</span></span>
- <span data-ttu-id="6a857-1211">numero de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="6a857-1211">numero de tarjeta</span></span>
- <span data-ttu-id="6a857-1212">número de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="6a857-1212">número de tarjeta</span></span>
- <span data-ttu-id="6a857-1213">tarjeta no
</span><span class="sxs-lookup"><span data-stu-id="6a857-1213">tarjeta no</span></span>
- <span data-ttu-id="6a857-1214">tarjetahabiente
</span><span class="sxs-lookup"><span data-stu-id="6a857-1214">tarjetahabiente</span></span>
- <span data-ttu-id="6a857-1215">cartão de crédito
</span><span class="sxs-lookup"><span data-stu-id="6a857-1215">cartão de crédito</span></span>
- <span data-ttu-id="6a857-1216">cartão de credito
</span><span class="sxs-lookup"><span data-stu-id="6a857-1216">cartão de credito</span></span>
- <span data-ttu-id="6a857-1217">cartao de crédito
</span><span class="sxs-lookup"><span data-stu-id="6a857-1217">cartao de crédito</span></span>
- <span data-ttu-id="6a857-1218">cartao de credito
</span><span class="sxs-lookup"><span data-stu-id="6a857-1218">cartao de credito</span></span>
- <span data-ttu-id="6a857-1219">cartão de débito
</span><span class="sxs-lookup"><span data-stu-id="6a857-1219">cartão de débito</span></span>
- <span data-ttu-id="6a857-1220">cartao de débito
</span><span class="sxs-lookup"><span data-stu-id="6a857-1220">cartao de débito</span></span>
- <span data-ttu-id="6a857-1221">cartão de debito
</span><span class="sxs-lookup"><span data-stu-id="6a857-1221">cartão de debito</span></span>
- <span data-ttu-id="6a857-1222">cartao de debito
</span><span class="sxs-lookup"><span data-stu-id="6a857-1222">cartao de debito</span></span>
- <span data-ttu-id="6a857-1223">débito automático</span><span class="sxs-lookup"><span data-stu-id="6a857-1223">débito automático</span></span>
- <span data-ttu-id="6a857-1224">debito automatico
</span><span class="sxs-lookup"><span data-stu-id="6a857-1224">debito automatico</span></span>
- <span data-ttu-id="6a857-1225">
número do cartão</span><span class="sxs-lookup"><span data-stu-id="6a857-1225">número do cartão</span></span>
- <span data-ttu-id="6a857-1226">
numero do cartão
</span><span class="sxs-lookup"><span data-stu-id="6a857-1226">numero do cartão</span></span> 
- <span data-ttu-id="6a857-1227">número do cartao</span><span class="sxs-lookup"><span data-stu-id="6a857-1227">número do cartao</span></span>
- <span data-ttu-id="6a857-1228">
numero do cartao</span><span class="sxs-lookup"><span data-stu-id="6a857-1228">numero do cartao</span></span>
- <span data-ttu-id="6a857-1229">número de cartão
</span><span class="sxs-lookup"><span data-stu-id="6a857-1229">número de cartão</span></span>
- <span data-ttu-id="6a857-1230">numero de cartão
</span><span class="sxs-lookup"><span data-stu-id="6a857-1230">numero de cartão</span></span>
- <span data-ttu-id="6a857-1231">número de cartao
</span><span class="sxs-lookup"><span data-stu-id="6a857-1231">número de cartao</span></span>
- <span data-ttu-id="6a857-1232">numero de cartao
</span><span class="sxs-lookup"><span data-stu-id="6a857-1232">numero de cartao</span></span>
- <span data-ttu-id="6a857-1233">nº 执行 cartão</span><span class="sxs-lookup"><span data-stu-id="6a857-1233">nº do cartão</span></span>
- <span data-ttu-id="6a857-1234">nº do cartao
</span><span class="sxs-lookup"><span data-stu-id="6a857-1234">nº do cartao</span></span>
- <span data-ttu-id="6a857-p112">nº. do cartão
</span><span class="sxs-lookup"><span data-stu-id="6a857-p112">nº. do cartão</span></span>
- <span data-ttu-id="6a857-1237">没有执行 cartão</span><span class="sxs-lookup"><span data-stu-id="6a857-1237">no do cartão</span></span>
- <span data-ttu-id="6a857-1238">没有执行 cartao</span><span class="sxs-lookup"><span data-stu-id="6a857-1238">no do cartao</span></span>
- <span data-ttu-id="6a857-p113">no. do cartão
</span><span class="sxs-lookup"><span data-stu-id="6a857-p113">no. do cartão</span></span>
- <span data-ttu-id="6a857-p114">
no. do cartao
</span><span class="sxs-lookup"><span data-stu-id="6a857-p114">no. do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="6a857-1243">	克罗地亚身份证号</span><span class="sxs-lookup"><span data-stu-id="6a857-1243">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-1244">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-1244">Format</span></span>

<span data-ttu-id="6a857-1245">九个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-1245">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-1246">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-1246">Pattern</span></span>

<span data-ttu-id="6a857-1247">九个连续的数字</span><span class="sxs-lookup"><span data-stu-id="6a857-1247">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-1248">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-1248">Checksum</span></span>

<span data-ttu-id="6a857-1249">否</span><span class="sxs-lookup"><span data-stu-id="6a857-1249">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-1250">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-1250">Definition</span></span>

<span data-ttu-id="6a857-1251">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-1251">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-1252">函数 Func_croatia_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-1252">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-1253">找到 Keyword_croatia_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-1253">A keyword from Keyword_croatia_id_card is found.</span></span>

```
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a857-1254">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-1254">Keywords</span></span>

#### <a name="keywordcroatiaidcard"></a><span data-ttu-id="6a857-1255">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="6a857-1255">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="6a857-1256">Croatian identity card</span><span class="sxs-lookup"><span data-stu-id="6a857-1256">Croatian identity card</span></span>
- <span data-ttu-id="6a857-1257">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="6a857-1257">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="6a857-1258">	Croatia Personal Identification (OIB) Number</span><span class="sxs-lookup"><span data-stu-id="6a857-1258">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-1259">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-1259">Format</span></span>

<span data-ttu-id="6a857-1260">10 个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-1260">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-1261">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-1261">Pattern</span></span>

<span data-ttu-id="6a857-1262">10 个数字：</span><span class="sxs-lookup"><span data-stu-id="6a857-1262">10 digits:</span></span>
- <span data-ttu-id="6a857-1263">六个数字，采用  DDMMYY 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="6a857-1263">Six digits in the form DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="6a857-1264">四个数字，最后一位数字是校验位</span><span class="sxs-lookup"><span data-stu-id="6a857-1264">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-1265">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-1265">Checksum</span></span>

<span data-ttu-id="6a857-1266">是</span><span class="sxs-lookup"><span data-stu-id="6a857-1266">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-1267">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-1267">Definition</span></span>

<span data-ttu-id="6a857-1268">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-1268">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-1269">函数 Func_croatia_oib_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-1269">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-1270">找到 Keyword_croatia_oib_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-1270">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="6a857-1271">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-1271">The checksum passes.</span></span>

<span data-ttu-id="6a857-1272">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-1272">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-1273">函数 Func_croatia_oib_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-1273">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-1274">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-1274">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-1275">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-1275">Keywords</span></span>

#### <a name="keywordcroatiaoibnumber"></a><span data-ttu-id="6a857-1276">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="6a857-1276">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="6a857-1277">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="6a857-1277">Personal Identification Number</span></span>
- <span data-ttu-id="6a857-1278">Osobni identifikacijski broj
</span><span class="sxs-lookup"><span data-stu-id="6a857-1278">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="6a857-1279">OIB
</span><span class="sxs-lookup"><span data-stu-id="6a857-1279">OIB</span></span> 

   
## <a name="czech-national-identity-card-number"></a><span data-ttu-id="6a857-1280">	捷克国家身份证号</span><span class="sxs-lookup"><span data-stu-id="6a857-1280">Czech National Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-1281">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-1281">Format</span></span>

<span data-ttu-id="6a857-1282">10 个数字，包含正斜杠</span><span class="sxs-lookup"><span data-stu-id="6a857-1282">10 digits containing a forward slash</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-1283">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-1283">Pattern</span></span>

<span data-ttu-id="6a857-1284">10 个数字：</span><span class="sxs-lookup"><span data-stu-id="6a857-1284">10 digits:</span></span>
- <span data-ttu-id="6a857-1285">六个数字，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="6a857-1285">Six digits which are the date of birth</span></span> 
- <span data-ttu-id="6a857-1286">一个正斜杠 </span><span class="sxs-lookup"><span data-stu-id="6a857-1286">A forward slash</span></span> 
- <span data-ttu-id="6a857-1287">四个数字，最后一位数字是校验位</span><span class="sxs-lookup"><span data-stu-id="6a857-1287">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-1288">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-1288">Checksum</span></span>

<span data-ttu-id="6a857-1289">是</span><span class="sxs-lookup"><span data-stu-id="6a857-1289">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-1290">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-1290">Definition</span></span>

<span data-ttu-id="6a857-p115">DLP 策略是 85%相信它已检测到此类型的敏感信息 if、 内 300 个字符的邻近度： 函数 Func_czech_id_card 查找与模式匹配的内容。找到从 Keyword_czech_id_card 关键字。将传递校验和。</span><span class="sxs-lookup"><span data-stu-id="6a857-p115">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern. A keyword from Keyword_czech_id_card is found. The checksum passes.</span></span>

```
<!-- Czech National Identity Card Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_czech_id_card"/>
     <Match idRef="Keyword_czech_id_card"/>
  </Pattern>
</Entity>
```


### <a name="keywords"></a><span data-ttu-id="6a857-1294">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-1294">Keywords</span></span>

- <span data-ttu-id="6a857-1295">Keyword_czech_id_card</span><span class="sxs-lookup"><span data-stu-id="6a857-1295">Keyword_czech_id_card</span></span>
- <span data-ttu-id="6a857-1296">Czech national identity card</span><span class="sxs-lookup"><span data-stu-id="6a857-1296">Czech national identity card</span></span>
- <span data-ttu-id="6a857-1297">Občanský průka</span><span class="sxs-lookup"><span data-stu-id="6a857-1297">Občanský průka</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="6a857-1298">	丹麦个人身份号码</span><span class="sxs-lookup"><span data-stu-id="6a857-1298">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-1299">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-1299">Format</span></span>

<span data-ttu-id="6a857-1300">10 个数字，包含连字符</span><span class="sxs-lookup"><span data-stu-id="6a857-1300">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-1301">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-1301">Pattern</span></span>

<span data-ttu-id="6a857-1302">10 个数字：</span><span class="sxs-lookup"><span data-stu-id="6a857-1302">10 digits:</span></span>
- <span data-ttu-id="6a857-1303">六个数字，采用  DDMMYY 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="6a857-1303">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="6a857-1304">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="6a857-1304">A hyphen</span></span> 
- <span data-ttu-id="6a857-1305">四个数字，最后一位数字是校验位</span><span class="sxs-lookup"><span data-stu-id="6a857-1305">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-1306">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-1306">Checksum</span></span>

<span data-ttu-id="6a857-1307">是</span><span class="sxs-lookup"><span data-stu-id="6a857-1307">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-1308">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-1308">Definition</span></span>

<span data-ttu-id="6a857-p116">DLP 策略是相信它已检测到此类型的敏感信息的 75 %if、 内 300 个字符的邻近度： 正则表达式 Regex_denmark_id 找到与模式匹配的内容。找到从 Keyword_denmark_id 关键字。将传递校验和。</span><span class="sxs-lookup"><span data-stu-id="6a857-p116">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern. A keyword from Keyword_denmark_id is found. The checksum passes.</span></span>

```
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a857-1312">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-1312">Keywords</span></span>

#### <a name="keyworddenmarkid"></a><span data-ttu-id="6a857-1313">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="6a857-1313">Keyword_denmark_id</span></span>

- <span data-ttu-id="6a857-1314">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="6a857-1314">Personal Identification Number</span></span>
- <span data-ttu-id="6a857-1315">CPR</span><span class="sxs-lookup"><span data-stu-id="6a857-1315">CPR</span></span>
- <span data-ttu-id="6a857-1316">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="6a857-1316">Det Centrale Personregister</span></span>
- <span data-ttu-id="6a857-1317">Personnummer</span><span class="sxs-lookup"><span data-stu-id="6a857-1317">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="6a857-1318">药品管制局 (DEA) 号码</span><span class="sxs-lookup"><span data-stu-id="6a857-1318">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-1319">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-1319">Format</span></span>

<span data-ttu-id="6a857-1320">两个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-1320">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-1321">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-1321">Pattern</span></span>

<span data-ttu-id="6a857-1322">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="6a857-1322">Pattern must include all of the following:</span></span>
- <span data-ttu-id="6a857-1323">这一组可能的字母（不区分大小写）中的一个字母：abcdefghjklmnprstux，这是注册人代码</span><span class="sxs-lookup"><span data-stu-id="6a857-1323">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="6a857-1324">一个字母（不区分大小写），这是注册人姓氏的第一个字母</span><span class="sxs-lookup"><span data-stu-id="6a857-1324">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="6a857-1325">七位数字，最后一个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="6a857-1325">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-1326">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-1326">Checksum</span></span>

<span data-ttu-id="6a857-1327">是</span><span class="sxs-lookup"><span data-stu-id="6a857-1327">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-1328">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-1328">Definition</span></span>

<span data-ttu-id="6a857-1329">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-1329">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-1330">函数 Func_dea_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-1330">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-1331">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-1331">The checksum passes.</span></span>

```
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a857-1332">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-1332">Keywords</span></span>

<span data-ttu-id="6a857-1333">无</span><span class="sxs-lookup"><span data-stu-id="6a857-1333">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="6a857-1334">欧盟借记卡号</span><span class="sxs-lookup"><span data-stu-id="6a857-1334">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-1335">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-1335">Format</span></span>

<span data-ttu-id="6a857-1336">16 个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-1336">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-1337">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-1337">Pattern</span></span>

<span data-ttu-id="6a857-1338">非常复杂且强大的模式</span><span class="sxs-lookup"><span data-stu-id="6a857-1338">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-1339">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-1339">Checksum</span></span>

<span data-ttu-id="6a857-1340">是</span><span class="sxs-lookup"><span data-stu-id="6a857-1340">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-1341">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-1341">Definition</span></span>

<span data-ttu-id="6a857-1342">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-1342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-1343">函数 Func_eu_debit_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-1343">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-1344">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="6a857-1344">At least one of the following is true:</span></span>
    - <span data-ttu-id="6a857-1345">找到 Keyword_eu_debit_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-1345">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="6a857-1346">找到 Keyword_card_terms_dict 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-1346">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="6a857-1347">找到 Keyword_card_security_terms_dict 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-1347">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="6a857-1348">找到 Keyword_card_expiration_terms_dict 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-1348">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="6a857-1349">函数 Func_expiration_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="6a857-1349">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="6a857-1350">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-1350">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-1351">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-1351">Keywords</span></span>

#### <a name="keywordeudebitcard"></a><span data-ttu-id="6a857-1352">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="6a857-1352">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="6a857-1353">帐号</span><span class="sxs-lookup"><span data-stu-id="6a857-1353">account number</span></span> 
- <span data-ttu-id="6a857-1354">card number
</span><span class="sxs-lookup"><span data-stu-id="6a857-1354">card number</span></span> 
- <span data-ttu-id="6a857-1355">card no.
</span><span class="sxs-lookup"><span data-stu-id="6a857-1355">card no.</span></span> 
- <span data-ttu-id="6a857-1356">security number
</span><span class="sxs-lookup"><span data-stu-id="6a857-1356">security number</span></span> 
- <span data-ttu-id="6a857-1357">抄送 #</span><span class="sxs-lookup"><span data-stu-id="6a857-1357">cc#</span></span> 

#### <a name="keywordcardtermsdict"></a><span data-ttu-id="6a857-1358">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="6a857-1358">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="6a857-1359">acct nbr
</span><span class="sxs-lookup"><span data-stu-id="6a857-1359">acct nbr</span></span> 
- <span data-ttu-id="6a857-1360">acct num
</span><span class="sxs-lookup"><span data-stu-id="6a857-1360">acct num</span></span> 
- <span data-ttu-id="6a857-1361">acct no
</span><span class="sxs-lookup"><span data-stu-id="6a857-1361">acct no</span></span> 
- <span data-ttu-id="6a857-1362">american express
</span><span class="sxs-lookup"><span data-stu-id="6a857-1362">american express</span></span> 
- <span data-ttu-id="6a857-1363">americanexpress
</span><span class="sxs-lookup"><span data-stu-id="6a857-1363">americanexpress</span></span> 
- <span data-ttu-id="6a857-1364">americano espresso
</span><span class="sxs-lookup"><span data-stu-id="6a857-1364">americano espresso</span></span> 
- <span data-ttu-id="6a857-1365">amex</span><span class="sxs-lookup"><span data-stu-id="6a857-1365">amex</span></span> 
- <span data-ttu-id="6a857-1366">atm card
</span><span class="sxs-lookup"><span data-stu-id="6a857-1366">atm card</span></span> 
- <span data-ttu-id="6a857-1367">atm cards
</span><span class="sxs-lookup"><span data-stu-id="6a857-1367">atm cards</span></span> 
- <span data-ttu-id="6a857-1368">atm kaart
</span><span class="sxs-lookup"><span data-stu-id="6a857-1368">atm kaart</span></span> 
- <span data-ttu-id="6a857-1369">atmcard
</span><span class="sxs-lookup"><span data-stu-id="6a857-1369">atmcard</span></span> 
- <span data-ttu-id="6a857-1370">atmcards
</span><span class="sxs-lookup"><span data-stu-id="6a857-1370">atmcards</span></span> 
- <span data-ttu-id="6a857-1371">atmkaart
</span><span class="sxs-lookup"><span data-stu-id="6a857-1371">atmkaart</span></span> 
- <span data-ttu-id="6a857-1372">atmkaarten
</span><span class="sxs-lookup"><span data-stu-id="6a857-1372">atmkaarten</span></span> 
- <span data-ttu-id="6a857-1373">bancontact
</span><span class="sxs-lookup"><span data-stu-id="6a857-1373">bancontact</span></span> 
- <span data-ttu-id="6a857-1374">bank card
</span><span class="sxs-lookup"><span data-stu-id="6a857-1374">bank card</span></span> 
- <span data-ttu-id="6a857-1375">bankkaart
</span><span class="sxs-lookup"><span data-stu-id="6a857-1375">bankkaart</span></span> 
- <span data-ttu-id="6a857-1376">card holder
</span><span class="sxs-lookup"><span data-stu-id="6a857-1376">card holder</span></span> 
- <span data-ttu-id="6a857-1377">card holders
</span><span class="sxs-lookup"><span data-stu-id="6a857-1377">card holders</span></span> 
- <span data-ttu-id="6a857-1378">card num
</span><span class="sxs-lookup"><span data-stu-id="6a857-1378">card num</span></span> 
- <span data-ttu-id="6a857-1379">card number
</span><span class="sxs-lookup"><span data-stu-id="6a857-1379">card number</span></span> 
- <span data-ttu-id="6a857-1380">card numbers
</span><span class="sxs-lookup"><span data-stu-id="6a857-1380">card numbers</span></span> 
- <span data-ttu-id="6a857-1381">card type
</span><span class="sxs-lookup"><span data-stu-id="6a857-1381">card type</span></span> 
- <span data-ttu-id="6a857-1382">cardano numerico
</span><span class="sxs-lookup"><span data-stu-id="6a857-1382">cardano numerico</span></span> 
- <span data-ttu-id="6a857-1383">cardholder
</span><span class="sxs-lookup"><span data-stu-id="6a857-1383">cardholder</span></span> 
- <span data-ttu-id="6a857-1384">cardholders
</span><span class="sxs-lookup"><span data-stu-id="6a857-1384">cardholders</span></span> 
- <span data-ttu-id="6a857-1385">cardnumber
</span><span class="sxs-lookup"><span data-stu-id="6a857-1385">cardnumber</span></span> 
- <span data-ttu-id="6a857-1386">cardnumbers
</span><span class="sxs-lookup"><span data-stu-id="6a857-1386">cardnumbers</span></span> 
- <span data-ttu-id="6a857-1387">carta bianca
</span><span class="sxs-lookup"><span data-stu-id="6a857-1387">carta bianca</span></span> 
- <span data-ttu-id="6a857-1388">carta credito
</span><span class="sxs-lookup"><span data-stu-id="6a857-1388">carta credito</span></span> 
- <span data-ttu-id="6a857-1389">carta di credito
</span><span class="sxs-lookup"><span data-stu-id="6a857-1389">carta di credito</span></span> 
- <span data-ttu-id="6a857-1390">cartao de credito
</span><span class="sxs-lookup"><span data-stu-id="6a857-1390">cartao de credito</span></span> 
- <span data-ttu-id="6a857-1391">cartao de crédito
</span><span class="sxs-lookup"><span data-stu-id="6a857-1391">cartao de crédito</span></span> 
- <span data-ttu-id="6a857-1392">cartao de debito
</span><span class="sxs-lookup"><span data-stu-id="6a857-1392">cartao de debito</span></span> 
- <span data-ttu-id="6a857-1393">cartao de débito
</span><span class="sxs-lookup"><span data-stu-id="6a857-1393">cartao de débito</span></span> 
- <span data-ttu-id="6a857-1394">carte bancaire
</span><span class="sxs-lookup"><span data-stu-id="6a857-1394">carte bancaire</span></span> 
- <span data-ttu-id="6a857-1395">carte blanche
</span><span class="sxs-lookup"><span data-stu-id="6a857-1395">carte blanche</span></span> 
- <span data-ttu-id="6a857-1396">carte bleue
</span><span class="sxs-lookup"><span data-stu-id="6a857-1396">carte bleue</span></span> 
- <span data-ttu-id="6a857-1397">carte de credit
</span><span class="sxs-lookup"><span data-stu-id="6a857-1397">carte de credit</span></span> 
- <span data-ttu-id="6a857-1398">carte de crédit
</span><span class="sxs-lookup"><span data-stu-id="6a857-1398">carte de crédit</span></span> 
- <span data-ttu-id="6a857-1399">carte di credito
</span><span class="sxs-lookup"><span data-stu-id="6a857-1399">carte di credito</span></span> 
- <span data-ttu-id="6a857-1400">carteblanche
</span><span class="sxs-lookup"><span data-stu-id="6a857-1400">carteblanche</span></span> 
- <span data-ttu-id="6a857-1401">cartão de credito
</span><span class="sxs-lookup"><span data-stu-id="6a857-1401">cartão de credito</span></span> 
- <span data-ttu-id="6a857-1402">cartão de crédito
</span><span class="sxs-lookup"><span data-stu-id="6a857-1402">cartão de crédito</span></span> 
- <span data-ttu-id="6a857-1403">cartão de debito
</span><span class="sxs-lookup"><span data-stu-id="6a857-1403">cartão de debito</span></span> 
- <span data-ttu-id="6a857-1404">cartão de débito
</span><span class="sxs-lookup"><span data-stu-id="6a857-1404">cartão de débito</span></span> 
- <span data-ttu-id="6a857-1405">cb
</span><span class="sxs-lookup"><span data-stu-id="6a857-1405">cb</span></span> 
- <span data-ttu-id="6a857-1406">ccn
</span><span class="sxs-lookup"><span data-stu-id="6a857-1406">ccn</span></span> 
- <span data-ttu-id="6a857-1407">check card
</span><span class="sxs-lookup"><span data-stu-id="6a857-1407">check card</span></span> 
- <span data-ttu-id="6a857-1408">check cards
</span><span class="sxs-lookup"><span data-stu-id="6a857-1408">check cards</span></span> 
- <span data-ttu-id="6a857-1409">checkcard
</span><span class="sxs-lookup"><span data-stu-id="6a857-1409">checkcard</span></span>
- <span data-ttu-id="6a857-1410">checkcards
</span><span class="sxs-lookup"><span data-stu-id="6a857-1410">checkcards</span></span> 
- <span data-ttu-id="6a857-1411">chequekaart
</span><span class="sxs-lookup"><span data-stu-id="6a857-1411">chequekaart</span></span> 
- <span data-ttu-id="6a857-1412">cirrus
</span><span class="sxs-lookup"><span data-stu-id="6a857-1412">cirrus</span></span> 
- <span data-ttu-id="6a857-1413">cirrus-edc-maestro
</span><span class="sxs-lookup"><span data-stu-id="6a857-1413">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="6a857-1414">controlekaart
</span><span class="sxs-lookup"><span data-stu-id="6a857-1414">controlekaart</span></span> 
- <span data-ttu-id="6a857-1415">controlekaarten
</span><span class="sxs-lookup"><span data-stu-id="6a857-1415">controlekaarten</span></span> 
- <span data-ttu-id="6a857-1416">credit card
</span><span class="sxs-lookup"><span data-stu-id="6a857-1416">credit card</span></span> 
- <span data-ttu-id="6a857-1417">credit cards
</span><span class="sxs-lookup"><span data-stu-id="6a857-1417">credit cards</span></span> 
- <span data-ttu-id="6a857-1418">creditcard
</span><span class="sxs-lookup"><span data-stu-id="6a857-1418">creditcard</span></span> 
- <span data-ttu-id="6a857-1419">creditcards
</span><span class="sxs-lookup"><span data-stu-id="6a857-1419">creditcards</span></span> 
- <span data-ttu-id="6a857-1420">debetkaart
</span><span class="sxs-lookup"><span data-stu-id="6a857-1420">debetkaart</span></span> 
- <span data-ttu-id="6a857-1421">debetkaarten
</span><span class="sxs-lookup"><span data-stu-id="6a857-1421">debetkaarten</span></span> 
- <span data-ttu-id="6a857-1422">debit card
</span><span class="sxs-lookup"><span data-stu-id="6a857-1422">debit card</span></span> 
- <span data-ttu-id="6a857-1423">debit cards
</span><span class="sxs-lookup"><span data-stu-id="6a857-1423">debit cards</span></span> 
- <span data-ttu-id="6a857-1424">debitcard
</span><span class="sxs-lookup"><span data-stu-id="6a857-1424">debitcard</span></span> 
- <span data-ttu-id="6a857-1425">debitcards
</span><span class="sxs-lookup"><span data-stu-id="6a857-1425">debitcards</span></span> 
- <span data-ttu-id="6a857-1426">debito automatico
</span><span class="sxs-lookup"><span data-stu-id="6a857-1426">debito automatico</span></span> 
- <span data-ttu-id="6a857-1427">diners club
</span><span class="sxs-lookup"><span data-stu-id="6a857-1427">diners club</span></span> 
- <span data-ttu-id="6a857-1428">dinersclub
</span><span class="sxs-lookup"><span data-stu-id="6a857-1428">dinersclub</span></span> 
- <span data-ttu-id="6a857-1429">发现</span><span class="sxs-lookup"><span data-stu-id="6a857-1429">discover</span></span> 
- <span data-ttu-id="6a857-1430">discover card
</span><span class="sxs-lookup"><span data-stu-id="6a857-1430">discover card</span></span> 
- <span data-ttu-id="6a857-1431">discover cards
</span><span class="sxs-lookup"><span data-stu-id="6a857-1431">discover cards</span></span> 
- <span data-ttu-id="6a857-1432">discovercard
</span><span class="sxs-lookup"><span data-stu-id="6a857-1432">discovercard</span></span> 
- <span data-ttu-id="6a857-1433">discovercards
</span><span class="sxs-lookup"><span data-stu-id="6a857-1433">discovercards</span></span> 
- <span data-ttu-id="6a857-1434">débito automático</span><span class="sxs-lookup"><span data-stu-id="6a857-1434">débito automático</span></span>
- <span data-ttu-id="6a857-1435">
edc
</span><span class="sxs-lookup"><span data-stu-id="6a857-1435">edc</span></span> 
- <span data-ttu-id="6a857-1436">eigentümername
</span><span class="sxs-lookup"><span data-stu-id="6a857-1436">eigentümername</span></span> 
- <span data-ttu-id="6a857-1437">european debit card
</span><span class="sxs-lookup"><span data-stu-id="6a857-1437">european debit card</span></span> 
- <span data-ttu-id="6a857-1438">hoofdkaart
</span><span class="sxs-lookup"><span data-stu-id="6a857-1438">hoofdkaart</span></span> 
- <span data-ttu-id="6a857-1439">hoofdkaarten
</span><span class="sxs-lookup"><span data-stu-id="6a857-1439">hoofdkaarten</span></span> 
- <span data-ttu-id="6a857-1440">in viaggio
</span><span class="sxs-lookup"><span data-stu-id="6a857-1440">in viaggio</span></span> 
- <span data-ttu-id="6a857-1441">japanese card bureau
</span><span class="sxs-lookup"><span data-stu-id="6a857-1441">japanese card bureau</span></span> 
- <span data-ttu-id="6a857-1442">japanse kaartdienst
</span><span class="sxs-lookup"><span data-stu-id="6a857-1442">japanse kaartdienst</span></span> 
- <span data-ttu-id="6a857-1443">jcb
</span><span class="sxs-lookup"><span data-stu-id="6a857-1443">jcb</span></span> 
- <span data-ttu-id="6a857-1444">kaart
</span><span class="sxs-lookup"><span data-stu-id="6a857-1444">kaart</span></span> 
- <span data-ttu-id="6a857-1445">kaart num
</span><span class="sxs-lookup"><span data-stu-id="6a857-1445">kaart num</span></span> 
- <span data-ttu-id="6a857-1446">kaartaantal
</span><span class="sxs-lookup"><span data-stu-id="6a857-1446">kaartaantal</span></span> 
- <span data-ttu-id="6a857-1447">kaartaantallen
</span><span class="sxs-lookup"><span data-stu-id="6a857-1447">kaartaantallen</span></span> 
- <span data-ttu-id="6a857-1448">kaarthouder
</span><span class="sxs-lookup"><span data-stu-id="6a857-1448">kaarthouder</span></span> 
- <span data-ttu-id="6a857-1449">kaarthouders
</span><span class="sxs-lookup"><span data-stu-id="6a857-1449">kaarthouders</span></span> 
- <span data-ttu-id="6a857-1450">karte
</span><span class="sxs-lookup"><span data-stu-id="6a857-1450">karte</span></span>  
- <span data-ttu-id="6a857-1451">karteninhaber
</span><span class="sxs-lookup"><span data-stu-id="6a857-1451">karteninhaber</span></span> 
- <span data-ttu-id="6a857-1452">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="6a857-1452">karteninhabers</span></span>
- <span data-ttu-id="6a857-1453">
kartennr
</span><span class="sxs-lookup"><span data-stu-id="6a857-1453">kartennr</span></span> 
- <span data-ttu-id="6a857-1454">kartennummer</span><span class="sxs-lookup"><span data-stu-id="6a857-1454">kartennummer</span></span> 
- <span data-ttu-id="6a857-1455">kreditkarte
</span><span class="sxs-lookup"><span data-stu-id="6a857-1455">kreditkarte</span></span> 
- <span data-ttu-id="6a857-1456">kreditkarten nummer</span><span class="sxs-lookup"><span data-stu-id="6a857-1456">kreditkarten-nummer</span></span> 
- <span data-ttu-id="6a857-1457">kreditkarteninhaber
</span><span class="sxs-lookup"><span data-stu-id="6a857-1457">kreditkarteninhaber</span></span> 
- <span data-ttu-id="6a857-1458">kreditkarteninstitut
</span><span class="sxs-lookup"><span data-stu-id="6a857-1458">kreditkarteninstitut</span></span> 
- <span data-ttu-id="6a857-1459">kreditkartennummer
</span><span class="sxs-lookup"><span data-stu-id="6a857-1459">kreditkartennummer</span></span> 
- <span data-ttu-id="6a857-1460">kreditkartentyp
</span><span class="sxs-lookup"><span data-stu-id="6a857-1460">kreditkartentyp</span></span> 
- <span data-ttu-id="6a857-1461">maestro
</span><span class="sxs-lookup"><span data-stu-id="6a857-1461">maestro</span></span> 
- <span data-ttu-id="6a857-1462">Master Card
</span><span class="sxs-lookup"><span data-stu-id="6a857-1462">master card</span></span> 
- <span data-ttu-id="6a857-1463">master cards
</span><span class="sxs-lookup"><span data-stu-id="6a857-1463">master cards</span></span> 
- <span data-ttu-id="6a857-1464">mastercard
</span><span class="sxs-lookup"><span data-stu-id="6a857-1464">mastercard</span></span> 
- <span data-ttu-id="6a857-1465">mastercards</span><span class="sxs-lookup"><span data-stu-id="6a857-1465">mastercards</span></span> 
- <span data-ttu-id="6a857-1466">mc</span><span class="sxs-lookup"><span data-stu-id="6a857-1466">mc</span></span> 
- <span data-ttu-id="6a857-1467">mister cash
</span><span class="sxs-lookup"><span data-stu-id="6a857-1467">mister cash</span></span> 
- <span data-ttu-id="6a857-1468">n carta</span><span class="sxs-lookup"><span data-stu-id="6a857-1468">n carta</span></span> 
- <span data-ttu-id="6a857-1469">carta</span><span class="sxs-lookup"><span data-stu-id="6a857-1469">carta</span></span> 
- <span data-ttu-id="6a857-1470">没有 de tarjeta</span><span class="sxs-lookup"><span data-stu-id="6a857-1470">no de tarjeta</span></span> 
- <span data-ttu-id="6a857-1471">没有执行 cartao</span><span class="sxs-lookup"><span data-stu-id="6a857-1471">no do cartao</span></span> 
- <span data-ttu-id="6a857-1472">没有执行 cartão</span><span class="sxs-lookup"><span data-stu-id="6a857-1472">no do cartão</span></span> 
- <span data-ttu-id="6a857-p117">no. de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="6a857-p117">no. de tarjeta</span></span> 
- <span data-ttu-id="6a857-p118">no. do cartao
</span><span class="sxs-lookup"><span data-stu-id="6a857-p118">no. do cartao</span></span> 
- <span data-ttu-id="6a857-p119">no. do cartão
</span><span class="sxs-lookup"><span data-stu-id="6a857-p119">no. do cartão</span></span> 
- <span data-ttu-id="6a857-1479">nr carta</span><span class="sxs-lookup"><span data-stu-id="6a857-1479">nr carta</span></span> 
- <span data-ttu-id="6a857-p120">nr. carta
</span><span class="sxs-lookup"><span data-stu-id="6a857-p120">nr. carta</span></span> 
- <span data-ttu-id="6a857-1482">numeri di scheda
</span><span class="sxs-lookup"><span data-stu-id="6a857-1482">numeri di scheda</span></span> 
- <span data-ttu-id="6a857-1483">numero carta
</span><span class="sxs-lookup"><span data-stu-id="6a857-1483">numero carta</span></span> 
- <span data-ttu-id="6a857-1484">numero de cartao
</span><span class="sxs-lookup"><span data-stu-id="6a857-1484">numero de cartao</span></span> 
- <span data-ttu-id="6a857-1485">numero de carte
</span><span class="sxs-lookup"><span data-stu-id="6a857-1485">numero de carte</span></span> 
- <span data-ttu-id="6a857-1486">numero de cartão
</span><span class="sxs-lookup"><span data-stu-id="6a857-1486">numero de cartão</span></span> 
- <span data-ttu-id="6a857-1487">numero de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="6a857-1487">numero de tarjeta</span></span>
- <span data-ttu-id="6a857-1488">numero della carta
</span><span class="sxs-lookup"><span data-stu-id="6a857-1488">numero della carta</span></span> 
- <span data-ttu-id="6a857-1489">numero di carta
</span><span class="sxs-lookup"><span data-stu-id="6a857-1489">numero di carta</span></span> 
- <span data-ttu-id="6a857-1490">numero di scheda
</span><span class="sxs-lookup"><span data-stu-id="6a857-1490">numero di scheda</span></span> 
- <span data-ttu-id="6a857-1491">numero do cartao
</span><span class="sxs-lookup"><span data-stu-id="6a857-1491">numero do cartao</span></span> 
- <span data-ttu-id="6a857-1492">numero do cartão
</span><span class="sxs-lookup"><span data-stu-id="6a857-1492">numero do cartão</span></span> 
- <span data-ttu-id="6a857-1493">numéro de carte
</span><span class="sxs-lookup"><span data-stu-id="6a857-1493">numéro de carte</span></span> 
- <span data-ttu-id="6a857-1494">nº carta
</span><span class="sxs-lookup"><span data-stu-id="6a857-1494">nº carta</span></span> 
- <span data-ttu-id="6a857-1495">nº de carte
</span><span class="sxs-lookup"><span data-stu-id="6a857-1495">nº de carte</span></span> 
- <span data-ttu-id="6a857-1496">nº de la carte
</span><span class="sxs-lookup"><span data-stu-id="6a857-1496">nº de la carte</span></span> 
- <span data-ttu-id="6a857-1497">nº de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="6a857-1497">nº de tarjeta</span></span> 
- <span data-ttu-id="6a857-1498">nº do cartao
</span><span class="sxs-lookup"><span data-stu-id="6a857-1498">nº do cartao</span></span> 
- <span data-ttu-id="6a857-1499">nº 执行 cartão</span><span class="sxs-lookup"><span data-stu-id="6a857-1499">nº do cartão</span></span> 
- <span data-ttu-id="6a857-p121">nº. do cartão
</span><span class="sxs-lookup"><span data-stu-id="6a857-p121">nº. do cartão</span></span> 
- <span data-ttu-id="6a857-1502">número de cartao
</span><span class="sxs-lookup"><span data-stu-id="6a857-1502">número de cartao</span></span> 
- <span data-ttu-id="6a857-1503">número de cartão
</span><span class="sxs-lookup"><span data-stu-id="6a857-1503">número de cartão</span></span> 
- <span data-ttu-id="6a857-1504">número de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="6a857-1504">número de tarjeta</span></span> 
- <span data-ttu-id="6a857-1505">número do cartao</span><span class="sxs-lookup"><span data-stu-id="6a857-1505">número do cartao</span></span> 
- <span data-ttu-id="6a857-1506">scheda dell'assegno
</span><span class="sxs-lookup"><span data-stu-id="6a857-1506">scheda dell'assegno</span></span> 
- <span data-ttu-id="6a857-1507">scheda dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="6a857-1507">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="6a857-1508">scheda dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="6a857-1508">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="6a857-1509">scheda della banca
</span><span class="sxs-lookup"><span data-stu-id="6a857-1509">scheda della banca</span></span> 
- <span data-ttu-id="6a857-1510">scheda di controllo
</span><span class="sxs-lookup"><span data-stu-id="6a857-1510">scheda di controllo</span></span> 
- <span data-ttu-id="6a857-1511">scheda di debito
</span><span class="sxs-lookup"><span data-stu-id="6a857-1511">scheda di debito</span></span> 
- <span data-ttu-id="6a857-1512">scheda matrice
</span><span class="sxs-lookup"><span data-stu-id="6a857-1512">scheda matrice</span></span> 
- <span data-ttu-id="6a857-1513">schede dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="6a857-1513">schede dell'atmosfera</span></span> 
- <span data-ttu-id="6a857-1514">schede di controllo
</span><span class="sxs-lookup"><span data-stu-id="6a857-1514">schede di controllo</span></span> 
- <span data-ttu-id="6a857-1515">schede di debito
</span><span class="sxs-lookup"><span data-stu-id="6a857-1515">schede di debito</span></span> 
- <span data-ttu-id="6a857-1516">schede matrici
</span><span class="sxs-lookup"><span data-stu-id="6a857-1516">schede matrici</span></span> 
- <span data-ttu-id="6a857-1517">scoprono la scheda
</span><span class="sxs-lookup"><span data-stu-id="6a857-1517">scoprono la scheda</span></span> 
- <span data-ttu-id="6a857-1518">scoprono le schede
</span><span class="sxs-lookup"><span data-stu-id="6a857-1518">scoprono le schede</span></span> 
- <span data-ttu-id="6a857-1519">solo
</span><span class="sxs-lookup"><span data-stu-id="6a857-1519">solo</span></span> 
- <span data-ttu-id="6a857-1520">supporti di scheda
</span><span class="sxs-lookup"><span data-stu-id="6a857-1520">supporti di scheda</span></span> 
- <span data-ttu-id="6a857-1521">supporto di scheda
</span><span class="sxs-lookup"><span data-stu-id="6a857-1521">supporto di scheda</span></span> 
- <span data-ttu-id="6a857-1522">切换</span><span class="sxs-lookup"><span data-stu-id="6a857-1522">switch</span></span> 
- <span data-ttu-id="6a857-1523">tarjeta atm
</span><span class="sxs-lookup"><span data-stu-id="6a857-1523">tarjeta atm</span></span> 
- <span data-ttu-id="6a857-1524">tarjeta credito
</span><span class="sxs-lookup"><span data-stu-id="6a857-1524">tarjeta credito</span></span> 
- <span data-ttu-id="6a857-1525">tarjeta de atm
</span><span class="sxs-lookup"><span data-stu-id="6a857-1525">tarjeta de atm</span></span> 
- <span data-ttu-id="6a857-1526">tarjeta de credito
</span><span class="sxs-lookup"><span data-stu-id="6a857-1526">tarjeta de credito</span></span> 
- <span data-ttu-id="6a857-1527">tarjeta de debito
</span><span class="sxs-lookup"><span data-stu-id="6a857-1527">tarjeta de debito</span></span> 
- <span data-ttu-id="6a857-1528">tarjeta debito
</span><span class="sxs-lookup"><span data-stu-id="6a857-1528">tarjeta debito</span></span> 
- <span data-ttu-id="6a857-1529">tarjeta no
</span><span class="sxs-lookup"><span data-stu-id="6a857-1529">tarjeta no</span></span>
- <span data-ttu-id="6a857-1530">tarjetahabiente
</span><span class="sxs-lookup"><span data-stu-id="6a857-1530">tarjetahabiente</span></span> 
- <span data-ttu-id="6a857-1531">tipo della scheda
</span><span class="sxs-lookup"><span data-stu-id="6a857-1531">tipo della scheda</span></span> 
- <span data-ttu-id="6a857-1532">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="6a857-1532">ufficio giapponese della</span></span> 
- <span data-ttu-id="6a857-1533">scheda
</span><span class="sxs-lookup"><span data-stu-id="6a857-1533">scheda</span></span> 
- <span data-ttu-id="6a857-1534">v pay
</span><span class="sxs-lookup"><span data-stu-id="6a857-1534">v pay</span></span> 
- <span data-ttu-id="6a857-1535">v 付薪</span><span class="sxs-lookup"><span data-stu-id="6a857-1535">v-pay</span></span> 
- <span data-ttu-id="6a857-1536">visa
</span><span class="sxs-lookup"><span data-stu-id="6a857-1536">visa</span></span> 
- <span data-ttu-id="6a857-1537">visa plus
</span><span class="sxs-lookup"><span data-stu-id="6a857-1537">visa plus</span></span> 
- <span data-ttu-id="6a857-1538">visa electron
</span><span class="sxs-lookup"><span data-stu-id="6a857-1538">visa electron</span></span> 
- <span data-ttu-id="6a857-1539">visto
</span><span class="sxs-lookup"><span data-stu-id="6a857-1539">visto</span></span> 
- <span data-ttu-id="6a857-1540">visum
</span><span class="sxs-lookup"><span data-stu-id="6a857-1540">visum</span></span> 
- <span data-ttu-id="6a857-1541">vpay
</span><span class="sxs-lookup"><span data-stu-id="6a857-1541">vpay</span></span>   

#### <a name="keywordcardsecuritytermsdict"></a><span data-ttu-id="6a857-1542">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="6a857-1542">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="6a857-1543">card identification number</span><span class="sxs-lookup"><span data-stu-id="6a857-1543">card identification number</span></span>
- <span data-ttu-id="6a857-1544">card verification</span><span class="sxs-lookup"><span data-stu-id="6a857-1544">card verification</span></span> 
- <span data-ttu-id="6a857-1545">cardi la verifica
</span><span class="sxs-lookup"><span data-stu-id="6a857-1545">cardi la verifica</span></span> 
- <span data-ttu-id="6a857-1546">cid
</span><span class="sxs-lookup"><span data-stu-id="6a857-1546">cid</span></span> 
- <span data-ttu-id="6a857-1547">cod seg</span><span class="sxs-lookup"><span data-stu-id="6a857-1547">cod seg</span></span> 
- <span data-ttu-id="6a857-1548">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="6a857-1548">cod seguranca</span></span> 
- <span data-ttu-id="6a857-1549">cod segurança</span><span class="sxs-lookup"><span data-stu-id="6a857-1549">cod segurança</span></span> 
- <span data-ttu-id="6a857-1550">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="6a857-1550">cod sicurezza</span></span> 
- <span data-ttu-id="6a857-p122">cod. seg
</span><span class="sxs-lookup"><span data-stu-id="6a857-p122">cod. seg</span></span> 
- <span data-ttu-id="6a857-p123">cod. seguranca
</span><span class="sxs-lookup"><span data-stu-id="6a857-p123">cod. seguranca</span></span> 
- <span data-ttu-id="6a857-p124">cod. segurança
</span><span class="sxs-lookup"><span data-stu-id="6a857-p124">cod. segurança</span></span> 
- <span data-ttu-id="6a857-p125">cod. sicurezza
</span><span class="sxs-lookup"><span data-stu-id="6a857-p125">cod. sicurezza</span></span> 
- <span data-ttu-id="6a857-1559">codice di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="6a857-1559">codice di sicurezza</span></span> 
- <span data-ttu-id="6a857-1560">codice di verifica
</span><span class="sxs-lookup"><span data-stu-id="6a857-1560">codice di verifica</span></span> 
- <span data-ttu-id="6a857-1561">codigo
</span><span class="sxs-lookup"><span data-stu-id="6a857-1561">codigo</span></span> 
- <span data-ttu-id="6a857-1562">codigo de seguranca
</span><span class="sxs-lookup"><span data-stu-id="6a857-1562">codigo de seguranca</span></span> 
- <span data-ttu-id="6a857-1563">codigo de segurança
</span><span class="sxs-lookup"><span data-stu-id="6a857-1563">codigo de segurança</span></span> 
- <span data-ttu-id="6a857-1564">crittogramma
</span><span class="sxs-lookup"><span data-stu-id="6a857-1564">crittogramma</span></span> 
- <span data-ttu-id="6a857-1565">cryptogram
</span><span class="sxs-lookup"><span data-stu-id="6a857-1565">cryptogram</span></span> 
- <span data-ttu-id="6a857-1566">cryptogramme
</span><span class="sxs-lookup"><span data-stu-id="6a857-1566">cryptogramme</span></span> 
- <span data-ttu-id="6a857-1567">cv2</span><span class="sxs-lookup"><span data-stu-id="6a857-1567">cv2</span></span> 
- <span data-ttu-id="6a857-1568">cvc
</span><span class="sxs-lookup"><span data-stu-id="6a857-1568">cvc</span></span> 
- <span data-ttu-id="6a857-1569">cvc2</span><span class="sxs-lookup"><span data-stu-id="6a857-1569">cvc2</span></span> 
- <span data-ttu-id="6a857-1570">cvn
</span><span class="sxs-lookup"><span data-stu-id="6a857-1570">cvn</span></span> 
- <span data-ttu-id="6a857-1571">cvv
</span><span class="sxs-lookup"><span data-stu-id="6a857-1571">cvv</span></span> 
- <span data-ttu-id="6a857-1572">cvv2</span><span class="sxs-lookup"><span data-stu-id="6a857-1572">cvv2</span></span> 
- <span data-ttu-id="6a857-1573">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="6a857-1573">cód seguranca</span></span> 
- <span data-ttu-id="6a857-1574">cód segurança</span><span class="sxs-lookup"><span data-stu-id="6a857-1574">cód segurança</span></span> 
- <span data-ttu-id="6a857-p126">cód. seguranca
</span><span class="sxs-lookup"><span data-stu-id="6a857-p126">cód. seguranca</span></span> 
- <span data-ttu-id="6a857-p127">cód. segurança
</span><span class="sxs-lookup"><span data-stu-id="6a857-p127">cód. segurança</span></span> 
- <span data-ttu-id="6a857-1579">código
</span><span class="sxs-lookup"><span data-stu-id="6a857-1579">código</span></span> 
- <span data-ttu-id="6a857-1580">código de seguranca
</span><span class="sxs-lookup"><span data-stu-id="6a857-1580">código de seguranca</span></span> 
- <span data-ttu-id="6a857-1581">código de segurança
</span><span class="sxs-lookup"><span data-stu-id="6a857-1581">código de segurança</span></span> 
- <span data-ttu-id="6a857-1582">de kaart controle
</span><span class="sxs-lookup"><span data-stu-id="6a857-1582">de kaart controle</span></span> 
- <span data-ttu-id="6a857-1583">geeft nr uit
</span><span class="sxs-lookup"><span data-stu-id="6a857-1583">geeft nr uit</span></span> 
- <span data-ttu-id="6a857-1584">issue no
</span><span class="sxs-lookup"><span data-stu-id="6a857-1584">issue no</span></span> 
- <span data-ttu-id="6a857-1585">issue number
</span><span class="sxs-lookup"><span data-stu-id="6a857-1585">issue number</span></span> 
- <span data-ttu-id="6a857-1586">kaartidentificatienummer
</span><span class="sxs-lookup"><span data-stu-id="6a857-1586">kaartidentificatienummer</span></span> 
- <span data-ttu-id="6a857-1587">kreditkartenprufnummer
</span><span class="sxs-lookup"><span data-stu-id="6a857-1587">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="6a857-1588">kreditkartenprüfnummer
</span><span class="sxs-lookup"><span data-stu-id="6a857-1588">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="6a857-1589">kwestieaantal
</span><span class="sxs-lookup"><span data-stu-id="6a857-1589">kwestieaantal</span></span> 
- <span data-ttu-id="6a857-p128">no. dell'edizione
</span><span class="sxs-lookup"><span data-stu-id="6a857-p128">no. dell'edizione</span></span> 
- <span data-ttu-id="6a857-p129">no. di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="6a857-p129">no. di sicurezza</span></span> 
- <span data-ttu-id="6a857-1594">numero de securite
</span><span class="sxs-lookup"><span data-stu-id="6a857-1594">numero de securite</span></span> 
- <span data-ttu-id="6a857-1595">numero de verificacao
</span><span class="sxs-lookup"><span data-stu-id="6a857-1595">numero de verificacao</span></span> 
- <span data-ttu-id="6a857-1596">numero dell'edizione
</span><span class="sxs-lookup"><span data-stu-id="6a857-1596">numero dell'edizione</span></span> 
- <span data-ttu-id="6a857-1597">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="6a857-1597">numero di identificazione della</span></span> 
- <span data-ttu-id="6a857-1598">scheda
</span><span class="sxs-lookup"><span data-stu-id="6a857-1598">scheda</span></span> 
- <span data-ttu-id="6a857-1599">numero di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="6a857-1599">numero di sicurezza</span></span> 
- <span data-ttu-id="6a857-1600">numero van veiligheid
</span><span class="sxs-lookup"><span data-stu-id="6a857-1600">numero van veiligheid</span></span> 
- <span data-ttu-id="6a857-1601">numéro de sécurité
</span><span class="sxs-lookup"><span data-stu-id="6a857-1601">numéro de sécurité</span></span> 
- <span data-ttu-id="6a857-1602">nº autorizzazione
</span><span class="sxs-lookup"><span data-stu-id="6a857-1602">nº autorizzazione</span></span> 
- <span data-ttu-id="6a857-1603">número de verificação
</span><span class="sxs-lookup"><span data-stu-id="6a857-1603">número de verificação</span></span> 
- <span data-ttu-id="6a857-1604">perno il blocco
</span><span class="sxs-lookup"><span data-stu-id="6a857-1604">perno il blocco</span></span> 
- <span data-ttu-id="6a857-1605">pin block
</span><span class="sxs-lookup"><span data-stu-id="6a857-1605">pin block</span></span> 
- <span data-ttu-id="6a857-1606">prufziffer
</span><span class="sxs-lookup"><span data-stu-id="6a857-1606">prufziffer</span></span> 
- <span data-ttu-id="6a857-1607">prüfziffer
</span><span class="sxs-lookup"><span data-stu-id="6a857-1607">prüfziffer</span></span> 
- <span data-ttu-id="6a857-1608">security code
</span><span class="sxs-lookup"><span data-stu-id="6a857-1608">security code</span></span> 
- <span data-ttu-id="6a857-1609">security no
</span><span class="sxs-lookup"><span data-stu-id="6a857-1609">security no</span></span> 
- <span data-ttu-id="6a857-1610">security number
</span><span class="sxs-lookup"><span data-stu-id="6a857-1610">security number</span></span> 
- <span data-ttu-id="6a857-1611">sicherheits kode
</span><span class="sxs-lookup"><span data-stu-id="6a857-1611">sicherheits kode</span></span> 
- <span data-ttu-id="6a857-1612">sicherheitscode
</span><span class="sxs-lookup"><span data-stu-id="6a857-1612">sicherheitscode</span></span> 
- <span data-ttu-id="6a857-1613">sicherheitsnummer
</span><span class="sxs-lookup"><span data-stu-id="6a857-1613">sicherheitsnummer</span></span> 
- <span data-ttu-id="6a857-1614">speldblok
</span><span class="sxs-lookup"><span data-stu-id="6a857-1614">speldblok</span></span> 
- <span data-ttu-id="6a857-1615">veiligheid nr
</span><span class="sxs-lookup"><span data-stu-id="6a857-1615">veiligheid nr</span></span> 
- <span data-ttu-id="6a857-1616">veiligheidsaantal
</span><span class="sxs-lookup"><span data-stu-id="6a857-1616">veiligheidsaantal</span></span> 
- <span data-ttu-id="6a857-1617">veiligheidscode
</span><span class="sxs-lookup"><span data-stu-id="6a857-1617">veiligheidscode</span></span> 
- <span data-ttu-id="6a857-1618">veiligheidsnummer
</span><span class="sxs-lookup"><span data-stu-id="6a857-1618">veiligheidsnummer</span></span> 
- <span data-ttu-id="6a857-1619">verfalldatum
</span><span class="sxs-lookup"><span data-stu-id="6a857-1619">verfalldatum</span></span> 

#### <a name="keywordcardexpirationtermsdict"></a><span data-ttu-id="6a857-1620">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="6a857-1620">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="6a857-1621">ablauf
</span><span class="sxs-lookup"><span data-stu-id="6a857-1621">ablauf</span></span> 
- <span data-ttu-id="6a857-1622">data de expiracao
</span><span class="sxs-lookup"><span data-stu-id="6a857-1622">data de expiracao</span></span> 
- <span data-ttu-id="6a857-1623">data de expiração
</span><span class="sxs-lookup"><span data-stu-id="6a857-1623">data de expiração</span></span> 
- <span data-ttu-id="6a857-1624">data del exp
</span><span class="sxs-lookup"><span data-stu-id="6a857-1624">data del exp</span></span> 
- <span data-ttu-id="6a857-1625">data di exp
</span><span class="sxs-lookup"><span data-stu-id="6a857-1625">data di exp</span></span> 
- <span data-ttu-id="6a857-1626">data di scadenza
</span><span class="sxs-lookup"><span data-stu-id="6a857-1626">data di scadenza</span></span> 
- <span data-ttu-id="6a857-1627">data em que expira
</span><span class="sxs-lookup"><span data-stu-id="6a857-1627">data em que expira</span></span> 
- <span data-ttu-id="6a857-1628">data scad
</span><span class="sxs-lookup"><span data-stu-id="6a857-1628">data scad</span></span> 
- <span data-ttu-id="6a857-1629">data scadenza
</span><span class="sxs-lookup"><span data-stu-id="6a857-1629">data scadenza</span></span> 
- <span data-ttu-id="6a857-1630">date de validité
</span><span class="sxs-lookup"><span data-stu-id="6a857-1630">date de validité</span></span> 
- <span data-ttu-id="6a857-1631">datum afloop
</span><span class="sxs-lookup"><span data-stu-id="6a857-1631">datum afloop</span></span> 
- <span data-ttu-id="6a857-1632">datum van exp
</span><span class="sxs-lookup"><span data-stu-id="6a857-1632">datum van exp</span></span> 
- <span data-ttu-id="6a857-1633">de afloop
</span><span class="sxs-lookup"><span data-stu-id="6a857-1633">de afloop</span></span> 
- <span data-ttu-id="6a857-1634">espira
</span><span class="sxs-lookup"><span data-stu-id="6a857-1634">espira</span></span> 
- <span data-ttu-id="6a857-1635">espira
</span><span class="sxs-lookup"><span data-stu-id="6a857-1635">espira</span></span> 
- <span data-ttu-id="6a857-1636">exp date
</span><span class="sxs-lookup"><span data-stu-id="6a857-1636">exp date</span></span> 
- <span data-ttu-id="6a857-1637">exp datum
</span><span class="sxs-lookup"><span data-stu-id="6a857-1637">exp datum</span></span> 
- <span data-ttu-id="6a857-1638">过期</span><span class="sxs-lookup"><span data-stu-id="6a857-1638">expiration</span></span> 
- <span data-ttu-id="6a857-1639">expire
</span><span class="sxs-lookup"><span data-stu-id="6a857-1639">expire</span></span> 
- <span data-ttu-id="6a857-1640">expires
</span><span class="sxs-lookup"><span data-stu-id="6a857-1640">expires</span></span> 
- <span data-ttu-id="6a857-1641">expiry
</span><span class="sxs-lookup"><span data-stu-id="6a857-1641">expiry</span></span> 
- <span data-ttu-id="6a857-1642">fecha de expiracion
</span><span class="sxs-lookup"><span data-stu-id="6a857-1642">fecha de expiracion</span></span> 
- <span data-ttu-id="6a857-1643">fecha de venc
</span><span class="sxs-lookup"><span data-stu-id="6a857-1643">fecha de venc</span></span> 
- <span data-ttu-id="6a857-1644">gultig bis
</span><span class="sxs-lookup"><span data-stu-id="6a857-1644">gultig bis</span></span> 
- <span data-ttu-id="6a857-1645">gultigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="6a857-1645">gultigkeitsdatum</span></span> 
- <span data-ttu-id="6a857-1646">gültig bis
</span><span class="sxs-lookup"><span data-stu-id="6a857-1646">gültig bis</span></span> 
- <span data-ttu-id="6a857-1647">gültigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="6a857-1647">gültigkeitsdatum</span></span> 
- <span data-ttu-id="6a857-1648">la scadenza
</span><span class="sxs-lookup"><span data-stu-id="6a857-1648">la scadenza</span></span> 
- <span data-ttu-id="6a857-1649">scadenza
</span><span class="sxs-lookup"><span data-stu-id="6a857-1649">scadenza</span></span> 
- <span data-ttu-id="6a857-1650">valable
</span><span class="sxs-lookup"><span data-stu-id="6a857-1650">valable</span></span> 
- <span data-ttu-id="6a857-1651">validade
</span><span class="sxs-lookup"><span data-stu-id="6a857-1651">validade</span></span> 
- <span data-ttu-id="6a857-1652">valido hasta
</span><span class="sxs-lookup"><span data-stu-id="6a857-1652">valido hasta</span></span> 
- <span data-ttu-id="6a857-1653">valor
</span><span class="sxs-lookup"><span data-stu-id="6a857-1653">valor</span></span> 
- <span data-ttu-id="6a857-1654">venc
</span><span class="sxs-lookup"><span data-stu-id="6a857-1654">venc</span></span> 
- <span data-ttu-id="6a857-1655">vencimento
</span><span class="sxs-lookup"><span data-stu-id="6a857-1655">vencimento</span></span> 
- <span data-ttu-id="6a857-1656">vencimiento
</span><span class="sxs-lookup"><span data-stu-id="6a857-1656">vencimiento</span></span> 
- <span data-ttu-id="6a857-1657">verloopt
</span><span class="sxs-lookup"><span data-stu-id="6a857-1657">verloopt</span></span> 
- <span data-ttu-id="6a857-1658">vervaldag
</span><span class="sxs-lookup"><span data-stu-id="6a857-1658">vervaldag</span></span> 
- <span data-ttu-id="6a857-1659">vervaldatum
</span><span class="sxs-lookup"><span data-stu-id="6a857-1659">vervaldatum</span></span> 
- <span data-ttu-id="6a857-1660">vto
</span><span class="sxs-lookup"><span data-stu-id="6a857-1660">vto</span></span> 
- <span data-ttu-id="6a857-1661">válido hasta
</span><span class="sxs-lookup"><span data-stu-id="6a857-1661">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="6a857-1662">欧盟驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="6a857-1662">EU Driver's License Number</span></span>

<span data-ttu-id="6a857-1663">若要了解详细信息，请参阅[欧盟驱动程序驾驶证号码敏感信息类型](eu-driver-s-license-number.md)。</span><span class="sxs-lookup"><span data-stu-id="6a857-1663">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="6a857-1664">欧盟 National 标识号</span><span class="sxs-lookup"><span data-stu-id="6a857-1664">EU National Identification Number</span></span>

<span data-ttu-id="6a857-1665">若要了解详细信息，请参阅[欧盟国家/地区标识号敏感信息类型](eu-national-identification-number.md)。</span><span class="sxs-lookup"><span data-stu-id="6a857-1665">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="6a857-1666">欧盟护照号码</span><span class="sxs-lookup"><span data-stu-id="6a857-1666">EU Passport Number</span></span>

<span data-ttu-id="6a857-1667">若要了解详细信息，请参阅[欧盟护照号码敏感信息类型](eu-passport-number.md)。</span><span class="sxs-lookup"><span data-stu-id="6a857-1667">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="6a857-1668">欧盟社会保险号或等效 ID</span><span class="sxs-lookup"><span data-stu-id="6a857-1668">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="6a857-1669">若要了解详细信息，请参阅[欧盟社会保险号或等效 ID 敏感信息类型](eu-social-security-number-or-equivalent-id.md)。</span><span class="sxs-lookup"><span data-stu-id="6a857-1669">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="6a857-1670">欧盟纳税标识号</span><span class="sxs-lookup"><span data-stu-id="6a857-1670">EU Tax Identification Number</span></span>

<span data-ttu-id="6a857-1671">若要了解详细信息，请参阅[欧盟纳税标识号敏感信息类型](eu-tax-identification-number.md)。</span><span class="sxs-lookup"><span data-stu-id="6a857-1671">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="6a857-1672">芬兰国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="6a857-1672">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="6a857-1673">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-1673">Format</span></span>

<span data-ttu-id="6a857-1674">六个数字加一个字符（表示一个世纪），加三个数字再加一个校验位</span><span class="sxs-lookup"><span data-stu-id="6a857-1674">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-1675">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-1675">Pattern</span></span>

<span data-ttu-id="6a857-1676">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="6a857-1676">Pattern must include all of the following:</span></span>
- <span data-ttu-id="6a857-1677">采用 DDMMYY 格式的六位数字，表示出生日期</span><span class="sxs-lookup"><span data-stu-id="6a857-1677">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="6a857-1678">世纪标记（“-”、“+”或“a”）</span><span class="sxs-lookup"><span data-stu-id="6a857-1678">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="6a857-1679">三位个人标识号</span><span class="sxs-lookup"><span data-stu-id="6a857-1679">Three-digit personal identification number</span></span> 
- <span data-ttu-id="6a857-1680">一个数字或字母（区分大小写），是校验位</span><span class="sxs-lookup"><span data-stu-id="6a857-1680">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-1681">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-1681">Checksum</span></span>

<span data-ttu-id="6a857-1682">是</span><span class="sxs-lookup"><span data-stu-id="6a857-1682">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-1683">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-1683">Definition</span></span>

<span data-ttu-id="6a857-1684">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-1684">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-1685">函数 Func_finnish_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-1685">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-1686">找到 Keyword_finnish_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-1686">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="6a857-1687">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-1687">The checksum passes.</span></span>

```
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a857-1688">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-1688">Keywords</span></span>

- <span data-ttu-id="6a857-1689">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="6a857-1689">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="6a857-1690">

Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="6a857-1690">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="6a857-1691">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="6a857-1691">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="6a857-1692">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="6a857-1692">Personbeteckning</span></span>
- <span data-ttu-id="6a857-1693">Personnummer</span><span class="sxs-lookup"><span data-stu-id="6a857-1693">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="6a857-1694">芬兰护照号</span><span class="sxs-lookup"><span data-stu-id="6a857-1694">Finland Passport Number</span></span>

<span data-ttu-id="6a857-p130">设置格式的九个字母和数字模式的九个字母和数字的组合组合： 两个字母 （不区分大小写） 的第七位数字校验和无定义 DLP 策略为 75%确信，如果，它已检测到此类型的敏感信息，在两者之间300 个字符的邻近性： 正则表达式 Regex_finland_passport_number 找到与模式匹配的内容。找到从 Keyword_finland_passport_number 关键字。<!-- Finland Passport Number --> 
 <Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern> 
</Entity>关键字 Keyword_finland_passport_number Passport Passi</span><span class="sxs-lookup"><span data-stu-id="6a857-p130">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern. A keyword from Keyword_finland_passport_number is found. <!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity> Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="6a857-1699">法国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="6a857-1699">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-1700">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-1700">Format</span></span>

<span data-ttu-id="6a857-1701">12 个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-1701">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-1702">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-1702">Pattern</span></span>

<span data-ttu-id="6a857-1703">12 个数字，会对类似模式（如法国电话号码）进行验证</span><span class="sxs-lookup"><span data-stu-id="6a857-1703">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-1704">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-1704">Checksum</span></span>

<span data-ttu-id="6a857-1705">否</span><span class="sxs-lookup"><span data-stu-id="6a857-1705">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-1706">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-1706">Definition</span></span>

<span data-ttu-id="6a857-1707">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-1707">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-1708">函数 Func_french_drivers_license 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-1708">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-1709">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="6a857-1709">At least one of the following is true:</span></span>
- <span data-ttu-id="6a857-1710">找到 Keyword_french_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-1710">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="6a857-1711">函数 Func_eu_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="6a857-1711">The function Func_eu_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-1712">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-1712">Keywords</span></span>

#### <a name="keywordfrenchdriverslicense"></a><span data-ttu-id="6a857-1713">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="6a857-1713">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="6a857-1714">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6a857-1714">drivers licence</span></span>
- <span data-ttu-id="6a857-1715">drivers license</span><span class="sxs-lookup"><span data-stu-id="6a857-1715">drivers license</span></span>
- <span data-ttu-id="6a857-1716">driving licence
</span><span class="sxs-lookup"><span data-stu-id="6a857-1716">driving licence</span></span>
- <span data-ttu-id="6a857-1717">驱动许可证</span><span class="sxs-lookup"><span data-stu-id="6a857-1717">driving license</span></span>
- <span data-ttu-id="6a857-1718">
permis de conduire</span><span class="sxs-lookup"><span data-stu-id="6a857-1718">permis de conduire</span></span>
- <span data-ttu-id="6a857-1719">
licence number</span><span class="sxs-lookup"><span data-stu-id="6a857-1719">licence number</span></span>
- <span data-ttu-id="6a857-1720">
license number</span><span class="sxs-lookup"><span data-stu-id="6a857-1720">license number</span></span>
- <span data-ttu-id="6a857-1721">
licence numbers</span><span class="sxs-lookup"><span data-stu-id="6a857-1721">licence numbers</span></span>
- <span data-ttu-id="6a857-1722">

license numbers</span><span class="sxs-lookup"><span data-stu-id="6a857-1722">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="6a857-1723">法国国家/地区 ID 卡 (CNI)</span><span class="sxs-lookup"><span data-stu-id="6a857-1723">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="6a857-1724">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-1724">Format</span></span>

<span data-ttu-id="6a857-1725">12 个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-1725">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-1726">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-1726">Pattern</span></span>

<span data-ttu-id="6a857-1727">12 个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-1727">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-1728">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-1728">Checksum</span></span>

<span data-ttu-id="6a857-1729">否</span><span class="sxs-lookup"><span data-stu-id="6a857-1729">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-1730">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-1730">Definition</span></span>

<span data-ttu-id="6a857-1731">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-1731">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-1732">正则表达式 Regex_france_cni 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-1732">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a857-1733">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-1733">Keywords</span></span>

<span data-ttu-id="6a857-1734">无</span><span class="sxs-lookup"><span data-stu-id="6a857-1734">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="6a857-1735">法国护照号码</span><span class="sxs-lookup"><span data-stu-id="6a857-1735">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-1736">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-1736">Format</span></span>

<span data-ttu-id="6a857-1737">9 个数字和字母</span><span class="sxs-lookup"><span data-stu-id="6a857-1737">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-1738">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-1738">Pattern</span></span>

<span data-ttu-id="6a857-1739">九位数字和字母：</span><span class="sxs-lookup"><span data-stu-id="6a857-1739">Nine digits and letters:</span></span>
- <span data-ttu-id="6a857-1740">两位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-1740">Two digits</span></span> 
- <span data-ttu-id="6a857-1741">两个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="6a857-1741">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="6a857-1742">五位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-1742">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-1743">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-1743">Checksum</span></span>

<span data-ttu-id="6a857-1744">否</span><span class="sxs-lookup"><span data-stu-id="6a857-1744">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-1745">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-1745">Definition</span></span>

<span data-ttu-id="6a857-1746">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-1746">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-1747">函数 Func_fr_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-1747">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-1748">找到 Keyword_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-1748">A keyword from Keyword_passport is found.</span></span>

```
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a857-1749">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-1749">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="6a857-1750">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="6a857-1750">Keyword_passport</span></span>

- <span data-ttu-id="6a857-1751">Passport Number</span><span class="sxs-lookup"><span data-stu-id="6a857-1751">Passport Number</span></span>
- <span data-ttu-id="6a857-1752">
Passport No</span><span class="sxs-lookup"><span data-stu-id="6a857-1752">Passport No</span></span>
- <span data-ttu-id="6a857-1753">Passport #
</span><span class="sxs-lookup"><span data-stu-id="6a857-1753">Passport #</span></span>
- <span data-ttu-id="6a857-1754">Passport#
</span><span class="sxs-lookup"><span data-stu-id="6a857-1754">Passport#</span></span>
- <span data-ttu-id="6a857-1755">PassportID</span><span class="sxs-lookup"><span data-stu-id="6a857-1755">PassportID</span></span>
- <span data-ttu-id="6a857-1756">Passportno
</span><span class="sxs-lookup"><span data-stu-id="6a857-1756">Passportno</span></span>
- <span data-ttu-id="6a857-1757">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="6a857-1757">passportnumber</span></span>
- <span data-ttu-id="6a857-1758">パスポート</span><span class="sxs-lookup"><span data-stu-id="6a857-1758">パスポート</span></span>
- <span data-ttu-id="6a857-1759">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="6a857-1759">パスポート番号</span></span>
- <span data-ttu-id="6a857-1760">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="6a857-1760">パスポートのNum</span></span>
- <span data-ttu-id="6a857-1761">
パスポート ＃
</span><span class="sxs-lookup"><span data-stu-id="6a857-1761">パスポート ＃</span></span> 
- <span data-ttu-id="6a857-1762">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="6a857-1762">Numéro de passeport</span></span>
- <span data-ttu-id="6a857-1763">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="6a857-1763">Passeport n °</span></span>
- <span data-ttu-id="6a857-1764">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="6a857-1764">Passeport Non</span></span>
- <span data-ttu-id="6a857-1765">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="6a857-1765">Passeport #</span></span>
- <span data-ttu-id="6a857-1766">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="6a857-1766">Passeport#</span></span>
- <span data-ttu-id="6a857-1767">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="6a857-1767">PasseportNon</span></span>
- <span data-ttu-id="6a857-1768">

Passeportn °</span><span class="sxs-lookup"><span data-stu-id="6a857-1768">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="6a857-1769">法国社会保险号 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="6a857-1769">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="6a857-1770">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-1770">Format</span></span>

<span data-ttu-id="6a857-1771">15 个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-1771">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-1772">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-1772">Pattern</span></span>

<span data-ttu-id="6a857-1773">必须匹配两种模式之一：</span><span class="sxs-lookup"><span data-stu-id="6a857-1773">Must match one of two patterns:</span></span>
- <span data-ttu-id="6a857-1774">13 跟两位数字后跟一个空格的数字</span><span class="sxs-lookup"><span data-stu-id="6a857-1774">13 digits followed by a space followed by two digits</span></span></br>
<span data-ttu-id="6a857-1775">或</span><span class="sxs-lookup"><span data-stu-id="6a857-1775">or</span></span>
- <span data-ttu-id="6a857-1776">15 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="6a857-1776">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-1777">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-1777">Checksum</span></span>

<span data-ttu-id="6a857-1778">是</span><span class="sxs-lookup"><span data-stu-id="6a857-1778">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-1779">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-1779">Definition</span></span>

<span data-ttu-id="6a857-1780">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-1780">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-1781">函数 Func_french_insee 或 Func_fr_insee 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-1781">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-1782">找到 Keyword_fr_insee 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-1782">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="6a857-1783">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-1783">The checksum passes.</span></span>

<span data-ttu-id="6a857-1784">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-1784">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-1785">函数 Func_french_insee 或 Func_fr_insee 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-1785">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-1786">未找到 Keyword_fr_insee 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-1786">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="6a857-1787">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-1787">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-1788">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-1788">Keywords</span></span>

#### <a name="keywordfrinsee"></a><span data-ttu-id="6a857-1789">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="6a857-1789">Keyword_fr_insee</span></span>

- <span data-ttu-id="6a857-1790">insee</span><span class="sxs-lookup"><span data-stu-id="6a857-1790">insee</span></span>
- <span data-ttu-id="6a857-1791">
securité sociale</span><span class="sxs-lookup"><span data-stu-id="6a857-1791">securité sociale</span></span>
- <span data-ttu-id="6a857-1792">
securite sociale</span><span class="sxs-lookup"><span data-stu-id="6a857-1792">securite sociale</span></span>
- <span data-ttu-id="6a857-1793">
national id</span><span class="sxs-lookup"><span data-stu-id="6a857-1793">national id</span></span>
- <span data-ttu-id="6a857-1794">
national identification</span><span class="sxs-lookup"><span data-stu-id="6a857-1794">national identification</span></span>
- <span data-ttu-id="6a857-1795">
numéro d identité</span><span class="sxs-lookup"><span data-stu-id="6a857-1795">numéro d'identité</span></span>
- <span data-ttu-id="6a857-1796">没有 d'identité</span><span class="sxs-lookup"><span data-stu-id="6a857-1796">no d'identité</span></span>
- <span data-ttu-id="6a857-p131">
no. d'identité</span><span class="sxs-lookup"><span data-stu-id="6a857-p131">no. d'identité</span></span>
- <span data-ttu-id="6a857-1799">
numero d'identite</span><span class="sxs-lookup"><span data-stu-id="6a857-1799">numero d'identite</span></span>
- <span data-ttu-id="6a857-1800">没有 d'identite</span><span class="sxs-lookup"><span data-stu-id="6a857-1800">no d'identite</span></span>
- <span data-ttu-id="6a857-p132">
no. d'identite</span><span class="sxs-lookup"><span data-stu-id="6a857-p132">no. d'identite</span></span>
- <span data-ttu-id="6a857-1803">social security number
</span><span class="sxs-lookup"><span data-stu-id="6a857-1803">social security number</span></span>
- <span data-ttu-id="6a857-1804">
social security code</span><span class="sxs-lookup"><span data-stu-id="6a857-1804">social security code</span></span>
- <span data-ttu-id="6a857-1805">social insurance number</span><span class="sxs-lookup"><span data-stu-id="6a857-1805">social insurance number</span></span>
- <span data-ttu-id="6a857-1806">
le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="6a857-1806">le numéro d'identification nationale</span></span>
- <span data-ttu-id="6a857-1807">
d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="6a857-1807">d'identité nationale</span></span>
- <span data-ttu-id="6a857-1808">
numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="6a857-1808">numéro de sécurité sociale</span></span>
- <span data-ttu-id="6a857-1809">
le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="6a857-1809">le code de la sécurité sociale</span></span>
- <span data-ttu-id="6a857-1810">
numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="6a857-1810">numéro d'assurance sociale</span></span>
- <span data-ttu-id="6a857-1811">
numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="6a857-1811">numéro de sécu</span></span>
- <span data-ttu-id="6a857-1812">
code sécu
</span><span class="sxs-lookup"><span data-stu-id="6a857-1812">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="6a857-1813">德国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="6a857-1813">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-1814">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-1814">Format</span></span>

<span data-ttu-id="6a857-1815">11 个数字和字母组合</span><span class="sxs-lookup"><span data-stu-id="6a857-1815">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-1816">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-1816">Pattern</span></span>

<span data-ttu-id="6a857-1817">11 位数字和字母（不区分大小写）：</span><span class="sxs-lookup"><span data-stu-id="6a857-1817">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="6a857-1818">一个数字或字母</span><span class="sxs-lookup"><span data-stu-id="6a857-1818">A digit or letter</span></span> 
- <span data-ttu-id="6a857-1819">两位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-1819">Two digits</span></span> 
- <span data-ttu-id="6a857-1820">六位数字或字母</span><span class="sxs-lookup"><span data-stu-id="6a857-1820">Six digits or letters</span></span> 
- <span data-ttu-id="6a857-1821">一位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-1821">A digit</span></span> 
- <span data-ttu-id="6a857-1822">一个数字或字母</span><span class="sxs-lookup"><span data-stu-id="6a857-1822">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-1823">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-1823">Checksum</span></span>

<span data-ttu-id="6a857-1824">是</span><span class="sxs-lookup"><span data-stu-id="6a857-1824">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-1825">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-1825">Definition</span></span>

<span data-ttu-id="6a857-1826">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-1826">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-1827">函数 Func_german_drivers_license 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-1827">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-1828">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="6a857-1828">At least one of the following is true:</span></span>
    - <span data-ttu-id="6a857-1829">找到 Keyword_german_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-1829">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="6a857-1830">找到 Keyword_german_drivers_license_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-1830">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="6a857-1831">找到 Keyword_german_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-1831">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="6a857-1832">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-1832">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-1833">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-1833">Keywords</span></span>

#### <a name="keywordgermandriverslicensenumber"></a><span data-ttu-id="6a857-1834">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="6a857-1834">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="6a857-1835">Führerschein</span><span class="sxs-lookup"><span data-stu-id="6a857-1835">Führerschein</span></span>
- <span data-ttu-id="6a857-1836">
Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="6a857-1836">Fuhrerschein</span></span>
- <span data-ttu-id="6a857-1837">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="6a857-1837">Fuehrerschein</span></span>
- <span data-ttu-id="6a857-1838">
Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="6a857-1838">Führerscheinnummer</span></span>
- <span data-ttu-id="6a857-1839">
Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="6a857-1839">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="6a857-1840">
Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="6a857-1840">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="6a857-1841">
Führerschein-
</span><span class="sxs-lookup"><span data-stu-id="6a857-1841">Führerschein-</span></span> 
- <span data-ttu-id="6a857-1842">Fuhrerschein-
</span><span class="sxs-lookup"><span data-stu-id="6a857-1842">Fuhrerschein-</span></span> 
- <span data-ttu-id="6a857-1843">Fuehrerschein-
</span><span class="sxs-lookup"><span data-stu-id="6a857-1843">Fuehrerschein-</span></span> 
- <span data-ttu-id="6a857-1844">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="6a857-1844">FührerscheinnummerNr</span></span>
- <span data-ttu-id="6a857-1845">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="6a857-1845">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="6a857-1846">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="6a857-1846">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="6a857-1847">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="6a857-1847">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="6a857-1848">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="6a857-1848">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="6a857-1849">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="6a857-1849">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="6a857-1850">Führerschein-Nr
</span><span class="sxs-lookup"><span data-stu-id="6a857-1850">Führerschein- Nr</span></span>
- <span data-ttu-id="6a857-1851">Fuhrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="6a857-1851">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="6a857-1852">Fuehrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="6a857-1852">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="6a857-1853">Führerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="6a857-1853">Führerschein- Klasse</span></span> 
- <span data-ttu-id="6a857-1854">Fuhrerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="6a857-1854">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="6a857-1855">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="6a857-1855">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="6a857-1856">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="6a857-1856">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="6a857-1857">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="6a857-1857">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="6a857-1858">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="6a857-1858">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="6a857-1859">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="6a857-1859">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="6a857-1860">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="6a857-1860">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="6a857-1861">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="6a857-1861">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="6a857-1862">Führerschein-Nr
</span><span class="sxs-lookup"><span data-stu-id="6a857-1862">Führerschein- Nr</span></span> 
- <span data-ttu-id="6a857-1863">Fuhrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="6a857-1863">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="6a857-1864">Fuehrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="6a857-1864">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="6a857-1865">Führerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="6a857-1865">Führerschein- Klasse</span></span> 
- <span data-ttu-id="6a857-1866">Fuhrerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="6a857-1866">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="6a857-1867">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="6a857-1867">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="6a857-1868">DL</span><span class="sxs-lookup"><span data-stu-id="6a857-1868">DL</span></span> 
- <span data-ttu-id="6a857-1869">DLS</span><span class="sxs-lookup"><span data-stu-id="6a857-1869">DLS</span></span>
- <span data-ttu-id="6a857-1870">
Driv Lic
</span><span class="sxs-lookup"><span data-stu-id="6a857-1870">Driv Lic</span></span> 
- <span data-ttu-id="6a857-1871">Driv Licen
</span><span class="sxs-lookup"><span data-stu-id="6a857-1871">Driv Licen</span></span> 
- <span data-ttu-id="6a857-1872">Driv License</span><span class="sxs-lookup"><span data-stu-id="6a857-1872">Driv License</span></span>
- <span data-ttu-id="6a857-1873">
Driv Licenses
</span><span class="sxs-lookup"><span data-stu-id="6a857-1873">Driv Licenses</span></span> 
- <span data-ttu-id="6a857-1874">Driv Licence
</span><span class="sxs-lookup"><span data-stu-id="6a857-1874">Driv Licence</span></span> 
- <span data-ttu-id="6a857-1875">Driv Licences
</span><span class="sxs-lookup"><span data-stu-id="6a857-1875">Driv Licences</span></span> 
- <span data-ttu-id="6a857-1876">Driv Lic
</span><span class="sxs-lookup"><span data-stu-id="6a857-1876">Driv Lic</span></span> 
- <span data-ttu-id="6a857-1877">Driver Licen
</span><span class="sxs-lookup"><span data-stu-id="6a857-1877">Driver Licen</span></span> 
- <span data-ttu-id="6a857-1878">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="6a857-1878">Driver License</span></span> 
- <span data-ttu-id="6a857-1879">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="6a857-1879">Driver Licenses</span></span> 
- <span data-ttu-id="6a857-1880">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="6a857-1880">Driver Licence</span></span> 
- <span data-ttu-id="6a857-1881">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="6a857-1881">Driver Licences</span></span> 
- <span data-ttu-id="6a857-1882">驱动因素 Lic</span><span class="sxs-lookup"><span data-stu-id="6a857-1882">Drivers Lic</span></span> 
- <span data-ttu-id="6a857-1883">驱动因素 Licen</span><span class="sxs-lookup"><span data-stu-id="6a857-1883">Drivers Licen</span></span> 
- <span data-ttu-id="6a857-1884">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="6a857-1884">Drivers License</span></span> 
- <span data-ttu-id="6a857-1885">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="6a857-1885">Drivers Licenses</span></span> 
- <span data-ttu-id="6a857-1886">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="6a857-1886">Drivers Licence</span></span> 
- <span data-ttu-id="6a857-1887">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="6a857-1887">Drivers Licences</span></span> 
- <span data-ttu-id="6a857-1888">驱动因素的 Lic</span><span class="sxs-lookup"><span data-stu-id="6a857-1888">Driver's Lic</span></span> 
- <span data-ttu-id="6a857-1889">Driver's Licen
</span><span class="sxs-lookup"><span data-stu-id="6a857-1889">Driver's Licen</span></span> 
- <span data-ttu-id="6a857-1890">驱动程序的许可证</span><span class="sxs-lookup"><span data-stu-id="6a857-1890">Driver's License</span></span> 
- <span data-ttu-id="6a857-1891">驱动程序的许可证</span><span class="sxs-lookup"><span data-stu-id="6a857-1891">Driver's Licenses</span></span> 
- <span data-ttu-id="6a857-1892">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="6a857-1892">Driver's Licence</span></span> 
- <span data-ttu-id="6a857-1893">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="6a857-1893">Driver's Licences</span></span> 
- <span data-ttu-id="6a857-1894">Driving Lic
</span><span class="sxs-lookup"><span data-stu-id="6a857-1894">Driving Lic</span></span> 
- <span data-ttu-id="6a857-1895">Driving Licen
</span><span class="sxs-lookup"><span data-stu-id="6a857-1895">Driving Licen</span></span> 
- <span data-ttu-id="6a857-1896">Driving License
</span><span class="sxs-lookup"><span data-stu-id="6a857-1896">Driving License</span></span> 
- <span data-ttu-id="6a857-1897">Driving Licenses
</span><span class="sxs-lookup"><span data-stu-id="6a857-1897">Driving Licenses</span></span> 
- <span data-ttu-id="6a857-1898">Driving Licence

</span><span class="sxs-lookup"><span data-stu-id="6a857-1898">Driving Licence</span></span> 
- <span data-ttu-id="6a857-1899">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="6a857-1899">Driving Licences</span></span>

#### <a name="keywordgermandriverslicensecollaborative"></a><span data-ttu-id="6a857-1900">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="6a857-1900">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="6a857-1901">
Nr-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="6a857-1901">Nr-Führerschein</span></span> 
- <span data-ttu-id="6a857-1902">Nr-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="6a857-1902">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="6a857-1903">Nr-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="6a857-1903">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="6a857-1904">No-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="6a857-1904">No-Führerschein</span></span> 
- <span data-ttu-id="6a857-1905">No-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="6a857-1905">No-Fuhrerschein</span></span> 
- <span data-ttu-id="6a857-1906">No-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="6a857-1906">No-Fuehrerschein</span></span> 
- <span data-ttu-id="6a857-1907">N-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="6a857-1907">N-Führerschein</span></span> 
- <span data-ttu-id="6a857-1908">N-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="6a857-1908">N-Fuhrerschein</span></span> 
- <span data-ttu-id="6a857-1909">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="6a857-1909">N-Fuehrerschein</span></span>
- <span data-ttu-id="6a857-1910">
Nr-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="6a857-1910">Nr-Führerschein</span></span> 
- <span data-ttu-id="6a857-1911">Nr-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="6a857-1911">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="6a857-1912">Nr-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="6a857-1912">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="6a857-1913">No-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="6a857-1913">No-Führerschein</span></span> 
- <span data-ttu-id="6a857-1914">No-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="6a857-1914">No-Fuhrerschein</span></span> 
- <span data-ttu-id="6a857-1915">No-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="6a857-1915">No-Fuehrerschein</span></span> 
- <span data-ttu-id="6a857-1916">N-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="6a857-1916">N-Führerschein</span></span> 
- <span data-ttu-id="6a857-1917">N-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="6a857-1917">N-Fuhrerschein</span></span> 
- <span data-ttu-id="6a857-1918">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="6a857-1918">N-Fuehrerschein</span></span> 

#### <a name="keywordgermandriverslicense"></a><span data-ttu-id="6a857-1919">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="6a857-1919">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="6a857-1920">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="6a857-1920">ausstellungsdatum</span></span>
- <span data-ttu-id="6a857-1921">
ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="6a857-1921">ausstellungsort</span></span>
- <span data-ttu-id="6a857-1922">
ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="6a857-1922">ausstellende behöde</span></span>
- <span data-ttu-id="6a857-1923">
ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="6a857-1923">ausstellende behorde</span></span>
- <span data-ttu-id="6a857-1924">

ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="6a857-1924">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="6a857-1925">德国护照号码</span><span class="sxs-lookup"><span data-stu-id="6a857-1925">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-1926">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-1926">Format</span></span>

<span data-ttu-id="6a857-1927">10 个数字或字母</span><span class="sxs-lookup"><span data-stu-id="6a857-1927">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-1928">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-1928">Pattern</span></span>

<span data-ttu-id="6a857-1929">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="6a857-1929">Pattern must include all of the following:</span></span>
- <span data-ttu-id="6a857-1930">第一个字符是这一组（C、F、G、H、J、K）中的数字或字母</span><span class="sxs-lookup"><span data-stu-id="6a857-1930">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="6a857-1931">三位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-1931">Three digits</span></span> 
- <span data-ttu-id="6a857-1932">五位数字或字母都来源于这一组（C、-H、J-N、P、R、T，V-Z）</span><span class="sxs-lookup"><span data-stu-id="6a857-1932">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="6a857-1933">一位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-1933">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-1934">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-1934">Checksum</span></span>

<span data-ttu-id="6a857-1935">是</span><span class="sxs-lookup"><span data-stu-id="6a857-1935">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-1936">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-1936">Definition</span></span>

<span data-ttu-id="6a857-1937">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-1937">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-1938">函数 Func_german_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-1938">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-1939">找到以下任意五个关键字列表中的关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-1939">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="6a857-1940">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-1940">The checksum passes.</span></span>

<span data-ttu-id="6a857-1941">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-1941">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-1942">函数 Func_german_passport_data 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-1942">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-1943">找到以下任意五个关键字列表中的关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-1943">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="6a857-1944">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-1944">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-1945">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-1945">Keywords</span></span>

#### <a name="keywordgermanpassport"></a><span data-ttu-id="6a857-1946">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="6a857-1946">Keyword_german_passport</span></span>

- <span data-ttu-id="6a857-1947">reisepass</span><span class="sxs-lookup"><span data-stu-id="6a857-1947">reisepass</span></span>
- <span data-ttu-id="6a857-1948">
reisepasse</span><span class="sxs-lookup"><span data-stu-id="6a857-1948">reisepasse</span></span>
- <span data-ttu-id="6a857-1949">
reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="6a857-1949">reisepassnummer</span></span>
- <span data-ttu-id="6a857-1950">passport</span><span class="sxs-lookup"><span data-stu-id="6a857-1950">passport</span></span>
- <span data-ttu-id="6a857-1951">

passports</span><span class="sxs-lookup"><span data-stu-id="6a857-1951">passports</span></span>

#### <a name="keywordgermanpassportcollaborative"></a><span data-ttu-id="6a857-1952">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="6a857-1952">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="6a857-1953">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="6a857-1953">geburtsdatum</span></span>
- <span data-ttu-id="6a857-1954">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="6a857-1954">ausstellungsdatum</span></span>
- <span data-ttu-id="6a857-1955">
ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="6a857-1955">ausstellungsort</span></span>

#### <a name="keywordgermanpassportnumber"></a><span data-ttu-id="6a857-1956">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="6a857-1956">Keyword_german_passport_number</span></span>

<span data-ttu-id="6a857-1957">不-Reisepass Nr Reisepass</span><span class="sxs-lookup"><span data-stu-id="6a857-1957">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keywordgermanpassport1"></a><span data-ttu-id="6a857-1958">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="6a857-1958">Keyword_german_passport1</span></span>

<span data-ttu-id="6a857-1959">Reisepass-Nr
</span><span class="sxs-lookup"><span data-stu-id="6a857-1959">Reisepass-Nr</span></span>

#### <a name="keywordgermanpassport2"></a><span data-ttu-id="6a857-1960">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="6a857-1960">Keyword_german_passport2</span></span>

<span data-ttu-id="6a857-1961">bnationalit.t</span><span class="sxs-lookup"><span data-stu-id="6a857-1961">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="6a857-1962">德国身份证号码</span><span class="sxs-lookup"><span data-stu-id="6a857-1962">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-1963">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-1963">Format</span></span>

<span data-ttu-id="6a857-1964">2010 年 11 月 1 相： 九个字母和数字</span><span class="sxs-lookup"><span data-stu-id="6a857-1964">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="6a857-1965">从直到 31 年 10 月 2010年: 10 位数字 1 年 4 月 1987</span><span class="sxs-lookup"><span data-stu-id="6a857-1965">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-1966">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-1966">Pattern</span></span>

<span data-ttu-id="6a857-1967">自 2010 年 11 月 1 日起：</span><span class="sxs-lookup"><span data-stu-id="6a857-1967">Since 1 November 2010:</span></span>
- <span data-ttu-id="6a857-1968">一个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="6a857-1968">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="6a857-1969">八个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-1969">Eight digits</span></span>

<span data-ttu-id="6a857-1970">从直到 31 2010 年 10 月 1 年 4 月 1987:</span><span class="sxs-lookup"><span data-stu-id="6a857-1970">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="6a857-1971">10 个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-1971">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-1972">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-1972">Checksum</span></span>

<span data-ttu-id="6a857-1973">否</span><span class="sxs-lookup"><span data-stu-id="6a857-1973">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-1974">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-1974">Definition</span></span>

<span data-ttu-id="6a857-1975">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-1975">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-1976">正则表达式 Regex_germany_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-1976">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-1977">找到 Keyword_germany_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-1977">A keyword from Keyword_germany_id_card is found.</span></span>

```
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a857-1978">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-1978">Keywords</span></span>

#### <a name="keywordgermanyidcard"></a><span data-ttu-id="6a857-1979">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="6a857-1979">Keyword_germany_id_card</span></span>

- <span data-ttu-id="6a857-1980">Identity Card</span><span class="sxs-lookup"><span data-stu-id="6a857-1980">Identity Card</span></span>
- <span data-ttu-id="6a857-1981">ID</span><span class="sxs-lookup"><span data-stu-id="6a857-1981">ID</span></span>
- <span data-ttu-id="6a857-1982">Identification</span><span class="sxs-lookup"><span data-stu-id="6a857-1982">Identification</span></span>
- <span data-ttu-id="6a857-1983">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="6a857-1983">Personalausweis</span></span>
- <span data-ttu-id="6a857-1984">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="6a857-1984">Identifizierungsnummer</span></span>
- <span data-ttu-id="6a857-1985">Ausweis</span><span class="sxs-lookup"><span data-stu-id="6a857-1985">Ausweis</span></span>
- <span data-ttu-id="6a857-1986">Identifikation</span><span class="sxs-lookup"><span data-stu-id="6a857-1986">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="6a857-1987">希腊国家 ID 卡</span><span class="sxs-lookup"><span data-stu-id="6a857-1987">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="6a857-1988">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-1988">Format</span></span>

<span data-ttu-id="6a857-1989">7-8 个字母和数字组合加一个短划线</span><span class="sxs-lookup"><span data-stu-id="6a857-1989">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-1990">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-1990">Pattern</span></span>

<span data-ttu-id="6a857-1991">七个字母和数字（旧格式）：</span><span class="sxs-lookup"><span data-stu-id="6a857-1991">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="6a857-1992">一个字母（希腊字母表中的任一字母） </span><span class="sxs-lookup"><span data-stu-id="6a857-1992">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="6a857-1993">一个短划线 </span><span class="sxs-lookup"><span data-stu-id="6a857-1993">A dash</span></span> 
- <span data-ttu-id="6a857-1994">六个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-1994">Six digits</span></span>

<span data-ttu-id="6a857-1995">八个字母和数字（新格式）：</span><span class="sxs-lookup"><span data-stu-id="6a857-1995">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="6a857-1996">大写字符同时出现在希腊和拉丁字母表中的两个字母 (ABEZHIKMNOPTYX) </span><span class="sxs-lookup"><span data-stu-id="6a857-1996">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="6a857-1997">一个短划线 </span><span class="sxs-lookup"><span data-stu-id="6a857-1997">A dash</span></span> 
- <span data-ttu-id="6a857-1998">六个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-1998">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-1999">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-1999">Checksum</span></span>

<span data-ttu-id="6a857-2000">否</span><span class="sxs-lookup"><span data-stu-id="6a857-2000">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2001">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2001">Definition</span></span>

<span data-ttu-id="6a857-2002">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2002">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2003">正则表达式 Regex_greece_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2003">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2004">找到 Keyword_greece_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2004">A keyword from Keyword_greece_id_card is found.</span></span>

```
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a857-2005">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2005">Keywords</span></span>

#### <a name="keywordgreeceidcard"></a><span data-ttu-id="6a857-2006">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="6a857-2006">Keyword_greece_id_card</span></span>

- <span data-ttu-id="6a857-2007">Greek identity Card</span><span class="sxs-lookup"><span data-stu-id="6a857-2007">Greek identity Card</span></span>
- <span data-ttu-id="6a857-2008">Tautotita</span><span class="sxs-lookup"><span data-stu-id="6a857-2008">Tautotita</span></span>
- <span data-ttu-id="6a857-2009">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="6a857-2009">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="6a857-2010">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="6a857-2010">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="6a857-2011">香港身份证 (HKID) 号</span><span class="sxs-lookup"><span data-stu-id="6a857-2011">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2012">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2012">Format</span></span>

<span data-ttu-id="6a857-2013">8-9 个字母和数字组合，最后一个字符两边可选择加括号</span><span class="sxs-lookup"><span data-stu-id="6a857-2013">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2014">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2014">Pattern</span></span>

<span data-ttu-id="6a857-2015">8-9 个字母组合：</span><span class="sxs-lookup"><span data-stu-id="6a857-2015">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="6a857-2016">1-2 个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="6a857-2016">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="6a857-2017">六个数字 </span><span class="sxs-lookup"><span data-stu-id="6a857-2017">Six digits</span></span> 
- <span data-ttu-id="6a857-2018">最后一个字符（任意数字或字母 A）是校验位，两边可以选择加括号。</span><span class="sxs-lookup"><span data-stu-id="6a857-2018">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2019">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2019">Checksum</span></span>

<span data-ttu-id="6a857-2020">是</span><span class="sxs-lookup"><span data-stu-id="6a857-2020">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2021">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2021">Definition</span></span>

<span data-ttu-id="6a857-2022">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2022">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2023">函数 Func_hong_kong_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2023">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2024">找到 Keyword_hong_kong_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2024">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="6a857-2025">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-2025">The checksum passes.</span></span>

<span data-ttu-id="6a857-2026">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2026">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2027">函数 Func_hong_kong_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2027">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2028">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-2028">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-2029">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2029">Keywords</span></span>

#### <a name="keywordhongkongidcard"></a><span data-ttu-id="6a857-2030">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="6a857-2030">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="6a857-2031">Hong Kong Identity Card</span><span class="sxs-lookup"><span data-stu-id="6a857-2031">Hong Kong Identity Card</span></span>
- <span data-ttu-id="6a857-2032">HKID</span><span class="sxs-lookup"><span data-stu-id="6a857-2032">HKID</span></span>
- <span data-ttu-id="6a857-2033">ID card</span><span class="sxs-lookup"><span data-stu-id="6a857-2033">ID card</span></span>
- <span data-ttu-id="6a857-2034">香港身份證
</span><span class="sxs-lookup"><span data-stu-id="6a857-2034">香港身份證</span></span> 
- <span data-ttu-id="6a857-2035">香港永久性居民身份證
</span><span class="sxs-lookup"><span data-stu-id="6a857-2035">香港永久性居民身份證</span></span> 
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="6a857-2036">印度永久帐号 (PAN)</span><span class="sxs-lookup"><span data-stu-id="6a857-2036">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2037">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2037">Format</span></span>

<span data-ttu-id="6a857-2038">10 个字母或数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2038">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2039">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2039">Pattern</span></span>

<span data-ttu-id="6a857-2040">10 个字母或数字：</span><span class="sxs-lookup"><span data-stu-id="6a857-2040">10 letters or digits:</span></span>
- <span data-ttu-id="6a857-2041">五个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="6a857-2041">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="6a857-2042">四个数字 </span><span class="sxs-lookup"><span data-stu-id="6a857-2042">Four digits</span></span> 
- <span data-ttu-id="6a857-2043">一个字母，是字母校验位</span><span class="sxs-lookup"><span data-stu-id="6a857-2043">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2044">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2044">Checksum</span></span>

<span data-ttu-id="6a857-2045">是</span><span class="sxs-lookup"><span data-stu-id="6a857-2045">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2046">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2046">Definition</span></span>

<span data-ttu-id="6a857-2047">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2047">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2048">正则表达式 Regex_india_permanent_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2048">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2049">找到 Keyword_india_permanent_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2049">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="6a857-2050">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-2050">The checksum passes.</span></span>

```
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a857-2051">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2051">Keywords</span></span>

#### <a name="keywordindiapermanentaccountnumber"></a><span data-ttu-id="6a857-2052">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="6a857-2052">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="6a857-2053">Permanent Account Number
</span><span class="sxs-lookup"><span data-stu-id="6a857-2053">Permanent Account Number</span></span> 
- <span data-ttu-id="6a857-2054">PAN
</span><span class="sxs-lookup"><span data-stu-id="6a857-2054">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="6a857-2055">India Unique Identification (Aadhaar) Number</span><span class="sxs-lookup"><span data-stu-id="6a857-2055">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2056">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2056">Format</span></span>

<span data-ttu-id="6a857-2057">12 个数字（包含可选空格或短划线）</span><span class="sxs-lookup"><span data-stu-id="6a857-2057">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2058">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2058">Pattern</span></span>

<span data-ttu-id="6a857-2059">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="6a857-2059">12 digits:</span></span>
- <span data-ttu-id="6a857-2060">四个数字 </span><span class="sxs-lookup"><span data-stu-id="6a857-2060">Four digits</span></span> 
- <span data-ttu-id="6a857-2061">一个可选空格或短划线 </span><span class="sxs-lookup"><span data-stu-id="6a857-2061">An optional space or dash</span></span> 
- <span data-ttu-id="6a857-2062">四个数字 </span><span class="sxs-lookup"><span data-stu-id="6a857-2062">Four digits</span></span> 
- <span data-ttu-id="6a857-2063">一个可选空格或短划线 </span><span class="sxs-lookup"><span data-stu-id="6a857-2063">An optional space or dash</span></span> 
- <span data-ttu-id="6a857-2064">最后一个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="6a857-2064">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2065">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2065">Checksum</span></span>

<span data-ttu-id="6a857-2066">是</span><span class="sxs-lookup"><span data-stu-id="6a857-2066">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2067">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2067">Definition</span></span>

<span data-ttu-id="6a857-p133">DLP 策略是 85%相信它已检测到此类型的敏感信息 if、 内 300 个字符的邻近度： 函数 Func_india_aadhaar 查找与模式匹配的内容。找到从 Keyword_india_aadhar 关键字。将传递校验和。DLP 策略是相信它已检测到此类型的敏感信息的 75 %if、 内 300 个字符的邻近度： 函数 Func_india_aadhaar 查找与模式匹配的内容。将传递校验和。<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="6a857-p133">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern. A keyword from Keyword_india_aadhar is found. The checksum passes. A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern. The checksum passes. <!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span></span>

### <a name="keywords"></a><span data-ttu-id="6a857-2074">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2074">Keywords</span></span>
   
#### <a name="keywordindiaaadhar"></a><span data-ttu-id="6a857-2075">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="6a857-2075">Keyword_india_aadhar</span></span>
- <span data-ttu-id="6a857-2076">Aadhar</span><span class="sxs-lookup"><span data-stu-id="6a857-2076">Aadhar</span></span>
- <span data-ttu-id="6a857-2077">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="6a857-2077">Aadhaar</span></span>
- <span data-ttu-id="6a857-2078">UID</span><span class="sxs-lookup"><span data-stu-id="6a857-2078">UID</span></span>
- <span data-ttu-id="6a857-2079">आधार</span><span class="sxs-lookup"><span data-stu-id="6a857-2079">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="6a857-2080">印度尼西亚身份证 (KTP) 号</span><span class="sxs-lookup"><span data-stu-id="6a857-2080">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2081">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2081">Format</span></span>

<span data-ttu-id="6a857-2082">16 个数字（包含可选点）</span><span class="sxs-lookup"><span data-stu-id="6a857-2082">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2083">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2083">Pattern</span></span>

<span data-ttu-id="6a857-2084">16 个数字：</span><span class="sxs-lookup"><span data-stu-id="6a857-2084">16 digits:</span></span>
- <span data-ttu-id="6a857-2085">两位省代码 </span><span class="sxs-lookup"><span data-stu-id="6a857-2085">Two-digit province code</span></span> 
- <span data-ttu-id="6a857-2086">一个点（可选） </span><span class="sxs-lookup"><span data-stu-id="6a857-2086">A period (optional)</span></span> 
- <span data-ttu-id="6a857-2087">两位摄政统治区或城市代码 </span><span class="sxs-lookup"><span data-stu-id="6a857-2087">Two-digit regency or city code</span></span> 
- <span data-ttu-id="6a857-2088">两位住宅小区代码 </span><span class="sxs-lookup"><span data-stu-id="6a857-2088">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="6a857-2089">一个点（可选） </span><span class="sxs-lookup"><span data-stu-id="6a857-2089">A period (optional)</span></span> 
- <span data-ttu-id="6a857-2090">六个数字，采用  DDMMYY 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="6a857-2090">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="6a857-2091">一个点（可选） </span><span class="sxs-lookup"><span data-stu-id="6a857-2091">A period (optional)</span></span> 
- <span data-ttu-id="6a857-2092">四个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2092">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2093">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2093">Checksum</span></span>

<span data-ttu-id="6a857-2094">否</span><span class="sxs-lookup"><span data-stu-id="6a857-2094">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2095">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2095">Definition</span></span>

<span data-ttu-id="6a857-2096">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2096">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2097">正则表达式 Regex_indonesia_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2097">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2098">找到 Keyword_indonesia_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2098">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="6a857-2099">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2099">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2100">正则表达式 Regex_indonesia_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2100">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-2101">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2101">Keywords</span></span>
   
#### <a name="keywordindonesiaidcard"></a><span data-ttu-id="6a857-2102">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="6a857-2102">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="6a857-2103">KTP</span><span class="sxs-lookup"><span data-stu-id="6a857-2103">KTP</span></span>
- <span data-ttu-id="6a857-2104">Kartu Tanda Penduduk
</span><span class="sxs-lookup"><span data-stu-id="6a857-2104">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="6a857-2105">Nomor Induk Kependudukan
</span><span class="sxs-lookup"><span data-stu-id="6a857-2105">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="6a857-2106">国际银行帐号 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="6a857-2106">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2107">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2107">Format</span></span>

<span data-ttu-id="6a857-2108">国家/地区代码（两个字母）加校验位（两个数字）以及 bban 号码（最多 30 个字符）</span><span class="sxs-lookup"><span data-stu-id="6a857-2108">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2109">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2109">Pattern</span></span>

<span data-ttu-id="6a857-2110">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="6a857-2110">Pattern must include all of the following:</span></span>

- <span data-ttu-id="6a857-2111">两个字母的国家/地区代码</span><span class="sxs-lookup"><span data-stu-id="6a857-2111">Two-letter country code</span></span>
- <span data-ttu-id="6a857-2112">两个校验位（后跟一个可选空间） </span><span class="sxs-lookup"><span data-stu-id="6a857-2112">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="6a857-2113">1-7 个包含 4 个字母或数字的组（可以使用空格进行分隔）</span><span class="sxs-lookup"><span data-stu-id="6a857-2113">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="6a857-2114">1-3 个字母或数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2114">1-3 letters or digits</span></span>

<span data-ttu-id="6a857-p134">每个国家/地区的格式稍有不同。IBAN 敏感信息类型涵盖这 60 个国家/地区：</span><span class="sxs-lookup"><span data-stu-id="6a857-p134">The format for each country is slightly different. The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="6a857-2117">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span><span class="sxs-lookup"><span data-stu-id="6a857-2117">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2118">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2118">Checksum</span></span>

<span data-ttu-id="6a857-2119">是</span><span class="sxs-lookup"><span data-stu-id="6a857-2119">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2120">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2120">Definition</span></span>

<span data-ttu-id="6a857-2121">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2121">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2122">函数 Func_iban 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2122">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2123">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-2123">The checksum passes.</span></span>

```
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a857-2124">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2124">Keywords</span></span>

<span data-ttu-id="6a857-2125">无</span><span class="sxs-lookup"><span data-stu-id="6a857-2125">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="6a857-2126">IP 地址</span><span class="sxs-lookup"><span data-stu-id="6a857-2126">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2127">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2127">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="6a857-2128">IPv4：</span><span class="sxs-lookup"><span data-stu-id="6a857-2128">IPv4:</span></span>
<span data-ttu-id="6a857-2129">解释 IPv4 地址格式化（点）版本或非格式化（没有点）版本的复杂模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2129">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="6a857-2130">IPv6：</span><span class="sxs-lookup"><span data-stu-id="6a857-2130">IPv6:</span></span>
<span data-ttu-id="6a857-2131"> 解释格式化 IPv6 号码（包含冒号）的复杂模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2131">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2132">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2132">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2133">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2133">Checksum</span></span>

<span data-ttu-id="6a857-2134">否</span><span class="sxs-lookup"><span data-stu-id="6a857-2134">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2135">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2135">Definition</span></span>

<span data-ttu-id="6a857-2136">对于 IPv6，在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2136">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2137">正则表达式 Regex_ipv6_address 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2137">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2138">未找到 Keyword_ipaddress 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2138">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="6a857-2139">对于 IPv4，在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2139">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2140">正则表达式 Regex_ipv4_address 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2140">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2141">找到 Keyword_ipaddress 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2141">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="6a857-2142">对于 IPv6，在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2142">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2143">正则表达式 Regex_ipv6_address 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2143">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2144">未找到 Keyword_ipaddress 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2144">No keyword from Keyword_ipaddress is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-2145">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2145">Keywords</span></span>

#### <a name="keywordipaddress"></a><span data-ttu-id="6a857-2146">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="6a857-2146">Keyword_ipaddress</span></span>

- <span data-ttu-id="6a857-2147">IP（此关键字区分大小写）</span><span class="sxs-lookup"><span data-stu-id="6a857-2147">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="6a857-2148">ip address
</span><span class="sxs-lookup"><span data-stu-id="6a857-2148">ip address</span></span> 
- <span data-ttu-id="6a857-2149">ip addresses</span><span class="sxs-lookup"><span data-stu-id="6a857-2149">ip addresses</span></span>
- <span data-ttu-id="6a857-2150">internet protocol</span><span class="sxs-lookup"><span data-stu-id="6a857-2150">internet protocol</span></span>
- <span data-ttu-id="6a857-2151">
IP-כתובת ה
</span><span class="sxs-lookup"><span data-stu-id="6a857-2151">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="6a857-2152">国际分类的科 （ICD-10-厘米）</span><span class="sxs-lookup"><span data-stu-id="6a857-2152">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2153">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2153">Format</span></span>

<span data-ttu-id="6a857-2154">词典</span><span class="sxs-lookup"><span data-stu-id="6a857-2154">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2155">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2155">Pattern</span></span>

<span data-ttu-id="6a857-2156">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2156">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2157">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2157">Checksum</span></span>

<span data-ttu-id="6a857-2158">否</span><span class="sxs-lookup"><span data-stu-id="6a857-2158">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2159">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2159">Definition</span></span>

<span data-ttu-id="6a857-2160">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2160">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2161">找到从 Dictionary_icd_10_cm 关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2161">A keyword from Dictionary_icd_10_cm is found.</span></span>

```
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

<span data-ttu-id="6a857-2162">Keywords</span><span class="sxs-lookup"><span data-stu-id="6a857-2162">Keywords</span></span>

<span data-ttu-id="6a857-p135">Dictionary_icd_10_cm 关键字字典中的任何术语的基于[国际分类的科、 第十修订，临床修改 （ICD-10-厘米）](https://go.microsoft.com/fwlink/?linkid=852604)。此类型仅查找术语，不保险代码。</span><span class="sxs-lookup"><span data-stu-id="6a857-p135">Any term from the Dictionary_icd_10_cm keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604). This type looks only for the term, not the insurance codes.</span></span>

   
## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="6a857-2165">国际分类的科 （ICD-9-厘米）</span><span class="sxs-lookup"><span data-stu-id="6a857-2165">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2166">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2166">Format</span></span>

<span data-ttu-id="6a857-2167">词典</span><span class="sxs-lookup"><span data-stu-id="6a857-2167">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2168">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2168">Pattern</span></span>

<span data-ttu-id="6a857-2169">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2169">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2170">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2170">Checksum</span></span>

<span data-ttu-id="6a857-2171">否</span><span class="sxs-lookup"><span data-stu-id="6a857-2171">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2172">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2172">Definition</span></span>

<span data-ttu-id="6a857-2173">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2173">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2174">找到从 Dictionary_icd_9_cm 关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2174">A keyword from Dictionary_icd_9_cm is found.</span></span>

```
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a857-2175">Keywords</span><span class="sxs-lookup"><span data-stu-id="6a857-2175">Keywords</span></span>

<span data-ttu-id="6a857-p136">Dictionary_icd_9_cm 关键字字典中的任何术语的基于[国际分类的科、 第九个修订，临床修改 （ICD-9-厘米）](https://go.microsoft.com/fwlink/?linkid=852605)。此类型仅查找术语，不保险代码。</span><span class="sxs-lookup"><span data-stu-id="6a857-p136">Any term from the Dictionary_icd_9_cm keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605). This type looks only for the term, not the insurance codes.</span></span>
   
## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="6a857-2178">爱尔兰个人公共服务 (PPS) 号码</span><span class="sxs-lookup"><span data-stu-id="6a857-2178">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2179">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2179">Format</span></span>

<span data-ttu-id="6a857-2180">（到 Dec 2012 年 31） 的旧格式：</span><span class="sxs-lookup"><span data-stu-id="6a857-2180">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="6a857-2181">七位数字后跟 1-2  个字母 </span><span class="sxs-lookup"><span data-stu-id="6a857-2181">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="6a857-2182">新的格式 (2013 年 1 月 1 和之后):</span><span class="sxs-lookup"><span data-stu-id="6a857-2182">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="6a857-2183">七位数字后跟两个字母</span><span class="sxs-lookup"><span data-stu-id="6a857-2183">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2184">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2184">Pattern</span></span>

<span data-ttu-id="6a857-2185">（到 Dec 2012 年 31） 的旧格式：</span><span class="sxs-lookup"><span data-stu-id="6a857-2185">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="6a857-2186">七个数字 </span><span class="sxs-lookup"><span data-stu-id="6a857-2186">Seven digits</span></span> 
- <span data-ttu-id="6a857-2187">1-2 个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="6a857-2187">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="6a857-2188">新的格式 (2013 年 1 月 1 和之后):</span><span class="sxs-lookup"><span data-stu-id="6a857-2188">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="6a857-2189">七个数字 </span><span class="sxs-lookup"><span data-stu-id="6a857-2189">Seven digits</span></span> 
- <span data-ttu-id="6a857-2190">一个字母（不区分大小写），是字母校验位 </span><span class="sxs-lookup"><span data-stu-id="6a857-2190">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="6a857-2191">字母“A”或“H”（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="6a857-2191">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2192">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2192">Checksum</span></span>

<span data-ttu-id="6a857-2193">是</span><span class="sxs-lookup"><span data-stu-id="6a857-2193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2194">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2194">Definition</span></span>

<span data-ttu-id="6a857-2195">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2196">函数 Func_ireland_pps 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2196">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2197">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="6a857-2197">One of the following is true:</span></span>
    - <span data-ttu-id="6a857-2198">找到 Keyword_ireland_pps 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2198">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="6a857-2199">函数 Func_eu_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="6a857-2199">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="6a857-2200">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-2200">The checksum passes.</span></span>

<span data-ttu-id="6a857-2201">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2201">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2202">函数 Func_ireland_pps 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2202">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2203">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-2203">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-2204">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2204">Keywords</span></span>

#### <a name="keywordirelandpps"></a><span data-ttu-id="6a857-2205">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="6a857-2205">Keyword_ireland_pps</span></span>

- <span data-ttu-id="6a857-2206">Personal Public Service Number 
</span><span class="sxs-lookup"><span data-stu-id="6a857-2206">Personal Public Service Number</span></span> 
- <span data-ttu-id="6a857-2207">PPS Number
</span><span class="sxs-lookup"><span data-stu-id="6a857-2207">PPS Number</span></span> 
- <span data-ttu-id="6a857-2208">PPS Num
</span><span class="sxs-lookup"><span data-stu-id="6a857-2208">PPS Num</span></span> 
- <span data-ttu-id="6a857-2209">PPS No.
</span><span class="sxs-lookup"><span data-stu-id="6a857-2209">PPS No.</span></span> 
- <span data-ttu-id="6a857-2210">PPS #
</span><span class="sxs-lookup"><span data-stu-id="6a857-2210">PPS #</span></span> 
- <span data-ttu-id="6a857-2211">PPS #</span><span class="sxs-lookup"><span data-stu-id="6a857-2211">PPS#</span></span> 
- <span data-ttu-id="6a857-2212">PPSN
</span><span class="sxs-lookup"><span data-stu-id="6a857-2212">PPSN</span></span> 
- <span data-ttu-id="6a857-2213">Public Services Card
</span><span class="sxs-lookup"><span data-stu-id="6a857-2213">Public Services Card</span></span> 
- <span data-ttu-id="6a857-2214">Uimhir Phearsanta Seirbhíse Poiblí
</span><span class="sxs-lookup"><span data-stu-id="6a857-2214">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="6a857-p137">Uimh.PSP
</span><span class="sxs-lookup"><span data-stu-id="6a857-p137">Uimh. PSP</span></span> 
- <span data-ttu-id="6a857-2217">PSP
</span><span class="sxs-lookup"><span data-stu-id="6a857-2217">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="6a857-2218">以色列银行帐号</span><span class="sxs-lookup"><span data-stu-id="6a857-2218">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2219">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2219">Format</span></span>

<span data-ttu-id="6a857-2220">13 位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2220">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2221">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2221">Pattern</span></span>

<span data-ttu-id="6a857-2222">有格式模式：</span><span class="sxs-lookup"><span data-stu-id="6a857-2222">Formatted:</span></span>
- <span data-ttu-id="6a857-2223">两位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2223">Two digits</span></span> 
- <span data-ttu-id="6a857-2224">破折号</span><span class="sxs-lookup"><span data-stu-id="6a857-2224">A dash</span></span> 
- <span data-ttu-id="6a857-2225">三位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2225">Three digits</span></span> 
- <span data-ttu-id="6a857-2226">破折号</span><span class="sxs-lookup"><span data-stu-id="6a857-2226">A dash</span></span> 
- <span data-ttu-id="6a857-2227">八个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2227">Eight digits</span></span>

<span data-ttu-id="6a857-2228">无格式模式：</span><span class="sxs-lookup"><span data-stu-id="6a857-2228">Unformatted:</span></span>
- <span data-ttu-id="6a857-2229">	13 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2229">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2230">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2230">Checksum</span></span>

<span data-ttu-id="6a857-2231">否</span><span class="sxs-lookup"><span data-stu-id="6a857-2231">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2232">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2232">Definition</span></span>

<span data-ttu-id="6a857-2233">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2234">正则表达式 Regex_israel_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2234">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2235">找到 Keyword_israel_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2235">A keyword from Keyword_israel_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-2236">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2236">Keywords</span></span>

#### <a name="keywordisraelbankaccountnumber"></a><span data-ttu-id="6a857-2237">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="6a857-2237">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="6a857-2238">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="6a857-2238">Bank Account Number</span></span> 
- <span data-ttu-id="6a857-2239">Bank Account
</span><span class="sxs-lookup"><span data-stu-id="6a857-2239">Bank Account</span></span> 
- <span data-ttu-id="6a857-2240">Account Number
</span><span class="sxs-lookup"><span data-stu-id="6a857-2240">Account Number</span></span> 
- <span data-ttu-id="6a857-2241">מספר חשבון בנק
</span><span class="sxs-lookup"><span data-stu-id="6a857-2241">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="6a857-2242">以色列国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="6a857-2242">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2243">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2243">Format</span></span>

<span data-ttu-id="6a857-2244">九个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2244">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2245">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2245">Pattern</span></span>

<span data-ttu-id="6a857-2246">九个连续的数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2246">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2247">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2247">Checksum</span></span>

<span data-ttu-id="6a857-2248">是</span><span class="sxs-lookup"><span data-stu-id="6a857-2248">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2249">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2249">Definition</span></span>

<span data-ttu-id="6a857-2250">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2251">函数 Func_israeli_national_id_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2251">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2252">找到 Keyword_Israel_National_ID 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2252">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="6a857-2253">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-2253">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-2254">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2254">Keywords</span></span>

#### <a name="keywordisraelnationalid"></a><span data-ttu-id="6a857-2255">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="6a857-2255">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="6a857-2256">מספר זהות
</span><span class="sxs-lookup"><span data-stu-id="6a857-2256">מספר זהות</span></span> 
- <span data-ttu-id="6a857-2257">National ID Number</span><span class="sxs-lookup"><span data-stu-id="6a857-2257">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="6a857-2258">意大利驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="6a857-2258">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2259">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2259">Format</span></span>

<span data-ttu-id="6a857-2260">10 个字母和数字的组合</span><span class="sxs-lookup"><span data-stu-id="6a857-2260">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2261">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2261">Pattern</span></span>

- <span data-ttu-id="6a857-2262">10 个字母和数字的组合：</span><span class="sxs-lookup"><span data-stu-id="6a857-2262">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="6a857-2263">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="6a857-2263">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="6a857-2264">字母“A”或者“V”（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="6a857-2264">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="6a857-2265">七个字母（不区分大小写）、数字或下划线字符</span><span class="sxs-lookup"><span data-stu-id="6a857-2265">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="6a857-2266">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="6a857-2266">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2267">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2267">Checksum</span></span>

<span data-ttu-id="6a857-2268">否</span><span class="sxs-lookup"><span data-stu-id="6a857-2268">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2269">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2269">Definition</span></span>

<span data-ttu-id="6a857-2270">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2270">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2271">正则表达式 Regex_italy_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2271">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2272">找到 Keyword_italy_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2272">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-2273">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2273">Keywords</span></span>

#### <a name="keyworditalydriverslicensenumber"></a><span data-ttu-id="6a857-2274">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="6a857-2274">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="6a857-2275">numero di patente di guida
</span><span class="sxs-lookup"><span data-stu-id="6a857-2275">numero di patente di guida</span></span> 
- <span data-ttu-id="6a857-2276">patente di guida
</span><span class="sxs-lookup"><span data-stu-id="6a857-2276">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="6a857-2277">日本银行帐号</span><span class="sxs-lookup"><span data-stu-id="6a857-2277">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2278">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2278">Format</span></span>

<span data-ttu-id="6a857-2279">七个或八个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2279">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2280">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2280">Pattern</span></span>

<span data-ttu-id="6a857-2281">银行帐号：</span><span class="sxs-lookup"><span data-stu-id="6a857-2281">Bank account number:</span></span>
- <span data-ttu-id="6a857-2282">七个或八个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2282">Seven or eight digits</span></span>
- <span data-ttu-id="6a857-2283">银行帐户分支代码：</span><span class="sxs-lookup"><span data-stu-id="6a857-2283">Bank account branch code:</span></span>
- <span data-ttu-id="6a857-2284">四位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2284">Four digits</span></span> 
- <span data-ttu-id="6a857-2285">空格或破折号（可选）</span><span class="sxs-lookup"><span data-stu-id="6a857-2285">A space or dash (optional)</span></span> 
- <span data-ttu-id="6a857-2286">三位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2286">Three digits</span></span>

<span data-ttu-id="6a857-2287">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2287">Checksum</span></span>

<span data-ttu-id="6a857-2288">否</span><span class="sxs-lookup"><span data-stu-id="6a857-2288">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2289">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2289">Definition</span></span>

<span data-ttu-id="6a857-2290">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2290">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2291">函数 Func_jp_bank_account 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2291">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2292">找到 Keyword_jp_bank_account 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2292">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="6a857-2293">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="6a857-2293">One of the following is true:</span></span>
- <span data-ttu-id="6a857-2294">函数 Func_jp_bank_account_branch_code 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2294">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2295">找到 Keyword_jp_bank_branch_code 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2295">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="6a857-2296">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2296">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2297">函数 Func_jp_bank_account 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2297">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2298">找到 Keyword_jp_bank_account 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2298">A keyword from Keyword_jp_bank_account is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-2299">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2299">Keywords</span></span>

#### <a name="keywordjpbankaccount"></a><span data-ttu-id="6a857-2300">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="6a857-2300">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="6a857-2301">Checking Account Number
</span><span class="sxs-lookup"><span data-stu-id="6a857-2301">Checking Account Number</span></span> 
- <span data-ttu-id="6a857-2302">Checking Account
</span><span class="sxs-lookup"><span data-stu-id="6a857-2302">Checking Account</span></span> 
- <span data-ttu-id="6a857-2303">Checking Account #
</span><span class="sxs-lookup"><span data-stu-id="6a857-2303">Checking Account #</span></span> 
- <span data-ttu-id="6a857-2304">Checking Acct Number
</span><span class="sxs-lookup"><span data-stu-id="6a857-2304">Checking Acct Number</span></span> 
- <span data-ttu-id="6a857-2305">Checking Acct #
</span><span class="sxs-lookup"><span data-stu-id="6a857-2305">Checking Acct #</span></span> 
- <span data-ttu-id="6a857-2306">Checking Acct No.
</span><span class="sxs-lookup"><span data-stu-id="6a857-2306">Checking Acct No.</span></span> 
- <span data-ttu-id="6a857-2307">Checking Account No.
</span><span class="sxs-lookup"><span data-stu-id="6a857-2307">Checking Account No.</span></span> 
- <span data-ttu-id="6a857-2308">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="6a857-2308">Bank Account Number</span></span> 
- <span data-ttu-id="6a857-2309">Bank Account
</span><span class="sxs-lookup"><span data-stu-id="6a857-2309">Bank Account</span></span> 
- <span data-ttu-id="6a857-2310">Bank Account #
</span><span class="sxs-lookup"><span data-stu-id="6a857-2310">Bank Account #</span></span> 
- <span data-ttu-id="6a857-2311">Bank Acct Number
</span><span class="sxs-lookup"><span data-stu-id="6a857-2311">Bank Acct Number</span></span> 
- <span data-ttu-id="6a857-2312">Bank Acct #
</span><span class="sxs-lookup"><span data-stu-id="6a857-2312">Bank Acct #</span></span> 
- <span data-ttu-id="6a857-2313">Bank Acct No.
</span><span class="sxs-lookup"><span data-stu-id="6a857-2313">Bank Acct No.</span></span> 
- <span data-ttu-id="6a857-2314">Bank Account No.
</span><span class="sxs-lookup"><span data-stu-id="6a857-2314">Bank Account No.</span></span> 
- <span data-ttu-id="6a857-2315">Savings Account Number
</span><span class="sxs-lookup"><span data-stu-id="6a857-2315">Savings Account Number</span></span> 
- <span data-ttu-id="6a857-2316">节省帐户</span><span class="sxs-lookup"><span data-stu-id="6a857-2316">Savings Account</span></span> 
- <span data-ttu-id="6a857-2317">Savings Account #
</span><span class="sxs-lookup"><span data-stu-id="6a857-2317">Savings Account #</span></span> 
- <span data-ttu-id="6a857-2318">Savings Acct Number
</span><span class="sxs-lookup"><span data-stu-id="6a857-2318">Savings Acct Number</span></span> 
- <span data-ttu-id="6a857-2319">Savings Acct #
</span><span class="sxs-lookup"><span data-stu-id="6a857-2319">Savings Acct #</span></span> 
- <span data-ttu-id="6a857-2320">Savings Acct No.
</span><span class="sxs-lookup"><span data-stu-id="6a857-2320">Savings Acct No.</span></span> 
- <span data-ttu-id="6a857-2321">Savings Account No.
</span><span class="sxs-lookup"><span data-stu-id="6a857-2321">Savings Account No.</span></span> 
- <span data-ttu-id="6a857-2322">Debit Account Number
</span><span class="sxs-lookup"><span data-stu-id="6a857-2322">Debit Account Number</span></span> 
- <span data-ttu-id="6a857-2323">Debit Account
</span><span class="sxs-lookup"><span data-stu-id="6a857-2323">Debit Account</span></span> 
- <span data-ttu-id="6a857-2324">Debit Account #
</span><span class="sxs-lookup"><span data-stu-id="6a857-2324">Debit Account #</span></span> 
- <span data-ttu-id="6a857-2325">Debit Acct Number
</span><span class="sxs-lookup"><span data-stu-id="6a857-2325">Debit Acct Number</span></span> 
- <span data-ttu-id="6a857-2326">Debit Acct #
</span><span class="sxs-lookup"><span data-stu-id="6a857-2326">Debit Acct #</span></span> 
- <span data-ttu-id="6a857-2327">Debit Acct No.
</span><span class="sxs-lookup"><span data-stu-id="6a857-2327">Debit Acct No.</span></span> 
- <span data-ttu-id="6a857-2328">Debit Account No.
</span><span class="sxs-lookup"><span data-stu-id="6a857-2328">Debit Account No.</span></span> 
- <span data-ttu-id="6a857-2329">口座番号を当座預金口座の確認
</span><span class="sxs-lookup"><span data-stu-id="6a857-2329">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="6a857-2330">＃アカウントの確認、勘定番号の確認
</span><span class="sxs-lookup"><span data-stu-id="6a857-2330">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="6a857-2331">＃勘定の確認
</span><span class="sxs-lookup"><span data-stu-id="6a857-2331">＃勘定の確認</span></span> 
- <span data-ttu-id="6a857-2332">勘定番号の確認
</span><span class="sxs-lookup"><span data-stu-id="6a857-2332">勘定番号の確認</span></span> 
- <span data-ttu-id="6a857-2333">口座番号の確認
</span><span class="sxs-lookup"><span data-stu-id="6a857-2333">口座番号の確認</span></span> 
- <span data-ttu-id="6a857-2334">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="6a857-2334">銀行口座番号</span></span> 
- <span data-ttu-id="6a857-2335">銀行口座</span><span class="sxs-lookup"><span data-stu-id="6a857-2335">銀行口座</span></span> 
- <span data-ttu-id="6a857-2336">銀行口座＃
</span><span class="sxs-lookup"><span data-stu-id="6a857-2336">銀行口座＃</span></span> 
- <span data-ttu-id="6a857-2337">銀行の勘定番号
</span><span class="sxs-lookup"><span data-stu-id="6a857-2337">銀行の勘定番号</span></span> 
- <span data-ttu-id="6a857-2338">銀行のacct＃
</span><span class="sxs-lookup"><span data-stu-id="6a857-2338">銀行のacct＃</span></span> 
- <span data-ttu-id="6a857-2339">銀行の勘定いいえ
</span><span class="sxs-lookup"><span data-stu-id="6a857-2339">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="6a857-2340">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="6a857-2340">銀行口座番号</span></span>
- <span data-ttu-id="6a857-2341">
普通預金口座番号
</span><span class="sxs-lookup"><span data-stu-id="6a857-2341">普通預金口座番号</span></span> 
- <span data-ttu-id="6a857-2342">預金口座
</span><span class="sxs-lookup"><span data-stu-id="6a857-2342">預金口座</span></span> 
- <span data-ttu-id="6a857-2343">貯蓄口座＃
</span><span class="sxs-lookup"><span data-stu-id="6a857-2343">貯蓄口座＃</span></span> 
- <span data-ttu-id="6a857-2344">貯蓄勘定の数
</span><span class="sxs-lookup"><span data-stu-id="6a857-2344">貯蓄勘定の数</span></span> 
- <span data-ttu-id="6a857-2345">貯蓄勘定＃
</span><span class="sxs-lookup"><span data-stu-id="6a857-2345">貯蓄勘定＃</span></span> 
- <span data-ttu-id="6a857-2346">貯蓄勘定番号
</span><span class="sxs-lookup"><span data-stu-id="6a857-2346">貯蓄勘定番号</span></span> 
- <span data-ttu-id="6a857-2347">普通預金口座番号
</span><span class="sxs-lookup"><span data-stu-id="6a857-2347">普通預金口座番号</span></span> 
- <span data-ttu-id="6a857-2348">引き落とし口座番号
</span><span class="sxs-lookup"><span data-stu-id="6a857-2348">引き落とし口座番号</span></span> 
- <span data-ttu-id="6a857-2349">口座番号</span><span class="sxs-lookup"><span data-stu-id="6a857-2349">口座番号</span></span> 
- <span data-ttu-id="6a857-2350">口座番号＃
</span><span class="sxs-lookup"><span data-stu-id="6a857-2350">口座番号＃</span></span> 
- <span data-ttu-id="6a857-2351">デビットのacct番号
</span><span class="sxs-lookup"><span data-stu-id="6a857-2351">デビットのacct番号</span></span> 
- <span data-ttu-id="6a857-2352">デビット勘定＃
</span><span class="sxs-lookup"><span data-stu-id="6a857-2352">デビット勘定＃</span></span> 
- <span data-ttu-id="6a857-2353">デビットACCTの番号
</span><span class="sxs-lookup"><span data-stu-id="6a857-2353">デビットACCTの番号</span></span> 
- <span data-ttu-id="6a857-2354">デビット口座番号
</span><span class="sxs-lookup"><span data-stu-id="6a857-2354">デビット口座番号</span></span> 

#### <a name="keywordjpbankbranchcode"></a><span data-ttu-id="6a857-2355">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="6a857-2355">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="6a857-2356">Otemachi</span><span class="sxs-lookup"><span data-stu-id="6a857-2356">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="6a857-2357">日本驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="6a857-2357">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2358">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2358">Format</span></span>

<span data-ttu-id="6a857-2359">12 个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2359">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2360">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2360">Pattern</span></span>

<span data-ttu-id="6a857-2361">12 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2361">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2362">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2362">Checksum</span></span>

<span data-ttu-id="6a857-2363">否</span><span class="sxs-lookup"><span data-stu-id="6a857-2363">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2364">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2364">Definition</span></span>

<span data-ttu-id="6a857-2365">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2365">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2366">函数 Func_jp_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2366">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2367">找到 Keyword_jp_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2367">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a857-2368">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2368">Keywords</span></span>

#### <a name="keywordjpdriverslicensenumber"></a><span data-ttu-id="6a857-2369">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="6a857-2369">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="6a857-2370">dl#</span><span class="sxs-lookup"><span data-stu-id="6a857-2370">dl#</span></span> 
- <span data-ttu-id="6a857-2371">DL #</span><span class="sxs-lookup"><span data-stu-id="6a857-2371">DL＃</span></span> 
- <span data-ttu-id="6a857-2372">dls#</span><span class="sxs-lookup"><span data-stu-id="6a857-2372">dls#</span></span> 
- <span data-ttu-id="6a857-2373">DL #</span><span class="sxs-lookup"><span data-stu-id="6a857-2373">DLS＃</span></span> 
- <span data-ttu-id="6a857-2374">driver license</span><span class="sxs-lookup"><span data-stu-id="6a857-2374">driver license</span></span> 
- <span data-ttu-id="6a857-2375">driver licenses</span><span class="sxs-lookup"><span data-stu-id="6a857-2375">driver licenses</span></span> 
- <span data-ttu-id="6a857-2376">drivers license</span><span class="sxs-lookup"><span data-stu-id="6a857-2376">drivers license</span></span> 
- <span data-ttu-id="6a857-2377">driver's license</span><span class="sxs-lookup"><span data-stu-id="6a857-2377">driver's license</span></span> 
- <span data-ttu-id="6a857-2378">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="6a857-2378">drivers licenses</span></span> 
- <span data-ttu-id="6a857-2379">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="6a857-2379">driver's licenses</span></span> 
- <span data-ttu-id="6a857-2380">driving licence
</span><span class="sxs-lookup"><span data-stu-id="6a857-2380">driving licence</span></span> 
- <span data-ttu-id="6a857-2381">lic#</span><span class="sxs-lookup"><span data-stu-id="6a857-2381">lic#</span></span> 
- <span data-ttu-id="6a857-2382">LIC #</span><span class="sxs-lookup"><span data-stu-id="6a857-2382">LIC＃</span></span> 
- <span data-ttu-id="6a857-2383">lics#</span><span class="sxs-lookup"><span data-stu-id="6a857-2383">lics#</span></span> 
- <span data-ttu-id="6a857-2384">状态 id</span><span class="sxs-lookup"><span data-stu-id="6a857-2384">state id</span></span> 
- <span data-ttu-id="6a857-2385">state identification
</span><span class="sxs-lookup"><span data-stu-id="6a857-2385">state identification</span></span> 
- <span data-ttu-id="6a857-2386">state identification number
</span><span class="sxs-lookup"><span data-stu-id="6a857-2386">state identification number</span></span> 
- <span data-ttu-id="6a857-2387">低所得国＃
</span><span class="sxs-lookup"><span data-stu-id="6a857-2387">低所得国＃</span></span> 
- <span data-ttu-id="6a857-2388">免許証</span><span class="sxs-lookup"><span data-stu-id="6a857-2388">免許証</span></span> 
- <span data-ttu-id="6a857-2389">状態ID</span><span class="sxs-lookup"><span data-stu-id="6a857-2389">状態ID</span></span>
- <span data-ttu-id="6a857-2390">
状態の識別
</span><span class="sxs-lookup"><span data-stu-id="6a857-2390">状態の識別</span></span> 
- <span data-ttu-id="6a857-2391">状態の識別番号
</span><span class="sxs-lookup"><span data-stu-id="6a857-2391">状態の識別番号</span></span> 
- <span data-ttu-id="6a857-2392">運転免許</span><span class="sxs-lookup"><span data-stu-id="6a857-2392">運転免許</span></span> 
- <span data-ttu-id="6a857-2393">運転免許証</span><span class="sxs-lookup"><span data-stu-id="6a857-2393">運転免許証</span></span> 
- <span data-ttu-id="6a857-2394">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="6a857-2394">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="6a857-2395">日本护照号码</span><span class="sxs-lookup"><span data-stu-id="6a857-2395">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2396">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2396">Format</span></span>

<span data-ttu-id="6a857-2397">两个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2397">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2398">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2398">Pattern</span></span>

<span data-ttu-id="6a857-2399">两个字母（不区分大小写）后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2399">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2400">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2400">Checksum</span></span>

<span data-ttu-id="6a857-2401">否</span><span class="sxs-lookup"><span data-stu-id="6a857-2401">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2402">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2402">Definition</span></span>

<span data-ttu-id="6a857-2403">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2403">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2404">函数 Func_jp_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2404">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2405">找到 Keyword_jp_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2405">A keyword from Keyword_jp_passport is found.</span></span>

```
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a857-2406">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2406">Keywords</span></span>

#### <a name="keywordjppassport"></a><span data-ttu-id="6a857-2407">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="6a857-2407">Keyword_jp_passport</span></span>

- <span data-ttu-id="6a857-2408">パスポート
</span><span class="sxs-lookup"><span data-stu-id="6a857-2408">パスポート</span></span> 
- <span data-ttu-id="6a857-2409">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="6a857-2409">パスポート番号</span></span> 
- <span data-ttu-id="6a857-2410">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="6a857-2410">パスポートのNum</span></span> 
- <span data-ttu-id="6a857-2411">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="6a857-2411">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="6a857-2412">日本居民登记号码</span><span class="sxs-lookup"><span data-stu-id="6a857-2412">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2413">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2413">Format</span></span>

<span data-ttu-id="6a857-2414">11 个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2414">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2415">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2415">Pattern</span></span>

<span data-ttu-id="6a857-2416">11 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2416">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2417">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2417">Checksum</span></span>

<span data-ttu-id="6a857-2418">否</span><span class="sxs-lookup"><span data-stu-id="6a857-2418">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2419">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2419">Definition</span></span>

<span data-ttu-id="6a857-2420">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2420">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2421">函数 Func_jp_resident_registration_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2421">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2422">找到 Keyword_jp_resident_registration_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2422">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a857-2423">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2423">Keywords</span></span>

#### <a name="keywordjpresidentregistrationnumber"></a><span data-ttu-id="6a857-2424">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="6a857-2424">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="6a857-2425">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="6a857-2425">Resident Registration Number</span></span>
- <span data-ttu-id="6a857-2426">Resident Register Number
</span><span class="sxs-lookup"><span data-stu-id="6a857-2426">Resident Register Number</span></span> 
- <span data-ttu-id="6a857-2427">Residents Basic Registry Number
</span><span class="sxs-lookup"><span data-stu-id="6a857-2427">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="6a857-2428">Resident Registration No.
</span><span class="sxs-lookup"><span data-stu-id="6a857-2428">Resident Registration No.</span></span> 
- <span data-ttu-id="6a857-2429">Resident Register No.
</span><span class="sxs-lookup"><span data-stu-id="6a857-2429">Resident Register No.</span></span> 
- <span data-ttu-id="6a857-2430">Residents Basic Registry No.
</span><span class="sxs-lookup"><span data-stu-id="6a857-2430">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="6a857-2431">Basic Resident Register No.
</span><span class="sxs-lookup"><span data-stu-id="6a857-2431">Basic Resident Register No.</span></span> 
- <span data-ttu-id="6a857-2432">住民登録番号、登録番号をレジデント
</span><span class="sxs-lookup"><span data-stu-id="6a857-2432">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="6a857-2433">住民基本登録番号、登録番号
</span><span class="sxs-lookup"><span data-stu-id="6a857-2433">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="6a857-2434">住民基本レジストリ番号を常駐
</span><span class="sxs-lookup"><span data-stu-id="6a857-2434">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="6a857-2435">登録番号を常駐住民基本台帳登録番号
</span><span class="sxs-lookup"><span data-stu-id="6a857-2435">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="6a857-2436">日本社会保险号码 (SIN)</span><span class="sxs-lookup"><span data-stu-id="6a857-2436">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2437">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2437">Format</span></span>

<span data-ttu-id="6a857-2438">7-12 个数字 </span><span class="sxs-lookup"><span data-stu-id="6a857-2438">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2439">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2439">Pattern</span></span>

<span data-ttu-id="6a857-2440">7-12 位数字：</span><span class="sxs-lookup"><span data-stu-id="6a857-2440">7-12 digits:</span></span>
- <span data-ttu-id="6a857-2441">四位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2441">Four digits</span></span> 
- <span data-ttu-id="6a857-2442">一个连字符（可选）</span><span class="sxs-lookup"><span data-stu-id="6a857-2442">A hyphen (optional)</span></span> 
- <span data-ttu-id="6a857-2443">6 个数字或</span><span class="sxs-lookup"><span data-stu-id="6a857-2443">Six digits OR</span></span>
- <span data-ttu-id="6a857-2444">7-12 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2444">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2445">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2445">Checksum</span></span>

<span data-ttu-id="6a857-2446">否</span><span class="sxs-lookup"><span data-stu-id="6a857-2446">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2447">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2447">Definition</span></span>

<span data-ttu-id="6a857-2448">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2448">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2449">函数 Func_jp_sin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2449">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2450">找到 Keyword_jp_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2450">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="6a857-2451">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2451">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2452">函数 Func_jp_sin_pre_1997 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2452">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2453">找到 Keyword_jp_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2453">A keyword from Keyword_jp_sin is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-2454">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2454">Keywords</span></span>

#### <a name="keywordjpsin"></a><span data-ttu-id="6a857-2455">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="6a857-2455">Keyword_jp_sin</span></span>

- <span data-ttu-id="6a857-2456">Social Insurance No.
</span><span class="sxs-lookup"><span data-stu-id="6a857-2456">Social Insurance No.</span></span> 
- <span data-ttu-id="6a857-2457">Social Insurance Num
</span><span class="sxs-lookup"><span data-stu-id="6a857-2457">Social Insurance Num</span></span> 
- <span data-ttu-id="6a857-2458">Social Insurance Number
</span><span class="sxs-lookup"><span data-stu-id="6a857-2458">Social Insurance Number</span></span> 
- <span data-ttu-id="6a857-2459">社会保険のテンキー
</span><span class="sxs-lookup"><span data-stu-id="6a857-2459">社会保険のテンキー</span></span> 
- <span data-ttu-id="6a857-2460">社会保険番号
</span><span class="sxs-lookup"><span data-stu-id="6a857-2460">社会保険番号</span></span> 
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="6a857-2461">马拉西亚身份证号码</span><span class="sxs-lookup"><span data-stu-id="6a857-2461">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2462">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2462">Format</span></span>

<span data-ttu-id="6a857-2463">12 个数字（包含可选连字符）</span><span class="sxs-lookup"><span data-stu-id="6a857-2463">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2464">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2464">Pattern</span></span>

<span data-ttu-id="6a857-2465">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="6a857-2465">12 digits:</span></span>
- <span data-ttu-id="6a857-2466">六个数字，采用  YYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="6a857-2466">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="6a857-2467">一个短划线（可选） </span><span class="sxs-lookup"><span data-stu-id="6a857-2467">A dash (optional)</span></span> 
- <span data-ttu-id="6a857-2468">两个字母的出生地代码 </span><span class="sxs-lookup"><span data-stu-id="6a857-2468">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="6a857-2469">一个短划线（可选） </span><span class="sxs-lookup"><span data-stu-id="6a857-2469">A dash (optional)</span></span> 
- <span data-ttu-id="6a857-2470">三个随机数字 </span><span class="sxs-lookup"><span data-stu-id="6a857-2470">Three random digits</span></span> 
- <span data-ttu-id="6a857-2471">一位性别代码</span><span class="sxs-lookup"><span data-stu-id="6a857-2471">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2472">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2472">Checksum</span></span>

<span data-ttu-id="6a857-2473">否</span><span class="sxs-lookup"><span data-stu-id="6a857-2473">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2474">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2474">Definition</span></span>

<span data-ttu-id="6a857-2475">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2475">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2476">正则表达式 Regex_malaysia_id_card_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2476">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2477">找到 Keyword_malaysia_id_card_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2477">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-2478">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2478">Keywords</span></span>
   
#### <a name="keywordmalaysiaidcardnumber"></a><span data-ttu-id="6a857-2479">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="6a857-2479">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="6a857-2480">MyKad</span><span class="sxs-lookup"><span data-stu-id="6a857-2480">MyKad</span></span> 
- <span data-ttu-id="6a857-2481">Identity Card</span><span class="sxs-lookup"><span data-stu-id="6a857-2481">Identity Card</span></span> 
- <span data-ttu-id="6a857-2482">身份证</span><span class="sxs-lookup"><span data-stu-id="6a857-2482">ID Card</span></span> 
- <span data-ttu-id="6a857-2483">身份证</span><span class="sxs-lookup"><span data-stu-id="6a857-2483">Identification Card</span></span> 
- <span data-ttu-id="6a857-2484">Digital Application Card
</span><span class="sxs-lookup"><span data-stu-id="6a857-2484">Digital Application Card</span></span> 
- <span data-ttu-id="6a857-2485">Kad Akuan Diri
</span><span class="sxs-lookup"><span data-stu-id="6a857-2485">Kad Akuan Diri</span></span> 
- <span data-ttu-id="6a857-2486">Kad Aplikasi Digital
</span><span class="sxs-lookup"><span data-stu-id="6a857-2486">Kad Aplikasi Digital</span></span> 
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="6a857-2487">荷兰公民服务 (BSN) 号码</span><span class="sxs-lookup"><span data-stu-id="6a857-2487">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2488">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2488">Format</span></span>

<span data-ttu-id="6a857-2489">8-9 个数字（包含可选空格）</span><span class="sxs-lookup"><span data-stu-id="6a857-2489">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2490">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2490">Pattern</span></span>

<span data-ttu-id="6a857-2491">8-9 个数字：</span><span class="sxs-lookup"><span data-stu-id="6a857-2491">8-9 digits:</span></span>
- <span data-ttu-id="6a857-2492">三个数字 </span><span class="sxs-lookup"><span data-stu-id="6a857-2492">Three digits</span></span> 
- <span data-ttu-id="6a857-2493">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="6a857-2493">A space (optional)</span></span> 
- <span data-ttu-id="6a857-2494">三个数字 </span><span class="sxs-lookup"><span data-stu-id="6a857-2494">Three digits</span></span> 
- <span data-ttu-id="6a857-2495">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="6a857-2495">A space (optional)</span></span> 
- <span data-ttu-id="6a857-2496">2-3 个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2496">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2497">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2497">Checksum</span></span>

<span data-ttu-id="6a857-2498">是</span><span class="sxs-lookup"><span data-stu-id="6a857-2498">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2499">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2499">Definition</span></span>

<span data-ttu-id="6a857-2500">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2500">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2501">函数 Func_netherlands_bsn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2501">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2502">找到 Keyword_netherlands_bsn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2502">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="6a857-2503">函数 Func_eu_date2 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="6a857-2503">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="6a857-2504">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-2504">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-2505">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2505">Keywords</span></span>

#### <a name="keywordnetherlandsbsn"></a><span data-ttu-id="6a857-2506">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="6a857-2506">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="6a857-2507">Citizen service number
</span><span class="sxs-lookup"><span data-stu-id="6a857-2507">Citizen service number</span></span> 
- <span data-ttu-id="6a857-2508">BSN

</span><span class="sxs-lookup"><span data-stu-id="6a857-2508">BSN</span></span> 
- <span data-ttu-id="6a857-2509">Burgerservicenummer
</span><span class="sxs-lookup"><span data-stu-id="6a857-2509">Burgerservicenummer</span></span> 
- <span data-ttu-id="6a857-2510">Sofinummer
</span><span class="sxs-lookup"><span data-stu-id="6a857-2510">Sofinummer</span></span> 
- <span data-ttu-id="6a857-2511">Persoonsgebonden nummer
</span><span class="sxs-lookup"><span data-stu-id="6a857-2511">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="6a857-2512">Persoonsnummer
</span><span class="sxs-lookup"><span data-stu-id="6a857-2512">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="6a857-2513">新西兰卫生部号码</span><span class="sxs-lookup"><span data-stu-id="6a857-2513">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2514">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2514">Format</span></span>

<span data-ttu-id="6a857-2515">三个字母、一个空格（可选）以及四个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2515">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2516">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2516">Pattern</span></span>

<span data-ttu-id="6a857-2517">三个字母 （不区分大小写） 空间 （可选） 四位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2517">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2518">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2518">Checksum</span></span>

<span data-ttu-id="6a857-2519">是</span><span class="sxs-lookup"><span data-stu-id="6a857-2519">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2520">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2520">Definition</span></span>

<span data-ttu-id="6a857-2521">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2521">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2522">函数 Func_new_zealand_ministry_of_health_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2522">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2523">找到 Keyword_nz_terms 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2523">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="6a857-2524">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-2524">The checksum passes.</span></span>

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

<span data-ttu-id="6a857-2525">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2525">Keywords</span></span>

<span data-ttu-id="6a857-2526">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="6a857-2526">Keyword_nz_terms</span></span>

- <span data-ttu-id="6a857-2527">NHI
</span><span class="sxs-lookup"><span data-stu-id="6a857-2527">NHI</span></span> 
- <span data-ttu-id="6a857-2528">新西兰</span><span class="sxs-lookup"><span data-stu-id="6a857-2528">New Zealand</span></span> 
- <span data-ttu-id="6a857-2529">运行状况</span><span class="sxs-lookup"><span data-stu-id="6a857-2529">Health</span></span> 
- <span data-ttu-id="6a857-2530">treatment
</span><span class="sxs-lookup"><span data-stu-id="6a857-2530">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="6a857-2531">挪威身份证号</span><span class="sxs-lookup"><span data-stu-id="6a857-2531">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2532">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2532">Format</span></span>

<span data-ttu-id="6a857-2533">11 个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2533">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2534">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2534">Pattern</span></span>

<span data-ttu-id="6a857-2535">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="6a857-2535">11 digits:</span></span>
- <span data-ttu-id="6a857-2536">六个数字，采用  DDMMYY 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="6a857-2536">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="6a857-2537">三位个人号码 </span><span class="sxs-lookup"><span data-stu-id="6a857-2537">Three-digit individual number</span></span> 
- <span data-ttu-id="6a857-2538">两个校验位</span><span class="sxs-lookup"><span data-stu-id="6a857-2538">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2539">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2539">Checksum</span></span>

<span data-ttu-id="6a857-2540">是</span><span class="sxs-lookup"><span data-stu-id="6a857-2540">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2541">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2541">Definition</span></span>

<span data-ttu-id="6a857-2542">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2542">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2543">函数 Func_norway_id_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2543">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2544">找到 Keyword_norway_id_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2544">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="6a857-2545">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-2545">The checksum passes.</span></span>
- <span data-ttu-id="6a857-2546">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2546">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2547">函数 Func_norway_id_numbe 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2547">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2548">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-2548">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-2549">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2549">Keywords</span></span>

#### <a name="keywordnorwayidnumber"></a><span data-ttu-id="6a857-2550">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="6a857-2550">Keyword_norway_id_number</span></span>

- <span data-ttu-id="6a857-2551">Personal identification number</span><span class="sxs-lookup"><span data-stu-id="6a857-2551">Personal identification number</span></span>
- <span data-ttu-id="6a857-2552">Norwegian ID Number</span><span class="sxs-lookup"><span data-stu-id="6a857-2552">Norwegian ID Number</span></span>
- <span data-ttu-id="6a857-2553">ID Number</span><span class="sxs-lookup"><span data-stu-id="6a857-2553">ID Number</span></span>
- <span data-ttu-id="6a857-2554">Identification</span><span class="sxs-lookup"><span data-stu-id="6a857-2554">Identification</span></span>
- <span data-ttu-id="6a857-2555">Personnummer</span><span class="sxs-lookup"><span data-stu-id="6a857-2555">Personnummer</span></span>
- <span data-ttu-id="6a857-2556">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="6a857-2556">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="6a857-2557">菲律宾统一多用途身份证号码</span><span class="sxs-lookup"><span data-stu-id="6a857-2557">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2558">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2558">Format</span></span>

<span data-ttu-id="6a857-2559">12 个数字，通过连字符分隔 </span><span class="sxs-lookup"><span data-stu-id="6a857-2559">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2560">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2560">Pattern</span></span>

<span data-ttu-id="6a857-2561">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="6a857-2561">12 digits:</span></span>
- <span data-ttu-id="6a857-2562">四个数字 </span><span class="sxs-lookup"><span data-stu-id="6a857-2562">Four digits</span></span> 
- <span data-ttu-id="6a857-2563">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="6a857-2563">A hyphen</span></span> 
- <span data-ttu-id="6a857-2564">七个数字 </span><span class="sxs-lookup"><span data-stu-id="6a857-2564">Seven digits</span></span> 
- <span data-ttu-id="6a857-2565">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="6a857-2565">A hyphen</span></span> 
- <span data-ttu-id="6a857-2566">一个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2566">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2567">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2567">Checksum</span></span>

<span data-ttu-id="6a857-2568">否</span><span class="sxs-lookup"><span data-stu-id="6a857-2568">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2569">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2569">Definition</span></span>

<span data-ttu-id="6a857-2570">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2570">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2571">正则表达式 Regex_philippines_unified_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2571">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2572">找到 Keyword_philippines_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2572">A keyword from Keyword_philippines_id is found.</span></span>

```
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a857-2573">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2573">Keywords</span></span>
   
#### <a name="keywordphilippinesid"></a><span data-ttu-id="6a857-2574">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="6a857-2574">Keyword_philippines_id</span></span>

- <span data-ttu-id="6a857-2575">Unified Multi-Purpose ID
</span><span class="sxs-lookup"><span data-stu-id="6a857-2575">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="6a857-2576">UMID
</span><span class="sxs-lookup"><span data-stu-id="6a857-2576">UMID</span></span> 
- <span data-ttu-id="6a857-2577">Identity Card</span><span class="sxs-lookup"><span data-stu-id="6a857-2577">Identity Card</span></span> 
- <span data-ttu-id="6a857-2578">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="6a857-2578">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="6a857-2579">波兰身份证</span><span class="sxs-lookup"><span data-stu-id="6a857-2579">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2580">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2580">Format</span></span>

<span data-ttu-id="6a857-2581">三个字母和六个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2581">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2582">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2582">Pattern</span></span>

<span data-ttu-id="6a857-2583">三个字母（不区分大小写）后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2583">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2584">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2584">Checksum</span></span>

<span data-ttu-id="6a857-2585">是</span><span class="sxs-lookup"><span data-stu-id="6a857-2585">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2586">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2586">Definition</span></span>

<span data-ttu-id="6a857-p138">DLP 策略是相信它已检测到此类型的敏感信息的 75 %if、 内 300 个字符的邻近度： 函数 Func_polish_national_id 查找与模式匹配的内容。找到从 Keyword_polish_national_id_passport_number 关键字。将传递校验和。</span><span class="sxs-lookup"><span data-stu-id="6a857-p138">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern. A keyword from Keyword_polish_national_id_passport_number is found. The checksum passes.</span></span>

```
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a857-2590">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2590">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="6a857-2591">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="6a857-2591">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="6a857-2592">Nazwa i nr dowodu tożsamości
</span><span class="sxs-lookup"><span data-stu-id="6a857-2592">Nazwa i nr dowodu tożsamości</span></span> 
- <span data-ttu-id="6a857-2593">Dowód Tożsamości
</span><span class="sxs-lookup"><span data-stu-id="6a857-2593">Dowód Tożsamości</span></span> 
- <span data-ttu-id="6a857-p139">dow. os.
</span><span class="sxs-lookup"><span data-stu-id="6a857-p139">dow. os.</span></span> 

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="6a857-2596">波兰国家/地区 ID (PESEL)</span><span class="sxs-lookup"><span data-stu-id="6a857-2596">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2597">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2597">Format</span></span>

<span data-ttu-id="6a857-2598">11 个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2598">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2599">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2599">Pattern</span></span>

<span data-ttu-id="6a857-2600">11 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2600">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2601">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2601">Checksum</span></span>

<span data-ttu-id="6a857-2602">是</span><span class="sxs-lookup"><span data-stu-id="6a857-2602">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2603">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2603">Definition</span></span>

<span data-ttu-id="6a857-2604">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2604">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2605">函数 Func_pesel_identification_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2605">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2606">找到 Keyword_pesel_identification_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2606">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="6a857-2607">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-2607">The checksum passes.</span></span>

```
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a857-2608">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2608">Keywords</span></span>

#### <a name="keywordpeselidentificationnumber"></a><span data-ttu-id="6a857-2609">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="6a857-2609">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="6a857-2610">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="6a857-2610">Nr PESEL</span></span>
- <span data-ttu-id="6a857-2611">PESEL</span><span class="sxs-lookup"><span data-stu-id="6a857-2611">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="6a857-2612">波兰护照</span><span class="sxs-lookup"><span data-stu-id="6a857-2612">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2613">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2613">Format</span></span>

<span data-ttu-id="6a857-2614">两个字母和七个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2614">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2615">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2615">Pattern</span></span>

<span data-ttu-id="6a857-2616">两个字母（不区分大小写）后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2616">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2617">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2617">Checksum</span></span>

<span data-ttu-id="6a857-2618">是</span><span class="sxs-lookup"><span data-stu-id="6a857-2618">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2619">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2619">Definition</span></span>

<span data-ttu-id="6a857-2620">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2620">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2621">函数 Func_polish_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2621">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2622">找到 Keyword_polish_national_id_passport_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2622">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="6a857-2623">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-2623">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-2624">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2624">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="6a857-2625">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="6a857-2625">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="6a857-2626">Nazwa i nr dowodu tożsamości
</span><span class="sxs-lookup"><span data-stu-id="6a857-2626">Nazwa i nr dowodu tożsamości</span></span> 
- <span data-ttu-id="6a857-2627">Dowód Tożsamości
</span><span class="sxs-lookup"><span data-stu-id="6a857-2627">Dowód Tożsamości</span></span> 
- <span data-ttu-id="6a857-p140">dow. os.
</span><span class="sxs-lookup"><span data-stu-id="6a857-p140">dow. os.</span></span> 

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="6a857-2630">葡萄牙公民身份证号</span><span class="sxs-lookup"><span data-stu-id="6a857-2630">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2631">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2631">Format</span></span>

<span data-ttu-id="6a857-2632">八个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2632">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2633">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2633">Pattern</span></span>

<span data-ttu-id="6a857-2634">八个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2634">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2635">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2635">Checksum</span></span>

<span data-ttu-id="6a857-2636">否</span><span class="sxs-lookup"><span data-stu-id="6a857-2636">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2637">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2637">Definition</span></span>

<span data-ttu-id="6a857-2638">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2638">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2639">正则表达式 Regex_portugal_citizen_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2639">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2640">找到 Keyword_portugal_citizen_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2640">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a857-2641">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2641">Keywords</span></span>

#### <a name="keywordportugalcitizencard"></a><span data-ttu-id="6a857-2642">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="6a857-2642">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="6a857-2643">Citizen Card</span><span class="sxs-lookup"><span data-stu-id="6a857-2643">Citizen Card</span></span>
- <span data-ttu-id="6a857-2644">National ID Card</span><span class="sxs-lookup"><span data-stu-id="6a857-2644">National ID Card</span></span>
- <span data-ttu-id="6a857-2645">CC</span><span class="sxs-lookup"><span data-stu-id="6a857-2645">CC</span></span>
- <span data-ttu-id="6a857-2646">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="6a857-2646">Cartão de Cidadão</span></span>
- <span data-ttu-id="6a857-2647">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="6a857-2647">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="6a857-2648">沙特阿拉伯国家 ID</span><span class="sxs-lookup"><span data-stu-id="6a857-2648">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2649">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2649">Format</span></span>

<span data-ttu-id="6a857-2650">10 个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2650">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2651">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2651">Pattern</span></span>

<span data-ttu-id="6a857-2652">10 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2652">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2653">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2653">Checksum</span></span>

<span data-ttu-id="6a857-2654">否</span><span class="sxs-lookup"><span data-stu-id="6a857-2654">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2655">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2655">Definition</span></span>

<span data-ttu-id="6a857-2656">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2656">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2657">正则表达式 Regex_saudi_arabia_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2657">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2658">找到 Keyword_saudi_arabia_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2658">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-2659">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2659">Keywords</span></span>

#### <a name="keywordsaudiarabianationalid"></a><span data-ttu-id="6a857-2660">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="6a857-2660">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="6a857-2661">Identification Card
</span><span class="sxs-lookup"><span data-stu-id="6a857-2661">Identification Card</span></span> 
- <span data-ttu-id="6a857-2662">I card number
</span><span class="sxs-lookup"><span data-stu-id="6a857-2662">I card number</span></span> 
- <span data-ttu-id="6a857-2663">ID 号</span><span class="sxs-lookup"><span data-stu-id="6a857-2663">ID number</span></span> 
- <span data-ttu-id="6a857-2664">الوطنية الهوية بطاقة رقم
</span><span class="sxs-lookup"><span data-stu-id="6a857-2664">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="6a857-2665">新加坡国家登记身份证 (NRIC) 号</span><span class="sxs-lookup"><span data-stu-id="6a857-2665">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2666">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2666">Format</span></span>

<span data-ttu-id="6a857-2667">九个字母和数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2667">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2668">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2668">Pattern</span></span>

- <span data-ttu-id="6a857-2669">九个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="6a857-2669">Nine letters and digits:</span></span>
- <span data-ttu-id="6a857-2670">字母“F”、“G”、“S”或“T”（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="6a857-2670">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="6a857-2671">七个数字 </span><span class="sxs-lookup"><span data-stu-id="6a857-2671">Seven digits</span></span> 
- <span data-ttu-id="6a857-2672">一个字母校验位</span><span class="sxs-lookup"><span data-stu-id="6a857-2672">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2673">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2673">Checksum</span></span>

<span data-ttu-id="6a857-2674">是</span><span class="sxs-lookup"><span data-stu-id="6a857-2674">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2675">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2675">Definition</span></span>

<span data-ttu-id="6a857-2676">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2676">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2677">正则表达式 Regex_singapore_nric 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2677">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2678">找到 Keyword_singapore_nric 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2678">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="6a857-2679">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-2679">The checksum passes.</span></span>

<span data-ttu-id="6a857-2680">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2680">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2681">正则表达式 Regex_singapore_nric 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2681">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2682">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-2682">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-2683">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2683">Keywords</span></span>
   
#### <a name="keywordsingaporenric"></a><span data-ttu-id="6a857-2684">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="6a857-2684">Keyword_singapore_nric</span></span>

- <span data-ttu-id="6a857-2685">National Registration Identity Card
</span><span class="sxs-lookup"><span data-stu-id="6a857-2685">National Registration Identity Card</span></span> 
- <span data-ttu-id="6a857-2686">Identity Card Number
</span><span class="sxs-lookup"><span data-stu-id="6a857-2686">Identity Card Number</span></span> 
- <span data-ttu-id="6a857-2687">NRIC
</span><span class="sxs-lookup"><span data-stu-id="6a857-2687">NRIC</span></span> 
- <span data-ttu-id="6a857-2688">IC
</span><span class="sxs-lookup"><span data-stu-id="6a857-2688">IC</span></span> 
- <span data-ttu-id="6a857-2689">Foreign Identification Number
</span><span class="sxs-lookup"><span data-stu-id="6a857-2689">Foreign Identification Number</span></span> 
- <span data-ttu-id="6a857-2690">FIN
</span><span class="sxs-lookup"><span data-stu-id="6a857-2690">FIN</span></span> 
- <span data-ttu-id="6a857-2691">身份证 </span><span class="sxs-lookup"><span data-stu-id="6a857-2691">身份证</span></span> 
- <span data-ttu-id="6a857-2692">身份證
</span><span class="sxs-lookup"><span data-stu-id="6a857-2692">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="6a857-2693">南非身份证号</span><span class="sxs-lookup"><span data-stu-id="6a857-2693">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2694">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2694">Format</span></span>

<span data-ttu-id="6a857-2695">13 个数字（可能包含空格）</span><span class="sxs-lookup"><span data-stu-id="6a857-2695">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2696">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2696">Pattern</span></span>

<span data-ttu-id="6a857-2697">13 个数字：</span><span class="sxs-lookup"><span data-stu-id="6a857-2697">13 digits:</span></span>
- <span data-ttu-id="6a857-2698">六个数字，采用  YYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="6a857-2698">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="6a857-2699">四个数字 </span><span class="sxs-lookup"><span data-stu-id="6a857-2699">Four digits</span></span> 
- <span data-ttu-id="6a857-2700">一位公民指示码 </span><span class="sxs-lookup"><span data-stu-id="6a857-2700">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="6a857-2701">数字“8”或“9” </span><span class="sxs-lookup"><span data-stu-id="6a857-2701">The digit "8" or "9"</span></span> 
- <span data-ttu-id="6a857-2702">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="6a857-2702">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2703">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2703">Checksum</span></span>

<span data-ttu-id="6a857-2704">是</span><span class="sxs-lookup"><span data-stu-id="6a857-2704">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2705">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2705">Definition</span></span>

<span data-ttu-id="6a857-2706">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2706">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2707">函数 Func_south_africa_identification_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2707">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2708">找到 Keyword_south_africa_identification_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2708">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="6a857-2709">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-2709">The checksum passes.</span></span>

```
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a857-2710">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2710">Keywords</span></span>
   
#### <a name="keywordsouthafricaidentificationnumber"></a><span data-ttu-id="6a857-2711">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="6a857-2711">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="6a857-2712">Identity card</span><span class="sxs-lookup"><span data-stu-id="6a857-2712">Identity card</span></span>
- <span data-ttu-id="6a857-2713">ID</span><span class="sxs-lookup"><span data-stu-id="6a857-2713">ID</span></span>
- <span data-ttu-id="6a857-2714">Identification</span><span class="sxs-lookup"><span data-stu-id="6a857-2714">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="6a857-2715">韩国居民注册号码</span><span class="sxs-lookup"><span data-stu-id="6a857-2715">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2716">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2716">Format</span></span>

<span data-ttu-id="6a857-2717">13 个数字（包含连字符）</span><span class="sxs-lookup"><span data-stu-id="6a857-2717">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2718">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2718">Pattern</span></span>

<span data-ttu-id="6a857-2719">13 个数字：</span><span class="sxs-lookup"><span data-stu-id="6a857-2719">13 digits:</span></span>
- <span data-ttu-id="6a857-2720">六个数字，采用  YYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="6a857-2720">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="6a857-2721">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="6a857-2721">A hyphen</span></span> 
- <span data-ttu-id="6a857-2722">一个数字，由世纪和性别 </span><span class="sxs-lookup"><span data-stu-id="6a857-2722">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="6a857-2723">四位数字的出生地区代码 </span><span class="sxs-lookup"><span data-stu-id="6a857-2723">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="6a857-2724">一个数字，用于区分前面数字均相同的人 </span><span class="sxs-lookup"><span data-stu-id="6a857-2724">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="6a857-2725">一个校验位。</span><span class="sxs-lookup"><span data-stu-id="6a857-2725">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2726">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2726">Checksum</span></span>

<span data-ttu-id="6a857-2727">是</span><span class="sxs-lookup"><span data-stu-id="6a857-2727">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2728">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2728">Definition</span></span>

<span data-ttu-id="6a857-2729">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2729">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2730">函数 Func_south_korea_resident_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2730">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2731">找到 Keyword_south_korea_resident_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2731">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="6a857-2732">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-2732">The checksum passes.</span></span>

<span data-ttu-id="6a857-2733">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2733">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2734">函数 Func_south_korea_resident_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2734">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2735">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-2735">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-2736">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2736">Keywords</span></span>
   
#### <a name="keywordsouthkorearesidentnumber"></a><span data-ttu-id="6a857-2737">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="6a857-2737">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="6a857-2738">National ID card
</span><span class="sxs-lookup"><span data-stu-id="6a857-2738">National ID card</span></span> 
- <span data-ttu-id="6a857-2739">Citizen's Registration Number
</span><span class="sxs-lookup"><span data-stu-id="6a857-2739">Citizen's Registration Number</span></span> 
- <span data-ttu-id="6a857-2740">Jumin deungnok beonho
</span><span class="sxs-lookup"><span data-stu-id="6a857-2740">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="6a857-2741">RRN
</span><span class="sxs-lookup"><span data-stu-id="6a857-2741">RRN</span></span> 
- <span data-ttu-id="6a857-2742">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="6a857-2742">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="6a857-2743">西班牙社会保险号码 (SSN)</span><span class="sxs-lookup"><span data-stu-id="6a857-2743">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2744">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2744">Format</span></span>

<span data-ttu-id="6a857-2745">11-12 个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2745">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2746">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2746">Pattern</span></span>

<span data-ttu-id="6a857-2747">11-12 数字：</span><span class="sxs-lookup"><span data-stu-id="6a857-2747">11-12 digits:</span></span>
- <span data-ttu-id="6a857-2748">两位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2748">Two digits</span></span> 
- <span data-ttu-id="6a857-2749">正斜杠（可选）</span><span class="sxs-lookup"><span data-stu-id="6a857-2749">A forward slash (optional)</span></span> 
- <span data-ttu-id="6a857-2750">7-8 位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2750">7-8 digits</span></span> 
- <span data-ttu-id="6a857-2751">正斜杠（可选）</span><span class="sxs-lookup"><span data-stu-id="6a857-2751">A forward slash (optional)</span></span> 
- <span data-ttu-id="6a857-2752">两位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2752">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2753">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2753">Checksum</span></span>

<span data-ttu-id="6a857-2754">是</span><span class="sxs-lookup"><span data-stu-id="6a857-2754">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2755">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2755">Definition</span></span>

<span data-ttu-id="6a857-2756">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2756">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2757">函数 Func_spanish_social_security_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2757">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2758">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-2758">The checksum passes.</span></span>

```
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a857-2759">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2759">Keywords</span></span>

<span data-ttu-id="6a857-2760">无</span><span class="sxs-lookup"><span data-stu-id="6a857-2760">None</span></span>
   
## <a name="sweden-national-id"></a><span data-ttu-id="6a857-2761">瑞典国家 ID</span><span class="sxs-lookup"><span data-stu-id="6a857-2761">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2762">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2762">Format</span></span>

<span data-ttu-id="6a857-2763">10 个或 12 个数字和一个可选分隔符</span><span class="sxs-lookup"><span data-stu-id="6a857-2763">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2764">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2764">Pattern</span></span>

<span data-ttu-id="6a857-2765">10 或 12 位数字和可选的分隔符：</span><span class="sxs-lookup"><span data-stu-id="6a857-2765">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="6a857-2766">2-4 位数字（可选）</span><span class="sxs-lookup"><span data-stu-id="6a857-2766">2-4 digits (optional)</span></span> 
- <span data-ttu-id="6a857-2767">采用日期格式 YYMMDD 的六位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2767">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="6a857-2768">“-”或“+”（可选）的分隔符，加</span><span class="sxs-lookup"><span data-stu-id="6a857-2768">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="6a857-2769">四位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2769">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2770">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2770">Checksum</span></span>

<span data-ttu-id="6a857-2771">是</span><span class="sxs-lookup"><span data-stu-id="6a857-2771">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2772">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2772">Definition</span></span>

<span data-ttu-id="6a857-2773">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2773">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2774">函数 Func_swedish_national_identifier 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2774">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2775">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-2775">The checksum passes.</span></span>

```
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a857-2776">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2776">Keywords</span></span>

<span data-ttu-id="6a857-2777">否</span><span class="sxs-lookup"><span data-stu-id="6a857-2777">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="6a857-2778">瑞典护照号码</span><span class="sxs-lookup"><span data-stu-id="6a857-2778">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2779">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2779">Format</span></span>

<span data-ttu-id="6a857-2780">八个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2780">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2781">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2781">Pattern</span></span>

<span data-ttu-id="6a857-2782">八个连续的数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2782">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2783">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2783">Checksum</span></span>

<span data-ttu-id="6a857-2784">否</span><span class="sxs-lookup"><span data-stu-id="6a857-2784">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2785">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2785">Definition</span></span>

<span data-ttu-id="6a857-2786">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2786">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2787">正则表达式 Regex_sweden_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2787">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2788">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="6a857-2788">One of the following is true:</span></span>
    - <span data-ttu-id="6a857-2789">找到 Keyword_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2789">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="6a857-2790">找到 Keyword_sweden_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2790">A keyword from Keyword_sweden_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-2791">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2791">Keywords</span></span>
   
#### <a name="keywordswedenpassport"></a><span data-ttu-id="6a857-2792">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="6a857-2792">Keyword_sweden_passport</span></span>

- <span data-ttu-id="6a857-2793">visa requirements
</span><span class="sxs-lookup"><span data-stu-id="6a857-2793">visa requirements</span></span> 
- <span data-ttu-id="6a857-2794">Alien Registration Card
</span><span class="sxs-lookup"><span data-stu-id="6a857-2794">Alien Registration Card</span></span> 
- <span data-ttu-id="6a857-2795">Schengen visas
</span><span class="sxs-lookup"><span data-stu-id="6a857-2795">Schengen visas</span></span> 
- <span data-ttu-id="6a857-2796">Schengen visa
</span><span class="sxs-lookup"><span data-stu-id="6a857-2796">Schengen visa</span></span> 
- <span data-ttu-id="6a857-2797">Visa Processing
</span><span class="sxs-lookup"><span data-stu-id="6a857-2797">Visa Processing</span></span> 
- <span data-ttu-id="6a857-2798">Visa Type
</span><span class="sxs-lookup"><span data-stu-id="6a857-2798">Visa Type</span></span> 
- <span data-ttu-id="6a857-2799">Single Entry
</span><span class="sxs-lookup"><span data-stu-id="6a857-2799">Single Entry</span></span> 
- <span data-ttu-id="6a857-2800">Multiple Entry
</span><span class="sxs-lookup"><span data-stu-id="6a857-2800">Multiple Entry</span></span> 
- <span data-ttu-id="6a857-2801">G3 Processing Fees

</span><span class="sxs-lookup"><span data-stu-id="6a857-2801">G3 Processing Fees</span></span> 

#### <a name="keywordpassport"></a><span data-ttu-id="6a857-2802">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="6a857-2802">Keyword_passport</span></span>

- <span data-ttu-id="6a857-2803">Passport Number</span><span class="sxs-lookup"><span data-stu-id="6a857-2803">Passport Number</span></span> 
- <span data-ttu-id="6a857-2804">
Passport No</span><span class="sxs-lookup"><span data-stu-id="6a857-2804">Passport No</span></span> 
- <span data-ttu-id="6a857-2805">Passport #
</span><span class="sxs-lookup"><span data-stu-id="6a857-2805">Passport #</span></span> 
- <span data-ttu-id="6a857-2806">Passport#
</span><span class="sxs-lookup"><span data-stu-id="6a857-2806">Passport#</span></span> 
- <span data-ttu-id="6a857-2807">PassportID</span><span class="sxs-lookup"><span data-stu-id="6a857-2807">PassportID</span></span> 
- <span data-ttu-id="6a857-2808">Passportno
</span><span class="sxs-lookup"><span data-stu-id="6a857-2808">Passportno</span></span> 
- <span data-ttu-id="6a857-2809">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="6a857-2809">passportnumber</span></span> 
- <span data-ttu-id="6a857-2810">パスポート</span><span class="sxs-lookup"><span data-stu-id="6a857-2810">パスポート</span></span> 
- <span data-ttu-id="6a857-2811">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="6a857-2811">パスポート番号</span></span> 
- <span data-ttu-id="6a857-2812">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="6a857-2812">パスポートのNum</span></span> 
- <span data-ttu-id="6a857-2813">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="6a857-2813">パスポート＃</span></span> 
- <span data-ttu-id="6a857-2814">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="6a857-2814">Numéro de passeport</span></span> 
- <span data-ttu-id="6a857-2815">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="6a857-2815">Passeport n °</span></span> 
- <span data-ttu-id="6a857-2816">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="6a857-2816">Passeport Non</span></span> 
- <span data-ttu-id="6a857-2817">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="6a857-2817">Passeport #</span></span> 
- <span data-ttu-id="6a857-2818">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="6a857-2818">Passeport#</span></span> 
- <span data-ttu-id="6a857-2819">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="6a857-2819">PasseportNon</span></span> 
- <span data-ttu-id="6a857-2820">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="6a857-2820">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="6a857-2821">SWIFT 代码</span><span class="sxs-lookup"><span data-stu-id="6a857-2821">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2822">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2822">Format</span></span>

<span data-ttu-id="6a857-2823">四个字母后跟 5-31 个字母或数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2823">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2824">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2824">Pattern</span></span>

<span data-ttu-id="6a857-2825">四个字母后跟 5-31 个字母或数字：</span><span class="sxs-lookup"><span data-stu-id="6a857-2825">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="6a857-2826">四个字母的银行代码（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="6a857-2826">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="6a857-2827">可选空格</span><span class="sxs-lookup"><span data-stu-id="6a857-2827">An optional space</span></span> 
- <span data-ttu-id="6a857-2828">4-28 个字母或数字（基本银行账号 (BBAN)）</span><span class="sxs-lookup"><span data-stu-id="6a857-2828">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="6a857-2829">可选空格</span><span class="sxs-lookup"><span data-stu-id="6a857-2829">An optional space</span></span> 
- <span data-ttu-id="6a857-2830">1-3 个字母或数字（BBAN 的剩余内容）</span><span class="sxs-lookup"><span data-stu-id="6a857-2830">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2831">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2831">Checksum</span></span>

<span data-ttu-id="6a857-2832">否</span><span class="sxs-lookup"><span data-stu-id="6a857-2832">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2833">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2833">Definition</span></span>

<span data-ttu-id="6a857-2834">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2834">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2835">正则表达式 Regex_swift 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2835">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2836">找到 Keyword_swift 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2836">A keyword from Keyword_swift is found.</span></span>

```
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a857-2837">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2837">Keywords</span></span>
   
#### <a name="keywordswift"></a><span data-ttu-id="6a857-2838">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="6a857-2838">Keyword_swift</span></span>

- <span data-ttu-id="6a857-2839">international organization for standardization 9362
</span><span class="sxs-lookup"><span data-stu-id="6a857-2839">international organization for standardization 9362</span></span> 
- <span data-ttu-id="6a857-2840">iso 9362
</span><span class="sxs-lookup"><span data-stu-id="6a857-2840">iso 9362</span></span> 
- <span data-ttu-id="6a857-2841">iso9362</span><span class="sxs-lookup"><span data-stu-id="6a857-2841">iso9362</span></span> 
- <span data-ttu-id="6a857-2842">swift\#</span><span class="sxs-lookup"><span data-stu-id="6a857-2842">swift\#</span></span> 
- <span data-ttu-id="6a857-2843">swiftcode
</span><span class="sxs-lookup"><span data-stu-id="6a857-2843">swiftcode</span></span> 
- <span data-ttu-id="6a857-2844">swiftnumber
</span><span class="sxs-lookup"><span data-stu-id="6a857-2844">swiftnumber</span></span> 
- <span data-ttu-id="6a857-2845">swiftroutingnumber
</span><span class="sxs-lookup"><span data-stu-id="6a857-2845">swiftroutingnumber</span></span> 
- <span data-ttu-id="6a857-2846">swift 代码</span><span class="sxs-lookup"><span data-stu-id="6a857-2846">swift code</span></span> 
- <span data-ttu-id="6a857-2847">swift number #
</span><span class="sxs-lookup"><span data-stu-id="6a857-2847">swift number #</span></span> 
- <span data-ttu-id="6a857-2848">swift routing number
</span><span class="sxs-lookup"><span data-stu-id="6a857-2848">swift routing number</span></span> 
- <span data-ttu-id="6a857-2849">bic number
</span><span class="sxs-lookup"><span data-stu-id="6a857-2849">bic number</span></span> 
- <span data-ttu-id="6a857-2850">bic code
</span><span class="sxs-lookup"><span data-stu-id="6a857-2850">bic code</span></span> 
- <span data-ttu-id="6a857-2851">bic\#</span><span class="sxs-lookup"><span data-stu-id="6a857-2851">bic \#</span></span> 
- <span data-ttu-id="6a857-2852">bic\#</span><span class="sxs-lookup"><span data-stu-id="6a857-2852">bic\#</span></span> 
- <span data-ttu-id="6a857-2853">bank identifier code
</span><span class="sxs-lookup"><span data-stu-id="6a857-2853">bank identifier code</span></span> 
- <span data-ttu-id="6a857-2854">標準化9362</span><span class="sxs-lookup"><span data-stu-id="6a857-2854">標準化9362</span></span> 
- <span data-ttu-id="6a857-2855">迅速＃
</span><span class="sxs-lookup"><span data-stu-id="6a857-2855">迅速＃</span></span> 
- <span data-ttu-id="6a857-2856">SWIFTコード
</span><span class="sxs-lookup"><span data-stu-id="6a857-2856">SWIFTコード</span></span> 
- <span data-ttu-id="6a857-2857">SWIFT番号
</span><span class="sxs-lookup"><span data-stu-id="6a857-2857">SWIFT番号</span></span> 
- <span data-ttu-id="6a857-2858">迅速なルーティング番号
</span><span class="sxs-lookup"><span data-stu-id="6a857-2858">迅速なルーティング番号</span></span> 
- <span data-ttu-id="6a857-2859">BIC番号
</span><span class="sxs-lookup"><span data-stu-id="6a857-2859">BIC番号</span></span> 
- <span data-ttu-id="6a857-2860">BICコード
</span><span class="sxs-lookup"><span data-stu-id="6a857-2860">BICコード</span></span> 
- <span data-ttu-id="6a857-2861">銀行識別コードのための国際組織
</span><span class="sxs-lookup"><span data-stu-id="6a857-2861">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="6a857-2862">Organisation internationale de normalisation 9362
</span><span class="sxs-lookup"><span data-stu-id="6a857-2862">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="6a857-2863">rapide\#</span><span class="sxs-lookup"><span data-stu-id="6a857-2863">rapide \#</span></span> 
- <span data-ttu-id="6a857-2864">code SWIFT
</span><span class="sxs-lookup"><span data-stu-id="6a857-2864">code SWIFT</span></span> 
- <span data-ttu-id="6a857-2865">le numéro de swift
</span><span class="sxs-lookup"><span data-stu-id="6a857-2865">le numéro de swift</span></span> 
- <span data-ttu-id="6a857-2866">swift numéro d'acheminement
</span><span class="sxs-lookup"><span data-stu-id="6a857-2866">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="6a857-2867">le numéro BIC
</span><span class="sxs-lookup"><span data-stu-id="6a857-2867">le numéro BIC</span></span> 
- <span data-ttu-id="6a857-2868">\#BIC</span><span class="sxs-lookup"><span data-stu-id="6a857-2868">\# BIC</span></span> 
- <span data-ttu-id="6a857-2869">code identificateur de banque
</span><span class="sxs-lookup"><span data-stu-id="6a857-2869">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="6a857-2870">台湾国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="6a857-2870">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2871">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2871">Format</span></span>

<span data-ttu-id="6a857-2872">一个字母后跟九个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2872">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2873">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2873">Pattern</span></span>

<span data-ttu-id="6a857-2874">一个字母后跟 9 位数字：</span><span class="sxs-lookup"><span data-stu-id="6a857-2874">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="6a857-2875">一个字母（英文，不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="6a857-2875">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="6a857-2876">数字“1”或“2”</span><span class="sxs-lookup"><span data-stu-id="6a857-2876">The digit "1" or "2"</span></span> 
- <span data-ttu-id="6a857-2877">八个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2877">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2878">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2878">Checksum</span></span>

<span data-ttu-id="6a857-2879">是</span><span class="sxs-lookup"><span data-stu-id="6a857-2879">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2880">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2880">Definition</span></span>

<span data-ttu-id="6a857-2881">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2881">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2882">函数 Func_taiwanese_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2882">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2883">找到 Keyword_taiwanese_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2883">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="6a857-2884">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-2884">The checksum passes.</span></span>

```
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a857-2885">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2885">Keywords</span></span>

#### <a name="keywordtaiwanesenationalid"></a><span data-ttu-id="6a857-2886">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="6a857-2886">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="6a857-2887">身份證字號
</span><span class="sxs-lookup"><span data-stu-id="6a857-2887">身份證字號</span></span> 
- <span data-ttu-id="6a857-2888">身份證
</span><span class="sxs-lookup"><span data-stu-id="6a857-2888">身份證</span></span> 
- <span data-ttu-id="6a857-2889">身份證號碼
</span><span class="sxs-lookup"><span data-stu-id="6a857-2889">身份證號碼</span></span> 
- <span data-ttu-id="6a857-2890">身份證號
</span><span class="sxs-lookup"><span data-stu-id="6a857-2890">身份證號</span></span> 
- <span data-ttu-id="6a857-2891">身分證字號
</span><span class="sxs-lookup"><span data-stu-id="6a857-2891">身分證字號</span></span> 
- <span data-ttu-id="6a857-2892">身分證 </span><span class="sxs-lookup"><span data-stu-id="6a857-2892">身分證</span></span> 
- <span data-ttu-id="6a857-2893">身分證號碼
</span><span class="sxs-lookup"><span data-stu-id="6a857-2893">身分證號碼</span></span> 
- <span data-ttu-id="6a857-2894">身份證號
</span><span class="sxs-lookup"><span data-stu-id="6a857-2894">身份證號</span></span> 
- <span data-ttu-id="6a857-2895">身分證統一編號
</span><span class="sxs-lookup"><span data-stu-id="6a857-2895">身分證統一編號</span></span> 
- <span data-ttu-id="6a857-2896">國民身分證統一編號
</span><span class="sxs-lookup"><span data-stu-id="6a857-2896">國民身分證統一編號</span></span> 
- <span data-ttu-id="6a857-2897">簽名
</span><span class="sxs-lookup"><span data-stu-id="6a857-2897">簽名</span></span> 
- <span data-ttu-id="6a857-2898">蓋章
</span><span class="sxs-lookup"><span data-stu-id="6a857-2898">蓋章</span></span> 
- <span data-ttu-id="6a857-2899">簽名或蓋章

</span><span class="sxs-lookup"><span data-stu-id="6a857-2899">簽名或蓋章</span></span> 
- <span data-ttu-id="6a857-2900">簽章</span><span class="sxs-lookup"><span data-stu-id="6a857-2900">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="6a857-2901">	台湾护照号码</span><span class="sxs-lookup"><span data-stu-id="6a857-2901">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2902">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2902">Format</span></span>

- <span data-ttu-id="6a857-2903">生物护照号码： 九个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2903">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="6a857-2904">非生物护照号码： 九个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2904">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2905">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2905">Pattern</span></span>
<span data-ttu-id="6a857-2906">生物护照号码：</span><span class="sxs-lookup"><span data-stu-id="6a857-2906">Biometric passport number:</span></span>
- <span data-ttu-id="6a857-2907">数字“3” </span><span class="sxs-lookup"><span data-stu-id="6a857-2907">The digit "3"</span></span> 
- <span data-ttu-id="6a857-2908">八个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2908">Eight digits</span></span>

<span data-ttu-id="6a857-2909">非生物护照号码：</span><span class="sxs-lookup"><span data-stu-id="6a857-2909">Non-biometric passport number:</span></span>
- <span data-ttu-id="6a857-2910">九个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2910">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2911">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2911">Checksum</span></span>

<span data-ttu-id="6a857-2912">否</span><span class="sxs-lookup"><span data-stu-id="6a857-2912">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2913">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2913">Definition</span></span>

<span data-ttu-id="6a857-2914">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2914">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2915">正则表达式 Regex_taiwan_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2915">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2916">找到 Keyword_taiwan_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2916">A keyword from Keyword_taiwan_passport is found.</span></span>

```
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a857-2917">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2917">Keywords</span></span>

#### <a name="keywordtaiwanpassport"></a><span data-ttu-id="6a857-2918">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="6a857-2918">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="6a857-2919">台湾 passport number
</span><span class="sxs-lookup"><span data-stu-id="6a857-2919">ROC passport number</span></span> 
- <span data-ttu-id="6a857-2920">护照号码</span><span class="sxs-lookup"><span data-stu-id="6a857-2920">Passport number</span></span> 
- <span data-ttu-id="6a857-2921">Passport 没有</span><span class="sxs-lookup"><span data-stu-id="6a857-2921">Passport no</span></span> 
- <span data-ttu-id="6a857-2922">Passport Num
</span><span class="sxs-lookup"><span data-stu-id="6a857-2922">Passport Num</span></span> 
- <span data-ttu-id="6a857-2923">Passport #
</span><span class="sxs-lookup"><span data-stu-id="6a857-2923">Passport #</span></span> 
- <span data-ttu-id="6a857-2924">护照
</span><span class="sxs-lookup"><span data-stu-id="6a857-2924">护照</span></span> 
- <span data-ttu-id="6a857-2925">中華民國護照
</span><span class="sxs-lookup"><span data-stu-id="6a857-2925">中華民國護照</span></span> 
- <span data-ttu-id="6a857-2926">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="6a857-2926">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="6a857-2927">台湾居民证 (ARC/TARC) 号码</span><span class="sxs-lookup"><span data-stu-id="6a857-2927">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2928">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2928">Format</span></span>

<span data-ttu-id="6a857-2929">10 letters and digits</span><span class="sxs-lookup"><span data-stu-id="6a857-2929">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2930">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2930">Pattern</span></span>

<span data-ttu-id="6a857-2931">10 个字母和数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2931">10 letters and digits:</span></span>
- <span data-ttu-id="6a857-2932">两个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="6a857-2932">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="6a857-2933">八个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2933">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2934">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2934">Checksum</span></span>

<span data-ttu-id="6a857-2935">否</span><span class="sxs-lookup"><span data-stu-id="6a857-2935">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2936">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2936">Definition</span></span>

<span data-ttu-id="6a857-2937">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2937">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2938">正则表达式 Regex_taiwan_resident_certificate 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2938">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2939">找到 Keyword_taiwan_resident_certificate 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2939">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a857-2940">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2940">Keywords</span></span>

#### <a name="keywordtaiwanresidentcertificate"></a><span data-ttu-id="6a857-2941">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="6a857-2941">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="6a857-2942">Resident Certificate
</span><span class="sxs-lookup"><span data-stu-id="6a857-2942">Resident Certificate</span></span> 
- <span data-ttu-id="6a857-2943">驻留的证书</span><span class="sxs-lookup"><span data-stu-id="6a857-2943">Resident Cert</span></span> 
- <span data-ttu-id="6a857-2944">Resident Cert.
</span><span class="sxs-lookup"><span data-stu-id="6a857-2944">Resident Cert.</span></span> 
- <span data-ttu-id="6a857-2945">身份证</span><span class="sxs-lookup"><span data-stu-id="6a857-2945">Identification card</span></span> 
- <span data-ttu-id="6a857-2946">Alien Resident Certificate
</span><span class="sxs-lookup"><span data-stu-id="6a857-2946">Alien Resident Certificate</span></span> 
- <span data-ttu-id="6a857-2947">ARC
</span><span class="sxs-lookup"><span data-stu-id="6a857-2947">ARC</span></span> 
- <span data-ttu-id="6a857-2948">Taiwan Area Resident Certificate
</span><span class="sxs-lookup"><span data-stu-id="6a857-2948">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="6a857-2949">TARC
</span><span class="sxs-lookup"><span data-stu-id="6a857-2949">TARC</span></span> 
- <span data-ttu-id="6a857-2950">居留證
</span><span class="sxs-lookup"><span data-stu-id="6a857-2950">居留證</span></span> 
- <span data-ttu-id="6a857-2951">外僑居留證
</span><span class="sxs-lookup"><span data-stu-id="6a857-2951">外僑居留證</span></span> 
- <span data-ttu-id="6a857-2952">台灣地區居留證
</span><span class="sxs-lookup"><span data-stu-id="6a857-2952">台灣地區居留證</span></span> 
   
## <a name="uk-drivers-license-number"></a><span data-ttu-id="6a857-p141">英国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="6a857-p141">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2955">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2955">Format</span></span>

<span data-ttu-id="6a857-2956">特定格式的 18 个字母和数字组合</span><span class="sxs-lookup"><span data-stu-id="6a857-2956">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2957">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2957">Pattern</span></span>

<span data-ttu-id="6a857-2958">18 个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="6a857-2958">18 letters and digits:</span></span>
- <span data-ttu-id="6a857-2959">用五个字母（不区分大小写）或数字“9”来代替一个字母</span><span class="sxs-lookup"><span data-stu-id="6a857-2959">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="6a857-2960">一位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2960">One digit</span></span> 
- <span data-ttu-id="6a857-2961">采用日期格式 DDMMY 的五位数字，表示出生日期</span><span class="sxs-lookup"><span data-stu-id="6a857-2961">Five digits in the date format DDMMY for date of birth</span></span> 
- <span data-ttu-id="6a857-2962">用两个字母（不区分大小写）或数字“9”来代替一个字母</span><span class="sxs-lookup"><span data-stu-id="6a857-2962">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="6a857-2963">五位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2963">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2964">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2964">Checksum</span></span>

<span data-ttu-id="6a857-2965">是</span><span class="sxs-lookup"><span data-stu-id="6a857-2965">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2966">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2966">Definition</span></span>

<span data-ttu-id="6a857-2967">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2967">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2968">函数 Func_uk_drivers_license 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2968">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2969">找到 Keyword_uk_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2969">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="6a857-2970">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-2970">The checksum passes.</span></span>

```
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a857-2971">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-2971">Keywords</span></span>

#### <a name="keywordukdriverslicense"></a><span data-ttu-id="6a857-2972">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="6a857-2972">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="6a857-2973">DVLA
</span><span class="sxs-lookup"><span data-stu-id="6a857-2973">DVLA</span></span> 
- <span data-ttu-id="6a857-2974">light vans
</span><span class="sxs-lookup"><span data-stu-id="6a857-2974">light vans</span></span> 
- <span data-ttu-id="6a857-2975">quadbikes
</span><span class="sxs-lookup"><span data-stu-id="6a857-2975">quadbikes</span></span> 
- <span data-ttu-id="6a857-2976">motor cars
</span><span class="sxs-lookup"><span data-stu-id="6a857-2976">motor cars</span></span> 
- <span data-ttu-id="6a857-2977">125cc</span><span class="sxs-lookup"><span data-stu-id="6a857-2977">125cc</span></span> 
- <span data-ttu-id="6a857-2978">sidecar
</span><span class="sxs-lookup"><span data-stu-id="6a857-2978">sidecar</span></span> 
- <span data-ttu-id="6a857-2979">tricycles
</span><span class="sxs-lookup"><span data-stu-id="6a857-2979">tricycles</span></span> 
- <span data-ttu-id="6a857-2980">motorcycles
</span><span class="sxs-lookup"><span data-stu-id="6a857-2980">motorcycles</span></span> 
- <span data-ttu-id="6a857-2981">photocard licence
</span><span class="sxs-lookup"><span data-stu-id="6a857-2981">photocard licence</span></span> 
- <span data-ttu-id="6a857-2982">learner drivers
</span><span class="sxs-lookup"><span data-stu-id="6a857-2982">learner drivers</span></span> 
- <span data-ttu-id="6a857-2983">licence holder
</span><span class="sxs-lookup"><span data-stu-id="6a857-2983">licence holder</span></span> 
- <span data-ttu-id="6a857-2984">licence holders
</span><span class="sxs-lookup"><span data-stu-id="6a857-2984">licence holders</span></span> 
- <span data-ttu-id="6a857-2985">driving licences
</span><span class="sxs-lookup"><span data-stu-id="6a857-2985">driving licences</span></span> 
- <span data-ttu-id="6a857-2986">driving licence
</span><span class="sxs-lookup"><span data-stu-id="6a857-2986">driving licence</span></span> 
- <span data-ttu-id="6a857-2987">dual control car
</span><span class="sxs-lookup"><span data-stu-id="6a857-2987">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="6a857-p142">英国选民名册号码</span><span class="sxs-lookup"><span data-stu-id="6a857-p142">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-2990">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-2990">Format</span></span>

<span data-ttu-id="6a857-2991">两个字母后跟 1-4 个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2991">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-2992">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-2992">Pattern</span></span>

<span data-ttu-id="6a857-2993">两个字母（不区分大小写）后跟 1-4 个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-2993">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-2994">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-2994">Checksum</span></span>

<span data-ttu-id="6a857-2995">否</span><span class="sxs-lookup"><span data-stu-id="6a857-2995">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-2996">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-2996">Definition</span></span>

<span data-ttu-id="6a857-2997">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-2997">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-2998">正则表达式 Regex_uk_electoral 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-2998">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-2999">找到 Keyword_uk_electoral 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-2999">A keyword from Keyword_uk_electoral is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-3000">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-3000">Keywords</span></span>

#### <a name="keywordukelectoral"></a><span data-ttu-id="6a857-3001">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="6a857-3001">Keyword_uk_electoral</span></span>

- <span data-ttu-id="6a857-3002">council nomination
</span><span class="sxs-lookup"><span data-stu-id="6a857-3002">council nomination</span></span> 
- <span data-ttu-id="6a857-3003">nomination form
</span><span class="sxs-lookup"><span data-stu-id="6a857-3003">nomination form</span></span> 
- <span data-ttu-id="6a857-3004">electoral register

</span><span class="sxs-lookup"><span data-stu-id="6a857-3004">electoral register</span></span> 
- <span data-ttu-id="6a857-3005">electoral roll</span><span class="sxs-lookup"><span data-stu-id="6a857-3005">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="6a857-p143">英国国家卫生服务号码</span><span class="sxs-lookup"><span data-stu-id="6a857-p143">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-3008">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-3008">Format</span></span>

<span data-ttu-id="6a857-3009">10-17 个数字，通过空格分隔 </span><span class="sxs-lookup"><span data-stu-id="6a857-3009">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-3010">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-3010">Pattern</span></span>

<span data-ttu-id="6a857-3011">10-17 位数字：</span><span class="sxs-lookup"><span data-stu-id="6a857-3011">10-17 digits:</span></span>
- <span data-ttu-id="6a857-3012">3 或 10 位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-3012">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="6a857-3013">一个空格</span><span class="sxs-lookup"><span data-stu-id="6a857-3013">A space</span></span> 
- <span data-ttu-id="6a857-3014">三位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-3014">Three digits</span></span> 
- <span data-ttu-id="6a857-3015">一个空格</span><span class="sxs-lookup"><span data-stu-id="6a857-3015">A space</span></span> 
- <span data-ttu-id="6a857-3016">四位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-3016">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-3017">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-3017">Checksum</span></span>

<span data-ttu-id="6a857-3018">是</span><span class="sxs-lookup"><span data-stu-id="6a857-3018">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-3019">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-3019">Definition</span></span>

<span data-ttu-id="6a857-3020">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-3020">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-3021">函数 Func_uk_nhs_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-3021">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-3022">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="6a857-3022">One of the following is true:</span></span>
    - <span data-ttu-id="6a857-3023">找到 Keyword_uk_nhs_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-3023">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="6a857-3024">找到 Keyword_uk_nhs_number1 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-3024">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="6a857-3025">找到 Keyword_uk_nhs_number_dob 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-3025">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="6a857-3026">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="6a857-3026">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-3027">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-3027">Keywords</span></span>
   
#### <a name="keyworduknhsnumber"></a><span data-ttu-id="6a857-3028">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="6a857-3028">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="6a857-3029">national health service
</span><span class="sxs-lookup"><span data-stu-id="6a857-3029">national health service</span></span> 
- <span data-ttu-id="6a857-3030">nhs
</span><span class="sxs-lookup"><span data-stu-id="6a857-3030">nhs</span></span> 
- <span data-ttu-id="6a857-3031">health services authority

</span><span class="sxs-lookup"><span data-stu-id="6a857-3031">health services authority</span></span> 
- <span data-ttu-id="6a857-3032">health authority</span><span class="sxs-lookup"><span data-stu-id="6a857-3032">health authority</span></span>

#### <a name="keyworduknhsnumber1"></a><span data-ttu-id="6a857-3033">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="6a857-3033">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="6a857-3034">patient id
</span><span class="sxs-lookup"><span data-stu-id="6a857-3034">patient id</span></span> 
- <span data-ttu-id="6a857-3035">patient identification
</span><span class="sxs-lookup"><span data-stu-id="6a857-3035">patient identification</span></span> 
- <span data-ttu-id="6a857-3036">patient no

</span><span class="sxs-lookup"><span data-stu-id="6a857-3036">patient no</span></span> 
- <span data-ttu-id="6a857-3037">patient number</span><span class="sxs-lookup"><span data-stu-id="6a857-3037">patient number</span></span>

#### <a name="keyworduknhsnumberdob"></a><span data-ttu-id="6a857-3038">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="6a857-3038">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="6a857-3039">GP</span><span class="sxs-lookup"><span data-stu-id="6a857-3039">GP</span></span> 
- <span data-ttu-id="6a857-3040">DOB
</span><span class="sxs-lookup"><span data-stu-id="6a857-3040">DOB</span></span> 
- <span data-ttu-id="6a857-3041">D.O.B</span><span class="sxs-lookup"><span data-stu-id="6a857-3041">D.O.B</span></span> 
- <span data-ttu-id="6a857-3042">Date of Birth
</span><span class="sxs-lookup"><span data-stu-id="6a857-3042">Date of Birth</span></span> 
- <span data-ttu-id="6a857-3043">Birth Date
</span><span class="sxs-lookup"><span data-stu-id="6a857-3043">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="6a857-p144">英国国家保险号码 (NINO)</span><span class="sxs-lookup"><span data-stu-id="6a857-p144">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="6a857-3046">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-3046">Format</span></span>

<span data-ttu-id="6a857-3047">7 个字符或 9 个字符，并用空格或短划线</span><span class="sxs-lookup"><span data-stu-id="6a857-3047">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-3048">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-3048">Pattern</span></span>

<span data-ttu-id="6a857-3049">两种可能的模式：</span><span class="sxs-lookup"><span data-stu-id="6a857-3049">Two possible patterns:</span></span>

- <span data-ttu-id="6a857-3050">两个字母 (有效 NINOs 使用此前缀，此模式中验证; 中只有某些字符不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="6a857-3050">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="6a857-3051">六位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-3051">Six digits</span></span>
- <span data-ttu-id="6a857-3052">任一 'A'，'B'，'C'，或具有 （如前缀，只某些字符允许在后缀; 不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="6a857-3052">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="6a857-3053">OR</span><span class="sxs-lookup"><span data-stu-id="6a857-3053">OR</span></span>

- <span data-ttu-id="6a857-3054">两个字母</span><span class="sxs-lookup"><span data-stu-id="6a857-3054">Two letters</span></span>
- <span data-ttu-id="6a857-3055">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="6a857-3055">A space or dash</span></span>
- <span data-ttu-id="6a857-3056">两位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-3056">Two digits</span></span>
- <span data-ttu-id="6a857-3057">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="6a857-3057">A space or dash</span></span>
- <span data-ttu-id="6a857-3058">两位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-3058">Two digits</span></span>
- <span data-ttu-id="6a857-3059">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="6a857-3059">A space or dash</span></span>
- <span data-ttu-id="6a857-3060">两位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-3060">Two digits</span></span>
- <span data-ttu-id="6a857-3061">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="6a857-3061">A space or dash</span></span>
- <span data-ttu-id="6a857-3062">任一 'A'，'B'，'C'，或具有</span><span class="sxs-lookup"><span data-stu-id="6a857-3062">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-3063">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-3063">Checksum</span></span>

<span data-ttu-id="6a857-3064">否</span><span class="sxs-lookup"><span data-stu-id="6a857-3064">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-3065">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-3065">Definition</span></span>

<span data-ttu-id="6a857-3066">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-3066">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-3067">函数 Func_uk_nino 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-3067">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-3068">找到 Keyword_uk_nino 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-3068">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="6a857-3069">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-3069">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-3070">函数 Func_uk_nino 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-3070">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-3071">未找到 Keyword_uk_nino 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-3071">No keyword from Keyword_uk_nino is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-3072">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-3072">Keywords</span></span>

#### <a name="keyworduknino"></a><span data-ttu-id="6a857-3073">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="6a857-3073">Keyword_uk_nino</span></span>

- <span data-ttu-id="6a857-3074">national insurance number
</span><span class="sxs-lookup"><span data-stu-id="6a857-3074">national insurance number</span></span> 
- <span data-ttu-id="6a857-3075">national insurance contributions
</span><span class="sxs-lookup"><span data-stu-id="6a857-3075">national insurance contributions</span></span> 
- <span data-ttu-id="6a857-3076">protection act
</span><span class="sxs-lookup"><span data-stu-id="6a857-3076">protection act</span></span> 
- <span data-ttu-id="6a857-3077">insurance
</span><span class="sxs-lookup"><span data-stu-id="6a857-3077">insurance</span></span> 
- <span data-ttu-id="6a857-3078">social security number
</span><span class="sxs-lookup"><span data-stu-id="6a857-3078">social security number</span></span> 
- <span data-ttu-id="6a857-3079">insurance application
</span><span class="sxs-lookup"><span data-stu-id="6a857-3079">insurance application</span></span> 
- <span data-ttu-id="6a857-3080">medical application
</span><span class="sxs-lookup"><span data-stu-id="6a857-3080">medical application</span></span> 
- <span data-ttu-id="6a857-3081">social insurance
</span><span class="sxs-lookup"><span data-stu-id="6a857-3081">social insurance</span></span> 
- <span data-ttu-id="6a857-3082">medical attention
</span><span class="sxs-lookup"><span data-stu-id="6a857-3082">medical attention</span></span> 
- <span data-ttu-id="6a857-3083">社会安全</span><span class="sxs-lookup"><span data-stu-id="6a857-3083">social security</span></span> 
- <span data-ttu-id="6a857-3084">great britain
</span><span class="sxs-lookup"><span data-stu-id="6a857-3084">great britain</span></span> 
- <span data-ttu-id="6a857-3085">insurance
</span><span class="sxs-lookup"><span data-stu-id="6a857-3085">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="6a857-p145">美国/英国护照号码</span><span class="sxs-lookup"><span data-stu-id="6a857-p145">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-3088">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-3088">Format</span></span>

<span data-ttu-id="6a857-3089">九个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-3089">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-3090">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-3090">Pattern</span></span>

<span data-ttu-id="6a857-3091">九个连续的数字</span><span class="sxs-lookup"><span data-stu-id="6a857-3091">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-3092">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-3092">Checksum</span></span>

<span data-ttu-id="6a857-3093">否</span><span class="sxs-lookup"><span data-stu-id="6a857-3093">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-3094">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-3094">Definition</span></span>

<span data-ttu-id="6a857-3095">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-3095">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-3096">函数 Func_usa_uk_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-3096">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-3097">找到 Keyword_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-3097">A keyword from Keyword_passport is found.</span></span>

```
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a857-3098">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-3098">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="6a857-3099">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="6a857-3099">Keyword_passport</span></span>

- <span data-ttu-id="6a857-3100">Passport Number</span><span class="sxs-lookup"><span data-stu-id="6a857-3100">Passport Number</span></span> 
- <span data-ttu-id="6a857-3101">
Passport No</span><span class="sxs-lookup"><span data-stu-id="6a857-3101">Passport No</span></span> 
- <span data-ttu-id="6a857-3102">Passport #
</span><span class="sxs-lookup"><span data-stu-id="6a857-3102">Passport #</span></span> 
- <span data-ttu-id="6a857-3103">Passport#
</span><span class="sxs-lookup"><span data-stu-id="6a857-3103">Passport#</span></span> 
- <span data-ttu-id="6a857-3104">PassportID</span><span class="sxs-lookup"><span data-stu-id="6a857-3104">PassportID</span></span> 
- <span data-ttu-id="6a857-3105">Passportno
</span><span class="sxs-lookup"><span data-stu-id="6a857-3105">Passportno</span></span> 
- <span data-ttu-id="6a857-3106">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="6a857-3106">passportnumber</span></span> 
- <span data-ttu-id="6a857-3107">パスポート</span><span class="sxs-lookup"><span data-stu-id="6a857-3107">パスポート</span></span> 
- <span data-ttu-id="6a857-3108">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="6a857-3108">パスポート番号</span></span> 
- <span data-ttu-id="6a857-3109">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="6a857-3109">パスポートのNum</span></span> 
- <span data-ttu-id="6a857-3110">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="6a857-3110">パスポート＃</span></span> 
- <span data-ttu-id="6a857-3111">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="6a857-3111">Numéro de passeport</span></span> 
- <span data-ttu-id="6a857-3112">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="6a857-3112">Passeport n °</span></span> 
- <span data-ttu-id="6a857-3113">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="6a857-3113">Passeport Non</span></span> 
- <span data-ttu-id="6a857-3114">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="6a857-3114">Passeport #</span></span> 
- <span data-ttu-id="6a857-3115">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="6a857-3115">Passeport#</span></span> 
- <span data-ttu-id="6a857-3116">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="6a857-3116">PasseportNon</span></span> 
- <span data-ttu-id="6a857-3117">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="6a857-3117">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="6a857-3118">美国银行帐号</span><span class="sxs-lookup"><span data-stu-id="6a857-3118">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-3119">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-3119">Format</span></span>

<span data-ttu-id="6a857-3120">8-17 个数字</span><span class="sxs-lookup"><span data-stu-id="6a857-3120">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-3121">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-3121">Pattern</span></span>

<span data-ttu-id="6a857-3122">8-17 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="6a857-3122">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-3123">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-3123">Checksum</span></span>

<span data-ttu-id="6a857-3124">否</span><span class="sxs-lookup"><span data-stu-id="6a857-3124">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-3125">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-3125">Definition</span></span>

<span data-ttu-id="6a857-3126">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-3126">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-3127">正则表达式 Regex_usa_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-3127">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-3128">找到 Keyword_usa_Bank_Account 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-3128">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6a857-3129">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-3129">Keywords</span></span>

#### <a name="keywordusabankaccount"></a><span data-ttu-id="6a857-3130">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="6a857-3130">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="6a857-3131">Checking Account Number
</span><span class="sxs-lookup"><span data-stu-id="6a857-3131">Checking Account Number</span></span> 
- <span data-ttu-id="6a857-3132">Checking Account
</span><span class="sxs-lookup"><span data-stu-id="6a857-3132">Checking Account</span></span> 
- <span data-ttu-id="6a857-3133">Checking Account #
</span><span class="sxs-lookup"><span data-stu-id="6a857-3133">Checking Account #</span></span> 
- <span data-ttu-id="6a857-3134">Checking Acct Number
</span><span class="sxs-lookup"><span data-stu-id="6a857-3134">Checking Acct Number</span></span> 
- <span data-ttu-id="6a857-3135">Checking Acct #
</span><span class="sxs-lookup"><span data-stu-id="6a857-3135">Checking Acct #</span></span> 
- <span data-ttu-id="6a857-3136">Checking Acct No.
</span><span class="sxs-lookup"><span data-stu-id="6a857-3136">Checking Acct No.</span></span> 
- <span data-ttu-id="6a857-3137">Checking Account No.
</span><span class="sxs-lookup"><span data-stu-id="6a857-3137">Checking Account No.</span></span> 
- <span data-ttu-id="6a857-3138">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="6a857-3138">Bank Account Number</span></span> 
- <span data-ttu-id="6a857-3139">Bank Account #
</span><span class="sxs-lookup"><span data-stu-id="6a857-3139">Bank Account #</span></span> 
- <span data-ttu-id="6a857-3140">Bank Acct Number
</span><span class="sxs-lookup"><span data-stu-id="6a857-3140">Bank Acct Number</span></span> 
- <span data-ttu-id="6a857-3141">Bank Acct #
</span><span class="sxs-lookup"><span data-stu-id="6a857-3141">Bank Acct #</span></span> 
- <span data-ttu-id="6a857-3142">Bank Acct No.
</span><span class="sxs-lookup"><span data-stu-id="6a857-3142">Bank Acct No.</span></span> 
- <span data-ttu-id="6a857-3143">Bank Account No.
</span><span class="sxs-lookup"><span data-stu-id="6a857-3143">Bank Account No.</span></span> 
- <span data-ttu-id="6a857-3144">Savings Account Number
</span><span class="sxs-lookup"><span data-stu-id="6a857-3144">Savings Account Number</span></span> 
- <span data-ttu-id="6a857-3145">Savings Account.
</span><span class="sxs-lookup"><span data-stu-id="6a857-3145">Savings Account.</span></span> 
- <span data-ttu-id="6a857-3146">Savings Account #
</span><span class="sxs-lookup"><span data-stu-id="6a857-3146">Savings Account #</span></span> 
- <span data-ttu-id="6a857-3147">Savings Acct Number
</span><span class="sxs-lookup"><span data-stu-id="6a857-3147">Savings Acct Number</span></span> 
- <span data-ttu-id="6a857-3148">Savings Acct #
</span><span class="sxs-lookup"><span data-stu-id="6a857-3148">Savings Acct #</span></span> 
- <span data-ttu-id="6a857-3149">Savings Acct No.
</span><span class="sxs-lookup"><span data-stu-id="6a857-3149">Savings Acct No.</span></span> 
- <span data-ttu-id="6a857-3150">Savings Account No.
</span><span class="sxs-lookup"><span data-stu-id="6a857-3150">Savings Account No.</span></span> 
- <span data-ttu-id="6a857-3151">Debit Account Number
</span><span class="sxs-lookup"><span data-stu-id="6a857-3151">Debit Account Number</span></span> 
- <span data-ttu-id="6a857-3152">Debit Account
</span><span class="sxs-lookup"><span data-stu-id="6a857-3152">Debit Account</span></span> 
- <span data-ttu-id="6a857-3153">Debit Account #
</span><span class="sxs-lookup"><span data-stu-id="6a857-3153">Debit Account #</span></span> 
- <span data-ttu-id="6a857-3154">Debit Acct Number
</span><span class="sxs-lookup"><span data-stu-id="6a857-3154">Debit Acct Number</span></span> 
- <span data-ttu-id="6a857-3155">Debit Acct #
</span><span class="sxs-lookup"><span data-stu-id="6a857-3155">Debit Acct #</span></span> 
- <span data-ttu-id="6a857-3156">Debit Acct No.
</span><span class="sxs-lookup"><span data-stu-id="6a857-3156">Debit Acct No.</span></span> 
- <span data-ttu-id="6a857-3157">Debit Account No.
</span><span class="sxs-lookup"><span data-stu-id="6a857-3157">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="6a857-3158">美国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="6a857-3158">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="6a857-3159">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-3159">Format</span></span>

<span data-ttu-id="6a857-3160">取决于州</span><span class="sxs-lookup"><span data-stu-id="6a857-3160">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-3161">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-3161">Pattern</span></span>

<span data-ttu-id="6a857-3162">取决于州 — 例如，纽约：</span><span class="sxs-lookup"><span data-stu-id="6a857-3162">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="6a857-3163">诸如 ddd ddd ddd 的 9 个数字的格式将匹配。</span><span class="sxs-lookup"><span data-stu-id="6a857-3163">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="6a857-3164">诸如 dddddddd 的 9 个数字将不匹配。</span><span class="sxs-lookup"><span data-stu-id="6a857-3164">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-3165">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-3165">Checksum</span></span>

<span data-ttu-id="6a857-3166">否</span><span class="sxs-lookup"><span data-stu-id="6a857-3166">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-3167">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-3167">Definition</span></span>

<span data-ttu-id="6a857-3168">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-3168">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-3169">函数 Func_new_york_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-3169">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-3170">找到 Keyword_[state_name]_drivers_license_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-3170">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="6a857-3171">找到 Keyword_us_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-3171">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="6a857-3172">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-3172">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-3173">函数 Func_new_york_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-3173">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-3174">找到 Keyword_[state_name]_drivers_license_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-3174">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="6a857-3175">找到 Keyword_us_drivers_license_abbreviations 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-3175">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="6a857-3176">未找到 Keyword_us_drivers_license 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-3176">No keyword from Keyword_us_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-3177">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-3177">Keywords</span></span>

#### <a name="keywordusdriverslicenseabbreviations"></a><span data-ttu-id="6a857-3178">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="6a857-3178">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="6a857-3179">DL</span><span class="sxs-lookup"><span data-stu-id="6a857-3179">DL</span></span> 
- <span data-ttu-id="6a857-3180">DLS</span><span class="sxs-lookup"><span data-stu-id="6a857-3180">DLS</span></span> 
- <span data-ttu-id="6a857-3181">CDL</span><span class="sxs-lookup"><span data-stu-id="6a857-3181">CDL</span></span> 
- <span data-ttu-id="6a857-3182">CDL</span><span class="sxs-lookup"><span data-stu-id="6a857-3182">CDLS</span></span> 
- <span data-ttu-id="6a857-3183">ID</span><span class="sxs-lookup"><span data-stu-id="6a857-3183">ID</span></span> 
- <span data-ttu-id="6a857-3184">Id</span><span class="sxs-lookup"><span data-stu-id="6a857-3184">IDs</span></span> 
- <span data-ttu-id="6a857-3185">DL#</span><span class="sxs-lookup"><span data-stu-id="6a857-3185">DL#</span></span> 
- <span data-ttu-id="6a857-3186">
DLS#
</span><span class="sxs-lookup"><span data-stu-id="6a857-3186">DLS#</span></span> 
- <span data-ttu-id="6a857-3187">CDL#
</span><span class="sxs-lookup"><span data-stu-id="6a857-3187">CDL#</span></span> 
- <span data-ttu-id="6a857-3188">CDLS#
</span><span class="sxs-lookup"><span data-stu-id="6a857-3188">CDLS#</span></span> 
- <span data-ttu-id="6a857-3189">ID#</span><span class="sxs-lookup"><span data-stu-id="6a857-3189">ID#</span></span>
- <span data-ttu-id="6a857-3190">
IDs#
</span><span class="sxs-lookup"><span data-stu-id="6a857-3190">IDs#</span></span> 
- <span data-ttu-id="6a857-3191">ID 号</span><span class="sxs-lookup"><span data-stu-id="6a857-3191">ID number</span></span> 
- <span data-ttu-id="6a857-3192">ID numbers
</span><span class="sxs-lookup"><span data-stu-id="6a857-3192">ID numbers</span></span> 
- <span data-ttu-id="6a857-3193">LIC</span><span class="sxs-lookup"><span data-stu-id="6a857-3193">LIC</span></span> 
- <span data-ttu-id="6a857-3194">LIC#
</span><span class="sxs-lookup"><span data-stu-id="6a857-3194">LIC#</span></span> 

#### <a name="keywordusdriverslicense"></a><span data-ttu-id="6a857-3195">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="6a857-3195">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="6a857-3196">DriverLic</span><span class="sxs-lookup"><span data-stu-id="6a857-3196">DriverLic</span></span> 
- <span data-ttu-id="6a857-3197">DriverLics</span><span class="sxs-lookup"><span data-stu-id="6a857-3197">DriverLics</span></span> 
- <span data-ttu-id="6a857-3198">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="6a857-3198">DriverLicense</span></span> 
- <span data-ttu-id="6a857-3199">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="6a857-3199">DriverLicenses</span></span> 
- <span data-ttu-id="6a857-3200">驱动程序 Lic</span><span class="sxs-lookup"><span data-stu-id="6a857-3200">Driver Lic</span></span> 
- <span data-ttu-id="6a857-3201">驱动程序 Lics</span><span class="sxs-lookup"><span data-stu-id="6a857-3201">Driver Lics</span></span> 
- <span data-ttu-id="6a857-3202">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="6a857-3202">Driver License</span></span> 
- <span data-ttu-id="6a857-3203">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="6a857-3203">Driver Licenses</span></span> 
- <span data-ttu-id="6a857-3204">DriversLic</span><span class="sxs-lookup"><span data-stu-id="6a857-3204">DriversLic</span></span> 
- <span data-ttu-id="6a857-3205">DriversLics</span><span class="sxs-lookup"><span data-stu-id="6a857-3205">DriversLics</span></span> 
- <span data-ttu-id="6a857-3206">驾驶员</span><span class="sxs-lookup"><span data-stu-id="6a857-3206">DriversLicense</span></span> 
- <span data-ttu-id="6a857-3207">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="6a857-3207">DriversLicenses</span></span> 
- <span data-ttu-id="6a857-3208">驱动因素 Lic</span><span class="sxs-lookup"><span data-stu-id="6a857-3208">Drivers Lic</span></span> 
- <span data-ttu-id="6a857-3209">驱动因素 Lics</span><span class="sxs-lookup"><span data-stu-id="6a857-3209">Drivers Lics</span></span> 
- <span data-ttu-id="6a857-3210">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="6a857-3210">Drivers License</span></span> 
- <span data-ttu-id="6a857-3211">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="6a857-3211">Drivers Licenses</span></span> 
- <span data-ttu-id="6a857-3212">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="6a857-3212">Driver'Lic</span></span> 
- <span data-ttu-id="6a857-3213">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="6a857-3213">Driver'Lics</span></span> 
- <span data-ttu-id="6a857-3214">Driver'License</span><span class="sxs-lookup"><span data-stu-id="6a857-3214">Driver'License</span></span> 
- <span data-ttu-id="6a857-3215">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="6a857-3215">Driver'Licenses</span></span> 
- <span data-ttu-id="6a857-3216">驱动因素 Lic</span><span class="sxs-lookup"><span data-stu-id="6a857-3216">Driver' Lic</span></span> 
- <span data-ttu-id="6a857-3217">驱动因素 Lics</span><span class="sxs-lookup"><span data-stu-id="6a857-3217">Driver' Lics</span></span> 
- <span data-ttu-id="6a857-3218">驱动因素许可证</span><span class="sxs-lookup"><span data-stu-id="6a857-3218">Driver' License</span></span> 
- <span data-ttu-id="6a857-3219">驱动因素许可证</span><span class="sxs-lookup"><span data-stu-id="6a857-3219">Driver' Licenses</span></span>
- <span data-ttu-id="6a857-3220">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="6a857-3220">Driver'sLic</span></span> 
- <span data-ttu-id="6a857-3221">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="6a857-3221">Driver'sLics</span></span> 
- <span data-ttu-id="6a857-3222">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="6a857-3222">Driver'sLicense</span></span> 
- <span data-ttu-id="6a857-3223">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="6a857-3223">Driver'sLicenses</span></span> 
- <span data-ttu-id="6a857-3224">驱动因素的 Lic</span><span class="sxs-lookup"><span data-stu-id="6a857-3224">Driver's Lic</span></span> 
- <span data-ttu-id="6a857-3225">驱动因素的 Lics</span><span class="sxs-lookup"><span data-stu-id="6a857-3225">Driver's Lics</span></span> 
- <span data-ttu-id="6a857-3226">驱动程序的许可证</span><span class="sxs-lookup"><span data-stu-id="6a857-3226">Driver's License</span></span> 
- <span data-ttu-id="6a857-3227">驱动程序的许可证</span><span class="sxs-lookup"><span data-stu-id="6a857-3227">Driver's Licenses</span></span> 
- <span data-ttu-id="6a857-3228">identification number
</span><span class="sxs-lookup"><span data-stu-id="6a857-3228">identification number</span></span> 
- <span data-ttu-id="6a857-3229">identification numbers
</span><span class="sxs-lookup"><span data-stu-id="6a857-3229">identification numbers</span></span> 
- <span data-ttu-id="6a857-3230">identification #
</span><span class="sxs-lookup"><span data-stu-id="6a857-3230">identification #</span></span> 
- <span data-ttu-id="6a857-3231">身份证</span><span class="sxs-lookup"><span data-stu-id="6a857-3231">id card</span></span> 
- <span data-ttu-id="6a857-3232">id 卡</span><span class="sxs-lookup"><span data-stu-id="6a857-3232">id cards</span></span> 
- <span data-ttu-id="6a857-3233">身份证</span><span class="sxs-lookup"><span data-stu-id="6a857-3233">identification card</span></span> 
- <span data-ttu-id="6a857-3234">身份证</span><span class="sxs-lookup"><span data-stu-id="6a857-3234">identification cards</span></span> 
- <span data-ttu-id="6a857-3235">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="6a857-3235">DriverLic#</span></span> 
- <span data-ttu-id="6a857-3236">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="6a857-3236">DriverLics#</span></span> 
- <span data-ttu-id="6a857-3237">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="6a857-3237">DriverLicense#</span></span> 
- <span data-ttu-id="6a857-3238">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="6a857-3238">DriverLicenses#</span></span> 
- <span data-ttu-id="6a857-3239">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="6a857-3239">Driver Lic#</span></span> 
- <span data-ttu-id="6a857-3240">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="6a857-3240">Driver Lics#</span></span> 
- <span data-ttu-id="6a857-3241">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="6a857-3241">Driver License#</span></span> 
- <span data-ttu-id="6a857-3242">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="6a857-3242">Driver Licenses#</span></span> 
- <span data-ttu-id="6a857-3243">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="6a857-3243">DriversLic#</span></span> 
- <span data-ttu-id="6a857-3244">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="6a857-3244">DriversLics#</span></span> 
- <span data-ttu-id="6a857-3245">驾驶员 #</span><span class="sxs-lookup"><span data-stu-id="6a857-3245">DriversLicense#</span></span> 
- <span data-ttu-id="6a857-3246">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="6a857-3246">DriversLicenses#</span></span> 
- <span data-ttu-id="6a857-3247">驱动因素 Lic #</span><span class="sxs-lookup"><span data-stu-id="6a857-3247">Drivers Lic#</span></span> 
- <span data-ttu-id="6a857-3248">驱动因素 Lics #</span><span class="sxs-lookup"><span data-stu-id="6a857-3248">Drivers Lics#</span></span> 
- <span data-ttu-id="6a857-3249">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="6a857-3249">Drivers License#</span></span> 
- <span data-ttu-id="6a857-3250">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="6a857-3250">Drivers Licenses#</span></span> 
- <span data-ttu-id="6a857-3251">Driver'Lic#
</span><span class="sxs-lookup"><span data-stu-id="6a857-3251">Driver'Lic#</span></span> 
- <span data-ttu-id="6a857-3252">Driver'Lics#
</span><span class="sxs-lookup"><span data-stu-id="6a857-3252">Driver'Lics#</span></span> 
- <span data-ttu-id="6a857-3253">Driver'License#
</span><span class="sxs-lookup"><span data-stu-id="6a857-3253">Driver'License#</span></span> 
- <span data-ttu-id="6a857-3254">Driver'Licenses#
</span><span class="sxs-lookup"><span data-stu-id="6a857-3254">Driver'Licenses#</span></span> 
- <span data-ttu-id="6a857-3255">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="6a857-3255">Driver' Lic#</span></span> 
- <span data-ttu-id="6a857-3256">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="6a857-3256">Driver' Lics#</span></span> 
- <span data-ttu-id="6a857-3257">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="6a857-3257">Driver' License#</span></span> 
- <span data-ttu-id="6a857-3258">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="6a857-3258">Driver' Licenses#</span></span> 
- <span data-ttu-id="6a857-3259">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="6a857-3259">Driver'sLic#</span></span> 
- <span data-ttu-id="6a857-3260">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="6a857-3260">Driver'sLics#</span></span> 
- <span data-ttu-id="6a857-3261">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="6a857-3261">Driver'sLicense#</span></span> 
- <span data-ttu-id="6a857-3262">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="6a857-3262">Driver'sLicenses#</span></span> 
- <span data-ttu-id="6a857-3263">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="6a857-3263">Driver's Lic#</span></span> 
- <span data-ttu-id="6a857-3264">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="6a857-3264">Driver's Lics#</span></span> 
- <span data-ttu-id="6a857-3265">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="6a857-3265">Driver's License#</span></span> 
- <span data-ttu-id="6a857-3266">Driver's Licenses#
</span><span class="sxs-lookup"><span data-stu-id="6a857-3266">Driver's Licenses#</span></span> 
- <span data-ttu-id="6a857-3267">id 卡 #</span><span class="sxs-lookup"><span data-stu-id="6a857-3267">id card#</span></span> 
- <span data-ttu-id="6a857-3268">id cards#
</span><span class="sxs-lookup"><span data-stu-id="6a857-3268">id cards#</span></span> 
- <span data-ttu-id="6a857-3269">identification card#
</span><span class="sxs-lookup"><span data-stu-id="6a857-3269">identification card#</span></span> 
- <span data-ttu-id="6a857-3270">identification cards#
</span><span class="sxs-lookup"><span data-stu-id="6a857-3270">identification cards#</span></span> 


#### <a name="keywordstatenamedriverslicensename"></a><span data-ttu-id="6a857-3271">Keyword_[state_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="6a857-3271">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="6a857-3272">州缩写（例如，“NY”）
</span><span class="sxs-lookup"><span data-stu-id="6a857-3272">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="6a857-3273">州名称（例如，“New York”）
</span><span class="sxs-lookup"><span data-stu-id="6a857-3273">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="6a857-3274">美国单独的纳税人标识号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="6a857-3274">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="6a857-3275">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-3275">Format</span></span>

<span data-ttu-id="6a857-3276">九个数字，以“9”开头，“7”或“8”作为第四个数字，可以采用空格或短划线格式</span><span class="sxs-lookup"><span data-stu-id="6a857-3276">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-3277">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-3277">Pattern</span></span>

<span data-ttu-id="6a857-3278">有格式模式：</span><span class="sxs-lookup"><span data-stu-id="6a857-3278">Formatted:</span></span>
- <span data-ttu-id="6a857-3279">数字“9”</span><span class="sxs-lookup"><span data-stu-id="6a857-3279">The digit "9"</span></span> 
- <span data-ttu-id="6a857-3280">两位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-3280">Two digits</span></span> 
- <span data-ttu-id="6a857-3281">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="6a857-3281">A space or dash</span></span> 
- <span data-ttu-id="6a857-3282">“7”或“8”</span><span class="sxs-lookup"><span data-stu-id="6a857-3282">A "7" or "8"</span></span> 
- <span data-ttu-id="6a857-3283">一位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-3283">A digit</span></span> 
- <span data-ttu-id="6a857-3284">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="6a857-3284">A space, or dash</span></span> 
- <span data-ttu-id="6a857-3285">四位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-3285">Four digits</span></span>

<span data-ttu-id="6a857-3286">无格式模式：</span><span class="sxs-lookup"><span data-stu-id="6a857-3286">Unformatted:</span></span>
- <span data-ttu-id="6a857-3287">数字“9”</span><span class="sxs-lookup"><span data-stu-id="6a857-3287">The digit "9"</span></span> 
- <span data-ttu-id="6a857-3288">两位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-3288">Two digits</span></span> 
- <span data-ttu-id="6a857-3289">“7”或“8”</span><span class="sxs-lookup"><span data-stu-id="6a857-3289">A "7" or "8"</span></span> 
- <span data-ttu-id="6a857-3290">五位数字</span><span class="sxs-lookup"><span data-stu-id="6a857-3290">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-3291">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-3291">Checksum</span></span>

<span data-ttu-id="6a857-3292">否</span><span class="sxs-lookup"><span data-stu-id="6a857-3292">No</span></span>

### <a name="definition"></a><span data-ttu-id="6a857-3293">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-3293">Definition</span></span>

<span data-ttu-id="6a857-3294">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-3294">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-3295">函数 Func_formatted_itin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-3295">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-3296">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="6a857-3296">At least one of the following is true:</span></span>
    - <span data-ttu-id="6a857-3297">找到 Keyword_itin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-3297">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="6a857-3298">函数 Func_us_address 找到正确日期格式的地址。</span><span class="sxs-lookup"><span data-stu-id="6a857-3298">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="6a857-3299">函数 Func_us_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="6a857-3299">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="6a857-3300">找到 Keyword_itin_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-3300">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="6a857-3301">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-3301">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-3302">函数 Func_unformatted_itin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-3302">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-3303">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="6a857-3303">At least one of the following is true:</span></span>
    - <span data-ttu-id="6a857-3304">找到 Keyword_itin_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-3304">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="6a857-3305">函数 Func_us_address 找到正确日期格式的地址。</span><span class="sxs-lookup"><span data-stu-id="6a857-3305">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="6a857-3306">函数 Func_us_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="6a857-3306">The function Func_us_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-3307">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-3307">Keywords</span></span>

#### <a name="keyworditin"></a><span data-ttu-id="6a857-3308">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="6a857-3308">Keyword_itin</span></span>

- <span data-ttu-id="6a857-3309">taxpayer
</span><span class="sxs-lookup"><span data-stu-id="6a857-3309">taxpayer</span></span> 
- <span data-ttu-id="6a857-3310">tax id
</span><span class="sxs-lookup"><span data-stu-id="6a857-3310">tax id</span></span> 
- <span data-ttu-id="6a857-3311">tax identification
</span><span class="sxs-lookup"><span data-stu-id="6a857-3311">tax identification</span></span> 
- <span data-ttu-id="6a857-3312">itin
</span><span class="sxs-lookup"><span data-stu-id="6a857-3312">itin</span></span> 
- <span data-ttu-id="6a857-3313">ssn</span><span class="sxs-lookup"><span data-stu-id="6a857-3313">ssn</span></span> 
- <span data-ttu-id="6a857-3314">tin
</span><span class="sxs-lookup"><span data-stu-id="6a857-3314">tin</span></span> 
- <span data-ttu-id="6a857-3315">社会安全</span><span class="sxs-lookup"><span data-stu-id="6a857-3315">social security</span></span> 
- <span data-ttu-id="6a857-3316">tax payer
</span><span class="sxs-lookup"><span data-stu-id="6a857-3316">tax payer</span></span> 
- <span data-ttu-id="6a857-3317">itins
</span><span class="sxs-lookup"><span data-stu-id="6a857-3317">itins</span></span> 
- <span data-ttu-id="6a857-3318">taxid

</span><span class="sxs-lookup"><span data-stu-id="6a857-3318">taxid</span></span> 
- <span data-ttu-id="6a857-3319">individual taxpayer
</span><span class="sxs-lookup"><span data-stu-id="6a857-3319">individual taxpayer</span></span> 

#### <a name="keyworditincollaborative"></a><span data-ttu-id="6a857-3320">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="6a857-3320">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="6a857-3321">License</span><span class="sxs-lookup"><span data-stu-id="6a857-3321">License</span></span> 
- <span data-ttu-id="6a857-3322">DL</span><span class="sxs-lookup"><span data-stu-id="6a857-3322">DL</span></span> 
- <span data-ttu-id="6a857-3323">DOB
</span><span class="sxs-lookup"><span data-stu-id="6a857-3323">DOB</span></span> 
- <span data-ttu-id="6a857-3324">出生日期</span><span class="sxs-lookup"><span data-stu-id="6a857-3324">Birthdate</span></span> 
- <span data-ttu-id="6a857-3325">生日 </span><span class="sxs-lookup"><span data-stu-id="6a857-3325">Birthday</span></span> 
- <span data-ttu-id="6a857-3326">Date of Birth
</span><span class="sxs-lookup"><span data-stu-id="6a857-3326">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="6a857-3327">美国社会保险号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="6a857-3327">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="6a857-3328">格式</span><span class="sxs-lookup"><span data-stu-id="6a857-3328">Format</span></span>

<span data-ttu-id="6a857-3329">9 个数字，可以是格式化模式，也可以是非格式化模式</span><span class="sxs-lookup"><span data-stu-id="6a857-3329">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="6a857-3330">如果在 2011 年中旬前发布，则 SSN 具有强格式，即数字的某部分必须介于某个有效的范围中（但是没有校验和）。</span><span class="sxs-lookup"><span data-stu-id="6a857-3330">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="6a857-3331">模式</span><span class="sxs-lookup"><span data-stu-id="6a857-3331">Pattern</span></span>

<span data-ttu-id="6a857-3332">四种不同模式中的 SSN 的四种函数外观：</span><span class="sxs-lookup"><span data-stu-id="6a857-3332">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="6a857-3333">Func_ssn 查找具有 2011 年以前使用短划线或空格格式化的强格式的 SSN（ddd-dd-dddd 或 ddd dd dddd）</span><span class="sxs-lookup"><span data-stu-id="6a857-3333">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="6a857-3334">Func_unformatted_ssn 查找具有 2011 年以前未格式化为 9 个连续数字的强格式的 SSN (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="6a857-3334">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="6a857-3335">Func_randomized_formatted_ssn 查找 2011 年后使用短划线或空格（ddd-dd-dddd 或 ddd dd dddd）格式化的 SSN</span><span class="sxs-lookup"><span data-stu-id="6a857-3335">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="6a857-3336">Func_randomized_unformatted_ssn 查找 2011 年后未格式化为 9 个连续数字 (ddddddddd) 的 SSN</span><span class="sxs-lookup"><span data-stu-id="6a857-3336">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="6a857-3337">校验和</span><span class="sxs-lookup"><span data-stu-id="6a857-3337">Checksum</span></span>

<span data-ttu-id="6a857-3338">否</span><span class="sxs-lookup"><span data-stu-id="6a857-3338">No</span></span>


### <a name="definition"></a><span data-ttu-id="6a857-3339">定义</span><span class="sxs-lookup"><span data-stu-id="6a857-3339">Definition</span></span>

<span data-ttu-id="6a857-3340">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-3340">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-3341">函数 Func_ssn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-3341">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-3342">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-3342">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="6a857-3343">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-3343">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-3344">函数 Func_unformatted_ssn 查找与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-3344">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-3345">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-3345">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="6a857-3346">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-3346">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-3347">函数 Func_randomized_formatted_ssn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-3347">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-3348">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-3348">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="6a857-3349">函数 Func_ssn 未找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-3349">The function Func_ssn does not find content that matches the pattern.</span></span>

<span data-ttu-id="6a857-3350">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 55% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="6a857-3350">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6a857-3351">函数 Func_randomized_unformatted_ssn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-3351">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="6a857-3352">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="6a857-3352">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="6a857-3353">函数 Func_unformatted_ssn 未找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="6a857-3353">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6a857-3354">关键字</span><span class="sxs-lookup"><span data-stu-id="6a857-3354">Keywords</span></span>

#### <a name="keywordssn"></a><span data-ttu-id="6a857-3355">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="6a857-3355">Keyword_ssn</span></span>

- <span data-ttu-id="6a857-3356">Social Security
</span><span class="sxs-lookup"><span data-stu-id="6a857-3356">Social Security</span></span> 
- <span data-ttu-id="6a857-3357">Social Security#
</span><span class="sxs-lookup"><span data-stu-id="6a857-3357">Social Security#</span></span> 
- <span data-ttu-id="6a857-3358">Soc Sec
</span><span class="sxs-lookup"><span data-stu-id="6a857-3358">Soc Sec</span></span> 
- <span data-ttu-id="6a857-3359">SSN</span><span class="sxs-lookup"><span data-stu-id="6a857-3359">SSN</span></span> 
- <span data-ttu-id="6a857-3360">SSNS
</span><span class="sxs-lookup"><span data-stu-id="6a857-3360">SSNS</span></span> 
- <span data-ttu-id="6a857-3361">SSN#
</span><span class="sxs-lookup"><span data-stu-id="6a857-3361">SSN#</span></span> 
- <span data-ttu-id="6a857-3362">SS#
</span><span class="sxs-lookup"><span data-stu-id="6a857-3362">SS#</span></span> 
- <span data-ttu-id="6a857-3363">SSID
</span><span class="sxs-lookup"><span data-stu-id="6a857-3363">SSID</span></span> 
   

