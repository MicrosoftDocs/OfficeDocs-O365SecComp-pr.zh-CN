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
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
ms.assetid: fd505979-76be-4d9f-b459-abef3fc9e86b
description: Office 365 安全性的数据丢失防护 (DLP)&amp;合规性中心包括可供您可以使用 DLP 策略中的 80 敏感信息类型。本主题列出了所有这些敏感信息类型，并显示 DLP 策略时检测到每种类型的寻找。
ms.openlocfilehash: 4b083f80e02c80053b63ee897b2515a4505c16d9
ms.sourcegitcommit: 8c5a88433cff23c59b436260808cf3d91b06fdef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2018
ms.locfileid: "27194733"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="e6b19-104">使用敏感信息类型查找什么</span><span class="sxs-lookup"><span data-stu-id="e6b19-104">What the sensitive information types look for</span></span>

<span data-ttu-id="e6b19-p102">Office 365 安全性的数据丢失防护 (DLP)&amp;合规性中心包括许多可供您可以使用 DLP 策略中的敏感信息类型。本主题列出了所有这些敏感信息类型，并显示 DLP 策略时检测到每种类型的寻找。敏感信息类型定义的正则表达式或函数可以识别的模式。此外，如关键字和校验和确定证据可以用于标识的敏感信息类型。在评估过程还使用可信度和接近度。</span><span class="sxs-lookup"><span data-stu-id="e6b19-p102">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies. This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type. A sensitive information type is defined by a pattern that can be identified by a regular expression or a function. In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type. Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="e6b19-110">ABA 银行代号</span><span class="sxs-lookup"><span data-stu-id="e6b19-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-111">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-111">Format</span></span>

<span data-ttu-id="e6b19-112">9 个数字，可以是格式化模式，也可以是非格式化模式 </span><span class="sxs-lookup"><span data-stu-id="e6b19-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-113">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-113">Pattern</span></span>

<span data-ttu-id="e6b19-114">有格式模式：</span><span class="sxs-lookup"><span data-stu-id="e6b19-114">Formatted:</span></span>
- <span data-ttu-id="e6b19-115">四个数字，以 0、 1、 2、 3、 6、 7 或 8 开头</span><span class="sxs-lookup"><span data-stu-id="e6b19-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="e6b19-116">连字符</span><span class="sxs-lookup"><span data-stu-id="e6b19-116">A hyphen</span></span>
- <span data-ttu-id="e6b19-117">四位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-117">Four digits</span></span>
- <span data-ttu-id="e6b19-118">连字符</span><span class="sxs-lookup"><span data-stu-id="e6b19-118">A hyphen</span></span>
- <span data-ttu-id="e6b19-119">一位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-119">A digit</span></span>

<span data-ttu-id="e6b19-120">未格式化： 9 连续的数字开头 0、 1、 2、 3、 6、 7 或 8</span><span class="sxs-lookup"><span data-stu-id="e6b19-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="e6b19-121">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-121">Checksum</span></span>

<span data-ttu-id="e6b19-122">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-123">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-123">Definition</span></span>

<span data-ttu-id="e6b19-124">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-125">函数 Func_aba_routing 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-126">找到 Keyword_ABA_Routing 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="e6b19-127">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-127">Keywords</span></span>

#### <a name="keywordabarouting"></a><span data-ttu-id="e6b19-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="e6b19-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="e6b19-129">aba</span><span class="sxs-lookup"><span data-stu-id="e6b19-129">aba</span></span>
- <span data-ttu-id="e6b19-130">
aba #</span><span class="sxs-lookup"><span data-stu-id="e6b19-130">aba #</span></span>
- <span data-ttu-id="e6b19-131">
aba routing #</span><span class="sxs-lookup"><span data-stu-id="e6b19-131">aba routing #</span></span>
- <span data-ttu-id="e6b19-132">aba 银行代号</span><span class="sxs-lookup"><span data-stu-id="e6b19-132">aba routing number</span></span>
- <span data-ttu-id="e6b19-133">
aba#</span><span class="sxs-lookup"><span data-stu-id="e6b19-133">aba#</span></span>
- <span data-ttu-id="e6b19-134">
abarouting#</span><span class="sxs-lookup"><span data-stu-id="e6b19-134">abarouting#</span></span>
- <span data-ttu-id="e6b19-135">
aba number</span><span class="sxs-lookup"><span data-stu-id="e6b19-135">aba number</span></span>
- <span data-ttu-id="e6b19-136">
abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="e6b19-136">abaroutingnumber</span></span>
- <span data-ttu-id="e6b19-137">
american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="e6b19-137">american bank association routing #</span></span>
- <span data-ttu-id="e6b19-138">
american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="e6b19-138">american bank association routing number</span></span>
- <span data-ttu-id="e6b19-139">
americanbankassociationrouting#</span><span class="sxs-lookup"><span data-stu-id="e6b19-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="e6b19-140">
americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="e6b19-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="e6b19-141">
bank routing number</span><span class="sxs-lookup"><span data-stu-id="e6b19-141">bank routing number</span></span>
- <span data-ttu-id="e6b19-142">
bankrouting#</span><span class="sxs-lookup"><span data-stu-id="e6b19-142">bankrouting#</span></span>
- <span data-ttu-id="e6b19-143">
bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="e6b19-143">bankroutingnumber</span></span>
- <span data-ttu-id="e6b19-144">
routing transit number</span><span class="sxs-lookup"><span data-stu-id="e6b19-144">routing transit number</span></span>
- <span data-ttu-id="e6b19-145">
RTN
</span><span class="sxs-lookup"><span data-stu-id="e6b19-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="e6b19-146">阿根廷国家身份证 (DNI) 号</span><span class="sxs-lookup"><span data-stu-id="e6b19-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-147">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-147">Format</span></span>

<span data-ttu-id="e6b19-148">八个数字，用点分隔</span><span class="sxs-lookup"><span data-stu-id="e6b19-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-149">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-149">Pattern</span></span>

<span data-ttu-id="e6b19-150">八个数字：</span><span class="sxs-lookup"><span data-stu-id="e6b19-150">Eight digits:</span></span>
- <span data-ttu-id="e6b19-151">两个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-151">Two digits</span></span>
- <span data-ttu-id="e6b19-152">一个点 </span><span class="sxs-lookup"><span data-stu-id="e6b19-152">A period</span></span>
- <span data-ttu-id="e6b19-153">三个数字 </span><span class="sxs-lookup"><span data-stu-id="e6b19-153">Three digits</span></span>
- <span data-ttu-id="e6b19-154">一个点 </span><span class="sxs-lookup"><span data-stu-id="e6b19-154">A period</span></span>
- <span data-ttu-id="e6b19-155">三个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-156">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-156">Checksum</span></span>

<span data-ttu-id="e6b19-157">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-158">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-158">Definition</span></span>

<span data-ttu-id="e6b19-159">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-160">正则表达式 Regex_argentina_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-161">找到 Keyword_argentina_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6b19-162">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-162">Keywords</span></span>

#### <a name="keywordargentinanationalid"></a><span data-ttu-id="e6b19-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="e6b19-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="e6b19-164">Argentina National Identity number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="e6b19-165">标识</span><span class="sxs-lookup"><span data-stu-id="e6b19-165">Identity</span></span> 
- <span data-ttu-id="e6b19-166">标识国家/地区身份证</span><span class="sxs-lookup"><span data-stu-id="e6b19-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="e6b19-167">DNI
</span><span class="sxs-lookup"><span data-stu-id="e6b19-167">DNI</span></span> 
- <span data-ttu-id="e6b19-168">NIC 的人员的国家/地区注册表</span><span class="sxs-lookup"><span data-stu-id="e6b19-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="e6b19-169">Documento Nacional de Identidad
</span><span class="sxs-lookup"><span data-stu-id="e6b19-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="e6b19-170">Registro Nacional de las Personas
</span><span class="sxs-lookup"><span data-stu-id="e6b19-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="e6b19-171">Identidad
</span><span class="sxs-lookup"><span data-stu-id="e6b19-171">Identidad</span></span> 
- <span data-ttu-id="e6b19-172">Identificación
</span><span class="sxs-lookup"><span data-stu-id="e6b19-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="e6b19-173">澳大利亚银行帐号</span><span class="sxs-lookup"><span data-stu-id="e6b19-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-174">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-174">Format</span></span>

<span data-ttu-id="e6b19-175">6-10 个数字，带或不带 BSB 号码 </span><span class="sxs-lookup"><span data-stu-id="e6b19-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-176">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-176">Pattern</span></span>

<span data-ttu-id="e6b19-p103">帐号是 6-10 位数字。澳大利亚银行状态分支编号：</span><span class="sxs-lookup"><span data-stu-id="e6b19-p103">Account number is 6-10 digits. Australia bank state branch number:</span></span>
- <span data-ttu-id="e6b19-179">三位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-179">Three digits</span></span> 
- <span data-ttu-id="e6b19-180">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="e6b19-180">A hyphen</span></span> 
- <span data-ttu-id="e6b19-181">三位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-182">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-182">Checksum</span></span>

<span data-ttu-id="e6b19-183">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-184">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-184">Definition</span></span>

<span data-ttu-id="e6b19-185">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-186">正则表达式 Regex_australia_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="e6b19-187">找到 Keyword_australia_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="e6b19-188">正则表达式 Regex_australia_bank_account_number_bsb 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="e6b19-189">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-190">正则表达式 Regex_australia_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="e6b19-191">找到 Keyword_australia_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-192">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-192">Keywords</span></span>

#### <a name="keywordaustraliabankaccountnumber"></a><span data-ttu-id="e6b19-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="e6b19-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="e6b19-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="e6b19-194">swift bank code</span></span>
- <span data-ttu-id="e6b19-195">
correspondent bank</span><span class="sxs-lookup"><span data-stu-id="e6b19-195">correspondent bank</span></span>
- <span data-ttu-id="e6b19-196">
base currency</span><span class="sxs-lookup"><span data-stu-id="e6b19-196">base currency</span></span>
- <span data-ttu-id="e6b19-197">
usa account</span><span class="sxs-lookup"><span data-stu-id="e6b19-197">usa account</span></span>
- <span data-ttu-id="e6b19-198">
holder address</span><span class="sxs-lookup"><span data-stu-id="e6b19-198">holder address</span></span>
- <span data-ttu-id="e6b19-199">
bank address</span><span class="sxs-lookup"><span data-stu-id="e6b19-199">bank address</span></span>
- <span data-ttu-id="e6b19-200">
information account</span><span class="sxs-lookup"><span data-stu-id="e6b19-200">information account</span></span>
- <span data-ttu-id="e6b19-201">
fund transfers</span><span class="sxs-lookup"><span data-stu-id="e6b19-201">fund transfers</span></span>
- <span data-ttu-id="e6b19-202">
bank charges</span><span class="sxs-lookup"><span data-stu-id="e6b19-202">bank charges</span></span>
- <span data-ttu-id="e6b19-203">
bank details</span><span class="sxs-lookup"><span data-stu-id="e6b19-203">bank details</span></span>
- <span data-ttu-id="e6b19-204">
banking information</span><span class="sxs-lookup"><span data-stu-id="e6b19-204">banking information</span></span>
- <span data-ttu-id="e6b19-205">
full names</span><span class="sxs-lookup"><span data-stu-id="e6b19-205">full names</span></span>
- <span data-ttu-id="e6b19-206">

iaea</span><span class="sxs-lookup"><span data-stu-id="e6b19-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="e6b19-207">澳大利亚驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-208">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-208">Format</span></span>

<span data-ttu-id="e6b19-209">九个字母和数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-210">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-210">Pattern</span></span>

<span data-ttu-id="e6b19-211">九个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="e6b19-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="e6b19-212">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="e6b19-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="e6b19-213">两位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-213">Two digits</span></span> 
- <span data-ttu-id="e6b19-214">五位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="e6b19-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="e6b19-215">或者</span><span class="sxs-lookup"><span data-stu-id="e6b19-215">OR</span></span>

- <span data-ttu-id="e6b19-216">1-2 个可选字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="e6b19-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="e6b19-217">4-9 位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-217">4-9 digits</span></span>

<span data-ttu-id="e6b19-218">或者</span><span class="sxs-lookup"><span data-stu-id="e6b19-218">OR</span></span>

- <span data-ttu-id="e6b19-219">九个数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="e6b19-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-220">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-220">Checksum</span></span>

<span data-ttu-id="e6b19-221">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-222">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-222">Definition</span></span>

<span data-ttu-id="e6b19-223">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-224">正则表达式 Regex_australia_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-225">找到 Keyword_australia_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="e6b19-226">未找到 Keyword_australia_drivers_license_number_exclusions 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-227">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-227">Keywords</span></span>

#### <a name="keywordaustraliadriverslicensenumber"></a><span data-ttu-id="e6b19-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="e6b19-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="e6b19-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="e6b19-229">international driving permits</span></span>
- <span data-ttu-id="e6b19-230">
australian automobile association</span><span class="sxs-lookup"><span data-stu-id="e6b19-230">australian automobile association</span></span>
- <span data-ttu-id="e6b19-231">
international driving permit</span><span class="sxs-lookup"><span data-stu-id="e6b19-231">international driving permit</span></span>
- <span data-ttu-id="e6b19-232">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="e6b19-232">DriverLicence</span></span>
- <span data-ttu-id="e6b19-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="e6b19-233">DriverLicences</span></span>
- <span data-ttu-id="e6b19-234">驱动程序 Lic</span><span class="sxs-lookup"><span data-stu-id="e6b19-234">Driver Lic</span></span>
- <span data-ttu-id="e6b19-235">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="e6b19-235">Driver Licence</span></span>
- <span data-ttu-id="e6b19-236">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="e6b19-236">Driver Licences</span></span>
- <span data-ttu-id="e6b19-237">DriversLic</span><span class="sxs-lookup"><span data-stu-id="e6b19-237">DriversLic</span></span>
- <span data-ttu-id="e6b19-238">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="e6b19-238">DriversLicence</span></span>
- <span data-ttu-id="e6b19-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="e6b19-239">DriversLicences</span></span>
- <span data-ttu-id="e6b19-240">驱动因素 Lic</span><span class="sxs-lookup"><span data-stu-id="e6b19-240">Drivers Lic</span></span>
- <span data-ttu-id="e6b19-241">驱动因素 Lics</span><span class="sxs-lookup"><span data-stu-id="e6b19-241">Drivers Lics</span></span>
- <span data-ttu-id="e6b19-242">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="e6b19-242">Drivers Licence</span></span>
- <span data-ttu-id="e6b19-243">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="e6b19-243">Drivers Licences</span></span>
- <span data-ttu-id="e6b19-244">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="e6b19-244">Driver'Lic</span></span>
- <span data-ttu-id="e6b19-245">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="e6b19-245">Driver'Lics</span></span>
- <span data-ttu-id="e6b19-246">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="e6b19-246">Driver'Licence</span></span>
- <span data-ttu-id="e6b19-247">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="e6b19-247">Driver'Licences</span></span>
- <span data-ttu-id="e6b19-248">驱动因素 Lic</span><span class="sxs-lookup"><span data-stu-id="e6b19-248">Driver' Lic</span></span>
- <span data-ttu-id="e6b19-249">驱动因素 Lics</span><span class="sxs-lookup"><span data-stu-id="e6b19-249">Driver' Lics</span></span>
- <span data-ttu-id="e6b19-250">驱动因素许可</span><span class="sxs-lookup"><span data-stu-id="e6b19-250">Driver' Licence</span></span>
- <span data-ttu-id="e6b19-251">驱动因素许可</span><span class="sxs-lookup"><span data-stu-id="e6b19-251">Driver' Licences</span></span>
- <span data-ttu-id="e6b19-252">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="e6b19-252">Driver'sLic</span></span>
- <span data-ttu-id="e6b19-253">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="e6b19-253">Driver'sLics</span></span>
- <span data-ttu-id="e6b19-254">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="e6b19-254">Driver'sLicence</span></span>
- <span data-ttu-id="e6b19-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="e6b19-255">Driver'sLicences</span></span>
- <span data-ttu-id="e6b19-256">驱动因素的 Lic</span><span class="sxs-lookup"><span data-stu-id="e6b19-256">Driver's Lic</span></span>
- <span data-ttu-id="e6b19-257">驱动因素的 Lics</span><span class="sxs-lookup"><span data-stu-id="e6b19-257">Driver's Lics</span></span>
- <span data-ttu-id="e6b19-258">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="e6b19-258">Driver's Licence</span></span>
- <span data-ttu-id="e6b19-259">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="e6b19-259">Driver's Licences</span></span>
- <span data-ttu-id="e6b19-260">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="e6b19-260">DriverLic#</span></span>
- <span data-ttu-id="e6b19-261">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="e6b19-261">DriverLics#</span></span>
- <span data-ttu-id="e6b19-262">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="e6b19-262">DriverLicence#</span></span>
- <span data-ttu-id="e6b19-263">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="e6b19-263">DriverLicences#</span></span>
- <span data-ttu-id="e6b19-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="e6b19-264">Driver Lic#</span></span>
- <span data-ttu-id="e6b19-265">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-265">Driver Lics#</span></span>
- <span data-ttu-id="e6b19-266">驱动程序许可 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-266">Driver Licence#</span></span>
- <span data-ttu-id="e6b19-267">驱动程序许可 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-267">Driver Licences#</span></span>
- <span data-ttu-id="e6b19-268">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="e6b19-268">DriversLic#</span></span>
- <span data-ttu-id="e6b19-269">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="e6b19-269">DriversLics#</span></span>
- <span data-ttu-id="e6b19-270">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="e6b19-270">DriversLicence#</span></span>
- <span data-ttu-id="e6b19-271">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="e6b19-271">DriversLicences#</span></span>
- <span data-ttu-id="e6b19-272">驱动因素 Lic #</span><span class="sxs-lookup"><span data-stu-id="e6b19-272">Drivers Lic#</span></span>
- <span data-ttu-id="e6b19-273">驱动因素 Lics #</span><span class="sxs-lookup"><span data-stu-id="e6b19-273">Drivers Lics#</span></span>
- <span data-ttu-id="e6b19-274">驱动因素许可 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-274">Drivers Licence#</span></span>
- <span data-ttu-id="e6b19-275">驱动因素许可 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-275">Drivers Licences#</span></span>
- <span data-ttu-id="e6b19-276">Driver'Lic#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-276">Driver'Lic#</span></span>
- <span data-ttu-id="e6b19-277">Driver'Lics#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-277">Driver'Lics#</span></span>
- <span data-ttu-id="e6b19-278">Driver'Licence#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-278">Driver'Licence#</span></span>
- <span data-ttu-id="e6b19-279">Driver'Licences#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-279">Driver'Licences#</span></span>
- <span data-ttu-id="e6b19-280">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-280">Driver' Lic#</span></span>
- <span data-ttu-id="e6b19-281">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-281">Driver' Lics#</span></span>
- <span data-ttu-id="e6b19-282">驱动因素许可 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-282">Driver' Licence#</span></span>
- <span data-ttu-id="e6b19-283">驱动因素许可 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-283">Driver' Licences#</span></span>
- <span data-ttu-id="e6b19-284">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="e6b19-284">Driver'sLic#</span></span>
- <span data-ttu-id="e6b19-285">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="e6b19-285">Driver'sLics#</span></span>
- <span data-ttu-id="e6b19-286">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="e6b19-286">Driver'sLicence#</span></span>
- <span data-ttu-id="e6b19-287">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="e6b19-287">Driver'sLicences#</span></span>
- <span data-ttu-id="e6b19-288">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-288">Driver's Lic#</span></span>
- <span data-ttu-id="e6b19-289">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-289">Driver's Lics#</span></span>
- <span data-ttu-id="e6b19-290">驱动程序的许可 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-290">Driver's Licence#</span></span>
- <span data-ttu-id="e6b19-291">驱动程序的许可 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-291">Driver's Licences#</span></span> 

#### <a name="keywordaustraliadriverslicensenumberexclusions"></a><span data-ttu-id="e6b19-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="e6b19-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="e6b19-293">aaa</span><span class="sxs-lookup"><span data-stu-id="e6b19-293">aaa</span></span>
- <span data-ttu-id="e6b19-294">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="e6b19-294">DriverLicense</span></span>
- <span data-ttu-id="e6b19-295">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="e6b19-295">DriverLicenses</span></span>
- <span data-ttu-id="e6b19-296">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="e6b19-296">Driver License</span></span>
- <span data-ttu-id="e6b19-297">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="e6b19-297">Driver Licenses</span></span>
- <span data-ttu-id="e6b19-298">驾驶员</span><span class="sxs-lookup"><span data-stu-id="e6b19-298">DriversLicense</span></span>
- <span data-ttu-id="e6b19-299">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="e6b19-299">DriversLicenses</span></span>
- <span data-ttu-id="e6b19-300">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="e6b19-300">Drivers License</span></span>
- <span data-ttu-id="e6b19-301">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="e6b19-301">Drivers Licenses</span></span>
- <span data-ttu-id="e6b19-302">Driver'License</span><span class="sxs-lookup"><span data-stu-id="e6b19-302">Driver'License</span></span>
- <span data-ttu-id="e6b19-303">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="e6b19-303">Driver'Licenses</span></span>
- <span data-ttu-id="e6b19-304">驱动因素许可证</span><span class="sxs-lookup"><span data-stu-id="e6b19-304">Driver' License</span></span>
- <span data-ttu-id="e6b19-305">驱动因素许可证</span><span class="sxs-lookup"><span data-stu-id="e6b19-305">Driver' Licenses</span></span>
- <span data-ttu-id="e6b19-306">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="e6b19-306">Driver'sLicense</span></span>
- <span data-ttu-id="e6b19-307">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="e6b19-307">Driver'sLicenses</span></span>
- <span data-ttu-id="e6b19-308">驱动程序的许可证</span><span class="sxs-lookup"><span data-stu-id="e6b19-308">Driver's License</span></span>
- <span data-ttu-id="e6b19-309">驱动程序的许可证</span><span class="sxs-lookup"><span data-stu-id="e6b19-309">Driver's Licenses</span></span>
- <span data-ttu-id="e6b19-310">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="e6b19-310">DriverLicense#</span></span>
- <span data-ttu-id="e6b19-311">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="e6b19-311">DriverLicenses#</span></span>
- <span data-ttu-id="e6b19-312">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-312">Driver License#</span></span>
- <span data-ttu-id="e6b19-313">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-313">Driver Licenses#</span></span>
- <span data-ttu-id="e6b19-314">驾驶员 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-314">DriversLicense#</span></span>
- <span data-ttu-id="e6b19-315">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="e6b19-315">DriversLicenses#</span></span>
- <span data-ttu-id="e6b19-316">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-316">Drivers License#</span></span>
- <span data-ttu-id="e6b19-317">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-317">Drivers Licenses#</span></span>
- <span data-ttu-id="e6b19-318">Driver'License#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-318">Driver'License#</span></span>
- <span data-ttu-id="e6b19-319">Driver'Licenses#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-319">Driver'Licenses#</span></span>
- <span data-ttu-id="e6b19-320">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-320">Driver' License#</span></span>
- <span data-ttu-id="e6b19-321">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-321">Driver' Licenses#</span></span>
- <span data-ttu-id="e6b19-322">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="e6b19-322">Driver'sLicense#</span></span>
- <span data-ttu-id="e6b19-323">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="e6b19-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="e6b19-324">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-324">Driver's License#</span></span>
- <span data-ttu-id="e6b19-325">

Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="e6b19-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="e6b19-326">澳大利亚医疗帐号</span><span class="sxs-lookup"><span data-stu-id="e6b19-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-327">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-327">Format</span></span>

<span data-ttu-id="e6b19-328">10-11 个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-329">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-329">Pattern</span></span>

<span data-ttu-id="e6b19-330">10-11 个数字：</span><span class="sxs-lookup"><span data-stu-id="e6b19-330">10-11 digits:</span></span>
- <span data-ttu-id="e6b19-331">第一个数字范围为 2-6</span><span class="sxs-lookup"><span data-stu-id="e6b19-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="e6b19-332">第九个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="e6b19-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="e6b19-333">第十个数字是问题数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="e6b19-334">第十一个数字（可选）是个人号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-335">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-335">Checksum</span></span>

<span data-ttu-id="e6b19-336">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-337">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-337">Definition</span></span>

<span data-ttu-id="e6b19-338">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-339">函数 Func_australian_medical_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-340">找到 Keyword_Australia_Medical_Account_Number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="e6b19-341">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-341">The checksum passes.</span></span>

<span data-ttu-id="e6b19-342">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-343">函数 Func_australian_medical_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-344">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-344">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-345">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-345">Keywords</span></span>

#### <a name="keywordaustraliamedicalaccountnumber"></a><span data-ttu-id="e6b19-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="e6b19-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="e6b19-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="e6b19-347">bank account details</span></span>
- <span data-ttu-id="e6b19-348">
medicare payments</span><span class="sxs-lookup"><span data-stu-id="e6b19-348">medicare payments</span></span>
- <span data-ttu-id="e6b19-349">
mortgage account</span><span class="sxs-lookup"><span data-stu-id="e6b19-349">mortgage account</span></span>
- <span data-ttu-id="e6b19-350">
bank payments</span><span class="sxs-lookup"><span data-stu-id="e6b19-350">bank payments</span></span>
- <span data-ttu-id="e6b19-351">
information branch</span><span class="sxs-lookup"><span data-stu-id="e6b19-351">information branch</span></span>
- <span data-ttu-id="e6b19-352">
credit card loan</span><span class="sxs-lookup"><span data-stu-id="e6b19-352">credit card loan</span></span>
- <span data-ttu-id="e6b19-353">
department of human services</span><span class="sxs-lookup"><span data-stu-id="e6b19-353">department of human services</span></span>
- <span data-ttu-id="e6b19-354">本地服务</span><span class="sxs-lookup"><span data-stu-id="e6b19-354">local service</span></span>
- <span data-ttu-id="e6b19-355">

medicare</span><span class="sxs-lookup"><span data-stu-id="e6b19-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="e6b19-356">澳大利亚护照号</span><span class="sxs-lookup"><span data-stu-id="e6b19-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-357">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-357">Format</span></span>

<span data-ttu-id="e6b19-358">一个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-359">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-359">Pattern</span></span>

<span data-ttu-id="e6b19-360">一个字母（不区分大小写）后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-361">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-361">Checksum</span></span>

<span data-ttu-id="e6b19-362">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-363">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-363">Definition</span></span>

<span data-ttu-id="e6b19-364">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-365">正则表达式 Regex_australia_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-366">找到从 Keyword_passport 或 Keyword_australia_passport_number 关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-367">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-367">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="e6b19-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="e6b19-368">Keyword_passport</span></span>

- <span data-ttu-id="e6b19-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="e6b19-369">Passport Number</span></span>
- <span data-ttu-id="e6b19-370">
Passport No</span><span class="sxs-lookup"><span data-stu-id="e6b19-370">Passport No</span></span>
- <span data-ttu-id="e6b19-371">Passport #
</span><span class="sxs-lookup"><span data-stu-id="e6b19-371">Passport #</span></span>
- <span data-ttu-id="e6b19-372">Passport#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-372">Passport#</span></span>
- <span data-ttu-id="e6b19-373">PassportID</span><span class="sxs-lookup"><span data-stu-id="e6b19-373">PassportID</span></span>
- <span data-ttu-id="e6b19-374">Passportno
</span><span class="sxs-lookup"><span data-stu-id="e6b19-374">Passportno</span></span>
- <span data-ttu-id="e6b19-375">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="e6b19-375">passportnumber</span></span>
- <span data-ttu-id="e6b19-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="e6b19-376">パスポート</span></span>
- <span data-ttu-id="e6b19-377">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="e6b19-377">パスポート番号</span></span>
- <span data-ttu-id="e6b19-378">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="e6b19-378">パスポートのNum</span></span>
- <span data-ttu-id="e6b19-379">
パスポート ＃
</span><span class="sxs-lookup"><span data-stu-id="e6b19-379">パスポート ＃</span></span> 
- <span data-ttu-id="e6b19-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="e6b19-380">Numéro de passeport</span></span>
- <span data-ttu-id="e6b19-381">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="e6b19-381">Passeport n °</span></span>
- <span data-ttu-id="e6b19-382">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="e6b19-382">Passeport Non</span></span>
- <span data-ttu-id="e6b19-383">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="e6b19-383">Passeport #</span></span>
- <span data-ttu-id="e6b19-384">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-384">Passeport#</span></span>
- <span data-ttu-id="e6b19-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="e6b19-385">PasseportNon</span></span>
- <span data-ttu-id="e6b19-386">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="e6b19-386">Passeportn °</span></span>

#### <a name="keywordaustraliapassportnumber"></a><span data-ttu-id="e6b19-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="e6b19-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="e6b19-388">passport</span><span class="sxs-lookup"><span data-stu-id="e6b19-388">passport</span></span>
- <span data-ttu-id="e6b19-389">
passport details</span><span class="sxs-lookup"><span data-stu-id="e6b19-389">passport details</span></span>
- <span data-ttu-id="e6b19-390">
immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="e6b19-390">immigration and citizenship</span></span>
- <span data-ttu-id="e6b19-391">
commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="e6b19-391">commonwealth of australia</span></span>
- <span data-ttu-id="e6b19-392">
department of immigration</span><span class="sxs-lookup"><span data-stu-id="e6b19-392">department of immigration</span></span>
- <span data-ttu-id="e6b19-393">
residential address</span><span class="sxs-lookup"><span data-stu-id="e6b19-393">residential address</span></span>
- <span data-ttu-id="e6b19-394">
department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="e6b19-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="e6b19-395">visa
</span><span class="sxs-lookup"><span data-stu-id="e6b19-395">visa</span></span>
- <span data-ttu-id="e6b19-396">
national identity card</span><span class="sxs-lookup"><span data-stu-id="e6b19-396">national identity card</span></span>
- <span data-ttu-id="e6b19-397">护照号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-397">passport number</span></span>
- <span data-ttu-id="e6b19-398">
travel document</span><span class="sxs-lookup"><span data-stu-id="e6b19-398">travel document</span></span>
- <span data-ttu-id="e6b19-399">

issuing authority</span><span class="sxs-lookup"><span data-stu-id="e6b19-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="e6b19-400">澳大利亚税号</span><span class="sxs-lookup"><span data-stu-id="e6b19-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-401">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-401">Format</span></span>

<span data-ttu-id="e6b19-402">8-9 个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-403">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-403">Pattern</span></span>

<span data-ttu-id="e6b19-404">通常 8-9 位数字，显示中包含空格，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e6b19-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="e6b19-405">三位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-405">Three digits</span></span> 
- <span data-ttu-id="e6b19-406">可选空格</span><span class="sxs-lookup"><span data-stu-id="e6b19-406">An optional space</span></span> 
- <span data-ttu-id="e6b19-407">三位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-407">Three digits</span></span> 
- <span data-ttu-id="e6b19-408">可选空格</span><span class="sxs-lookup"><span data-stu-id="e6b19-408">An optional space</span></span> 
- <span data-ttu-id="e6b19-409">2-3 位数字，最后一位数字是校验位</span><span class="sxs-lookup"><span data-stu-id="e6b19-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-410">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-410">Checksum</span></span>

<span data-ttu-id="e6b19-411">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-412">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-412">Definition</span></span>

<span data-ttu-id="e6b19-413">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-414">函数 Func_australian_tax_file_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-415">未找到 Keyword_Australia_Tax_File_Number 或 Keyword_number_exclusions 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="e6b19-416">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-416">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-417">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-417">Keywords</span></span>

#### <a name="keywordaustraliataxfilenumber"></a><span data-ttu-id="e6b19-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="e6b19-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="e6b19-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="e6b19-419">australian business number</span></span>
- <span data-ttu-id="e6b19-420">
marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="e6b19-420">marginal tax rate</span></span>
- <span data-ttu-id="e6b19-421">
medicare levy</span><span class="sxs-lookup"><span data-stu-id="e6b19-421">medicare levy</span></span>
- <span data-ttu-id="e6b19-422">
portfolio number</span><span class="sxs-lookup"><span data-stu-id="e6b19-422">portfolio number</span></span>
- <span data-ttu-id="e6b19-423">
service veterans</span><span class="sxs-lookup"><span data-stu-id="e6b19-423">service veterans</span></span>
- <span data-ttu-id="e6b19-424">
withholding tax</span><span class="sxs-lookup"><span data-stu-id="e6b19-424">withholding tax</span></span>
- <span data-ttu-id="e6b19-425">
individual tax return</span><span class="sxs-lookup"><span data-stu-id="e6b19-425">individual tax return</span></span>
- <span data-ttu-id="e6b19-426">

tax file number</span><span class="sxs-lookup"><span data-stu-id="e6b19-426">tax file number</span></span>

#### <a name="keywordnumberexclusions"></a><span data-ttu-id="e6b19-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="e6b19-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="e6b19-428">00000000</span><span class="sxs-lookup"><span data-stu-id="e6b19-428">00000000</span></span>
- <span data-ttu-id="e6b19-429">11111111</span><span class="sxs-lookup"><span data-stu-id="e6b19-429">11111111</span></span>
- <span data-ttu-id="e6b19-430">22222222</span><span class="sxs-lookup"><span data-stu-id="e6b19-430">22222222</span></span>
- <span data-ttu-id="e6b19-431">33333333</span><span class="sxs-lookup"><span data-stu-id="e6b19-431">33333333</span></span>
- <span data-ttu-id="e6b19-432">44444444</span><span class="sxs-lookup"><span data-stu-id="e6b19-432">44444444</span></span>
- <span data-ttu-id="e6b19-433">55555555</span><span class="sxs-lookup"><span data-stu-id="e6b19-433">55555555</span></span>
- <span data-ttu-id="e6b19-434">66666666</span><span class="sxs-lookup"><span data-stu-id="e6b19-434">66666666</span></span>
- <span data-ttu-id="e6b19-435">77777777</span><span class="sxs-lookup"><span data-stu-id="e6b19-435">77777777</span></span>
- <span data-ttu-id="e6b19-436">88888888</span><span class="sxs-lookup"><span data-stu-id="e6b19-436">88888888</span></span>
- <span data-ttu-id="e6b19-437">99999999</span><span class="sxs-lookup"><span data-stu-id="e6b19-437">99999999</span></span>
- <span data-ttu-id="e6b19-438">000000000</span><span class="sxs-lookup"><span data-stu-id="e6b19-438">000000000</span></span>
- <span data-ttu-id="e6b19-439">111111111</span><span class="sxs-lookup"><span data-stu-id="e6b19-439">111111111</span></span>
- <span data-ttu-id="e6b19-440">222222222</span><span class="sxs-lookup"><span data-stu-id="e6b19-440">222222222</span></span>
- <span data-ttu-id="e6b19-441">333333333</span><span class="sxs-lookup"><span data-stu-id="e6b19-441">333333333</span></span>
- <span data-ttu-id="e6b19-442">444444444</span><span class="sxs-lookup"><span data-stu-id="e6b19-442">444444444</span></span>
- <span data-ttu-id="e6b19-443">555555555</span><span class="sxs-lookup"><span data-stu-id="e6b19-443">555555555</span></span>
- <span data-ttu-id="e6b19-444">666666666</span><span class="sxs-lookup"><span data-stu-id="e6b19-444">666666666</span></span>
- <span data-ttu-id="e6b19-445">777777777</span><span class="sxs-lookup"><span data-stu-id="e6b19-445">777777777</span></span>
- <span data-ttu-id="e6b19-446">888888888</span><span class="sxs-lookup"><span data-stu-id="e6b19-446">888888888</span></span>
- <span data-ttu-id="e6b19-447">999999999</span><span class="sxs-lookup"><span data-stu-id="e6b19-447">999999999</span></span>
- <span data-ttu-id="e6b19-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="e6b19-448">0000000000</span></span>
- <span data-ttu-id="e6b19-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="e6b19-449">1111111111</span></span>
- <span data-ttu-id="e6b19-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="e6b19-450">2222222222</span></span>
- <span data-ttu-id="e6b19-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="e6b19-451">3333333333</span></span>
- <span data-ttu-id="e6b19-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="e6b19-452">4444444444</span></span>
- <span data-ttu-id="e6b19-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="e6b19-453">5555555555</span></span>
- <span data-ttu-id="e6b19-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="e6b19-454">6666666666</span></span>
- <span data-ttu-id="e6b19-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="e6b19-455">7777777777</span></span>
- <span data-ttu-id="e6b19-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="e6b19-456">8888888888</span></span>
- <span data-ttu-id="e6b19-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="e6b19-457">9999999999</span></span>
   
## <a name="belgium-national-number"></a><span data-ttu-id="e6b19-458">比利时国家号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-458">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-459">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-459">Format</span></span>

<span data-ttu-id="e6b19-460">11 个数字加分隔符</span><span class="sxs-lookup"><span data-stu-id="e6b19-460">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-461">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-461">Pattern</span></span>

<span data-ttu-id="e6b19-462">11 个数字加分隔符：</span><span class="sxs-lookup"><span data-stu-id="e6b19-462">11 digits plus delimiters:</span></span>
- <span data-ttu-id="e6b19-463">六个数字加两个点，采用格式  YY.MM.DD，代表出生日期  </span><span class="sxs-lookup"><span data-stu-id="e6b19-463">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="e6b19-464">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="e6b19-464">A hyphen</span></span> 
- <span data-ttu-id="e6b19-465">三个连续的数字（男性用奇数，女性用偶数） </span><span class="sxs-lookup"><span data-stu-id="e6b19-465">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="e6b19-466">一个点 </span><span class="sxs-lookup"><span data-stu-id="e6b19-466">A period</span></span> 
- <span data-ttu-id="e6b19-467">两个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="e6b19-467">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-468">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-468">Checksum</span></span>

<span data-ttu-id="e6b19-469">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-469">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-470">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-470">Definition</span></span>

<span data-ttu-id="e6b19-471">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-472">函数 Func_belgium_national_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-472">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-473">找到 Keyword_belgium_national_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-473">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="e6b19-474">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-474">The checksum passes.</span></span>

```
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6b19-475">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-475">Keywords</span></span>

#### <a name="keywordbelgiumnationalnumber"></a><span data-ttu-id="e6b19-476">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="e6b19-476">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="e6b19-477">Identity</span><span class="sxs-lookup"><span data-stu-id="e6b19-477">Identity</span></span>
- <span data-ttu-id="e6b19-478">Registration</span><span class="sxs-lookup"><span data-stu-id="e6b19-478">Registration</span></span>
- <span data-ttu-id="e6b19-479">Identification</span><span class="sxs-lookup"><span data-stu-id="e6b19-479">Identification</span></span> 
- <span data-ttu-id="e6b19-480">ID</span><span class="sxs-lookup"><span data-stu-id="e6b19-480">ID</span></span> 
- <span data-ttu-id="e6b19-481">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="e6b19-481">Identiteitskaart</span></span>
- <span data-ttu-id="e6b19-482">Registratie nummer 
</span><span class="sxs-lookup"><span data-stu-id="e6b19-482">Registratie nummer</span></span> 
- <span data-ttu-id="e6b19-483">Identificatie nummer
</span><span class="sxs-lookup"><span data-stu-id="e6b19-483">Identificatie nummer</span></span> 
- <span data-ttu-id="e6b19-484">Identiteit</span><span class="sxs-lookup"><span data-stu-id="e6b19-484">Identiteit</span></span>
- <span data-ttu-id="e6b19-485">Registratie</span><span class="sxs-lookup"><span data-stu-id="e6b19-485">Registratie</span></span>
- <span data-ttu-id="e6b19-486">Identificatie

</span><span class="sxs-lookup"><span data-stu-id="e6b19-486">Identificatie</span></span> 
- <span data-ttu-id="e6b19-487">Carte d’identité
</span><span class="sxs-lookup"><span data-stu-id="e6b19-487">Carte d’identité</span></span> 
- <span data-ttu-id="e6b19-488">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="e6b19-488">numéro d'immatriculation</span></span>
- <span data-ttu-id="e6b19-489">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="e6b19-489">numéro d'identification</span></span>
- <span data-ttu-id="e6b19-490">
identité
</span><span class="sxs-lookup"><span data-stu-id="e6b19-490">identité</span></span> 
- <span data-ttu-id="e6b19-491">inscription
</span><span class="sxs-lookup"><span data-stu-id="e6b19-491">inscription</span></span> 
- <span data-ttu-id="e6b19-492">Identifikation</span><span class="sxs-lookup"><span data-stu-id="e6b19-492">Identifikation</span></span>
- <span data-ttu-id="e6b19-493">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="e6b19-493">Identifizierung</span></span>
- <span data-ttu-id="e6b19-494">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="e6b19-494">Identifikationsnummer</span></span>
- <span data-ttu-id="e6b19-495">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="e6b19-495">Personalausweis</span></span>
- <span data-ttu-id="e6b19-496">Registrierung</span><span class="sxs-lookup"><span data-stu-id="e6b19-496">Registrierung</span></span>
- <span data-ttu-id="e6b19-497">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="e6b19-497">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="e6b19-498">巴西 CPF 号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-498">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-499">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-499">Format</span></span>

<span data-ttu-id="e6b19-500">11 个数字（包括校验位），可以格式化，也可以非格式化</span><span class="sxs-lookup"><span data-stu-id="e6b19-500">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-501">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-501">Pattern</span></span>

<span data-ttu-id="e6b19-502">有格式模式：</span><span class="sxs-lookup"><span data-stu-id="e6b19-502">Formatted:</span></span>
- <span data-ttu-id="e6b19-503">三个数字 </span><span class="sxs-lookup"><span data-stu-id="e6b19-503">Three digits</span></span> 
- <span data-ttu-id="e6b19-504">一个点 </span><span class="sxs-lookup"><span data-stu-id="e6b19-504">A period</span></span> 
- <span data-ttu-id="e6b19-505">三个数字 </span><span class="sxs-lookup"><span data-stu-id="e6b19-505">Three digits</span></span> 
- <span data-ttu-id="e6b19-506">一个点 </span><span class="sxs-lookup"><span data-stu-id="e6b19-506">A period</span></span> 
- <span data-ttu-id="e6b19-507">三个数字 </span><span class="sxs-lookup"><span data-stu-id="e6b19-507">Three digits</span></span> 
- <span data-ttu-id="e6b19-508">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="e6b19-508">A hyphen</span></span> 
- <span data-ttu-id="e6b19-509">两个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="e6b19-509">Two digits which are check digits</span></span>

<span data-ttu-id="e6b19-510">非格式化：</span><span class="sxs-lookup"><span data-stu-id="e6b19-510">Unformatted:</span></span>
- <span data-ttu-id="e6b19-511">11 个数字，其中最后两个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="e6b19-511">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-512">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-512">Checksum</span></span>

<span data-ttu-id="e6b19-513">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-513">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-514">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-514">Definition</span></span>

<span data-ttu-id="e6b19-515">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-515">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-516">函数 Func_brazil_cpf 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-516">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-517">找到 Keyword_brazil_cpf 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-517">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="e6b19-518">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-518">The checksum passes.</span></span>

<span data-ttu-id="e6b19-519">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-519">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-520">函数 Func_brazil_cpf 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-520">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-521">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-521">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-522">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-522">Keywords</span></span>

#### <a name="keywordbrazilcpf"></a><span data-ttu-id="e6b19-523">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="e6b19-523">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="e6b19-524">CPF</span><span class="sxs-lookup"><span data-stu-id="e6b19-524">CPF</span></span>
- <span data-ttu-id="e6b19-525">Identification</span><span class="sxs-lookup"><span data-stu-id="e6b19-525">Identification</span></span>
- <span data-ttu-id="e6b19-526">Registration</span><span class="sxs-lookup"><span data-stu-id="e6b19-526">Registration</span></span>
- <span data-ttu-id="e6b19-527">Revenue</span><span class="sxs-lookup"><span data-stu-id="e6b19-527">Revenue</span></span>
- <span data-ttu-id="e6b19-528">Cadastro de Pessoas Físicas
</span><span class="sxs-lookup"><span data-stu-id="e6b19-528">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="e6b19-529">Imposto
</span><span class="sxs-lookup"><span data-stu-id="e6b19-529">Imposto</span></span> 
- <span data-ttu-id="e6b19-530">Identificação
</span><span class="sxs-lookup"><span data-stu-id="e6b19-530">Identificação</span></span> 
- <span data-ttu-id="e6b19-531">Inscrição
</span><span class="sxs-lookup"><span data-stu-id="e6b19-531">Inscrição</span></span> 
- <span data-ttu-id="e6b19-532">Receita

</span><span class="sxs-lookup"><span data-stu-id="e6b19-532">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="e6b19-533">巴西法律实体编号 (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="e6b19-533">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-534">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-534">Format</span></span>

<span data-ttu-id="e6b19-535">14 个数字（包括注册号、分行号码和校验位），再加上分隔符</span><span class="sxs-lookup"><span data-stu-id="e6b19-535">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-536">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-536">Pattern</span></span>
<span data-ttu-id="e6b19-537">14 个数字，再加上分隔符：</span><span class="sxs-lookup"><span data-stu-id="e6b19-537">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="e6b19-538">两个数字 </span><span class="sxs-lookup"><span data-stu-id="e6b19-538">Two digits</span></span> 
- <span data-ttu-id="e6b19-539">一个点 </span><span class="sxs-lookup"><span data-stu-id="e6b19-539">A period</span></span> 
- <span data-ttu-id="e6b19-540">三个数字 </span><span class="sxs-lookup"><span data-stu-id="e6b19-540">Three digits</span></span> 
- <span data-ttu-id="e6b19-541">一个点 </span><span class="sxs-lookup"><span data-stu-id="e6b19-541">A period</span></span> 
- <span data-ttu-id="e6b19-542">三个数字（前 8 位数是注册号） </span><span class="sxs-lookup"><span data-stu-id="e6b19-542">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="e6b19-543">正斜杠 </span><span class="sxs-lookup"><span data-stu-id="e6b19-543">A forward slash</span></span> 
- <span data-ttu-id="e6b19-544">四位分行号码 </span><span class="sxs-lookup"><span data-stu-id="e6b19-544">Four-digit branch number</span></span> 
- <span data-ttu-id="e6b19-545">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="e6b19-545">A hyphen</span></span> 
- <span data-ttu-id="e6b19-546">两个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="e6b19-546">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-547">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-547">Checksum</span></span>

<span data-ttu-id="e6b19-548">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-548">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-549">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-549">Definition</span></span>

<span data-ttu-id="e6b19-550">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-550">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-551">函数 Func_brazil_cnpj 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-551">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-552">找到 Keyword_brazil_cnpj 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-552">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="e6b19-553">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-553">The checksum passes.</span></span>

<span data-ttu-id="e6b19-554">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-554">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-555">函数 Func_brazil_cnpj 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-555">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-556">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-556">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-557">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-557">Keywords</span></span>

#### <a name="keywordbrazilcnpj"></a><span data-ttu-id="e6b19-558">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="e6b19-558">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="e6b19-559">CNPJ
</span><span class="sxs-lookup"><span data-stu-id="e6b19-559">CNPJ</span></span> 
- <span data-ttu-id="e6b19-560">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="e6b19-560">CNPJ/MF</span></span> 
- <span data-ttu-id="e6b19-561">CNPJ-MF
</span><span class="sxs-lookup"><span data-stu-id="e6b19-561">CNPJ-MF</span></span> 
- <span data-ttu-id="e6b19-562">National Registry of Legal Entities
</span><span class="sxs-lookup"><span data-stu-id="e6b19-562">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="e6b19-563">Taxpayers Registry
</span><span class="sxs-lookup"><span data-stu-id="e6b19-563">Taxpayers Registry</span></span> 
- <span data-ttu-id="e6b19-564">Legal entity
</span><span class="sxs-lookup"><span data-stu-id="e6b19-564">Legal entity</span></span> 
- <span data-ttu-id="e6b19-565">Legal entities
</span><span class="sxs-lookup"><span data-stu-id="e6b19-565">Legal entities</span></span> 
- <span data-ttu-id="e6b19-566">Registration Status
</span><span class="sxs-lookup"><span data-stu-id="e6b19-566">Registration Status</span></span> 
- <span data-ttu-id="e6b19-567">Business
</span><span class="sxs-lookup"><span data-stu-id="e6b19-567">Business</span></span> 
- <span data-ttu-id="e6b19-568">Company</span><span class="sxs-lookup"><span data-stu-id="e6b19-568">Company</span></span>
- <span data-ttu-id="e6b19-569">CNPJ
</span><span class="sxs-lookup"><span data-stu-id="e6b19-569">CNPJ</span></span> 
- <span data-ttu-id="e6b19-570">Cadastro Nacional da Pessoa Jurídica
</span><span class="sxs-lookup"><span data-stu-id="e6b19-570">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="e6b19-571">Cadastro Geral de Contribuintes
</span><span class="sxs-lookup"><span data-stu-id="e6b19-571">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="e6b19-572">CGC
</span><span class="sxs-lookup"><span data-stu-id="e6b19-572">CGC</span></span> 
- <span data-ttu-id="e6b19-573">Pessoa jurídica
</span><span class="sxs-lookup"><span data-stu-id="e6b19-573">Pessoa jurídica</span></span> 
- <span data-ttu-id="e6b19-574">Pessoas jurídicas
</span><span class="sxs-lookup"><span data-stu-id="e6b19-574">Pessoas jurídicas</span></span> 
- <span data-ttu-id="e6b19-575">Situação cadastral
</span><span class="sxs-lookup"><span data-stu-id="e6b19-575">Situação cadastral</span></span> 
- <span data-ttu-id="e6b19-576">Inscrição
</span><span class="sxs-lookup"><span data-stu-id="e6b19-576">Inscrição</span></span> 
- <span data-ttu-id="e6b19-577">Empresa
</span><span class="sxs-lookup"><span data-stu-id="e6b19-577">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="e6b19-578">巴西国家身份证 (RG)</span><span class="sxs-lookup"><span data-stu-id="e6b19-578">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-579">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-579">Format</span></span>

<span data-ttu-id="e6b19-580">Registro Geral （旧格式）： 九个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-580">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="e6b19-581">Registro de Identidade (RIC) （新格式）： 11 位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-581">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-582">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-582">Pattern</span></span>

<span data-ttu-id="e6b19-583">Registro Geral（旧格式）：</span><span class="sxs-lookup"><span data-stu-id="e6b19-583">Registro Geral (old format):</span></span>
- <span data-ttu-id="e6b19-584">两个数字 </span><span class="sxs-lookup"><span data-stu-id="e6b19-584">Two digits</span></span> 
- <span data-ttu-id="e6b19-585">一个点 </span><span class="sxs-lookup"><span data-stu-id="e6b19-585">A period</span></span> 
- <span data-ttu-id="e6b19-586">三个数字 </span><span class="sxs-lookup"><span data-stu-id="e6b19-586">Three digits</span></span> 
- <span data-ttu-id="e6b19-587">一个点 </span><span class="sxs-lookup"><span data-stu-id="e6b19-587">A period</span></span> 
- <span data-ttu-id="e6b19-588">三个数字 </span><span class="sxs-lookup"><span data-stu-id="e6b19-588">Three digits</span></span> 
- <span data-ttu-id="e6b19-589">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="e6b19-589">A hyphen</span></span> 
- <span data-ttu-id="e6b19-590">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="e6b19-590">One digit which is a check digit</span></span>

<span data-ttu-id="e6b19-591">Registro de Identidade (RIC) （新格式）：</span><span class="sxs-lookup"><span data-stu-id="e6b19-591">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="e6b19-592">10 个数字 </span><span class="sxs-lookup"><span data-stu-id="e6b19-592">10 digits</span></span> 
- <span data-ttu-id="e6b19-593">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="e6b19-593">A hyphen</span></span> 
- <span data-ttu-id="e6b19-594">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="e6b19-594">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-595">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-595">Checksum</span></span>

<span data-ttu-id="e6b19-596">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-596">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-597">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-597">Definition</span></span>

<span data-ttu-id="e6b19-598">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-598">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-599">函数 Func_brazil_rg 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-599">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-600">找到 Keyword_brazil_rg 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-600">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="e6b19-601">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-601">The checksum passes.</span></span>

<span data-ttu-id="e6b19-602">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-602">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-603">函数 Func_brazil_rg 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-603">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-604">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-604">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-605">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-605">Keywords</span></span>

#### <a name="keywordbrazilrg"></a><span data-ttu-id="e6b19-606">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="e6b19-606">Keyword_brazil_rg</span></span>

<span data-ttu-id="e6b19-607">Cédula de identidade 身份证国家/地区 id número de rregistro registro de Iidentidade registro geral RG （此关键字是区分大小写） RIC （此关键字是区分大小写）</span><span class="sxs-lookup"><span data-stu-id="e6b19-607">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="e6b19-608">加拿大银行帐号</span><span class="sxs-lookup"><span data-stu-id="e6b19-608">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-609">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-609">Format</span></span>

<span data-ttu-id="e6b19-610">七个或十二个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-610">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-611">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-611">Pattern</span></span>

<span data-ttu-id="e6b19-612">加拿大银行帐号是七个或十二个数字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-612">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="e6b19-613">加拿大银行帐户的银行代号是：</span><span class="sxs-lookup"><span data-stu-id="e6b19-613">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="e6b19-614">五位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-614">Five digits</span></span> 
- <span data-ttu-id="e6b19-615">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="e6b19-615">A hyphen</span></span> 
- <span data-ttu-id="e6b19-616">三个数字或</span><span class="sxs-lookup"><span data-stu-id="e6b19-616">Three digits OR</span></span>
- <span data-ttu-id="e6b19-617">一个零“0” </span><span class="sxs-lookup"><span data-stu-id="e6b19-617">A zero "0"</span></span> 
- <span data-ttu-id="e6b19-618">八个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-618">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-619">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-619">Checksum</span></span>

<span data-ttu-id="e6b19-620">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-620">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-621">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-621">Definition</span></span>

<span data-ttu-id="e6b19-622">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-622">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-623">正则表达式 Regex_canada_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-623">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-624">找到 Keyword_canada_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-624">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="e6b19-625">正则表达式 Regex_canada_bank_account_transit_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-625">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="e6b19-626">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-627">正则表达式 Regex_canada_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-627">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-628">找到 Keyword_canada_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-628">A keyword from Keyword_canada_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-629">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-629">Keywords</span></span>

#### <a name="keywordcanadabankaccountnumber"></a><span data-ttu-id="e6b19-630">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="e6b19-630">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="e6b19-631">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="e6b19-631">canada savings bonds</span></span>
- <span data-ttu-id="e6b19-632">
canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="e6b19-632">canada revenue agency</span></span>
- <span data-ttu-id="e6b19-633">
canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="e6b19-633">canadian financial institution</span></span>
- <span data-ttu-id="e6b19-634">
direct deposit form</span><span class="sxs-lookup"><span data-stu-id="e6b19-634">direct deposit form</span></span>
- <span data-ttu-id="e6b19-635">
canadian citizen</span><span class="sxs-lookup"><span data-stu-id="e6b19-635">canadian citizen</span></span>
- <span data-ttu-id="e6b19-636">
legal representative</span><span class="sxs-lookup"><span data-stu-id="e6b19-636">legal representative</span></span>
- <span data-ttu-id="e6b19-637">
notary public</span><span class="sxs-lookup"><span data-stu-id="e6b19-637">notary public</span></span>
- <span data-ttu-id="e6b19-638">
commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="e6b19-638">commissioner for oaths</span></span>
- <span data-ttu-id="e6b19-639">
child care benefit</span><span class="sxs-lookup"><span data-stu-id="e6b19-639">child care benefit</span></span>
- <span data-ttu-id="e6b19-640">
universal child care</span><span class="sxs-lookup"><span data-stu-id="e6b19-640">universal child care</span></span>
- <span data-ttu-id="e6b19-641">
canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="e6b19-641">canada child tax benefit</span></span>
- <span data-ttu-id="e6b19-642">
income tax benefit</span><span class="sxs-lookup"><span data-stu-id="e6b19-642">income tax benefit</span></span>
- <span data-ttu-id="e6b19-643">
harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="e6b19-643">harmonized sales tax</span></span>
- <span data-ttu-id="e6b19-644">social insurance number</span><span class="sxs-lookup"><span data-stu-id="e6b19-644">social insurance number</span></span>
- <span data-ttu-id="e6b19-645">
income tax refund</span><span class="sxs-lookup"><span data-stu-id="e6b19-645">income tax refund</span></span>
- <span data-ttu-id="e6b19-646">
child tax benefit</span><span class="sxs-lookup"><span data-stu-id="e6b19-646">child tax benefit</span></span>
- <span data-ttu-id="e6b19-647">
territorial payments</span><span class="sxs-lookup"><span data-stu-id="e6b19-647">territorial payments</span></span>
- <span data-ttu-id="e6b19-648">
institution number</span><span class="sxs-lookup"><span data-stu-id="e6b19-648">institution number</span></span>
- <span data-ttu-id="e6b19-649">
deposit request</span><span class="sxs-lookup"><span data-stu-id="e6b19-649">deposit request</span></span>
- <span data-ttu-id="e6b19-650">
banking information</span><span class="sxs-lookup"><span data-stu-id="e6b19-650">banking information</span></span>
- <span data-ttu-id="e6b19-651">

direct deposit</span><span class="sxs-lookup"><span data-stu-id="e6b19-651">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="e6b19-652">加拿大驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-652">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-653">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-653">Format</span></span>

<span data-ttu-id="e6b19-654">因省而异</span><span class="sxs-lookup"><span data-stu-id="e6b19-654">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-655">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-655">Pattern</span></span>

<span data-ttu-id="e6b19-656">各种模式，涵盖艾伯塔、 不列颠哥伦比亚、 马尼托巴、 新不伦瑞克、 纽芬兰/拉布拉多、 新斯科舍、 安大略、 爱德华王子岛，魁北克和萨斯喀彻温</span><span class="sxs-lookup"><span data-stu-id="e6b19-656">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-657">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-657">Checksum</span></span>

<span data-ttu-id="e6b19-658">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-658">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-659">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-659">Definition</span></span>

<span data-ttu-id="e6b19-660">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-660">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-661">函数 Func_[province_name]_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-661">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-662">找到 Keyword_[province_name]_drivers_license_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-662">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="e6b19-663">找到 Keyword_canada_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-663">A keyword from Keyword_canada_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-664">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-664">Keywords</span></span>

#### <a name="keywordprovincenamedriverslicensename"></a><span data-ttu-id="e6b19-665">Keyword_[province_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="e6b19-665">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="e6b19-666">省/市/自治区的缩写，例如 AB</span><span class="sxs-lookup"><span data-stu-id="e6b19-666">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="e6b19-667">
省名称，例如 Alberta</span><span class="sxs-lookup"><span data-stu-id="e6b19-667">The province name, for example Alberta</span></span>

#### <a name="keywordcanadadriverslicense"></a><span data-ttu-id="e6b19-668">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="e6b19-668">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="e6b19-669">DL</span><span class="sxs-lookup"><span data-stu-id="e6b19-669">DL</span></span>
- <span data-ttu-id="e6b19-670">DLS</span><span class="sxs-lookup"><span data-stu-id="e6b19-670">DLS</span></span>
- <span data-ttu-id="e6b19-671">CDL</span><span class="sxs-lookup"><span data-stu-id="e6b19-671">CDL</span></span>
- <span data-ttu-id="e6b19-672">CDL</span><span class="sxs-lookup"><span data-stu-id="e6b19-672">CDLS</span></span>
- <span data-ttu-id="e6b19-673">DriverLic</span><span class="sxs-lookup"><span data-stu-id="e6b19-673">DriverLic</span></span>
- <span data-ttu-id="e6b19-674">DriverLics</span><span class="sxs-lookup"><span data-stu-id="e6b19-674">DriverLics</span></span>
- <span data-ttu-id="e6b19-675">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="e6b19-675">DriverLicense</span></span>
- <span data-ttu-id="e6b19-676">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="e6b19-676">DriverLicenses</span></span>
- <span data-ttu-id="e6b19-677">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="e6b19-677">DriverLicence</span></span>
- <span data-ttu-id="e6b19-678">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="e6b19-678">DriverLicences</span></span>
- <span data-ttu-id="e6b19-679">驱动程序 Lic</span><span class="sxs-lookup"><span data-stu-id="e6b19-679">Driver Lic</span></span>
- <span data-ttu-id="e6b19-680">驱动程序 Lics</span><span class="sxs-lookup"><span data-stu-id="e6b19-680">Driver Lics</span></span>
- <span data-ttu-id="e6b19-681">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="e6b19-681">Driver License</span></span>
- <span data-ttu-id="e6b19-682">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="e6b19-682">Driver Licenses</span></span>
- <span data-ttu-id="e6b19-683">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="e6b19-683">Driver Licence</span></span>
- <span data-ttu-id="e6b19-684">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="e6b19-684">Driver Licences</span></span>
- <span data-ttu-id="e6b19-685">DriversLic</span><span class="sxs-lookup"><span data-stu-id="e6b19-685">DriversLic</span></span>
- <span data-ttu-id="e6b19-686">DriversLics</span><span class="sxs-lookup"><span data-stu-id="e6b19-686">DriversLics</span></span>
- <span data-ttu-id="e6b19-687">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="e6b19-687">DriversLicence</span></span>
- <span data-ttu-id="e6b19-688">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="e6b19-688">DriversLicences</span></span>
- <span data-ttu-id="e6b19-689">驾驶员</span><span class="sxs-lookup"><span data-stu-id="e6b19-689">DriversLicense</span></span>
- <span data-ttu-id="e6b19-690">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="e6b19-690">DriversLicenses</span></span>
- <span data-ttu-id="e6b19-691">驱动因素 Lic</span><span class="sxs-lookup"><span data-stu-id="e6b19-691">Drivers Lic</span></span>
- <span data-ttu-id="e6b19-692">驱动因素 Lics</span><span class="sxs-lookup"><span data-stu-id="e6b19-692">Drivers Lics</span></span>
- <span data-ttu-id="e6b19-693">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="e6b19-693">Drivers License</span></span>
- <span data-ttu-id="e6b19-694">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="e6b19-694">Drivers Licenses</span></span>
- <span data-ttu-id="e6b19-695">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="e6b19-695">Drivers Licence</span></span>
- <span data-ttu-id="e6b19-696">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="e6b19-696">Drivers Licences</span></span>
- <span data-ttu-id="e6b19-697">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="e6b19-697">Driver'Lic</span></span>
- <span data-ttu-id="e6b19-698">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="e6b19-698">Driver'Lics</span></span>
- <span data-ttu-id="e6b19-699">Driver'License</span><span class="sxs-lookup"><span data-stu-id="e6b19-699">Driver'License</span></span>
- <span data-ttu-id="e6b19-700">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="e6b19-700">Driver'Licenses</span></span>
- <span data-ttu-id="e6b19-701">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="e6b19-701">Driver'Licence</span></span>
- <span data-ttu-id="e6b19-702">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="e6b19-702">Driver'Licences</span></span>
- <span data-ttu-id="e6b19-703">驱动因素 Lic</span><span class="sxs-lookup"><span data-stu-id="e6b19-703">Driver' Lic</span></span>
- <span data-ttu-id="e6b19-704">驱动因素 Lics</span><span class="sxs-lookup"><span data-stu-id="e6b19-704">Driver' Lics</span></span>
- <span data-ttu-id="e6b19-705">驱动因素许可证</span><span class="sxs-lookup"><span data-stu-id="e6b19-705">Driver' License</span></span>
- <span data-ttu-id="e6b19-706">驱动因素许可证</span><span class="sxs-lookup"><span data-stu-id="e6b19-706">Driver' Licenses</span></span>
- <span data-ttu-id="e6b19-707">驱动因素许可</span><span class="sxs-lookup"><span data-stu-id="e6b19-707">Driver' Licence</span></span>
- <span data-ttu-id="e6b19-708">驱动因素许可</span><span class="sxs-lookup"><span data-stu-id="e6b19-708">Driver' Licences</span></span>
- <span data-ttu-id="e6b19-709">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="e6b19-709">Driver'sLic</span></span>
- <span data-ttu-id="e6b19-710">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="e6b19-710">Driver'sLics</span></span>
- <span data-ttu-id="e6b19-711">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="e6b19-711">Driver'sLicense</span></span>
- <span data-ttu-id="e6b19-712">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="e6b19-712">Driver'sLicenses</span></span>
- <span data-ttu-id="e6b19-713">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="e6b19-713">Driver'sLicence</span></span>
- <span data-ttu-id="e6b19-714">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="e6b19-714">Driver'sLicences</span></span>
- <span data-ttu-id="e6b19-715">驱动因素的 Lic</span><span class="sxs-lookup"><span data-stu-id="e6b19-715">Driver's Lic</span></span>
- <span data-ttu-id="e6b19-716">驱动因素的 Lics</span><span class="sxs-lookup"><span data-stu-id="e6b19-716">Driver's Lics</span></span>
- <span data-ttu-id="e6b19-717">驱动程序的许可证</span><span class="sxs-lookup"><span data-stu-id="e6b19-717">Driver's License</span></span>
- <span data-ttu-id="e6b19-718">驱动程序的许可证</span><span class="sxs-lookup"><span data-stu-id="e6b19-718">Driver's Licenses</span></span>
- <span data-ttu-id="e6b19-719">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="e6b19-719">Driver's Licence</span></span>
- <span data-ttu-id="e6b19-720">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="e6b19-720">Driver's Licences</span></span>
- <span data-ttu-id="e6b19-721">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="e6b19-721">Permis de Conduire</span></span>
- <span data-ttu-id="e6b19-722">id</span><span class="sxs-lookup"><span data-stu-id="e6b19-722">id</span></span>
- <span data-ttu-id="e6b19-723">id</span><span class="sxs-lookup"><span data-stu-id="e6b19-723">ids</span></span>
- <span data-ttu-id="e6b19-724">
idcard number</span><span class="sxs-lookup"><span data-stu-id="e6b19-724">idcard number</span></span>
- <span data-ttu-id="e6b19-725">
idcard numbers</span><span class="sxs-lookup"><span data-stu-id="e6b19-725">idcard numbers</span></span>
- <span data-ttu-id="e6b19-726">
idcard #</span><span class="sxs-lookup"><span data-stu-id="e6b19-726">idcard #</span></span>
- <span data-ttu-id="e6b19-727">
idcard #s</span><span class="sxs-lookup"><span data-stu-id="e6b19-727">idcard #s</span></span>
- <span data-ttu-id="e6b19-728">idcard 卡片</span><span class="sxs-lookup"><span data-stu-id="e6b19-728">idcard card</span></span>
- <span data-ttu-id="e6b19-729">idcard 卡</span><span class="sxs-lookup"><span data-stu-id="e6b19-729">idcard cards</span></span>
- <span data-ttu-id="e6b19-730">idcard</span><span class="sxs-lookup"><span data-stu-id="e6b19-730">idcard</span></span>
- <span data-ttu-id="e6b19-731">identification number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-731">identification number</span></span>
- <span data-ttu-id="e6b19-732">identification numbers
</span><span class="sxs-lookup"><span data-stu-id="e6b19-732">identification numbers</span></span>
- <span data-ttu-id="e6b19-733">identification #
</span><span class="sxs-lookup"><span data-stu-id="e6b19-733">identification #</span></span>
- <span data-ttu-id="e6b19-734">
identification #s</span><span class="sxs-lookup"><span data-stu-id="e6b19-734">identification #s</span></span>
- <span data-ttu-id="e6b19-735">身份证</span><span class="sxs-lookup"><span data-stu-id="e6b19-735">identification card</span></span>
- <span data-ttu-id="e6b19-736">身份证</span><span class="sxs-lookup"><span data-stu-id="e6b19-736">identification cards</span></span>
- <span data-ttu-id="e6b19-737">
identification
</span><span class="sxs-lookup"><span data-stu-id="e6b19-737">identification</span></span> 
- <span data-ttu-id="e6b19-738">DL#</span><span class="sxs-lookup"><span data-stu-id="e6b19-738">DL#</span></span>
- <span data-ttu-id="e6b19-739">
DLS#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-739">DLS#</span></span> 
- <span data-ttu-id="e6b19-740">CDL#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-740">CDL#</span></span> 
- <span data-ttu-id="e6b19-741">CDLS#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-741">CDLS#</span></span> 
- <span data-ttu-id="e6b19-742">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="e6b19-742">DriverLic#</span></span> 
- <span data-ttu-id="e6b19-743">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="e6b19-743">DriverLics#</span></span> 
- <span data-ttu-id="e6b19-744">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="e6b19-744">DriverLicense#</span></span> 
- <span data-ttu-id="e6b19-745">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="e6b19-745">DriverLicenses#</span></span> 
- <span data-ttu-id="e6b19-746">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="e6b19-746">DriverLicence#</span></span> 
- <span data-ttu-id="e6b19-747">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="e6b19-747">DriverLicences#</span></span> 
- <span data-ttu-id="e6b19-748">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="e6b19-748">Driver Lic#</span></span>
- <span data-ttu-id="e6b19-749">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-749">Driver Lics#</span></span> 
- <span data-ttu-id="e6b19-750">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-750">Driver License#</span></span> 
- <span data-ttu-id="e6b19-751">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-751">Driver Licenses#</span></span> 
- <span data-ttu-id="e6b19-752">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-752">Driver License#</span></span> 
- <span data-ttu-id="e6b19-753">驱动程序许可 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-753">Driver Licences#</span></span> 
- <span data-ttu-id="e6b19-754">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="e6b19-754">DriversLic#</span></span> 
- <span data-ttu-id="e6b19-755">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="e6b19-755">DriversLics#</span></span> 
- <span data-ttu-id="e6b19-756">驾驶员 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-756">DriversLicense#</span></span> 
- <span data-ttu-id="e6b19-757">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="e6b19-757">DriversLicenses#</span></span> 
- <span data-ttu-id="e6b19-758">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="e6b19-758">DriversLicence#</span></span> 
- <span data-ttu-id="e6b19-759">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="e6b19-759">DriversLicences#</span></span> 
- <span data-ttu-id="e6b19-760">驱动因素 Lic #</span><span class="sxs-lookup"><span data-stu-id="e6b19-760">Drivers Lic#</span></span> 
- <span data-ttu-id="e6b19-761">驱动因素 Lics #</span><span class="sxs-lookup"><span data-stu-id="e6b19-761">Drivers Lics#</span></span> 
- <span data-ttu-id="e6b19-762">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-762">Drivers License#</span></span> 
- <span data-ttu-id="e6b19-763">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-763">Drivers Licenses#</span></span> 
- <span data-ttu-id="e6b19-764">驱动因素许可 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-764">Drivers Licence#</span></span> 
- <span data-ttu-id="e6b19-765">驱动因素许可 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-765">Drivers Licences#</span></span> 
- <span data-ttu-id="e6b19-766">Driver'Lic#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-766">Driver'Lic#</span></span> 
- <span data-ttu-id="e6b19-767">Driver'Lics#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-767">Driver'Lics#</span></span> 
- <span data-ttu-id="e6b19-768">Driver'License#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-768">Driver'License#</span></span> 
- <span data-ttu-id="e6b19-769">Driver'Licenses#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-769">Driver'Licenses#</span></span> 
- <span data-ttu-id="e6b19-770">Driver'Licence#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-770">Driver'Licence#</span></span> 
- <span data-ttu-id="e6b19-771">Driver'Licences#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-771">Driver'Licences#</span></span> 
- <span data-ttu-id="e6b19-772">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-772">Driver' Lic#</span></span> 
- <span data-ttu-id="e6b19-773">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-773">Driver' Lics#</span></span> 
- <span data-ttu-id="e6b19-774">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-774">Driver' License#</span></span> 
- <span data-ttu-id="e6b19-775">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-775">Driver' Licenses#</span></span> 
- <span data-ttu-id="e6b19-776">驱动因素许可 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-776">Driver' Licence#</span></span> 
- <span data-ttu-id="e6b19-777">驱动因素许可 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-777">Driver' Licences#</span></span> 
- <span data-ttu-id="e6b19-778">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="e6b19-778">Driver'sLic#</span></span> 
- <span data-ttu-id="e6b19-779">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="e6b19-779">Driver'sLics#</span></span> 
- <span data-ttu-id="e6b19-780">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="e6b19-780">Driver'sLicense#</span></span> 
- <span data-ttu-id="e6b19-781">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="e6b19-781">Driver'sLicenses#</span></span> 
- <span data-ttu-id="e6b19-782">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="e6b19-782">Driver'sLicence#</span></span> 
- <span data-ttu-id="e6b19-783">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="e6b19-783">Driver'sLicences#</span></span> 
- <span data-ttu-id="e6b19-784">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-784">Driver's Lic#</span></span> 
- <span data-ttu-id="e6b19-785">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-785">Driver's Lics#</span></span> 
- <span data-ttu-id="e6b19-786">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-786">Driver's License#</span></span> 
- <span data-ttu-id="e6b19-787">Driver's Licenses#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-787">Driver's Licenses#</span></span> 
- <span data-ttu-id="e6b19-788">驱动程序的许可 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-788">Driver's Licence#</span></span> 
- <span data-ttu-id="e6b19-789">驱动程序的许可 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-789">Driver's Licences#</span></span> 
- <span data-ttu-id="e6b19-790">Permis de Conduire #</span><span class="sxs-lookup"><span data-stu-id="e6b19-790">Permis de Conduire#</span></span> 
- <span data-ttu-id="e6b19-791">id #</span><span class="sxs-lookup"><span data-stu-id="e6b19-791">id#</span></span> 
- <span data-ttu-id="e6b19-792">id #</span><span class="sxs-lookup"><span data-stu-id="e6b19-792">ids#</span></span> 
- <span data-ttu-id="e6b19-793">idcard card#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-793">idcard card#</span></span> 
- <span data-ttu-id="e6b19-794">idcard cards#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-794">idcard cards#</span></span> 
- <span data-ttu-id="e6b19-795">idcard#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-795">idcard#</span></span> 
- <span data-ttu-id="e6b19-796">identification card#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-796">identification card#</span></span> 
- <span data-ttu-id="e6b19-797">identification cards#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-797">identification cards#</span></span> 
- <span data-ttu-id="e6b19-798">identification#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-798">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="e6b19-799">加拿大卫生服务号</span><span class="sxs-lookup"><span data-stu-id="e6b19-799">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-800">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-800">Format</span></span>

<span data-ttu-id="e6b19-801">10 个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-801">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-802">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-802">Pattern</span></span>

<span data-ttu-id="e6b19-803">10 个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-803">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-804">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-804">Checksum</span></span>

<span data-ttu-id="e6b19-805">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-805">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-806">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-806">Definition</span></span>

<span data-ttu-id="e6b19-807">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-807">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-808">正则表达式 Regex_canada_health_service_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-808">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-809">找到 Keyword_canada_health_service_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-809">A keyword from Keyword_canada_health_service_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-810">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-810">Keywords</span></span>

#### <a name="keywordcanadahealthservicenumber"></a><span data-ttu-id="e6b19-811">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="e6b19-811">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="e6b19-812">personal health number</span><span class="sxs-lookup"><span data-stu-id="e6b19-812">personal health number</span></span>
- <span data-ttu-id="e6b19-813">
patient information</span><span class="sxs-lookup"><span data-stu-id="e6b19-813">patient information</span></span>
- <span data-ttu-id="e6b19-814">运行状况服务</span><span class="sxs-lookup"><span data-stu-id="e6b19-814">health services</span></span>
- <span data-ttu-id="e6b19-815">
speciality services</span><span class="sxs-lookup"><span data-stu-id="e6b19-815">speciality services</span></span>
- <span data-ttu-id="e6b19-816">
automobile accident</span><span class="sxs-lookup"><span data-stu-id="e6b19-816">automobile accident</span></span>
- <span data-ttu-id="e6b19-817">
patient hospital</span><span class="sxs-lookup"><span data-stu-id="e6b19-817">patient hospital</span></span>
- <span data-ttu-id="e6b19-818">
psychiatrist</span><span class="sxs-lookup"><span data-stu-id="e6b19-818">psychiatrist</span></span>
- <span data-ttu-id="e6b19-819">
workers compensation</span><span class="sxs-lookup"><span data-stu-id="e6b19-819">workers compensation</span></span>
- <span data-ttu-id="e6b19-820">
disability</span><span class="sxs-lookup"><span data-stu-id="e6b19-820">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="e6b19-821">加拿大护照号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-821">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-822">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-822">Format</span></span>

<span data-ttu-id="e6b19-823">两个大写字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-823">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-824">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-824">Pattern</span></span>

<span data-ttu-id="e6b19-825">两个大写字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-825">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-826">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-826">Checksum</span></span>

<span data-ttu-id="e6b19-827">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-827">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-828">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-828">Definition</span></span>

<span data-ttu-id="e6b19-829">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-829">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-830">正则表达式 Regex_canada_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-830">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-831">找到从 Keyword_canada_passport_number 或 Keyword_passport 关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-831">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-832">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-832">Keywords</span></span>

#### <a name="keywordcanadapassportnumber"></a><span data-ttu-id="e6b19-833">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="e6b19-833">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="e6b19-834">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="e6b19-834">canadian citizenship</span></span>
- <span data-ttu-id="e6b19-835">
canadian passport</span><span class="sxs-lookup"><span data-stu-id="e6b19-835">canadian passport</span></span>
- <span data-ttu-id="e6b19-836">
passport application</span><span class="sxs-lookup"><span data-stu-id="e6b19-836">passport application</span></span>
- <span data-ttu-id="e6b19-837">
passport photos</span><span class="sxs-lookup"><span data-stu-id="e6b19-837">passport photos</span></span>
- <span data-ttu-id="e6b19-838">
certified translator</span><span class="sxs-lookup"><span data-stu-id="e6b19-838">certified translator</span></span>
- <span data-ttu-id="e6b19-839">
canadian citizens</span><span class="sxs-lookup"><span data-stu-id="e6b19-839">canadian citizens</span></span>
- <span data-ttu-id="e6b19-840">
processing times</span><span class="sxs-lookup"><span data-stu-id="e6b19-840">processing times</span></span>
- <span data-ttu-id="e6b19-841">

renewal application</span><span class="sxs-lookup"><span data-stu-id="e6b19-841">renewal application</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="e6b19-842">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="e6b19-842">Keyword_passport</span></span>

- <span data-ttu-id="e6b19-843">Passport Number</span><span class="sxs-lookup"><span data-stu-id="e6b19-843">Passport Number</span></span>
- <span data-ttu-id="e6b19-844">
Passport No</span><span class="sxs-lookup"><span data-stu-id="e6b19-844">Passport No</span></span>
- <span data-ttu-id="e6b19-845">Passport #
</span><span class="sxs-lookup"><span data-stu-id="e6b19-845">Passport #</span></span>
- <span data-ttu-id="e6b19-846">Passport#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-846">Passport#</span></span>
- <span data-ttu-id="e6b19-847">PassportID</span><span class="sxs-lookup"><span data-stu-id="e6b19-847">PassportID</span></span>
- <span data-ttu-id="e6b19-848">Passportno
</span><span class="sxs-lookup"><span data-stu-id="e6b19-848">Passportno</span></span>
- <span data-ttu-id="e6b19-849">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="e6b19-849">passportnumber</span></span>
- <span data-ttu-id="e6b19-850">パスポート</span><span class="sxs-lookup"><span data-stu-id="e6b19-850">パスポート</span></span>
- <span data-ttu-id="e6b19-851">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="e6b19-851">パスポート番号</span></span>
- <span data-ttu-id="e6b19-852">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="e6b19-852">パスポートのNum</span></span>
- <span data-ttu-id="e6b19-853">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="e6b19-853">パスポート＃</span></span>
- <span data-ttu-id="e6b19-854">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="e6b19-854">Numéro de passeport</span></span>
- <span data-ttu-id="e6b19-855">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="e6b19-855">Passeport n °</span></span>
- <span data-ttu-id="e6b19-856">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="e6b19-856">Passeport Non</span></span>
- <span data-ttu-id="e6b19-857">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="e6b19-857">Passeport #</span></span>
- <span data-ttu-id="e6b19-858">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-858">Passeport#</span></span>
- <span data-ttu-id="e6b19-859">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="e6b19-859">PasseportNon</span></span>
- <span data-ttu-id="e6b19-860">

Passeportn °</span><span class="sxs-lookup"><span data-stu-id="e6b19-860">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="e6b19-861">加拿大个人健康标识号 (PHIN)</span><span class="sxs-lookup"><span data-stu-id="e6b19-861">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-862">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-862">Format</span></span>

<span data-ttu-id="e6b19-863">九个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-863">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-864">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-864">Pattern</span></span>

<span data-ttu-id="e6b19-865">九个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-865">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-866">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-866">Checksum</span></span>

<span data-ttu-id="e6b19-867">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-867">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-868">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-868">Definition</span></span>

<span data-ttu-id="e6b19-p104">DLP 策略是相信它已检测到此类型的敏感信息的 75 %if、 内 300 个字符的邻近度： 正则表达式 Regex_canada_phin 找到与模式匹配的内容。找到来自 Keyword_canada_phin 或 Keyword_canada_provinces 至少两个关键字正在</span><span class="sxs-lookup"><span data-stu-id="e6b19-p104">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern. At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-871">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-871">Keywords</span></span>

#### <a name="keywordcanadaphin"></a><span data-ttu-id="e6b19-872">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="e6b19-872">Keyword_canada_phin</span></span>

- <span data-ttu-id="e6b19-873">social insurance number</span><span class="sxs-lookup"><span data-stu-id="e6b19-873">social insurance number</span></span>
- <span data-ttu-id="e6b19-874">
health information act</span><span class="sxs-lookup"><span data-stu-id="e6b19-874">health information act</span></span>
- <span data-ttu-id="e6b19-875">
income tax information</span><span class="sxs-lookup"><span data-stu-id="e6b19-875">income tax information</span></span>
- <span data-ttu-id="e6b19-876">
manitoba health</span><span class="sxs-lookup"><span data-stu-id="e6b19-876">manitoba health</span></span>
- <span data-ttu-id="e6b19-877">
health registration</span><span class="sxs-lookup"><span data-stu-id="e6b19-877">health registration</span></span>
- <span data-ttu-id="e6b19-878">
prescription purchases</span><span class="sxs-lookup"><span data-stu-id="e6b19-878">prescription purchases</span></span>
- <span data-ttu-id="e6b19-879">
benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="e6b19-879">benefit eligibility</span></span>
- <span data-ttu-id="e6b19-880">
personal health</span><span class="sxs-lookup"><span data-stu-id="e6b19-880">personal health</span></span>
- <span data-ttu-id="e6b19-881">
power of attorney</span><span class="sxs-lookup"><span data-stu-id="e6b19-881">power of attorney</span></span>
- <span data-ttu-id="e6b19-882">
registration number</span><span class="sxs-lookup"><span data-stu-id="e6b19-882">registration number</span></span>
- <span data-ttu-id="e6b19-883">personal health number</span><span class="sxs-lookup"><span data-stu-id="e6b19-883">personal health number</span></span>
- <span data-ttu-id="e6b19-884">
practitioner referral</span><span class="sxs-lookup"><span data-stu-id="e6b19-884">practitioner referral</span></span>
- <span data-ttu-id="e6b19-885">
wellness professional</span><span class="sxs-lookup"><span data-stu-id="e6b19-885">wellness professional</span></span>
- <span data-ttu-id="e6b19-886">
patient referral</span><span class="sxs-lookup"><span data-stu-id="e6b19-886">patient referral</span></span>
- <span data-ttu-id="e6b19-887">

health and wellness</span><span class="sxs-lookup"><span data-stu-id="e6b19-887">health and wellness</span></span>

#### <a name="keywordcanadaprovinces"></a><span data-ttu-id="e6b19-888">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="e6b19-888">Keyword_canada_provinces</span></span>

- <span data-ttu-id="e6b19-889">Nunavut</span><span class="sxs-lookup"><span data-stu-id="e6b19-889">Nunavut</span></span>
- <span data-ttu-id="e6b19-890">
Quebec</span><span class="sxs-lookup"><span data-stu-id="e6b19-890">Quebec</span></span>
- <span data-ttu-id="e6b19-891">
Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="e6b19-891">Northwest Territories</span></span>
- <span data-ttu-id="e6b19-892">
Ontario</span><span class="sxs-lookup"><span data-stu-id="e6b19-892">Ontario</span></span>
- <span data-ttu-id="e6b19-893">
British Columbia</span><span class="sxs-lookup"><span data-stu-id="e6b19-893">British Columbia</span></span>
- <span data-ttu-id="e6b19-894">
Alberta</span><span class="sxs-lookup"><span data-stu-id="e6b19-894">Alberta</span></span>
- <span data-ttu-id="e6b19-895">
Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="e6b19-895">Saskatchewan</span></span>
- <span data-ttu-id="e6b19-896">
Manitoba</span><span class="sxs-lookup"><span data-stu-id="e6b19-896">Manitoba</span></span>
- <span data-ttu-id="e6b19-897">
Yukon</span><span class="sxs-lookup"><span data-stu-id="e6b19-897">Yukon</span></span>
- <span data-ttu-id="e6b19-898">
Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="e6b19-898">Newfoundland and Labrador</span></span>
- <span data-ttu-id="e6b19-899">
New Brunswick</span><span class="sxs-lookup"><span data-stu-id="e6b19-899">New Brunswick</span></span>
- <span data-ttu-id="e6b19-900">
Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="e6b19-900">Nova Scotia</span></span>
- <span data-ttu-id="e6b19-901">
Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="e6b19-901">Prince Edward Island</span></span>
- <span data-ttu-id="e6b19-902">加拿大</span><span class="sxs-lookup"><span data-stu-id="e6b19-902">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="e6b19-903">加拿大社会保险号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-903">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-904">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-904">Format</span></span>

<span data-ttu-id="e6b19-905">九个数字，包含可选连字符或空格</span><span class="sxs-lookup"><span data-stu-id="e6b19-905">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-906">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-906">Pattern</span></span>

<span data-ttu-id="e6b19-907">有格式模式：</span><span class="sxs-lookup"><span data-stu-id="e6b19-907">Formatted:</span></span>
- <span data-ttu-id="e6b19-908">三位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-908">Three digits</span></span> 
- <span data-ttu-id="e6b19-909">连字符或空格</span><span class="sxs-lookup"><span data-stu-id="e6b19-909">A hyphen or space</span></span> 
- <span data-ttu-id="e6b19-910">三位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-910">Three digits</span></span> 
- <span data-ttu-id="e6b19-911">连字符或空格</span><span class="sxs-lookup"><span data-stu-id="e6b19-911">A hyphen or space</span></span> 
- <span data-ttu-id="e6b19-912">三位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-912">Three digits</span></span>

<span data-ttu-id="e6b19-913">未格式化： 九个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-913">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-914">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-914">Checksum</span></span>

<span data-ttu-id="e6b19-915">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-915">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-916">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-916">Definition</span></span>

<span data-ttu-id="e6b19-917">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-917">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-918">函数 Func_canadian_sin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-918">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-919">至少两个以下任意组合：</span><span class="sxs-lookup"><span data-stu-id="e6b19-919">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="e6b19-920">找到 Keyword_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-920">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="e6b19-921">找到 Keyword_sin_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-921">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="e6b19-922">函数 Func_eu_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="e6b19-922">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="e6b19-923">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-923">The checksum passes.</span></span>

<span data-ttu-id="e6b19-924">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-924">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-925">函数 Func_unformatted_canadian_sin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-925">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-926">找到 Keyword_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-926">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="e6b19-927">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-927">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-928">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-928">Keywords</span></span>

#### <a name="keywordsin"></a><span data-ttu-id="e6b19-929">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="e6b19-929">Keyword_sin</span></span>

- <span data-ttu-id="e6b19-930">sin</span><span class="sxs-lookup"><span data-stu-id="e6b19-930">sin</span></span> 
- <span data-ttu-id="e6b19-931">social insurance
</span><span class="sxs-lookup"><span data-stu-id="e6b19-931">social insurance</span></span> 
- <span data-ttu-id="e6b19-932">numero d'assurance sociale
</span><span class="sxs-lookup"><span data-stu-id="e6b19-932">numero d'assurance sociale</span></span> 
- <span data-ttu-id="e6b19-933">sins
</span><span class="sxs-lookup"><span data-stu-id="e6b19-933">sins</span></span> 
- <span data-ttu-id="e6b19-934">ssn</span><span class="sxs-lookup"><span data-stu-id="e6b19-934">ssn</span></span> 
- <span data-ttu-id="e6b19-935">ssn</span><span class="sxs-lookup"><span data-stu-id="e6b19-935">ssns</span></span> 
- <span data-ttu-id="e6b19-936">社会安全</span><span class="sxs-lookup"><span data-stu-id="e6b19-936">social security</span></span> 
- <span data-ttu-id="e6b19-937">numero d'assurance social
</span><span class="sxs-lookup"><span data-stu-id="e6b19-937">numero d'assurance social</span></span> 
- <span data-ttu-id="e6b19-938">国家/地区标识号</span><span class="sxs-lookup"><span data-stu-id="e6b19-938">national identification number</span></span> 
- <span data-ttu-id="e6b19-939">
national id</span><span class="sxs-lookup"><span data-stu-id="e6b19-939">national id</span></span> 
- <span data-ttu-id="e6b19-940">sin#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-940">sin#</span></span> 
- <span data-ttu-id="e6b19-941">soc ins
</span><span class="sxs-lookup"><span data-stu-id="e6b19-941">soc ins</span></span> 
- <span data-ttu-id="e6b19-942">social ins
</span><span class="sxs-lookup"><span data-stu-id="e6b19-942">social ins</span></span> 

#### <a name="keywordsincollaborative"></a><span data-ttu-id="e6b19-943">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="e6b19-943">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="e6b19-944">driver's license</span><span class="sxs-lookup"><span data-stu-id="e6b19-944">driver's license</span></span> 
- <span data-ttu-id="e6b19-945">drivers license</span><span class="sxs-lookup"><span data-stu-id="e6b19-945">drivers license</span></span> 
- <span data-ttu-id="e6b19-946">驱动程序的许可</span><span class="sxs-lookup"><span data-stu-id="e6b19-946">driver's licence</span></span> 
- <span data-ttu-id="e6b19-947">drivers licence</span><span class="sxs-lookup"><span data-stu-id="e6b19-947">drivers licence</span></span> 
- <span data-ttu-id="e6b19-948">DOB
</span><span class="sxs-lookup"><span data-stu-id="e6b19-948">DOB</span></span> 
- <span data-ttu-id="e6b19-949">出生日期</span><span class="sxs-lookup"><span data-stu-id="e6b19-949">Birthdate</span></span> 
- <span data-ttu-id="e6b19-950">生日 </span><span class="sxs-lookup"><span data-stu-id="e6b19-950">Birthday</span></span> 
- <span data-ttu-id="e6b19-951">Date of Birth
</span><span class="sxs-lookup"><span data-stu-id="e6b19-951">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="e6b19-952">	智利身份证号</span><span class="sxs-lookup"><span data-stu-id="e6b19-952">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-953">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-953">Format</span></span>

<span data-ttu-id="e6b19-954">7-8 数字以及定界符复选数字或字母</span><span class="sxs-lookup"><span data-stu-id="e6b19-954">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-955">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-955">Pattern</span></span>

<span data-ttu-id="e6b19-956">7-8 个数字加分隔符：</span><span class="sxs-lookup"><span data-stu-id="e6b19-956">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="e6b19-957">1-2 个数字 </span><span class="sxs-lookup"><span data-stu-id="e6b19-957">1-2 digits</span></span> 
- <span data-ttu-id="e6b19-958">一个点 </span><span class="sxs-lookup"><span data-stu-id="e6b19-958">A period</span></span> 
- <span data-ttu-id="e6b19-959">三个数字 </span><span class="sxs-lookup"><span data-stu-id="e6b19-959">Three digits</span></span> 
- <span data-ttu-id="e6b19-960">一个点 </span><span class="sxs-lookup"><span data-stu-id="e6b19-960">A period</span></span> 
- <span data-ttu-id="e6b19-961">三个数字 </span><span class="sxs-lookup"><span data-stu-id="e6b19-961">Three digits</span></span> 
- <span data-ttu-id="e6b19-962">一个短划线 </span><span class="sxs-lookup"><span data-stu-id="e6b19-962">A dash</span></span> 
- <span data-ttu-id="e6b19-963">一个数字或字母（不区分大小写），是校验位</span><span class="sxs-lookup"><span data-stu-id="e6b19-963">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-964">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-964">Checksum</span></span>

<span data-ttu-id="e6b19-965">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-965">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-966">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-966">Definition</span></span>

<span data-ttu-id="e6b19-967">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-967">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-968">函数 Func_chile_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-968">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-969">找到 Keyword_chile_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-969">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="e6b19-970">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-970">The checksum passes.</span></span>

<span data-ttu-id="e6b19-971">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-971">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-972">函数 Func_chile_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-972">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-973">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-973">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-974">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-974">Keywords</span></span>

#### <a name="keywordchileidcard"></a><span data-ttu-id="e6b19-975">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="e6b19-975">Keyword_chile_id_card</span></span>

- <span data-ttu-id="e6b19-976">National Identification Number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-976">National Identification Number</span></span> 
- <span data-ttu-id="e6b19-977">Identity card</span><span class="sxs-lookup"><span data-stu-id="e6b19-977">Identity card</span></span> 
- <span data-ttu-id="e6b19-978">ID</span><span class="sxs-lookup"><span data-stu-id="e6b19-978">ID</span></span> 
- <span data-ttu-id="e6b19-979">Identification</span><span class="sxs-lookup"><span data-stu-id="e6b19-979">Identification</span></span> 
- <span data-ttu-id="e6b19-980">Rol Único Nacional
</span><span class="sxs-lookup"><span data-stu-id="e6b19-980">Rol Único Nacional</span></span> 
- <span data-ttu-id="e6b19-981">运行</span><span class="sxs-lookup"><span data-stu-id="e6b19-981">RUN</span></span> 
- <span data-ttu-id="e6b19-982">Rol Único Tributario
</span><span class="sxs-lookup"><span data-stu-id="e6b19-982">Rol Único Tributario</span></span> 
- <span data-ttu-id="e6b19-983">RUT
</span><span class="sxs-lookup"><span data-stu-id="e6b19-983">RUT</span></span> 
- <span data-ttu-id="e6b19-984">Cédula de Identidad
</span><span class="sxs-lookup"><span data-stu-id="e6b19-984">Cédula de Identidad</span></span> 
- <span data-ttu-id="e6b19-985">Número De Identificación Nacional
</span><span class="sxs-lookup"><span data-stu-id="e6b19-985">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="e6b19-986">Tarjeta de identificación
</span><span class="sxs-lookup"><span data-stu-id="e6b19-986">Tarjeta de identificación</span></span> 
- <span data-ttu-id="e6b19-987">Identificación
</span><span class="sxs-lookup"><span data-stu-id="e6b19-987">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="e6b19-988">	中国居民身份证号</span><span class="sxs-lookup"><span data-stu-id="e6b19-988">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-989">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-989">Format</span></span>

<span data-ttu-id="e6b19-990">18 个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-990">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-991">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-991">Pattern</span></span>

<span data-ttu-id="e6b19-992">18 个数字：</span><span class="sxs-lookup"><span data-stu-id="e6b19-992">18 digits:</span></span>
- <span data-ttu-id="e6b19-993">其中六个数字是地址代码 </span><span class="sxs-lookup"><span data-stu-id="e6b19-993">Six digits which are an address code</span></span> 
- <span data-ttu-id="e6b19-994">八个数字，采用  YYYYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="e6b19-994">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="e6b19-995">三个数字，是顺序代码 </span><span class="sxs-lookup"><span data-stu-id="e6b19-995">Three digits which are an order code</span></span> 
- <span data-ttu-id="e6b19-996">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="e6b19-996">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-997">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-997">Checksum</span></span>

<span data-ttu-id="e6b19-998">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-998">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-999">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-999">Definition</span></span>

<span data-ttu-id="e6b19-1000">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1000">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-1001">函数 Func_china_resident_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1001">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-1002">找到 Keyword_china_resident_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1002">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="e6b19-1003">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1003">The checksum passes.</span></span>

<span data-ttu-id="e6b19-1004">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1004">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-1005">函数 Func_china_resident_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1005">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-1006">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1006">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-1007">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1007">Keywords</span></span>

### <a name="keywordchinaresidentid"></a><span data-ttu-id="e6b19-1008">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="e6b19-1008">Keyword_china_resident_id</span></span>

- <span data-ttu-id="e6b19-1009">Resident Identity Card
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1009">Resident Identity Card</span></span> 
- <span data-ttu-id="e6b19-1010">PRC
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1010">PRC</span></span> 
- <span data-ttu-id="e6b19-1011">National Identification Card
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1011">National Identification Card</span></span> 
- <span data-ttu-id="e6b19-1012">身份证 </span><span class="sxs-lookup"><span data-stu-id="e6b19-1012">身份证</span></span> 
- <span data-ttu-id="e6b19-1013">居民 身份证 </span><span class="sxs-lookup"><span data-stu-id="e6b19-1013">居民 身份证</span></span> 
- <span data-ttu-id="e6b19-1014">居民身份证
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1014">居民身份证</span></span> 
- <span data-ttu-id="e6b19-1015">鉴定

</span><span class="sxs-lookup"><span data-stu-id="e6b19-1015">鉴定</span></span> 
- <span data-ttu-id="e6b19-1016">身分證 </span><span class="sxs-lookup"><span data-stu-id="e6b19-1016">身分證</span></span> 
- <span data-ttu-id="e6b19-1017">居民身份證</span><span class="sxs-lookup"><span data-stu-id="e6b19-1017">居民 身份證</span></span>
- <span data-ttu-id="e6b19-1018">鑑定 </span><span class="sxs-lookup"><span data-stu-id="e6b19-1018">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="e6b19-1019">信用卡号</span><span class="sxs-lookup"><span data-stu-id="e6b19-1019">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-1020">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-1020">Format</span></span>

<span data-ttu-id="e6b19-1021">16 位数字格式化或无格式 (dddddddddddddddd)，必须将传递 Luhn 测试。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1021">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-1022">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-1022">Pattern</span></span>

<span data-ttu-id="e6b19-1023">非常复杂且强大的模式，检测到来自世界各地所有重要品牌的卡，包括 Visa、万事达卡、发现卡、JCB卡、美国运通卡、礼品卡以及大莱卡。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1023">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-1024">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-1024">Checksum</span></span>

<span data-ttu-id="e6b19-1025">是，Luhn 校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-1025">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-1026">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-1026">Definition</span></span>

<span data-ttu-id="e6b19-1027">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1027">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-1028">函数 Func_credit_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1028">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-1029">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1029">One of the following is true:</span></span>
    - <span data-ttu-id="e6b19-1030">找到 Keyword_cc_verification 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1030">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="e6b19-1031">找到 Keyword_cc_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1031">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="e6b19-1032">函数 Func_expiration_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1032">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="e6b19-1033">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1033">The checksum passes.</span></span>

<span data-ttu-id="e6b19-1034">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1034">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-1035">函数 Func_credit_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1035">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-1036">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1036">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-1037">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1037">Keywords</span></span>

#### <a name="keywordccverification"></a><span data-ttu-id="e6b19-1038">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="e6b19-1038">Keyword_cc_verification</span></span>

- <span data-ttu-id="e6b19-1039">card verification</span><span class="sxs-lookup"><span data-stu-id="e6b19-1039">card verification</span></span>
- <span data-ttu-id="e6b19-1040">card identification number</span><span class="sxs-lookup"><span data-stu-id="e6b19-1040">card identification number</span></span>
- <span data-ttu-id="e6b19-1041">cvn
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1041">cvn</span></span>
- <span data-ttu-id="e6b19-1042">cid
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1042">cid</span></span>
- <span data-ttu-id="e6b19-1043">cvc2</span><span class="sxs-lookup"><span data-stu-id="e6b19-1043">cvc2</span></span>
- <span data-ttu-id="e6b19-1044">cvv2</span><span class="sxs-lookup"><span data-stu-id="e6b19-1044">cvv2</span></span>
- <span data-ttu-id="e6b19-1045">pin block
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1045">pin block</span></span>
- <span data-ttu-id="e6b19-1046">security code
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1046">security code</span></span>
- <span data-ttu-id="e6b19-1047">security number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1047">security number</span></span>
- <span data-ttu-id="e6b19-1048">security no
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1048">security no</span></span>
- <span data-ttu-id="e6b19-1049">issue number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1049">issue number</span></span>
- <span data-ttu-id="e6b19-1050">issue no
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1050">issue no</span></span>
- <span data-ttu-id="e6b19-1051">cryptogramme
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1051">cryptogramme</span></span>
- <span data-ttu-id="e6b19-1052">numéro de sécurité
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1052">numéro de sécurité</span></span>
- <span data-ttu-id="e6b19-1053">numero de securite
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1053">numero de securite</span></span>
- <span data-ttu-id="e6b19-1054">kreditkartenprüfnummer
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1054">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="e6b19-1055">kreditkartenprufnummer
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1055">kreditkartenprufnummer</span></span>
- <span data-ttu-id="e6b19-1056">prüfziffer
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1056">prüfziffer</span></span>
- <span data-ttu-id="e6b19-1057">prufziffer
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1057">prufziffer</span></span>
- <span data-ttu-id="e6b19-1058">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="e6b19-1058">sicherheits Kode</span></span>
- <span data-ttu-id="e6b19-1059">sicherheitscode
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1059">sicherheitscode</span></span>
- <span data-ttu-id="e6b19-1060">sicherheitsnummer
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1060">sicherheitsnummer</span></span>
- <span data-ttu-id="e6b19-1061">verfalldatum
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1061">verfalldatum</span></span>
- <span data-ttu-id="e6b19-1062">codice di verifica
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1062">codice di verifica</span></span>
- <span data-ttu-id="e6b19-p105">cod. sicurezza
</span><span class="sxs-lookup"><span data-stu-id="e6b19-p105">cod. sicurezza</span></span>
- <span data-ttu-id="e6b19-1065">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="e6b19-1065">cod sicurezza</span></span>
- <span data-ttu-id="e6b19-1066">
n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="e6b19-1066">n autorizzazione</span></span>
- <span data-ttu-id="e6b19-1067">código
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1067">código</span></span>
- <span data-ttu-id="e6b19-1068">codigo
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1068">codigo</span></span>
- <span data-ttu-id="e6b19-p106">cod. seg
</span><span class="sxs-lookup"><span data-stu-id="e6b19-p106">cod. seg</span></span>
- <span data-ttu-id="e6b19-1071">cod seg</span><span class="sxs-lookup"><span data-stu-id="e6b19-1071">cod seg</span></span>
- <span data-ttu-id="e6b19-1072">código de segurança
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1072">código de segurança</span></span>
- <span data-ttu-id="e6b19-1073">codigo de seguranca
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1073">codigo de seguranca</span></span>
- <span data-ttu-id="e6b19-1074">codigo de segurança
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1074">codigo de segurança</span></span>
- <span data-ttu-id="e6b19-1075">código de seguranca
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1075">código de seguranca</span></span>
- <span data-ttu-id="e6b19-p107">cód. segurança
</span><span class="sxs-lookup"><span data-stu-id="e6b19-p107">cód. segurança</span></span>
- <span data-ttu-id="e6b19-p108">cod。seguranca cod。segurança</span><span class="sxs-lookup"><span data-stu-id="e6b19-p108">cod. seguranca cod. segurança</span></span>
- <span data-ttu-id="e6b19-p109">cód. seguranca
</span><span class="sxs-lookup"><span data-stu-id="e6b19-p109">cód. seguranca</span></span>
- <span data-ttu-id="e6b19-1083">cód segurança</span><span class="sxs-lookup"><span data-stu-id="e6b19-1083">cód segurança</span></span>
- <span data-ttu-id="e6b19-1084">货 seguranca cod segurança 到付款</span><span class="sxs-lookup"><span data-stu-id="e6b19-1084">cod seguranca cod segurança</span></span>
- <span data-ttu-id="e6b19-1085">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="e6b19-1085">cód seguranca</span></span>
- <span data-ttu-id="e6b19-1086">número de verificação
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1086">número de verificação</span></span>
- <span data-ttu-id="e6b19-1087">numero de verificacao
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1087">numero de verificacao</span></span>
- <span data-ttu-id="e6b19-1088">ablauf
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1088">ablauf</span></span>
- <span data-ttu-id="e6b19-1089">gültig bis
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1089">gültig bis</span></span>
- <span data-ttu-id="e6b19-1090">gültigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1090">gültigkeitsdatum</span></span>
- <span data-ttu-id="e6b19-1091">gultig bis
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1091">gultig bis</span></span>
- <span data-ttu-id="e6b19-1092">gultigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1092">gultigkeitsdatum</span></span>
- <span data-ttu-id="e6b19-1093">scadenza
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1093">scadenza</span></span>
- <span data-ttu-id="e6b19-1094">data scad
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1094">data scad</span></span>
- <span data-ttu-id="e6b19-1095">fecha de expiracion
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1095">fecha de expiracion</span></span>
- <span data-ttu-id="e6b19-1096">fecha de venc
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1096">fecha de venc</span></span>
- <span data-ttu-id="e6b19-1097">vencimiento
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1097">vencimiento</span></span>
- <span data-ttu-id="e6b19-1098">válido hasta
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1098">válido hasta</span></span>
- <span data-ttu-id="e6b19-1099">valido hasta
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1099">valido hasta</span></span>
- <span data-ttu-id="e6b19-1100">vto
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1100">vto</span></span>
- <span data-ttu-id="e6b19-1101">data de expiração
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1101">data de expiração</span></span>
- <span data-ttu-id="e6b19-1102">data de expiracao
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1102">data de expiracao</span></span>
- <span data-ttu-id="e6b19-1103">data em que expira
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1103">data em que expira</span></span>
- <span data-ttu-id="e6b19-1104">validade
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1104">validade</span></span>
- <span data-ttu-id="e6b19-1105">valor
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1105">valor</span></span>
- <span data-ttu-id="e6b19-1106">vencimento
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1106">vencimento</span></span>
- <span data-ttu-id="e6b19-1107">Venc</span><span class="sxs-lookup"><span data-stu-id="e6b19-1107">Venc</span></span> 

#### <a name="keywordccname"></a><span data-ttu-id="e6b19-1108">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="e6b19-1108">Keyword_cc_name</span></span>

- <span data-ttu-id="e6b19-1109">amex</span><span class="sxs-lookup"><span data-stu-id="e6b19-1109">amex</span></span>
- <span data-ttu-id="e6b19-1110">
american express</span><span class="sxs-lookup"><span data-stu-id="e6b19-1110">american express</span></span>
- <span data-ttu-id="e6b19-1111">americanexpress
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1111">americanexpress</span></span>
- <span data-ttu-id="e6b19-1112">Visa</span><span class="sxs-lookup"><span data-stu-id="e6b19-1112">Visa</span></span>
- <span data-ttu-id="e6b19-1113">mastercard
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1113">mastercard</span></span>
- <span data-ttu-id="e6b19-1114">Master Card
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1114">master card</span></span>
- <span data-ttu-id="e6b19-1115">
mc
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1115">mc</span></span> 
- <span data-ttu-id="e6b19-1116">mastercards</span><span class="sxs-lookup"><span data-stu-id="e6b19-1116">mastercards</span></span>
- <span data-ttu-id="e6b19-1117">
master cards</span><span class="sxs-lookup"><span data-stu-id="e6b19-1117">master cards</span></span>
- <span data-ttu-id="e6b19-1118">进餐的俱乐部</span><span class="sxs-lookup"><span data-stu-id="e6b19-1118">diner's Club</span></span>
- <span data-ttu-id="e6b19-1119">diners club
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1119">diners club</span></span>
- <span data-ttu-id="e6b19-1120">dinersclub
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1120">dinersclub</span></span>
- <span data-ttu-id="e6b19-1121">discover card
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1121">discover card</span></span>
- <span data-ttu-id="e6b19-1122">discovercard
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1122">discovercard</span></span>
- <span data-ttu-id="e6b19-1123">discover cards
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1123">discover cards</span></span>
- <span data-ttu-id="e6b19-1124">JCB</span><span class="sxs-lookup"><span data-stu-id="e6b19-1124">JCB</span></span>
- <span data-ttu-id="e6b19-1125">japanese card bureau
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1125">japanese card bureau</span></span>
- <span data-ttu-id="e6b19-1126">carte blanche
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1126">carte blanche</span></span>
- <span data-ttu-id="e6b19-1127">carteblanche
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1127">carteblanche</span></span>
- <span data-ttu-id="e6b19-1128">credit card
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1128">credit card</span></span>
- <span data-ttu-id="e6b19-1129">抄送 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-1129">cc#</span></span>
- <span data-ttu-id="e6b19-1130">抄送 # 中：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1130">cc#:</span></span>
- <span data-ttu-id="e6b19-1131">
expiration date</span><span class="sxs-lookup"><span data-stu-id="e6b19-1131">expiration date</span></span>
- <span data-ttu-id="e6b19-1132">exp date
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1132">exp date</span></span>
- <span data-ttu-id="e6b19-1133">
expiry date</span><span class="sxs-lookup"><span data-stu-id="e6b19-1133">expiry date</span></span>
- <span data-ttu-id="e6b19-1134">
date d’expiration</span><span class="sxs-lookup"><span data-stu-id="e6b19-1134">date d’expiration</span></span>
- <span data-ttu-id="e6b19-1135">
date d'exp</span><span class="sxs-lookup"><span data-stu-id="e6b19-1135">date d'exp</span></span>
- <span data-ttu-id="e6b19-1136">
date expiration</span><span class="sxs-lookup"><span data-stu-id="e6b19-1136">date expiration</span></span>
- <span data-ttu-id="e6b19-1137">bank card
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1137">bank card</span></span>
- <span data-ttu-id="e6b19-1138">
bankcard</span><span class="sxs-lookup"><span data-stu-id="e6b19-1138">bankcard</span></span>
- <span data-ttu-id="e6b19-1139">card number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1139">card number</span></span>
- <span data-ttu-id="e6b19-1140">card num
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1140">card num</span></span>
- <span data-ttu-id="e6b19-1141">cardnumber
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1141">cardnumber</span></span>
- <span data-ttu-id="e6b19-1142">cardnumbers
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1142">cardnumbers</span></span>
- <span data-ttu-id="e6b19-1143">card numbers
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1143">card numbers</span></span>
- <span data-ttu-id="e6b19-1144">creditcard
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1144">creditcard</span></span>
- <span data-ttu-id="e6b19-1145">credit cards
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1145">credit cards</span></span>
- <span data-ttu-id="e6b19-1146">creditcards
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1146">creditcards</span></span>
- <span data-ttu-id="e6b19-1147">ccn
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1147">ccn</span></span>
- <span data-ttu-id="e6b19-1148">card holder
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1148">card holder</span></span>
- <span data-ttu-id="e6b19-1149">cardholder
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1149">cardholder</span></span>
- <span data-ttu-id="e6b19-1150">card holders
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1150">card holders</span></span>
- <span data-ttu-id="e6b19-1151">cardholders
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1151">cardholders</span></span>
- <span data-ttu-id="e6b19-1152">check card
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1152">check card</span></span>
- <span data-ttu-id="e6b19-1153">checkcard
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1153">checkcard</span></span>
- <span data-ttu-id="e6b19-1154">check cards
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1154">check cards</span></span>
- <span data-ttu-id="e6b19-1155">checkcards
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1155">checkcards</span></span>
- <span data-ttu-id="e6b19-1156">debit card
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1156">debit card</span></span>
- <span data-ttu-id="e6b19-1157">debitcard
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1157">debitcard</span></span>
- <span data-ttu-id="e6b19-1158">debit cards
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1158">debit cards</span></span>
- <span data-ttu-id="e6b19-1159">debitcards
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1159">debitcards</span></span>
- <span data-ttu-id="e6b19-1160">atm card
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1160">atm card</span></span>
- <span data-ttu-id="e6b19-1161">atmcard
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1161">atmcard</span></span>
- <span data-ttu-id="e6b19-1162">atm cards
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1162">atm cards</span></span>
- <span data-ttu-id="e6b19-1163">atmcards
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1163">atmcards</span></span>
- <span data-ttu-id="e6b19-1164">
enroute</span><span class="sxs-lookup"><span data-stu-id="e6b19-1164">enroute</span></span>
- <span data-ttu-id="e6b19-1165">
en route</span><span class="sxs-lookup"><span data-stu-id="e6b19-1165">en route</span></span>
- <span data-ttu-id="e6b19-1166">card type
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1166">card type</span></span>
- <span data-ttu-id="e6b19-1167">carte bancaire
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1167">carte bancaire</span></span>
- <span data-ttu-id="e6b19-1168">carte de crédit
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1168">carte de crédit</span></span>
- <span data-ttu-id="e6b19-1169">carte de credit
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1169">carte de credit</span></span>
- <span data-ttu-id="e6b19-1170">numéro de carte
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1170">numéro de carte</span></span>
- <span data-ttu-id="e6b19-1171">numero de carte
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1171">numero de carte</span></span>
- <span data-ttu-id="e6b19-1172">nº de la carte
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1172">nº de la carte</span></span>
- <span data-ttu-id="e6b19-1173">nº de carte
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1173">nº de carte</span></span>
- <span data-ttu-id="e6b19-1174">kreditkarte
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1174">kreditkarte</span></span>
- <span data-ttu-id="e6b19-1175">karte
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1175">karte</span></span>
- <span data-ttu-id="e6b19-1176">karteninhaber
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1176">karteninhaber</span></span>
- <span data-ttu-id="e6b19-1177">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="e6b19-1177">karteninhabers</span></span>
- <span data-ttu-id="e6b19-1178">kreditkarteninhaber
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1178">kreditkarteninhaber</span></span>
- <span data-ttu-id="e6b19-1179">kreditkarteninstitut
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1179">kreditkarteninstitut</span></span>
- <span data-ttu-id="e6b19-1180">kreditkartentyp
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1180">kreditkartentyp</span></span>
- <span data-ttu-id="e6b19-1181">eigentümername
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1181">eigentümername</span></span>
- <span data-ttu-id="e6b19-1182">
kartennr
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1182">kartennr</span></span> 
- <span data-ttu-id="e6b19-1183">kartennummer</span><span class="sxs-lookup"><span data-stu-id="e6b19-1183">kartennummer</span></span>
- <span data-ttu-id="e6b19-1184">
kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="e6b19-1184">kreditkartennummer</span></span>
- <span data-ttu-id="e6b19-1185">kreditkarten nummer</span><span class="sxs-lookup"><span data-stu-id="e6b19-1185">kreditkarten-nummer</span></span>
- <span data-ttu-id="e6b19-1186">carta di credito
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1186">carta di credito</span></span>
- <span data-ttu-id="e6b19-1187">carta credito
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1187">carta credito</span></span>
- <span data-ttu-id="e6b19-1188">carta</span><span class="sxs-lookup"><span data-stu-id="e6b19-1188">carta</span></span>
- <span data-ttu-id="e6b19-1189">n carta</span><span class="sxs-lookup"><span data-stu-id="e6b19-1189">n carta</span></span>
- <span data-ttu-id="e6b19-p110">nr. carta
</span><span class="sxs-lookup"><span data-stu-id="e6b19-p110">nr. carta</span></span>
- <span data-ttu-id="e6b19-1192">nr carta</span><span class="sxs-lookup"><span data-stu-id="e6b19-1192">nr carta</span></span>
- <span data-ttu-id="e6b19-1193">numero carta
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1193">numero carta</span></span>
- <span data-ttu-id="e6b19-1194">numero della carta
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1194">numero della carta</span></span>
- <span data-ttu-id="e6b19-1195">numero di carta
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1195">numero di carta</span></span>
- <span data-ttu-id="e6b19-1196">tarjeta credito
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1196">tarjeta credito</span></span>
- <span data-ttu-id="e6b19-1197">tarjeta de credito
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1197">tarjeta de credito</span></span>
- <span data-ttu-id="e6b19-1198">
tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="e6b19-1198">tarjeta crédito</span></span>
- <span data-ttu-id="e6b19-1199">
tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="e6b19-1199">tarjeta de crédito</span></span>
- <span data-ttu-id="e6b19-1200">tarjeta de atm
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1200">tarjeta de atm</span></span>
- <span data-ttu-id="e6b19-1201">tarjeta atm
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1201">tarjeta atm</span></span>
- <span data-ttu-id="e6b19-1202">tarjeta debito
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1202">tarjeta debito</span></span>
- <span data-ttu-id="e6b19-1203">tarjeta de debito
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1203">tarjeta de debito</span></span>
- <span data-ttu-id="e6b19-1204">
tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="e6b19-1204">tarjeta débito</span></span>
- <span data-ttu-id="e6b19-1205">
tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="e6b19-1205">tarjeta de débito</span></span>
- <span data-ttu-id="e6b19-1206">nº de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1206">nº de tarjeta</span></span>
- <span data-ttu-id="e6b19-p111">no. de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="e6b19-p111">no. de tarjeta</span></span>
- <span data-ttu-id="e6b19-1209">没有 de tarjeta</span><span class="sxs-lookup"><span data-stu-id="e6b19-1209">no de tarjeta</span></span>
- <span data-ttu-id="e6b19-1210">numero de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1210">numero de tarjeta</span></span>
- <span data-ttu-id="e6b19-1211">número de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1211">número de tarjeta</span></span>
- <span data-ttu-id="e6b19-1212">tarjeta no
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1212">tarjeta no</span></span>
- <span data-ttu-id="e6b19-1213">tarjetahabiente
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1213">tarjetahabiente</span></span>
- <span data-ttu-id="e6b19-1214">cartão de crédito
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1214">cartão de crédito</span></span>
- <span data-ttu-id="e6b19-1215">cartão de credito
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1215">cartão de credito</span></span>
- <span data-ttu-id="e6b19-1216">cartao de crédito
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1216">cartao de crédito</span></span>
- <span data-ttu-id="e6b19-1217">cartao de credito
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1217">cartao de credito</span></span>
- <span data-ttu-id="e6b19-1218">cartão de débito
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1218">cartão de débito</span></span>
- <span data-ttu-id="e6b19-1219">cartao de débito
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1219">cartao de débito</span></span>
- <span data-ttu-id="e6b19-1220">cartão de debito
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1220">cartão de debito</span></span>
- <span data-ttu-id="e6b19-1221">cartao de debito
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1221">cartao de debito</span></span>
- <span data-ttu-id="e6b19-1222">débito automático</span><span class="sxs-lookup"><span data-stu-id="e6b19-1222">débito automático</span></span>
- <span data-ttu-id="e6b19-1223">debito automatico
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1223">debito automatico</span></span>
- <span data-ttu-id="e6b19-1224">
número do cartão</span><span class="sxs-lookup"><span data-stu-id="e6b19-1224">número do cartão</span></span>
- <span data-ttu-id="e6b19-1225">
numero do cartão
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1225">numero do cartão</span></span> 
- <span data-ttu-id="e6b19-1226">número do cartao</span><span class="sxs-lookup"><span data-stu-id="e6b19-1226">número do cartao</span></span>
- <span data-ttu-id="e6b19-1227">
numero do cartao</span><span class="sxs-lookup"><span data-stu-id="e6b19-1227">numero do cartao</span></span>
- <span data-ttu-id="e6b19-1228">número de cartão
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1228">número de cartão</span></span>
- <span data-ttu-id="e6b19-1229">numero de cartão
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1229">numero de cartão</span></span>
- <span data-ttu-id="e6b19-1230">número de cartao
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1230">número de cartao</span></span>
- <span data-ttu-id="e6b19-1231">numero de cartao
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1231">numero de cartao</span></span>
- <span data-ttu-id="e6b19-1232">nº 执行 cartão</span><span class="sxs-lookup"><span data-stu-id="e6b19-1232">nº do cartão</span></span>
- <span data-ttu-id="e6b19-1233">nº do cartao
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1233">nº do cartao</span></span>
- <span data-ttu-id="e6b19-p112">nº. do cartão
</span><span class="sxs-lookup"><span data-stu-id="e6b19-p112">nº. do cartão</span></span>
- <span data-ttu-id="e6b19-1236">没有执行 cartão</span><span class="sxs-lookup"><span data-stu-id="e6b19-1236">no do cartão</span></span>
- <span data-ttu-id="e6b19-1237">没有执行 cartao</span><span class="sxs-lookup"><span data-stu-id="e6b19-1237">no do cartao</span></span>
- <span data-ttu-id="e6b19-p113">no. do cartão
</span><span class="sxs-lookup"><span data-stu-id="e6b19-p113">no. do cartão</span></span>
- <span data-ttu-id="e6b19-p114">
no. do cartao
</span><span class="sxs-lookup"><span data-stu-id="e6b19-p114">no. do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="e6b19-1242">	克罗地亚身份证号</span><span class="sxs-lookup"><span data-stu-id="e6b19-1242">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-1243">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-1243">Format</span></span>

<span data-ttu-id="e6b19-1244">九个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1244">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-1245">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-1245">Pattern</span></span>

<span data-ttu-id="e6b19-1246">九个连续的数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1246">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-1247">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-1247">Checksum</span></span>

<span data-ttu-id="e6b19-1248">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-1248">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-1249">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-1249">Definition</span></span>

<span data-ttu-id="e6b19-1250">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-1251">函数 Func_croatia_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1251">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-1252">找到 Keyword_croatia_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1252">A keyword from Keyword_croatia_id_card is found.</span></span>

```
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6b19-1253">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1253">Keywords</span></span>

#### <a name="keywordcroatiaidcard"></a><span data-ttu-id="e6b19-1254">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="e6b19-1254">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="e6b19-1255">Croatian identity card</span><span class="sxs-lookup"><span data-stu-id="e6b19-1255">Croatian identity card</span></span>
- <span data-ttu-id="e6b19-1256">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="e6b19-1256">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="e6b19-1257">	Croatia Personal Identification (OIB) Number</span><span class="sxs-lookup"><span data-stu-id="e6b19-1257">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-1258">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-1258">Format</span></span>

<span data-ttu-id="e6b19-1259">11 个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1259">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-1260">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-1260">Pattern</span></span>

<span data-ttu-id="e6b19-1261">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1261">11 digits:</span></span>
- <span data-ttu-id="e6b19-1262">10 个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1262">10 digits</span></span> 
- <span data-ttu-id="e6b19-1263">最后一数字的国际数据交换为复选位数，11 个数字的前面添加字母 HR。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1263">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-1264">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-1264">Checksum</span></span>

<span data-ttu-id="e6b19-1265">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-1265">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-1266">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-1266">Definition</span></span>

<span data-ttu-id="e6b19-1267">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1267">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-1268">函数 Func_croatia_oib_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1268">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-1269">找到 Keyword_croatia_oib_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1269">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="e6b19-1270">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1270">The checksum passes.</span></span>

<span data-ttu-id="e6b19-1271">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1271">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-1272">函数 Func_croatia_oib_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1272">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-1273">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1273">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-1274">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1274">Keywords</span></span>

#### <a name="keywordcroatiaoibnumber"></a><span data-ttu-id="e6b19-1275">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="e6b19-1275">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="e6b19-1276">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="e6b19-1276">Personal Identification Number</span></span>
- <span data-ttu-id="e6b19-1277">Osobni identifikacijski broj
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1277">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="e6b19-1278">OIB
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1278">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="e6b19-1279">捷克个人标识号</span><span class="sxs-lookup"><span data-stu-id="e6b19-1279">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-1280">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-1280">Format</span></span>

<span data-ttu-id="e6b19-1281">使用可选的九个数字正斜杠 （旧格式） 使用可选的 10 位数字正斜杠 （新格式）</span><span class="sxs-lookup"><span data-stu-id="e6b19-1281">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-1282">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-1282">Pattern</span></span>

<span data-ttu-id="e6b19-1283">九个数字 （旧格式）：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1283">Nine digits (old format):</span></span>
- <span data-ttu-id="e6b19-1284">九个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1284">Nine digits</span></span>

<span data-ttu-id="e6b19-1285">或者</span><span class="sxs-lookup"><span data-stu-id="e6b19-1285">OR</span></span>

- <span data-ttu-id="e6b19-1286">包含 6 位数字表示出生日期</span><span class="sxs-lookup"><span data-stu-id="e6b19-1286">Six digits that represent date of birth</span></span>
- <span data-ttu-id="e6b19-1287">一个正斜杠 </span><span class="sxs-lookup"><span data-stu-id="e6b19-1287">A forward slash</span></span>
- <span data-ttu-id="e6b19-1288">三位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1288">Three digits</span></span>

<span data-ttu-id="e6b19-1289">10 位数字 （新格式）：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1289">10 digits (new format):</span></span>
- <span data-ttu-id="e6b19-1290">10 个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1290">10 digits</span></span>

<span data-ttu-id="e6b19-1291">或者</span><span class="sxs-lookup"><span data-stu-id="e6b19-1291">OR</span></span>

- <span data-ttu-id="e6b19-1292">包含 6 位数字表示出生日期</span><span class="sxs-lookup"><span data-stu-id="e6b19-1292">Six digits that represent date of birth</span></span>
- <span data-ttu-id="e6b19-1293">一个正斜杠 </span><span class="sxs-lookup"><span data-stu-id="e6b19-1293">A forward slash</span></span> 
- <span data-ttu-id="e6b19-1294">其中最后一位是复选数字值的四位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1294">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-1295">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-1295">Checksum</span></span>

<span data-ttu-id="e6b19-1296">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-1296">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-1297">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-1297">Definition</span></span>

<span data-ttu-id="e6b19-p115">DLP 策略是 85%相信它已检测到此类型的敏感信息 if、 内 300 个字符的邻近度： 函数 Func_czech_id_card 查找与模式匹配的内容。找到从 Keyword_czech_id_card 关键字。将传递校验和。</span><span class="sxs-lookup"><span data-stu-id="e6b19-p115">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern. A keyword from Keyword_czech_id_card is found. The checksum passes.</span></span>

```
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="e6b19-1301">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1301">Keywords</span></span>

- <span data-ttu-id="e6b19-1302">捷克个人标识号</span><span class="sxs-lookup"><span data-stu-id="e6b19-1302">czech personal identity number</span></span>
- <span data-ttu-id="e6b19-1303">Rodné číslo</span><span class="sxs-lookup"><span data-stu-id="e6b19-1303">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="e6b19-1304">	丹麦个人身份号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-1304">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-1305">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-1305">Format</span></span>

<span data-ttu-id="e6b19-1306">10 个数字，包含连字符</span><span class="sxs-lookup"><span data-stu-id="e6b19-1306">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-1307">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-1307">Pattern</span></span>

<span data-ttu-id="e6b19-1308">10 个数字：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1308">10 digits:</span></span>
- <span data-ttu-id="e6b19-1309">六个数字，采用  DDMMYY 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="e6b19-1309">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="e6b19-1310">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="e6b19-1310">A hyphen</span></span> 
- <span data-ttu-id="e6b19-1311">四个数字，最后一位数字是校验位</span><span class="sxs-lookup"><span data-stu-id="e6b19-1311">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-1312">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-1312">Checksum</span></span>

<span data-ttu-id="e6b19-1313">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-1313">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-1314">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-1314">Definition</span></span>

<span data-ttu-id="e6b19-p116">DLP 策略是相信它已检测到此类型的敏感信息的 75 %if、 内 300 个字符的邻近度： 正则表达式 Regex_denmark_id 找到与模式匹配的内容。找到从 Keyword_denmark_id 关键字。将传递校验和。</span><span class="sxs-lookup"><span data-stu-id="e6b19-p116">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern. A keyword from Keyword_denmark_id is found. The checksum passes.</span></span>

```
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6b19-1318">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1318">Keywords</span></span>

#### <a name="keyworddenmarkid"></a><span data-ttu-id="e6b19-1319">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="e6b19-1319">Keyword_denmark_id</span></span>

- <span data-ttu-id="e6b19-1320">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="e6b19-1320">Personal Identification Number</span></span>
- <span data-ttu-id="e6b19-1321">CPR</span><span class="sxs-lookup"><span data-stu-id="e6b19-1321">CPR</span></span>
- <span data-ttu-id="e6b19-1322">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="e6b19-1322">Det Centrale Personregister</span></span>
- <span data-ttu-id="e6b19-1323">Personnummer</span><span class="sxs-lookup"><span data-stu-id="e6b19-1323">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="e6b19-1324">药品管制局 (DEA) 号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-1324">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-1325">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-1325">Format</span></span>

<span data-ttu-id="e6b19-1326">两个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1326">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-1327">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-1327">Pattern</span></span>

<span data-ttu-id="e6b19-1328">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1328">Pattern must include all of the following:</span></span>
- <span data-ttu-id="e6b19-1329">这一组可能的字母（不区分大小写）中的一个字母：abcdefghjklmnprstux，这是注册人代码</span><span class="sxs-lookup"><span data-stu-id="e6b19-1329">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="e6b19-1330">一个字母（不区分大小写），这是注册人姓氏的第一个字母</span><span class="sxs-lookup"><span data-stu-id="e6b19-1330">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="e6b19-1331">七位数字，最后一个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="e6b19-1331">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-1332">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-1332">Checksum</span></span>

<span data-ttu-id="e6b19-1333">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-1333">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-1334">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-1334">Definition</span></span>

<span data-ttu-id="e6b19-1335">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1335">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-1336">函数 Func_dea_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1336">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-1337">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1337">The checksum passes.</span></span>

```
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6b19-1338">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1338">Keywords</span></span>

<span data-ttu-id="e6b19-1339">无</span><span class="sxs-lookup"><span data-stu-id="e6b19-1339">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="e6b19-1340">欧盟借记卡号</span><span class="sxs-lookup"><span data-stu-id="e6b19-1340">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-1341">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-1341">Format</span></span>

<span data-ttu-id="e6b19-1342">16 个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1342">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-1343">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-1343">Pattern</span></span>

<span data-ttu-id="e6b19-1344">非常复杂且强大的模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-1344">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-1345">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-1345">Checksum</span></span>

<span data-ttu-id="e6b19-1346">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-1346">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-1347">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-1347">Definition</span></span>

<span data-ttu-id="e6b19-1348">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1348">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-1349">函数 Func_eu_debit_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1349">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-1350">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1350">At least one of the following is true:</span></span>
    - <span data-ttu-id="e6b19-1351">找到 Keyword_eu_debit_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1351">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="e6b19-1352">找到 Keyword_card_terms_dict 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1352">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="e6b19-1353">找到 Keyword_card_security_terms_dict 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1353">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="e6b19-1354">找到 Keyword_card_expiration_terms_dict 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1354">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="e6b19-1355">函数 Func_expiration_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1355">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="e6b19-1356">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1356">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-1357">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1357">Keywords</span></span>

#### <a name="keywordeudebitcard"></a><span data-ttu-id="e6b19-1358">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="e6b19-1358">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="e6b19-1359">帐号</span><span class="sxs-lookup"><span data-stu-id="e6b19-1359">account number</span></span> 
- <span data-ttu-id="e6b19-1360">card number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1360">card number</span></span> 
- <span data-ttu-id="e6b19-1361">card no.
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1361">card no.</span></span> 
- <span data-ttu-id="e6b19-1362">security number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1362">security number</span></span> 
- <span data-ttu-id="e6b19-1363">抄送 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-1363">cc#</span></span> 

#### <a name="keywordcardtermsdict"></a><span data-ttu-id="e6b19-1364">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="e6b19-1364">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="e6b19-1365">acct nbr
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1365">acct nbr</span></span> 
- <span data-ttu-id="e6b19-1366">acct num
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1366">acct num</span></span> 
- <span data-ttu-id="e6b19-1367">acct no
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1367">acct no</span></span> 
- <span data-ttu-id="e6b19-1368">american express
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1368">american express</span></span> 
- <span data-ttu-id="e6b19-1369">americanexpress
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1369">americanexpress</span></span> 
- <span data-ttu-id="e6b19-1370">americano espresso
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1370">americano espresso</span></span> 
- <span data-ttu-id="e6b19-1371">amex</span><span class="sxs-lookup"><span data-stu-id="e6b19-1371">amex</span></span> 
- <span data-ttu-id="e6b19-1372">atm card
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1372">atm card</span></span> 
- <span data-ttu-id="e6b19-1373">atm cards
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1373">atm cards</span></span> 
- <span data-ttu-id="e6b19-1374">atm kaart
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1374">atm kaart</span></span> 
- <span data-ttu-id="e6b19-1375">atmcard
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1375">atmcard</span></span> 
- <span data-ttu-id="e6b19-1376">atmcards
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1376">atmcards</span></span> 
- <span data-ttu-id="e6b19-1377">atmkaart
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1377">atmkaart</span></span> 
- <span data-ttu-id="e6b19-1378">atmkaarten
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1378">atmkaarten</span></span> 
- <span data-ttu-id="e6b19-1379">bancontact
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1379">bancontact</span></span> 
- <span data-ttu-id="e6b19-1380">bank card
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1380">bank card</span></span> 
- <span data-ttu-id="e6b19-1381">bankkaart
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1381">bankkaart</span></span> 
- <span data-ttu-id="e6b19-1382">card holder
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1382">card holder</span></span> 
- <span data-ttu-id="e6b19-1383">card holders
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1383">card holders</span></span> 
- <span data-ttu-id="e6b19-1384">card num
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1384">card num</span></span> 
- <span data-ttu-id="e6b19-1385">card number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1385">card number</span></span> 
- <span data-ttu-id="e6b19-1386">card numbers
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1386">card numbers</span></span> 
- <span data-ttu-id="e6b19-1387">card type
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1387">card type</span></span> 
- <span data-ttu-id="e6b19-1388">cardano numerico
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1388">cardano numerico</span></span> 
- <span data-ttu-id="e6b19-1389">cardholder
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1389">cardholder</span></span> 
- <span data-ttu-id="e6b19-1390">cardholders
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1390">cardholders</span></span> 
- <span data-ttu-id="e6b19-1391">cardnumber
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1391">cardnumber</span></span> 
- <span data-ttu-id="e6b19-1392">cardnumbers
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1392">cardnumbers</span></span> 
- <span data-ttu-id="e6b19-1393">carta bianca
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1393">carta bianca</span></span> 
- <span data-ttu-id="e6b19-1394">carta credito
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1394">carta credito</span></span> 
- <span data-ttu-id="e6b19-1395">carta di credito
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1395">carta di credito</span></span> 
- <span data-ttu-id="e6b19-1396">cartao de credito
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1396">cartao de credito</span></span> 
- <span data-ttu-id="e6b19-1397">cartao de crédito
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1397">cartao de crédito</span></span> 
- <span data-ttu-id="e6b19-1398">cartao de debito
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1398">cartao de debito</span></span> 
- <span data-ttu-id="e6b19-1399">cartao de débito
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1399">cartao de débito</span></span> 
- <span data-ttu-id="e6b19-1400">carte bancaire
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1400">carte bancaire</span></span> 
- <span data-ttu-id="e6b19-1401">carte blanche
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1401">carte blanche</span></span> 
- <span data-ttu-id="e6b19-1402">carte bleue
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1402">carte bleue</span></span> 
- <span data-ttu-id="e6b19-1403">carte de credit
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1403">carte de credit</span></span> 
- <span data-ttu-id="e6b19-1404">carte de crédit
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1404">carte de crédit</span></span> 
- <span data-ttu-id="e6b19-1405">carte di credito
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1405">carte di credito</span></span> 
- <span data-ttu-id="e6b19-1406">carteblanche
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1406">carteblanche</span></span> 
- <span data-ttu-id="e6b19-1407">cartão de credito
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1407">cartão de credito</span></span> 
- <span data-ttu-id="e6b19-1408">cartão de crédito
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1408">cartão de crédito</span></span> 
- <span data-ttu-id="e6b19-1409">cartão de debito
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1409">cartão de debito</span></span> 
- <span data-ttu-id="e6b19-1410">cartão de débito
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1410">cartão de débito</span></span> 
- <span data-ttu-id="e6b19-1411">cb
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1411">cb</span></span> 
- <span data-ttu-id="e6b19-1412">ccn
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1412">ccn</span></span> 
- <span data-ttu-id="e6b19-1413">check card
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1413">check card</span></span> 
- <span data-ttu-id="e6b19-1414">check cards
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1414">check cards</span></span> 
- <span data-ttu-id="e6b19-1415">checkcard
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1415">checkcard</span></span>
- <span data-ttu-id="e6b19-1416">checkcards
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1416">checkcards</span></span> 
- <span data-ttu-id="e6b19-1417">chequekaart
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1417">chequekaart</span></span> 
- <span data-ttu-id="e6b19-1418">cirrus
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1418">cirrus</span></span> 
- <span data-ttu-id="e6b19-1419">cirrus-edc-maestro
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1419">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="e6b19-1420">controlekaart
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1420">controlekaart</span></span> 
- <span data-ttu-id="e6b19-1421">controlekaarten
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1421">controlekaarten</span></span> 
- <span data-ttu-id="e6b19-1422">credit card
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1422">credit card</span></span> 
- <span data-ttu-id="e6b19-1423">credit cards
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1423">credit cards</span></span> 
- <span data-ttu-id="e6b19-1424">creditcard
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1424">creditcard</span></span> 
- <span data-ttu-id="e6b19-1425">creditcards
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1425">creditcards</span></span> 
- <span data-ttu-id="e6b19-1426">debetkaart
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1426">debetkaart</span></span> 
- <span data-ttu-id="e6b19-1427">debetkaarten
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1427">debetkaarten</span></span> 
- <span data-ttu-id="e6b19-1428">debit card
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1428">debit card</span></span> 
- <span data-ttu-id="e6b19-1429">debit cards
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1429">debit cards</span></span> 
- <span data-ttu-id="e6b19-1430">debitcard
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1430">debitcard</span></span> 
- <span data-ttu-id="e6b19-1431">debitcards
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1431">debitcards</span></span> 
- <span data-ttu-id="e6b19-1432">debito automatico
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1432">debito automatico</span></span> 
- <span data-ttu-id="e6b19-1433">diners club
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1433">diners club</span></span> 
- <span data-ttu-id="e6b19-1434">dinersclub
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1434">dinersclub</span></span> 
- <span data-ttu-id="e6b19-1435">发现</span><span class="sxs-lookup"><span data-stu-id="e6b19-1435">discover</span></span> 
- <span data-ttu-id="e6b19-1436">discover card
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1436">discover card</span></span> 
- <span data-ttu-id="e6b19-1437">discover cards
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1437">discover cards</span></span> 
- <span data-ttu-id="e6b19-1438">discovercard
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1438">discovercard</span></span> 
- <span data-ttu-id="e6b19-1439">discovercards
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1439">discovercards</span></span> 
- <span data-ttu-id="e6b19-1440">débito automático</span><span class="sxs-lookup"><span data-stu-id="e6b19-1440">débito automático</span></span>
- <span data-ttu-id="e6b19-1441">
edc
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1441">edc</span></span> 
- <span data-ttu-id="e6b19-1442">eigentümername
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1442">eigentümername</span></span> 
- <span data-ttu-id="e6b19-1443">european debit card
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1443">european debit card</span></span> 
- <span data-ttu-id="e6b19-1444">hoofdkaart
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1444">hoofdkaart</span></span> 
- <span data-ttu-id="e6b19-1445">hoofdkaarten
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1445">hoofdkaarten</span></span> 
- <span data-ttu-id="e6b19-1446">in viaggio
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1446">in viaggio</span></span> 
- <span data-ttu-id="e6b19-1447">japanese card bureau
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1447">japanese card bureau</span></span> 
- <span data-ttu-id="e6b19-1448">japanse kaartdienst
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1448">japanse kaartdienst</span></span> 
- <span data-ttu-id="e6b19-1449">jcb
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1449">jcb</span></span> 
- <span data-ttu-id="e6b19-1450">kaart
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1450">kaart</span></span> 
- <span data-ttu-id="e6b19-1451">kaart num
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1451">kaart num</span></span> 
- <span data-ttu-id="e6b19-1452">kaartaantal
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1452">kaartaantal</span></span> 
- <span data-ttu-id="e6b19-1453">kaartaantallen
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1453">kaartaantallen</span></span> 
- <span data-ttu-id="e6b19-1454">kaarthouder
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1454">kaarthouder</span></span> 
- <span data-ttu-id="e6b19-1455">kaarthouders
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1455">kaarthouders</span></span> 
- <span data-ttu-id="e6b19-1456">karte
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1456">karte</span></span>  
- <span data-ttu-id="e6b19-1457">karteninhaber
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1457">karteninhaber</span></span> 
- <span data-ttu-id="e6b19-1458">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="e6b19-1458">karteninhabers</span></span>
- <span data-ttu-id="e6b19-1459">
kartennr
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1459">kartennr</span></span> 
- <span data-ttu-id="e6b19-1460">kartennummer</span><span class="sxs-lookup"><span data-stu-id="e6b19-1460">kartennummer</span></span> 
- <span data-ttu-id="e6b19-1461">kreditkarte
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1461">kreditkarte</span></span> 
- <span data-ttu-id="e6b19-1462">kreditkarten nummer</span><span class="sxs-lookup"><span data-stu-id="e6b19-1462">kreditkarten-nummer</span></span> 
- <span data-ttu-id="e6b19-1463">kreditkarteninhaber
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1463">kreditkarteninhaber</span></span> 
- <span data-ttu-id="e6b19-1464">kreditkarteninstitut
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1464">kreditkarteninstitut</span></span> 
- <span data-ttu-id="e6b19-1465">kreditkartennummer
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1465">kreditkartennummer</span></span> 
- <span data-ttu-id="e6b19-1466">kreditkartentyp
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1466">kreditkartentyp</span></span> 
- <span data-ttu-id="e6b19-1467">maestro
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1467">maestro</span></span> 
- <span data-ttu-id="e6b19-1468">Master Card
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1468">master card</span></span> 
- <span data-ttu-id="e6b19-1469">master cards
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1469">master cards</span></span> 
- <span data-ttu-id="e6b19-1470">mastercard
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1470">mastercard</span></span> 
- <span data-ttu-id="e6b19-1471">mastercards</span><span class="sxs-lookup"><span data-stu-id="e6b19-1471">mastercards</span></span> 
- <span data-ttu-id="e6b19-1472">mc</span><span class="sxs-lookup"><span data-stu-id="e6b19-1472">mc</span></span> 
- <span data-ttu-id="e6b19-1473">mister cash
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1473">mister cash</span></span> 
- <span data-ttu-id="e6b19-1474">n carta</span><span class="sxs-lookup"><span data-stu-id="e6b19-1474">n carta</span></span> 
- <span data-ttu-id="e6b19-1475">carta</span><span class="sxs-lookup"><span data-stu-id="e6b19-1475">carta</span></span> 
- <span data-ttu-id="e6b19-1476">没有 de tarjeta</span><span class="sxs-lookup"><span data-stu-id="e6b19-1476">no de tarjeta</span></span> 
- <span data-ttu-id="e6b19-1477">没有执行 cartao</span><span class="sxs-lookup"><span data-stu-id="e6b19-1477">no do cartao</span></span> 
- <span data-ttu-id="e6b19-1478">没有执行 cartão</span><span class="sxs-lookup"><span data-stu-id="e6b19-1478">no do cartão</span></span> 
- <span data-ttu-id="e6b19-p117">no. de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="e6b19-p117">no. de tarjeta</span></span> 
- <span data-ttu-id="e6b19-p118">no. do cartao
</span><span class="sxs-lookup"><span data-stu-id="e6b19-p118">no. do cartao</span></span> 
- <span data-ttu-id="e6b19-p119">no. do cartão
</span><span class="sxs-lookup"><span data-stu-id="e6b19-p119">no. do cartão</span></span> 
- <span data-ttu-id="e6b19-1485">nr carta</span><span class="sxs-lookup"><span data-stu-id="e6b19-1485">nr carta</span></span> 
- <span data-ttu-id="e6b19-p120">nr. carta
</span><span class="sxs-lookup"><span data-stu-id="e6b19-p120">nr. carta</span></span> 
- <span data-ttu-id="e6b19-1488">numeri di scheda
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1488">numeri di scheda</span></span> 
- <span data-ttu-id="e6b19-1489">numero carta
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1489">numero carta</span></span> 
- <span data-ttu-id="e6b19-1490">numero de cartao
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1490">numero de cartao</span></span> 
- <span data-ttu-id="e6b19-1491">numero de carte
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1491">numero de carte</span></span> 
- <span data-ttu-id="e6b19-1492">numero de cartão
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1492">numero de cartão</span></span> 
- <span data-ttu-id="e6b19-1493">numero de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1493">numero de tarjeta</span></span>
- <span data-ttu-id="e6b19-1494">numero della carta
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1494">numero della carta</span></span> 
- <span data-ttu-id="e6b19-1495">numero di carta
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1495">numero di carta</span></span> 
- <span data-ttu-id="e6b19-1496">numero di scheda
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1496">numero di scheda</span></span> 
- <span data-ttu-id="e6b19-1497">numero do cartao
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1497">numero do cartao</span></span> 
- <span data-ttu-id="e6b19-1498">numero do cartão
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1498">numero do cartão</span></span> 
- <span data-ttu-id="e6b19-1499">numéro de carte
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1499">numéro de carte</span></span> 
- <span data-ttu-id="e6b19-1500">nº carta
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1500">nº carta</span></span> 
- <span data-ttu-id="e6b19-1501">nº de carte
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1501">nº de carte</span></span> 
- <span data-ttu-id="e6b19-1502">nº de la carte
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1502">nº de la carte</span></span> 
- <span data-ttu-id="e6b19-1503">nº de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1503">nº de tarjeta</span></span> 
- <span data-ttu-id="e6b19-1504">nº do cartao
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1504">nº do cartao</span></span> 
- <span data-ttu-id="e6b19-1505">nº 执行 cartão</span><span class="sxs-lookup"><span data-stu-id="e6b19-1505">nº do cartão</span></span> 
- <span data-ttu-id="e6b19-p121">nº. do cartão
</span><span class="sxs-lookup"><span data-stu-id="e6b19-p121">nº. do cartão</span></span> 
- <span data-ttu-id="e6b19-1508">número de cartao
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1508">número de cartao</span></span> 
- <span data-ttu-id="e6b19-1509">número de cartão
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1509">número de cartão</span></span> 
- <span data-ttu-id="e6b19-1510">número de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1510">número de tarjeta</span></span> 
- <span data-ttu-id="e6b19-1511">número do cartao</span><span class="sxs-lookup"><span data-stu-id="e6b19-1511">número do cartao</span></span> 
- <span data-ttu-id="e6b19-1512">scheda dell'assegno
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1512">scheda dell'assegno</span></span> 
- <span data-ttu-id="e6b19-1513">scheda dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1513">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="e6b19-1514">scheda dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1514">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="e6b19-1515">scheda della banca
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1515">scheda della banca</span></span> 
- <span data-ttu-id="e6b19-1516">scheda di controllo
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1516">scheda di controllo</span></span> 
- <span data-ttu-id="e6b19-1517">scheda di debito
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1517">scheda di debito</span></span> 
- <span data-ttu-id="e6b19-1518">scheda matrice
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1518">scheda matrice</span></span> 
- <span data-ttu-id="e6b19-1519">schede dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1519">schede dell'atmosfera</span></span> 
- <span data-ttu-id="e6b19-1520">schede di controllo
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1520">schede di controllo</span></span> 
- <span data-ttu-id="e6b19-1521">schede di debito
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1521">schede di debito</span></span> 
- <span data-ttu-id="e6b19-1522">schede matrici
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1522">schede matrici</span></span> 
- <span data-ttu-id="e6b19-1523">scoprono la scheda
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1523">scoprono la scheda</span></span> 
- <span data-ttu-id="e6b19-1524">scoprono le schede
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1524">scoprono le schede</span></span> 
- <span data-ttu-id="e6b19-1525">solo
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1525">solo</span></span> 
- <span data-ttu-id="e6b19-1526">supporti di scheda
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1526">supporti di scheda</span></span> 
- <span data-ttu-id="e6b19-1527">supporto di scheda
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1527">supporto di scheda</span></span> 
- <span data-ttu-id="e6b19-1528">切换</span><span class="sxs-lookup"><span data-stu-id="e6b19-1528">switch</span></span> 
- <span data-ttu-id="e6b19-1529">tarjeta atm
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1529">tarjeta atm</span></span> 
- <span data-ttu-id="e6b19-1530">tarjeta credito
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1530">tarjeta credito</span></span> 
- <span data-ttu-id="e6b19-1531">tarjeta de atm
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1531">tarjeta de atm</span></span> 
- <span data-ttu-id="e6b19-1532">tarjeta de credito
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1532">tarjeta de credito</span></span> 
- <span data-ttu-id="e6b19-1533">tarjeta de debito
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1533">tarjeta de debito</span></span> 
- <span data-ttu-id="e6b19-1534">tarjeta debito
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1534">tarjeta debito</span></span> 
- <span data-ttu-id="e6b19-1535">tarjeta no
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1535">tarjeta no</span></span>
- <span data-ttu-id="e6b19-1536">tarjetahabiente
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1536">tarjetahabiente</span></span> 
- <span data-ttu-id="e6b19-1537">tipo della scheda
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1537">tipo della scheda</span></span> 
- <span data-ttu-id="e6b19-1538">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="e6b19-1538">ufficio giapponese della</span></span> 
- <span data-ttu-id="e6b19-1539">scheda
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1539">scheda</span></span> 
- <span data-ttu-id="e6b19-1540">v pay
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1540">v pay</span></span> 
- <span data-ttu-id="e6b19-1541">v 付薪</span><span class="sxs-lookup"><span data-stu-id="e6b19-1541">v-pay</span></span> 
- <span data-ttu-id="e6b19-1542">visa
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1542">visa</span></span> 
- <span data-ttu-id="e6b19-1543">visa plus
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1543">visa plus</span></span> 
- <span data-ttu-id="e6b19-1544">visa electron
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1544">visa electron</span></span> 
- <span data-ttu-id="e6b19-1545">visto
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1545">visto</span></span> 
- <span data-ttu-id="e6b19-1546">visum
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1546">visum</span></span> 
- <span data-ttu-id="e6b19-1547">vpay
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1547">vpay</span></span>   

#### <a name="keywordcardsecuritytermsdict"></a><span data-ttu-id="e6b19-1548">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="e6b19-1548">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="e6b19-1549">card identification number</span><span class="sxs-lookup"><span data-stu-id="e6b19-1549">card identification number</span></span>
- <span data-ttu-id="e6b19-1550">card verification</span><span class="sxs-lookup"><span data-stu-id="e6b19-1550">card verification</span></span> 
- <span data-ttu-id="e6b19-1551">cardi la verifica
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1551">cardi la verifica</span></span> 
- <span data-ttu-id="e6b19-1552">cid
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1552">cid</span></span> 
- <span data-ttu-id="e6b19-1553">cod seg</span><span class="sxs-lookup"><span data-stu-id="e6b19-1553">cod seg</span></span> 
- <span data-ttu-id="e6b19-1554">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="e6b19-1554">cod seguranca</span></span> 
- <span data-ttu-id="e6b19-1555">cod segurança</span><span class="sxs-lookup"><span data-stu-id="e6b19-1555">cod segurança</span></span> 
- <span data-ttu-id="e6b19-1556">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="e6b19-1556">cod sicurezza</span></span> 
- <span data-ttu-id="e6b19-p122">cod. seg
</span><span class="sxs-lookup"><span data-stu-id="e6b19-p122">cod. seg</span></span> 
- <span data-ttu-id="e6b19-p123">cod. seguranca
</span><span class="sxs-lookup"><span data-stu-id="e6b19-p123">cod. seguranca</span></span> 
- <span data-ttu-id="e6b19-p124">cod. segurança
</span><span class="sxs-lookup"><span data-stu-id="e6b19-p124">cod. segurança</span></span> 
- <span data-ttu-id="e6b19-p125">cod. sicurezza
</span><span class="sxs-lookup"><span data-stu-id="e6b19-p125">cod. sicurezza</span></span> 
- <span data-ttu-id="e6b19-1565">codice di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1565">codice di sicurezza</span></span> 
- <span data-ttu-id="e6b19-1566">codice di verifica
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1566">codice di verifica</span></span> 
- <span data-ttu-id="e6b19-1567">codigo
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1567">codigo</span></span> 
- <span data-ttu-id="e6b19-1568">codigo de seguranca
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1568">codigo de seguranca</span></span> 
- <span data-ttu-id="e6b19-1569">codigo de segurança
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1569">codigo de segurança</span></span> 
- <span data-ttu-id="e6b19-1570">crittogramma
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1570">crittogramma</span></span> 
- <span data-ttu-id="e6b19-1571">cryptogram
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1571">cryptogram</span></span> 
- <span data-ttu-id="e6b19-1572">cryptogramme
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1572">cryptogramme</span></span> 
- <span data-ttu-id="e6b19-1573">cv2</span><span class="sxs-lookup"><span data-stu-id="e6b19-1573">cv2</span></span> 
- <span data-ttu-id="e6b19-1574">cvc
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1574">cvc</span></span> 
- <span data-ttu-id="e6b19-1575">cvc2</span><span class="sxs-lookup"><span data-stu-id="e6b19-1575">cvc2</span></span> 
- <span data-ttu-id="e6b19-1576">cvn
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1576">cvn</span></span> 
- <span data-ttu-id="e6b19-1577">cvv
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1577">cvv</span></span> 
- <span data-ttu-id="e6b19-1578">cvv2</span><span class="sxs-lookup"><span data-stu-id="e6b19-1578">cvv2</span></span> 
- <span data-ttu-id="e6b19-1579">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="e6b19-1579">cód seguranca</span></span> 
- <span data-ttu-id="e6b19-1580">cód segurança</span><span class="sxs-lookup"><span data-stu-id="e6b19-1580">cód segurança</span></span> 
- <span data-ttu-id="e6b19-p126">cód. seguranca
</span><span class="sxs-lookup"><span data-stu-id="e6b19-p126">cód. seguranca</span></span> 
- <span data-ttu-id="e6b19-p127">cód. segurança
</span><span class="sxs-lookup"><span data-stu-id="e6b19-p127">cód. segurança</span></span> 
- <span data-ttu-id="e6b19-1585">código
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1585">código</span></span> 
- <span data-ttu-id="e6b19-1586">código de seguranca
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1586">código de seguranca</span></span> 
- <span data-ttu-id="e6b19-1587">código de segurança
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1587">código de segurança</span></span> 
- <span data-ttu-id="e6b19-1588">de kaart controle
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1588">de kaart controle</span></span> 
- <span data-ttu-id="e6b19-1589">geeft nr uit
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1589">geeft nr uit</span></span> 
- <span data-ttu-id="e6b19-1590">issue no
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1590">issue no</span></span> 
- <span data-ttu-id="e6b19-1591">issue number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1591">issue number</span></span> 
- <span data-ttu-id="e6b19-1592">kaartidentificatienummer
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1592">kaartidentificatienummer</span></span> 
- <span data-ttu-id="e6b19-1593">kreditkartenprufnummer
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1593">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="e6b19-1594">kreditkartenprüfnummer
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1594">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="e6b19-1595">kwestieaantal
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1595">kwestieaantal</span></span> 
- <span data-ttu-id="e6b19-p128">no. dell'edizione
</span><span class="sxs-lookup"><span data-stu-id="e6b19-p128">no. dell'edizione</span></span> 
- <span data-ttu-id="e6b19-p129">no. di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="e6b19-p129">no. di sicurezza</span></span> 
- <span data-ttu-id="e6b19-1600">numero de securite
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1600">numero de securite</span></span> 
- <span data-ttu-id="e6b19-1601">numero de verificacao
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1601">numero de verificacao</span></span> 
- <span data-ttu-id="e6b19-1602">numero dell'edizione
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1602">numero dell'edizione</span></span> 
- <span data-ttu-id="e6b19-1603">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="e6b19-1603">numero di identificazione della</span></span> 
- <span data-ttu-id="e6b19-1604">scheda
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1604">scheda</span></span> 
- <span data-ttu-id="e6b19-1605">numero di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1605">numero di sicurezza</span></span> 
- <span data-ttu-id="e6b19-1606">numero van veiligheid
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1606">numero van veiligheid</span></span> 
- <span data-ttu-id="e6b19-1607">numéro de sécurité
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1607">numéro de sécurité</span></span> 
- <span data-ttu-id="e6b19-1608">nº autorizzazione
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1608">nº autorizzazione</span></span> 
- <span data-ttu-id="e6b19-1609">número de verificação
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1609">número de verificação</span></span> 
- <span data-ttu-id="e6b19-1610">perno il blocco
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1610">perno il blocco</span></span> 
- <span data-ttu-id="e6b19-1611">pin block
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1611">pin block</span></span> 
- <span data-ttu-id="e6b19-1612">prufziffer
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1612">prufziffer</span></span> 
- <span data-ttu-id="e6b19-1613">prüfziffer
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1613">prüfziffer</span></span> 
- <span data-ttu-id="e6b19-1614">security code
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1614">security code</span></span> 
- <span data-ttu-id="e6b19-1615">security no
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1615">security no</span></span> 
- <span data-ttu-id="e6b19-1616">security number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1616">security number</span></span> 
- <span data-ttu-id="e6b19-1617">sicherheits kode
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1617">sicherheits kode</span></span> 
- <span data-ttu-id="e6b19-1618">sicherheitscode
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1618">sicherheitscode</span></span> 
- <span data-ttu-id="e6b19-1619">sicherheitsnummer
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1619">sicherheitsnummer</span></span> 
- <span data-ttu-id="e6b19-1620">speldblok
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1620">speldblok</span></span> 
- <span data-ttu-id="e6b19-1621">veiligheid nr
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1621">veiligheid nr</span></span> 
- <span data-ttu-id="e6b19-1622">veiligheidsaantal
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1622">veiligheidsaantal</span></span> 
- <span data-ttu-id="e6b19-1623">veiligheidscode
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1623">veiligheidscode</span></span> 
- <span data-ttu-id="e6b19-1624">veiligheidsnummer
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1624">veiligheidsnummer</span></span> 
- <span data-ttu-id="e6b19-1625">verfalldatum
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1625">verfalldatum</span></span> 

#### <a name="keywordcardexpirationtermsdict"></a><span data-ttu-id="e6b19-1626">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="e6b19-1626">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="e6b19-1627">ablauf
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1627">ablauf</span></span> 
- <span data-ttu-id="e6b19-1628">data de expiracao
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1628">data de expiracao</span></span> 
- <span data-ttu-id="e6b19-1629">data de expiração
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1629">data de expiração</span></span> 
- <span data-ttu-id="e6b19-1630">data del exp
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1630">data del exp</span></span> 
- <span data-ttu-id="e6b19-1631">data di exp
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1631">data di exp</span></span> 
- <span data-ttu-id="e6b19-1632">data di scadenza
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1632">data di scadenza</span></span> 
- <span data-ttu-id="e6b19-1633">data em que expira
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1633">data em que expira</span></span> 
- <span data-ttu-id="e6b19-1634">data scad
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1634">data scad</span></span> 
- <span data-ttu-id="e6b19-1635">data scadenza
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1635">data scadenza</span></span> 
- <span data-ttu-id="e6b19-1636">date de validité
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1636">date de validité</span></span> 
- <span data-ttu-id="e6b19-1637">datum afloop
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1637">datum afloop</span></span> 
- <span data-ttu-id="e6b19-1638">datum van exp
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1638">datum van exp</span></span> 
- <span data-ttu-id="e6b19-1639">de afloop
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1639">de afloop</span></span> 
- <span data-ttu-id="e6b19-1640">espira
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1640">espira</span></span> 
- <span data-ttu-id="e6b19-1641">espira
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1641">espira</span></span> 
- <span data-ttu-id="e6b19-1642">exp date
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1642">exp date</span></span> 
- <span data-ttu-id="e6b19-1643">exp datum
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1643">exp datum</span></span> 
- <span data-ttu-id="e6b19-1644">过期</span><span class="sxs-lookup"><span data-stu-id="e6b19-1644">expiration</span></span> 
- <span data-ttu-id="e6b19-1645">expire
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1645">expire</span></span> 
- <span data-ttu-id="e6b19-1646">expires
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1646">expires</span></span> 
- <span data-ttu-id="e6b19-1647">expiry
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1647">expiry</span></span> 
- <span data-ttu-id="e6b19-1648">fecha de expiracion
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1648">fecha de expiracion</span></span> 
- <span data-ttu-id="e6b19-1649">fecha de venc
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1649">fecha de venc</span></span> 
- <span data-ttu-id="e6b19-1650">gultig bis
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1650">gultig bis</span></span> 
- <span data-ttu-id="e6b19-1651">gultigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1651">gultigkeitsdatum</span></span> 
- <span data-ttu-id="e6b19-1652">gültig bis
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1652">gültig bis</span></span> 
- <span data-ttu-id="e6b19-1653">gültigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1653">gültigkeitsdatum</span></span> 
- <span data-ttu-id="e6b19-1654">la scadenza
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1654">la scadenza</span></span> 
- <span data-ttu-id="e6b19-1655">scadenza
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1655">scadenza</span></span> 
- <span data-ttu-id="e6b19-1656">valable
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1656">valable</span></span> 
- <span data-ttu-id="e6b19-1657">validade
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1657">validade</span></span> 
- <span data-ttu-id="e6b19-1658">valido hasta
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1658">valido hasta</span></span> 
- <span data-ttu-id="e6b19-1659">valor
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1659">valor</span></span> 
- <span data-ttu-id="e6b19-1660">venc
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1660">venc</span></span> 
- <span data-ttu-id="e6b19-1661">vencimento
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1661">vencimento</span></span> 
- <span data-ttu-id="e6b19-1662">vencimiento
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1662">vencimiento</span></span> 
- <span data-ttu-id="e6b19-1663">verloopt
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1663">verloopt</span></span> 
- <span data-ttu-id="e6b19-1664">vervaldag
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1664">vervaldag</span></span> 
- <span data-ttu-id="e6b19-1665">vervaldatum
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1665">vervaldatum</span></span> 
- <span data-ttu-id="e6b19-1666">vto
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1666">vto</span></span> 
- <span data-ttu-id="e6b19-1667">válido hasta
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1667">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="e6b19-1668">欧盟驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-1668">EU Driver's License Number</span></span>

<span data-ttu-id="e6b19-1669">若要了解详细信息，请参阅[欧盟驱动程序驾驶证号码敏感信息类型](eu-driver-s-license-number.md)。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1669">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="e6b19-1670">欧盟 National 标识号</span><span class="sxs-lookup"><span data-stu-id="e6b19-1670">EU National Identification Number</span></span>

<span data-ttu-id="e6b19-1671">若要了解详细信息，请参阅[欧盟国家/地区标识号敏感信息类型](eu-national-identification-number.md)。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1671">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="e6b19-1672">欧盟护照号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-1672">EU Passport Number</span></span>

<span data-ttu-id="e6b19-1673">若要了解详细信息，请参阅[欧盟护照号码敏感信息类型](eu-passport-number.md)。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1673">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="e6b19-1674">欧盟社会保险号或等效 ID</span><span class="sxs-lookup"><span data-stu-id="e6b19-1674">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="e6b19-1675">若要了解详细信息，请参阅[欧盟社会保险号或等效 ID 敏感信息类型](eu-social-security-number-or-equivalent-id.md)。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1675">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="e6b19-1676">欧盟纳税标识号</span><span class="sxs-lookup"><span data-stu-id="e6b19-1676">EU Tax Identification Number</span></span>

<span data-ttu-id="e6b19-1677">若要了解详细信息，请参阅[欧盟纳税标识号敏感信息类型](eu-tax-identification-number.md)。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1677">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="e6b19-1678">芬兰国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="e6b19-1678">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-1679">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-1679">Format</span></span>

<span data-ttu-id="e6b19-1680">六个数字加一个字符（表示一个世纪），加三个数字再加一个校验位</span><span class="sxs-lookup"><span data-stu-id="e6b19-1680">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-1681">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-1681">Pattern</span></span>

<span data-ttu-id="e6b19-1682">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1682">Pattern must include all of the following:</span></span>
- <span data-ttu-id="e6b19-1683">采用 DDMMYY 格式的六位数字，表示出生日期</span><span class="sxs-lookup"><span data-stu-id="e6b19-1683">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="e6b19-1684">世纪标记（“-”、“+”或“a”）</span><span class="sxs-lookup"><span data-stu-id="e6b19-1684">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="e6b19-1685">三位个人标识号</span><span class="sxs-lookup"><span data-stu-id="e6b19-1685">Three-digit personal identification number</span></span> 
- <span data-ttu-id="e6b19-1686">一个数字或字母（区分大小写），是校验位</span><span class="sxs-lookup"><span data-stu-id="e6b19-1686">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-1687">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-1687">Checksum</span></span>

<span data-ttu-id="e6b19-1688">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-1688">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-1689">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-1689">Definition</span></span>

<span data-ttu-id="e6b19-1690">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1690">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-1691">函数 Func_finnish_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1691">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-1692">找到 Keyword_finnish_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1692">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="e6b19-1693">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1693">The checksum passes.</span></span>

```
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6b19-1694">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1694">Keywords</span></span>

- <span data-ttu-id="e6b19-1695">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="e6b19-1695">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="e6b19-1696">

Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="e6b19-1696">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="e6b19-1697">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="e6b19-1697">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="e6b19-1698">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="e6b19-1698">Personbeteckning</span></span>
- <span data-ttu-id="e6b19-1699">Personnummer</span><span class="sxs-lookup"><span data-stu-id="e6b19-1699">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="e6b19-1700">芬兰护照号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-1700">Finland Passport Number</span></span>

<span data-ttu-id="e6b19-p130">设置格式的九个字母和数字模式的九个字母和数字的组合组合： 两个字母 （不区分大小写） 的第七位数字校验和无定义 DLP 策略为 75%确信，如果，它已检测到此类型的敏感信息，在两者之间300 个字符的邻近性： 正则表达式 Regex_finland_passport_number 找到与模式匹配的内容。找到从 Keyword_finland_passport_number 关键字。<!-- Finland Passport Number --> 
 <Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern> 
</Entity>关键字 Keyword_finland_passport_number Passport Passi</span><span class="sxs-lookup"><span data-stu-id="e6b19-p130">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern. A keyword from Keyword_finland_passport_number is found. <!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity> Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="e6b19-1705">法国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-1705">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-1706">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-1706">Format</span></span>

<span data-ttu-id="e6b19-1707">12 个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1707">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-1708">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-1708">Pattern</span></span>

<span data-ttu-id="e6b19-1709">12 个数字，会对类似模式（如法国电话号码）进行验证</span><span class="sxs-lookup"><span data-stu-id="e6b19-1709">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-1710">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-1710">Checksum</span></span>

<span data-ttu-id="e6b19-1711">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-1711">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-1712">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-1712">Definition</span></span>

<span data-ttu-id="e6b19-1713">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1713">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-1714">函数 Func_french_drivers_license 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1714">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-1715">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1715">At least one of the following is true:</span></span>
- <span data-ttu-id="e6b19-1716">找到 Keyword_french_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1716">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="e6b19-1717">函数 Func_eu_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1717">The function Func_eu_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-1718">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1718">Keywords</span></span>

#### <a name="keywordfrenchdriverslicense"></a><span data-ttu-id="e6b19-1719">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="e6b19-1719">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="e6b19-1720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="e6b19-1720">drivers licence</span></span>
- <span data-ttu-id="e6b19-1721">drivers license</span><span class="sxs-lookup"><span data-stu-id="e6b19-1721">drivers license</span></span>
- <span data-ttu-id="e6b19-1722">driving licence
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1722">driving licence</span></span>
- <span data-ttu-id="e6b19-1723">驱动许可证</span><span class="sxs-lookup"><span data-stu-id="e6b19-1723">driving license</span></span>
- <span data-ttu-id="e6b19-1724">
permis de conduire</span><span class="sxs-lookup"><span data-stu-id="e6b19-1724">permis de conduire</span></span>
- <span data-ttu-id="e6b19-1725">
licence number</span><span class="sxs-lookup"><span data-stu-id="e6b19-1725">licence number</span></span>
- <span data-ttu-id="e6b19-1726">
license number</span><span class="sxs-lookup"><span data-stu-id="e6b19-1726">license number</span></span>
- <span data-ttu-id="e6b19-1727">
licence numbers</span><span class="sxs-lookup"><span data-stu-id="e6b19-1727">licence numbers</span></span>
- <span data-ttu-id="e6b19-1728">

license numbers</span><span class="sxs-lookup"><span data-stu-id="e6b19-1728">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="e6b19-1729">法国国家/地区 ID 卡 (CNI)</span><span class="sxs-lookup"><span data-stu-id="e6b19-1729">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-1730">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-1730">Format</span></span>

<span data-ttu-id="e6b19-1731">12 个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1731">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-1732">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-1732">Pattern</span></span>

<span data-ttu-id="e6b19-1733">12 个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1733">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-1734">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-1734">Checksum</span></span>

<span data-ttu-id="e6b19-1735">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-1735">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-1736">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-1736">Definition</span></span>

<span data-ttu-id="e6b19-1737">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1737">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-1738">正则表达式 Regex_france_cni 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1738">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6b19-1739">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1739">Keywords</span></span>

<span data-ttu-id="e6b19-1740">无</span><span class="sxs-lookup"><span data-stu-id="e6b19-1740">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="e6b19-1741">法国护照号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-1741">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-1742">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-1742">Format</span></span>

<span data-ttu-id="e6b19-1743">9 个数字和字母</span><span class="sxs-lookup"><span data-stu-id="e6b19-1743">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-1744">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-1744">Pattern</span></span>

<span data-ttu-id="e6b19-1745">九位数字和字母：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1745">Nine digits and letters:</span></span>
- <span data-ttu-id="e6b19-1746">两位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1746">Two digits</span></span> 
- <span data-ttu-id="e6b19-1747">两个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="e6b19-1747">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="e6b19-1748">五位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1748">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-1749">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-1749">Checksum</span></span>

<span data-ttu-id="e6b19-1750">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-1750">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-1751">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-1751">Definition</span></span>

<span data-ttu-id="e6b19-1752">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1752">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-1753">函数 Func_fr_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1753">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-1754">找到 Keyword_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1754">A keyword from Keyword_passport is found.</span></span>

```
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6b19-1755">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1755">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="e6b19-1756">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="e6b19-1756">Keyword_passport</span></span>

- <span data-ttu-id="e6b19-1757">Passport Number</span><span class="sxs-lookup"><span data-stu-id="e6b19-1757">Passport Number</span></span>
- <span data-ttu-id="e6b19-1758">
Passport No</span><span class="sxs-lookup"><span data-stu-id="e6b19-1758">Passport No</span></span>
- <span data-ttu-id="e6b19-1759">Passport #
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1759">Passport #</span></span>
- <span data-ttu-id="e6b19-1760">Passport#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1760">Passport#</span></span>
- <span data-ttu-id="e6b19-1761">PassportID</span><span class="sxs-lookup"><span data-stu-id="e6b19-1761">PassportID</span></span>
- <span data-ttu-id="e6b19-1762">Passportno
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1762">Passportno</span></span>
- <span data-ttu-id="e6b19-1763">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1763">passportnumber</span></span>
- <span data-ttu-id="e6b19-1764">パスポート</span><span class="sxs-lookup"><span data-stu-id="e6b19-1764">パスポート</span></span>
- <span data-ttu-id="e6b19-1765">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1765">パスポート番号</span></span>
- <span data-ttu-id="e6b19-1766">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1766">パスポートのNum</span></span>
- <span data-ttu-id="e6b19-1767">
パスポート ＃
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1767">パスポート ＃</span></span> 
- <span data-ttu-id="e6b19-1768">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="e6b19-1768">Numéro de passeport</span></span>
- <span data-ttu-id="e6b19-1769">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="e6b19-1769">Passeport n °</span></span>
- <span data-ttu-id="e6b19-1770">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1770">Passeport Non</span></span>
- <span data-ttu-id="e6b19-1771">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1771">Passeport #</span></span>
- <span data-ttu-id="e6b19-1772">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1772">Passeport#</span></span>
- <span data-ttu-id="e6b19-1773">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="e6b19-1773">PasseportNon</span></span>
- <span data-ttu-id="e6b19-1774">

Passeportn °</span><span class="sxs-lookup"><span data-stu-id="e6b19-1774">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="e6b19-1775">法国社会保险号 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="e6b19-1775">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-1776">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-1776">Format</span></span>

<span data-ttu-id="e6b19-1777">15 个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1777">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-1778">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-1778">Pattern</span></span>

<span data-ttu-id="e6b19-1779">必须匹配两种模式之一：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1779">Must match one of two patterns:</span></span>
- <span data-ttu-id="e6b19-1780">13 跟两位数字后跟一个空格的数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1780">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="e6b19-1781">或</span><span class="sxs-lookup"><span data-stu-id="e6b19-1781">or</span></span>
- <span data-ttu-id="e6b19-1782">15 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1782">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-1783">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-1783">Checksum</span></span>

<span data-ttu-id="e6b19-1784">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-1784">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-1785">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-1785">Definition</span></span>

<span data-ttu-id="e6b19-1786">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1786">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-1787">函数 Func_french_insee 或 Func_fr_insee 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1787">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-1788">找到 Keyword_fr_insee 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1788">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="e6b19-1789">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1789">The checksum passes.</span></span>

<span data-ttu-id="e6b19-1790">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1790">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-1791">函数 Func_french_insee 或 Func_fr_insee 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1791">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-1792">未找到 Keyword_fr_insee 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1792">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="e6b19-1793">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1793">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-1794">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1794">Keywords</span></span>

#### <a name="keywordfrinsee"></a><span data-ttu-id="e6b19-1795">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="e6b19-1795">Keyword_fr_insee</span></span>

- <span data-ttu-id="e6b19-1796">insee</span><span class="sxs-lookup"><span data-stu-id="e6b19-1796">insee</span></span>
- <span data-ttu-id="e6b19-1797">
securité sociale</span><span class="sxs-lookup"><span data-stu-id="e6b19-1797">securité sociale</span></span>
- <span data-ttu-id="e6b19-1798">
securite sociale</span><span class="sxs-lookup"><span data-stu-id="e6b19-1798">securite sociale</span></span>
- <span data-ttu-id="e6b19-1799">
national id</span><span class="sxs-lookup"><span data-stu-id="e6b19-1799">national id</span></span>
- <span data-ttu-id="e6b19-1800">
national identification</span><span class="sxs-lookup"><span data-stu-id="e6b19-1800">national identification</span></span>
- <span data-ttu-id="e6b19-1801">
numéro d identité</span><span class="sxs-lookup"><span data-stu-id="e6b19-1801">numéro d'identité</span></span>
- <span data-ttu-id="e6b19-1802">没有 d'identité</span><span class="sxs-lookup"><span data-stu-id="e6b19-1802">no d'identité</span></span>
- <span data-ttu-id="e6b19-p131">
no. d'identité</span><span class="sxs-lookup"><span data-stu-id="e6b19-p131">no. d'identité</span></span>
- <span data-ttu-id="e6b19-1805">
numero d'identite</span><span class="sxs-lookup"><span data-stu-id="e6b19-1805">numero d'identite</span></span>
- <span data-ttu-id="e6b19-1806">没有 d'identite</span><span class="sxs-lookup"><span data-stu-id="e6b19-1806">no d'identite</span></span>
- <span data-ttu-id="e6b19-p132">
no. d'identite</span><span class="sxs-lookup"><span data-stu-id="e6b19-p132">no. d'identite</span></span>
- <span data-ttu-id="e6b19-1809">social security number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1809">social security number</span></span>
- <span data-ttu-id="e6b19-1810">
social security code</span><span class="sxs-lookup"><span data-stu-id="e6b19-1810">social security code</span></span>
- <span data-ttu-id="e6b19-1811">social insurance number</span><span class="sxs-lookup"><span data-stu-id="e6b19-1811">social insurance number</span></span>
- <span data-ttu-id="e6b19-1812">
le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="e6b19-1812">le numéro d'identification nationale</span></span>
- <span data-ttu-id="e6b19-1813">
d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="e6b19-1813">d'identité nationale</span></span>
- <span data-ttu-id="e6b19-1814">
numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="e6b19-1814">numéro de sécurité sociale</span></span>
- <span data-ttu-id="e6b19-1815">
le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="e6b19-1815">le code de la sécurité sociale</span></span>
- <span data-ttu-id="e6b19-1816">
numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="e6b19-1816">numéro d'assurance sociale</span></span>
- <span data-ttu-id="e6b19-1817">
numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="e6b19-1817">numéro de sécu</span></span>
- <span data-ttu-id="e6b19-1818">
code sécu
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1818">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="e6b19-1819">德国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-1819">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-1820">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-1820">Format</span></span>

<span data-ttu-id="e6b19-1821">11 个数字和字母组合</span><span class="sxs-lookup"><span data-stu-id="e6b19-1821">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-1822">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-1822">Pattern</span></span>

<span data-ttu-id="e6b19-1823">11 位数字和字母（不区分大小写）：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1823">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="e6b19-1824">一个数字或字母</span><span class="sxs-lookup"><span data-stu-id="e6b19-1824">A digit or letter</span></span> 
- <span data-ttu-id="e6b19-1825">两位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1825">Two digits</span></span> 
- <span data-ttu-id="e6b19-1826">六位数字或字母</span><span class="sxs-lookup"><span data-stu-id="e6b19-1826">Six digits or letters</span></span> 
- <span data-ttu-id="e6b19-1827">一位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1827">A digit</span></span> 
- <span data-ttu-id="e6b19-1828">一个数字或字母</span><span class="sxs-lookup"><span data-stu-id="e6b19-1828">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-1829">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-1829">Checksum</span></span>

<span data-ttu-id="e6b19-1830">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-1830">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-1831">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-1831">Definition</span></span>

<span data-ttu-id="e6b19-1832">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-1833">函数 Func_german_drivers_license 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1833">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-1834">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1834">At least one of the following is true:</span></span>
    - <span data-ttu-id="e6b19-1835">找到 Keyword_german_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1835">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="e6b19-1836">找到 Keyword_german_drivers_license_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1836">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="e6b19-1837">找到 Keyword_german_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1837">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="e6b19-1838">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1838">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-1839">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1839">Keywords</span></span>

#### <a name="keywordgermandriverslicensenumber"></a><span data-ttu-id="e6b19-1840">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="e6b19-1840">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="e6b19-1841">Führerschein</span><span class="sxs-lookup"><span data-stu-id="e6b19-1841">Führerschein</span></span>
- <span data-ttu-id="e6b19-1842">
Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="e6b19-1842">Fuhrerschein</span></span>
- <span data-ttu-id="e6b19-1843">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="e6b19-1843">Fuehrerschein</span></span>
- <span data-ttu-id="e6b19-1844">
Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="e6b19-1844">Führerscheinnummer</span></span>
- <span data-ttu-id="e6b19-1845">
Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="e6b19-1845">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="e6b19-1846">
Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="e6b19-1846">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="e6b19-1847">
Führerschein-
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1847">Führerschein-</span></span> 
- <span data-ttu-id="e6b19-1848">Fuhrerschein-
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1848">Fuhrerschein-</span></span> 
- <span data-ttu-id="e6b19-1849">Fuehrerschein-
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1849">Fuehrerschein-</span></span> 
- <span data-ttu-id="e6b19-1850">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="e6b19-1850">FührerscheinnummerNr</span></span>
- <span data-ttu-id="e6b19-1851">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="e6b19-1851">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="e6b19-1852">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="e6b19-1852">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="e6b19-1853">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="e6b19-1853">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="e6b19-1854">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="e6b19-1854">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="e6b19-1855">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="e6b19-1855">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="e6b19-1856">Führerschein-Nr
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1856">Führerschein- Nr</span></span>
- <span data-ttu-id="e6b19-1857">Fuhrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1857">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="e6b19-1858">Fuehrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1858">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="e6b19-1859">Führerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1859">Führerschein- Klasse</span></span> 
- <span data-ttu-id="e6b19-1860">Fuhrerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1860">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="e6b19-1861">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="e6b19-1861">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="e6b19-1862">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="e6b19-1862">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="e6b19-1863">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="e6b19-1863">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="e6b19-1864">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="e6b19-1864">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="e6b19-1865">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="e6b19-1865">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="e6b19-1866">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="e6b19-1866">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="e6b19-1867">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="e6b19-1867">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="e6b19-1868">Führerschein-Nr
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1868">Führerschein- Nr</span></span> 
- <span data-ttu-id="e6b19-1869">Fuhrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1869">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="e6b19-1870">Fuehrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1870">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="e6b19-1871">Führerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1871">Führerschein- Klasse</span></span> 
- <span data-ttu-id="e6b19-1872">Fuhrerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1872">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="e6b19-1873">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="e6b19-1873">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="e6b19-1874">DL</span><span class="sxs-lookup"><span data-stu-id="e6b19-1874">DL</span></span> 
- <span data-ttu-id="e6b19-1875">DLS</span><span class="sxs-lookup"><span data-stu-id="e6b19-1875">DLS</span></span>
- <span data-ttu-id="e6b19-1876">
Driv Lic
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1876">Driv Lic</span></span> 
- <span data-ttu-id="e6b19-1877">Driv Licen
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1877">Driv Licen</span></span> 
- <span data-ttu-id="e6b19-1878">Driv License</span><span class="sxs-lookup"><span data-stu-id="e6b19-1878">Driv License</span></span>
- <span data-ttu-id="e6b19-1879">
Driv Licenses
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1879">Driv Licenses</span></span> 
- <span data-ttu-id="e6b19-1880">Driv Licence
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1880">Driv Licence</span></span> 
- <span data-ttu-id="e6b19-1881">Driv Licences
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1881">Driv Licences</span></span> 
- <span data-ttu-id="e6b19-1882">Driv Lic
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1882">Driv Lic</span></span> 
- <span data-ttu-id="e6b19-1883">Driver Licen
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1883">Driver Licen</span></span> 
- <span data-ttu-id="e6b19-1884">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="e6b19-1884">Driver License</span></span> 
- <span data-ttu-id="e6b19-1885">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="e6b19-1885">Driver Licenses</span></span> 
- <span data-ttu-id="e6b19-1886">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1886">Driver Licence</span></span> 
- <span data-ttu-id="e6b19-1887">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1887">Driver Licences</span></span> 
- <span data-ttu-id="e6b19-1888">驱动因素 Lic</span><span class="sxs-lookup"><span data-stu-id="e6b19-1888">Drivers Lic</span></span> 
- <span data-ttu-id="e6b19-1889">驱动因素 Licen</span><span class="sxs-lookup"><span data-stu-id="e6b19-1889">Drivers Licen</span></span> 
- <span data-ttu-id="e6b19-1890">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="e6b19-1890">Drivers License</span></span> 
- <span data-ttu-id="e6b19-1891">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="e6b19-1891">Drivers Licenses</span></span> 
- <span data-ttu-id="e6b19-1892">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="e6b19-1892">Drivers Licence</span></span> 
- <span data-ttu-id="e6b19-1893">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="e6b19-1893">Drivers Licences</span></span> 
- <span data-ttu-id="e6b19-1894">驱动因素的 Lic</span><span class="sxs-lookup"><span data-stu-id="e6b19-1894">Driver's Lic</span></span> 
- <span data-ttu-id="e6b19-1895">Driver's Licen
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1895">Driver's Licen</span></span> 
- <span data-ttu-id="e6b19-1896">驱动程序的许可证</span><span class="sxs-lookup"><span data-stu-id="e6b19-1896">Driver's License</span></span> 
- <span data-ttu-id="e6b19-1897">驱动程序的许可证</span><span class="sxs-lookup"><span data-stu-id="e6b19-1897">Driver's Licenses</span></span> 
- <span data-ttu-id="e6b19-1898">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1898">Driver's Licence</span></span> 
- <span data-ttu-id="e6b19-1899">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1899">Driver's Licences</span></span> 
- <span data-ttu-id="e6b19-1900">Driving Lic
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1900">Driving Lic</span></span> 
- <span data-ttu-id="e6b19-1901">Driving Licen
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1901">Driving Licen</span></span> 
- <span data-ttu-id="e6b19-1902">Driving License
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1902">Driving License</span></span> 
- <span data-ttu-id="e6b19-1903">Driving Licenses
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1903">Driving Licenses</span></span> 
- <span data-ttu-id="e6b19-1904">Driving Licence

</span><span class="sxs-lookup"><span data-stu-id="e6b19-1904">Driving Licence</span></span> 
- <span data-ttu-id="e6b19-1905">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="e6b19-1905">Driving Licences</span></span>

#### <a name="keywordgermandriverslicensecollaborative"></a><span data-ttu-id="e6b19-1906">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="e6b19-1906">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="e6b19-1907">
Nr-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1907">Nr-Führerschein</span></span> 
- <span data-ttu-id="e6b19-1908">Nr-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1908">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="e6b19-1909">Nr-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1909">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="e6b19-1910">No-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1910">No-Führerschein</span></span> 
- <span data-ttu-id="e6b19-1911">No-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1911">No-Fuhrerschein</span></span> 
- <span data-ttu-id="e6b19-1912">No-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1912">No-Fuehrerschein</span></span> 
- <span data-ttu-id="e6b19-1913">N-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1913">N-Führerschein</span></span> 
- <span data-ttu-id="e6b19-1914">N-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1914">N-Fuhrerschein</span></span> 
- <span data-ttu-id="e6b19-1915">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="e6b19-1915">N-Fuehrerschein</span></span>
- <span data-ttu-id="e6b19-1916">
Nr-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1916">Nr-Führerschein</span></span> 
- <span data-ttu-id="e6b19-1917">Nr-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1917">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="e6b19-1918">Nr-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1918">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="e6b19-1919">No-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1919">No-Führerschein</span></span> 
- <span data-ttu-id="e6b19-1920">No-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1920">No-Fuhrerschein</span></span> 
- <span data-ttu-id="e6b19-1921">No-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1921">No-Fuehrerschein</span></span> 
- <span data-ttu-id="e6b19-1922">N-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1922">N-Führerschein</span></span> 
- <span data-ttu-id="e6b19-1923">N-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1923">N-Fuhrerschein</span></span> 
- <span data-ttu-id="e6b19-1924">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="e6b19-1924">N-Fuehrerschein</span></span> 

#### <a name="keywordgermandriverslicense"></a><span data-ttu-id="e6b19-1925">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="e6b19-1925">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="e6b19-1926">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="e6b19-1926">ausstellungsdatum</span></span>
- <span data-ttu-id="e6b19-1927">
ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="e6b19-1927">ausstellungsort</span></span>
- <span data-ttu-id="e6b19-1928">
ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="e6b19-1928">ausstellende behöde</span></span>
- <span data-ttu-id="e6b19-1929">
ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="e6b19-1929">ausstellende behorde</span></span>
- <span data-ttu-id="e6b19-1930">

ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="e6b19-1930">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="e6b19-1931">德国护照号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-1931">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-1932">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-1932">Format</span></span>

<span data-ttu-id="e6b19-1933">10 个数字或字母</span><span class="sxs-lookup"><span data-stu-id="e6b19-1933">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-1934">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-1934">Pattern</span></span>

<span data-ttu-id="e6b19-1935">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1935">Pattern must include all of the following:</span></span>
- <span data-ttu-id="e6b19-1936">第一个字符是这一组（C、F、G、H、J、K）中的数字或字母</span><span class="sxs-lookup"><span data-stu-id="e6b19-1936">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="e6b19-1937">三位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1937">Three digits</span></span> 
- <span data-ttu-id="e6b19-1938">五位数字或字母都来源于这一组（C、-H、J-N、P、R、T，V-Z）</span><span class="sxs-lookup"><span data-stu-id="e6b19-1938">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="e6b19-1939">一位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1939">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-1940">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-1940">Checksum</span></span>

<span data-ttu-id="e6b19-1941">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-1941">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-1942">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-1942">Definition</span></span>

<span data-ttu-id="e6b19-1943">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1943">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-1944">函数 Func_german_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1944">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-1945">找到以下任意五个关键字列表中的关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1945">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="e6b19-1946">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1946">The checksum passes.</span></span>

<span data-ttu-id="e6b19-1947">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1947">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-1948">函数 Func_german_passport_data 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1948">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-1949">找到以下任意五个关键字列表中的关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1949">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="e6b19-1950">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1950">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-1951">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1951">Keywords</span></span>

#### <a name="keywordgermanpassport"></a><span data-ttu-id="e6b19-1952">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="e6b19-1952">Keyword_german_passport</span></span>

- <span data-ttu-id="e6b19-1953">reisepass</span><span class="sxs-lookup"><span data-stu-id="e6b19-1953">reisepass</span></span>
- <span data-ttu-id="e6b19-1954">
reisepasse</span><span class="sxs-lookup"><span data-stu-id="e6b19-1954">reisepasse</span></span>
- <span data-ttu-id="e6b19-1955">
reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="e6b19-1955">reisepassnummer</span></span>
- <span data-ttu-id="e6b19-1956">passport</span><span class="sxs-lookup"><span data-stu-id="e6b19-1956">passport</span></span>
- <span data-ttu-id="e6b19-1957">

passports</span><span class="sxs-lookup"><span data-stu-id="e6b19-1957">passports</span></span>

#### <a name="keywordgermanpassportcollaborative"></a><span data-ttu-id="e6b19-1958">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="e6b19-1958">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="e6b19-1959">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="e6b19-1959">geburtsdatum</span></span>
- <span data-ttu-id="e6b19-1960">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="e6b19-1960">ausstellungsdatum</span></span>
- <span data-ttu-id="e6b19-1961">
ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="e6b19-1961">ausstellungsort</span></span>

#### <a name="keywordgermanpassportnumber"></a><span data-ttu-id="e6b19-1962">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="e6b19-1962">Keyword_german_passport_number</span></span>

<span data-ttu-id="e6b19-1963">不-Reisepass Nr Reisepass</span><span class="sxs-lookup"><span data-stu-id="e6b19-1963">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keywordgermanpassport1"></a><span data-ttu-id="e6b19-1964">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="e6b19-1964">Keyword_german_passport1</span></span>

<span data-ttu-id="e6b19-1965">Reisepass-Nr
</span><span class="sxs-lookup"><span data-stu-id="e6b19-1965">Reisepass-Nr</span></span>

#### <a name="keywordgermanpassport2"></a><span data-ttu-id="e6b19-1966">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="e6b19-1966">Keyword_german_passport2</span></span>

<span data-ttu-id="e6b19-1967">bnationalit.t</span><span class="sxs-lookup"><span data-stu-id="e6b19-1967">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="e6b19-1968">德国身份证号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-1968">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-1969">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-1969">Format</span></span>

<span data-ttu-id="e6b19-1970">2010 年 11 月 1 相： 九个字母和数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1970">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="e6b19-1971">从直到 31 年 10 月 2010年: 10 位数字 1 年 4 月 1987</span><span class="sxs-lookup"><span data-stu-id="e6b19-1971">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-1972">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-1972">Pattern</span></span>

<span data-ttu-id="e6b19-1973">自 2010 年 11 月 1 日起：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1973">Since 1 November 2010:</span></span>
- <span data-ttu-id="e6b19-1974">一个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="e6b19-1974">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="e6b19-1975">八个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1975">Eight digits</span></span>

<span data-ttu-id="e6b19-1976">从直到 31 2010 年 10 月 1 年 4 月 1987:</span><span class="sxs-lookup"><span data-stu-id="e6b19-1976">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="e6b19-1977">10 个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1977">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-1978">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-1978">Checksum</span></span>

<span data-ttu-id="e6b19-1979">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-1979">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-1980">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-1980">Definition</span></span>

<span data-ttu-id="e6b19-1981">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1981">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-1982">正则表达式 Regex_germany_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1982">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-1983">找到 Keyword_germany_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-1983">A keyword from Keyword_germany_id_card is found.</span></span>

```
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6b19-1984">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-1984">Keywords</span></span>

#### <a name="keywordgermanyidcard"></a><span data-ttu-id="e6b19-1985">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="e6b19-1985">Keyword_germany_id_card</span></span>

- <span data-ttu-id="e6b19-1986">Identity Card</span><span class="sxs-lookup"><span data-stu-id="e6b19-1986">Identity Card</span></span>
- <span data-ttu-id="e6b19-1987">ID</span><span class="sxs-lookup"><span data-stu-id="e6b19-1987">ID</span></span>
- <span data-ttu-id="e6b19-1988">Identification</span><span class="sxs-lookup"><span data-stu-id="e6b19-1988">Identification</span></span>
- <span data-ttu-id="e6b19-1989">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="e6b19-1989">Personalausweis</span></span>
- <span data-ttu-id="e6b19-1990">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="e6b19-1990">Identifizierungsnummer</span></span>
- <span data-ttu-id="e6b19-1991">Ausweis</span><span class="sxs-lookup"><span data-stu-id="e6b19-1991">Ausweis</span></span>
- <span data-ttu-id="e6b19-1992">Identifikation</span><span class="sxs-lookup"><span data-stu-id="e6b19-1992">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="e6b19-1993">希腊国家 ID 卡</span><span class="sxs-lookup"><span data-stu-id="e6b19-1993">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-1994">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-1994">Format</span></span>

<span data-ttu-id="e6b19-1995">7-8 个字母和数字组合加一个短划线</span><span class="sxs-lookup"><span data-stu-id="e6b19-1995">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-1996">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-1996">Pattern</span></span>

<span data-ttu-id="e6b19-1997">七个字母和数字（旧格式）：</span><span class="sxs-lookup"><span data-stu-id="e6b19-1997">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="e6b19-1998">一个字母（希腊字母表中的任一字母） </span><span class="sxs-lookup"><span data-stu-id="e6b19-1998">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="e6b19-1999">一个短划线 </span><span class="sxs-lookup"><span data-stu-id="e6b19-1999">A dash</span></span> 
- <span data-ttu-id="e6b19-2000">六个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2000">Six digits</span></span>

<span data-ttu-id="e6b19-2001">八个字母和数字（新格式）：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2001">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="e6b19-2002">大写字符同时出现在希腊和拉丁字母表中的两个字母 (ABEZHIKMNOPTYX) </span><span class="sxs-lookup"><span data-stu-id="e6b19-2002">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="e6b19-2003">一个短划线 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2003">A dash</span></span> 
- <span data-ttu-id="e6b19-2004">六个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2004">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2005">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2005">Checksum</span></span>

<span data-ttu-id="e6b19-2006">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-2006">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2007">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2007">Definition</span></span>

<span data-ttu-id="e6b19-2008">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2008">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2009">正则表达式 Regex_greece_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2009">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2010">找到 Keyword_greece_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2010">A keyword from Keyword_greece_id_card is found.</span></span>

```
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6b19-2011">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2011">Keywords</span></span>

#### <a name="keywordgreeceidcard"></a><span data-ttu-id="e6b19-2012">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="e6b19-2012">Keyword_greece_id_card</span></span>

- <span data-ttu-id="e6b19-2013">Greek identity Card</span><span class="sxs-lookup"><span data-stu-id="e6b19-2013">Greek identity Card</span></span>
- <span data-ttu-id="e6b19-2014">Tautotita</span><span class="sxs-lookup"><span data-stu-id="e6b19-2014">Tautotita</span></span>
- <span data-ttu-id="e6b19-2015">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="e6b19-2015">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="e6b19-2016">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="e6b19-2016">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="e6b19-2017">香港身份证 (HKID) 号</span><span class="sxs-lookup"><span data-stu-id="e6b19-2017">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2018">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2018">Format</span></span>

<span data-ttu-id="e6b19-2019">8-9 个字母和数字组合，最后一个字符两边可选择加括号</span><span class="sxs-lookup"><span data-stu-id="e6b19-2019">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2020">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2020">Pattern</span></span>

<span data-ttu-id="e6b19-2021">8-9 个字母组合：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2021">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="e6b19-2022">1-2 个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="e6b19-2022">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="e6b19-2023">六个数字 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2023">Six digits</span></span> 
- <span data-ttu-id="e6b19-2024">最后一个字符（任意数字或字母 A）是校验位，两边可以选择加括号。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2024">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2025">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2025">Checksum</span></span>

<span data-ttu-id="e6b19-2026">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-2026">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2027">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2027">Definition</span></span>

<span data-ttu-id="e6b19-2028">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2028">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2029">函数 Func_hong_kong_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2029">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2030">找到 Keyword_hong_kong_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2030">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="e6b19-2031">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2031">The checksum passes.</span></span>

<span data-ttu-id="e6b19-2032">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2032">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2033">函数 Func_hong_kong_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2033">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2034">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2034">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-2035">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2035">Keywords</span></span>

#### <a name="keywordhongkongidcard"></a><span data-ttu-id="e6b19-2036">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="e6b19-2036">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="e6b19-2037">香港特别行政区身份证</span><span class="sxs-lookup"><span data-stu-id="e6b19-2037">hong kong identity card</span></span>
- <span data-ttu-id="e6b19-2038">HKIDC</span><span class="sxs-lookup"><span data-stu-id="e6b19-2038">HKIDC</span></span>
- <span data-ttu-id="e6b19-2039">身份证</span><span class="sxs-lookup"><span data-stu-id="e6b19-2039">id card</span></span>
- <span data-ttu-id="e6b19-2040">identity card</span><span class="sxs-lookup"><span data-stu-id="e6b19-2040">identity card</span></span>
- <span data-ttu-id="e6b19-2041">hk 身份证</span><span class="sxs-lookup"><span data-stu-id="e6b19-2041">hk identity card</span></span>
- <span data-ttu-id="e6b19-2042">香港特别行政区 id</span><span class="sxs-lookup"><span data-stu-id="e6b19-2042">hong kong id</span></span>
- <span data-ttu-id="e6b19-2043">香港身份證
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2043">香港身份證</span></span>
- <span data-ttu-id="e6b19-2044">香港永久性居民身份證
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2044">香港永久性居民身份證</span></span>
- <span data-ttu-id="e6b19-2045">身份證
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2045">身份證</span></span>
- <span data-ttu-id="e6b19-2046">身份証</span><span class="sxs-lookup"><span data-stu-id="e6b19-2046">身份証</span></span>
- <span data-ttu-id="e6b19-2047">身分證 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2047">身分證</span></span>
- <span data-ttu-id="e6b19-2048">身分証</span><span class="sxs-lookup"><span data-stu-id="e6b19-2048">身分証</span></span>
- <span data-ttu-id="e6b19-2049">香港身份証</span><span class="sxs-lookup"><span data-stu-id="e6b19-2049">香港身份証</span></span>
- <span data-ttu-id="e6b19-2050">香港身分證</span><span class="sxs-lookup"><span data-stu-id="e6b19-2050">香港身分證</span></span>
- <span data-ttu-id="e6b19-2051">香港身分証</span><span class="sxs-lookup"><span data-stu-id="e6b19-2051">香港身分証</span></span>
- <span data-ttu-id="e6b19-2052">香港身份證
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2052">香港身份證</span></span>
- <span data-ttu-id="e6b19-2053">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="e6b19-2053">香港居民身份證</span></span>
- <span data-ttu-id="e6b19-2054">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="e6b19-2054">香港居民身份証</span></span>
- <span data-ttu-id="e6b19-2055">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="e6b19-2055">香港居民身分證</span></span>
- <span data-ttu-id="e6b19-2056">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="e6b19-2056">香港居民身分証</span></span>
- <span data-ttu-id="e6b19-2057">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="e6b19-2057">香港永久性居民身份証</span></span>
- <span data-ttu-id="e6b19-2058">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="e6b19-2058">香港永久性居民身分證</span></span>
- <span data-ttu-id="e6b19-2059">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="e6b19-2059">香港永久性居民身分証</span></span>
- <span data-ttu-id="e6b19-2060">香港永久性居民身份證
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2060">香港永久性居民身份證</span></span>
- <span data-ttu-id="e6b19-2061">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="e6b19-2061">香港非永久性居民身份證</span></span>
- <span data-ttu-id="e6b19-2062">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="e6b19-2062">香港非永久性居民身份証</span></span>
- <span data-ttu-id="e6b19-2063">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="e6b19-2063">香港非永久性居民身分證</span></span>
- <span data-ttu-id="e6b19-2064">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="e6b19-2064">香港非永久性居民身分証</span></span>
- <span data-ttu-id="e6b19-2065">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="e6b19-2065">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="e6b19-2066">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="e6b19-2066">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="e6b19-2067">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="e6b19-2067">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="e6b19-2068">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="e6b19-2068">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="e6b19-2069">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="e6b19-2069">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="e6b19-2070">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="e6b19-2070">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="e6b19-2071">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="e6b19-2071">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="e6b19-2072">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="e6b19-2072">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="e6b19-2073">印度永久帐号 (PAN)</span><span class="sxs-lookup"><span data-stu-id="e6b19-2073">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2074">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2074">Format</span></span>

<span data-ttu-id="e6b19-2075">10 个字母或数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2075">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2076">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2076">Pattern</span></span>

<span data-ttu-id="e6b19-2077">10 个字母或数字：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2077">10 letters or digits:</span></span>
- <span data-ttu-id="e6b19-2078">五个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="e6b19-2078">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="e6b19-2079">四个数字 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2079">Four digits</span></span> 
- <span data-ttu-id="e6b19-2080">一个字母，是字母校验位</span><span class="sxs-lookup"><span data-stu-id="e6b19-2080">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2081">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2081">Checksum</span></span>

<span data-ttu-id="e6b19-2082">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-2082">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2083">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2083">Definition</span></span>

<span data-ttu-id="e6b19-2084">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2084">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2085">正则表达式 Regex_india_permanent_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2085">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2086">找到 Keyword_india_permanent_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2086">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="e6b19-2087">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2087">The checksum passes.</span></span>

```
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6b19-2088">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2088">Keywords</span></span>

#### <a name="keywordindiapermanentaccountnumber"></a><span data-ttu-id="e6b19-2089">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="e6b19-2089">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="e6b19-2090">Permanent Account Number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2090">Permanent Account Number</span></span> 
- <span data-ttu-id="e6b19-2091">PAN
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2091">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="e6b19-2092">India Unique Identification (Aadhaar) Number</span><span class="sxs-lookup"><span data-stu-id="e6b19-2092">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2093">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2093">Format</span></span>

<span data-ttu-id="e6b19-2094">12 个数字（包含可选空格或短划线）</span><span class="sxs-lookup"><span data-stu-id="e6b19-2094">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2095">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2095">Pattern</span></span>

<span data-ttu-id="e6b19-2096">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2096">12 digits:</span></span>
- <span data-ttu-id="e6b19-2097">四个数字 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2097">Four digits</span></span> 
- <span data-ttu-id="e6b19-2098">一个可选空格或短划线 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2098">An optional space or dash</span></span> 
- <span data-ttu-id="e6b19-2099">四个数字 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2099">Four digits</span></span> 
- <span data-ttu-id="e6b19-2100">一个可选空格或短划线 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2100">An optional space or dash</span></span> 
- <span data-ttu-id="e6b19-2101">最后一个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="e6b19-2101">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2102">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2102">Checksum</span></span>

<span data-ttu-id="e6b19-2103">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-2103">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2104">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2104">Definition</span></span>

<span data-ttu-id="e6b19-p133">DLP 策略是 85%相信它已检测到此类型的敏感信息 if、 内 300 个字符的邻近度： 函数 Func_india_aadhaar 查找与模式匹配的内容。找到从 Keyword_india_aadhar 关键字。将传递校验和。DLP 策略是相信它已检测到此类型的敏感信息的 75 %if、 内 300 个字符的邻近度： 函数 Func_india_aadhaar 查找与模式匹配的内容。将传递校验和。<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="e6b19-p133">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern. A keyword from Keyword_india_aadhar is found. The checksum passes. A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern. The checksum passes. <!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span></span>

### <a name="keywords"></a><span data-ttu-id="e6b19-2111">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2111">Keywords</span></span>
   
#### <a name="keywordindiaaadhar"></a><span data-ttu-id="e6b19-2112">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="e6b19-2112">Keyword_india_aadhar</span></span>
- <span data-ttu-id="e6b19-2113">Aadhar</span><span class="sxs-lookup"><span data-stu-id="e6b19-2113">Aadhar</span></span>
- <span data-ttu-id="e6b19-2114">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="e6b19-2114">Aadhaar</span></span>
- <span data-ttu-id="e6b19-2115">UID</span><span class="sxs-lookup"><span data-stu-id="e6b19-2115">UID</span></span>
- <span data-ttu-id="e6b19-2116">आधार</span><span class="sxs-lookup"><span data-stu-id="e6b19-2116">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="e6b19-2117">印度尼西亚身份证 (KTP) 号</span><span class="sxs-lookup"><span data-stu-id="e6b19-2117">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2118">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2118">Format</span></span>

<span data-ttu-id="e6b19-2119">16 个数字（包含可选点）</span><span class="sxs-lookup"><span data-stu-id="e6b19-2119">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2120">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2120">Pattern</span></span>

<span data-ttu-id="e6b19-2121">16 个数字：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2121">16 digits:</span></span>
- <span data-ttu-id="e6b19-2122">两位省代码 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2122">Two-digit province code</span></span> 
- <span data-ttu-id="e6b19-2123">一个点（可选） </span><span class="sxs-lookup"><span data-stu-id="e6b19-2123">A period (optional)</span></span> 
- <span data-ttu-id="e6b19-2124">两位摄政统治区或城市代码 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2124">Two-digit regency or city code</span></span> 
- <span data-ttu-id="e6b19-2125">两位住宅小区代码 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2125">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="e6b19-2126">一个点（可选） </span><span class="sxs-lookup"><span data-stu-id="e6b19-2126">A period (optional)</span></span> 
- <span data-ttu-id="e6b19-2127">六个数字，采用  DDMMYY 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2127">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="e6b19-2128">一个点（可选） </span><span class="sxs-lookup"><span data-stu-id="e6b19-2128">A period (optional)</span></span> 
- <span data-ttu-id="e6b19-2129">四个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2129">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2130">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2130">Checksum</span></span>

<span data-ttu-id="e6b19-2131">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-2131">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2132">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2132">Definition</span></span>

<span data-ttu-id="e6b19-2133">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2133">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2134">正则表达式 Regex_indonesia_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2134">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2135">找到 Keyword_indonesia_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2135">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="e6b19-2136">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2136">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2137">正则表达式 Regex_indonesia_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2137">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-2138">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2138">Keywords</span></span>
   
#### <a name="keywordindonesiaidcard"></a><span data-ttu-id="e6b19-2139">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="e6b19-2139">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="e6b19-2140">KTP</span><span class="sxs-lookup"><span data-stu-id="e6b19-2140">KTP</span></span>
- <span data-ttu-id="e6b19-2141">Kartu Tanda Penduduk
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2141">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="e6b19-2142">Nomor Induk Kependudukan
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2142">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="e6b19-2143">国际银行帐号 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="e6b19-2143">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2144">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2144">Format</span></span>

<span data-ttu-id="e6b19-2145">国家/地区代码（两个字母）加校验位（两个数字）以及 bban 号码（最多 30 个字符）</span><span class="sxs-lookup"><span data-stu-id="e6b19-2145">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2146">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2146">Pattern</span></span>

<span data-ttu-id="e6b19-2147">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2147">Pattern must include all of the following:</span></span>

- <span data-ttu-id="e6b19-2148">两个字母的国家/地区代码</span><span class="sxs-lookup"><span data-stu-id="e6b19-2148">Two-letter country code</span></span>
- <span data-ttu-id="e6b19-2149">两个校验位（后跟一个可选空间） </span><span class="sxs-lookup"><span data-stu-id="e6b19-2149">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="e6b19-2150">1-7 个包含 4 个字母或数字的组（可以使用空格进行分隔）</span><span class="sxs-lookup"><span data-stu-id="e6b19-2150">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="e6b19-2151">1-3 个字母或数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2151">1-3 letters or digits</span></span>

<span data-ttu-id="e6b19-p134">每个国家/地区的格式稍有不同。IBAN 敏感信息类型涵盖这 60 个国家/地区：</span><span class="sxs-lookup"><span data-stu-id="e6b19-p134">The format for each country is slightly different. The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="e6b19-2154">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span><span class="sxs-lookup"><span data-stu-id="e6b19-2154">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2155">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2155">Checksum</span></span>

<span data-ttu-id="e6b19-2156">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-2156">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2157">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2157">Definition</span></span>

<span data-ttu-id="e6b19-2158">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2158">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2159">函数 Func_iban 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2159">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2160">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2160">The checksum passes.</span></span>

```
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6b19-2161">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2161">Keywords</span></span>

<span data-ttu-id="e6b19-2162">无</span><span class="sxs-lookup"><span data-stu-id="e6b19-2162">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="e6b19-2163">IP 地址</span><span class="sxs-lookup"><span data-stu-id="e6b19-2163">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2164">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2164">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="e6b19-2165">IPv4：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2165">IPv4:</span></span>
<span data-ttu-id="e6b19-2166">解释 IPv4 地址格式化（点）版本或非格式化（没有点）版本的复杂模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2166">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="e6b19-2167">IPv6：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2167">IPv6:</span></span>
<span data-ttu-id="e6b19-2168"> 解释格式化 IPv6 号码（包含冒号）的复杂模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2168">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2169">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2169">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2170">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2170">Checksum</span></span>

<span data-ttu-id="e6b19-2171">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-2171">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2172">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2172">Definition</span></span>

<span data-ttu-id="e6b19-2173">对于 IPv6，在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2173">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2174">正则表达式 Regex_ipv6_address 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2174">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2175">未找到 Keyword_ipaddress 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2175">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="e6b19-2176">对于 IPv4，在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2176">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2177">正则表达式 Regex_ipv4_address 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2177">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2178">找到 Keyword_ipaddress 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2178">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="e6b19-2179">对于 IPv6，在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2179">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2180">正则表达式 Regex_ipv6_address 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2180">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2181">未找到 Keyword_ipaddress 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2181">No keyword from Keyword_ipaddress is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-2182">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2182">Keywords</span></span>

#### <a name="keywordipaddress"></a><span data-ttu-id="e6b19-2183">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="e6b19-2183">Keyword_ipaddress</span></span>

- <span data-ttu-id="e6b19-2184">IP（此关键字区分大小写）</span><span class="sxs-lookup"><span data-stu-id="e6b19-2184">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="e6b19-2185">ip address
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2185">ip address</span></span> 
- <span data-ttu-id="e6b19-2186">ip addresses</span><span class="sxs-lookup"><span data-stu-id="e6b19-2186">ip addresses</span></span>
- <span data-ttu-id="e6b19-2187">internet protocol</span><span class="sxs-lookup"><span data-stu-id="e6b19-2187">internet protocol</span></span>
- <span data-ttu-id="e6b19-2188">
IP-כתובת ה
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2188">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="e6b19-2189">国际分类的科 （ICD-10-厘米）</span><span class="sxs-lookup"><span data-stu-id="e6b19-2189">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2190">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2190">Format</span></span>

<span data-ttu-id="e6b19-2191">词典</span><span class="sxs-lookup"><span data-stu-id="e6b19-2191">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2192">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2192">Pattern</span></span>

<span data-ttu-id="e6b19-2193">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2193">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2194">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2194">Checksum</span></span>

<span data-ttu-id="e6b19-2195">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-2195">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2196">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2196">Definition</span></span>

<span data-ttu-id="e6b19-2197">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2197">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2198">找到从 Dictionary_icd_10_cm 关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2198">A keyword from Dictionary_icd_10_cm is found.</span></span>

```
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

<span data-ttu-id="e6b19-2199">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2199">Keywords</span></span>

<span data-ttu-id="e6b19-p135">Dictionary_icd_10_cm 关键字字典中的任何术语的基于[国际分类的科、 第十修订，临床修改 （ICD-10-厘米）](https://go.microsoft.com/fwlink/?linkid=852604)。此类型仅查找术语，不保险代码。</span><span class="sxs-lookup"><span data-stu-id="e6b19-p135">Any term from the Dictionary_icd_10_cm keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604). This type looks only for the term, not the insurance codes.</span></span>

   
## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="e6b19-2202">国际分类的科 （ICD-9-厘米）</span><span class="sxs-lookup"><span data-stu-id="e6b19-2202">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2203">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2203">Format</span></span>

<span data-ttu-id="e6b19-2204">词典</span><span class="sxs-lookup"><span data-stu-id="e6b19-2204">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2205">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2205">Pattern</span></span>

<span data-ttu-id="e6b19-2206">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2206">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2207">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2207">Checksum</span></span>

<span data-ttu-id="e6b19-2208">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-2208">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2209">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2209">Definition</span></span>

<span data-ttu-id="e6b19-2210">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2210">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2211">找到从 Dictionary_icd_9_cm 关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2211">A keyword from Dictionary_icd_9_cm is found.</span></span>

```
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6b19-2212">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2212">Keywords</span></span>

<span data-ttu-id="e6b19-p136">Dictionary_icd_9_cm 关键字字典中的任何术语的基于[国际分类的科、 第九个修订，临床修改 （ICD-9-厘米）](https://go.microsoft.com/fwlink/?linkid=852605)。此类型仅查找术语，不保险代码。</span><span class="sxs-lookup"><span data-stu-id="e6b19-p136">Any term from the Dictionary_icd_9_cm keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605). This type looks only for the term, not the insurance codes.</span></span>
   
## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="e6b19-2215">爱尔兰个人公共服务 (PPS) 号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-2215">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2216">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2216">Format</span></span>

<span data-ttu-id="e6b19-2217">（到 Dec 2012 年 31） 的旧格式：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2217">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="e6b19-2218">七位数字后跟 1-2  个字母 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2218">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="e6b19-2219">新的格式 (2013 年 1 月 1 和之后):</span><span class="sxs-lookup"><span data-stu-id="e6b19-2219">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="e6b19-2220">七位数字后跟两个字母</span><span class="sxs-lookup"><span data-stu-id="e6b19-2220">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2221">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2221">Pattern</span></span>

<span data-ttu-id="e6b19-2222">（到 Dec 2012 年 31） 的旧格式：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2222">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="e6b19-2223">七个数字 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2223">Seven digits</span></span> 
- <span data-ttu-id="e6b19-2224">1-2 个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="e6b19-2224">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="e6b19-2225">新的格式 (2013 年 1 月 1 和之后):</span><span class="sxs-lookup"><span data-stu-id="e6b19-2225">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="e6b19-2226">七个数字 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2226">Seven digits</span></span> 
- <span data-ttu-id="e6b19-2227">一个字母（不区分大小写），是字母校验位 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2227">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="e6b19-2228">字母“A”或“H”（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="e6b19-2228">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2229">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2229">Checksum</span></span>

<span data-ttu-id="e6b19-2230">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-2230">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2231">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2231">Definition</span></span>

<span data-ttu-id="e6b19-2232">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2232">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2233">函数 Func_ireland_pps 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2233">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2234">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2234">One of the following is true:</span></span>
    - <span data-ttu-id="e6b19-2235">找到 Keyword_ireland_pps 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2235">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="e6b19-2236">函数 Func_eu_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2236">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="e6b19-2237">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2237">The checksum passes.</span></span>

<span data-ttu-id="e6b19-2238">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2238">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2239">函数 Func_ireland_pps 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2239">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2240">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2240">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-2241">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2241">Keywords</span></span>

#### <a name="keywordirelandpps"></a><span data-ttu-id="e6b19-2242">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="e6b19-2242">Keyword_ireland_pps</span></span>

- <span data-ttu-id="e6b19-2243">Personal Public Service Number 
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2243">Personal Public Service Number</span></span> 
- <span data-ttu-id="e6b19-2244">PPS Number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2244">PPS Number</span></span> 
- <span data-ttu-id="e6b19-2245">PPS Num
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2245">PPS Num</span></span> 
- <span data-ttu-id="e6b19-2246">PPS No.
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2246">PPS No.</span></span> 
- <span data-ttu-id="e6b19-2247">PPS #
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2247">PPS #</span></span> 
- <span data-ttu-id="e6b19-2248">PPS #</span><span class="sxs-lookup"><span data-stu-id="e6b19-2248">PPS#</span></span> 
- <span data-ttu-id="e6b19-2249">PPSN
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2249">PPSN</span></span> 
- <span data-ttu-id="e6b19-2250">Public Services Card
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2250">Public Services Card</span></span> 
- <span data-ttu-id="e6b19-2251">Uimhir Phearsanta Seirbhíse Poiblí
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2251">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="e6b19-p137">Uimh.PSP
</span><span class="sxs-lookup"><span data-stu-id="e6b19-p137">Uimh. PSP</span></span> 
- <span data-ttu-id="e6b19-2254">PSP
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2254">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="e6b19-2255">以色列银行帐号</span><span class="sxs-lookup"><span data-stu-id="e6b19-2255">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2256">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2256">Format</span></span>

<span data-ttu-id="e6b19-2257">13 位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2257">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2258">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2258">Pattern</span></span>

<span data-ttu-id="e6b19-2259">有格式模式：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2259">Formatted:</span></span>
- <span data-ttu-id="e6b19-2260">两位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2260">Two digits</span></span> 
- <span data-ttu-id="e6b19-2261">破折号</span><span class="sxs-lookup"><span data-stu-id="e6b19-2261">A dash</span></span> 
- <span data-ttu-id="e6b19-2262">三位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2262">Three digits</span></span> 
- <span data-ttu-id="e6b19-2263">破折号</span><span class="sxs-lookup"><span data-stu-id="e6b19-2263">A dash</span></span> 
- <span data-ttu-id="e6b19-2264">八个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2264">Eight digits</span></span>

<span data-ttu-id="e6b19-2265">无格式模式：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2265">Unformatted:</span></span>
- <span data-ttu-id="e6b19-2266">	13 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2266">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2267">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2267">Checksum</span></span>

<span data-ttu-id="e6b19-2268">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-2268">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2269">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2269">Definition</span></span>

<span data-ttu-id="e6b19-2270">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2270">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2271">正则表达式 Regex_israel_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2271">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2272">找到 Keyword_israel_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2272">A keyword from Keyword_israel_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-2273">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2273">Keywords</span></span>

#### <a name="keywordisraelbankaccountnumber"></a><span data-ttu-id="e6b19-2274">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="e6b19-2274">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="e6b19-2275">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2275">Bank Account Number</span></span> 
- <span data-ttu-id="e6b19-2276">Bank Account
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2276">Bank Account</span></span> 
- <span data-ttu-id="e6b19-2277">Account Number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2277">Account Number</span></span> 
- <span data-ttu-id="e6b19-2278">מספר חשבון בנק
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2278">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="e6b19-2279">以色列国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="e6b19-2279">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2280">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2280">Format</span></span>

<span data-ttu-id="e6b19-2281">九个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2281">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2282">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2282">Pattern</span></span>

<span data-ttu-id="e6b19-2283">九个连续的数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2283">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2284">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2284">Checksum</span></span>

<span data-ttu-id="e6b19-2285">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-2285">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2286">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2286">Definition</span></span>

<span data-ttu-id="e6b19-2287">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2287">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2288">函数 Func_israeli_national_id_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2288">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2289">找到 Keyword_Israel_National_ID 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2289">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="e6b19-2290">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2290">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-2291">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2291">Keywords</span></span>

#### <a name="keywordisraelnationalid"></a><span data-ttu-id="e6b19-2292">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="e6b19-2292">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="e6b19-2293">מספר זהות
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2293">מספר זהות</span></span> 
- <span data-ttu-id="e6b19-2294">National ID Number</span><span class="sxs-lookup"><span data-stu-id="e6b19-2294">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="e6b19-2295">意大利驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-2295">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2296">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2296">Format</span></span>

<span data-ttu-id="e6b19-2297">10 个字母和数字的组合</span><span class="sxs-lookup"><span data-stu-id="e6b19-2297">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2298">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2298">Pattern</span></span>

- <span data-ttu-id="e6b19-2299">10 个字母和数字的组合：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2299">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="e6b19-2300">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="e6b19-2300">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="e6b19-2301">字母“A”或者“V”（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="e6b19-2301">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="e6b19-2302">七个字母（不区分大小写）、数字或下划线字符</span><span class="sxs-lookup"><span data-stu-id="e6b19-2302">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="e6b19-2303">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="e6b19-2303">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2304">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2304">Checksum</span></span>

<span data-ttu-id="e6b19-2305">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-2305">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2306">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2306">Definition</span></span>

<span data-ttu-id="e6b19-2307">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2307">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2308">正则表达式 Regex_italy_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2308">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2309">找到 Keyword_italy_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2309">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-2310">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2310">Keywords</span></span>

#### <a name="keyworditalydriverslicensenumber"></a><span data-ttu-id="e6b19-2311">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="e6b19-2311">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="e6b19-2312">numero di patente di guida
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2312">numero di patente di guida</span></span> 
- <span data-ttu-id="e6b19-2313">patente di guida
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2313">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="e6b19-2314">日本银行帐号</span><span class="sxs-lookup"><span data-stu-id="e6b19-2314">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2315">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2315">Format</span></span>

<span data-ttu-id="e6b19-2316">七个或八个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2316">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2317">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2317">Pattern</span></span>

<span data-ttu-id="e6b19-2318">银行帐号：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2318">Bank account number:</span></span>
- <span data-ttu-id="e6b19-2319">七个或八个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2319">Seven or eight digits</span></span>
- <span data-ttu-id="e6b19-2320">银行帐户分支代码：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2320">Bank account branch code:</span></span>
- <span data-ttu-id="e6b19-2321">四位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2321">Four digits</span></span> 
- <span data-ttu-id="e6b19-2322">空格或破折号（可选）</span><span class="sxs-lookup"><span data-stu-id="e6b19-2322">A space or dash (optional)</span></span> 
- <span data-ttu-id="e6b19-2323">三位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2323">Three digits</span></span>

<span data-ttu-id="e6b19-2324">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2324">Checksum</span></span>

<span data-ttu-id="e6b19-2325">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-2325">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2326">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2326">Definition</span></span>

<span data-ttu-id="e6b19-2327">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2327">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2328">函数 Func_jp_bank_account 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2328">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2329">找到 Keyword_jp_bank_account 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2329">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="e6b19-2330">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2330">One of the following is true:</span></span>
- <span data-ttu-id="e6b19-2331">函数 Func_jp_bank_account_branch_code 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2331">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2332">找到 Keyword_jp_bank_branch_code 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2332">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="e6b19-2333">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2333">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2334">函数 Func_jp_bank_account 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2334">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2335">找到 Keyword_jp_bank_account 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2335">A keyword from Keyword_jp_bank_account is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-2336">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2336">Keywords</span></span>

#### <a name="keywordjpbankaccount"></a><span data-ttu-id="e6b19-2337">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="e6b19-2337">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="e6b19-2338">Checking Account Number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2338">Checking Account Number</span></span> 
- <span data-ttu-id="e6b19-2339">Checking Account
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2339">Checking Account</span></span> 
- <span data-ttu-id="e6b19-2340">Checking Account #
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2340">Checking Account #</span></span> 
- <span data-ttu-id="e6b19-2341">Checking Acct Number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2341">Checking Acct Number</span></span> 
- <span data-ttu-id="e6b19-2342">Checking Acct #
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2342">Checking Acct #</span></span> 
- <span data-ttu-id="e6b19-2343">Checking Acct No.
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2343">Checking Acct No.</span></span> 
- <span data-ttu-id="e6b19-2344">Checking Account No.
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2344">Checking Account No.</span></span> 
- <span data-ttu-id="e6b19-2345">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2345">Bank Account Number</span></span> 
- <span data-ttu-id="e6b19-2346">Bank Account
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2346">Bank Account</span></span> 
- <span data-ttu-id="e6b19-2347">Bank Account #
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2347">Bank Account #</span></span> 
- <span data-ttu-id="e6b19-2348">Bank Acct Number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2348">Bank Acct Number</span></span> 
- <span data-ttu-id="e6b19-2349">Bank Acct #
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2349">Bank Acct #</span></span> 
- <span data-ttu-id="e6b19-2350">Bank Acct No.
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2350">Bank Acct No.</span></span> 
- <span data-ttu-id="e6b19-2351">Bank Account No.
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2351">Bank Account No.</span></span> 
- <span data-ttu-id="e6b19-2352">Savings Account Number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2352">Savings Account Number</span></span> 
- <span data-ttu-id="e6b19-2353">节省帐户</span><span class="sxs-lookup"><span data-stu-id="e6b19-2353">Savings Account</span></span> 
- <span data-ttu-id="e6b19-2354">Savings Account #
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2354">Savings Account #</span></span> 
- <span data-ttu-id="e6b19-2355">Savings Acct Number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2355">Savings Acct Number</span></span> 
- <span data-ttu-id="e6b19-2356">Savings Acct #
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2356">Savings Acct #</span></span> 
- <span data-ttu-id="e6b19-2357">Savings Acct No.
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2357">Savings Acct No.</span></span> 
- <span data-ttu-id="e6b19-2358">Savings Account No.
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2358">Savings Account No.</span></span> 
- <span data-ttu-id="e6b19-2359">Debit Account Number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2359">Debit Account Number</span></span> 
- <span data-ttu-id="e6b19-2360">Debit Account
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2360">Debit Account</span></span> 
- <span data-ttu-id="e6b19-2361">Debit Account #
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2361">Debit Account #</span></span> 
- <span data-ttu-id="e6b19-2362">Debit Acct Number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2362">Debit Acct Number</span></span> 
- <span data-ttu-id="e6b19-2363">Debit Acct #
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2363">Debit Acct #</span></span> 
- <span data-ttu-id="e6b19-2364">Debit Acct No.
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2364">Debit Acct No.</span></span> 
- <span data-ttu-id="e6b19-2365">Debit Account No.
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2365">Debit Account No.</span></span> 
- <span data-ttu-id="e6b19-2366">口座番号を当座預金口座の確認
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2366">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="e6b19-2367">＃アカウントの確認、勘定番号の確認
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2367">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="e6b19-2368">＃勘定の確認
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2368">＃勘定の確認</span></span> 
- <span data-ttu-id="e6b19-2369">勘定番号の確認
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2369">勘定番号の確認</span></span> 
- <span data-ttu-id="e6b19-2370">口座番号の確認
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2370">口座番号の確認</span></span> 
- <span data-ttu-id="e6b19-2371">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="e6b19-2371">銀行口座番号</span></span> 
- <span data-ttu-id="e6b19-2372">銀行口座</span><span class="sxs-lookup"><span data-stu-id="e6b19-2372">銀行口座</span></span> 
- <span data-ttu-id="e6b19-2373">銀行口座＃
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2373">銀行口座＃</span></span> 
- <span data-ttu-id="e6b19-2374">銀行の勘定番号
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2374">銀行の勘定番号</span></span> 
- <span data-ttu-id="e6b19-2375">銀行のacct＃
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2375">銀行のacct＃</span></span> 
- <span data-ttu-id="e6b19-2376">銀行の勘定いいえ
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2376">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="e6b19-2377">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="e6b19-2377">銀行口座番号</span></span>
- <span data-ttu-id="e6b19-2378">
普通預金口座番号
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2378">普通預金口座番号</span></span> 
- <span data-ttu-id="e6b19-2379">預金口座
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2379">預金口座</span></span> 
- <span data-ttu-id="e6b19-2380">貯蓄口座＃
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2380">貯蓄口座＃</span></span> 
- <span data-ttu-id="e6b19-2381">貯蓄勘定の数
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2381">貯蓄勘定の数</span></span> 
- <span data-ttu-id="e6b19-2382">貯蓄勘定＃
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2382">貯蓄勘定＃</span></span> 
- <span data-ttu-id="e6b19-2383">貯蓄勘定番号
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2383">貯蓄勘定番号</span></span> 
- <span data-ttu-id="e6b19-2384">普通預金口座番号
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2384">普通預金口座番号</span></span> 
- <span data-ttu-id="e6b19-2385">引き落とし口座番号
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2385">引き落とし口座番号</span></span> 
- <span data-ttu-id="e6b19-2386">口座番号</span><span class="sxs-lookup"><span data-stu-id="e6b19-2386">口座番号</span></span> 
- <span data-ttu-id="e6b19-2387">口座番号＃
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2387">口座番号＃</span></span> 
- <span data-ttu-id="e6b19-2388">デビットのacct番号
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2388">デビットのacct番号</span></span> 
- <span data-ttu-id="e6b19-2389">デビット勘定＃
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2389">デビット勘定＃</span></span> 
- <span data-ttu-id="e6b19-2390">デビットACCTの番号
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2390">デビットACCTの番号</span></span> 
- <span data-ttu-id="e6b19-2391">デビット口座番号
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2391">デビット口座番号</span></span> 

#### <a name="keywordjpbankbranchcode"></a><span data-ttu-id="e6b19-2392">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="e6b19-2392">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="e6b19-2393">Otemachi</span><span class="sxs-lookup"><span data-stu-id="e6b19-2393">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="e6b19-2394">日本驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-2394">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2395">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2395">Format</span></span>

<span data-ttu-id="e6b19-2396">12 个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2396">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2397">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2397">Pattern</span></span>

<span data-ttu-id="e6b19-2398">12 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2398">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2399">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2399">Checksum</span></span>

<span data-ttu-id="e6b19-2400">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-2400">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2401">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2401">Definition</span></span>

<span data-ttu-id="e6b19-2402">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2402">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2403">函数 Func_jp_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2403">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2404">找到 Keyword_jp_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2404">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6b19-2405">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2405">Keywords</span></span>

#### <a name="keywordjpdriverslicensenumber"></a><span data-ttu-id="e6b19-2406">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="e6b19-2406">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="e6b19-2407">dl#</span><span class="sxs-lookup"><span data-stu-id="e6b19-2407">dl#</span></span> 
- <span data-ttu-id="e6b19-2408">DL #</span><span class="sxs-lookup"><span data-stu-id="e6b19-2408">DL＃</span></span> 
- <span data-ttu-id="e6b19-2409">dls#</span><span class="sxs-lookup"><span data-stu-id="e6b19-2409">dls#</span></span> 
- <span data-ttu-id="e6b19-2410">DL #</span><span class="sxs-lookup"><span data-stu-id="e6b19-2410">DLS＃</span></span> 
- <span data-ttu-id="e6b19-2411">driver license</span><span class="sxs-lookup"><span data-stu-id="e6b19-2411">driver license</span></span> 
- <span data-ttu-id="e6b19-2412">driver licenses</span><span class="sxs-lookup"><span data-stu-id="e6b19-2412">driver licenses</span></span> 
- <span data-ttu-id="e6b19-2413">drivers license</span><span class="sxs-lookup"><span data-stu-id="e6b19-2413">drivers license</span></span> 
- <span data-ttu-id="e6b19-2414">driver's license</span><span class="sxs-lookup"><span data-stu-id="e6b19-2414">driver's license</span></span> 
- <span data-ttu-id="e6b19-2415">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="e6b19-2415">drivers licenses</span></span> 
- <span data-ttu-id="e6b19-2416">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="e6b19-2416">driver's licenses</span></span> 
- <span data-ttu-id="e6b19-2417">driving licence
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2417">driving licence</span></span> 
- <span data-ttu-id="e6b19-2418">lic#</span><span class="sxs-lookup"><span data-stu-id="e6b19-2418">lic#</span></span> 
- <span data-ttu-id="e6b19-2419">LIC #</span><span class="sxs-lookup"><span data-stu-id="e6b19-2419">LIC＃</span></span> 
- <span data-ttu-id="e6b19-2420">lics#</span><span class="sxs-lookup"><span data-stu-id="e6b19-2420">lics#</span></span> 
- <span data-ttu-id="e6b19-2421">状态 id</span><span class="sxs-lookup"><span data-stu-id="e6b19-2421">state id</span></span> 
- <span data-ttu-id="e6b19-2422">state identification
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2422">state identification</span></span> 
- <span data-ttu-id="e6b19-2423">state identification number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2423">state identification number</span></span> 
- <span data-ttu-id="e6b19-2424">低所得国＃
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2424">低所得国＃</span></span> 
- <span data-ttu-id="e6b19-2425">免許証</span><span class="sxs-lookup"><span data-stu-id="e6b19-2425">免許証</span></span> 
- <span data-ttu-id="e6b19-2426">状態ID</span><span class="sxs-lookup"><span data-stu-id="e6b19-2426">状態ID</span></span>
- <span data-ttu-id="e6b19-2427">
状態の識別
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2427">状態の識別</span></span> 
- <span data-ttu-id="e6b19-2428">状態の識別番号
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2428">状態の識別番号</span></span> 
- <span data-ttu-id="e6b19-2429">運転免許</span><span class="sxs-lookup"><span data-stu-id="e6b19-2429">運転免許</span></span> 
- <span data-ttu-id="e6b19-2430">運転免許証</span><span class="sxs-lookup"><span data-stu-id="e6b19-2430">運転免許証</span></span> 
- <span data-ttu-id="e6b19-2431">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="e6b19-2431">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="e6b19-2432">日本护照号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-2432">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2433">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2433">Format</span></span>

<span data-ttu-id="e6b19-2434">两个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2434">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2435">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2435">Pattern</span></span>

<span data-ttu-id="e6b19-2436">两个字母（不区分大小写）后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2436">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2437">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2437">Checksum</span></span>

<span data-ttu-id="e6b19-2438">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-2438">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2439">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2439">Definition</span></span>

<span data-ttu-id="e6b19-2440">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2441">函数 Func_jp_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2441">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2442">找到 Keyword_jp_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2442">A keyword from Keyword_jp_passport is found.</span></span>

```
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6b19-2443">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2443">Keywords</span></span>

#### <a name="keywordjppassport"></a><span data-ttu-id="e6b19-2444">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="e6b19-2444">Keyword_jp_passport</span></span>

- <span data-ttu-id="e6b19-2445">パスポート
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2445">パスポート</span></span> 
- <span data-ttu-id="e6b19-2446">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2446">パスポート番号</span></span> 
- <span data-ttu-id="e6b19-2447">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2447">パスポートのNum</span></span> 
- <span data-ttu-id="e6b19-2448">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2448">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="e6b19-2449">日本居民登记号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-2449">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2450">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2450">Format</span></span>

<span data-ttu-id="e6b19-2451">11 个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2451">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2452">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2452">Pattern</span></span>

<span data-ttu-id="e6b19-2453">11 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2453">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2454">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2454">Checksum</span></span>

<span data-ttu-id="e6b19-2455">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-2455">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2456">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2456">Definition</span></span>

<span data-ttu-id="e6b19-2457">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2458">函数 Func_jp_resident_registration_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2458">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2459">找到 Keyword_jp_resident_registration_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2459">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6b19-2460">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2460">Keywords</span></span>

#### <a name="keywordjpresidentregistrationnumber"></a><span data-ttu-id="e6b19-2461">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="e6b19-2461">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="e6b19-2462">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="e6b19-2462">Resident Registration Number</span></span>
- <span data-ttu-id="e6b19-2463">Resident Register Number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2463">Resident Register Number</span></span> 
- <span data-ttu-id="e6b19-2464">Residents Basic Registry Number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2464">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="e6b19-2465">Resident Registration No.
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2465">Resident Registration No.</span></span> 
- <span data-ttu-id="e6b19-2466">Resident Register No.
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2466">Resident Register No.</span></span> 
- <span data-ttu-id="e6b19-2467">Residents Basic Registry No.
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2467">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="e6b19-2468">Basic Resident Register No.
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2468">Basic Resident Register No.</span></span> 
- <span data-ttu-id="e6b19-2469">住民登録番号、登録番号をレジデント
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2469">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="e6b19-2470">住民基本登録番号、登録番号
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2470">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="e6b19-2471">住民基本レジストリ番号を常駐
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2471">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="e6b19-2472">登録番号を常駐住民基本台帳登録番号
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2472">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="e6b19-2473">日本社会保险号码 (SIN)</span><span class="sxs-lookup"><span data-stu-id="e6b19-2473">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2474">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2474">Format</span></span>

<span data-ttu-id="e6b19-2475">7-12 个数字 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2475">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2476">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2476">Pattern</span></span>

<span data-ttu-id="e6b19-2477">7-12 位数字：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2477">7-12 digits:</span></span>
- <span data-ttu-id="e6b19-2478">四位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2478">Four digits</span></span> 
- <span data-ttu-id="e6b19-2479">一个连字符（可选）</span><span class="sxs-lookup"><span data-stu-id="e6b19-2479">A hyphen (optional)</span></span> 
- <span data-ttu-id="e6b19-2480">6 个数字或</span><span class="sxs-lookup"><span data-stu-id="e6b19-2480">Six digits OR</span></span>
- <span data-ttu-id="e6b19-2481">7-12 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2481">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2482">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2482">Checksum</span></span>

<span data-ttu-id="e6b19-2483">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-2483">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2484">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2484">Definition</span></span>

<span data-ttu-id="e6b19-2485">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2485">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2486">函数 Func_jp_sin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2486">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2487">找到 Keyword_jp_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2487">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="e6b19-2488">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2488">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2489">函数 Func_jp_sin_pre_1997 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2489">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2490">找到 Keyword_jp_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2490">A keyword from Keyword_jp_sin is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-2491">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2491">Keywords</span></span>

#### <a name="keywordjpsin"></a><span data-ttu-id="e6b19-2492">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="e6b19-2492">Keyword_jp_sin</span></span>

- <span data-ttu-id="e6b19-2493">Social Insurance No.
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2493">Social Insurance No.</span></span> 
- <span data-ttu-id="e6b19-2494">Social Insurance Num
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2494">Social Insurance Num</span></span> 
- <span data-ttu-id="e6b19-2495">Social Insurance Number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2495">Social Insurance Number</span></span> 
- <span data-ttu-id="e6b19-2496">社会保険のテンキー
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2496">社会保険のテンキー</span></span> 
- <span data-ttu-id="e6b19-2497">社会保険番号
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2497">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="e6b19-2498">日语居住卡号</span><span class="sxs-lookup"><span data-stu-id="e6b19-2498">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2499">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2499">Format</span></span>

<span data-ttu-id="e6b19-2500">12 字母和数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2500">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2501">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2501">Pattern</span></span>

<span data-ttu-id="e6b19-2502">12 字母和数字：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2502">12 letters and digits:</span></span>
- <span data-ttu-id="e6b19-2503">两个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="e6b19-2503">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="e6b19-2504">八个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2504">Eight digits</span></span> 
- <span data-ttu-id="e6b19-2505">两个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="e6b19-2505">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2506">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2506">Checksum</span></span>

<span data-ttu-id="e6b19-2507">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-2507">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2508">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2508">Definition</span></span>

<span data-ttu-id="e6b19-2509">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2509">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2510">正则表达式 Regex_jp_residence_card_number 找到与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2510">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2511">找到从 Keyword_jp_residence_card_number 关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2511">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6b19-2512">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2512">Keywords</span></span>

#### <a name="keywordjpresidencecardnumber"></a><span data-ttu-id="e6b19-2513">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="e6b19-2513">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="e6b19-2514">居住卡号</span><span class="sxs-lookup"><span data-stu-id="e6b19-2514">Residence card number</span></span>
- <span data-ttu-id="e6b19-2515">居住卡片否</span><span class="sxs-lookup"><span data-stu-id="e6b19-2515">Residence card no</span></span>
- <span data-ttu-id="e6b19-2516">居住卡片 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-2516">Residence card #</span></span>
- <span data-ttu-id="e6b19-2517">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="e6b19-2517">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="e6b19-2518">马拉西亚身份证号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-2518">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2519">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2519">Format</span></span>

<span data-ttu-id="e6b19-2520">12 个数字（包含可选连字符）</span><span class="sxs-lookup"><span data-stu-id="e6b19-2520">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2521">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2521">Pattern</span></span>

<span data-ttu-id="e6b19-2522">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2522">12 digits:</span></span>
- <span data-ttu-id="e6b19-2523">六个数字，采用  YYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2523">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="e6b19-2524">一个短划线（可选） </span><span class="sxs-lookup"><span data-stu-id="e6b19-2524">A dash (optional)</span></span> 
- <span data-ttu-id="e6b19-2525">两个字母的出生地代码 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2525">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="e6b19-2526">一个短划线（可选） </span><span class="sxs-lookup"><span data-stu-id="e6b19-2526">A dash (optional)</span></span> 
- <span data-ttu-id="e6b19-2527">三个随机数字 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2527">Three random digits</span></span> 
- <span data-ttu-id="e6b19-2528">一位性别代码</span><span class="sxs-lookup"><span data-stu-id="e6b19-2528">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2529">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2529">Checksum</span></span>

<span data-ttu-id="e6b19-2530">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-2530">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2531">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2531">Definition</span></span>

<span data-ttu-id="e6b19-2532">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2532">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2533">正则表达式 Regex_malaysia_id_card_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2533">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2534">找到 Keyword_malaysia_id_card_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2534">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-2535">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2535">Keywords</span></span>
   
#### <a name="keywordmalaysiaidcardnumber"></a><span data-ttu-id="e6b19-2536">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="e6b19-2536">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="e6b19-2537">数字应用程序卡片</span><span class="sxs-lookup"><span data-stu-id="e6b19-2537">digital application card</span></span>
- <span data-ttu-id="e6b19-2538">我 /c</span><span class="sxs-lookup"><span data-stu-id="e6b19-2538">i/c</span></span>
- <span data-ttu-id="e6b19-2539">我 /c 没有</span><span class="sxs-lookup"><span data-stu-id="e6b19-2539">i/c no</span></span>
- <span data-ttu-id="e6b19-2540">ic</span><span class="sxs-lookup"><span data-stu-id="e6b19-2540">ic</span></span>
- <span data-ttu-id="e6b19-2541">ic 没有</span><span class="sxs-lookup"><span data-stu-id="e6b19-2541">ic no</span></span>
- <span data-ttu-id="e6b19-2542">身份证</span><span class="sxs-lookup"><span data-stu-id="e6b19-2542">id card</span></span>
- <span data-ttu-id="e6b19-2543">身份证</span><span class="sxs-lookup"><span data-stu-id="e6b19-2543">identification Card</span></span>
- <span data-ttu-id="e6b19-2544">identity card</span><span class="sxs-lookup"><span data-stu-id="e6b19-2544">identity card</span></span>
- <span data-ttu-id="e6b19-2545">k/p</span><span class="sxs-lookup"><span data-stu-id="e6b19-2545">k/p</span></span>
- <span data-ttu-id="e6b19-2546">k/p 没有</span><span class="sxs-lookup"><span data-stu-id="e6b19-2546">k/p no</span></span>
- <span data-ttu-id="e6b19-2547">kad akuan diri</span><span class="sxs-lookup"><span data-stu-id="e6b19-2547">kad akuan diri</span></span>
- <span data-ttu-id="e6b19-2548">kad aplikasi 数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2548">kad aplikasi digital</span></span>
- <span data-ttu-id="e6b19-2549">kad pengenalan 马来西亚</span><span class="sxs-lookup"><span data-stu-id="e6b19-2549">kad pengenalan malaysia</span></span>
- <span data-ttu-id="e6b19-2550">kp</span><span class="sxs-lookup"><span data-stu-id="e6b19-2550">kp</span></span>
- <span data-ttu-id="e6b19-2551">kp 没有</span><span class="sxs-lookup"><span data-stu-id="e6b19-2551">kp no</span></span>
- <span data-ttu-id="e6b19-2552">mykad</span><span class="sxs-lookup"><span data-stu-id="e6b19-2552">mykad</span></span>
- <span data-ttu-id="e6b19-2553">mykas</span><span class="sxs-lookup"><span data-stu-id="e6b19-2553">mykas</span></span>
- <span data-ttu-id="e6b19-2554">mykid</span><span class="sxs-lookup"><span data-stu-id="e6b19-2554">mykid</span></span>
- <span data-ttu-id="e6b19-2555">mypr</span><span class="sxs-lookup"><span data-stu-id="e6b19-2555">mypr</span></span>
- <span data-ttu-id="e6b19-2556">mytentera</span><span class="sxs-lookup"><span data-stu-id="e6b19-2556">mytentera</span></span>
- <span data-ttu-id="e6b19-2557">马来西亚身份证</span><span class="sxs-lookup"><span data-stu-id="e6b19-2557">malaysia identity card</span></span>
- <span data-ttu-id="e6b19-2558">马来西亚身份证</span><span class="sxs-lookup"><span data-stu-id="e6b19-2558">malaysian identity card</span></span>
- <span data-ttu-id="e6b19-2559">nric</span><span class="sxs-lookup"><span data-stu-id="e6b19-2559">nric</span></span>
- <span data-ttu-id="e6b19-2560">个人标识卡</span><span class="sxs-lookup"><span data-stu-id="e6b19-2560">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="e6b19-2561">荷兰公民服务 (BSN) 号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-2561">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2562">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2562">Format</span></span>

<span data-ttu-id="e6b19-2563">8-9 个数字（包含可选空格）</span><span class="sxs-lookup"><span data-stu-id="e6b19-2563">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2564">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2564">Pattern</span></span>

<span data-ttu-id="e6b19-2565">8-9 个数字：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2565">8-9 digits:</span></span>
- <span data-ttu-id="e6b19-2566">三个数字 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2566">Three digits</span></span> 
- <span data-ttu-id="e6b19-2567">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="e6b19-2567">A space (optional)</span></span> 
- <span data-ttu-id="e6b19-2568">三个数字 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2568">Three digits</span></span> 
- <span data-ttu-id="e6b19-2569">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="e6b19-2569">A space (optional)</span></span> 
- <span data-ttu-id="e6b19-2570">2-3 个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2570">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2571">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2571">Checksum</span></span>

<span data-ttu-id="e6b19-2572">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-2572">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2573">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2573">Definition</span></span>

<span data-ttu-id="e6b19-2574">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2574">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2575">函数 Func_netherlands_bsn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2575">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2576">找到 Keyword_netherlands_bsn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2576">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="e6b19-2577">函数 Func_eu_date2 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2577">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="e6b19-2578">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2578">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-2579">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2579">Keywords</span></span>

#### <a name="keywordnetherlandsbsn"></a><span data-ttu-id="e6b19-2580">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="e6b19-2580">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="e6b19-2581">Citizen service number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2581">Citizen service number</span></span> 
- <span data-ttu-id="e6b19-2582">BSN

</span><span class="sxs-lookup"><span data-stu-id="e6b19-2582">BSN</span></span> 
- <span data-ttu-id="e6b19-2583">Burgerservicenummer
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2583">Burgerservicenummer</span></span> 
- <span data-ttu-id="e6b19-2584">Sofinummer
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2584">Sofinummer</span></span> 
- <span data-ttu-id="e6b19-2585">Persoonsgebonden nummer
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2585">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="e6b19-2586">Persoonsnummer
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2586">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="e6b19-2587">新西兰卫生部号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-2587">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2588">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2588">Format</span></span>

<span data-ttu-id="e6b19-2589">三个字母、一个空格（可选）以及四个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2589">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2590">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2590">Pattern</span></span>

<span data-ttu-id="e6b19-2591">三个字母 （不区分大小写） 空间 （可选） 四位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2591">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2592">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2592">Checksum</span></span>

<span data-ttu-id="e6b19-2593">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-2593">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2594">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2594">Definition</span></span>

<span data-ttu-id="e6b19-2595">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2595">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2596">函数 Func_new_zealand_ministry_of_health_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2596">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2597">找到 Keyword_nz_terms 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2597">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="e6b19-2598">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2598">The checksum passes.</span></span>

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

<span data-ttu-id="e6b19-2599">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2599">Keywords</span></span>

<span data-ttu-id="e6b19-2600">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="e6b19-2600">Keyword_nz_terms</span></span>

- <span data-ttu-id="e6b19-2601">NHI
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2601">NHI</span></span> 
- <span data-ttu-id="e6b19-2602">新西兰</span><span class="sxs-lookup"><span data-stu-id="e6b19-2602">New Zealand</span></span> 
- <span data-ttu-id="e6b19-2603">运行状况</span><span class="sxs-lookup"><span data-stu-id="e6b19-2603">Health</span></span> 
- <span data-ttu-id="e6b19-2604">treatment
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2604">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="e6b19-2605">挪威身份证号</span><span class="sxs-lookup"><span data-stu-id="e6b19-2605">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2606">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2606">Format</span></span>

<span data-ttu-id="e6b19-2607">11 个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2607">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2608">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2608">Pattern</span></span>

<span data-ttu-id="e6b19-2609">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2609">11 digits:</span></span>
- <span data-ttu-id="e6b19-2610">六个数字，采用  DDMMYY 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2610">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="e6b19-2611">三位个人号码 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2611">Three-digit individual number</span></span> 
- <span data-ttu-id="e6b19-2612">两个校验位</span><span class="sxs-lookup"><span data-stu-id="e6b19-2612">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2613">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2613">Checksum</span></span>

<span data-ttu-id="e6b19-2614">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-2614">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2615">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2615">Definition</span></span>

<span data-ttu-id="e6b19-2616">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2616">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2617">函数 Func_norway_id_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2617">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2618">找到 Keyword_norway_id_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2618">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="e6b19-2619">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2619">The checksum passes.</span></span>
- <span data-ttu-id="e6b19-2620">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2620">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2621">函数 Func_norway_id_numbe 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2621">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2622">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2622">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-2623">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2623">Keywords</span></span>

#### <a name="keywordnorwayidnumber"></a><span data-ttu-id="e6b19-2624">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="e6b19-2624">Keyword_norway_id_number</span></span>

- <span data-ttu-id="e6b19-2625">Personal identification number</span><span class="sxs-lookup"><span data-stu-id="e6b19-2625">Personal identification number</span></span>
- <span data-ttu-id="e6b19-2626">Norwegian ID Number</span><span class="sxs-lookup"><span data-stu-id="e6b19-2626">Norwegian ID Number</span></span>
- <span data-ttu-id="e6b19-2627">ID Number</span><span class="sxs-lookup"><span data-stu-id="e6b19-2627">ID Number</span></span>
- <span data-ttu-id="e6b19-2628">Identification</span><span class="sxs-lookup"><span data-stu-id="e6b19-2628">Identification</span></span>
- <span data-ttu-id="e6b19-2629">Personnummer</span><span class="sxs-lookup"><span data-stu-id="e6b19-2629">Personnummer</span></span>
- <span data-ttu-id="e6b19-2630">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="e6b19-2630">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="e6b19-2631">菲律宾统一多用途身份证号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-2631">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2632">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2632">Format</span></span>

<span data-ttu-id="e6b19-2633">12 个数字，通过连字符分隔 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2633">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2634">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2634">Pattern</span></span>

<span data-ttu-id="e6b19-2635">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2635">12 digits:</span></span>
- <span data-ttu-id="e6b19-2636">四个数字 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2636">Four digits</span></span> 
- <span data-ttu-id="e6b19-2637">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2637">A hyphen</span></span> 
- <span data-ttu-id="e6b19-2638">七个数字 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2638">Seven digits</span></span> 
- <span data-ttu-id="e6b19-2639">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2639">A hyphen</span></span> 
- <span data-ttu-id="e6b19-2640">一个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2640">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2641">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2641">Checksum</span></span>

<span data-ttu-id="e6b19-2642">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-2642">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2643">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2643">Definition</span></span>

<span data-ttu-id="e6b19-2644">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2644">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2645">正则表达式 Regex_philippines_unified_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2645">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2646">找到 Keyword_philippines_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2646">A keyword from Keyword_philippines_id is found.</span></span>

```
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6b19-2647">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2647">Keywords</span></span>
   
#### <a name="keywordphilippinesid"></a><span data-ttu-id="e6b19-2648">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="e6b19-2648">Keyword_philippines_id</span></span>

- <span data-ttu-id="e6b19-2649">Unified Multi-Purpose ID
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2649">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="e6b19-2650">UMID
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2650">UMID</span></span> 
- <span data-ttu-id="e6b19-2651">Identity Card</span><span class="sxs-lookup"><span data-stu-id="e6b19-2651">Identity Card</span></span> 
- <span data-ttu-id="e6b19-2652">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="e6b19-2652">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="e6b19-2653">波兰身份证</span><span class="sxs-lookup"><span data-stu-id="e6b19-2653">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2654">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2654">Format</span></span>

<span data-ttu-id="e6b19-2655">三个字母和六个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2655">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2656">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2656">Pattern</span></span>

<span data-ttu-id="e6b19-2657">三个字母（不区分大小写）后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2657">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2658">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2658">Checksum</span></span>

<span data-ttu-id="e6b19-2659">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-2659">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2660">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2660">Definition</span></span>

<span data-ttu-id="e6b19-p138">DLP 策略是相信它已检测到此类型的敏感信息的 75 %if、 内 300 个字符的邻近度： 函数 Func_polish_national_id 查找与模式匹配的内容。找到从 Keyword_polish_national_id_passport_number 关键字。将传递校验和。</span><span class="sxs-lookup"><span data-stu-id="e6b19-p138">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern. A keyword from Keyword_polish_national_id_passport_number is found. The checksum passes.</span></span>

```
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6b19-2664">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2664">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="e6b19-2665">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="e6b19-2665">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="e6b19-2666">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="e6b19-2666">Dowód osobisty</span></span>
- <span data-ttu-id="e6b19-2667">个数 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="e6b19-2667">Numer dowodu osobistego</span></span>
- <span data-ttu-id="e6b19-2668">Nazwa 我个数 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="e6b19-2668">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="e6b19-2669">Nazwa 我 nr dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="e6b19-2669">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="e6b19-2670">Nazwa i nr dowodu tożsamości
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2670">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="e6b19-2671">Dowód Tożsamości
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2671">Dowód Tożsamości</span></span>
- <span data-ttu-id="e6b19-p139">dow. os.
</span><span class="sxs-lookup"><span data-stu-id="e6b19-p139">dow. os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="e6b19-2674">波兰国家/地区 ID (PESEL)</span><span class="sxs-lookup"><span data-stu-id="e6b19-2674">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2675">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2675">Format</span></span>

<span data-ttu-id="e6b19-2676">11 个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2676">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2677">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2677">Pattern</span></span>

<span data-ttu-id="e6b19-2678">11 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2678">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2679">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2679">Checksum</span></span>

<span data-ttu-id="e6b19-2680">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-2680">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2681">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2681">Definition</span></span>

<span data-ttu-id="e6b19-2682">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2682">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2683">函数 Func_pesel_identification_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2683">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2684">找到 Keyword_pesel_identification_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2684">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="e6b19-2685">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2685">The checksum passes.</span></span>

```
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6b19-2686">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2686">Keywords</span></span>

#### <a name="keywordpeselidentificationnumber"></a><span data-ttu-id="e6b19-2687">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="e6b19-2687">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="e6b19-2688">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="e6b19-2688">Nr PESEL</span></span>
- <span data-ttu-id="e6b19-2689">PESEL</span><span class="sxs-lookup"><span data-stu-id="e6b19-2689">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="e6b19-2690">波兰护照</span><span class="sxs-lookup"><span data-stu-id="e6b19-2690">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2691">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2691">Format</span></span>

<span data-ttu-id="e6b19-2692">两个字母和七个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2692">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2693">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2693">Pattern</span></span>

<span data-ttu-id="e6b19-2694">两个字母（不区分大小写）后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2694">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2695">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2695">Checksum</span></span>

<span data-ttu-id="e6b19-2696">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-2696">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2697">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2697">Definition</span></span>

<span data-ttu-id="e6b19-2698">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2698">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2699">函数 Func_polish_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2699">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2700">找到 Keyword_polish_national_id_passport_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2700">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="e6b19-2701">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2701">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-2702">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2702">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="e6b19-2703">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="e6b19-2703">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="e6b19-2704">个数 paszportu</span><span class="sxs-lookup"><span data-stu-id="e6b19-2704">Numer paszportu</span></span>
- <span data-ttu-id="e6b19-p140">Paszportu nr。</span><span class="sxs-lookup"><span data-stu-id="e6b19-p140">Nr. Paszportu</span></span>
- <span data-ttu-id="e6b19-2707">Paszport</span><span class="sxs-lookup"><span data-stu-id="e6b19-2707">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="e6b19-2708">葡萄牙公民身份证号</span><span class="sxs-lookup"><span data-stu-id="e6b19-2708">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2709">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2709">Format</span></span>

<span data-ttu-id="e6b19-2710">八个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2710">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2711">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2711">Pattern</span></span>

<span data-ttu-id="e6b19-2712">八个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2712">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2713">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2713">Checksum</span></span>

<span data-ttu-id="e6b19-2714">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-2714">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2715">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2715">Definition</span></span>

<span data-ttu-id="e6b19-2716">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2716">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2717">正则表达式 Regex_portugal_citizen_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2717">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2718">找到 Keyword_portugal_citizen_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2718">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6b19-2719">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2719">Keywords</span></span>

#### <a name="keywordportugalcitizencard"></a><span data-ttu-id="e6b19-2720">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="e6b19-2720">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="e6b19-2721">Citizen Card</span><span class="sxs-lookup"><span data-stu-id="e6b19-2721">Citizen Card</span></span>
- <span data-ttu-id="e6b19-2722">National ID Card</span><span class="sxs-lookup"><span data-stu-id="e6b19-2722">National ID Card</span></span>
- <span data-ttu-id="e6b19-2723">CC</span><span class="sxs-lookup"><span data-stu-id="e6b19-2723">CC</span></span>
- <span data-ttu-id="e6b19-2724">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="e6b19-2724">Cartão de Cidadão</span></span>
- <span data-ttu-id="e6b19-2725">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="e6b19-2725">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="e6b19-2726">沙特阿拉伯国家 ID</span><span class="sxs-lookup"><span data-stu-id="e6b19-2726">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2727">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2727">Format</span></span>

<span data-ttu-id="e6b19-2728">10 个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2728">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2729">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2729">Pattern</span></span>

<span data-ttu-id="e6b19-2730">10 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2730">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2731">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2731">Checksum</span></span>

<span data-ttu-id="e6b19-2732">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-2732">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2733">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2733">Definition</span></span>

<span data-ttu-id="e6b19-2734">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2734">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2735">正则表达式 Regex_saudi_arabia_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2735">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2736">找到 Keyword_saudi_arabia_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2736">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-2737">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2737">Keywords</span></span>

#### <a name="keywordsaudiarabianationalid"></a><span data-ttu-id="e6b19-2738">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="e6b19-2738">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="e6b19-2739">Identification Card
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2739">Identification Card</span></span> 
- <span data-ttu-id="e6b19-2740">I card number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2740">I card number</span></span> 
- <span data-ttu-id="e6b19-2741">ID 号</span><span class="sxs-lookup"><span data-stu-id="e6b19-2741">ID number</span></span> 
- <span data-ttu-id="e6b19-2742">الوطنية الهوية بطاقة رقم
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2742">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="e6b19-2743">新加坡国家登记身份证 (NRIC) 号</span><span class="sxs-lookup"><span data-stu-id="e6b19-2743">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2744">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2744">Format</span></span>

<span data-ttu-id="e6b19-2745">九个字母和数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2745">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2746">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2746">Pattern</span></span>

- <span data-ttu-id="e6b19-2747">九个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2747">Nine letters and digits:</span></span>
- <span data-ttu-id="e6b19-2748">字母“F”、“G”、“S”或“T”（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="e6b19-2748">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="e6b19-2749">七个数字 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2749">Seven digits</span></span> 
- <span data-ttu-id="e6b19-2750">一个字母校验位</span><span class="sxs-lookup"><span data-stu-id="e6b19-2750">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2751">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2751">Checksum</span></span>

<span data-ttu-id="e6b19-2752">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-2752">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2753">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2753">Definition</span></span>

<span data-ttu-id="e6b19-2754">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2754">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2755">正则表达式 Regex_singapore_nric 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2755">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2756">找到 Keyword_singapore_nric 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2756">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="e6b19-2757">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2757">The checksum passes.</span></span>

<span data-ttu-id="e6b19-2758">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2758">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2759">正则表达式 Regex_singapore_nric 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2759">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2760">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2760">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-2761">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2761">Keywords</span></span>
   
#### <a name="keywordsingaporenric"></a><span data-ttu-id="e6b19-2762">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="e6b19-2762">Keyword_singapore_nric</span></span>

- <span data-ttu-id="e6b19-2763">National Registration Identity Card
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2763">National Registration Identity Card</span></span> 
- <span data-ttu-id="e6b19-2764">Identity Card Number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2764">Identity Card Number</span></span> 
- <span data-ttu-id="e6b19-2765">NRIC
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2765">NRIC</span></span> 
- <span data-ttu-id="e6b19-2766">IC
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2766">IC</span></span> 
- <span data-ttu-id="e6b19-2767">Foreign Identification Number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2767">Foreign Identification Number</span></span> 
- <span data-ttu-id="e6b19-2768">FIN
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2768">FIN</span></span> 
- <span data-ttu-id="e6b19-2769">身份证 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2769">身份证</span></span> 
- <span data-ttu-id="e6b19-2770">身份證
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2770">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="e6b19-2771">南非身份证号</span><span class="sxs-lookup"><span data-stu-id="e6b19-2771">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2772">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2772">Format</span></span>

<span data-ttu-id="e6b19-2773">13 个数字（可能包含空格）</span><span class="sxs-lookup"><span data-stu-id="e6b19-2773">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2774">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2774">Pattern</span></span>

<span data-ttu-id="e6b19-2775">13 个数字：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2775">13 digits:</span></span>
- <span data-ttu-id="e6b19-2776">六个数字，采用  YYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2776">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="e6b19-2777">四个数字 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2777">Four digits</span></span> 
- <span data-ttu-id="e6b19-2778">一位公民指示码 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2778">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="e6b19-2779">数字“8”或“9” </span><span class="sxs-lookup"><span data-stu-id="e6b19-2779">The digit "8" or "9"</span></span> 
- <span data-ttu-id="e6b19-2780">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="e6b19-2780">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2781">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2781">Checksum</span></span>

<span data-ttu-id="e6b19-2782">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-2782">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2783">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2783">Definition</span></span>

<span data-ttu-id="e6b19-2784">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2784">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2785">函数 Func_south_africa_identification_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2785">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2786">找到 Keyword_south_africa_identification_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2786">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="e6b19-2787">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2787">The checksum passes.</span></span>

```
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6b19-2788">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2788">Keywords</span></span>
   
#### <a name="keywordsouthafricaidentificationnumber"></a><span data-ttu-id="e6b19-2789">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="e6b19-2789">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="e6b19-2790">Identity card</span><span class="sxs-lookup"><span data-stu-id="e6b19-2790">Identity card</span></span>
- <span data-ttu-id="e6b19-2791">ID</span><span class="sxs-lookup"><span data-stu-id="e6b19-2791">ID</span></span>
- <span data-ttu-id="e6b19-2792">Identification</span><span class="sxs-lookup"><span data-stu-id="e6b19-2792">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="e6b19-2793">韩国居民注册号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-2793">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2794">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2794">Format</span></span>

<span data-ttu-id="e6b19-2795">13 个数字（包含连字符）</span><span class="sxs-lookup"><span data-stu-id="e6b19-2795">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2796">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2796">Pattern</span></span>

<span data-ttu-id="e6b19-2797">13 个数字：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2797">13 digits:</span></span>
- <span data-ttu-id="e6b19-2798">六个数字，采用  YYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2798">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="e6b19-2799">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2799">A hyphen</span></span> 
- <span data-ttu-id="e6b19-2800">一个数字，由世纪和性别 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2800">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="e6b19-2801">四位数字的出生地区代码 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2801">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="e6b19-2802">一个数字，用于区分前面数字均相同的人 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2802">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="e6b19-2803">一个校验位。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2803">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2804">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2804">Checksum</span></span>

<span data-ttu-id="e6b19-2805">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-2805">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2806">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2806">Definition</span></span>

<span data-ttu-id="e6b19-2807">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2807">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2808">函数 Func_south_korea_resident_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2808">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2809">找到 Keyword_south_korea_resident_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2809">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="e6b19-2810">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2810">The checksum passes.</span></span>

<span data-ttu-id="e6b19-2811">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2811">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2812">函数 Func_south_korea_resident_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2812">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2813">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2813">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-2814">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2814">Keywords</span></span>
   
#### <a name="keywordsouthkorearesidentnumber"></a><span data-ttu-id="e6b19-2815">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="e6b19-2815">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="e6b19-2816">National ID card
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2816">National ID card</span></span> 
- <span data-ttu-id="e6b19-2817">Citizen's Registration Number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2817">Citizen's Registration Number</span></span> 
- <span data-ttu-id="e6b19-2818">Jumin deungnok beonho
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2818">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="e6b19-2819">RRN
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2819">RRN</span></span> 
- <span data-ttu-id="e6b19-2820">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="e6b19-2820">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="e6b19-2821">西班牙社会保险号码 (SSN)</span><span class="sxs-lookup"><span data-stu-id="e6b19-2821">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2822">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2822">Format</span></span>

<span data-ttu-id="e6b19-2823">11-12 个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2823">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2824">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2824">Pattern</span></span>

<span data-ttu-id="e6b19-2825">11-12 数字：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2825">11-12 digits:</span></span>
- <span data-ttu-id="e6b19-2826">两位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2826">Two digits</span></span> 
- <span data-ttu-id="e6b19-2827">正斜杠（可选）</span><span class="sxs-lookup"><span data-stu-id="e6b19-2827">A forward slash (optional)</span></span> 
- <span data-ttu-id="e6b19-2828">7-8 位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2828">7-8 digits</span></span> 
- <span data-ttu-id="e6b19-2829">正斜杠（可选）</span><span class="sxs-lookup"><span data-stu-id="e6b19-2829">A forward slash (optional)</span></span> 
- <span data-ttu-id="e6b19-2830">两位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2830">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2831">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2831">Checksum</span></span>

<span data-ttu-id="e6b19-2832">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-2832">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2833">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2833">Definition</span></span>

<span data-ttu-id="e6b19-2834">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2834">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2835">函数 Func_spanish_social_security_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2835">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2836">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2836">The checksum passes.</span></span>

```
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6b19-2837">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2837">Keywords</span></span>

<span data-ttu-id="e6b19-2838">无</span><span class="sxs-lookup"><span data-stu-id="e6b19-2838">None</span></span>
   
## <a name="sweden-national-id"></a><span data-ttu-id="e6b19-2839">瑞典国家 ID</span><span class="sxs-lookup"><span data-stu-id="e6b19-2839">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2840">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2840">Format</span></span>

<span data-ttu-id="e6b19-2841">10 个或 12 个数字和一个可选分隔符</span><span class="sxs-lookup"><span data-stu-id="e6b19-2841">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2842">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2842">Pattern</span></span>

<span data-ttu-id="e6b19-2843">10 或 12 位数字和可选的分隔符：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2843">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="e6b19-2844">2-4 位数字（可选）</span><span class="sxs-lookup"><span data-stu-id="e6b19-2844">2-4 digits (optional)</span></span> 
- <span data-ttu-id="e6b19-2845">采用日期格式 YYMMDD 的六位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2845">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="e6b19-2846">“-”或“+”（可选）的分隔符，加</span><span class="sxs-lookup"><span data-stu-id="e6b19-2846">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="e6b19-2847">四位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2847">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2848">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2848">Checksum</span></span>

<span data-ttu-id="e6b19-2849">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-2849">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2850">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2850">Definition</span></span>

<span data-ttu-id="e6b19-2851">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2851">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2852">函数 Func_swedish_national_identifier 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2852">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2853">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2853">The checksum passes.</span></span>

```
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6b19-2854">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2854">Keywords</span></span>

<span data-ttu-id="e6b19-2855">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-2855">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="e6b19-2856">瑞典护照号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-2856">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2857">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2857">Format</span></span>

<span data-ttu-id="e6b19-2858">八个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2858">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2859">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2859">Pattern</span></span>

<span data-ttu-id="e6b19-2860">八个连续的数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2860">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2861">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2861">Checksum</span></span>

<span data-ttu-id="e6b19-2862">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-2862">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2863">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2863">Definition</span></span>

<span data-ttu-id="e6b19-2864">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2864">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2865">正则表达式 Regex_sweden_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2865">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2866">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2866">One of the following is true:</span></span>
    - <span data-ttu-id="e6b19-2867">找到 Keyword_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2867">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="e6b19-2868">找到 Keyword_sweden_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2868">A keyword from Keyword_sweden_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-2869">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2869">Keywords</span></span>
   
#### <a name="keywordswedenpassport"></a><span data-ttu-id="e6b19-2870">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="e6b19-2870">Keyword_sweden_passport</span></span>

- <span data-ttu-id="e6b19-2871">visa requirements
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2871">visa requirements</span></span> 
- <span data-ttu-id="e6b19-2872">Alien Registration Card
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2872">Alien Registration Card</span></span> 
- <span data-ttu-id="e6b19-2873">Schengen visas
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2873">Schengen visas</span></span> 
- <span data-ttu-id="e6b19-2874">Schengen visa
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2874">Schengen visa</span></span> 
- <span data-ttu-id="e6b19-2875">Visa Processing
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2875">Visa Processing</span></span> 
- <span data-ttu-id="e6b19-2876">Visa Type
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2876">Visa Type</span></span> 
- <span data-ttu-id="e6b19-2877">Single Entry
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2877">Single Entry</span></span> 
- <span data-ttu-id="e6b19-2878">Multiple Entry
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2878">Multiple Entry</span></span> 
- <span data-ttu-id="e6b19-2879">G3 Processing Fees

</span><span class="sxs-lookup"><span data-stu-id="e6b19-2879">G3 Processing Fees</span></span> 

#### <a name="keywordpassport"></a><span data-ttu-id="e6b19-2880">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="e6b19-2880">Keyword_passport</span></span>

- <span data-ttu-id="e6b19-2881">Passport Number</span><span class="sxs-lookup"><span data-stu-id="e6b19-2881">Passport Number</span></span> 
- <span data-ttu-id="e6b19-2882">
Passport No</span><span class="sxs-lookup"><span data-stu-id="e6b19-2882">Passport No</span></span> 
- <span data-ttu-id="e6b19-2883">Passport #
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2883">Passport #</span></span> 
- <span data-ttu-id="e6b19-2884">Passport#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2884">Passport#</span></span> 
- <span data-ttu-id="e6b19-2885">PassportID</span><span class="sxs-lookup"><span data-stu-id="e6b19-2885">PassportID</span></span> 
- <span data-ttu-id="e6b19-2886">Passportno
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2886">Passportno</span></span> 
- <span data-ttu-id="e6b19-2887">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2887">passportnumber</span></span> 
- <span data-ttu-id="e6b19-2888">パスポート</span><span class="sxs-lookup"><span data-stu-id="e6b19-2888">パスポート</span></span> 
- <span data-ttu-id="e6b19-2889">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2889">パスポート番号</span></span> 
- <span data-ttu-id="e6b19-2890">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2890">パスポートのNum</span></span> 
- <span data-ttu-id="e6b19-2891">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2891">パスポート＃</span></span> 
- <span data-ttu-id="e6b19-2892">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="e6b19-2892">Numéro de passeport</span></span> 
- <span data-ttu-id="e6b19-2893">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="e6b19-2893">Passeport n °</span></span> 
- <span data-ttu-id="e6b19-2894">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2894">Passeport Non</span></span> 
- <span data-ttu-id="e6b19-2895">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2895">Passeport #</span></span> 
- <span data-ttu-id="e6b19-2896">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2896">Passeport#</span></span> 
- <span data-ttu-id="e6b19-2897">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="e6b19-2897">PasseportNon</span></span> 
- <span data-ttu-id="e6b19-2898">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2898">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="e6b19-2899">SWIFT 代码</span><span class="sxs-lookup"><span data-stu-id="e6b19-2899">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2900">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2900">Format</span></span>

<span data-ttu-id="e6b19-2901">四个字母后跟 5-31 个字母或数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2901">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2902">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2902">Pattern</span></span>

<span data-ttu-id="e6b19-2903">四个字母后跟 5-31 个字母或数字：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2903">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="e6b19-2904">四个字母的银行代码（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="e6b19-2904">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="e6b19-2905">可选空格</span><span class="sxs-lookup"><span data-stu-id="e6b19-2905">An optional space</span></span> 
- <span data-ttu-id="e6b19-2906">4-28 个字母或数字（基本银行账号 (BBAN)）</span><span class="sxs-lookup"><span data-stu-id="e6b19-2906">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="e6b19-2907">可选空格</span><span class="sxs-lookup"><span data-stu-id="e6b19-2907">An optional space</span></span> 
- <span data-ttu-id="e6b19-2908">1-3 个字母或数字（BBAN 的剩余内容）</span><span class="sxs-lookup"><span data-stu-id="e6b19-2908">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2909">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2909">Checksum</span></span>

<span data-ttu-id="e6b19-2910">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-2910">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2911">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2911">Definition</span></span>

<span data-ttu-id="e6b19-2912">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2912">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2913">正则表达式 Regex_swift 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2913">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2914">找到 Keyword_swift 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2914">A keyword from Keyword_swift is found.</span></span>

```
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6b19-2915">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2915">Keywords</span></span>
   
#### <a name="keywordswift"></a><span data-ttu-id="e6b19-2916">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="e6b19-2916">Keyword_swift</span></span>

- <span data-ttu-id="e6b19-2917">international organization for standardization 9362
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2917">international organization for standardization 9362</span></span> 
- <span data-ttu-id="e6b19-2918">iso 9362
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2918">iso 9362</span></span> 
- <span data-ttu-id="e6b19-2919">iso9362</span><span class="sxs-lookup"><span data-stu-id="e6b19-2919">iso9362</span></span> 
- <span data-ttu-id="e6b19-2920">swift\#</span><span class="sxs-lookup"><span data-stu-id="e6b19-2920">swift\#</span></span> 
- <span data-ttu-id="e6b19-2921">swiftcode
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2921">swiftcode</span></span> 
- <span data-ttu-id="e6b19-2922">swiftnumber
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2922">swiftnumber</span></span> 
- <span data-ttu-id="e6b19-2923">swiftroutingnumber
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2923">swiftroutingnumber</span></span> 
- <span data-ttu-id="e6b19-2924">swift 代码</span><span class="sxs-lookup"><span data-stu-id="e6b19-2924">swift code</span></span> 
- <span data-ttu-id="e6b19-2925">swift number #
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2925">swift number #</span></span> 
- <span data-ttu-id="e6b19-2926">swift routing number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2926">swift routing number</span></span> 
- <span data-ttu-id="e6b19-2927">bic number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2927">bic number</span></span> 
- <span data-ttu-id="e6b19-2928">bic code
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2928">bic code</span></span> 
- <span data-ttu-id="e6b19-2929">bic\#</span><span class="sxs-lookup"><span data-stu-id="e6b19-2929">bic \#</span></span> 
- <span data-ttu-id="e6b19-2930">bic\#</span><span class="sxs-lookup"><span data-stu-id="e6b19-2930">bic\#</span></span> 
- <span data-ttu-id="e6b19-2931">bank identifier code
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2931">bank identifier code</span></span> 
- <span data-ttu-id="e6b19-2932">標準化9362</span><span class="sxs-lookup"><span data-stu-id="e6b19-2932">標準化9362</span></span> 
- <span data-ttu-id="e6b19-2933">迅速＃
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2933">迅速＃</span></span> 
- <span data-ttu-id="e6b19-2934">SWIFTコード
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2934">SWIFTコード</span></span> 
- <span data-ttu-id="e6b19-2935">SWIFT番号
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2935">SWIFT番号</span></span> 
- <span data-ttu-id="e6b19-2936">迅速なルーティング番号
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2936">迅速なルーティング番号</span></span> 
- <span data-ttu-id="e6b19-2937">BIC番号
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2937">BIC番号</span></span> 
- <span data-ttu-id="e6b19-2938">BICコード
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2938">BICコード</span></span> 
- <span data-ttu-id="e6b19-2939">銀行識別コードのための国際組織
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2939">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="e6b19-2940">Organisation internationale de normalisation 9362
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2940">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="e6b19-2941">rapide\#</span><span class="sxs-lookup"><span data-stu-id="e6b19-2941">rapide \#</span></span> 
- <span data-ttu-id="e6b19-2942">code SWIFT
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2942">code SWIFT</span></span> 
- <span data-ttu-id="e6b19-2943">le numéro de swift
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2943">le numéro de swift</span></span> 
- <span data-ttu-id="e6b19-2944">swift numéro d'acheminement
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2944">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="e6b19-2945">le numéro BIC
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2945">le numéro BIC</span></span> 
- <span data-ttu-id="e6b19-2946">\#BIC</span><span class="sxs-lookup"><span data-stu-id="e6b19-2946">\# BIC</span></span> 
- <span data-ttu-id="e6b19-2947">code identificateur de banque
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2947">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="e6b19-2948">台湾国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="e6b19-2948">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2949">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2949">Format</span></span>

<span data-ttu-id="e6b19-2950">一个字母后跟九个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2950">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2951">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2951">Pattern</span></span>

<span data-ttu-id="e6b19-2952">一个字母后跟 9 位数字：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2952">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="e6b19-2953">一个字母（英文，不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="e6b19-2953">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="e6b19-2954">数字“1”或“2”</span><span class="sxs-lookup"><span data-stu-id="e6b19-2954">The digit "1" or "2"</span></span> 
- <span data-ttu-id="e6b19-2955">八个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2955">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2956">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2956">Checksum</span></span>

<span data-ttu-id="e6b19-2957">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-2957">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2958">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2958">Definition</span></span>

<span data-ttu-id="e6b19-2959">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2959">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2960">函数 Func_taiwanese_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2960">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2961">找到 Keyword_taiwanese_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2961">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="e6b19-2962">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2962">The checksum passes.</span></span>

```
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6b19-2963">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2963">Keywords</span></span>

#### <a name="keywordtaiwanesenationalid"></a><span data-ttu-id="e6b19-2964">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="e6b19-2964">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="e6b19-2965">身份證字號
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2965">身份證字號</span></span> 
- <span data-ttu-id="e6b19-2966">身份證
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2966">身份證</span></span> 
- <span data-ttu-id="e6b19-2967">身份證號碼
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2967">身份證號碼</span></span> 
- <span data-ttu-id="e6b19-2968">身份證號
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2968">身份證號</span></span> 
- <span data-ttu-id="e6b19-2969">身分證字號
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2969">身分證字號</span></span> 
- <span data-ttu-id="e6b19-2970">身分證 </span><span class="sxs-lookup"><span data-stu-id="e6b19-2970">身分證</span></span> 
- <span data-ttu-id="e6b19-2971">身分證號碼
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2971">身分證號碼</span></span> 
- <span data-ttu-id="e6b19-2972">身份證號
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2972">身份證號</span></span> 
- <span data-ttu-id="e6b19-2973">身分證統一編號
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2973">身分證統一編號</span></span> 
- <span data-ttu-id="e6b19-2974">國民身分證統一編號
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2974">國民身分證統一編號</span></span> 
- <span data-ttu-id="e6b19-2975">簽名
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2975">簽名</span></span> 
- <span data-ttu-id="e6b19-2976">蓋章
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2976">蓋章</span></span> 
- <span data-ttu-id="e6b19-2977">簽名或蓋章

</span><span class="sxs-lookup"><span data-stu-id="e6b19-2977">簽名或蓋章</span></span> 
- <span data-ttu-id="e6b19-2978">簽章</span><span class="sxs-lookup"><span data-stu-id="e6b19-2978">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="e6b19-2979">	台湾护照号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-2979">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-2980">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2980">Format</span></span>

- <span data-ttu-id="e6b19-2981">生物护照号码： 九个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2981">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="e6b19-2982">非生物护照号码： 九个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2982">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-2983">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-2983">Pattern</span></span>
<span data-ttu-id="e6b19-2984">生物护照号码：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2984">Biometric passport number:</span></span>
- <span data-ttu-id="e6b19-2985">数字“3” </span><span class="sxs-lookup"><span data-stu-id="e6b19-2985">The digit "3"</span></span> 
- <span data-ttu-id="e6b19-2986">八个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2986">Eight digits</span></span>

<span data-ttu-id="e6b19-2987">非生物护照号码：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2987">Non-biometric passport number:</span></span>
- <span data-ttu-id="e6b19-2988">九个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2988">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-2989">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-2989">Checksum</span></span>

<span data-ttu-id="e6b19-2990">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-2990">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-2991">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-2991">Definition</span></span>

<span data-ttu-id="e6b19-2992">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-2992">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-2993">正则表达式 Regex_taiwan_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2993">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-2994">找到 Keyword_taiwan_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-2994">A keyword from Keyword_taiwan_passport is found.</span></span>

```
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6b19-2995">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-2995">Keywords</span></span>

#### <a name="keywordtaiwanpassport"></a><span data-ttu-id="e6b19-2996">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="e6b19-2996">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="e6b19-2997">台湾 passport number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-2997">ROC passport number</span></span> 
- <span data-ttu-id="e6b19-2998">护照号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-2998">Passport number</span></span> 
- <span data-ttu-id="e6b19-2999">Passport 没有</span><span class="sxs-lookup"><span data-stu-id="e6b19-2999">Passport no</span></span> 
- <span data-ttu-id="e6b19-3000">Passport Num
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3000">Passport Num</span></span> 
- <span data-ttu-id="e6b19-3001">Passport #
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3001">Passport #</span></span> 
- <span data-ttu-id="e6b19-3002">护照
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3002">护照</span></span> 
- <span data-ttu-id="e6b19-3003">中華民國護照
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3003">中華民國護照</span></span> 
- <span data-ttu-id="e6b19-3004">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="e6b19-3004">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="e6b19-3005">台湾居民证 (ARC/TARC) 号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-3005">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-3006">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-3006">Format</span></span>

<span data-ttu-id="e6b19-3007">10 letters and digits</span><span class="sxs-lookup"><span data-stu-id="e6b19-3007">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-3008">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-3008">Pattern</span></span>

<span data-ttu-id="e6b19-3009">10 个字母和数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3009">10 letters and digits:</span></span>
- <span data-ttu-id="e6b19-3010">两个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="e6b19-3010">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="e6b19-3011">八个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3011">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-3012">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-3012">Checksum</span></span>

<span data-ttu-id="e6b19-3013">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-3013">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-3014">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-3014">Definition</span></span>

<span data-ttu-id="e6b19-3015">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-3015">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-3016">正则表达式 Regex_taiwan_resident_certificate 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3016">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-3017">找到 Keyword_taiwan_resident_certificate 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3017">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6b19-3018">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3018">Keywords</span></span>

#### <a name="keywordtaiwanresidentcertificate"></a><span data-ttu-id="e6b19-3019">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="e6b19-3019">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="e6b19-3020">Resident Certificate
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3020">Resident Certificate</span></span> 
- <span data-ttu-id="e6b19-3021">驻留的证书</span><span class="sxs-lookup"><span data-stu-id="e6b19-3021">Resident Cert</span></span> 
- <span data-ttu-id="e6b19-3022">Resident Cert.
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3022">Resident Cert.</span></span> 
- <span data-ttu-id="e6b19-3023">身份证</span><span class="sxs-lookup"><span data-stu-id="e6b19-3023">Identification card</span></span> 
- <span data-ttu-id="e6b19-3024">Alien Resident Certificate
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3024">Alien Resident Certificate</span></span> 
- <span data-ttu-id="e6b19-3025">ARC
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3025">ARC</span></span> 
- <span data-ttu-id="e6b19-3026">Taiwan Area Resident Certificate
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3026">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="e6b19-3027">TARC
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3027">TARC</span></span> 
- <span data-ttu-id="e6b19-3028">居留證
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3028">居留證</span></span> 
- <span data-ttu-id="e6b19-3029">外僑居留證
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3029">外僑居留證</span></span> 
- <span data-ttu-id="e6b19-3030">台灣地區居留證
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3030">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="e6b19-3031">泰语总体标识代码</span><span class="sxs-lookup"><span data-stu-id="e6b19-3031">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-3032">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-3032">Format</span></span>

<span data-ttu-id="e6b19-3033">13 位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3033">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-3034">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-3034">Pattern</span></span>

<span data-ttu-id="e6b19-3035">13 个数字：</span><span class="sxs-lookup"><span data-stu-id="e6b19-3035">13 digits:</span></span>
- <span data-ttu-id="e6b19-3036">第一个数字不是 0 或 9</span><span class="sxs-lookup"><span data-stu-id="e6b19-3036">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="e6b19-3037">12 个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3037">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-3038">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-3038">Checksum</span></span>

<span data-ttu-id="e6b19-3039">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-3039">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-3040">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-3040">Definition</span></span>

<span data-ttu-id="e6b19-3041">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-3041">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-3042">函数 Func_Thai_Citizen_Id 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3042">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-3043">找到从 Keyword_Thai_Citizen_Id 关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3043">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="e6b19-3044">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-3044">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-3045">函数 Func_Thai_Citizen_Id 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3045">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-3046">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3046">Keywords</span></span>

#### <a name="keywordthaicitizenid"></a><span data-ttu-id="e6b19-3047">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="e6b19-3047">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="e6b19-3048">ID Number</span><span class="sxs-lookup"><span data-stu-id="e6b19-3048">ID Number</span></span>
- <span data-ttu-id="e6b19-3049">标识号</span><span class="sxs-lookup"><span data-stu-id="e6b19-3049">Identification Number</span></span>
- <span data-ttu-id="e6b19-3050">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="e6b19-3050">บัตรประชาชน</span></span>
- <span data-ttu-id="e6b19-3051">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="e6b19-3051">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="e6b19-3052">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="e6b19-3052">บัตรประชาชน</span></span>
- <span data-ttu-id="e6b19-3053">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="e6b19-3053">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="e6b19-3054">土耳其语的国家/地区标识号</span><span class="sxs-lookup"><span data-stu-id="e6b19-3054">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-3055">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-3055">Format</span></span>

<span data-ttu-id="e6b19-3056">11 个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3056">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-3057">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-3057">Pattern</span></span>

<span data-ttu-id="e6b19-3058">11 个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3058">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-3059">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-3059">Checksum</span></span>

<span data-ttu-id="e6b19-3060">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-3060">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-3061">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-3061">Definition</span></span>

<span data-ttu-id="e6b19-3062">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-3062">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-3063">函数 Func_Turkish_National_Id 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3063">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-3064">找到从 Keyword_Turkish_National_Id 关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3064">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="e6b19-3065">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-3065">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-3066">函数 Func_Turkish_National_Id 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3066">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-3067">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3067">Keywords</span></span>

#### <a name="keywordturkishnationalid"></a><span data-ttu-id="e6b19-3068">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="e6b19-3068">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="e6b19-3069">TC Kimlik 否</span><span class="sxs-lookup"><span data-stu-id="e6b19-3069">TC Kimlik No</span></span>
- <span data-ttu-id="e6b19-3070">TC Kimlik numarası</span><span class="sxs-lookup"><span data-stu-id="e6b19-3070">TC Kimlik numarası</span></span>
- <span data-ttu-id="e6b19-3071">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="e6b19-3071">Vatandaşlık numarası</span></span>
- <span data-ttu-id="e6b19-3072">Vatandaşlık 没有</span><span class="sxs-lookup"><span data-stu-id="e6b19-3072">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="e6b19-p141">英国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-p141">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-3075">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-3075">Format</span></span>

<span data-ttu-id="e6b19-3076">特定格式的 18 个字母和数字组合</span><span class="sxs-lookup"><span data-stu-id="e6b19-3076">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-3077">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-3077">Pattern</span></span>

<span data-ttu-id="e6b19-3078">18 个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="e6b19-3078">18 letters and digits:</span></span>
- <span data-ttu-id="e6b19-3079">用五个字母（不区分大小写）或数字“9”来代替一个字母</span><span class="sxs-lookup"><span data-stu-id="e6b19-3079">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="e6b19-3080">一位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3080">One digit</span></span> 
- <span data-ttu-id="e6b19-3081">采用日期格式 DDMMY 的五位数字，表示出生日期</span><span class="sxs-lookup"><span data-stu-id="e6b19-3081">Five digits in the date format DDMMY for date of birth</span></span> 
- <span data-ttu-id="e6b19-3082">用两个字母（不区分大小写）或数字“9”来代替一个字母</span><span class="sxs-lookup"><span data-stu-id="e6b19-3082">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="e6b19-3083">五位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3083">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-3084">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-3084">Checksum</span></span>

<span data-ttu-id="e6b19-3085">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-3085">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-3086">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-3086">Definition</span></span>

<span data-ttu-id="e6b19-3087">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-3087">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-3088">函数 Func_uk_drivers_license 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3088">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-3089">找到 Keyword_uk_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3089">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="e6b19-3090">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3090">The checksum passes.</span></span>

```
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6b19-3091">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3091">Keywords</span></span>

#### <a name="keywordukdriverslicense"></a><span data-ttu-id="e6b19-3092">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="e6b19-3092">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="e6b19-3093">DVLA
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3093">DVLA</span></span> 
- <span data-ttu-id="e6b19-3094">light vans
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3094">light vans</span></span> 
- <span data-ttu-id="e6b19-3095">quadbikes
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3095">quadbikes</span></span> 
- <span data-ttu-id="e6b19-3096">motor cars
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3096">motor cars</span></span> 
- <span data-ttu-id="e6b19-3097">125cc</span><span class="sxs-lookup"><span data-stu-id="e6b19-3097">125cc</span></span> 
- <span data-ttu-id="e6b19-3098">sidecar
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3098">sidecar</span></span> 
- <span data-ttu-id="e6b19-3099">tricycles
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3099">tricycles</span></span> 
- <span data-ttu-id="e6b19-3100">motorcycles
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3100">motorcycles</span></span> 
- <span data-ttu-id="e6b19-3101">photocard licence
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3101">photocard licence</span></span> 
- <span data-ttu-id="e6b19-3102">learner drivers
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3102">learner drivers</span></span> 
- <span data-ttu-id="e6b19-3103">licence holder
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3103">licence holder</span></span> 
- <span data-ttu-id="e6b19-3104">licence holders
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3104">licence holders</span></span> 
- <span data-ttu-id="e6b19-3105">driving licences
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3105">driving licences</span></span> 
- <span data-ttu-id="e6b19-3106">driving licence
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3106">driving licence</span></span> 
- <span data-ttu-id="e6b19-3107">dual control car
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3107">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="e6b19-p142">英国选民名册号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-p142">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-3110">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-3110">Format</span></span>

<span data-ttu-id="e6b19-3111">两个字母后跟 1-4 个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3111">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-3112">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-3112">Pattern</span></span>

<span data-ttu-id="e6b19-3113">两个字母（不区分大小写）后跟 1-4 个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3113">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-3114">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-3114">Checksum</span></span>

<span data-ttu-id="e6b19-3115">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-3115">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-3116">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-3116">Definition</span></span>

<span data-ttu-id="e6b19-3117">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-3117">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-3118">正则表达式 Regex_uk_electoral 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3118">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-3119">找到 Keyword_uk_electoral 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3119">A keyword from Keyword_uk_electoral is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-3120">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3120">Keywords</span></span>

#### <a name="keywordukelectoral"></a><span data-ttu-id="e6b19-3121">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="e6b19-3121">Keyword_uk_electoral</span></span>

- <span data-ttu-id="e6b19-3122">council nomination
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3122">council nomination</span></span> 
- <span data-ttu-id="e6b19-3123">nomination form
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3123">nomination form</span></span> 
- <span data-ttu-id="e6b19-3124">electoral register

</span><span class="sxs-lookup"><span data-stu-id="e6b19-3124">electoral register</span></span> 
- <span data-ttu-id="e6b19-3125">electoral roll</span><span class="sxs-lookup"><span data-stu-id="e6b19-3125">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="e6b19-p143">英国国家卫生服务号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-p143">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-3128">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-3128">Format</span></span>

<span data-ttu-id="e6b19-3129">10-17 个数字，通过空格分隔 </span><span class="sxs-lookup"><span data-stu-id="e6b19-3129">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-3130">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-3130">Pattern</span></span>

<span data-ttu-id="e6b19-3131">10-17 位数字：</span><span class="sxs-lookup"><span data-stu-id="e6b19-3131">10-17 digits:</span></span>
- <span data-ttu-id="e6b19-3132">3 或 10 位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3132">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="e6b19-3133">一个空格</span><span class="sxs-lookup"><span data-stu-id="e6b19-3133">A space</span></span> 
- <span data-ttu-id="e6b19-3134">三位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3134">Three digits</span></span> 
- <span data-ttu-id="e6b19-3135">一个空格</span><span class="sxs-lookup"><span data-stu-id="e6b19-3135">A space</span></span> 
- <span data-ttu-id="e6b19-3136">四位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3136">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-3137">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-3137">Checksum</span></span>

<span data-ttu-id="e6b19-3138">是</span><span class="sxs-lookup"><span data-stu-id="e6b19-3138">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-3139">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-3139">Definition</span></span>

<span data-ttu-id="e6b19-3140">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-3140">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-3141">函数 Func_uk_nhs_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3141">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-3142">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="e6b19-3142">One of the following is true:</span></span>
    - <span data-ttu-id="e6b19-3143">找到 Keyword_uk_nhs_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3143">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="e6b19-3144">找到 Keyword_uk_nhs_number1 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3144">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="e6b19-3145">找到 Keyword_uk_nhs_number_dob 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3145">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="e6b19-3146">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3146">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-3147">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3147">Keywords</span></span>
   
#### <a name="keyworduknhsnumber"></a><span data-ttu-id="e6b19-3148">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="e6b19-3148">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="e6b19-3149">national health service
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3149">national health service</span></span> 
- <span data-ttu-id="e6b19-3150">nhs
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3150">nhs</span></span> 
- <span data-ttu-id="e6b19-3151">health services authority

</span><span class="sxs-lookup"><span data-stu-id="e6b19-3151">health services authority</span></span> 
- <span data-ttu-id="e6b19-3152">health authority</span><span class="sxs-lookup"><span data-stu-id="e6b19-3152">health authority</span></span>

#### <a name="keyworduknhsnumber1"></a><span data-ttu-id="e6b19-3153">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="e6b19-3153">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="e6b19-3154">patient id
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3154">patient id</span></span> 
- <span data-ttu-id="e6b19-3155">patient identification
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3155">patient identification</span></span> 
- <span data-ttu-id="e6b19-3156">patient no

</span><span class="sxs-lookup"><span data-stu-id="e6b19-3156">patient no</span></span> 
- <span data-ttu-id="e6b19-3157">patient number</span><span class="sxs-lookup"><span data-stu-id="e6b19-3157">patient number</span></span>

#### <a name="keyworduknhsnumberdob"></a><span data-ttu-id="e6b19-3158">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="e6b19-3158">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="e6b19-3159">GP</span><span class="sxs-lookup"><span data-stu-id="e6b19-3159">GP</span></span> 
- <span data-ttu-id="e6b19-3160">DOB
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3160">DOB</span></span> 
- <span data-ttu-id="e6b19-3161">D.O.B</span><span class="sxs-lookup"><span data-stu-id="e6b19-3161">D.O.B</span></span> 
- <span data-ttu-id="e6b19-3162">Date of Birth
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3162">Date of Birth</span></span> 
- <span data-ttu-id="e6b19-3163">Birth Date
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3163">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="e6b19-p144">英国国家保险号码 (NINO)</span><span class="sxs-lookup"><span data-stu-id="e6b19-p144">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-3166">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-3166">Format</span></span>

<span data-ttu-id="e6b19-3167">7 个字符或 9 个字符，并用空格或短划线</span><span class="sxs-lookup"><span data-stu-id="e6b19-3167">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-3168">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-3168">Pattern</span></span>

<span data-ttu-id="e6b19-3169">两种可能的模式：</span><span class="sxs-lookup"><span data-stu-id="e6b19-3169">Two possible patterns:</span></span>

- <span data-ttu-id="e6b19-3170">两个字母 (有效 NINOs 使用此前缀，此模式中验证; 中只有某些字符不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="e6b19-3170">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="e6b19-3171">六位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3171">Six digits</span></span>
- <span data-ttu-id="e6b19-3172">任一 'A'，'B'，'C'，或具有 （如前缀，只某些字符允许在后缀; 不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="e6b19-3172">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="e6b19-3173">或者</span><span class="sxs-lookup"><span data-stu-id="e6b19-3173">OR</span></span>

- <span data-ttu-id="e6b19-3174">两个字母</span><span class="sxs-lookup"><span data-stu-id="e6b19-3174">Two letters</span></span>
- <span data-ttu-id="e6b19-3175">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="e6b19-3175">A space or dash</span></span>
- <span data-ttu-id="e6b19-3176">两位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3176">Two digits</span></span>
- <span data-ttu-id="e6b19-3177">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="e6b19-3177">A space or dash</span></span>
- <span data-ttu-id="e6b19-3178">两位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3178">Two digits</span></span>
- <span data-ttu-id="e6b19-3179">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="e6b19-3179">A space or dash</span></span>
- <span data-ttu-id="e6b19-3180">两位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3180">Two digits</span></span>
- <span data-ttu-id="e6b19-3181">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="e6b19-3181">A space or dash</span></span>
- <span data-ttu-id="e6b19-3182">任一 'A'，'B'，'C'，或具有</span><span class="sxs-lookup"><span data-stu-id="e6b19-3182">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-3183">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-3183">Checksum</span></span>

<span data-ttu-id="e6b19-3184">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-3184">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-3185">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-3185">Definition</span></span>

<span data-ttu-id="e6b19-3186">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-3186">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-3187">函数 Func_uk_nino 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3187">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-3188">找到 Keyword_uk_nino 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3188">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="e6b19-3189">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-3189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-3190">函数 Func_uk_nino 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3190">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-3191">未找到 Keyword_uk_nino 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3191">No keyword from Keyword_uk_nino is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-3192">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3192">Keywords</span></span>

#### <a name="keyworduknino"></a><span data-ttu-id="e6b19-3193">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="e6b19-3193">Keyword_uk_nino</span></span>

- <span data-ttu-id="e6b19-3194">national insurance number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3194">national insurance number</span></span> 
- <span data-ttu-id="e6b19-3195">national insurance contributions
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3195">national insurance contributions</span></span> 
- <span data-ttu-id="e6b19-3196">protection act
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3196">protection act</span></span> 
- <span data-ttu-id="e6b19-3197">insurance
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3197">insurance</span></span> 
- <span data-ttu-id="e6b19-3198">social security number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3198">social security number</span></span> 
- <span data-ttu-id="e6b19-3199">insurance application
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3199">insurance application</span></span> 
- <span data-ttu-id="e6b19-3200">medical application
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3200">medical application</span></span> 
- <span data-ttu-id="e6b19-3201">social insurance
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3201">social insurance</span></span> 
- <span data-ttu-id="e6b19-3202">medical attention
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3202">medical attention</span></span> 
- <span data-ttu-id="e6b19-3203">社会安全</span><span class="sxs-lookup"><span data-stu-id="e6b19-3203">social security</span></span> 
- <span data-ttu-id="e6b19-3204">great britain
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3204">great britain</span></span> 
- <span data-ttu-id="e6b19-3205">insurance
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3205">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="e6b19-p145">美国/英国护照号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-p145">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-3208">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-3208">Format</span></span>

<span data-ttu-id="e6b19-3209">九个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3209">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-3210">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-3210">Pattern</span></span>

<span data-ttu-id="e6b19-3211">九个连续的数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3211">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-3212">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-3212">Checksum</span></span>

<span data-ttu-id="e6b19-3213">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-3213">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-3214">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-3214">Definition</span></span>

<span data-ttu-id="e6b19-3215">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-3215">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-3216">函数 Func_usa_uk_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3216">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-3217">找到 Keyword_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3217">A keyword from Keyword_passport is found.</span></span>

```
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6b19-3218">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3218">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="e6b19-3219">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="e6b19-3219">Keyword_passport</span></span>

- <span data-ttu-id="e6b19-3220">Passport Number</span><span class="sxs-lookup"><span data-stu-id="e6b19-3220">Passport Number</span></span> 
- <span data-ttu-id="e6b19-3221">
Passport No</span><span class="sxs-lookup"><span data-stu-id="e6b19-3221">Passport No</span></span> 
- <span data-ttu-id="e6b19-3222">Passport #
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3222">Passport #</span></span> 
- <span data-ttu-id="e6b19-3223">Passport#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3223">Passport#</span></span> 
- <span data-ttu-id="e6b19-3224">PassportID</span><span class="sxs-lookup"><span data-stu-id="e6b19-3224">PassportID</span></span> 
- <span data-ttu-id="e6b19-3225">Passportno
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3225">Passportno</span></span> 
- <span data-ttu-id="e6b19-3226">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3226">passportnumber</span></span> 
- <span data-ttu-id="e6b19-3227">パスポート</span><span class="sxs-lookup"><span data-stu-id="e6b19-3227">パスポート</span></span> 
- <span data-ttu-id="e6b19-3228">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3228">パスポート番号</span></span> 
- <span data-ttu-id="e6b19-3229">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3229">パスポートのNum</span></span> 
- <span data-ttu-id="e6b19-3230">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3230">パスポート＃</span></span> 
- <span data-ttu-id="e6b19-3231">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="e6b19-3231">Numéro de passeport</span></span> 
- <span data-ttu-id="e6b19-3232">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="e6b19-3232">Passeport n °</span></span> 
- <span data-ttu-id="e6b19-3233">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3233">Passeport Non</span></span> 
- <span data-ttu-id="e6b19-3234">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3234">Passeport #</span></span> 
- <span data-ttu-id="e6b19-3235">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3235">Passeport#</span></span> 
- <span data-ttu-id="e6b19-3236">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="e6b19-3236">PasseportNon</span></span> 
- <span data-ttu-id="e6b19-3237">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3237">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="e6b19-3238">美国银行帐号</span><span class="sxs-lookup"><span data-stu-id="e6b19-3238">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-3239">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-3239">Format</span></span>

<span data-ttu-id="e6b19-3240">8-17 个数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3240">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-3241">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-3241">Pattern</span></span>

<span data-ttu-id="e6b19-3242">8-17 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3242">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-3243">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-3243">Checksum</span></span>

<span data-ttu-id="e6b19-3244">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-3244">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-3245">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-3245">Definition</span></span>

<span data-ttu-id="e6b19-3246">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-3246">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-3247">正则表达式 Regex_usa_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3247">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-3248">找到 Keyword_usa_Bank_Account 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3248">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6b19-3249">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3249">Keywords</span></span>

#### <a name="keywordusabankaccount"></a><span data-ttu-id="e6b19-3250">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="e6b19-3250">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="e6b19-3251">Checking Account Number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3251">Checking Account Number</span></span> 
- <span data-ttu-id="e6b19-3252">Checking Account
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3252">Checking Account</span></span> 
- <span data-ttu-id="e6b19-3253">Checking Account #
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3253">Checking Account #</span></span> 
- <span data-ttu-id="e6b19-3254">Checking Acct Number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3254">Checking Acct Number</span></span> 
- <span data-ttu-id="e6b19-3255">Checking Acct #
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3255">Checking Acct #</span></span> 
- <span data-ttu-id="e6b19-3256">Checking Acct No.
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3256">Checking Acct No.</span></span> 
- <span data-ttu-id="e6b19-3257">Checking Account No.
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3257">Checking Account No.</span></span> 
- <span data-ttu-id="e6b19-3258">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3258">Bank Account Number</span></span> 
- <span data-ttu-id="e6b19-3259">Bank Account #
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3259">Bank Account #</span></span> 
- <span data-ttu-id="e6b19-3260">Bank Acct Number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3260">Bank Acct Number</span></span> 
- <span data-ttu-id="e6b19-3261">Bank Acct #
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3261">Bank Acct #</span></span> 
- <span data-ttu-id="e6b19-3262">Bank Acct No.
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3262">Bank Acct No.</span></span> 
- <span data-ttu-id="e6b19-3263">Bank Account No.
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3263">Bank Account No.</span></span> 
- <span data-ttu-id="e6b19-3264">Savings Account Number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3264">Savings Account Number</span></span> 
- <span data-ttu-id="e6b19-3265">Savings Account.
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3265">Savings Account.</span></span> 
- <span data-ttu-id="e6b19-3266">Savings Account #
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3266">Savings Account #</span></span> 
- <span data-ttu-id="e6b19-3267">Savings Acct Number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3267">Savings Acct Number</span></span> 
- <span data-ttu-id="e6b19-3268">Savings Acct #
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3268">Savings Acct #</span></span> 
- <span data-ttu-id="e6b19-3269">Savings Acct No.
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3269">Savings Acct No.</span></span> 
- <span data-ttu-id="e6b19-3270">Savings Account No.
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3270">Savings Account No.</span></span> 
- <span data-ttu-id="e6b19-3271">Debit Account Number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3271">Debit Account Number</span></span> 
- <span data-ttu-id="e6b19-3272">Debit Account
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3272">Debit Account</span></span> 
- <span data-ttu-id="e6b19-3273">Debit Account #
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3273">Debit Account #</span></span> 
- <span data-ttu-id="e6b19-3274">Debit Acct Number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3274">Debit Acct Number</span></span> 
- <span data-ttu-id="e6b19-3275">Debit Acct #
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3275">Debit Acct #</span></span> 
- <span data-ttu-id="e6b19-3276">Debit Acct No.
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3276">Debit Acct No.</span></span> 
- <span data-ttu-id="e6b19-3277">Debit Account No.
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3277">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="e6b19-3278">美国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6b19-3278">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-3279">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-3279">Format</span></span>

<span data-ttu-id="e6b19-3280">取决于州</span><span class="sxs-lookup"><span data-stu-id="e6b19-3280">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-3281">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-3281">Pattern</span></span>

<span data-ttu-id="e6b19-3282">取决于州 — 例如，纽约：</span><span class="sxs-lookup"><span data-stu-id="e6b19-3282">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="e6b19-3283">诸如 ddd ddd ddd 的 9 个数字的格式将匹配。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3283">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="e6b19-3284">诸如 dddddddd 的 9 个数字将不匹配。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3284">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-3285">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-3285">Checksum</span></span>

<span data-ttu-id="e6b19-3286">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-3286">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-3287">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-3287">Definition</span></span>

<span data-ttu-id="e6b19-3288">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-3288">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-3289">函数 Func_new_york_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3289">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-3290">找到 Keyword_[state_name]_drivers_license_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3290">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="e6b19-3291">找到 Keyword_us_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3291">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="e6b19-3292">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-3292">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-3293">函数 Func_new_york_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3293">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-3294">找到 Keyword_[state_name]_drivers_license_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3294">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="e6b19-3295">找到 Keyword_us_drivers_license_abbreviations 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3295">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="e6b19-3296">未找到 Keyword_us_drivers_license 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3296">No keyword from Keyword_us_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-3297">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3297">Keywords</span></span>

#### <a name="keywordusdriverslicenseabbreviations"></a><span data-ttu-id="e6b19-3298">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="e6b19-3298">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="e6b19-3299">DL</span><span class="sxs-lookup"><span data-stu-id="e6b19-3299">DL</span></span> 
- <span data-ttu-id="e6b19-3300">DLS</span><span class="sxs-lookup"><span data-stu-id="e6b19-3300">DLS</span></span> 
- <span data-ttu-id="e6b19-3301">CDL</span><span class="sxs-lookup"><span data-stu-id="e6b19-3301">CDL</span></span> 
- <span data-ttu-id="e6b19-3302">CDL</span><span class="sxs-lookup"><span data-stu-id="e6b19-3302">CDLS</span></span> 
- <span data-ttu-id="e6b19-3303">ID</span><span class="sxs-lookup"><span data-stu-id="e6b19-3303">ID</span></span> 
- <span data-ttu-id="e6b19-3304">Id</span><span class="sxs-lookup"><span data-stu-id="e6b19-3304">IDs</span></span> 
- <span data-ttu-id="e6b19-3305">DL#</span><span class="sxs-lookup"><span data-stu-id="e6b19-3305">DL#</span></span> 
- <span data-ttu-id="e6b19-3306">
DLS#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3306">DLS#</span></span> 
- <span data-ttu-id="e6b19-3307">CDL#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3307">CDL#</span></span> 
- <span data-ttu-id="e6b19-3308">CDLS#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3308">CDLS#</span></span> 
- <span data-ttu-id="e6b19-3309">ID#</span><span class="sxs-lookup"><span data-stu-id="e6b19-3309">ID#</span></span>
- <span data-ttu-id="e6b19-3310">
IDs#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3310">IDs#</span></span> 
- <span data-ttu-id="e6b19-3311">ID 号</span><span class="sxs-lookup"><span data-stu-id="e6b19-3311">ID number</span></span> 
- <span data-ttu-id="e6b19-3312">ID numbers
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3312">ID numbers</span></span> 
- <span data-ttu-id="e6b19-3313">LIC</span><span class="sxs-lookup"><span data-stu-id="e6b19-3313">LIC</span></span> 
- <span data-ttu-id="e6b19-3314">LIC#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3314">LIC#</span></span> 

#### <a name="keywordusdriverslicense"></a><span data-ttu-id="e6b19-3315">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="e6b19-3315">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="e6b19-3316">DriverLic</span><span class="sxs-lookup"><span data-stu-id="e6b19-3316">DriverLic</span></span> 
- <span data-ttu-id="e6b19-3317">DriverLics</span><span class="sxs-lookup"><span data-stu-id="e6b19-3317">DriverLics</span></span> 
- <span data-ttu-id="e6b19-3318">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="e6b19-3318">DriverLicense</span></span> 
- <span data-ttu-id="e6b19-3319">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="e6b19-3319">DriverLicenses</span></span> 
- <span data-ttu-id="e6b19-3320">驱动程序 Lic</span><span class="sxs-lookup"><span data-stu-id="e6b19-3320">Driver Lic</span></span> 
- <span data-ttu-id="e6b19-3321">驱动程序 Lics</span><span class="sxs-lookup"><span data-stu-id="e6b19-3321">Driver Lics</span></span> 
- <span data-ttu-id="e6b19-3322">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="e6b19-3322">Driver License</span></span> 
- <span data-ttu-id="e6b19-3323">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="e6b19-3323">Driver Licenses</span></span> 
- <span data-ttu-id="e6b19-3324">DriversLic</span><span class="sxs-lookup"><span data-stu-id="e6b19-3324">DriversLic</span></span> 
- <span data-ttu-id="e6b19-3325">DriversLics</span><span class="sxs-lookup"><span data-stu-id="e6b19-3325">DriversLics</span></span> 
- <span data-ttu-id="e6b19-3326">驾驶员</span><span class="sxs-lookup"><span data-stu-id="e6b19-3326">DriversLicense</span></span> 
- <span data-ttu-id="e6b19-3327">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="e6b19-3327">DriversLicenses</span></span> 
- <span data-ttu-id="e6b19-3328">驱动因素 Lic</span><span class="sxs-lookup"><span data-stu-id="e6b19-3328">Drivers Lic</span></span> 
- <span data-ttu-id="e6b19-3329">驱动因素 Lics</span><span class="sxs-lookup"><span data-stu-id="e6b19-3329">Drivers Lics</span></span> 
- <span data-ttu-id="e6b19-3330">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="e6b19-3330">Drivers License</span></span> 
- <span data-ttu-id="e6b19-3331">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="e6b19-3331">Drivers Licenses</span></span> 
- <span data-ttu-id="e6b19-3332">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="e6b19-3332">Driver'Lic</span></span> 
- <span data-ttu-id="e6b19-3333">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="e6b19-3333">Driver'Lics</span></span> 
- <span data-ttu-id="e6b19-3334">Driver'License</span><span class="sxs-lookup"><span data-stu-id="e6b19-3334">Driver'License</span></span> 
- <span data-ttu-id="e6b19-3335">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="e6b19-3335">Driver'Licenses</span></span> 
- <span data-ttu-id="e6b19-3336">驱动因素 Lic</span><span class="sxs-lookup"><span data-stu-id="e6b19-3336">Driver' Lic</span></span> 
- <span data-ttu-id="e6b19-3337">驱动因素 Lics</span><span class="sxs-lookup"><span data-stu-id="e6b19-3337">Driver' Lics</span></span> 
- <span data-ttu-id="e6b19-3338">驱动因素许可证</span><span class="sxs-lookup"><span data-stu-id="e6b19-3338">Driver' License</span></span> 
- <span data-ttu-id="e6b19-3339">驱动因素许可证</span><span class="sxs-lookup"><span data-stu-id="e6b19-3339">Driver' Licenses</span></span>
- <span data-ttu-id="e6b19-3340">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="e6b19-3340">Driver'sLic</span></span> 
- <span data-ttu-id="e6b19-3341">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="e6b19-3341">Driver'sLics</span></span> 
- <span data-ttu-id="e6b19-3342">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="e6b19-3342">Driver'sLicense</span></span> 
- <span data-ttu-id="e6b19-3343">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="e6b19-3343">Driver'sLicenses</span></span> 
- <span data-ttu-id="e6b19-3344">驱动因素的 Lic</span><span class="sxs-lookup"><span data-stu-id="e6b19-3344">Driver's Lic</span></span> 
- <span data-ttu-id="e6b19-3345">驱动因素的 Lics</span><span class="sxs-lookup"><span data-stu-id="e6b19-3345">Driver's Lics</span></span> 
- <span data-ttu-id="e6b19-3346">驱动程序的许可证</span><span class="sxs-lookup"><span data-stu-id="e6b19-3346">Driver's License</span></span> 
- <span data-ttu-id="e6b19-3347">驱动程序的许可证</span><span class="sxs-lookup"><span data-stu-id="e6b19-3347">Driver's Licenses</span></span> 
- <span data-ttu-id="e6b19-3348">identification number
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3348">identification number</span></span> 
- <span data-ttu-id="e6b19-3349">identification numbers
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3349">identification numbers</span></span> 
- <span data-ttu-id="e6b19-3350">identification #
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3350">identification #</span></span> 
- <span data-ttu-id="e6b19-3351">身份证</span><span class="sxs-lookup"><span data-stu-id="e6b19-3351">id card</span></span> 
- <span data-ttu-id="e6b19-3352">id 卡</span><span class="sxs-lookup"><span data-stu-id="e6b19-3352">id cards</span></span> 
- <span data-ttu-id="e6b19-3353">身份证</span><span class="sxs-lookup"><span data-stu-id="e6b19-3353">identification card</span></span> 
- <span data-ttu-id="e6b19-3354">身份证</span><span class="sxs-lookup"><span data-stu-id="e6b19-3354">identification cards</span></span> 
- <span data-ttu-id="e6b19-3355">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="e6b19-3355">DriverLic#</span></span> 
- <span data-ttu-id="e6b19-3356">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="e6b19-3356">DriverLics#</span></span> 
- <span data-ttu-id="e6b19-3357">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="e6b19-3357">DriverLicense#</span></span> 
- <span data-ttu-id="e6b19-3358">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="e6b19-3358">DriverLicenses#</span></span> 
- <span data-ttu-id="e6b19-3359">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="e6b19-3359">Driver Lic#</span></span> 
- <span data-ttu-id="e6b19-3360">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3360">Driver Lics#</span></span> 
- <span data-ttu-id="e6b19-3361">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-3361">Driver License#</span></span> 
- <span data-ttu-id="e6b19-3362">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-3362">Driver Licenses#</span></span> 
- <span data-ttu-id="e6b19-3363">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="e6b19-3363">DriversLic#</span></span> 
- <span data-ttu-id="e6b19-3364">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="e6b19-3364">DriversLics#</span></span> 
- <span data-ttu-id="e6b19-3365">驾驶员 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-3365">DriversLicense#</span></span> 
- <span data-ttu-id="e6b19-3366">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="e6b19-3366">DriversLicenses#</span></span> 
- <span data-ttu-id="e6b19-3367">驱动因素 Lic #</span><span class="sxs-lookup"><span data-stu-id="e6b19-3367">Drivers Lic#</span></span> 
- <span data-ttu-id="e6b19-3368">驱动因素 Lics #</span><span class="sxs-lookup"><span data-stu-id="e6b19-3368">Drivers Lics#</span></span> 
- <span data-ttu-id="e6b19-3369">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-3369">Drivers License#</span></span> 
- <span data-ttu-id="e6b19-3370">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-3370">Drivers Licenses#</span></span> 
- <span data-ttu-id="e6b19-3371">Driver'Lic#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3371">Driver'Lic#</span></span> 
- <span data-ttu-id="e6b19-3372">Driver'Lics#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3372">Driver'Lics#</span></span> 
- <span data-ttu-id="e6b19-3373">Driver'License#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3373">Driver'License#</span></span> 
- <span data-ttu-id="e6b19-3374">Driver'Licenses#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3374">Driver'Licenses#</span></span> 
- <span data-ttu-id="e6b19-3375">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3375">Driver' Lic#</span></span> 
- <span data-ttu-id="e6b19-3376">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3376">Driver' Lics#</span></span> 
- <span data-ttu-id="e6b19-3377">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3377">Driver' License#</span></span> 
- <span data-ttu-id="e6b19-3378">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3378">Driver' Licenses#</span></span> 
- <span data-ttu-id="e6b19-3379">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="e6b19-3379">Driver'sLic#</span></span> 
- <span data-ttu-id="e6b19-3380">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="e6b19-3380">Driver'sLics#</span></span> 
- <span data-ttu-id="e6b19-3381">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="e6b19-3381">Driver'sLicense#</span></span> 
- <span data-ttu-id="e6b19-3382">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="e6b19-3382">Driver'sLicenses#</span></span> 
- <span data-ttu-id="e6b19-3383">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3383">Driver's Lic#</span></span> 
- <span data-ttu-id="e6b19-3384">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3384">Driver's Lics#</span></span> 
- <span data-ttu-id="e6b19-3385">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3385">Driver's License#</span></span> 
- <span data-ttu-id="e6b19-3386">Driver's Licenses#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3386">Driver's Licenses#</span></span> 
- <span data-ttu-id="e6b19-3387">id 卡 #</span><span class="sxs-lookup"><span data-stu-id="e6b19-3387">id card#</span></span> 
- <span data-ttu-id="e6b19-3388">id cards#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3388">id cards#</span></span> 
- <span data-ttu-id="e6b19-3389">identification card#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3389">identification card#</span></span> 
- <span data-ttu-id="e6b19-3390">identification cards#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3390">identification cards#</span></span> 


#### <a name="keywordstatenamedriverslicensename"></a><span data-ttu-id="e6b19-3391">Keyword_[state_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="e6b19-3391">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="e6b19-3392">州缩写（例如，“NY”）
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3392">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="e6b19-3393">州名称（例如，“New York”）
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3393">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="e6b19-3394">美国单独的纳税人标识号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="e6b19-3394">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-3395">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-3395">Format</span></span>

<span data-ttu-id="e6b19-3396">九个数字，以“9”开头，“7”或“8”作为第四个数字，可以采用空格或短划线格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-3396">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-3397">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-3397">Pattern</span></span>

<span data-ttu-id="e6b19-3398">有格式模式：</span><span class="sxs-lookup"><span data-stu-id="e6b19-3398">Formatted:</span></span>
- <span data-ttu-id="e6b19-3399">数字“9”</span><span class="sxs-lookup"><span data-stu-id="e6b19-3399">The digit "9"</span></span> 
- <span data-ttu-id="e6b19-3400">两位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3400">Two digits</span></span> 
- <span data-ttu-id="e6b19-3401">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="e6b19-3401">A space or dash</span></span> 
- <span data-ttu-id="e6b19-3402">“7”或“8”</span><span class="sxs-lookup"><span data-stu-id="e6b19-3402">A "7" or "8"</span></span> 
- <span data-ttu-id="e6b19-3403">一位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3403">A digit</span></span> 
- <span data-ttu-id="e6b19-3404">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="e6b19-3404">A space, or dash</span></span> 
- <span data-ttu-id="e6b19-3405">四位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3405">Four digits</span></span>

<span data-ttu-id="e6b19-3406">无格式模式：</span><span class="sxs-lookup"><span data-stu-id="e6b19-3406">Unformatted:</span></span>
- <span data-ttu-id="e6b19-3407">数字“9”</span><span class="sxs-lookup"><span data-stu-id="e6b19-3407">The digit "9"</span></span> 
- <span data-ttu-id="e6b19-3408">两位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3408">Two digits</span></span> 
- <span data-ttu-id="e6b19-3409">“7”或“8”</span><span class="sxs-lookup"><span data-stu-id="e6b19-3409">A "7" or "8"</span></span> 
- <span data-ttu-id="e6b19-3410">五位数字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3410">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-3411">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-3411">Checksum</span></span>

<span data-ttu-id="e6b19-3412">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-3412">No</span></span>

### <a name="definition"></a><span data-ttu-id="e6b19-3413">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-3413">Definition</span></span>

<span data-ttu-id="e6b19-3414">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-3414">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-3415">函数 Func_formatted_itin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3415">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-3416">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="e6b19-3416">At least one of the following is true:</span></span>
    - <span data-ttu-id="e6b19-3417">找到 Keyword_itin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3417">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="e6b19-3418">函数 Func_us_address 找到正确日期格式的地址。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3418">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="e6b19-3419">函数 Func_us_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3419">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="e6b19-3420">找到 Keyword_itin_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3420">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="e6b19-3421">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-3421">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-3422">函数 Func_unformatted_itin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3422">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-3423">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="e6b19-3423">At least one of the following is true:</span></span>
    - <span data-ttu-id="e6b19-3424">找到 Keyword_itin_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3424">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="e6b19-3425">函数 Func_us_address 找到正确日期格式的地址。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3425">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="e6b19-3426">函数 Func_us_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3426">The function Func_us_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-3427">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3427">Keywords</span></span>

#### <a name="keyworditin"></a><span data-ttu-id="e6b19-3428">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="e6b19-3428">Keyword_itin</span></span>

- <span data-ttu-id="e6b19-3429">taxpayer
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3429">taxpayer</span></span> 
- <span data-ttu-id="e6b19-3430">tax id
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3430">tax id</span></span> 
- <span data-ttu-id="e6b19-3431">tax identification
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3431">tax identification</span></span> 
- <span data-ttu-id="e6b19-3432">itin
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3432">itin</span></span> 
- <span data-ttu-id="e6b19-3433">ssn</span><span class="sxs-lookup"><span data-stu-id="e6b19-3433">ssn</span></span> 
- <span data-ttu-id="e6b19-3434">tin
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3434">tin</span></span> 
- <span data-ttu-id="e6b19-3435">社会安全</span><span class="sxs-lookup"><span data-stu-id="e6b19-3435">social security</span></span> 
- <span data-ttu-id="e6b19-3436">tax payer
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3436">tax payer</span></span> 
- <span data-ttu-id="e6b19-3437">itins
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3437">itins</span></span> 
- <span data-ttu-id="e6b19-3438">taxid

</span><span class="sxs-lookup"><span data-stu-id="e6b19-3438">taxid</span></span> 
- <span data-ttu-id="e6b19-3439">individual taxpayer
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3439">individual taxpayer</span></span> 

#### <a name="keyworditincollaborative"></a><span data-ttu-id="e6b19-3440">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="e6b19-3440">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="e6b19-3441">License</span><span class="sxs-lookup"><span data-stu-id="e6b19-3441">License</span></span> 
- <span data-ttu-id="e6b19-3442">DL</span><span class="sxs-lookup"><span data-stu-id="e6b19-3442">DL</span></span> 
- <span data-ttu-id="e6b19-3443">DOB
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3443">DOB</span></span> 
- <span data-ttu-id="e6b19-3444">出生日期</span><span class="sxs-lookup"><span data-stu-id="e6b19-3444">Birthdate</span></span> 
- <span data-ttu-id="e6b19-3445">生日 </span><span class="sxs-lookup"><span data-stu-id="e6b19-3445">Birthday</span></span> 
- <span data-ttu-id="e6b19-3446">Date of Birth
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3446">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="e6b19-3447">美国社会保险号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="e6b19-3447">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="e6b19-3448">格式</span><span class="sxs-lookup"><span data-stu-id="e6b19-3448">Format</span></span>

<span data-ttu-id="e6b19-3449">9 个数字，可以是格式化模式，也可以是非格式化模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-3449">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="e6b19-3450">如果在 2011 年中旬前发布，则 SSN 具有强格式，即数字的某部分必须介于某个有效的范围中（但是没有校验和）。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3450">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="e6b19-3451">模式</span><span class="sxs-lookup"><span data-stu-id="e6b19-3451">Pattern</span></span>

<span data-ttu-id="e6b19-3452">四种不同模式中的 SSN 的四种函数外观：</span><span class="sxs-lookup"><span data-stu-id="e6b19-3452">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="e6b19-3453">Func_ssn 查找具有 2011 年以前使用短划线或空格格式化的强格式的 SSN（ddd-dd-dddd 或 ddd dd dddd）</span><span class="sxs-lookup"><span data-stu-id="e6b19-3453">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="e6b19-3454">Func_unformatted_ssn 查找具有 2011 年以前未格式化为 9 个连续数字的强格式的 SSN (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="e6b19-3454">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="e6b19-3455">Func_randomized_formatted_ssn 查找 2011 年后使用短划线或空格（ddd-dd-dddd 或 ddd dd dddd）格式化的 SSN</span><span class="sxs-lookup"><span data-stu-id="e6b19-3455">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="e6b19-3456">Func_randomized_unformatted_ssn 查找 2011 年后未格式化为 9 个连续数字 (ddddddddd) 的 SSN</span><span class="sxs-lookup"><span data-stu-id="e6b19-3456">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="e6b19-3457">校验和</span><span class="sxs-lookup"><span data-stu-id="e6b19-3457">Checksum</span></span>

<span data-ttu-id="e6b19-3458">否</span><span class="sxs-lookup"><span data-stu-id="e6b19-3458">No</span></span>


### <a name="definition"></a><span data-ttu-id="e6b19-3459">定义</span><span class="sxs-lookup"><span data-stu-id="e6b19-3459">Definition</span></span>

<span data-ttu-id="e6b19-3460">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-3460">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-3461">函数 Func_ssn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3461">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-3462">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3462">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="e6b19-3463">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-3463">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-3464">函数 Func_unformatted_ssn 查找与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3464">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-3465">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3465">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="e6b19-3466">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-3466">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-3467">函数 Func_randomized_formatted_ssn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3467">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-3468">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3468">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="e6b19-3469">函数 Func_ssn 未找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3469">The function Func_ssn does not find content that matches the pattern.</span></span>

<span data-ttu-id="e6b19-3470">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 55% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e6b19-3470">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e6b19-3471">函数 Func_randomized_unformatted_ssn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3471">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="e6b19-3472">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3472">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="e6b19-3473">函数 Func_unformatted_ssn 未找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e6b19-3473">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="e6b19-3474">关键字</span><span class="sxs-lookup"><span data-stu-id="e6b19-3474">Keywords</span></span>

#### <a name="keywordssn"></a><span data-ttu-id="e6b19-3475">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="e6b19-3475">Keyword_ssn</span></span>

- <span data-ttu-id="e6b19-3476">Social Security
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3476">Social Security</span></span> 
- <span data-ttu-id="e6b19-3477">Social Security#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3477">Social Security#</span></span> 
- <span data-ttu-id="e6b19-3478">Soc Sec
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3478">Soc Sec</span></span> 
- <span data-ttu-id="e6b19-3479">SSN</span><span class="sxs-lookup"><span data-stu-id="e6b19-3479">SSN</span></span> 
- <span data-ttu-id="e6b19-3480">SSNS
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3480">SSNS</span></span> 
- <span data-ttu-id="e6b19-3481">SSN#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3481">SSN#</span></span> 
- <span data-ttu-id="e6b19-3482">SS#
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3482">SS#</span></span> 
- <span data-ttu-id="e6b19-3483">SSID
</span><span class="sxs-lookup"><span data-stu-id="e6b19-3483">SSID</span></span> 
   

