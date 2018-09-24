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
ms.openlocfilehash: 2e59b322730ca7fa828a685ed3a80c48ebdbbfd8
ms.sourcegitcommit: 17c7e18d7d00135b1af40cbea117c9a817a41117
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2018
ms.locfileid: "24972354"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="a7f02-104">使用敏感信息类型查找什么</span><span class="sxs-lookup"><span data-stu-id="a7f02-104">What the sensitive information types look for</span></span>

<span data-ttu-id="a7f02-p102">Office 365 安全性的数据丢失防护 (DLP)&amp;合规性中心包括许多可供您可以使用 DLP 策略中的敏感信息类型。本主题列出了所有这些敏感信息类型，并显示 DLP 策略时检测到每种类型的寻找。敏感信息类型定义的正则表达式或函数可以识别的模式。此外，如关键字和校验和确定证据可以用于标识的敏感信息类型。在评估过程还使用可信度和接近度。</span><span class="sxs-lookup"><span data-stu-id="a7f02-p102">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies. This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type. A sensitive information type is defined by a pattern that can be identified by a regular expression or a function. In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type. Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="a7f02-110">ABA 银行代号</span><span class="sxs-lookup"><span data-stu-id="a7f02-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-111">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-111">Format</span></span>

<span data-ttu-id="a7f02-112">9 个数字，可以是格式化模式，也可以是非格式化模式 </span><span class="sxs-lookup"><span data-stu-id="a7f02-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-113">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-113">Pattern</span></span>

<span data-ttu-id="a7f02-114">有格式模式：</span><span class="sxs-lookup"><span data-stu-id="a7f02-114">Formatted:</span></span>
- <span data-ttu-id="a7f02-115">四个数字，以 0、 1、 2、 3、 6、 7 或 8 开头</span><span class="sxs-lookup"><span data-stu-id="a7f02-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="a7f02-116">连字符</span><span class="sxs-lookup"><span data-stu-id="a7f02-116">A hyphen</span></span>
- <span data-ttu-id="a7f02-117">四位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-117">Four digits</span></span>
- <span data-ttu-id="a7f02-118">连字符</span><span class="sxs-lookup"><span data-stu-id="a7f02-118">A hyphen</span></span>
- <span data-ttu-id="a7f02-119">一位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-119">A digit</span></span>

<span data-ttu-id="a7f02-120">未格式化： 9 连续的数字开头 0、 1、 2、 3、 6、 7 或 8</span><span class="sxs-lookup"><span data-stu-id="a7f02-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="a7f02-121">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-121">Checksum</span></span>

<span data-ttu-id="a7f02-122">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-123">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-123">Definition</span></span>

<span data-ttu-id="a7f02-124">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-125">函数 Func_aba_routing 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-126">找到 Keyword_ABA_Routing 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="a7f02-127">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-127">Keywords</span></span>

#### <a name="keywordabarouting"></a><span data-ttu-id="a7f02-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="a7f02-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="a7f02-129">aba</span><span class="sxs-lookup"><span data-stu-id="a7f02-129">aba</span></span>
- <span data-ttu-id="a7f02-130">
aba #</span><span class="sxs-lookup"><span data-stu-id="a7f02-130">aba #</span></span>
- <span data-ttu-id="a7f02-131">
aba routing #</span><span class="sxs-lookup"><span data-stu-id="a7f02-131">aba routing #</span></span>
- <span data-ttu-id="a7f02-132">aba 银行代号</span><span class="sxs-lookup"><span data-stu-id="a7f02-132">aba routing number</span></span>
- <span data-ttu-id="a7f02-133">
aba#</span><span class="sxs-lookup"><span data-stu-id="a7f02-133">aba#</span></span>
- <span data-ttu-id="a7f02-134">
abarouting#</span><span class="sxs-lookup"><span data-stu-id="a7f02-134">abarouting#</span></span>
- <span data-ttu-id="a7f02-135">
aba number</span><span class="sxs-lookup"><span data-stu-id="a7f02-135">aba number</span></span>
- <span data-ttu-id="a7f02-136">
abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="a7f02-136">abaroutingnumber</span></span>
- <span data-ttu-id="a7f02-137">
american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="a7f02-137">american bank association routing #</span></span>
- <span data-ttu-id="a7f02-138">
american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="a7f02-138">american bank association routing number</span></span>
- <span data-ttu-id="a7f02-139">
americanbankassociationrouting#</span><span class="sxs-lookup"><span data-stu-id="a7f02-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="a7f02-140">
americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="a7f02-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="a7f02-141">
bank routing number</span><span class="sxs-lookup"><span data-stu-id="a7f02-141">bank routing number</span></span>
- <span data-ttu-id="a7f02-142">
bankrouting#</span><span class="sxs-lookup"><span data-stu-id="a7f02-142">bankrouting#</span></span>
- <span data-ttu-id="a7f02-143">
bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="a7f02-143">bankroutingnumber</span></span>
- <span data-ttu-id="a7f02-144">
routing transit number</span><span class="sxs-lookup"><span data-stu-id="a7f02-144">routing transit number</span></span>
- <span data-ttu-id="a7f02-145">
RTN
</span><span class="sxs-lookup"><span data-stu-id="a7f02-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="a7f02-146">阿根廷国家身份证 (DNI) 号</span><span class="sxs-lookup"><span data-stu-id="a7f02-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-147">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-147">Format</span></span>

<span data-ttu-id="a7f02-148">八个数字，用点分隔</span><span class="sxs-lookup"><span data-stu-id="a7f02-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-149">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-149">Pattern</span></span>

<span data-ttu-id="a7f02-150">八个数字：</span><span class="sxs-lookup"><span data-stu-id="a7f02-150">Eight digits:</span></span>
- <span data-ttu-id="a7f02-151">两个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-151">Two digits</span></span>
- <span data-ttu-id="a7f02-152">一个点 </span><span class="sxs-lookup"><span data-stu-id="a7f02-152">A period</span></span>
- <span data-ttu-id="a7f02-153">三个数字 </span><span class="sxs-lookup"><span data-stu-id="a7f02-153">Three digits</span></span>
- <span data-ttu-id="a7f02-154">一个点 </span><span class="sxs-lookup"><span data-stu-id="a7f02-154">A period</span></span>
- <span data-ttu-id="a7f02-155">三个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-156">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-156">Checksum</span></span>

<span data-ttu-id="a7f02-157">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-158">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-158">Definition</span></span>

<span data-ttu-id="a7f02-159">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-160">正则表达式 Regex_argentina_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-161">找到 Keyword_argentina_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7f02-162">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-162">Keywords</span></span>

#### <a name="keywordargentinanationalid"></a><span data-ttu-id="a7f02-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="a7f02-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="a7f02-164">Argentina National Identity number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="a7f02-165">标识</span><span class="sxs-lookup"><span data-stu-id="a7f02-165">Identity</span></span> 
- <span data-ttu-id="a7f02-166">标识国家/地区身份证</span><span class="sxs-lookup"><span data-stu-id="a7f02-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="a7f02-167">DNI
</span><span class="sxs-lookup"><span data-stu-id="a7f02-167">DNI</span></span> 
- <span data-ttu-id="a7f02-168">NIC 的人员的国家/地区注册表</span><span class="sxs-lookup"><span data-stu-id="a7f02-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="a7f02-169">Documento Nacional de Identidad
</span><span class="sxs-lookup"><span data-stu-id="a7f02-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="a7f02-170">Registro Nacional de las Personas
</span><span class="sxs-lookup"><span data-stu-id="a7f02-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="a7f02-171">Identidad
</span><span class="sxs-lookup"><span data-stu-id="a7f02-171">Identidad</span></span> 
- <span data-ttu-id="a7f02-172">Identificación
</span><span class="sxs-lookup"><span data-stu-id="a7f02-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="a7f02-173">澳大利亚银行帐号</span><span class="sxs-lookup"><span data-stu-id="a7f02-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-174">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-174">Format</span></span>

<span data-ttu-id="a7f02-175">6-10 个数字，带或不带 BSB 号码 </span><span class="sxs-lookup"><span data-stu-id="a7f02-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-176">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-176">Pattern</span></span>

<span data-ttu-id="a7f02-p103">帐号是 6-10 位数字。澳大利亚银行状态分支编号：</span><span class="sxs-lookup"><span data-stu-id="a7f02-p103">Account number is 6-10 digits. Australia bank state branch number:</span></span>
- <span data-ttu-id="a7f02-179">三位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-179">Three digits</span></span> 
- <span data-ttu-id="a7f02-180">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="a7f02-180">A hyphen</span></span> 
- <span data-ttu-id="a7f02-181">三位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-182">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-182">Checksum</span></span>

<span data-ttu-id="a7f02-183">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-184">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-184">Definition</span></span>

<span data-ttu-id="a7f02-185">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-186">正则表达式 Regex_australia_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="a7f02-187">找到 Keyword_australia_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="a7f02-188">正则表达式 Regex_australia_bank_account_number_bsb 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="a7f02-189">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-190">正则表达式 Regex_australia_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="a7f02-191">找到 Keyword_australia_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-192">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-192">Keywords</span></span>

#### <a name="keywordaustraliabankaccountnumber"></a><span data-ttu-id="a7f02-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="a7f02-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="a7f02-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="a7f02-194">swift bank code</span></span>
- <span data-ttu-id="a7f02-195">
correspondent bank</span><span class="sxs-lookup"><span data-stu-id="a7f02-195">correspondent bank</span></span>
- <span data-ttu-id="a7f02-196">
base currency</span><span class="sxs-lookup"><span data-stu-id="a7f02-196">base currency</span></span>
- <span data-ttu-id="a7f02-197">
usa account</span><span class="sxs-lookup"><span data-stu-id="a7f02-197">usa account</span></span>
- <span data-ttu-id="a7f02-198">
holder address</span><span class="sxs-lookup"><span data-stu-id="a7f02-198">holder address</span></span>
- <span data-ttu-id="a7f02-199">
bank address</span><span class="sxs-lookup"><span data-stu-id="a7f02-199">bank address</span></span>
- <span data-ttu-id="a7f02-200">
information account</span><span class="sxs-lookup"><span data-stu-id="a7f02-200">information account</span></span>
- <span data-ttu-id="a7f02-201">
fund transfers</span><span class="sxs-lookup"><span data-stu-id="a7f02-201">fund transfers</span></span>
- <span data-ttu-id="a7f02-202">
bank charges</span><span class="sxs-lookup"><span data-stu-id="a7f02-202">bank charges</span></span>
- <span data-ttu-id="a7f02-203">
bank details</span><span class="sxs-lookup"><span data-stu-id="a7f02-203">bank details</span></span>
- <span data-ttu-id="a7f02-204">
banking information</span><span class="sxs-lookup"><span data-stu-id="a7f02-204">banking information</span></span>
- <span data-ttu-id="a7f02-205">
full names</span><span class="sxs-lookup"><span data-stu-id="a7f02-205">full names</span></span>
- <span data-ttu-id="a7f02-206">

iaea</span><span class="sxs-lookup"><span data-stu-id="a7f02-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="a7f02-207">澳大利亚驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-208">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-208">Format</span></span>

<span data-ttu-id="a7f02-209">九个字母和数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-210">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-210">Pattern</span></span>

<span data-ttu-id="a7f02-211">九个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="a7f02-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="a7f02-212">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="a7f02-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="a7f02-213">两位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-213">Two digits</span></span> 
- <span data-ttu-id="a7f02-214">五位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="a7f02-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="a7f02-215">或者</span><span class="sxs-lookup"><span data-stu-id="a7f02-215">OR</span></span>

- <span data-ttu-id="a7f02-216">1-2 个可选字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="a7f02-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="a7f02-217">4-9 位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-217">4-9 digits</span></span>

<span data-ttu-id="a7f02-218">或者</span><span class="sxs-lookup"><span data-stu-id="a7f02-218">OR</span></span>

- <span data-ttu-id="a7f02-219">九个数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="a7f02-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-220">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-220">Checksum</span></span>

<span data-ttu-id="a7f02-221">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-222">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-222">Definition</span></span>

<span data-ttu-id="a7f02-223">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-224">正则表达式 Regex_australia_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-225">找到 Keyword_australia_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="a7f02-226">未找到 Keyword_australia_drivers_license_number_exclusions 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-227">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-227">Keywords</span></span>

#### <a name="keywordaustraliadriverslicensenumber"></a><span data-ttu-id="a7f02-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="a7f02-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="a7f02-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="a7f02-229">international driving permits</span></span>
- <span data-ttu-id="a7f02-230">
australian automobile association</span><span class="sxs-lookup"><span data-stu-id="a7f02-230">australian automobile association</span></span>
- <span data-ttu-id="a7f02-231">
sydney nsw</span><span class="sxs-lookup"><span data-stu-id="a7f02-231">sydney nsw</span></span>
- <span data-ttu-id="a7f02-232">
international driving permit</span><span class="sxs-lookup"><span data-stu-id="a7f02-232">international driving permit</span></span>
- <span data-ttu-id="a7f02-233">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="a7f02-233">DriverLicence</span></span>
- <span data-ttu-id="a7f02-234">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="a7f02-234">DriverLicences</span></span>
- <span data-ttu-id="a7f02-235">驱动程序 Lic</span><span class="sxs-lookup"><span data-stu-id="a7f02-235">Driver Lic</span></span>
- <span data-ttu-id="a7f02-236">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="a7f02-236">Driver Licence</span></span>
- <span data-ttu-id="a7f02-237">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="a7f02-237">Driver Licences</span></span>
- <span data-ttu-id="a7f02-238">DriversLic</span><span class="sxs-lookup"><span data-stu-id="a7f02-238">DriversLic</span></span>
- <span data-ttu-id="a7f02-239">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="a7f02-239">DriversLicence</span></span>
- <span data-ttu-id="a7f02-240">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="a7f02-240">DriversLicences</span></span>
- <span data-ttu-id="a7f02-241">驱动因素 Lic</span><span class="sxs-lookup"><span data-stu-id="a7f02-241">Drivers Lic</span></span>
- <span data-ttu-id="a7f02-242">驱动因素 Lics</span><span class="sxs-lookup"><span data-stu-id="a7f02-242">Drivers Lics</span></span>
- <span data-ttu-id="a7f02-243">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="a7f02-243">Drivers Licence</span></span>
- <span data-ttu-id="a7f02-244">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="a7f02-244">Drivers Licences</span></span>
- <span data-ttu-id="a7f02-245">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="a7f02-245">Driver'Lic</span></span>
- <span data-ttu-id="a7f02-246">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="a7f02-246">Driver'Lics</span></span>
- <span data-ttu-id="a7f02-247">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="a7f02-247">Driver'Licence</span></span>
- <span data-ttu-id="a7f02-248">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="a7f02-248">Driver'Licences</span></span>
- <span data-ttu-id="a7f02-249">驱动因素 Lic</span><span class="sxs-lookup"><span data-stu-id="a7f02-249">Driver' Lic</span></span>
- <span data-ttu-id="a7f02-250">驱动因素 Lics</span><span class="sxs-lookup"><span data-stu-id="a7f02-250">Driver' Lics</span></span>
- <span data-ttu-id="a7f02-251">驱动因素许可</span><span class="sxs-lookup"><span data-stu-id="a7f02-251">Driver' Licence</span></span>
- <span data-ttu-id="a7f02-252">驱动因素许可</span><span class="sxs-lookup"><span data-stu-id="a7f02-252">Driver' Licences</span></span>
- <span data-ttu-id="a7f02-253">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="a7f02-253">Driver'sLic</span></span>
- <span data-ttu-id="a7f02-254">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="a7f02-254">Driver'sLics</span></span>
- <span data-ttu-id="a7f02-255">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="a7f02-255">Driver'sLicence</span></span>
- <span data-ttu-id="a7f02-256">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="a7f02-256">Driver'sLicences</span></span>
- <span data-ttu-id="a7f02-257">驱动因素的 Lic</span><span class="sxs-lookup"><span data-stu-id="a7f02-257">Driver's Lic</span></span>
- <span data-ttu-id="a7f02-258">驱动因素的 Lics</span><span class="sxs-lookup"><span data-stu-id="a7f02-258">Driver's Lics</span></span>
- <span data-ttu-id="a7f02-259">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="a7f02-259">Driver's Licence</span></span>
- <span data-ttu-id="a7f02-260">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="a7f02-260">Driver's Licences</span></span>
- <span data-ttu-id="a7f02-261">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="a7f02-261">DriverLic#</span></span>
- <span data-ttu-id="a7f02-262">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="a7f02-262">DriverLics#</span></span>
- <span data-ttu-id="a7f02-263">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="a7f02-263">DriverLicence#</span></span>
- <span data-ttu-id="a7f02-264">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="a7f02-264">DriverLicences#</span></span>
- <span data-ttu-id="a7f02-265">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="a7f02-265">Driver Lic#</span></span>
- <span data-ttu-id="a7f02-266">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-266">Driver Lics#</span></span>
- <span data-ttu-id="a7f02-267">驱动程序许可 #</span><span class="sxs-lookup"><span data-stu-id="a7f02-267">Driver Licence#</span></span>
- <span data-ttu-id="a7f02-268">驱动程序许可 #</span><span class="sxs-lookup"><span data-stu-id="a7f02-268">Driver Licences#</span></span>
- <span data-ttu-id="a7f02-269">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="a7f02-269">DriversLic#</span></span>
- <span data-ttu-id="a7f02-270">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="a7f02-270">DriversLics#</span></span>
- <span data-ttu-id="a7f02-271">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="a7f02-271">DriversLicence#</span></span>
- <span data-ttu-id="a7f02-272">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="a7f02-272">DriversLicences#</span></span>
- <span data-ttu-id="a7f02-273">驱动因素 Lic #</span><span class="sxs-lookup"><span data-stu-id="a7f02-273">Drivers Lic#</span></span>
- <span data-ttu-id="a7f02-274">驱动因素 Lics #</span><span class="sxs-lookup"><span data-stu-id="a7f02-274">Drivers Lics#</span></span>
- <span data-ttu-id="a7f02-275">驱动因素许可 #</span><span class="sxs-lookup"><span data-stu-id="a7f02-275">Drivers Licence#</span></span>
- <span data-ttu-id="a7f02-276">驱动因素许可 #</span><span class="sxs-lookup"><span data-stu-id="a7f02-276">Drivers Licences#</span></span>
- <span data-ttu-id="a7f02-277">Driver'Lic#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-277">Driver'Lic#</span></span>
- <span data-ttu-id="a7f02-278">Driver'Lics#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-278">Driver'Lics#</span></span>
- <span data-ttu-id="a7f02-279">Driver'Licence#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-279">Driver'Licence#</span></span>
- <span data-ttu-id="a7f02-280">Driver'Licences#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-280">Driver'Licences#</span></span>
- <span data-ttu-id="a7f02-281">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-281">Driver' Lic#</span></span>
- <span data-ttu-id="a7f02-282">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-282">Driver' Lics#</span></span>
- <span data-ttu-id="a7f02-283">驱动因素许可 #</span><span class="sxs-lookup"><span data-stu-id="a7f02-283">Driver' Licence#</span></span>
- <span data-ttu-id="a7f02-284">驱动因素许可 #</span><span class="sxs-lookup"><span data-stu-id="a7f02-284">Driver' Licences#</span></span>
- <span data-ttu-id="a7f02-285">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="a7f02-285">Driver'sLic#</span></span>
- <span data-ttu-id="a7f02-286">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="a7f02-286">Driver'sLics#</span></span>
- <span data-ttu-id="a7f02-287">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="a7f02-287">Driver'sLicence#</span></span>
- <span data-ttu-id="a7f02-288">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="a7f02-288">Driver'sLicences#</span></span>
- <span data-ttu-id="a7f02-289">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-289">Driver's Lic#</span></span>
- <span data-ttu-id="a7f02-290">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-290">Driver's Lics#</span></span>
- <span data-ttu-id="a7f02-291">驱动程序的许可 #</span><span class="sxs-lookup"><span data-stu-id="a7f02-291">Driver's Licence#</span></span>
- <span data-ttu-id="a7f02-292">驱动程序的许可 #</span><span class="sxs-lookup"><span data-stu-id="a7f02-292">Driver's Licences#</span></span> 

#### <a name="keywordaustraliadriverslicensenumberexclusions"></a><span data-ttu-id="a7f02-293">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="a7f02-293">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="a7f02-294">aaa</span><span class="sxs-lookup"><span data-stu-id="a7f02-294">aaa</span></span>
- <span data-ttu-id="a7f02-295">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="a7f02-295">DriverLicense</span></span>
- <span data-ttu-id="a7f02-296">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="a7f02-296">DriverLicenses</span></span>
- <span data-ttu-id="a7f02-297">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="a7f02-297">Driver License</span></span>
- <span data-ttu-id="a7f02-298">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="a7f02-298">Driver Licenses</span></span>
- <span data-ttu-id="a7f02-299">驾驶员</span><span class="sxs-lookup"><span data-stu-id="a7f02-299">DriversLicense</span></span>
- <span data-ttu-id="a7f02-300">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="a7f02-300">DriversLicenses</span></span>
- <span data-ttu-id="a7f02-301">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="a7f02-301">Drivers License</span></span>
- <span data-ttu-id="a7f02-302">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="a7f02-302">Drivers Licenses</span></span>
- <span data-ttu-id="a7f02-303">Driver'License</span><span class="sxs-lookup"><span data-stu-id="a7f02-303">Driver'License</span></span>
- <span data-ttu-id="a7f02-304">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="a7f02-304">Driver'Licenses</span></span>
- <span data-ttu-id="a7f02-305">驱动因素许可证</span><span class="sxs-lookup"><span data-stu-id="a7f02-305">Driver' License</span></span>
- <span data-ttu-id="a7f02-306">驱动因素许可证</span><span class="sxs-lookup"><span data-stu-id="a7f02-306">Driver' Licenses</span></span>
- <span data-ttu-id="a7f02-307">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="a7f02-307">Driver'sLicense</span></span>
- <span data-ttu-id="a7f02-308">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="a7f02-308">Driver'sLicenses</span></span>
- <span data-ttu-id="a7f02-309">驱动程序的许可证</span><span class="sxs-lookup"><span data-stu-id="a7f02-309">Driver's License</span></span>
- <span data-ttu-id="a7f02-310">驱动程序的许可证</span><span class="sxs-lookup"><span data-stu-id="a7f02-310">Driver's Licenses</span></span>
- <span data-ttu-id="a7f02-311">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="a7f02-311">DriverLicense#</span></span>
- <span data-ttu-id="a7f02-312">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="a7f02-312">DriverLicenses#</span></span>
- <span data-ttu-id="a7f02-313">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="a7f02-313">Driver License#</span></span>
- <span data-ttu-id="a7f02-314">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="a7f02-314">Driver Licenses#</span></span>
- <span data-ttu-id="a7f02-315">驾驶员 #</span><span class="sxs-lookup"><span data-stu-id="a7f02-315">DriversLicense#</span></span>
- <span data-ttu-id="a7f02-316">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="a7f02-316">DriversLicenses#</span></span>
- <span data-ttu-id="a7f02-317">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="a7f02-317">Drivers License#</span></span>
- <span data-ttu-id="a7f02-318">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="a7f02-318">Drivers Licenses#</span></span>
- <span data-ttu-id="a7f02-319">Driver'License#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-319">Driver'License#</span></span>
- <span data-ttu-id="a7f02-320">Driver'Licenses#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-320">Driver'Licenses#</span></span>
- <span data-ttu-id="a7f02-321">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-321">Driver' License#</span></span>
- <span data-ttu-id="a7f02-322">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-322">Driver' Licenses#</span></span>
- <span data-ttu-id="a7f02-323">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="a7f02-323">Driver'sLicense#</span></span>
- <span data-ttu-id="a7f02-324">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="a7f02-324">Driver'sLicenses#</span></span>
- <span data-ttu-id="a7f02-325">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-325">Driver's License#</span></span>
- <span data-ttu-id="a7f02-326">

Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="a7f02-326">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="a7f02-327">澳大利亚医疗帐号</span><span class="sxs-lookup"><span data-stu-id="a7f02-327">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-328">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-328">Format</span></span>

<span data-ttu-id="a7f02-329">10-11 个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-329">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-330">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-330">Pattern</span></span>

<span data-ttu-id="a7f02-331">10-11 个数字：</span><span class="sxs-lookup"><span data-stu-id="a7f02-331">10-11 digits:</span></span>
- <span data-ttu-id="a7f02-332">第一个数字范围为 2-6</span><span class="sxs-lookup"><span data-stu-id="a7f02-332">First digit is in the range 2-6</span></span>
- <span data-ttu-id="a7f02-333">第九个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="a7f02-333">Ninth digit is a check digit</span></span>
- <span data-ttu-id="a7f02-334">第十个数字是问题数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-334">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="a7f02-335">第十一个数字（可选）是个人号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-335">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-336">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-336">Checksum</span></span>

<span data-ttu-id="a7f02-337">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-337">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-338">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-338">Definition</span></span>

<span data-ttu-id="a7f02-339">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-339">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-340">函数 Func_australian_medical_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-340">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-341">找到 Keyword_Australia_Medical_Account_Number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-341">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="a7f02-342">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-342">The checksum passes.</span></span>

<span data-ttu-id="a7f02-343">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-343">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-344">函数 Func_australian_medical_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-344">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-345">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-345">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-346">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-346">Keywords</span></span>

#### <a name="keywordaustraliamedicalaccountnumber"></a><span data-ttu-id="a7f02-347">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="a7f02-347">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="a7f02-348">bank account details</span><span class="sxs-lookup"><span data-stu-id="a7f02-348">bank account details</span></span>
- <span data-ttu-id="a7f02-349">
medicare payments</span><span class="sxs-lookup"><span data-stu-id="a7f02-349">medicare payments</span></span>
- <span data-ttu-id="a7f02-350">
mortgage account</span><span class="sxs-lookup"><span data-stu-id="a7f02-350">mortgage account</span></span>
- <span data-ttu-id="a7f02-351">
bank payments</span><span class="sxs-lookup"><span data-stu-id="a7f02-351">bank payments</span></span>
- <span data-ttu-id="a7f02-352">
information branch</span><span class="sxs-lookup"><span data-stu-id="a7f02-352">information branch</span></span>
- <span data-ttu-id="a7f02-353">
credit card loan</span><span class="sxs-lookup"><span data-stu-id="a7f02-353">credit card loan</span></span>
- <span data-ttu-id="a7f02-354">
department of human services</span><span class="sxs-lookup"><span data-stu-id="a7f02-354">department of human services</span></span>
- <span data-ttu-id="a7f02-355">本地服务</span><span class="sxs-lookup"><span data-stu-id="a7f02-355">local service</span></span>
- <span data-ttu-id="a7f02-356">

medicare</span><span class="sxs-lookup"><span data-stu-id="a7f02-356">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="a7f02-357">澳大利亚护照号</span><span class="sxs-lookup"><span data-stu-id="a7f02-357">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-358">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-358">Format</span></span>

<span data-ttu-id="a7f02-359">一个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-359">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-360">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-360">Pattern</span></span>

<span data-ttu-id="a7f02-361">一个字母（不区分大小写）后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-361">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-362">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-362">Checksum</span></span>

<span data-ttu-id="a7f02-363">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-363">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-364">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-364">Definition</span></span>

<span data-ttu-id="a7f02-365">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-365">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-366">正则表达式 Regex_australia_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-366">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-367">找到从 Keyword_passport 或 Keyword_australia_passport_number 关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-367">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-368">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-368">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="a7f02-369">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="a7f02-369">Keyword_passport</span></span>

- <span data-ttu-id="a7f02-370">Passport Number</span><span class="sxs-lookup"><span data-stu-id="a7f02-370">Passport Number</span></span>
- <span data-ttu-id="a7f02-371">
Passport No</span><span class="sxs-lookup"><span data-stu-id="a7f02-371">Passport No</span></span>
- <span data-ttu-id="a7f02-372">Passport #
</span><span class="sxs-lookup"><span data-stu-id="a7f02-372">Passport #</span></span>
- <span data-ttu-id="a7f02-373">Passport#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-373">Passport#</span></span>
- <span data-ttu-id="a7f02-374">PassportID</span><span class="sxs-lookup"><span data-stu-id="a7f02-374">PassportID</span></span>
- <span data-ttu-id="a7f02-375">Passportno
</span><span class="sxs-lookup"><span data-stu-id="a7f02-375">Passportno</span></span>
- <span data-ttu-id="a7f02-376">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="a7f02-376">passportnumber</span></span>
- <span data-ttu-id="a7f02-377">パスポート</span><span class="sxs-lookup"><span data-stu-id="a7f02-377">パスポート</span></span>
- <span data-ttu-id="a7f02-378">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="a7f02-378">パスポート番号</span></span>
- <span data-ttu-id="a7f02-379">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="a7f02-379">パスポートのNum</span></span>
- <span data-ttu-id="a7f02-380">
パスポート ＃
</span><span class="sxs-lookup"><span data-stu-id="a7f02-380">パスポート ＃</span></span> 
- <span data-ttu-id="a7f02-381">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="a7f02-381">Numéro de passeport</span></span>
- <span data-ttu-id="a7f02-382">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="a7f02-382">Passeport n °</span></span>
- <span data-ttu-id="a7f02-383">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="a7f02-383">Passeport Non</span></span>
- <span data-ttu-id="a7f02-384">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="a7f02-384">Passeport #</span></span>
- <span data-ttu-id="a7f02-385">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-385">Passeport#</span></span>
- <span data-ttu-id="a7f02-386">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="a7f02-386">PasseportNon</span></span>
- <span data-ttu-id="a7f02-387">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="a7f02-387">Passeportn °</span></span>

#### <a name="keywordaustraliapassportnumber"></a><span data-ttu-id="a7f02-388">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="a7f02-388">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="a7f02-389">passport</span><span class="sxs-lookup"><span data-stu-id="a7f02-389">passport</span></span>
- <span data-ttu-id="a7f02-390">
passport details</span><span class="sxs-lookup"><span data-stu-id="a7f02-390">passport details</span></span>
- <span data-ttu-id="a7f02-391">
immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="a7f02-391">immigration and citizenship</span></span>
- <span data-ttu-id="a7f02-392">
commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="a7f02-392">commonwealth of australia</span></span>
- <span data-ttu-id="a7f02-393">
department of immigration</span><span class="sxs-lookup"><span data-stu-id="a7f02-393">department of immigration</span></span>
- <span data-ttu-id="a7f02-394">
residential address</span><span class="sxs-lookup"><span data-stu-id="a7f02-394">residential address</span></span>
- <span data-ttu-id="a7f02-395">
department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="a7f02-395">department of immigration and citizenship</span></span>
- <span data-ttu-id="a7f02-396">visa
</span><span class="sxs-lookup"><span data-stu-id="a7f02-396">visa</span></span>
- <span data-ttu-id="a7f02-397">
national identity card</span><span class="sxs-lookup"><span data-stu-id="a7f02-397">national identity card</span></span>
- <span data-ttu-id="a7f02-398">护照号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-398">passport number</span></span>
- <span data-ttu-id="a7f02-399">
travel document</span><span class="sxs-lookup"><span data-stu-id="a7f02-399">travel document</span></span>
- <span data-ttu-id="a7f02-400">

issuing authority</span><span class="sxs-lookup"><span data-stu-id="a7f02-400">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="a7f02-401">澳大利亚税号</span><span class="sxs-lookup"><span data-stu-id="a7f02-401">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-402">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-402">Format</span></span>

<span data-ttu-id="a7f02-403">8-9 个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-403">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-404">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-404">Pattern</span></span>

<span data-ttu-id="a7f02-405">通常 8-9 位数字，显示中包含空格，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a7f02-405">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="a7f02-406">三位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-406">Three digits</span></span> 
- <span data-ttu-id="a7f02-407">可选空格</span><span class="sxs-lookup"><span data-stu-id="a7f02-407">An optional space</span></span> 
- <span data-ttu-id="a7f02-408">三位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-408">Three digits</span></span> 
- <span data-ttu-id="a7f02-409">可选空格</span><span class="sxs-lookup"><span data-stu-id="a7f02-409">An optional space</span></span> 
- <span data-ttu-id="a7f02-410">2-3 位数字，最后一位数字是校验位</span><span class="sxs-lookup"><span data-stu-id="a7f02-410">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-411">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-411">Checksum</span></span>

<span data-ttu-id="a7f02-412">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-412">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-413">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-413">Definition</span></span>

<span data-ttu-id="a7f02-414">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-414">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-415">函数 Func_australian_tax_file_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-415">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-416">未找到 Keyword_Australia_Tax_File_Number 或 Keyword_number_exclusions 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-416">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="a7f02-417">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-417">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-418">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-418">Keywords</span></span>

#### <a name="keywordaustraliataxfilenumber"></a><span data-ttu-id="a7f02-419">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="a7f02-419">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="a7f02-420">australian business number</span><span class="sxs-lookup"><span data-stu-id="a7f02-420">australian business number</span></span>
- <span data-ttu-id="a7f02-421">
marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="a7f02-421">marginal tax rate</span></span>
- <span data-ttu-id="a7f02-422">
medicare levy</span><span class="sxs-lookup"><span data-stu-id="a7f02-422">medicare levy</span></span>
- <span data-ttu-id="a7f02-423">
portfolio number</span><span class="sxs-lookup"><span data-stu-id="a7f02-423">portfolio number</span></span>
- <span data-ttu-id="a7f02-424">
service veterans</span><span class="sxs-lookup"><span data-stu-id="a7f02-424">service veterans</span></span>
- <span data-ttu-id="a7f02-425">
withholding tax</span><span class="sxs-lookup"><span data-stu-id="a7f02-425">withholding tax</span></span>
- <span data-ttu-id="a7f02-426">
individual tax return</span><span class="sxs-lookup"><span data-stu-id="a7f02-426">individual tax return</span></span>
- <span data-ttu-id="a7f02-427">

tax file number</span><span class="sxs-lookup"><span data-stu-id="a7f02-427">tax file number</span></span>

#### <a name="keywordnumberexclusions"></a><span data-ttu-id="a7f02-428">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="a7f02-428">Keyword_number_exclusions</span></span>

- <span data-ttu-id="a7f02-429">00000000</span><span class="sxs-lookup"><span data-stu-id="a7f02-429">00000000</span></span>
- <span data-ttu-id="a7f02-430">11111111</span><span class="sxs-lookup"><span data-stu-id="a7f02-430">11111111</span></span>
- <span data-ttu-id="a7f02-431">22222222</span><span class="sxs-lookup"><span data-stu-id="a7f02-431">22222222</span></span>
- <span data-ttu-id="a7f02-432">33333333</span><span class="sxs-lookup"><span data-stu-id="a7f02-432">33333333</span></span>
- <span data-ttu-id="a7f02-433">44444444</span><span class="sxs-lookup"><span data-stu-id="a7f02-433">44444444</span></span>
- <span data-ttu-id="a7f02-434">55555555</span><span class="sxs-lookup"><span data-stu-id="a7f02-434">55555555</span></span>
- <span data-ttu-id="a7f02-435">66666666</span><span class="sxs-lookup"><span data-stu-id="a7f02-435">66666666</span></span>
- <span data-ttu-id="a7f02-436">77777777</span><span class="sxs-lookup"><span data-stu-id="a7f02-436">77777777</span></span>
- <span data-ttu-id="a7f02-437">88888888</span><span class="sxs-lookup"><span data-stu-id="a7f02-437">88888888</span></span>
- <span data-ttu-id="a7f02-438">99999999</span><span class="sxs-lookup"><span data-stu-id="a7f02-438">99999999</span></span>
- <span data-ttu-id="a7f02-439">000000000</span><span class="sxs-lookup"><span data-stu-id="a7f02-439">000000000</span></span>
- <span data-ttu-id="a7f02-440">111111111</span><span class="sxs-lookup"><span data-stu-id="a7f02-440">111111111</span></span>
- <span data-ttu-id="a7f02-441">222222222</span><span class="sxs-lookup"><span data-stu-id="a7f02-441">222222222</span></span>
- <span data-ttu-id="a7f02-442">333333333</span><span class="sxs-lookup"><span data-stu-id="a7f02-442">333333333</span></span>
- <span data-ttu-id="a7f02-443">444444444</span><span class="sxs-lookup"><span data-stu-id="a7f02-443">444444444</span></span>
- <span data-ttu-id="a7f02-444">555555555</span><span class="sxs-lookup"><span data-stu-id="a7f02-444">555555555</span></span>
- <span data-ttu-id="a7f02-445">666666666</span><span class="sxs-lookup"><span data-stu-id="a7f02-445">666666666</span></span>
- <span data-ttu-id="a7f02-446">777777777</span><span class="sxs-lookup"><span data-stu-id="a7f02-446">777777777</span></span>
- <span data-ttu-id="a7f02-447">888888888</span><span class="sxs-lookup"><span data-stu-id="a7f02-447">888888888</span></span>
- <span data-ttu-id="a7f02-448">999999999</span><span class="sxs-lookup"><span data-stu-id="a7f02-448">999999999</span></span>
- <span data-ttu-id="a7f02-449">0000000000</span><span class="sxs-lookup"><span data-stu-id="a7f02-449">0000000000</span></span>
- <span data-ttu-id="a7f02-450">1111111111</span><span class="sxs-lookup"><span data-stu-id="a7f02-450">1111111111</span></span>
- <span data-ttu-id="a7f02-451">2222222222</span><span class="sxs-lookup"><span data-stu-id="a7f02-451">2222222222</span></span>
- <span data-ttu-id="a7f02-452">3333333333</span><span class="sxs-lookup"><span data-stu-id="a7f02-452">3333333333</span></span>
- <span data-ttu-id="a7f02-453">4444444444</span><span class="sxs-lookup"><span data-stu-id="a7f02-453">4444444444</span></span>
- <span data-ttu-id="a7f02-454">5555555555</span><span class="sxs-lookup"><span data-stu-id="a7f02-454">5555555555</span></span>
- <span data-ttu-id="a7f02-455">6666666666</span><span class="sxs-lookup"><span data-stu-id="a7f02-455">6666666666</span></span>
- <span data-ttu-id="a7f02-456">7777777777</span><span class="sxs-lookup"><span data-stu-id="a7f02-456">7777777777</span></span>
- <span data-ttu-id="a7f02-457">8888888888</span><span class="sxs-lookup"><span data-stu-id="a7f02-457">8888888888</span></span>
- <span data-ttu-id="a7f02-458">9999999999</span><span class="sxs-lookup"><span data-stu-id="a7f02-458">9999999999</span></span>
   
## <a name="belgium-national-number"></a><span data-ttu-id="a7f02-459">比利时国家号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-459">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-460">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-460">Format</span></span>

<span data-ttu-id="a7f02-461">11 个数字加分隔符</span><span class="sxs-lookup"><span data-stu-id="a7f02-461">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-462">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-462">Pattern</span></span>

<span data-ttu-id="a7f02-463">11 个数字加分隔符：</span><span class="sxs-lookup"><span data-stu-id="a7f02-463">11 digits plus delimiters:</span></span>
- <span data-ttu-id="a7f02-464">六个数字加两个点，采用格式  YY.MM.DD，代表出生日期  </span><span class="sxs-lookup"><span data-stu-id="a7f02-464">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="a7f02-465">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="a7f02-465">A hyphen</span></span> 
- <span data-ttu-id="a7f02-466">三个连续的数字（男性用奇数，女性用偶数） </span><span class="sxs-lookup"><span data-stu-id="a7f02-466">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="a7f02-467">一个点 </span><span class="sxs-lookup"><span data-stu-id="a7f02-467">A period</span></span> 
- <span data-ttu-id="a7f02-468">两个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="a7f02-468">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-469">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-469">Checksum</span></span>

<span data-ttu-id="a7f02-470">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-470">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-471">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-471">Definition</span></span>

<span data-ttu-id="a7f02-472">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-472">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-473">函数 Func_belgium_national_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-473">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-474">找到 Keyword_belgium_national_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-474">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="a7f02-475">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-475">The checksum passes.</span></span>

```
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7f02-476">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-476">Keywords</span></span>

#### <a name="keywordbelgiumnationalnumber"></a><span data-ttu-id="a7f02-477">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="a7f02-477">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="a7f02-478">Identity</span><span class="sxs-lookup"><span data-stu-id="a7f02-478">Identity</span></span>
- <span data-ttu-id="a7f02-479">Registration</span><span class="sxs-lookup"><span data-stu-id="a7f02-479">Registration</span></span>
- <span data-ttu-id="a7f02-480">Identification</span><span class="sxs-lookup"><span data-stu-id="a7f02-480">Identification</span></span> 
- <span data-ttu-id="a7f02-481">ID</span><span class="sxs-lookup"><span data-stu-id="a7f02-481">ID</span></span> 
- <span data-ttu-id="a7f02-482">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="a7f02-482">Identiteitskaart</span></span>
- <span data-ttu-id="a7f02-483">Registratie nummer 
</span><span class="sxs-lookup"><span data-stu-id="a7f02-483">Registratie nummer</span></span> 
- <span data-ttu-id="a7f02-484">Identificatie nummer
</span><span class="sxs-lookup"><span data-stu-id="a7f02-484">Identificatie nummer</span></span> 
- <span data-ttu-id="a7f02-485">Identiteit</span><span class="sxs-lookup"><span data-stu-id="a7f02-485">Identiteit</span></span>
- <span data-ttu-id="a7f02-486">Registratie</span><span class="sxs-lookup"><span data-stu-id="a7f02-486">Registratie</span></span>
- <span data-ttu-id="a7f02-487">Identificatie

</span><span class="sxs-lookup"><span data-stu-id="a7f02-487">Identificatie</span></span> 
- <span data-ttu-id="a7f02-488">Carte d’identité
</span><span class="sxs-lookup"><span data-stu-id="a7f02-488">Carte d’identité</span></span> 
- <span data-ttu-id="a7f02-489">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="a7f02-489">numéro d'immatriculation</span></span>
- <span data-ttu-id="a7f02-490">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="a7f02-490">numéro d'identification</span></span>
- <span data-ttu-id="a7f02-491">
identité
</span><span class="sxs-lookup"><span data-stu-id="a7f02-491">identité</span></span> 
- <span data-ttu-id="a7f02-492">inscription
</span><span class="sxs-lookup"><span data-stu-id="a7f02-492">inscription</span></span> 
- <span data-ttu-id="a7f02-493">Identifikation</span><span class="sxs-lookup"><span data-stu-id="a7f02-493">Identifikation</span></span>
- <span data-ttu-id="a7f02-494">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="a7f02-494">Identifizierung</span></span>
- <span data-ttu-id="a7f02-495">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="a7f02-495">Identifikationsnummer</span></span>
- <span data-ttu-id="a7f02-496">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="a7f02-496">Personalausweis</span></span>
- <span data-ttu-id="a7f02-497">Registrierung</span><span class="sxs-lookup"><span data-stu-id="a7f02-497">Registrierung</span></span>
- <span data-ttu-id="a7f02-498">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="a7f02-498">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="a7f02-499">巴西 CPF 号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-499">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-500">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-500">Format</span></span>

<span data-ttu-id="a7f02-501">11 个数字（包括校验位），可以格式化，也可以非格式化</span><span class="sxs-lookup"><span data-stu-id="a7f02-501">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-502">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-502">Pattern</span></span>

<span data-ttu-id="a7f02-503">有格式模式：</span><span class="sxs-lookup"><span data-stu-id="a7f02-503">Formatted:</span></span>
- <span data-ttu-id="a7f02-504">三个数字 </span><span class="sxs-lookup"><span data-stu-id="a7f02-504">Three digits</span></span> 
- <span data-ttu-id="a7f02-505">一个点 </span><span class="sxs-lookup"><span data-stu-id="a7f02-505">A period</span></span> 
- <span data-ttu-id="a7f02-506">三个数字 </span><span class="sxs-lookup"><span data-stu-id="a7f02-506">Three digits</span></span> 
- <span data-ttu-id="a7f02-507">一个点 </span><span class="sxs-lookup"><span data-stu-id="a7f02-507">A period</span></span> 
- <span data-ttu-id="a7f02-508">三个数字 </span><span class="sxs-lookup"><span data-stu-id="a7f02-508">Three digits</span></span> 
- <span data-ttu-id="a7f02-509">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="a7f02-509">A hyphen</span></span> 
- <span data-ttu-id="a7f02-510">两个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="a7f02-510">Two digits which are check digits</span></span>

<span data-ttu-id="a7f02-511">非格式化：</span><span class="sxs-lookup"><span data-stu-id="a7f02-511">Unformatted:</span></span>
- <span data-ttu-id="a7f02-512">11 个数字，其中最后两个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="a7f02-512">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-513">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-513">Checksum</span></span>

<span data-ttu-id="a7f02-514">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-514">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-515">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-515">Definition</span></span>

<span data-ttu-id="a7f02-516">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-516">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-517">函数 Func_brazil_cpf 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-517">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-518">找到 Keyword_brazil_cpf 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-518">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="a7f02-519">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-519">The checksum passes.</span></span>

<span data-ttu-id="a7f02-520">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-520">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-521">函数 Func_brazil_cpf 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-521">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-522">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-522">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-523">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-523">Keywords</span></span>

#### <a name="keywordbrazilcpf"></a><span data-ttu-id="a7f02-524">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="a7f02-524">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="a7f02-525">CPF</span><span class="sxs-lookup"><span data-stu-id="a7f02-525">CPF</span></span>
- <span data-ttu-id="a7f02-526">Identification</span><span class="sxs-lookup"><span data-stu-id="a7f02-526">Identification</span></span>
- <span data-ttu-id="a7f02-527">Registration</span><span class="sxs-lookup"><span data-stu-id="a7f02-527">Registration</span></span>
- <span data-ttu-id="a7f02-528">Revenue</span><span class="sxs-lookup"><span data-stu-id="a7f02-528">Revenue</span></span>
- <span data-ttu-id="a7f02-529">Cadastro de Pessoas Físicas
</span><span class="sxs-lookup"><span data-stu-id="a7f02-529">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="a7f02-530">Imposto
</span><span class="sxs-lookup"><span data-stu-id="a7f02-530">Imposto</span></span> 
- <span data-ttu-id="a7f02-531">Identificação
</span><span class="sxs-lookup"><span data-stu-id="a7f02-531">Identificação</span></span> 
- <span data-ttu-id="a7f02-532">Inscrição
</span><span class="sxs-lookup"><span data-stu-id="a7f02-532">Inscrição</span></span> 
- <span data-ttu-id="a7f02-533">Receita

</span><span class="sxs-lookup"><span data-stu-id="a7f02-533">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="a7f02-534">巴西法律实体编号 (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="a7f02-534">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-535">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-535">Format</span></span>

<span data-ttu-id="a7f02-536">14 个数字（包括注册号、分行号码和校验位），再加上分隔符</span><span class="sxs-lookup"><span data-stu-id="a7f02-536">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-537">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-537">Pattern</span></span>
<span data-ttu-id="a7f02-538">14 个数字，再加上分隔符：</span><span class="sxs-lookup"><span data-stu-id="a7f02-538">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="a7f02-539">两个数字 </span><span class="sxs-lookup"><span data-stu-id="a7f02-539">Two digits</span></span> 
- <span data-ttu-id="a7f02-540">一个点 </span><span class="sxs-lookup"><span data-stu-id="a7f02-540">A period</span></span> 
- <span data-ttu-id="a7f02-541">三个数字 </span><span class="sxs-lookup"><span data-stu-id="a7f02-541">Three digits</span></span> 
- <span data-ttu-id="a7f02-542">一个点 </span><span class="sxs-lookup"><span data-stu-id="a7f02-542">A period</span></span> 
- <span data-ttu-id="a7f02-543">三个数字（前 8 位数是注册号） </span><span class="sxs-lookup"><span data-stu-id="a7f02-543">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="a7f02-544">正斜杠 </span><span class="sxs-lookup"><span data-stu-id="a7f02-544">A forward slash</span></span> 
- <span data-ttu-id="a7f02-545">四位分行号码 </span><span class="sxs-lookup"><span data-stu-id="a7f02-545">Four-digit branch number</span></span> 
- <span data-ttu-id="a7f02-546">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="a7f02-546">A hyphen</span></span> 
- <span data-ttu-id="a7f02-547">两个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="a7f02-547">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-548">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-548">Checksum</span></span>

<span data-ttu-id="a7f02-549">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-549">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-550">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-550">Definition</span></span>

<span data-ttu-id="a7f02-551">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-551">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-552">函数 Func_brazil_cnpj 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-552">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-553">找到 Keyword_brazil_cnpj 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-553">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="a7f02-554">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-554">The checksum passes.</span></span>

<span data-ttu-id="a7f02-555">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-555">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-556">函数 Func_brazil_cnpj 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-556">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-557">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-557">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-558">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-558">Keywords</span></span>

#### <a name="keywordbrazilcnpj"></a><span data-ttu-id="a7f02-559">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="a7f02-559">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="a7f02-560">CNPJ
</span><span class="sxs-lookup"><span data-stu-id="a7f02-560">CNPJ</span></span> 
- <span data-ttu-id="a7f02-561">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="a7f02-561">CNPJ/MF</span></span> 
- <span data-ttu-id="a7f02-562">CNPJ-MF
</span><span class="sxs-lookup"><span data-stu-id="a7f02-562">CNPJ-MF</span></span> 
- <span data-ttu-id="a7f02-563">National Registry of Legal Entities
</span><span class="sxs-lookup"><span data-stu-id="a7f02-563">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="a7f02-564">Taxpayers Registry
</span><span class="sxs-lookup"><span data-stu-id="a7f02-564">Taxpayers Registry</span></span> 
- <span data-ttu-id="a7f02-565">Legal entity
</span><span class="sxs-lookup"><span data-stu-id="a7f02-565">Legal entity</span></span> 
- <span data-ttu-id="a7f02-566">Legal entities
</span><span class="sxs-lookup"><span data-stu-id="a7f02-566">Legal entities</span></span> 
- <span data-ttu-id="a7f02-567">Registration Status
</span><span class="sxs-lookup"><span data-stu-id="a7f02-567">Registration Status</span></span> 
- <span data-ttu-id="a7f02-568">Business
</span><span class="sxs-lookup"><span data-stu-id="a7f02-568">Business</span></span> 
- <span data-ttu-id="a7f02-569">Company</span><span class="sxs-lookup"><span data-stu-id="a7f02-569">Company</span></span>
- <span data-ttu-id="a7f02-570">CNPJ
</span><span class="sxs-lookup"><span data-stu-id="a7f02-570">CNPJ</span></span> 
- <span data-ttu-id="a7f02-571">Cadastro Nacional da Pessoa Jurídica
</span><span class="sxs-lookup"><span data-stu-id="a7f02-571">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="a7f02-572">Cadastro Geral de Contribuintes
</span><span class="sxs-lookup"><span data-stu-id="a7f02-572">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="a7f02-573">CGC
</span><span class="sxs-lookup"><span data-stu-id="a7f02-573">CGC</span></span> 
- <span data-ttu-id="a7f02-574">Pessoa jurídica
</span><span class="sxs-lookup"><span data-stu-id="a7f02-574">Pessoa jurídica</span></span> 
- <span data-ttu-id="a7f02-575">Pessoas jurídicas
</span><span class="sxs-lookup"><span data-stu-id="a7f02-575">Pessoas jurídicas</span></span> 
- <span data-ttu-id="a7f02-576">Situação cadastral
</span><span class="sxs-lookup"><span data-stu-id="a7f02-576">Situação cadastral</span></span> 
- <span data-ttu-id="a7f02-577">Inscrição
</span><span class="sxs-lookup"><span data-stu-id="a7f02-577">Inscrição</span></span> 
- <span data-ttu-id="a7f02-578">Empresa
</span><span class="sxs-lookup"><span data-stu-id="a7f02-578">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="a7f02-579">巴西国家身份证 (RG)</span><span class="sxs-lookup"><span data-stu-id="a7f02-579">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-580">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-580">Format</span></span>

<span data-ttu-id="a7f02-581">Registro Geral （旧格式）： 九个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-581">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="a7f02-582">Registro de Identidade (RIC) （新格式）： 11 位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-582">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-583">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-583">Pattern</span></span>

<span data-ttu-id="a7f02-584">Registro Geral（旧格式）：</span><span class="sxs-lookup"><span data-stu-id="a7f02-584">Registro Geral (old format):</span></span>
- <span data-ttu-id="a7f02-585">两个数字 </span><span class="sxs-lookup"><span data-stu-id="a7f02-585">Two digits</span></span> 
- <span data-ttu-id="a7f02-586">一个点 </span><span class="sxs-lookup"><span data-stu-id="a7f02-586">A period</span></span> 
- <span data-ttu-id="a7f02-587">三个数字 </span><span class="sxs-lookup"><span data-stu-id="a7f02-587">Three digits</span></span> 
- <span data-ttu-id="a7f02-588">一个点 </span><span class="sxs-lookup"><span data-stu-id="a7f02-588">A period</span></span> 
- <span data-ttu-id="a7f02-589">三个数字 </span><span class="sxs-lookup"><span data-stu-id="a7f02-589">Three digits</span></span> 
- <span data-ttu-id="a7f02-590">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="a7f02-590">A hyphen</span></span> 
- <span data-ttu-id="a7f02-591">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="a7f02-591">One digit which is a check digit</span></span>

<span data-ttu-id="a7f02-592">Registro de Identidade (RIC) （新格式）：</span><span class="sxs-lookup"><span data-stu-id="a7f02-592">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="a7f02-593">10 个数字 </span><span class="sxs-lookup"><span data-stu-id="a7f02-593">10 digits</span></span> 
- <span data-ttu-id="a7f02-594">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="a7f02-594">A hyphen</span></span> 
- <span data-ttu-id="a7f02-595">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="a7f02-595">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-596">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-596">Checksum</span></span>

<span data-ttu-id="a7f02-597">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-597">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-598">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-598">Definition</span></span>

<span data-ttu-id="a7f02-599">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-599">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-600">函数 Func_brazil_rg 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-600">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-601">找到 Keyword_brazil_rg 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-601">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="a7f02-602">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-602">The checksum passes.</span></span>

<span data-ttu-id="a7f02-603">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-603">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-604">函数 Func_brazil_rg 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-604">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-605">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-605">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-606">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-606">Keywords</span></span>

#### <a name="keywordbrazilrg"></a><span data-ttu-id="a7f02-607">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="a7f02-607">Keyword_brazil_rg</span></span>

<span data-ttu-id="a7f02-608">Cédula de identidade 身份证国家/地区 id número de rregistro registro de Iidentidade registro geral RG （此关键字是区分大小写） RIC （此关键字是区分大小写）</span><span class="sxs-lookup"><span data-stu-id="a7f02-608">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="a7f02-609">加拿大银行帐号</span><span class="sxs-lookup"><span data-stu-id="a7f02-609">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-610">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-610">Format</span></span>

<span data-ttu-id="a7f02-611">七个或十二个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-611">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-612">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-612">Pattern</span></span>

<span data-ttu-id="a7f02-613">加拿大银行帐号是七个或十二个数字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-613">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="a7f02-614">加拿大银行帐户的银行代号是：</span><span class="sxs-lookup"><span data-stu-id="a7f02-614">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="a7f02-615">五位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-615">Five digits</span></span> 
- <span data-ttu-id="a7f02-616">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="a7f02-616">A hyphen</span></span> 
- <span data-ttu-id="a7f02-617">三个数字或</span><span class="sxs-lookup"><span data-stu-id="a7f02-617">Three digits OR</span></span>
- <span data-ttu-id="a7f02-618">一个零“0” </span><span class="sxs-lookup"><span data-stu-id="a7f02-618">A zero "0"</span></span> 
- <span data-ttu-id="a7f02-619">八个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-619">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-620">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-620">Checksum</span></span>

<span data-ttu-id="a7f02-621">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-621">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-622">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-622">Definition</span></span>

<span data-ttu-id="a7f02-623">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-623">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-624">正则表达式 Regex_canada_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-624">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-625">找到 Keyword_canada_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-625">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="a7f02-626">正则表达式 Regex_canada_bank_account_transit_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-626">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="a7f02-627">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-627">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-628">正则表达式 Regex_canada_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-628">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-629">找到 Keyword_canada_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-629">A keyword from Keyword_canada_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-630">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-630">Keywords</span></span>

#### <a name="keywordcanadabankaccountnumber"></a><span data-ttu-id="a7f02-631">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="a7f02-631">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="a7f02-632">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="a7f02-632">canada savings bonds</span></span>
- <span data-ttu-id="a7f02-633">
canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="a7f02-633">canada revenue agency</span></span>
- <span data-ttu-id="a7f02-634">
canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="a7f02-634">canadian financial institution</span></span>
- <span data-ttu-id="a7f02-635">
direct deposit form</span><span class="sxs-lookup"><span data-stu-id="a7f02-635">direct deposit form</span></span>
- <span data-ttu-id="a7f02-636">
canadian citizen</span><span class="sxs-lookup"><span data-stu-id="a7f02-636">canadian citizen</span></span>
- <span data-ttu-id="a7f02-637">
legal representative</span><span class="sxs-lookup"><span data-stu-id="a7f02-637">legal representative</span></span>
- <span data-ttu-id="a7f02-638">
notary public</span><span class="sxs-lookup"><span data-stu-id="a7f02-638">notary public</span></span>
- <span data-ttu-id="a7f02-639">
commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="a7f02-639">commissioner for oaths</span></span>
- <span data-ttu-id="a7f02-640">
child care benefit</span><span class="sxs-lookup"><span data-stu-id="a7f02-640">child care benefit</span></span>
- <span data-ttu-id="a7f02-641">
universal child care</span><span class="sxs-lookup"><span data-stu-id="a7f02-641">universal child care</span></span>
- <span data-ttu-id="a7f02-642">
canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="a7f02-642">canada child tax benefit</span></span>
- <span data-ttu-id="a7f02-643">
income tax benefit</span><span class="sxs-lookup"><span data-stu-id="a7f02-643">income tax benefit</span></span>
- <span data-ttu-id="a7f02-644">
harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="a7f02-644">harmonized sales tax</span></span>
- <span data-ttu-id="a7f02-645">social insurance number</span><span class="sxs-lookup"><span data-stu-id="a7f02-645">social insurance number</span></span>
- <span data-ttu-id="a7f02-646">
income tax refund</span><span class="sxs-lookup"><span data-stu-id="a7f02-646">income tax refund</span></span>
- <span data-ttu-id="a7f02-647">
child tax benefit</span><span class="sxs-lookup"><span data-stu-id="a7f02-647">child tax benefit</span></span>
- <span data-ttu-id="a7f02-648">
territorial payments</span><span class="sxs-lookup"><span data-stu-id="a7f02-648">territorial payments</span></span>
- <span data-ttu-id="a7f02-649">
institution number</span><span class="sxs-lookup"><span data-stu-id="a7f02-649">institution number</span></span>
- <span data-ttu-id="a7f02-650">
deposit request</span><span class="sxs-lookup"><span data-stu-id="a7f02-650">deposit request</span></span>
- <span data-ttu-id="a7f02-651">
banking information</span><span class="sxs-lookup"><span data-stu-id="a7f02-651">banking information</span></span>
- <span data-ttu-id="a7f02-652">

direct deposit</span><span class="sxs-lookup"><span data-stu-id="a7f02-652">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="a7f02-653">加拿大驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-653">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-654">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-654">Format</span></span>

<span data-ttu-id="a7f02-655">因省而异</span><span class="sxs-lookup"><span data-stu-id="a7f02-655">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-656">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-656">Pattern</span></span>

<span data-ttu-id="a7f02-657">各种模式，涵盖艾伯塔、 不列颠哥伦比亚、 马尼托巴、 新不伦瑞克、 纽芬兰/拉布拉多、 新斯科舍、 安大略、 爱德华王子岛，魁北克和萨斯喀彻温</span><span class="sxs-lookup"><span data-stu-id="a7f02-657">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-658">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-658">Checksum</span></span>

<span data-ttu-id="a7f02-659">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-659">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-660">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-660">Definition</span></span>

<span data-ttu-id="a7f02-661">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-661">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-662">函数 Func_[province_name]_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-662">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-663">找到 Keyword_[province_name]_drivers_license_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-663">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="a7f02-664">找到 Keyword_canada_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-664">A keyword from Keyword_canada_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-665">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-665">Keywords</span></span>

#### <a name="keywordprovincenamedriverslicensename"></a><span data-ttu-id="a7f02-666">Keyword_[province_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="a7f02-666">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="a7f02-667">省/市/自治区的缩写，例如 AB</span><span class="sxs-lookup"><span data-stu-id="a7f02-667">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="a7f02-668">
省名称，例如 Alberta</span><span class="sxs-lookup"><span data-stu-id="a7f02-668">The province name, for example Alberta</span></span>

#### <a name="keywordcanadadriverslicense"></a><span data-ttu-id="a7f02-669">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="a7f02-669">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="a7f02-670">DL</span><span class="sxs-lookup"><span data-stu-id="a7f02-670">DL</span></span>
- <span data-ttu-id="a7f02-671">DLS</span><span class="sxs-lookup"><span data-stu-id="a7f02-671">DLS</span></span>
- <span data-ttu-id="a7f02-672">CDL</span><span class="sxs-lookup"><span data-stu-id="a7f02-672">CDL</span></span>
- <span data-ttu-id="a7f02-673">CDL</span><span class="sxs-lookup"><span data-stu-id="a7f02-673">CDLS</span></span>
- <span data-ttu-id="a7f02-674">DriverLic</span><span class="sxs-lookup"><span data-stu-id="a7f02-674">DriverLic</span></span>
- <span data-ttu-id="a7f02-675">DriverLics</span><span class="sxs-lookup"><span data-stu-id="a7f02-675">DriverLics</span></span>
- <span data-ttu-id="a7f02-676">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="a7f02-676">DriverLicense</span></span>
- <span data-ttu-id="a7f02-677">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="a7f02-677">DriverLicenses</span></span>
- <span data-ttu-id="a7f02-678">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="a7f02-678">DriverLicence</span></span>
- <span data-ttu-id="a7f02-679">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="a7f02-679">DriverLicences</span></span>
- <span data-ttu-id="a7f02-680">驱动程序 Lic</span><span class="sxs-lookup"><span data-stu-id="a7f02-680">Driver Lic</span></span>
- <span data-ttu-id="a7f02-681">驱动程序 Lics</span><span class="sxs-lookup"><span data-stu-id="a7f02-681">Driver Lics</span></span>
- <span data-ttu-id="a7f02-682">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="a7f02-682">Driver License</span></span>
- <span data-ttu-id="a7f02-683">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="a7f02-683">Driver Licenses</span></span>
- <span data-ttu-id="a7f02-684">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="a7f02-684">Driver Licence</span></span>
- <span data-ttu-id="a7f02-685">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="a7f02-685">Driver Licences</span></span>
- <span data-ttu-id="a7f02-686">DriversLic</span><span class="sxs-lookup"><span data-stu-id="a7f02-686">DriversLic</span></span>
- <span data-ttu-id="a7f02-687">DriversLics</span><span class="sxs-lookup"><span data-stu-id="a7f02-687">DriversLics</span></span>
- <span data-ttu-id="a7f02-688">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="a7f02-688">DriversLicence</span></span>
- <span data-ttu-id="a7f02-689">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="a7f02-689">DriversLicences</span></span>
- <span data-ttu-id="a7f02-690">驾驶员</span><span class="sxs-lookup"><span data-stu-id="a7f02-690">DriversLicense</span></span>
- <span data-ttu-id="a7f02-691">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="a7f02-691">DriversLicenses</span></span>
- <span data-ttu-id="a7f02-692">驱动因素 Lic</span><span class="sxs-lookup"><span data-stu-id="a7f02-692">Drivers Lic</span></span>
- <span data-ttu-id="a7f02-693">驱动因素 Lics</span><span class="sxs-lookup"><span data-stu-id="a7f02-693">Drivers Lics</span></span>
- <span data-ttu-id="a7f02-694">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="a7f02-694">Drivers License</span></span>
- <span data-ttu-id="a7f02-695">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="a7f02-695">Drivers Licenses</span></span>
- <span data-ttu-id="a7f02-696">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="a7f02-696">Drivers Licence</span></span>
- <span data-ttu-id="a7f02-697">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="a7f02-697">Drivers Licences</span></span>
- <span data-ttu-id="a7f02-698">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="a7f02-698">Driver'Lic</span></span>
- <span data-ttu-id="a7f02-699">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="a7f02-699">Driver'Lics</span></span>
- <span data-ttu-id="a7f02-700">Driver'License</span><span class="sxs-lookup"><span data-stu-id="a7f02-700">Driver'License</span></span>
- <span data-ttu-id="a7f02-701">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="a7f02-701">Driver'Licenses</span></span>
- <span data-ttu-id="a7f02-702">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="a7f02-702">Driver'Licence</span></span>
- <span data-ttu-id="a7f02-703">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="a7f02-703">Driver'Licences</span></span>
- <span data-ttu-id="a7f02-704">驱动因素 Lic</span><span class="sxs-lookup"><span data-stu-id="a7f02-704">Driver' Lic</span></span>
- <span data-ttu-id="a7f02-705">驱动因素 Lics</span><span class="sxs-lookup"><span data-stu-id="a7f02-705">Driver' Lics</span></span>
- <span data-ttu-id="a7f02-706">驱动因素许可证</span><span class="sxs-lookup"><span data-stu-id="a7f02-706">Driver' License</span></span>
- <span data-ttu-id="a7f02-707">驱动因素许可证</span><span class="sxs-lookup"><span data-stu-id="a7f02-707">Driver' Licenses</span></span>
- <span data-ttu-id="a7f02-708">驱动因素许可</span><span class="sxs-lookup"><span data-stu-id="a7f02-708">Driver' Licence</span></span>
- <span data-ttu-id="a7f02-709">驱动因素许可</span><span class="sxs-lookup"><span data-stu-id="a7f02-709">Driver' Licences</span></span>
- <span data-ttu-id="a7f02-710">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="a7f02-710">Driver'sLic</span></span>
- <span data-ttu-id="a7f02-711">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="a7f02-711">Driver'sLics</span></span>
- <span data-ttu-id="a7f02-712">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="a7f02-712">Driver'sLicense</span></span>
- <span data-ttu-id="a7f02-713">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="a7f02-713">Driver'sLicenses</span></span>
- <span data-ttu-id="a7f02-714">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="a7f02-714">Driver'sLicence</span></span>
- <span data-ttu-id="a7f02-715">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="a7f02-715">Driver'sLicences</span></span>
- <span data-ttu-id="a7f02-716">驱动因素的 Lic</span><span class="sxs-lookup"><span data-stu-id="a7f02-716">Driver's Lic</span></span>
- <span data-ttu-id="a7f02-717">驱动因素的 Lics</span><span class="sxs-lookup"><span data-stu-id="a7f02-717">Driver's Lics</span></span>
- <span data-ttu-id="a7f02-718">驱动程序的许可证</span><span class="sxs-lookup"><span data-stu-id="a7f02-718">Driver's License</span></span>
- <span data-ttu-id="a7f02-719">驱动程序的许可证</span><span class="sxs-lookup"><span data-stu-id="a7f02-719">Driver's Licenses</span></span>
- <span data-ttu-id="a7f02-720">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="a7f02-720">Driver's Licence</span></span>
- <span data-ttu-id="a7f02-721">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="a7f02-721">Driver's Licences</span></span>
- <span data-ttu-id="a7f02-722">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="a7f02-722">Permis de Conduire</span></span>
- <span data-ttu-id="a7f02-723">id</span><span class="sxs-lookup"><span data-stu-id="a7f02-723">id</span></span>
- <span data-ttu-id="a7f02-724">id</span><span class="sxs-lookup"><span data-stu-id="a7f02-724">ids</span></span>
- <span data-ttu-id="a7f02-725">
idcard number</span><span class="sxs-lookup"><span data-stu-id="a7f02-725">idcard number</span></span>
- <span data-ttu-id="a7f02-726">
idcard numbers</span><span class="sxs-lookup"><span data-stu-id="a7f02-726">idcard numbers</span></span>
- <span data-ttu-id="a7f02-727">
idcard #</span><span class="sxs-lookup"><span data-stu-id="a7f02-727">idcard #</span></span>
- <span data-ttu-id="a7f02-728">
idcard #s</span><span class="sxs-lookup"><span data-stu-id="a7f02-728">idcard #s</span></span>
- <span data-ttu-id="a7f02-729">idcard 卡片</span><span class="sxs-lookup"><span data-stu-id="a7f02-729">idcard card</span></span>
- <span data-ttu-id="a7f02-730">idcard 卡</span><span class="sxs-lookup"><span data-stu-id="a7f02-730">idcard cards</span></span>
- <span data-ttu-id="a7f02-731">idcard</span><span class="sxs-lookup"><span data-stu-id="a7f02-731">idcard</span></span>
- <span data-ttu-id="a7f02-732">identification number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-732">identification number</span></span>
- <span data-ttu-id="a7f02-733">identification numbers
</span><span class="sxs-lookup"><span data-stu-id="a7f02-733">identification numbers</span></span>
- <span data-ttu-id="a7f02-734">identification #
</span><span class="sxs-lookup"><span data-stu-id="a7f02-734">identification #</span></span>
- <span data-ttu-id="a7f02-735">
identification #s</span><span class="sxs-lookup"><span data-stu-id="a7f02-735">identification #s</span></span>
- <span data-ttu-id="a7f02-736">身份证</span><span class="sxs-lookup"><span data-stu-id="a7f02-736">identification card</span></span>
- <span data-ttu-id="a7f02-737">身份证</span><span class="sxs-lookup"><span data-stu-id="a7f02-737">identification cards</span></span>
- <span data-ttu-id="a7f02-738">
identification
</span><span class="sxs-lookup"><span data-stu-id="a7f02-738">identification</span></span> 
- <span data-ttu-id="a7f02-739">DL#</span><span class="sxs-lookup"><span data-stu-id="a7f02-739">DL#</span></span>
- <span data-ttu-id="a7f02-740">
DLS#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-740">DLS#</span></span> 
- <span data-ttu-id="a7f02-741">CDL#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-741">CDL#</span></span> 
- <span data-ttu-id="a7f02-742">CDLS#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-742">CDLS#</span></span> 
- <span data-ttu-id="a7f02-743">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="a7f02-743">DriverLic#</span></span> 
- <span data-ttu-id="a7f02-744">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="a7f02-744">DriverLics#</span></span> 
- <span data-ttu-id="a7f02-745">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="a7f02-745">DriverLicense#</span></span> 
- <span data-ttu-id="a7f02-746">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="a7f02-746">DriverLicenses#</span></span> 
- <span data-ttu-id="a7f02-747">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="a7f02-747">DriverLicence#</span></span> 
- <span data-ttu-id="a7f02-748">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="a7f02-748">DriverLicences#</span></span> 
- <span data-ttu-id="a7f02-749">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="a7f02-749">Driver Lic#</span></span>
- <span data-ttu-id="a7f02-750">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-750">Driver Lics#</span></span> 
- <span data-ttu-id="a7f02-751">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="a7f02-751">Driver License#</span></span> 
- <span data-ttu-id="a7f02-752">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="a7f02-752">Driver Licenses#</span></span> 
- <span data-ttu-id="a7f02-753">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="a7f02-753">Driver License#</span></span> 
- <span data-ttu-id="a7f02-754">驱动程序许可 #</span><span class="sxs-lookup"><span data-stu-id="a7f02-754">Driver Licences#</span></span> 
- <span data-ttu-id="a7f02-755">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="a7f02-755">DriversLic#</span></span> 
- <span data-ttu-id="a7f02-756">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="a7f02-756">DriversLics#</span></span> 
- <span data-ttu-id="a7f02-757">驾驶员 #</span><span class="sxs-lookup"><span data-stu-id="a7f02-757">DriversLicense#</span></span> 
- <span data-ttu-id="a7f02-758">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="a7f02-758">DriversLicenses#</span></span> 
- <span data-ttu-id="a7f02-759">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="a7f02-759">DriversLicence#</span></span> 
- <span data-ttu-id="a7f02-760">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="a7f02-760">DriversLicences#</span></span> 
- <span data-ttu-id="a7f02-761">驱动因素 Lic #</span><span class="sxs-lookup"><span data-stu-id="a7f02-761">Drivers Lic#</span></span> 
- <span data-ttu-id="a7f02-762">驱动因素 Lics #</span><span class="sxs-lookup"><span data-stu-id="a7f02-762">Drivers Lics#</span></span> 
- <span data-ttu-id="a7f02-763">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="a7f02-763">Drivers License#</span></span> 
- <span data-ttu-id="a7f02-764">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="a7f02-764">Drivers Licenses#</span></span> 
- <span data-ttu-id="a7f02-765">驱动因素许可 #</span><span class="sxs-lookup"><span data-stu-id="a7f02-765">Drivers Licence#</span></span> 
- <span data-ttu-id="a7f02-766">驱动因素许可 #</span><span class="sxs-lookup"><span data-stu-id="a7f02-766">Drivers Licences#</span></span> 
- <span data-ttu-id="a7f02-767">Driver'Lic#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-767">Driver'Lic#</span></span> 
- <span data-ttu-id="a7f02-768">Driver'Lics#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-768">Driver'Lics#</span></span> 
- <span data-ttu-id="a7f02-769">Driver'License#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-769">Driver'License#</span></span> 
- <span data-ttu-id="a7f02-770">Driver'Licenses#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-770">Driver'Licenses#</span></span> 
- <span data-ttu-id="a7f02-771">Driver'Licence#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-771">Driver'Licence#</span></span> 
- <span data-ttu-id="a7f02-772">Driver'Licences#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-772">Driver'Licences#</span></span> 
- <span data-ttu-id="a7f02-773">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-773">Driver' Lic#</span></span> 
- <span data-ttu-id="a7f02-774">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-774">Driver' Lics#</span></span> 
- <span data-ttu-id="a7f02-775">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-775">Driver' License#</span></span> 
- <span data-ttu-id="a7f02-776">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-776">Driver' Licenses#</span></span> 
- <span data-ttu-id="a7f02-777">驱动因素许可 #</span><span class="sxs-lookup"><span data-stu-id="a7f02-777">Driver' Licence#</span></span> 
- <span data-ttu-id="a7f02-778">驱动因素许可 #</span><span class="sxs-lookup"><span data-stu-id="a7f02-778">Driver' Licences#</span></span> 
- <span data-ttu-id="a7f02-779">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="a7f02-779">Driver'sLic#</span></span> 
- <span data-ttu-id="a7f02-780">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="a7f02-780">Driver'sLics#</span></span> 
- <span data-ttu-id="a7f02-781">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="a7f02-781">Driver'sLicense#</span></span> 
- <span data-ttu-id="a7f02-782">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="a7f02-782">Driver'sLicenses#</span></span> 
- <span data-ttu-id="a7f02-783">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="a7f02-783">Driver'sLicence#</span></span> 
- <span data-ttu-id="a7f02-784">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="a7f02-784">Driver'sLicences#</span></span> 
- <span data-ttu-id="a7f02-785">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-785">Driver's Lic#</span></span> 
- <span data-ttu-id="a7f02-786">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-786">Driver's Lics#</span></span> 
- <span data-ttu-id="a7f02-787">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-787">Driver's License#</span></span> 
- <span data-ttu-id="a7f02-788">Driver's Licenses#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-788">Driver's Licenses#</span></span> 
- <span data-ttu-id="a7f02-789">驱动程序的许可 #</span><span class="sxs-lookup"><span data-stu-id="a7f02-789">Driver's Licence#</span></span> 
- <span data-ttu-id="a7f02-790">驱动程序的许可 #</span><span class="sxs-lookup"><span data-stu-id="a7f02-790">Driver's Licences#</span></span> 
- <span data-ttu-id="a7f02-791">Permis de Conduire #</span><span class="sxs-lookup"><span data-stu-id="a7f02-791">Permis de Conduire#</span></span> 
- <span data-ttu-id="a7f02-792">id #</span><span class="sxs-lookup"><span data-stu-id="a7f02-792">id#</span></span> 
- <span data-ttu-id="a7f02-793">id #</span><span class="sxs-lookup"><span data-stu-id="a7f02-793">ids#</span></span> 
- <span data-ttu-id="a7f02-794">idcard card#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-794">idcard card#</span></span> 
- <span data-ttu-id="a7f02-795">idcard cards#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-795">idcard cards#</span></span> 
- <span data-ttu-id="a7f02-796">idcard#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-796">idcard#</span></span> 
- <span data-ttu-id="a7f02-797">identification card#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-797">identification card#</span></span> 
- <span data-ttu-id="a7f02-798">identification cards#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-798">identification cards#</span></span> 
- <span data-ttu-id="a7f02-799">identification#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-799">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="a7f02-800">加拿大卫生服务号</span><span class="sxs-lookup"><span data-stu-id="a7f02-800">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-801">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-801">Format</span></span>

<span data-ttu-id="a7f02-802">10 个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-802">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-803">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-803">Pattern</span></span>

<span data-ttu-id="a7f02-804">10 个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-804">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-805">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-805">Checksum</span></span>

<span data-ttu-id="a7f02-806">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-806">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-807">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-807">Definition</span></span>

<span data-ttu-id="a7f02-808">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-808">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-809">正则表达式 Regex_canada_health_service_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-809">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-810">找到 Keyword_canada_health_service_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-810">A keyword from Keyword_canada_health_service_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-811">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-811">Keywords</span></span>

#### <a name="keywordcanadahealthservicenumber"></a><span data-ttu-id="a7f02-812">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="a7f02-812">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="a7f02-813">personal health number</span><span class="sxs-lookup"><span data-stu-id="a7f02-813">personal health number</span></span>
- <span data-ttu-id="a7f02-814">
patient information</span><span class="sxs-lookup"><span data-stu-id="a7f02-814">patient information</span></span>
- <span data-ttu-id="a7f02-815">运行状况服务</span><span class="sxs-lookup"><span data-stu-id="a7f02-815">health services</span></span>
- <span data-ttu-id="a7f02-816">
speciality services</span><span class="sxs-lookup"><span data-stu-id="a7f02-816">speciality services</span></span>
- <span data-ttu-id="a7f02-817">
automobile accident</span><span class="sxs-lookup"><span data-stu-id="a7f02-817">automobile accident</span></span>
- <span data-ttu-id="a7f02-818">
patient hospital</span><span class="sxs-lookup"><span data-stu-id="a7f02-818">patient hospital</span></span>
- <span data-ttu-id="a7f02-819">
psychiatrist</span><span class="sxs-lookup"><span data-stu-id="a7f02-819">psychiatrist</span></span>
- <span data-ttu-id="a7f02-820">
workers compensation</span><span class="sxs-lookup"><span data-stu-id="a7f02-820">workers compensation</span></span>
- <span data-ttu-id="a7f02-821">
disability</span><span class="sxs-lookup"><span data-stu-id="a7f02-821">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="a7f02-822">加拿大护照号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-822">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-823">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-823">Format</span></span>

<span data-ttu-id="a7f02-824">两个大写字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-824">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-825">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-825">Pattern</span></span>

<span data-ttu-id="a7f02-826">两个大写字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-826">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-827">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-827">Checksum</span></span>

<span data-ttu-id="a7f02-828">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-828">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-829">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-829">Definition</span></span>

<span data-ttu-id="a7f02-830">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-830">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-831">正则表达式 Regex_canada_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-831">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-832">找到从 Keyword_canada_passport_number 或 Keyword_passport 关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-832">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-833">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-833">Keywords</span></span>

#### <a name="keywordcanadapassportnumber"></a><span data-ttu-id="a7f02-834">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="a7f02-834">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="a7f02-835">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="a7f02-835">canadian citizenship</span></span>
- <span data-ttu-id="a7f02-836">
canadian passport</span><span class="sxs-lookup"><span data-stu-id="a7f02-836">canadian passport</span></span>
- <span data-ttu-id="a7f02-837">
passport application</span><span class="sxs-lookup"><span data-stu-id="a7f02-837">passport application</span></span>
- <span data-ttu-id="a7f02-838">
passport photos</span><span class="sxs-lookup"><span data-stu-id="a7f02-838">passport photos</span></span>
- <span data-ttu-id="a7f02-839">
certified translator</span><span class="sxs-lookup"><span data-stu-id="a7f02-839">certified translator</span></span>
- <span data-ttu-id="a7f02-840">
canadian citizens</span><span class="sxs-lookup"><span data-stu-id="a7f02-840">canadian citizens</span></span>
- <span data-ttu-id="a7f02-841">
processing times</span><span class="sxs-lookup"><span data-stu-id="a7f02-841">processing times</span></span>
- <span data-ttu-id="a7f02-842">

renewal application</span><span class="sxs-lookup"><span data-stu-id="a7f02-842">renewal application</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="a7f02-843">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="a7f02-843">Keyword_passport</span></span>

- <span data-ttu-id="a7f02-844">Passport Number</span><span class="sxs-lookup"><span data-stu-id="a7f02-844">Passport Number</span></span>
- <span data-ttu-id="a7f02-845">
Passport No</span><span class="sxs-lookup"><span data-stu-id="a7f02-845">Passport No</span></span>
- <span data-ttu-id="a7f02-846">Passport #
</span><span class="sxs-lookup"><span data-stu-id="a7f02-846">Passport #</span></span>
- <span data-ttu-id="a7f02-847">Passport#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-847">Passport#</span></span>
- <span data-ttu-id="a7f02-848">PassportID</span><span class="sxs-lookup"><span data-stu-id="a7f02-848">PassportID</span></span>
- <span data-ttu-id="a7f02-849">Passportno
</span><span class="sxs-lookup"><span data-stu-id="a7f02-849">Passportno</span></span>
- <span data-ttu-id="a7f02-850">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="a7f02-850">passportnumber</span></span>
- <span data-ttu-id="a7f02-851">パスポート</span><span class="sxs-lookup"><span data-stu-id="a7f02-851">パスポート</span></span>
- <span data-ttu-id="a7f02-852">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="a7f02-852">パスポート番号</span></span>
- <span data-ttu-id="a7f02-853">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="a7f02-853">パスポートのNum</span></span>
- <span data-ttu-id="a7f02-854">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="a7f02-854">パスポート＃</span></span>
- <span data-ttu-id="a7f02-855">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="a7f02-855">Numéro de passeport</span></span>
- <span data-ttu-id="a7f02-856">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="a7f02-856">Passeport n °</span></span>
- <span data-ttu-id="a7f02-857">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="a7f02-857">Passeport Non</span></span>
- <span data-ttu-id="a7f02-858">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="a7f02-858">Passeport #</span></span>
- <span data-ttu-id="a7f02-859">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-859">Passeport#</span></span>
- <span data-ttu-id="a7f02-860">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="a7f02-860">PasseportNon</span></span>
- <span data-ttu-id="a7f02-861">

Passeportn °</span><span class="sxs-lookup"><span data-stu-id="a7f02-861">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="a7f02-862">加拿大个人健康标识号 (PHIN)</span><span class="sxs-lookup"><span data-stu-id="a7f02-862">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-863">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-863">Format</span></span>

<span data-ttu-id="a7f02-864">九个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-864">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-865">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-865">Pattern</span></span>

<span data-ttu-id="a7f02-866">九个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-866">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-867">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-867">Checksum</span></span>

<span data-ttu-id="a7f02-868">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-868">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-869">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-869">Definition</span></span>

<span data-ttu-id="a7f02-p104">DLP 策略是相信它已检测到此类型的敏感信息的 75 %if、 内 300 个字符的邻近度： 正则表达式 Regex_canada_phin 找到与模式匹配的内容。找到来自 Keyword_canada_phin 或 Keyword_canada_provinces 至少两个关键字正在</span><span class="sxs-lookup"><span data-stu-id="a7f02-p104">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern. At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-872">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-872">Keywords</span></span>

#### <a name="keywordcanadaphin"></a><span data-ttu-id="a7f02-873">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="a7f02-873">Keyword_canada_phin</span></span>

- <span data-ttu-id="a7f02-874">social insurance number</span><span class="sxs-lookup"><span data-stu-id="a7f02-874">social insurance number</span></span>
- <span data-ttu-id="a7f02-875">
health information act</span><span class="sxs-lookup"><span data-stu-id="a7f02-875">health information act</span></span>
- <span data-ttu-id="a7f02-876">
income tax information</span><span class="sxs-lookup"><span data-stu-id="a7f02-876">income tax information</span></span>
- <span data-ttu-id="a7f02-877">
manitoba health</span><span class="sxs-lookup"><span data-stu-id="a7f02-877">manitoba health</span></span>
- <span data-ttu-id="a7f02-878">
health registration</span><span class="sxs-lookup"><span data-stu-id="a7f02-878">health registration</span></span>
- <span data-ttu-id="a7f02-879">
prescription purchases</span><span class="sxs-lookup"><span data-stu-id="a7f02-879">prescription purchases</span></span>
- <span data-ttu-id="a7f02-880">
benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="a7f02-880">benefit eligibility</span></span>
- <span data-ttu-id="a7f02-881">
personal health</span><span class="sxs-lookup"><span data-stu-id="a7f02-881">personal health</span></span>
- <span data-ttu-id="a7f02-882">
power of attorney</span><span class="sxs-lookup"><span data-stu-id="a7f02-882">power of attorney</span></span>
- <span data-ttu-id="a7f02-883">
registration number</span><span class="sxs-lookup"><span data-stu-id="a7f02-883">registration number</span></span>
- <span data-ttu-id="a7f02-884">personal health number</span><span class="sxs-lookup"><span data-stu-id="a7f02-884">personal health number</span></span>
- <span data-ttu-id="a7f02-885">
practitioner referral</span><span class="sxs-lookup"><span data-stu-id="a7f02-885">practitioner referral</span></span>
- <span data-ttu-id="a7f02-886">
wellness professional</span><span class="sxs-lookup"><span data-stu-id="a7f02-886">wellness professional</span></span>
- <span data-ttu-id="a7f02-887">
patient referral</span><span class="sxs-lookup"><span data-stu-id="a7f02-887">patient referral</span></span>
- <span data-ttu-id="a7f02-888">

health and wellness</span><span class="sxs-lookup"><span data-stu-id="a7f02-888">health and wellness</span></span>

#### <a name="keywordcanadaprovinces"></a><span data-ttu-id="a7f02-889">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="a7f02-889">Keyword_canada_provinces</span></span>

- <span data-ttu-id="a7f02-890">Nunavut</span><span class="sxs-lookup"><span data-stu-id="a7f02-890">Nunavut</span></span>
- <span data-ttu-id="a7f02-891">
Quebec</span><span class="sxs-lookup"><span data-stu-id="a7f02-891">Quebec</span></span>
- <span data-ttu-id="a7f02-892">
Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="a7f02-892">Northwest Territories</span></span>
- <span data-ttu-id="a7f02-893">
Ontario</span><span class="sxs-lookup"><span data-stu-id="a7f02-893">Ontario</span></span>
- <span data-ttu-id="a7f02-894">
British Columbia</span><span class="sxs-lookup"><span data-stu-id="a7f02-894">British Columbia</span></span>
- <span data-ttu-id="a7f02-895">
Alberta</span><span class="sxs-lookup"><span data-stu-id="a7f02-895">Alberta</span></span>
- <span data-ttu-id="a7f02-896">
Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="a7f02-896">Saskatchewan</span></span>
- <span data-ttu-id="a7f02-897">
Manitoba</span><span class="sxs-lookup"><span data-stu-id="a7f02-897">Manitoba</span></span>
- <span data-ttu-id="a7f02-898">
Yukon</span><span class="sxs-lookup"><span data-stu-id="a7f02-898">Yukon</span></span>
- <span data-ttu-id="a7f02-899">
Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="a7f02-899">Newfoundland and Labrador</span></span>
- <span data-ttu-id="a7f02-900">
New Brunswick</span><span class="sxs-lookup"><span data-stu-id="a7f02-900">New Brunswick</span></span>
- <span data-ttu-id="a7f02-901">
Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="a7f02-901">Nova Scotia</span></span>
- <span data-ttu-id="a7f02-902">
Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="a7f02-902">Prince Edward Island</span></span>
- <span data-ttu-id="a7f02-903">加拿大</span><span class="sxs-lookup"><span data-stu-id="a7f02-903">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="a7f02-904">加拿大社会保险号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-904">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-905">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-905">Format</span></span>

<span data-ttu-id="a7f02-906">九个数字，包含可选连字符或空格</span><span class="sxs-lookup"><span data-stu-id="a7f02-906">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-907">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-907">Pattern</span></span>

<span data-ttu-id="a7f02-908">有格式模式：</span><span class="sxs-lookup"><span data-stu-id="a7f02-908">Formatted:</span></span>
- <span data-ttu-id="a7f02-909">三位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-909">Three digits</span></span> 
- <span data-ttu-id="a7f02-910">连字符或空格</span><span class="sxs-lookup"><span data-stu-id="a7f02-910">A hyphen or space</span></span> 
- <span data-ttu-id="a7f02-911">三位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-911">Three digits</span></span> 
- <span data-ttu-id="a7f02-912">连字符或空格</span><span class="sxs-lookup"><span data-stu-id="a7f02-912">A hyphen or space</span></span> 
- <span data-ttu-id="a7f02-913">三位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-913">Three digits</span></span>

<span data-ttu-id="a7f02-914">未格式化： 九个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-914">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-915">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-915">Checksum</span></span>

<span data-ttu-id="a7f02-916">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-916">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-917">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-917">Definition</span></span>

<span data-ttu-id="a7f02-918">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-918">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-919">函数 Func_canadian_sin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-919">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-920">至少两个以下任意组合：</span><span class="sxs-lookup"><span data-stu-id="a7f02-920">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="a7f02-921">找到 Keyword_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-921">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="a7f02-922">找到 Keyword_sin_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-922">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="a7f02-923">函数 Func_eu_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="a7f02-923">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="a7f02-924">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-924">The checksum passes.</span></span>

<span data-ttu-id="a7f02-925">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-925">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-926">函数 Func_unformatted_canadian_sin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-926">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-927">找到 Keyword_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-927">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="a7f02-928">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-928">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-929">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-929">Keywords</span></span>

#### <a name="keywordsin"></a><span data-ttu-id="a7f02-930">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="a7f02-930">Keyword_sin</span></span>

- <span data-ttu-id="a7f02-931">sin</span><span class="sxs-lookup"><span data-stu-id="a7f02-931">sin</span></span> 
- <span data-ttu-id="a7f02-932">social insurance
</span><span class="sxs-lookup"><span data-stu-id="a7f02-932">social insurance</span></span> 
- <span data-ttu-id="a7f02-933">numero d'assurance sociale
</span><span class="sxs-lookup"><span data-stu-id="a7f02-933">numero d'assurance sociale</span></span> 
- <span data-ttu-id="a7f02-934">sins
</span><span class="sxs-lookup"><span data-stu-id="a7f02-934">sins</span></span> 
- <span data-ttu-id="a7f02-935">ssn</span><span class="sxs-lookup"><span data-stu-id="a7f02-935">ssn</span></span> 
- <span data-ttu-id="a7f02-936">ssn</span><span class="sxs-lookup"><span data-stu-id="a7f02-936">ssns</span></span> 
- <span data-ttu-id="a7f02-937">社会安全</span><span class="sxs-lookup"><span data-stu-id="a7f02-937">social security</span></span> 
- <span data-ttu-id="a7f02-938">numero d'assurance social
</span><span class="sxs-lookup"><span data-stu-id="a7f02-938">numero d'assurance social</span></span> 
- <span data-ttu-id="a7f02-939">国家/地区标识号</span><span class="sxs-lookup"><span data-stu-id="a7f02-939">national identification number</span></span> 
- <span data-ttu-id="a7f02-940">
national id</span><span class="sxs-lookup"><span data-stu-id="a7f02-940">national id</span></span> 
- <span data-ttu-id="a7f02-941">sin#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-941">sin#</span></span> 
- <span data-ttu-id="a7f02-942">soc ins
</span><span class="sxs-lookup"><span data-stu-id="a7f02-942">soc ins</span></span> 
- <span data-ttu-id="a7f02-943">social ins
</span><span class="sxs-lookup"><span data-stu-id="a7f02-943">social ins</span></span> 

#### <a name="keywordsincollaborative"></a><span data-ttu-id="a7f02-944">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="a7f02-944">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="a7f02-945">driver's license</span><span class="sxs-lookup"><span data-stu-id="a7f02-945">driver's license</span></span> 
- <span data-ttu-id="a7f02-946">drivers license</span><span class="sxs-lookup"><span data-stu-id="a7f02-946">drivers license</span></span> 
- <span data-ttu-id="a7f02-947">驱动程序的许可</span><span class="sxs-lookup"><span data-stu-id="a7f02-947">driver's licence</span></span> 
- <span data-ttu-id="a7f02-948">drivers licence</span><span class="sxs-lookup"><span data-stu-id="a7f02-948">drivers licence</span></span> 
- <span data-ttu-id="a7f02-949">DOB
</span><span class="sxs-lookup"><span data-stu-id="a7f02-949">DOB</span></span> 
- <span data-ttu-id="a7f02-950">出生日期</span><span class="sxs-lookup"><span data-stu-id="a7f02-950">Birthdate</span></span> 
- <span data-ttu-id="a7f02-951">生日 </span><span class="sxs-lookup"><span data-stu-id="a7f02-951">Birthday</span></span> 
- <span data-ttu-id="a7f02-952">Date of Birth
</span><span class="sxs-lookup"><span data-stu-id="a7f02-952">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="a7f02-953">	智利身份证号</span><span class="sxs-lookup"><span data-stu-id="a7f02-953">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-954">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-954">Format</span></span>

<span data-ttu-id="a7f02-955">7-8 数字以及定界符复选数字或字母</span><span class="sxs-lookup"><span data-stu-id="a7f02-955">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-956">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-956">Pattern</span></span>

<span data-ttu-id="a7f02-957">7-8 个数字加分隔符：</span><span class="sxs-lookup"><span data-stu-id="a7f02-957">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="a7f02-958">1-2 个数字 </span><span class="sxs-lookup"><span data-stu-id="a7f02-958">1-2 digits</span></span> 
- <span data-ttu-id="a7f02-959">一个点 </span><span class="sxs-lookup"><span data-stu-id="a7f02-959">A period</span></span> 
- <span data-ttu-id="a7f02-960">三个数字 </span><span class="sxs-lookup"><span data-stu-id="a7f02-960">Three digits</span></span> 
- <span data-ttu-id="a7f02-961">一个点 </span><span class="sxs-lookup"><span data-stu-id="a7f02-961">A period</span></span> 
- <span data-ttu-id="a7f02-962">三个数字 </span><span class="sxs-lookup"><span data-stu-id="a7f02-962">Three digits</span></span> 
- <span data-ttu-id="a7f02-963">一个短划线 </span><span class="sxs-lookup"><span data-stu-id="a7f02-963">A dash</span></span> 
- <span data-ttu-id="a7f02-964">一个数字或字母（不区分大小写），是校验位</span><span class="sxs-lookup"><span data-stu-id="a7f02-964">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-965">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-965">Checksum</span></span>

<span data-ttu-id="a7f02-966">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-967">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-967">Definition</span></span>

<span data-ttu-id="a7f02-968">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-969">函数 Func_chile_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-969">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-970">找到 Keyword_chile_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-970">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="a7f02-971">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-971">The checksum passes.</span></span>

<span data-ttu-id="a7f02-972">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-972">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-973">函数 Func_chile_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-973">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-974">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-974">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-975">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-975">Keywords</span></span>

#### <a name="keywordchileidcard"></a><span data-ttu-id="a7f02-976">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="a7f02-976">Keyword_chile_id_card</span></span>

- <span data-ttu-id="a7f02-977">National Identification Number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-977">National Identification Number</span></span> 
- <span data-ttu-id="a7f02-978">Identity card</span><span class="sxs-lookup"><span data-stu-id="a7f02-978">Identity card</span></span> 
- <span data-ttu-id="a7f02-979">ID</span><span class="sxs-lookup"><span data-stu-id="a7f02-979">ID</span></span> 
- <span data-ttu-id="a7f02-980">Identification</span><span class="sxs-lookup"><span data-stu-id="a7f02-980">Identification</span></span> 
- <span data-ttu-id="a7f02-981">Rol Único Nacional
</span><span class="sxs-lookup"><span data-stu-id="a7f02-981">Rol Único Nacional</span></span> 
- <span data-ttu-id="a7f02-982">运行</span><span class="sxs-lookup"><span data-stu-id="a7f02-982">RUN</span></span> 
- <span data-ttu-id="a7f02-983">Rol Único Tributario
</span><span class="sxs-lookup"><span data-stu-id="a7f02-983">Rol Único Tributario</span></span> 
- <span data-ttu-id="a7f02-984">RUT
</span><span class="sxs-lookup"><span data-stu-id="a7f02-984">RUT</span></span> 
- <span data-ttu-id="a7f02-985">Cédula de Identidad
</span><span class="sxs-lookup"><span data-stu-id="a7f02-985">Cédula de Identidad</span></span> 
- <span data-ttu-id="a7f02-986">Número De Identificación Nacional
</span><span class="sxs-lookup"><span data-stu-id="a7f02-986">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="a7f02-987">Tarjeta de identificación
</span><span class="sxs-lookup"><span data-stu-id="a7f02-987">Tarjeta de identificación</span></span> 
- <span data-ttu-id="a7f02-988">Identificación
</span><span class="sxs-lookup"><span data-stu-id="a7f02-988">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="a7f02-989">	中国居民身份证号</span><span class="sxs-lookup"><span data-stu-id="a7f02-989">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-990">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-990">Format</span></span>

<span data-ttu-id="a7f02-991">18 个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-991">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-992">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-992">Pattern</span></span>

<span data-ttu-id="a7f02-993">18 个数字：</span><span class="sxs-lookup"><span data-stu-id="a7f02-993">18 digits:</span></span>
- <span data-ttu-id="a7f02-994">其中六个数字是地址代码 </span><span class="sxs-lookup"><span data-stu-id="a7f02-994">Six digits which are an address code</span></span> 
- <span data-ttu-id="a7f02-995">八个数字，采用  YYYYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="a7f02-995">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="a7f02-996">三个数字，是顺序代码 </span><span class="sxs-lookup"><span data-stu-id="a7f02-996">Three digits which are an order code</span></span> 
- <span data-ttu-id="a7f02-997">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="a7f02-997">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-998">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-998">Checksum</span></span>

<span data-ttu-id="a7f02-999">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-999">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-1000">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-1000">Definition</span></span>

<span data-ttu-id="a7f02-1001">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1001">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-1002">函数 Func_china_resident_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1002">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-1003">找到 Keyword_china_resident_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1003">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="a7f02-1004">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1004">The checksum passes.</span></span>

<span data-ttu-id="a7f02-1005">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1005">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-1006">函数 Func_china_resident_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1006">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-1007">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1007">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-1008">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1008">Keywords</span></span>

### <a name="keywordchinaresidentid"></a><span data-ttu-id="a7f02-1009">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="a7f02-1009">Keyword_china_resident_id</span></span>

- <span data-ttu-id="a7f02-1010">Resident Identity Card
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1010">Resident Identity Card</span></span> 
- <span data-ttu-id="a7f02-1011">PRC
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1011">PRC</span></span> 
- <span data-ttu-id="a7f02-1012">National Identification Card
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1012">National Identification Card</span></span> 
- <span data-ttu-id="a7f02-1013">身份证 </span><span class="sxs-lookup"><span data-stu-id="a7f02-1013">身份证</span></span> 
- <span data-ttu-id="a7f02-1014">居民 身份证 </span><span class="sxs-lookup"><span data-stu-id="a7f02-1014">居民 身份证</span></span> 
- <span data-ttu-id="a7f02-1015">居民身份证
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1015">居民身份证</span></span> 
- <span data-ttu-id="a7f02-1016">鉴定

</span><span class="sxs-lookup"><span data-stu-id="a7f02-1016">鉴定</span></span> 
- <span data-ttu-id="a7f02-1017">身分證 </span><span class="sxs-lookup"><span data-stu-id="a7f02-1017">身分證</span></span> 
- <span data-ttu-id="a7f02-1018">居民身份證</span><span class="sxs-lookup"><span data-stu-id="a7f02-1018">居民 身份證</span></span>
- <span data-ttu-id="a7f02-1019">鑑定 </span><span class="sxs-lookup"><span data-stu-id="a7f02-1019">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="a7f02-1020">信用卡号</span><span class="sxs-lookup"><span data-stu-id="a7f02-1020">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-1021">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-1021">Format</span></span>

<span data-ttu-id="a7f02-1022">16 位数字格式化或无格式 (dddddddddddddddd)，必须将传递 Luhn 测试。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1022">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-1023">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-1023">Pattern</span></span>

<span data-ttu-id="a7f02-1024">非常复杂且强大的模式，检测到来自世界各地所有重要品牌的卡，包括 Visa、万事达卡、发现卡、JCB卡、美国运通卡、礼品卡以及大莱卡。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1024">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-1025">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-1025">Checksum</span></span>

<span data-ttu-id="a7f02-1026">是，Luhn 校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-1026">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-1027">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-1027">Definition</span></span>

<span data-ttu-id="a7f02-1028">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1028">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-1029">函数 Func_credit_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1029">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-1030">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1030">One of the following is true:</span></span>
    - <span data-ttu-id="a7f02-1031">找到 Keyword_cc_verification 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1031">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="a7f02-1032">找到 Keyword_cc_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1032">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="a7f02-1033">函数 Func_expiration_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1033">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="a7f02-1034">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1034">The checksum passes.</span></span>

<span data-ttu-id="a7f02-1035">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1035">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-1036">函数 Func_credit_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1036">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-1037">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1037">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-1038">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1038">Keywords</span></span>

#### <a name="keywordccverification"></a><span data-ttu-id="a7f02-1039">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="a7f02-1039">Keyword_cc_verification</span></span>

- <span data-ttu-id="a7f02-1040">card verification</span><span class="sxs-lookup"><span data-stu-id="a7f02-1040">card verification</span></span>
- <span data-ttu-id="a7f02-1041">card identification number</span><span class="sxs-lookup"><span data-stu-id="a7f02-1041">card identification number</span></span>
- <span data-ttu-id="a7f02-1042">cvn
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1042">cvn</span></span>
- <span data-ttu-id="a7f02-1043">cid
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1043">cid</span></span>
- <span data-ttu-id="a7f02-1044">cvc2</span><span class="sxs-lookup"><span data-stu-id="a7f02-1044">cvc2</span></span>
- <span data-ttu-id="a7f02-1045">cvv2</span><span class="sxs-lookup"><span data-stu-id="a7f02-1045">cvv2</span></span>
- <span data-ttu-id="a7f02-1046">pin block
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1046">pin block</span></span>
- <span data-ttu-id="a7f02-1047">security code
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1047">security code</span></span>
- <span data-ttu-id="a7f02-1048">security number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1048">security number</span></span>
- <span data-ttu-id="a7f02-1049">security no
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1049">security no</span></span>
- <span data-ttu-id="a7f02-1050">issue number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1050">issue number</span></span>
- <span data-ttu-id="a7f02-1051">issue no
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1051">issue no</span></span>
- <span data-ttu-id="a7f02-1052">cryptogramme
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1052">cryptogramme</span></span>
- <span data-ttu-id="a7f02-1053">numéro de sécurité
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1053">numéro de sécurité</span></span>
- <span data-ttu-id="a7f02-1054">numero de securite
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1054">numero de securite</span></span>
- <span data-ttu-id="a7f02-1055">kreditkartenprüfnummer
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1055">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="a7f02-1056">kreditkartenprufnummer
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1056">kreditkartenprufnummer</span></span>
- <span data-ttu-id="a7f02-1057">prüfziffer
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1057">prüfziffer</span></span>
- <span data-ttu-id="a7f02-1058">prufziffer
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1058">prufziffer</span></span>
- <span data-ttu-id="a7f02-1059">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="a7f02-1059">sicherheits Kode</span></span>
- <span data-ttu-id="a7f02-1060">sicherheitscode
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1060">sicherheitscode</span></span>
- <span data-ttu-id="a7f02-1061">sicherheitsnummer
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1061">sicherheitsnummer</span></span>
- <span data-ttu-id="a7f02-1062">verfalldatum
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1062">verfalldatum</span></span>
- <span data-ttu-id="a7f02-1063">codice di verifica
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1063">codice di verifica</span></span>
- <span data-ttu-id="a7f02-p105">cod. sicurezza
</span><span class="sxs-lookup"><span data-stu-id="a7f02-p105">cod. sicurezza</span></span>
- <span data-ttu-id="a7f02-1066">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="a7f02-1066">cod sicurezza</span></span>
- <span data-ttu-id="a7f02-1067">
n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="a7f02-1067">n autorizzazione</span></span>
- <span data-ttu-id="a7f02-1068">código
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1068">código</span></span>
- <span data-ttu-id="a7f02-1069">codigo
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1069">codigo</span></span>
- <span data-ttu-id="a7f02-p106">cod. seg
</span><span class="sxs-lookup"><span data-stu-id="a7f02-p106">cod. seg</span></span>
- <span data-ttu-id="a7f02-1072">cod seg</span><span class="sxs-lookup"><span data-stu-id="a7f02-1072">cod seg</span></span>
- <span data-ttu-id="a7f02-1073">código de segurança
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1073">código de segurança</span></span>
- <span data-ttu-id="a7f02-1074">codigo de seguranca
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1074">codigo de seguranca</span></span>
- <span data-ttu-id="a7f02-1075">codigo de segurança
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1075">codigo de segurança</span></span>
- <span data-ttu-id="a7f02-1076">código de seguranca
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1076">código de seguranca</span></span>
- <span data-ttu-id="a7f02-p107">cód. segurança
</span><span class="sxs-lookup"><span data-stu-id="a7f02-p107">cód. segurança</span></span>
- <span data-ttu-id="a7f02-p108">cod。seguranca cod。segurança</span><span class="sxs-lookup"><span data-stu-id="a7f02-p108">cod. seguranca cod. segurança</span></span>
- <span data-ttu-id="a7f02-p109">cód. seguranca
</span><span class="sxs-lookup"><span data-stu-id="a7f02-p109">cód. seguranca</span></span>
- <span data-ttu-id="a7f02-1084">cód segurança</span><span class="sxs-lookup"><span data-stu-id="a7f02-1084">cód segurança</span></span>
- <span data-ttu-id="a7f02-1085">货 seguranca cod segurança 到付款</span><span class="sxs-lookup"><span data-stu-id="a7f02-1085">cod seguranca cod segurança</span></span>
- <span data-ttu-id="a7f02-1086">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="a7f02-1086">cód seguranca</span></span>
- <span data-ttu-id="a7f02-1087">número de verificação
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1087">número de verificação</span></span>
- <span data-ttu-id="a7f02-1088">numero de verificacao
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1088">numero de verificacao</span></span>
- <span data-ttu-id="a7f02-1089">ablauf
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1089">ablauf</span></span>
- <span data-ttu-id="a7f02-1090">gültig bis
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1090">gültig bis</span></span>
- <span data-ttu-id="a7f02-1091">gültigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1091">gültigkeitsdatum</span></span>
- <span data-ttu-id="a7f02-1092">gultig bis
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1092">gultig bis</span></span>
- <span data-ttu-id="a7f02-1093">gultigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1093">gultigkeitsdatum</span></span>
- <span data-ttu-id="a7f02-1094">scadenza
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1094">scadenza</span></span>
- <span data-ttu-id="a7f02-1095">data scad
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1095">data scad</span></span>
- <span data-ttu-id="a7f02-1096">fecha de expiracion
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1096">fecha de expiracion</span></span>
- <span data-ttu-id="a7f02-1097">fecha de venc
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1097">fecha de venc</span></span>
- <span data-ttu-id="a7f02-1098">vencimiento
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1098">vencimiento</span></span>
- <span data-ttu-id="a7f02-1099">válido hasta
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1099">válido hasta</span></span>
- <span data-ttu-id="a7f02-1100">valido hasta
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1100">valido hasta</span></span>
- <span data-ttu-id="a7f02-1101">vto
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1101">vto</span></span>
- <span data-ttu-id="a7f02-1102">data de expiração
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1102">data de expiração</span></span>
- <span data-ttu-id="a7f02-1103">data de expiracao
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1103">data de expiracao</span></span>
- <span data-ttu-id="a7f02-1104">data em que expira
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1104">data em que expira</span></span>
- <span data-ttu-id="a7f02-1105">validade
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1105">validade</span></span>
- <span data-ttu-id="a7f02-1106">valor
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1106">valor</span></span>
- <span data-ttu-id="a7f02-1107">vencimento
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1107">vencimento</span></span>
- <span data-ttu-id="a7f02-1108">Venc</span><span class="sxs-lookup"><span data-stu-id="a7f02-1108">Venc</span></span> 

#### <a name="keywordccname"></a><span data-ttu-id="a7f02-1109">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="a7f02-1109">Keyword_cc_name</span></span>

- <span data-ttu-id="a7f02-1110">amex</span><span class="sxs-lookup"><span data-stu-id="a7f02-1110">amex</span></span>
- <span data-ttu-id="a7f02-1111">
american express</span><span class="sxs-lookup"><span data-stu-id="a7f02-1111">american express</span></span>
- <span data-ttu-id="a7f02-1112">americanexpress
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1112">americanexpress</span></span>
- <span data-ttu-id="a7f02-1113">Visa</span><span class="sxs-lookup"><span data-stu-id="a7f02-1113">Visa</span></span>
- <span data-ttu-id="a7f02-1114">mastercard
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1114">mastercard</span></span>
- <span data-ttu-id="a7f02-1115">Master Card
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1115">master card</span></span>
- <span data-ttu-id="a7f02-1116">
mc
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1116">mc</span></span> 
- <span data-ttu-id="a7f02-1117">mastercards</span><span class="sxs-lookup"><span data-stu-id="a7f02-1117">mastercards</span></span>
- <span data-ttu-id="a7f02-1118">
master cards</span><span class="sxs-lookup"><span data-stu-id="a7f02-1118">master cards</span></span>
- <span data-ttu-id="a7f02-1119">进餐的俱乐部</span><span class="sxs-lookup"><span data-stu-id="a7f02-1119">diner's Club</span></span>
- <span data-ttu-id="a7f02-1120">diners club
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1120">diners club</span></span>
- <span data-ttu-id="a7f02-1121">dinersclub
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1121">dinersclub</span></span>
- <span data-ttu-id="a7f02-1122">discover card
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1122">discover card</span></span>
- <span data-ttu-id="a7f02-1123">discovercard
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1123">discovercard</span></span>
- <span data-ttu-id="a7f02-1124">discover cards
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1124">discover cards</span></span>
- <span data-ttu-id="a7f02-1125">JCB</span><span class="sxs-lookup"><span data-stu-id="a7f02-1125">JCB</span></span>
- <span data-ttu-id="a7f02-1126">japanese card bureau
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1126">japanese card bureau</span></span>
- <span data-ttu-id="a7f02-1127">carte blanche
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1127">carte blanche</span></span>
- <span data-ttu-id="a7f02-1128">carteblanche
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1128">carteblanche</span></span>
- <span data-ttu-id="a7f02-1129">credit card
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1129">credit card</span></span>
- <span data-ttu-id="a7f02-1130">抄送 #</span><span class="sxs-lookup"><span data-stu-id="a7f02-1130">cc#</span></span>
- <span data-ttu-id="a7f02-1131">抄送 # 中：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1131">cc#:</span></span>
- <span data-ttu-id="a7f02-1132">
expiration date</span><span class="sxs-lookup"><span data-stu-id="a7f02-1132">expiration date</span></span>
- <span data-ttu-id="a7f02-1133">exp date
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1133">exp date</span></span>
- <span data-ttu-id="a7f02-1134">
expiry date</span><span class="sxs-lookup"><span data-stu-id="a7f02-1134">expiry date</span></span>
- <span data-ttu-id="a7f02-1135">
date d’expiration</span><span class="sxs-lookup"><span data-stu-id="a7f02-1135">date d’expiration</span></span>
- <span data-ttu-id="a7f02-1136">
date d'exp</span><span class="sxs-lookup"><span data-stu-id="a7f02-1136">date d'exp</span></span>
- <span data-ttu-id="a7f02-1137">
date expiration</span><span class="sxs-lookup"><span data-stu-id="a7f02-1137">date expiration</span></span>
- <span data-ttu-id="a7f02-1138">bank card
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1138">bank card</span></span>
- <span data-ttu-id="a7f02-1139">
bankcard</span><span class="sxs-lookup"><span data-stu-id="a7f02-1139">bankcard</span></span>
- <span data-ttu-id="a7f02-1140">card number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1140">card number</span></span>
- <span data-ttu-id="a7f02-1141">card num
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1141">card num</span></span>
- <span data-ttu-id="a7f02-1142">cardnumber
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1142">cardnumber</span></span>
- <span data-ttu-id="a7f02-1143">cardnumbers
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1143">cardnumbers</span></span>
- <span data-ttu-id="a7f02-1144">card numbers
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1144">card numbers</span></span>
- <span data-ttu-id="a7f02-1145">creditcard
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1145">creditcard</span></span>
- <span data-ttu-id="a7f02-1146">credit cards
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1146">credit cards</span></span>
- <span data-ttu-id="a7f02-1147">creditcards
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1147">creditcards</span></span>
- <span data-ttu-id="a7f02-1148">ccn
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1148">ccn</span></span>
- <span data-ttu-id="a7f02-1149">card holder
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1149">card holder</span></span>
- <span data-ttu-id="a7f02-1150">cardholder
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1150">cardholder</span></span>
- <span data-ttu-id="a7f02-1151">card holders
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1151">card holders</span></span>
- <span data-ttu-id="a7f02-1152">cardholders
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1152">cardholders</span></span>
- <span data-ttu-id="a7f02-1153">check card
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1153">check card</span></span>
- <span data-ttu-id="a7f02-1154">checkcard
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1154">checkcard</span></span>
- <span data-ttu-id="a7f02-1155">check cards
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1155">check cards</span></span>
- <span data-ttu-id="a7f02-1156">checkcards
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1156">checkcards</span></span>
- <span data-ttu-id="a7f02-1157">debit card
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1157">debit card</span></span>
- <span data-ttu-id="a7f02-1158">debitcard
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1158">debitcard</span></span>
- <span data-ttu-id="a7f02-1159">debit cards
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1159">debit cards</span></span>
- <span data-ttu-id="a7f02-1160">debitcards
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1160">debitcards</span></span>
- <span data-ttu-id="a7f02-1161">atm card
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1161">atm card</span></span>
- <span data-ttu-id="a7f02-1162">atmcard
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1162">atmcard</span></span>
- <span data-ttu-id="a7f02-1163">atm cards
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1163">atm cards</span></span>
- <span data-ttu-id="a7f02-1164">atmcards
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1164">atmcards</span></span>
- <span data-ttu-id="a7f02-1165">
enroute</span><span class="sxs-lookup"><span data-stu-id="a7f02-1165">enroute</span></span>
- <span data-ttu-id="a7f02-1166">
en route</span><span class="sxs-lookup"><span data-stu-id="a7f02-1166">en route</span></span>
- <span data-ttu-id="a7f02-1167">card type
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1167">card type</span></span>
- <span data-ttu-id="a7f02-1168">carte bancaire
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1168">carte bancaire</span></span>
- <span data-ttu-id="a7f02-1169">carte de crédit
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1169">carte de crédit</span></span>
- <span data-ttu-id="a7f02-1170">carte de credit
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1170">carte de credit</span></span>
- <span data-ttu-id="a7f02-1171">numéro de carte
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1171">numéro de carte</span></span>
- <span data-ttu-id="a7f02-1172">numero de carte
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1172">numero de carte</span></span>
- <span data-ttu-id="a7f02-1173">nº de la carte
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1173">nº de la carte</span></span>
- <span data-ttu-id="a7f02-1174">nº de carte
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1174">nº de carte</span></span>
- <span data-ttu-id="a7f02-1175">kreditkarte
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1175">kreditkarte</span></span>
- <span data-ttu-id="a7f02-1176">karte
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1176">karte</span></span>
- <span data-ttu-id="a7f02-1177">karteninhaber
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1177">karteninhaber</span></span>
- <span data-ttu-id="a7f02-1178">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="a7f02-1178">karteninhabers</span></span>
- <span data-ttu-id="a7f02-1179">kreditkarteninhaber
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1179">kreditkarteninhaber</span></span>
- <span data-ttu-id="a7f02-1180">kreditkarteninstitut
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1180">kreditkarteninstitut</span></span>
- <span data-ttu-id="a7f02-1181">kreditkartentyp
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1181">kreditkartentyp</span></span>
- <span data-ttu-id="a7f02-1182">eigentümername
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1182">eigentümername</span></span>
- <span data-ttu-id="a7f02-1183">
kartennr
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1183">kartennr</span></span> 
- <span data-ttu-id="a7f02-1184">kartennummer</span><span class="sxs-lookup"><span data-stu-id="a7f02-1184">kartennummer</span></span>
- <span data-ttu-id="a7f02-1185">
kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="a7f02-1185">kreditkartennummer</span></span>
- <span data-ttu-id="a7f02-1186">kreditkarten nummer</span><span class="sxs-lookup"><span data-stu-id="a7f02-1186">kreditkarten-nummer</span></span>
- <span data-ttu-id="a7f02-1187">carta di credito
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1187">carta di credito</span></span>
- <span data-ttu-id="a7f02-1188">carta credito
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1188">carta credito</span></span>
- <span data-ttu-id="a7f02-1189">carta</span><span class="sxs-lookup"><span data-stu-id="a7f02-1189">carta</span></span>
- <span data-ttu-id="a7f02-1190">n carta</span><span class="sxs-lookup"><span data-stu-id="a7f02-1190">n carta</span></span>
- <span data-ttu-id="a7f02-p110">nr. carta
</span><span class="sxs-lookup"><span data-stu-id="a7f02-p110">nr. carta</span></span>
- <span data-ttu-id="a7f02-1193">nr carta</span><span class="sxs-lookup"><span data-stu-id="a7f02-1193">nr carta</span></span>
- <span data-ttu-id="a7f02-1194">numero carta
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1194">numero carta</span></span>
- <span data-ttu-id="a7f02-1195">numero della carta
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1195">numero della carta</span></span>
- <span data-ttu-id="a7f02-1196">numero di carta
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1196">numero di carta</span></span>
- <span data-ttu-id="a7f02-1197">tarjeta credito
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1197">tarjeta credito</span></span>
- <span data-ttu-id="a7f02-1198">tarjeta de credito
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1198">tarjeta de credito</span></span>
- <span data-ttu-id="a7f02-1199">
tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="a7f02-1199">tarjeta crédito</span></span>
- <span data-ttu-id="a7f02-1200">
tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="a7f02-1200">tarjeta de crédito</span></span>
- <span data-ttu-id="a7f02-1201">tarjeta de atm
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1201">tarjeta de atm</span></span>
- <span data-ttu-id="a7f02-1202">tarjeta atm
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1202">tarjeta atm</span></span>
- <span data-ttu-id="a7f02-1203">tarjeta debito
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1203">tarjeta debito</span></span>
- <span data-ttu-id="a7f02-1204">tarjeta de debito
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1204">tarjeta de debito</span></span>
- <span data-ttu-id="a7f02-1205">
tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="a7f02-1205">tarjeta débito</span></span>
- <span data-ttu-id="a7f02-1206">
tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="a7f02-1206">tarjeta de débito</span></span>
- <span data-ttu-id="a7f02-1207">nº de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1207">nº de tarjeta</span></span>
- <span data-ttu-id="a7f02-p111">no. de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="a7f02-p111">no. de tarjeta</span></span>
- <span data-ttu-id="a7f02-1210">没有 de tarjeta</span><span class="sxs-lookup"><span data-stu-id="a7f02-1210">no de tarjeta</span></span>
- <span data-ttu-id="a7f02-1211">numero de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1211">numero de tarjeta</span></span>
- <span data-ttu-id="a7f02-1212">número de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1212">número de tarjeta</span></span>
- <span data-ttu-id="a7f02-1213">tarjeta no
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1213">tarjeta no</span></span>
- <span data-ttu-id="a7f02-1214">tarjetahabiente
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1214">tarjetahabiente</span></span>
- <span data-ttu-id="a7f02-1215">cartão de crédito
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1215">cartão de crédito</span></span>
- <span data-ttu-id="a7f02-1216">cartão de credito
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1216">cartão de credito</span></span>
- <span data-ttu-id="a7f02-1217">cartao de crédito
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1217">cartao de crédito</span></span>
- <span data-ttu-id="a7f02-1218">cartao de credito
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1218">cartao de credito</span></span>
- <span data-ttu-id="a7f02-1219">cartão de débito
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1219">cartão de débito</span></span>
- <span data-ttu-id="a7f02-1220">cartao de débito
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1220">cartao de débito</span></span>
- <span data-ttu-id="a7f02-1221">cartão de debito
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1221">cartão de debito</span></span>
- <span data-ttu-id="a7f02-1222">cartao de debito
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1222">cartao de debito</span></span>
- <span data-ttu-id="a7f02-1223">débito automático</span><span class="sxs-lookup"><span data-stu-id="a7f02-1223">débito automático</span></span>
- <span data-ttu-id="a7f02-1224">debito automatico
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1224">debito automatico</span></span>
- <span data-ttu-id="a7f02-1225">
número do cartão</span><span class="sxs-lookup"><span data-stu-id="a7f02-1225">número do cartão</span></span>
- <span data-ttu-id="a7f02-1226">
numero do cartão
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1226">numero do cartão</span></span> 
- <span data-ttu-id="a7f02-1227">número do cartao</span><span class="sxs-lookup"><span data-stu-id="a7f02-1227">número do cartao</span></span>
- <span data-ttu-id="a7f02-1228">
numero do cartao</span><span class="sxs-lookup"><span data-stu-id="a7f02-1228">numero do cartao</span></span>
- <span data-ttu-id="a7f02-1229">número de cartão
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1229">número de cartão</span></span>
- <span data-ttu-id="a7f02-1230">numero de cartão
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1230">numero de cartão</span></span>
- <span data-ttu-id="a7f02-1231">número de cartao
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1231">número de cartao</span></span>
- <span data-ttu-id="a7f02-1232">numero de cartao
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1232">numero de cartao</span></span>
- <span data-ttu-id="a7f02-1233">nº 执行 cartão</span><span class="sxs-lookup"><span data-stu-id="a7f02-1233">nº do cartão</span></span>
- <span data-ttu-id="a7f02-1234">nº do cartao
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1234">nº do cartao</span></span>
- <span data-ttu-id="a7f02-p112">nº. do cartão
</span><span class="sxs-lookup"><span data-stu-id="a7f02-p112">nº. do cartão</span></span>
- <span data-ttu-id="a7f02-1237">没有执行 cartão</span><span class="sxs-lookup"><span data-stu-id="a7f02-1237">no do cartão</span></span>
- <span data-ttu-id="a7f02-1238">没有执行 cartao</span><span class="sxs-lookup"><span data-stu-id="a7f02-1238">no do cartao</span></span>
- <span data-ttu-id="a7f02-p113">no. do cartão
</span><span class="sxs-lookup"><span data-stu-id="a7f02-p113">no. do cartão</span></span>
- <span data-ttu-id="a7f02-p114">
no. do cartao
</span><span class="sxs-lookup"><span data-stu-id="a7f02-p114">no. do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="a7f02-1243">	克罗地亚身份证号</span><span class="sxs-lookup"><span data-stu-id="a7f02-1243">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-1244">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-1244">Format</span></span>

<span data-ttu-id="a7f02-1245">九个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1245">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-1246">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-1246">Pattern</span></span>

<span data-ttu-id="a7f02-1247">九个连续的数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1247">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-1248">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-1248">Checksum</span></span>

<span data-ttu-id="a7f02-1249">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-1249">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-1250">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-1250">Definition</span></span>

<span data-ttu-id="a7f02-1251">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1251">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-1252">函数 Func_croatia_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1252">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-1253">找到 Keyword_croatia_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1253">A keyword from Keyword_croatia_id_card is found.</span></span>

```
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7f02-1254">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1254">Keywords</span></span>

#### <a name="keywordcroatiaidcard"></a><span data-ttu-id="a7f02-1255">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="a7f02-1255">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="a7f02-1256">Croatian identity card</span><span class="sxs-lookup"><span data-stu-id="a7f02-1256">Croatian identity card</span></span>
- <span data-ttu-id="a7f02-1257">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="a7f02-1257">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="a7f02-1258">	Croatia Personal Identification (OIB) Number</span><span class="sxs-lookup"><span data-stu-id="a7f02-1258">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-1259">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-1259">Format</span></span>

<span data-ttu-id="a7f02-1260">10 个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1260">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-1261">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-1261">Pattern</span></span>

<span data-ttu-id="a7f02-1262">10 个数字：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1262">10 digits:</span></span>
- <span data-ttu-id="a7f02-1263">六个数字，采用  DDMMYY 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="a7f02-1263">Six digits in the form DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="a7f02-1264">四个数字，最后一位数字是校验位</span><span class="sxs-lookup"><span data-stu-id="a7f02-1264">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-1265">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-1265">Checksum</span></span>

<span data-ttu-id="a7f02-1266">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-1266">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-1267">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-1267">Definition</span></span>

<span data-ttu-id="a7f02-1268">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1268">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-1269">函数 Func_croatia_oib_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1269">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-1270">找到 Keyword_croatia_oib_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1270">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="a7f02-1271">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1271">The checksum passes.</span></span>

<span data-ttu-id="a7f02-1272">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1272">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-1273">函数 Func_croatia_oib_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1273">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-1274">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1274">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-1275">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1275">Keywords</span></span>

#### <a name="keywordcroatiaoibnumber"></a><span data-ttu-id="a7f02-1276">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="a7f02-1276">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="a7f02-1277">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="a7f02-1277">Personal Identification Number</span></span>
- <span data-ttu-id="a7f02-1278">Osobni identifikacijski broj
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1278">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="a7f02-1279">OIB
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1279">OIB</span></span> 

   
## <a name="czech-national-identity-card-number"></a><span data-ttu-id="a7f02-1280">	捷克国家身份证号</span><span class="sxs-lookup"><span data-stu-id="a7f02-1280">Czech National Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-1281">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-1281">Format</span></span>

<span data-ttu-id="a7f02-1282">10 个数字，包含正斜杠</span><span class="sxs-lookup"><span data-stu-id="a7f02-1282">10 digits containing a forward slash</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-1283">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-1283">Pattern</span></span>

<span data-ttu-id="a7f02-1284">10 个数字：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1284">10 digits:</span></span>
- <span data-ttu-id="a7f02-1285">六个数字，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="a7f02-1285">Six digits which are the date of birth</span></span> 
- <span data-ttu-id="a7f02-1286">一个正斜杠 </span><span class="sxs-lookup"><span data-stu-id="a7f02-1286">A forward slash</span></span> 
- <span data-ttu-id="a7f02-1287">四个数字，最后一位数字是校验位</span><span class="sxs-lookup"><span data-stu-id="a7f02-1287">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-1288">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-1288">Checksum</span></span>

<span data-ttu-id="a7f02-1289">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-1289">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-1290">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-1290">Definition</span></span>

<span data-ttu-id="a7f02-p115">DLP 策略是 85%相信它已检测到此类型的敏感信息 if、 内 300 个字符的邻近度： 函数 Func_czech_id_card 查找与模式匹配的内容。找到从 Keyword_czech_id_card 关键字。将传递校验和。</span><span class="sxs-lookup"><span data-stu-id="a7f02-p115">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern. A keyword from Keyword_czech_id_card is found. The checksum passes.</span></span>

```
<!-- Czech National Identity Card Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_czech_id_card"/>
     <Match idRef="Keyword_czech_id_card"/>
  </Pattern>
</Entity>
```


### <a name="keywords"></a><span data-ttu-id="a7f02-1294">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1294">Keywords</span></span>

- <span data-ttu-id="a7f02-1295">Keyword_czech_id_card</span><span class="sxs-lookup"><span data-stu-id="a7f02-1295">Keyword_czech_id_card</span></span>
- <span data-ttu-id="a7f02-1296">Czech national identity card</span><span class="sxs-lookup"><span data-stu-id="a7f02-1296">Czech national identity card</span></span>
- <span data-ttu-id="a7f02-1297">Občanský průka</span><span class="sxs-lookup"><span data-stu-id="a7f02-1297">Občanský průka</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="a7f02-1298">	丹麦个人身份号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-1298">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-1299">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-1299">Format</span></span>

<span data-ttu-id="a7f02-1300">10 个数字，包含连字符</span><span class="sxs-lookup"><span data-stu-id="a7f02-1300">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-1301">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-1301">Pattern</span></span>

<span data-ttu-id="a7f02-1302">10 个数字：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1302">10 digits:</span></span>
- <span data-ttu-id="a7f02-1303">六个数字，采用  DDMMYY 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="a7f02-1303">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="a7f02-1304">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="a7f02-1304">A hyphen</span></span> 
- <span data-ttu-id="a7f02-1305">四个数字，最后一位数字是校验位</span><span class="sxs-lookup"><span data-stu-id="a7f02-1305">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-1306">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-1306">Checksum</span></span>

<span data-ttu-id="a7f02-1307">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-1307">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-1308">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-1308">Definition</span></span>

<span data-ttu-id="a7f02-p116">DLP 策略是相信它已检测到此类型的敏感信息的 75 %if、 内 300 个字符的邻近度： 正则表达式 Regex_denmark_id 找到与模式匹配的内容。找到从 Keyword_denmark_id 关键字。将传递校验和。</span><span class="sxs-lookup"><span data-stu-id="a7f02-p116">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern. A keyword from Keyword_denmark_id is found. The checksum passes.</span></span>

```
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7f02-1312">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1312">Keywords</span></span>

#### <a name="keyworddenmarkid"></a><span data-ttu-id="a7f02-1313">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="a7f02-1313">Keyword_denmark_id</span></span>

- <span data-ttu-id="a7f02-1314">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="a7f02-1314">Personal Identification Number</span></span>
- <span data-ttu-id="a7f02-1315">CPR</span><span class="sxs-lookup"><span data-stu-id="a7f02-1315">CPR</span></span>
- <span data-ttu-id="a7f02-1316">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="a7f02-1316">Det Centrale Personregister</span></span>
- <span data-ttu-id="a7f02-1317">Personnummer</span><span class="sxs-lookup"><span data-stu-id="a7f02-1317">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="a7f02-1318">药品管制局 (DEA) 号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-1318">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-1319">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-1319">Format</span></span>

<span data-ttu-id="a7f02-1320">两个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1320">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-1321">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-1321">Pattern</span></span>

<span data-ttu-id="a7f02-1322">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1322">Pattern must include all of the following:</span></span>
- <span data-ttu-id="a7f02-1323">这一组可能的字母（不区分大小写）中的一个字母：abcdefghjklmnprstux，这是注册人代码</span><span class="sxs-lookup"><span data-stu-id="a7f02-1323">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="a7f02-1324">一个字母（不区分大小写），这是注册人姓氏的第一个字母</span><span class="sxs-lookup"><span data-stu-id="a7f02-1324">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="a7f02-1325">七位数字，最后一个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="a7f02-1325">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-1326">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-1326">Checksum</span></span>

<span data-ttu-id="a7f02-1327">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-1327">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-1328">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-1328">Definition</span></span>

<span data-ttu-id="a7f02-1329">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1329">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-1330">函数 Func_dea_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1330">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-1331">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1331">The checksum passes.</span></span>

```
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7f02-1332">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1332">Keywords</span></span>

<span data-ttu-id="a7f02-1333">无</span><span class="sxs-lookup"><span data-stu-id="a7f02-1333">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="a7f02-1334">欧盟借记卡号</span><span class="sxs-lookup"><span data-stu-id="a7f02-1334">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-1335">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-1335">Format</span></span>

<span data-ttu-id="a7f02-1336">16 个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1336">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-1337">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-1337">Pattern</span></span>

<span data-ttu-id="a7f02-1338">非常复杂且强大的模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-1338">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-1339">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-1339">Checksum</span></span>

<span data-ttu-id="a7f02-1340">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-1340">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-1341">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-1341">Definition</span></span>

<span data-ttu-id="a7f02-1342">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-1343">函数 Func_eu_debit_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1343">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-1344">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1344">At least one of the following is true:</span></span>
    - <span data-ttu-id="a7f02-1345">找到 Keyword_eu_debit_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1345">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="a7f02-1346">找到 Keyword_card_terms_dict 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1346">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="a7f02-1347">找到 Keyword_card_security_terms_dict 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1347">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="a7f02-1348">找到 Keyword_card_expiration_terms_dict 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1348">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="a7f02-1349">函数 Func_expiration_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1349">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="a7f02-1350">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1350">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-1351">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1351">Keywords</span></span>

#### <a name="keywordeudebitcard"></a><span data-ttu-id="a7f02-1352">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="a7f02-1352">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="a7f02-1353">帐号</span><span class="sxs-lookup"><span data-stu-id="a7f02-1353">account number</span></span> 
- <span data-ttu-id="a7f02-1354">card number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1354">card number</span></span> 
- <span data-ttu-id="a7f02-1355">card no.
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1355">card no.</span></span> 
- <span data-ttu-id="a7f02-1356">security number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1356">security number</span></span> 
- <span data-ttu-id="a7f02-1357">抄送 #</span><span class="sxs-lookup"><span data-stu-id="a7f02-1357">cc#</span></span> 

#### <a name="keywordcardtermsdict"></a><span data-ttu-id="a7f02-1358">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="a7f02-1358">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="a7f02-1359">acct nbr
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1359">acct nbr</span></span> 
- <span data-ttu-id="a7f02-1360">acct num
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1360">acct num</span></span> 
- <span data-ttu-id="a7f02-1361">acct no
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1361">acct no</span></span> 
- <span data-ttu-id="a7f02-1362">american express
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1362">american express</span></span> 
- <span data-ttu-id="a7f02-1363">americanexpress
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1363">americanexpress</span></span> 
- <span data-ttu-id="a7f02-1364">americano espresso
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1364">americano espresso</span></span> 
- <span data-ttu-id="a7f02-1365">amex</span><span class="sxs-lookup"><span data-stu-id="a7f02-1365">amex</span></span> 
- <span data-ttu-id="a7f02-1366">atm card
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1366">atm card</span></span> 
- <span data-ttu-id="a7f02-1367">atm cards
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1367">atm cards</span></span> 
- <span data-ttu-id="a7f02-1368">atm kaart
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1368">atm kaart</span></span> 
- <span data-ttu-id="a7f02-1369">atmcard
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1369">atmcard</span></span> 
- <span data-ttu-id="a7f02-1370">atmcards
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1370">atmcards</span></span> 
- <span data-ttu-id="a7f02-1371">atmkaart
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1371">atmkaart</span></span> 
- <span data-ttu-id="a7f02-1372">atmkaarten
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1372">atmkaarten</span></span> 
- <span data-ttu-id="a7f02-1373">bancontact
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1373">bancontact</span></span> 
- <span data-ttu-id="a7f02-1374">bank card
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1374">bank card</span></span> 
- <span data-ttu-id="a7f02-1375">bankkaart
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1375">bankkaart</span></span> 
- <span data-ttu-id="a7f02-1376">card holder
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1376">card holder</span></span> 
- <span data-ttu-id="a7f02-1377">card holders
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1377">card holders</span></span> 
- <span data-ttu-id="a7f02-1378">card num
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1378">card num</span></span> 
- <span data-ttu-id="a7f02-1379">card number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1379">card number</span></span> 
- <span data-ttu-id="a7f02-1380">card numbers
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1380">card numbers</span></span> 
- <span data-ttu-id="a7f02-1381">card type
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1381">card type</span></span> 
- <span data-ttu-id="a7f02-1382">cardano numerico
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1382">cardano numerico</span></span> 
- <span data-ttu-id="a7f02-1383">cardholder
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1383">cardholder</span></span> 
- <span data-ttu-id="a7f02-1384">cardholders
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1384">cardholders</span></span> 
- <span data-ttu-id="a7f02-1385">cardnumber
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1385">cardnumber</span></span> 
- <span data-ttu-id="a7f02-1386">cardnumbers
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1386">cardnumbers</span></span> 
- <span data-ttu-id="a7f02-1387">carta bianca
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1387">carta bianca</span></span> 
- <span data-ttu-id="a7f02-1388">carta credito
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1388">carta credito</span></span> 
- <span data-ttu-id="a7f02-1389">carta di credito
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1389">carta di credito</span></span> 
- <span data-ttu-id="a7f02-1390">cartao de credito
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1390">cartao de credito</span></span> 
- <span data-ttu-id="a7f02-1391">cartao de crédito
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1391">cartao de crédito</span></span> 
- <span data-ttu-id="a7f02-1392">cartao de debito
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1392">cartao de debito</span></span> 
- <span data-ttu-id="a7f02-1393">cartao de débito
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1393">cartao de débito</span></span> 
- <span data-ttu-id="a7f02-1394">carte bancaire
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1394">carte bancaire</span></span> 
- <span data-ttu-id="a7f02-1395">carte blanche
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1395">carte blanche</span></span> 
- <span data-ttu-id="a7f02-1396">carte bleue
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1396">carte bleue</span></span> 
- <span data-ttu-id="a7f02-1397">carte de credit
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1397">carte de credit</span></span> 
- <span data-ttu-id="a7f02-1398">carte de crédit
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1398">carte de crédit</span></span> 
- <span data-ttu-id="a7f02-1399">carte di credito
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1399">carte di credito</span></span> 
- <span data-ttu-id="a7f02-1400">carteblanche
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1400">carteblanche</span></span> 
- <span data-ttu-id="a7f02-1401">cartão de credito
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1401">cartão de credito</span></span> 
- <span data-ttu-id="a7f02-1402">cartão de crédito
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1402">cartão de crédito</span></span> 
- <span data-ttu-id="a7f02-1403">cartão de debito
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1403">cartão de debito</span></span> 
- <span data-ttu-id="a7f02-1404">cartão de débito
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1404">cartão de débito</span></span> 
- <span data-ttu-id="a7f02-1405">cb
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1405">cb</span></span> 
- <span data-ttu-id="a7f02-1406">ccn
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1406">ccn</span></span> 
- <span data-ttu-id="a7f02-1407">check card
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1407">check card</span></span> 
- <span data-ttu-id="a7f02-1408">check cards
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1408">check cards</span></span> 
- <span data-ttu-id="a7f02-1409">checkcard
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1409">checkcard</span></span>
- <span data-ttu-id="a7f02-1410">checkcards
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1410">checkcards</span></span> 
- <span data-ttu-id="a7f02-1411">chequekaart
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1411">chequekaart</span></span> 
- <span data-ttu-id="a7f02-1412">cirrus
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1412">cirrus</span></span> 
- <span data-ttu-id="a7f02-1413">cirrus-edc-maestro
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1413">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="a7f02-1414">controlekaart
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1414">controlekaart</span></span> 
- <span data-ttu-id="a7f02-1415">controlekaarten
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1415">controlekaarten</span></span> 
- <span data-ttu-id="a7f02-1416">credit card
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1416">credit card</span></span> 
- <span data-ttu-id="a7f02-1417">credit cards
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1417">credit cards</span></span> 
- <span data-ttu-id="a7f02-1418">creditcard
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1418">creditcard</span></span> 
- <span data-ttu-id="a7f02-1419">creditcards
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1419">creditcards</span></span> 
- <span data-ttu-id="a7f02-1420">debetkaart
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1420">debetkaart</span></span> 
- <span data-ttu-id="a7f02-1421">debetkaarten
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1421">debetkaarten</span></span> 
- <span data-ttu-id="a7f02-1422">debit card
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1422">debit card</span></span> 
- <span data-ttu-id="a7f02-1423">debit cards
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1423">debit cards</span></span> 
- <span data-ttu-id="a7f02-1424">debitcard
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1424">debitcard</span></span> 
- <span data-ttu-id="a7f02-1425">debitcards
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1425">debitcards</span></span> 
- <span data-ttu-id="a7f02-1426">debito automatico
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1426">debito automatico</span></span> 
- <span data-ttu-id="a7f02-1427">diners club
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1427">diners club</span></span> 
- <span data-ttu-id="a7f02-1428">dinersclub
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1428">dinersclub</span></span> 
- <span data-ttu-id="a7f02-1429">发现</span><span class="sxs-lookup"><span data-stu-id="a7f02-1429">discover</span></span> 
- <span data-ttu-id="a7f02-1430">discover card
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1430">discover card</span></span> 
- <span data-ttu-id="a7f02-1431">discover cards
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1431">discover cards</span></span> 
- <span data-ttu-id="a7f02-1432">discovercard
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1432">discovercard</span></span> 
- <span data-ttu-id="a7f02-1433">discovercards
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1433">discovercards</span></span> 
- <span data-ttu-id="a7f02-1434">débito automático</span><span class="sxs-lookup"><span data-stu-id="a7f02-1434">débito automático</span></span>
- <span data-ttu-id="a7f02-1435">
edc
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1435">edc</span></span> 
- <span data-ttu-id="a7f02-1436">eigentümername
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1436">eigentümername</span></span> 
- <span data-ttu-id="a7f02-1437">european debit card
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1437">european debit card</span></span> 
- <span data-ttu-id="a7f02-1438">hoofdkaart
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1438">hoofdkaart</span></span> 
- <span data-ttu-id="a7f02-1439">hoofdkaarten
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1439">hoofdkaarten</span></span> 
- <span data-ttu-id="a7f02-1440">in viaggio
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1440">in viaggio</span></span> 
- <span data-ttu-id="a7f02-1441">japanese card bureau
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1441">japanese card bureau</span></span> 
- <span data-ttu-id="a7f02-1442">japanse kaartdienst
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1442">japanse kaartdienst</span></span> 
- <span data-ttu-id="a7f02-1443">jcb
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1443">jcb</span></span> 
- <span data-ttu-id="a7f02-1444">kaart
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1444">kaart</span></span> 
- <span data-ttu-id="a7f02-1445">kaart num
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1445">kaart num</span></span> 
- <span data-ttu-id="a7f02-1446">kaartaantal
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1446">kaartaantal</span></span> 
- <span data-ttu-id="a7f02-1447">kaartaantallen
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1447">kaartaantallen</span></span> 
- <span data-ttu-id="a7f02-1448">kaarthouder
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1448">kaarthouder</span></span> 
- <span data-ttu-id="a7f02-1449">kaarthouders
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1449">kaarthouders</span></span> 
- <span data-ttu-id="a7f02-1450">karte
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1450">karte</span></span>  
- <span data-ttu-id="a7f02-1451">karteninhaber
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1451">karteninhaber</span></span> 
- <span data-ttu-id="a7f02-1452">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="a7f02-1452">karteninhabers</span></span>
- <span data-ttu-id="a7f02-1453">
kartennr
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1453">kartennr</span></span> 
- <span data-ttu-id="a7f02-1454">kartennummer</span><span class="sxs-lookup"><span data-stu-id="a7f02-1454">kartennummer</span></span> 
- <span data-ttu-id="a7f02-1455">kreditkarte
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1455">kreditkarte</span></span> 
- <span data-ttu-id="a7f02-1456">kreditkarten nummer</span><span class="sxs-lookup"><span data-stu-id="a7f02-1456">kreditkarten-nummer</span></span> 
- <span data-ttu-id="a7f02-1457">kreditkarteninhaber
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1457">kreditkarteninhaber</span></span> 
- <span data-ttu-id="a7f02-1458">kreditkarteninstitut
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1458">kreditkarteninstitut</span></span> 
- <span data-ttu-id="a7f02-1459">kreditkartennummer
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1459">kreditkartennummer</span></span> 
- <span data-ttu-id="a7f02-1460">kreditkartentyp
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1460">kreditkartentyp</span></span> 
- <span data-ttu-id="a7f02-1461">maestro
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1461">maestro</span></span> 
- <span data-ttu-id="a7f02-1462">Master Card
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1462">master card</span></span> 
- <span data-ttu-id="a7f02-1463">master cards
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1463">master cards</span></span> 
- <span data-ttu-id="a7f02-1464">mastercard
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1464">mastercard</span></span> 
- <span data-ttu-id="a7f02-1465">mastercards</span><span class="sxs-lookup"><span data-stu-id="a7f02-1465">mastercards</span></span> 
- <span data-ttu-id="a7f02-1466">mc</span><span class="sxs-lookup"><span data-stu-id="a7f02-1466">mc</span></span> 
- <span data-ttu-id="a7f02-1467">mister cash
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1467">mister cash</span></span> 
- <span data-ttu-id="a7f02-1468">n carta</span><span class="sxs-lookup"><span data-stu-id="a7f02-1468">n carta</span></span> 
- <span data-ttu-id="a7f02-1469">carta</span><span class="sxs-lookup"><span data-stu-id="a7f02-1469">carta</span></span> 
- <span data-ttu-id="a7f02-1470">没有 de tarjeta</span><span class="sxs-lookup"><span data-stu-id="a7f02-1470">no de tarjeta</span></span> 
- <span data-ttu-id="a7f02-1471">没有执行 cartao</span><span class="sxs-lookup"><span data-stu-id="a7f02-1471">no do cartao</span></span> 
- <span data-ttu-id="a7f02-1472">没有执行 cartão</span><span class="sxs-lookup"><span data-stu-id="a7f02-1472">no do cartão</span></span> 
- <span data-ttu-id="a7f02-p117">no. de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="a7f02-p117">no. de tarjeta</span></span> 
- <span data-ttu-id="a7f02-p118">no. do cartao
</span><span class="sxs-lookup"><span data-stu-id="a7f02-p118">no. do cartao</span></span> 
- <span data-ttu-id="a7f02-p119">no. do cartão
</span><span class="sxs-lookup"><span data-stu-id="a7f02-p119">no. do cartão</span></span> 
- <span data-ttu-id="a7f02-1479">nr carta</span><span class="sxs-lookup"><span data-stu-id="a7f02-1479">nr carta</span></span> 
- <span data-ttu-id="a7f02-p120">nr. carta
</span><span class="sxs-lookup"><span data-stu-id="a7f02-p120">nr. carta</span></span> 
- <span data-ttu-id="a7f02-1482">numeri di scheda
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1482">numeri di scheda</span></span> 
- <span data-ttu-id="a7f02-1483">numero carta
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1483">numero carta</span></span> 
- <span data-ttu-id="a7f02-1484">numero de cartao
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1484">numero de cartao</span></span> 
- <span data-ttu-id="a7f02-1485">numero de carte
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1485">numero de carte</span></span> 
- <span data-ttu-id="a7f02-1486">numero de cartão
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1486">numero de cartão</span></span> 
- <span data-ttu-id="a7f02-1487">numero de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1487">numero de tarjeta</span></span>
- <span data-ttu-id="a7f02-1488">numero della carta
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1488">numero della carta</span></span> 
- <span data-ttu-id="a7f02-1489">numero di carta
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1489">numero di carta</span></span> 
- <span data-ttu-id="a7f02-1490">numero di scheda
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1490">numero di scheda</span></span> 
- <span data-ttu-id="a7f02-1491">numero do cartao
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1491">numero do cartao</span></span> 
- <span data-ttu-id="a7f02-1492">numero do cartão
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1492">numero do cartão</span></span> 
- <span data-ttu-id="a7f02-1493">numéro de carte
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1493">numéro de carte</span></span> 
- <span data-ttu-id="a7f02-1494">nº carta
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1494">nº carta</span></span> 
- <span data-ttu-id="a7f02-1495">nº de carte
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1495">nº de carte</span></span> 
- <span data-ttu-id="a7f02-1496">nº de la carte
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1496">nº de la carte</span></span> 
- <span data-ttu-id="a7f02-1497">nº de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1497">nº de tarjeta</span></span> 
- <span data-ttu-id="a7f02-1498">nº do cartao
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1498">nº do cartao</span></span> 
- <span data-ttu-id="a7f02-1499">nº 执行 cartão</span><span class="sxs-lookup"><span data-stu-id="a7f02-1499">nº do cartão</span></span> 
- <span data-ttu-id="a7f02-p121">nº. do cartão
</span><span class="sxs-lookup"><span data-stu-id="a7f02-p121">nº. do cartão</span></span> 
- <span data-ttu-id="a7f02-1502">número de cartao
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1502">número de cartao</span></span> 
- <span data-ttu-id="a7f02-1503">número de cartão
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1503">número de cartão</span></span> 
- <span data-ttu-id="a7f02-1504">número de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1504">número de tarjeta</span></span> 
- <span data-ttu-id="a7f02-1505">número do cartao</span><span class="sxs-lookup"><span data-stu-id="a7f02-1505">número do cartao</span></span> 
- <span data-ttu-id="a7f02-1506">scheda dell'assegno
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1506">scheda dell'assegno</span></span> 
- <span data-ttu-id="a7f02-1507">scheda dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1507">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="a7f02-1508">scheda dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1508">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="a7f02-1509">scheda della banca
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1509">scheda della banca</span></span> 
- <span data-ttu-id="a7f02-1510">scheda di controllo
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1510">scheda di controllo</span></span> 
- <span data-ttu-id="a7f02-1511">scheda di debito
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1511">scheda di debito</span></span> 
- <span data-ttu-id="a7f02-1512">scheda matrice
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1512">scheda matrice</span></span> 
- <span data-ttu-id="a7f02-1513">schede dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1513">schede dell'atmosfera</span></span> 
- <span data-ttu-id="a7f02-1514">schede di controllo
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1514">schede di controllo</span></span> 
- <span data-ttu-id="a7f02-1515">schede di debito
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1515">schede di debito</span></span> 
- <span data-ttu-id="a7f02-1516">schede matrici
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1516">schede matrici</span></span> 
- <span data-ttu-id="a7f02-1517">scoprono la scheda
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1517">scoprono la scheda</span></span> 
- <span data-ttu-id="a7f02-1518">scoprono le schede
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1518">scoprono le schede</span></span> 
- <span data-ttu-id="a7f02-1519">solo
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1519">solo</span></span> 
- <span data-ttu-id="a7f02-1520">supporti di scheda
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1520">supporti di scheda</span></span> 
- <span data-ttu-id="a7f02-1521">supporto di scheda
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1521">supporto di scheda</span></span> 
- <span data-ttu-id="a7f02-1522">切换</span><span class="sxs-lookup"><span data-stu-id="a7f02-1522">switch</span></span> 
- <span data-ttu-id="a7f02-1523">tarjeta atm
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1523">tarjeta atm</span></span> 
- <span data-ttu-id="a7f02-1524">tarjeta credito
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1524">tarjeta credito</span></span> 
- <span data-ttu-id="a7f02-1525">tarjeta de atm
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1525">tarjeta de atm</span></span> 
- <span data-ttu-id="a7f02-1526">tarjeta de credito
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1526">tarjeta de credito</span></span> 
- <span data-ttu-id="a7f02-1527">tarjeta de debito
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1527">tarjeta de debito</span></span> 
- <span data-ttu-id="a7f02-1528">tarjeta debito
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1528">tarjeta debito</span></span> 
- <span data-ttu-id="a7f02-1529">tarjeta no
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1529">tarjeta no</span></span>
- <span data-ttu-id="a7f02-1530">tarjetahabiente
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1530">tarjetahabiente</span></span> 
- <span data-ttu-id="a7f02-1531">tipo della scheda
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1531">tipo della scheda</span></span> 
- <span data-ttu-id="a7f02-1532">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="a7f02-1532">ufficio giapponese della</span></span> 
- <span data-ttu-id="a7f02-1533">scheda
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1533">scheda</span></span> 
- <span data-ttu-id="a7f02-1534">v pay
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1534">v pay</span></span> 
- <span data-ttu-id="a7f02-1535">v 付薪</span><span class="sxs-lookup"><span data-stu-id="a7f02-1535">v-pay</span></span> 
- <span data-ttu-id="a7f02-1536">visa
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1536">visa</span></span> 
- <span data-ttu-id="a7f02-1537">visa plus
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1537">visa plus</span></span> 
- <span data-ttu-id="a7f02-1538">visa electron
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1538">visa electron</span></span> 
- <span data-ttu-id="a7f02-1539">visto
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1539">visto</span></span> 
- <span data-ttu-id="a7f02-1540">visum
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1540">visum</span></span> 
- <span data-ttu-id="a7f02-1541">vpay
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1541">vpay</span></span>   

#### <a name="keywordcardsecuritytermsdict"></a><span data-ttu-id="a7f02-1542">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="a7f02-1542">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="a7f02-1543">card identification number</span><span class="sxs-lookup"><span data-stu-id="a7f02-1543">card identification number</span></span>
- <span data-ttu-id="a7f02-1544">card verification</span><span class="sxs-lookup"><span data-stu-id="a7f02-1544">card verification</span></span> 
- <span data-ttu-id="a7f02-1545">cardi la verifica
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1545">cardi la verifica</span></span> 
- <span data-ttu-id="a7f02-1546">cid
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1546">cid</span></span> 
- <span data-ttu-id="a7f02-1547">cod seg</span><span class="sxs-lookup"><span data-stu-id="a7f02-1547">cod seg</span></span> 
- <span data-ttu-id="a7f02-1548">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="a7f02-1548">cod seguranca</span></span> 
- <span data-ttu-id="a7f02-1549">cod segurança</span><span class="sxs-lookup"><span data-stu-id="a7f02-1549">cod segurança</span></span> 
- <span data-ttu-id="a7f02-1550">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="a7f02-1550">cod sicurezza</span></span> 
- <span data-ttu-id="a7f02-p122">cod. seg
</span><span class="sxs-lookup"><span data-stu-id="a7f02-p122">cod. seg</span></span> 
- <span data-ttu-id="a7f02-p123">cod. seguranca
</span><span class="sxs-lookup"><span data-stu-id="a7f02-p123">cod. seguranca</span></span> 
- <span data-ttu-id="a7f02-p124">cod. segurança
</span><span class="sxs-lookup"><span data-stu-id="a7f02-p124">cod. segurança</span></span> 
- <span data-ttu-id="a7f02-p125">cod. sicurezza
</span><span class="sxs-lookup"><span data-stu-id="a7f02-p125">cod. sicurezza</span></span> 
- <span data-ttu-id="a7f02-1559">codice di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1559">codice di sicurezza</span></span> 
- <span data-ttu-id="a7f02-1560">codice di verifica
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1560">codice di verifica</span></span> 
- <span data-ttu-id="a7f02-1561">codigo
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1561">codigo</span></span> 
- <span data-ttu-id="a7f02-1562">codigo de seguranca
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1562">codigo de seguranca</span></span> 
- <span data-ttu-id="a7f02-1563">codigo de segurança
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1563">codigo de segurança</span></span> 
- <span data-ttu-id="a7f02-1564">crittogramma
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1564">crittogramma</span></span> 
- <span data-ttu-id="a7f02-1565">cryptogram
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1565">cryptogram</span></span> 
- <span data-ttu-id="a7f02-1566">cryptogramme
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1566">cryptogramme</span></span> 
- <span data-ttu-id="a7f02-1567">cv2</span><span class="sxs-lookup"><span data-stu-id="a7f02-1567">cv2</span></span> 
- <span data-ttu-id="a7f02-1568">cvc
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1568">cvc</span></span> 
- <span data-ttu-id="a7f02-1569">cvc2</span><span class="sxs-lookup"><span data-stu-id="a7f02-1569">cvc2</span></span> 
- <span data-ttu-id="a7f02-1570">cvn
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1570">cvn</span></span> 
- <span data-ttu-id="a7f02-1571">cvv
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1571">cvv</span></span> 
- <span data-ttu-id="a7f02-1572">cvv2</span><span class="sxs-lookup"><span data-stu-id="a7f02-1572">cvv2</span></span> 
- <span data-ttu-id="a7f02-1573">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="a7f02-1573">cód seguranca</span></span> 
- <span data-ttu-id="a7f02-1574">cód segurança</span><span class="sxs-lookup"><span data-stu-id="a7f02-1574">cód segurança</span></span> 
- <span data-ttu-id="a7f02-p126">cód. seguranca
</span><span class="sxs-lookup"><span data-stu-id="a7f02-p126">cód. seguranca</span></span> 
- <span data-ttu-id="a7f02-p127">cód. segurança
</span><span class="sxs-lookup"><span data-stu-id="a7f02-p127">cód. segurança</span></span> 
- <span data-ttu-id="a7f02-1579">código
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1579">código</span></span> 
- <span data-ttu-id="a7f02-1580">código de seguranca
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1580">código de seguranca</span></span> 
- <span data-ttu-id="a7f02-1581">código de segurança
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1581">código de segurança</span></span> 
- <span data-ttu-id="a7f02-1582">de kaart controle
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1582">de kaart controle</span></span> 
- <span data-ttu-id="a7f02-1583">geeft nr uit
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1583">geeft nr uit</span></span> 
- <span data-ttu-id="a7f02-1584">issue no
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1584">issue no</span></span> 
- <span data-ttu-id="a7f02-1585">issue number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1585">issue number</span></span> 
- <span data-ttu-id="a7f02-1586">kaartidentificatienummer
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1586">kaartidentificatienummer</span></span> 
- <span data-ttu-id="a7f02-1587">kreditkartenprufnummer
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1587">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="a7f02-1588">kreditkartenprüfnummer
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1588">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="a7f02-1589">kwestieaantal
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1589">kwestieaantal</span></span> 
- <span data-ttu-id="a7f02-p128">no. dell'edizione
</span><span class="sxs-lookup"><span data-stu-id="a7f02-p128">no. dell'edizione</span></span> 
- <span data-ttu-id="a7f02-p129">no. di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="a7f02-p129">no. di sicurezza</span></span> 
- <span data-ttu-id="a7f02-1594">numero de securite
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1594">numero de securite</span></span> 
- <span data-ttu-id="a7f02-1595">numero de verificacao
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1595">numero de verificacao</span></span> 
- <span data-ttu-id="a7f02-1596">numero dell'edizione
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1596">numero dell'edizione</span></span> 
- <span data-ttu-id="a7f02-1597">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="a7f02-1597">numero di identificazione della</span></span> 
- <span data-ttu-id="a7f02-1598">scheda
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1598">scheda</span></span> 
- <span data-ttu-id="a7f02-1599">numero di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1599">numero di sicurezza</span></span> 
- <span data-ttu-id="a7f02-1600">numero van veiligheid
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1600">numero van veiligheid</span></span> 
- <span data-ttu-id="a7f02-1601">numéro de sécurité
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1601">numéro de sécurité</span></span> 
- <span data-ttu-id="a7f02-1602">nº autorizzazione
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1602">nº autorizzazione</span></span> 
- <span data-ttu-id="a7f02-1603">número de verificação
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1603">número de verificação</span></span> 
- <span data-ttu-id="a7f02-1604">perno il blocco
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1604">perno il blocco</span></span> 
- <span data-ttu-id="a7f02-1605">pin block
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1605">pin block</span></span> 
- <span data-ttu-id="a7f02-1606">prufziffer
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1606">prufziffer</span></span> 
- <span data-ttu-id="a7f02-1607">prüfziffer
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1607">prüfziffer</span></span> 
- <span data-ttu-id="a7f02-1608">security code
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1608">security code</span></span> 
- <span data-ttu-id="a7f02-1609">security no
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1609">security no</span></span> 
- <span data-ttu-id="a7f02-1610">security number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1610">security number</span></span> 
- <span data-ttu-id="a7f02-1611">sicherheits kode
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1611">sicherheits kode</span></span> 
- <span data-ttu-id="a7f02-1612">sicherheitscode
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1612">sicherheitscode</span></span> 
- <span data-ttu-id="a7f02-1613">sicherheitsnummer
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1613">sicherheitsnummer</span></span> 
- <span data-ttu-id="a7f02-1614">speldblok
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1614">speldblok</span></span> 
- <span data-ttu-id="a7f02-1615">veiligheid nr
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1615">veiligheid nr</span></span> 
- <span data-ttu-id="a7f02-1616">veiligheidsaantal
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1616">veiligheidsaantal</span></span> 
- <span data-ttu-id="a7f02-1617">veiligheidscode
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1617">veiligheidscode</span></span> 
- <span data-ttu-id="a7f02-1618">veiligheidsnummer
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1618">veiligheidsnummer</span></span> 
- <span data-ttu-id="a7f02-1619">verfalldatum
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1619">verfalldatum</span></span> 

#### <a name="keywordcardexpirationtermsdict"></a><span data-ttu-id="a7f02-1620">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="a7f02-1620">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="a7f02-1621">ablauf
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1621">ablauf</span></span> 
- <span data-ttu-id="a7f02-1622">data de expiracao
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1622">data de expiracao</span></span> 
- <span data-ttu-id="a7f02-1623">data de expiração
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1623">data de expiração</span></span> 
- <span data-ttu-id="a7f02-1624">data del exp
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1624">data del exp</span></span> 
- <span data-ttu-id="a7f02-1625">data di exp
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1625">data di exp</span></span> 
- <span data-ttu-id="a7f02-1626">data di scadenza
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1626">data di scadenza</span></span> 
- <span data-ttu-id="a7f02-1627">data em que expira
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1627">data em que expira</span></span> 
- <span data-ttu-id="a7f02-1628">data scad
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1628">data scad</span></span> 
- <span data-ttu-id="a7f02-1629">data scadenza
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1629">data scadenza</span></span> 
- <span data-ttu-id="a7f02-1630">date de validité
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1630">date de validité</span></span> 
- <span data-ttu-id="a7f02-1631">datum afloop
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1631">datum afloop</span></span> 
- <span data-ttu-id="a7f02-1632">datum van exp
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1632">datum van exp</span></span> 
- <span data-ttu-id="a7f02-1633">de afloop
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1633">de afloop</span></span> 
- <span data-ttu-id="a7f02-1634">espira
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1634">espira</span></span> 
- <span data-ttu-id="a7f02-1635">espira
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1635">espira</span></span> 
- <span data-ttu-id="a7f02-1636">exp date
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1636">exp date</span></span> 
- <span data-ttu-id="a7f02-1637">exp datum
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1637">exp datum</span></span> 
- <span data-ttu-id="a7f02-1638">过期</span><span class="sxs-lookup"><span data-stu-id="a7f02-1638">expiration</span></span> 
- <span data-ttu-id="a7f02-1639">expire
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1639">expire</span></span> 
- <span data-ttu-id="a7f02-1640">expires
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1640">expires</span></span> 
- <span data-ttu-id="a7f02-1641">expiry
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1641">expiry</span></span> 
- <span data-ttu-id="a7f02-1642">fecha de expiracion
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1642">fecha de expiracion</span></span> 
- <span data-ttu-id="a7f02-1643">fecha de venc
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1643">fecha de venc</span></span> 
- <span data-ttu-id="a7f02-1644">gultig bis
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1644">gultig bis</span></span> 
- <span data-ttu-id="a7f02-1645">gultigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1645">gultigkeitsdatum</span></span> 
- <span data-ttu-id="a7f02-1646">gültig bis
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1646">gültig bis</span></span> 
- <span data-ttu-id="a7f02-1647">gültigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1647">gültigkeitsdatum</span></span> 
- <span data-ttu-id="a7f02-1648">la scadenza
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1648">la scadenza</span></span> 
- <span data-ttu-id="a7f02-1649">scadenza
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1649">scadenza</span></span> 
- <span data-ttu-id="a7f02-1650">valable
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1650">valable</span></span> 
- <span data-ttu-id="a7f02-1651">validade
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1651">validade</span></span> 
- <span data-ttu-id="a7f02-1652">valido hasta
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1652">valido hasta</span></span> 
- <span data-ttu-id="a7f02-1653">valor
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1653">valor</span></span> 
- <span data-ttu-id="a7f02-1654">venc
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1654">venc</span></span> 
- <span data-ttu-id="a7f02-1655">vencimento
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1655">vencimento</span></span> 
- <span data-ttu-id="a7f02-1656">vencimiento
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1656">vencimiento</span></span> 
- <span data-ttu-id="a7f02-1657">verloopt
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1657">verloopt</span></span> 
- <span data-ttu-id="a7f02-1658">vervaldag
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1658">vervaldag</span></span> 
- <span data-ttu-id="a7f02-1659">vervaldatum
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1659">vervaldatum</span></span> 
- <span data-ttu-id="a7f02-1660">vto
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1660">vto</span></span> 
- <span data-ttu-id="a7f02-1661">válido hasta
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1661">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="a7f02-1662">欧盟驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-1662">EU Driver's License Number</span></span>

<span data-ttu-id="a7f02-1663">若要了解详细信息，请参阅[欧盟驱动程序驾驶证号码敏感信息类型](eu-driver-s-license-number.md)。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1663">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="a7f02-1664">欧盟 National 标识号</span><span class="sxs-lookup"><span data-stu-id="a7f02-1664">EU National Identification Number</span></span>

<span data-ttu-id="a7f02-1665">若要了解详细信息，请参阅[欧盟国家/地区标识号敏感信息类型](eu-national-identification-number.md)。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1665">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="a7f02-1666">欧盟护照号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-1666">EU Passport Number</span></span>

<span data-ttu-id="a7f02-1667">若要了解详细信息，请参阅[欧盟护照号码敏感信息类型](eu-passport-number.md)。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1667">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="a7f02-1668">欧盟社会保险号或等效 ID</span><span class="sxs-lookup"><span data-stu-id="a7f02-1668">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="a7f02-1669">若要了解详细信息，请参阅[欧盟社会保险号或等效 ID 敏感信息类型](eu-social-security-number-or-equivalent-id.md)。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1669">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="a7f02-1670">欧盟纳税标识号</span><span class="sxs-lookup"><span data-stu-id="a7f02-1670">EU Tax Identification Number</span></span>

<span data-ttu-id="a7f02-1671">若要了解详细信息，请参阅[欧盟纳税标识号敏感信息类型](eu-tax-identification-number.md)。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1671">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="a7f02-1672">芬兰国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="a7f02-1672">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-1673">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-1673">Format</span></span>

<span data-ttu-id="a7f02-1674">六个数字加一个字符（表示一个世纪），加三个数字再加一个校验位</span><span class="sxs-lookup"><span data-stu-id="a7f02-1674">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-1675">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-1675">Pattern</span></span>

<span data-ttu-id="a7f02-1676">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1676">Pattern must include all of the following:</span></span>
- <span data-ttu-id="a7f02-1677">采用 DDMMYY 格式的六位数字，表示出生日期</span><span class="sxs-lookup"><span data-stu-id="a7f02-1677">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="a7f02-1678">世纪标记（“-”、“+”或“a”）</span><span class="sxs-lookup"><span data-stu-id="a7f02-1678">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="a7f02-1679">三位个人标识号</span><span class="sxs-lookup"><span data-stu-id="a7f02-1679">Three-digit personal identification number</span></span> 
- <span data-ttu-id="a7f02-1680">一个数字或字母（区分大小写），是校验位</span><span class="sxs-lookup"><span data-stu-id="a7f02-1680">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-1681">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-1681">Checksum</span></span>

<span data-ttu-id="a7f02-1682">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-1682">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-1683">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-1683">Definition</span></span>

<span data-ttu-id="a7f02-1684">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1684">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-1685">函数 Func_finnish_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1685">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-1686">找到 Keyword_finnish_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1686">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="a7f02-1687">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1687">The checksum passes.</span></span>

```
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7f02-1688">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1688">Keywords</span></span>

- <span data-ttu-id="a7f02-1689">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="a7f02-1689">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="a7f02-1690">

Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="a7f02-1690">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="a7f02-1691">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="a7f02-1691">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="a7f02-1692">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="a7f02-1692">Personbeteckning</span></span>
- <span data-ttu-id="a7f02-1693">Personnummer</span><span class="sxs-lookup"><span data-stu-id="a7f02-1693">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="a7f02-1694">芬兰护照号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-1694">Finland Passport Number</span></span>

<span data-ttu-id="a7f02-p130">设置格式的九个字母和数字模式的九个字母和数字的组合组合： 两个字母 （不区分大小写） 的第七位数字校验和无定义 DLP 策略为 75%确信，如果，它已检测到此类型的敏感信息，在两者之间300 个字符的邻近性： 正则表达式 Regex_finland_passport_number 找到与模式匹配的内容。找到从 Keyword_finland_passport_number 关键字。<!-- Finland Passport Number --> 
 <Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern> 
</Entity>关键字 Keyword_finland_passport_number Passport Passi</span><span class="sxs-lookup"><span data-stu-id="a7f02-p130">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern. A keyword from Keyword_finland_passport_number is found. <!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity> Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="a7f02-1699">法国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-1699">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-1700">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-1700">Format</span></span>

<span data-ttu-id="a7f02-1701">12 个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1701">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-1702">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-1702">Pattern</span></span>

<span data-ttu-id="a7f02-1703">12 个数字，会对类似模式（如法国电话号码）进行验证</span><span class="sxs-lookup"><span data-stu-id="a7f02-1703">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-1704">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-1704">Checksum</span></span>

<span data-ttu-id="a7f02-1705">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-1705">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-1706">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-1706">Definition</span></span>

<span data-ttu-id="a7f02-1707">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1707">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-1708">函数 Func_french_drivers_license 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1708">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-1709">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1709">At least one of the following is true:</span></span>
- <span data-ttu-id="a7f02-1710">找到 Keyword_french_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1710">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="a7f02-1711">函数 Func_eu_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1711">The function Func_eu_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-1712">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1712">Keywords</span></span>

#### <a name="keywordfrenchdriverslicense"></a><span data-ttu-id="a7f02-1713">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="a7f02-1713">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="a7f02-1714">drivers licence</span><span class="sxs-lookup"><span data-stu-id="a7f02-1714">drivers licence</span></span>
- <span data-ttu-id="a7f02-1715">drivers license</span><span class="sxs-lookup"><span data-stu-id="a7f02-1715">drivers license</span></span>
- <span data-ttu-id="a7f02-1716">driving licence
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1716">driving licence</span></span>
- <span data-ttu-id="a7f02-1717">驱动许可证</span><span class="sxs-lookup"><span data-stu-id="a7f02-1717">driving license</span></span>
- <span data-ttu-id="a7f02-1718">
permis de conduire</span><span class="sxs-lookup"><span data-stu-id="a7f02-1718">permis de conduire</span></span>
- <span data-ttu-id="a7f02-1719">
licence number</span><span class="sxs-lookup"><span data-stu-id="a7f02-1719">licence number</span></span>
- <span data-ttu-id="a7f02-1720">
license number</span><span class="sxs-lookup"><span data-stu-id="a7f02-1720">license number</span></span>
- <span data-ttu-id="a7f02-1721">
licence numbers</span><span class="sxs-lookup"><span data-stu-id="a7f02-1721">licence numbers</span></span>
- <span data-ttu-id="a7f02-1722">

license numbers</span><span class="sxs-lookup"><span data-stu-id="a7f02-1722">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="a7f02-1723">法国国家/地区 ID 卡 (CNI)</span><span class="sxs-lookup"><span data-stu-id="a7f02-1723">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-1724">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-1724">Format</span></span>

<span data-ttu-id="a7f02-1725">12 个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1725">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-1726">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-1726">Pattern</span></span>

<span data-ttu-id="a7f02-1727">12 个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1727">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-1728">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-1728">Checksum</span></span>

<span data-ttu-id="a7f02-1729">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-1729">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-1730">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-1730">Definition</span></span>

<span data-ttu-id="a7f02-1731">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1731">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-1732">正则表达式 Regex_france_cni 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1732">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7f02-1733">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1733">Keywords</span></span>

<span data-ttu-id="a7f02-1734">无</span><span class="sxs-lookup"><span data-stu-id="a7f02-1734">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="a7f02-1735">法国护照号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-1735">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-1736">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-1736">Format</span></span>

<span data-ttu-id="a7f02-1737">9 个数字和字母</span><span class="sxs-lookup"><span data-stu-id="a7f02-1737">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-1738">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-1738">Pattern</span></span>

<span data-ttu-id="a7f02-1739">九位数字和字母：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1739">Nine digits and letters:</span></span>
- <span data-ttu-id="a7f02-1740">两位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1740">Two digits</span></span> 
- <span data-ttu-id="a7f02-1741">两个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="a7f02-1741">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="a7f02-1742">五位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1742">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-1743">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-1743">Checksum</span></span>

<span data-ttu-id="a7f02-1744">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-1744">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-1745">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-1745">Definition</span></span>

<span data-ttu-id="a7f02-1746">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1746">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-1747">函数 Func_fr_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1747">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-1748">找到 Keyword_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1748">A keyword from Keyword_passport is found.</span></span>

```
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7f02-1749">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1749">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="a7f02-1750">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="a7f02-1750">Keyword_passport</span></span>

- <span data-ttu-id="a7f02-1751">Passport Number</span><span class="sxs-lookup"><span data-stu-id="a7f02-1751">Passport Number</span></span>
- <span data-ttu-id="a7f02-1752">
Passport No</span><span class="sxs-lookup"><span data-stu-id="a7f02-1752">Passport No</span></span>
- <span data-ttu-id="a7f02-1753">Passport #
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1753">Passport #</span></span>
- <span data-ttu-id="a7f02-1754">Passport#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1754">Passport#</span></span>
- <span data-ttu-id="a7f02-1755">PassportID</span><span class="sxs-lookup"><span data-stu-id="a7f02-1755">PassportID</span></span>
- <span data-ttu-id="a7f02-1756">Passportno
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1756">Passportno</span></span>
- <span data-ttu-id="a7f02-1757">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1757">passportnumber</span></span>
- <span data-ttu-id="a7f02-1758">パスポート</span><span class="sxs-lookup"><span data-stu-id="a7f02-1758">パスポート</span></span>
- <span data-ttu-id="a7f02-1759">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1759">パスポート番号</span></span>
- <span data-ttu-id="a7f02-1760">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1760">パスポートのNum</span></span>
- <span data-ttu-id="a7f02-1761">
パスポート ＃
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1761">パスポート ＃</span></span> 
- <span data-ttu-id="a7f02-1762">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="a7f02-1762">Numéro de passeport</span></span>
- <span data-ttu-id="a7f02-1763">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="a7f02-1763">Passeport n °</span></span>
- <span data-ttu-id="a7f02-1764">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1764">Passeport Non</span></span>
- <span data-ttu-id="a7f02-1765">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1765">Passeport #</span></span>
- <span data-ttu-id="a7f02-1766">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1766">Passeport#</span></span>
- <span data-ttu-id="a7f02-1767">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="a7f02-1767">PasseportNon</span></span>
- <span data-ttu-id="a7f02-1768">

Passeportn °</span><span class="sxs-lookup"><span data-stu-id="a7f02-1768">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="a7f02-1769">法国社会保险号 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="a7f02-1769">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-1770">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-1770">Format</span></span>

<span data-ttu-id="a7f02-1771">15 个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1771">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-1772">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-1772">Pattern</span></span>

<span data-ttu-id="a7f02-1773">必须匹配两种模式之一：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1773">Must match one of two patterns:</span></span>
- <span data-ttu-id="a7f02-1774">13 跟两位数字后跟一个空格的数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1774">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="a7f02-1775">或</span><span class="sxs-lookup"><span data-stu-id="a7f02-1775">or</span></span>
- <span data-ttu-id="a7f02-1776">15 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1776">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-1777">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-1777">Checksum</span></span>

<span data-ttu-id="a7f02-1778">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-1778">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-1779">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-1779">Definition</span></span>

<span data-ttu-id="a7f02-1780">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1780">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-1781">函数 Func_french_insee 或 Func_fr_insee 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1781">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-1782">找到 Keyword_fr_insee 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1782">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="a7f02-1783">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1783">The checksum passes.</span></span>

<span data-ttu-id="a7f02-1784">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1784">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-1785">函数 Func_french_insee 或 Func_fr_insee 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1785">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-1786">未找到 Keyword_fr_insee 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1786">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="a7f02-1787">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1787">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-1788">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1788">Keywords</span></span>

#### <a name="keywordfrinsee"></a><span data-ttu-id="a7f02-1789">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="a7f02-1789">Keyword_fr_insee</span></span>

- <span data-ttu-id="a7f02-1790">insee</span><span class="sxs-lookup"><span data-stu-id="a7f02-1790">insee</span></span>
- <span data-ttu-id="a7f02-1791">
securité sociale</span><span class="sxs-lookup"><span data-stu-id="a7f02-1791">securité sociale</span></span>
- <span data-ttu-id="a7f02-1792">
securite sociale</span><span class="sxs-lookup"><span data-stu-id="a7f02-1792">securite sociale</span></span>
- <span data-ttu-id="a7f02-1793">
national id</span><span class="sxs-lookup"><span data-stu-id="a7f02-1793">national id</span></span>
- <span data-ttu-id="a7f02-1794">
national identification</span><span class="sxs-lookup"><span data-stu-id="a7f02-1794">national identification</span></span>
- <span data-ttu-id="a7f02-1795">
numéro d identité</span><span class="sxs-lookup"><span data-stu-id="a7f02-1795">numéro d'identité</span></span>
- <span data-ttu-id="a7f02-1796">没有 d'identité</span><span class="sxs-lookup"><span data-stu-id="a7f02-1796">no d'identité</span></span>
- <span data-ttu-id="a7f02-p131">
no. d'identité</span><span class="sxs-lookup"><span data-stu-id="a7f02-p131">no. d'identité</span></span>
- <span data-ttu-id="a7f02-1799">
numero d'identite</span><span class="sxs-lookup"><span data-stu-id="a7f02-1799">numero d'identite</span></span>
- <span data-ttu-id="a7f02-1800">没有 d'identite</span><span class="sxs-lookup"><span data-stu-id="a7f02-1800">no d'identite</span></span>
- <span data-ttu-id="a7f02-p132">
no. d'identite</span><span class="sxs-lookup"><span data-stu-id="a7f02-p132">no. d'identite</span></span>
- <span data-ttu-id="a7f02-1803">social security number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1803">social security number</span></span>
- <span data-ttu-id="a7f02-1804">
social security code</span><span class="sxs-lookup"><span data-stu-id="a7f02-1804">social security code</span></span>
- <span data-ttu-id="a7f02-1805">social insurance number</span><span class="sxs-lookup"><span data-stu-id="a7f02-1805">social insurance number</span></span>
- <span data-ttu-id="a7f02-1806">
le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="a7f02-1806">le numéro d'identification nationale</span></span>
- <span data-ttu-id="a7f02-1807">
d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="a7f02-1807">d'identité nationale</span></span>
- <span data-ttu-id="a7f02-1808">
numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="a7f02-1808">numéro de sécurité sociale</span></span>
- <span data-ttu-id="a7f02-1809">
le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="a7f02-1809">le code de la sécurité sociale</span></span>
- <span data-ttu-id="a7f02-1810">
numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="a7f02-1810">numéro d'assurance sociale</span></span>
- <span data-ttu-id="a7f02-1811">
numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="a7f02-1811">numéro de sécu</span></span>
- <span data-ttu-id="a7f02-1812">
code sécu
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1812">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="a7f02-1813">德国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-1813">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-1814">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-1814">Format</span></span>

<span data-ttu-id="a7f02-1815">11 个数字和字母组合</span><span class="sxs-lookup"><span data-stu-id="a7f02-1815">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-1816">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-1816">Pattern</span></span>

<span data-ttu-id="a7f02-1817">11 位数字和字母（不区分大小写）：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1817">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="a7f02-1818">一个数字或字母</span><span class="sxs-lookup"><span data-stu-id="a7f02-1818">A digit or letter</span></span> 
- <span data-ttu-id="a7f02-1819">两位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1819">Two digits</span></span> 
- <span data-ttu-id="a7f02-1820">六位数字或字母</span><span class="sxs-lookup"><span data-stu-id="a7f02-1820">Six digits or letters</span></span> 
- <span data-ttu-id="a7f02-1821">一位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1821">A digit</span></span> 
- <span data-ttu-id="a7f02-1822">一个数字或字母</span><span class="sxs-lookup"><span data-stu-id="a7f02-1822">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-1823">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-1823">Checksum</span></span>

<span data-ttu-id="a7f02-1824">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-1824">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-1825">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-1825">Definition</span></span>

<span data-ttu-id="a7f02-1826">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1826">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-1827">函数 Func_german_drivers_license 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1827">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-1828">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1828">At least one of the following is true:</span></span>
    - <span data-ttu-id="a7f02-1829">找到 Keyword_german_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1829">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="a7f02-1830">找到 Keyword_german_drivers_license_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1830">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="a7f02-1831">找到 Keyword_german_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1831">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="a7f02-1832">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1832">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-1833">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1833">Keywords</span></span>

#### <a name="keywordgermandriverslicensenumber"></a><span data-ttu-id="a7f02-1834">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="a7f02-1834">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="a7f02-1835">Führerschein</span><span class="sxs-lookup"><span data-stu-id="a7f02-1835">Führerschein</span></span>
- <span data-ttu-id="a7f02-1836">
Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="a7f02-1836">Fuhrerschein</span></span>
- <span data-ttu-id="a7f02-1837">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="a7f02-1837">Fuehrerschein</span></span>
- <span data-ttu-id="a7f02-1838">
Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="a7f02-1838">Führerscheinnummer</span></span>
- <span data-ttu-id="a7f02-1839">
Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="a7f02-1839">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="a7f02-1840">
Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="a7f02-1840">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="a7f02-1841">
Führerschein-
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1841">Führerschein-</span></span> 
- <span data-ttu-id="a7f02-1842">Fuhrerschein-
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1842">Fuhrerschein-</span></span> 
- <span data-ttu-id="a7f02-1843">Fuehrerschein-
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1843">Fuehrerschein-</span></span> 
- <span data-ttu-id="a7f02-1844">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="a7f02-1844">FührerscheinnummerNr</span></span>
- <span data-ttu-id="a7f02-1845">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="a7f02-1845">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="a7f02-1846">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="a7f02-1846">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="a7f02-1847">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="a7f02-1847">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="a7f02-1848">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="a7f02-1848">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="a7f02-1849">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="a7f02-1849">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="a7f02-1850">Führerschein-Nr
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1850">Führerschein- Nr</span></span>
- <span data-ttu-id="a7f02-1851">Fuhrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1851">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="a7f02-1852">Fuehrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1852">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="a7f02-1853">Führerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1853">Führerschein- Klasse</span></span> 
- <span data-ttu-id="a7f02-1854">Fuhrerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1854">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="a7f02-1855">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="a7f02-1855">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="a7f02-1856">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="a7f02-1856">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="a7f02-1857">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="a7f02-1857">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="a7f02-1858">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="a7f02-1858">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="a7f02-1859">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="a7f02-1859">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="a7f02-1860">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="a7f02-1860">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="a7f02-1861">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="a7f02-1861">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="a7f02-1862">Führerschein-Nr
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1862">Führerschein- Nr</span></span> 
- <span data-ttu-id="a7f02-1863">Fuhrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1863">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="a7f02-1864">Fuehrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1864">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="a7f02-1865">Führerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1865">Führerschein- Klasse</span></span> 
- <span data-ttu-id="a7f02-1866">Fuhrerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1866">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="a7f02-1867">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="a7f02-1867">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="a7f02-1868">DL</span><span class="sxs-lookup"><span data-stu-id="a7f02-1868">DL</span></span> 
- <span data-ttu-id="a7f02-1869">DLS</span><span class="sxs-lookup"><span data-stu-id="a7f02-1869">DLS</span></span>
- <span data-ttu-id="a7f02-1870">
Driv Lic
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1870">Driv Lic</span></span> 
- <span data-ttu-id="a7f02-1871">Driv Licen
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1871">Driv Licen</span></span> 
- <span data-ttu-id="a7f02-1872">Driv License</span><span class="sxs-lookup"><span data-stu-id="a7f02-1872">Driv License</span></span>
- <span data-ttu-id="a7f02-1873">
Driv Licenses
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1873">Driv Licenses</span></span> 
- <span data-ttu-id="a7f02-1874">Driv Licence
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1874">Driv Licence</span></span> 
- <span data-ttu-id="a7f02-1875">Driv Licences
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1875">Driv Licences</span></span> 
- <span data-ttu-id="a7f02-1876">Driv Lic
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1876">Driv Lic</span></span> 
- <span data-ttu-id="a7f02-1877">Driver Licen
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1877">Driver Licen</span></span> 
- <span data-ttu-id="a7f02-1878">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="a7f02-1878">Driver License</span></span> 
- <span data-ttu-id="a7f02-1879">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="a7f02-1879">Driver Licenses</span></span> 
- <span data-ttu-id="a7f02-1880">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1880">Driver Licence</span></span> 
- <span data-ttu-id="a7f02-1881">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1881">Driver Licences</span></span> 
- <span data-ttu-id="a7f02-1882">驱动因素 Lic</span><span class="sxs-lookup"><span data-stu-id="a7f02-1882">Drivers Lic</span></span> 
- <span data-ttu-id="a7f02-1883">驱动因素 Licen</span><span class="sxs-lookup"><span data-stu-id="a7f02-1883">Drivers Licen</span></span> 
- <span data-ttu-id="a7f02-1884">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="a7f02-1884">Drivers License</span></span> 
- <span data-ttu-id="a7f02-1885">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="a7f02-1885">Drivers Licenses</span></span> 
- <span data-ttu-id="a7f02-1886">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="a7f02-1886">Drivers Licence</span></span> 
- <span data-ttu-id="a7f02-1887">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="a7f02-1887">Drivers Licences</span></span> 
- <span data-ttu-id="a7f02-1888">驱动因素的 Lic</span><span class="sxs-lookup"><span data-stu-id="a7f02-1888">Driver's Lic</span></span> 
- <span data-ttu-id="a7f02-1889">Driver's Licen
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1889">Driver's Licen</span></span> 
- <span data-ttu-id="a7f02-1890">驱动程序的许可证</span><span class="sxs-lookup"><span data-stu-id="a7f02-1890">Driver's License</span></span> 
- <span data-ttu-id="a7f02-1891">驱动程序的许可证</span><span class="sxs-lookup"><span data-stu-id="a7f02-1891">Driver's Licenses</span></span> 
- <span data-ttu-id="a7f02-1892">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1892">Driver's Licence</span></span> 
- <span data-ttu-id="a7f02-1893">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1893">Driver's Licences</span></span> 
- <span data-ttu-id="a7f02-1894">Driving Lic
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1894">Driving Lic</span></span> 
- <span data-ttu-id="a7f02-1895">Driving Licen
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1895">Driving Licen</span></span> 
- <span data-ttu-id="a7f02-1896">Driving License
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1896">Driving License</span></span> 
- <span data-ttu-id="a7f02-1897">Driving Licenses
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1897">Driving Licenses</span></span> 
- <span data-ttu-id="a7f02-1898">Driving Licence

</span><span class="sxs-lookup"><span data-stu-id="a7f02-1898">Driving Licence</span></span> 
- <span data-ttu-id="a7f02-1899">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="a7f02-1899">Driving Licences</span></span>

#### <a name="keywordgermandriverslicensecollaborative"></a><span data-ttu-id="a7f02-1900">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="a7f02-1900">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="a7f02-1901">
Nr-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1901">Nr-Führerschein</span></span> 
- <span data-ttu-id="a7f02-1902">Nr-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1902">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="a7f02-1903">Nr-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1903">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="a7f02-1904">No-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1904">No-Führerschein</span></span> 
- <span data-ttu-id="a7f02-1905">No-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1905">No-Fuhrerschein</span></span> 
- <span data-ttu-id="a7f02-1906">No-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1906">No-Fuehrerschein</span></span> 
- <span data-ttu-id="a7f02-1907">N-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1907">N-Führerschein</span></span> 
- <span data-ttu-id="a7f02-1908">N-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1908">N-Fuhrerschein</span></span> 
- <span data-ttu-id="a7f02-1909">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="a7f02-1909">N-Fuehrerschein</span></span>
- <span data-ttu-id="a7f02-1910">
Nr-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1910">Nr-Führerschein</span></span> 
- <span data-ttu-id="a7f02-1911">Nr-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1911">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="a7f02-1912">Nr-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1912">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="a7f02-1913">No-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1913">No-Führerschein</span></span> 
- <span data-ttu-id="a7f02-1914">No-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1914">No-Fuhrerschein</span></span> 
- <span data-ttu-id="a7f02-1915">No-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1915">No-Fuehrerschein</span></span> 
- <span data-ttu-id="a7f02-1916">N-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1916">N-Führerschein</span></span> 
- <span data-ttu-id="a7f02-1917">N-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1917">N-Fuhrerschein</span></span> 
- <span data-ttu-id="a7f02-1918">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="a7f02-1918">N-Fuehrerschein</span></span> 

#### <a name="keywordgermandriverslicense"></a><span data-ttu-id="a7f02-1919">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="a7f02-1919">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="a7f02-1920">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="a7f02-1920">ausstellungsdatum</span></span>
- <span data-ttu-id="a7f02-1921">
ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="a7f02-1921">ausstellungsort</span></span>
- <span data-ttu-id="a7f02-1922">
ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="a7f02-1922">ausstellende behöde</span></span>
- <span data-ttu-id="a7f02-1923">
ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="a7f02-1923">ausstellende behorde</span></span>
- <span data-ttu-id="a7f02-1924">

ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="a7f02-1924">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="a7f02-1925">德国护照号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-1925">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-1926">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-1926">Format</span></span>

<span data-ttu-id="a7f02-1927">10 个数字或字母</span><span class="sxs-lookup"><span data-stu-id="a7f02-1927">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-1928">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-1928">Pattern</span></span>

<span data-ttu-id="a7f02-1929">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1929">Pattern must include all of the following:</span></span>
- <span data-ttu-id="a7f02-1930">第一个字符是这一组（C、F、G、H、J、K）中的数字或字母</span><span class="sxs-lookup"><span data-stu-id="a7f02-1930">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="a7f02-1931">三位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1931">Three digits</span></span> 
- <span data-ttu-id="a7f02-1932">五位数字或字母都来源于这一组（C、-H、J-N、P、R、T，V-Z）</span><span class="sxs-lookup"><span data-stu-id="a7f02-1932">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="a7f02-1933">一位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1933">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-1934">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-1934">Checksum</span></span>

<span data-ttu-id="a7f02-1935">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-1935">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-1936">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-1936">Definition</span></span>

<span data-ttu-id="a7f02-1937">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1937">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-1938">函数 Func_german_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1938">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-1939">找到以下任意五个关键字列表中的关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1939">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="a7f02-1940">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1940">The checksum passes.</span></span>

<span data-ttu-id="a7f02-1941">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1941">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-1942">函数 Func_german_passport_data 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1942">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-1943">找到以下任意五个关键字列表中的关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1943">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="a7f02-1944">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1944">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-1945">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1945">Keywords</span></span>

#### <a name="keywordgermanpassport"></a><span data-ttu-id="a7f02-1946">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="a7f02-1946">Keyword_german_passport</span></span>

- <span data-ttu-id="a7f02-1947">reisepass</span><span class="sxs-lookup"><span data-stu-id="a7f02-1947">reisepass</span></span>
- <span data-ttu-id="a7f02-1948">
reisepasse</span><span class="sxs-lookup"><span data-stu-id="a7f02-1948">reisepasse</span></span>
- <span data-ttu-id="a7f02-1949">
reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="a7f02-1949">reisepassnummer</span></span>
- <span data-ttu-id="a7f02-1950">passport</span><span class="sxs-lookup"><span data-stu-id="a7f02-1950">passport</span></span>
- <span data-ttu-id="a7f02-1951">

passports</span><span class="sxs-lookup"><span data-stu-id="a7f02-1951">passports</span></span>

#### <a name="keywordgermanpassportcollaborative"></a><span data-ttu-id="a7f02-1952">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="a7f02-1952">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="a7f02-1953">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="a7f02-1953">geburtsdatum</span></span>
- <span data-ttu-id="a7f02-1954">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="a7f02-1954">ausstellungsdatum</span></span>
- <span data-ttu-id="a7f02-1955">
ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="a7f02-1955">ausstellungsort</span></span>

#### <a name="keywordgermanpassportnumber"></a><span data-ttu-id="a7f02-1956">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="a7f02-1956">Keyword_german_passport_number</span></span>

<span data-ttu-id="a7f02-1957">不-Reisepass Nr Reisepass</span><span class="sxs-lookup"><span data-stu-id="a7f02-1957">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keywordgermanpassport1"></a><span data-ttu-id="a7f02-1958">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="a7f02-1958">Keyword_german_passport1</span></span>

<span data-ttu-id="a7f02-1959">Reisepass-Nr
</span><span class="sxs-lookup"><span data-stu-id="a7f02-1959">Reisepass-Nr</span></span>

#### <a name="keywordgermanpassport2"></a><span data-ttu-id="a7f02-1960">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="a7f02-1960">Keyword_german_passport2</span></span>

<span data-ttu-id="a7f02-1961">bnationalit.t</span><span class="sxs-lookup"><span data-stu-id="a7f02-1961">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="a7f02-1962">德国身份证号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-1962">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-1963">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-1963">Format</span></span>

<span data-ttu-id="a7f02-1964">2010 年 11 月 1 相： 九个字母和数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1964">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="a7f02-1965">从直到 31 年 10 月 2010年: 10 位数字 1 年 4 月 1987</span><span class="sxs-lookup"><span data-stu-id="a7f02-1965">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-1966">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-1966">Pattern</span></span>

<span data-ttu-id="a7f02-1967">自 2010 年 11 月 1 日起：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1967">Since 1 November 2010:</span></span>
- <span data-ttu-id="a7f02-1968">一个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="a7f02-1968">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="a7f02-1969">八个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1969">Eight digits</span></span>

<span data-ttu-id="a7f02-1970">从直到 31 2010 年 10 月 1 年 4 月 1987:</span><span class="sxs-lookup"><span data-stu-id="a7f02-1970">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="a7f02-1971">10 个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1971">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-1972">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-1972">Checksum</span></span>

<span data-ttu-id="a7f02-1973">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-1973">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-1974">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-1974">Definition</span></span>

<span data-ttu-id="a7f02-1975">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1975">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-1976">正则表达式 Regex_germany_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1976">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-1977">找到 Keyword_germany_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-1977">A keyword from Keyword_germany_id_card is found.</span></span>

```
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7f02-1978">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1978">Keywords</span></span>

#### <a name="keywordgermanyidcard"></a><span data-ttu-id="a7f02-1979">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="a7f02-1979">Keyword_germany_id_card</span></span>

- <span data-ttu-id="a7f02-1980">Identity Card</span><span class="sxs-lookup"><span data-stu-id="a7f02-1980">Identity Card</span></span>
- <span data-ttu-id="a7f02-1981">ID</span><span class="sxs-lookup"><span data-stu-id="a7f02-1981">ID</span></span>
- <span data-ttu-id="a7f02-1982">Identification</span><span class="sxs-lookup"><span data-stu-id="a7f02-1982">Identification</span></span>
- <span data-ttu-id="a7f02-1983">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="a7f02-1983">Personalausweis</span></span>
- <span data-ttu-id="a7f02-1984">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="a7f02-1984">Identifizierungsnummer</span></span>
- <span data-ttu-id="a7f02-1985">Ausweis</span><span class="sxs-lookup"><span data-stu-id="a7f02-1985">Ausweis</span></span>
- <span data-ttu-id="a7f02-1986">Identifikation</span><span class="sxs-lookup"><span data-stu-id="a7f02-1986">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="a7f02-1987">希腊国家 ID 卡</span><span class="sxs-lookup"><span data-stu-id="a7f02-1987">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-1988">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-1988">Format</span></span>

<span data-ttu-id="a7f02-1989">7-8 个字母和数字组合加一个短划线</span><span class="sxs-lookup"><span data-stu-id="a7f02-1989">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-1990">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-1990">Pattern</span></span>

<span data-ttu-id="a7f02-1991">七个字母和数字（旧格式）：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1991">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="a7f02-1992">一个字母（希腊字母表中的任一字母） </span><span class="sxs-lookup"><span data-stu-id="a7f02-1992">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="a7f02-1993">一个短划线 </span><span class="sxs-lookup"><span data-stu-id="a7f02-1993">A dash</span></span> 
- <span data-ttu-id="a7f02-1994">六个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1994">Six digits</span></span>

<span data-ttu-id="a7f02-1995">八个字母和数字（新格式）：</span><span class="sxs-lookup"><span data-stu-id="a7f02-1995">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="a7f02-1996">大写字符同时出现在希腊和拉丁字母表中的两个字母 (ABEZHIKMNOPTYX) </span><span class="sxs-lookup"><span data-stu-id="a7f02-1996">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="a7f02-1997">一个短划线 </span><span class="sxs-lookup"><span data-stu-id="a7f02-1997">A dash</span></span> 
- <span data-ttu-id="a7f02-1998">六个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-1998">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-1999">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-1999">Checksum</span></span>

<span data-ttu-id="a7f02-2000">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-2000">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2001">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2001">Definition</span></span>

<span data-ttu-id="a7f02-2002">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2002">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2003">正则表达式 Regex_greece_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2003">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2004">找到 Keyword_greece_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2004">A keyword from Keyword_greece_id_card is found.</span></span>

```
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7f02-2005">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2005">Keywords</span></span>

#### <a name="keywordgreeceidcard"></a><span data-ttu-id="a7f02-2006">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="a7f02-2006">Keyword_greece_id_card</span></span>

- <span data-ttu-id="a7f02-2007">Greek identity Card</span><span class="sxs-lookup"><span data-stu-id="a7f02-2007">Greek identity Card</span></span>
- <span data-ttu-id="a7f02-2008">Tautotita</span><span class="sxs-lookup"><span data-stu-id="a7f02-2008">Tautotita</span></span>
- <span data-ttu-id="a7f02-2009">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="a7f02-2009">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="a7f02-2010">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="a7f02-2010">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="a7f02-2011">香港身份证 (HKID) 号</span><span class="sxs-lookup"><span data-stu-id="a7f02-2011">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2012">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2012">Format</span></span>

<span data-ttu-id="a7f02-2013">8-9 个字母和数字组合，最后一个字符两边可选择加括号</span><span class="sxs-lookup"><span data-stu-id="a7f02-2013">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2014">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2014">Pattern</span></span>

<span data-ttu-id="a7f02-2015">8-9 个字母组合：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2015">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="a7f02-2016">1-2 个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="a7f02-2016">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="a7f02-2017">六个数字 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2017">Six digits</span></span> 
- <span data-ttu-id="a7f02-2018">最后一个字符（任意数字或字母 A）是校验位，两边可以选择加括号。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2018">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2019">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2019">Checksum</span></span>

<span data-ttu-id="a7f02-2020">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-2020">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2021">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2021">Definition</span></span>

<span data-ttu-id="a7f02-2022">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2022">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2023">函数 Func_hong_kong_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2023">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2024">找到 Keyword_hong_kong_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2024">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="a7f02-2025">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2025">The checksum passes.</span></span>

<span data-ttu-id="a7f02-2026">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2026">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2027">函数 Func_hong_kong_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2027">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2028">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2028">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-2029">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2029">Keywords</span></span>

#### <a name="keywordhongkongidcard"></a><span data-ttu-id="a7f02-2030">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="a7f02-2030">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="a7f02-2031">Hong Kong Identity Card</span><span class="sxs-lookup"><span data-stu-id="a7f02-2031">Hong Kong Identity Card</span></span>
- <span data-ttu-id="a7f02-2032">HKID</span><span class="sxs-lookup"><span data-stu-id="a7f02-2032">HKID</span></span>
- <span data-ttu-id="a7f02-2033">ID card</span><span class="sxs-lookup"><span data-stu-id="a7f02-2033">ID card</span></span>
- <span data-ttu-id="a7f02-2034">香港身份證
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2034">香港身份證</span></span> 
- <span data-ttu-id="a7f02-2035">香港永久性居民身份證
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2035">香港永久性居民身份證</span></span> 
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="a7f02-2036">印度永久帐号 (PAN)</span><span class="sxs-lookup"><span data-stu-id="a7f02-2036">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2037">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2037">Format</span></span>

<span data-ttu-id="a7f02-2038">10 个字母或数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2038">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2039">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2039">Pattern</span></span>

<span data-ttu-id="a7f02-2040">10 个字母或数字：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2040">10 letters or digits:</span></span>
- <span data-ttu-id="a7f02-2041">五个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="a7f02-2041">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="a7f02-2042">四个数字 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2042">Four digits</span></span> 
- <span data-ttu-id="a7f02-2043">一个字母，是字母校验位</span><span class="sxs-lookup"><span data-stu-id="a7f02-2043">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2044">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2044">Checksum</span></span>

<span data-ttu-id="a7f02-2045">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-2045">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2046">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2046">Definition</span></span>

<span data-ttu-id="a7f02-2047">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2047">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2048">正则表达式 Regex_india_permanent_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2048">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2049">找到 Keyword_india_permanent_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2049">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="a7f02-2050">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2050">The checksum passes.</span></span>

```
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7f02-2051">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2051">Keywords</span></span>

#### <a name="keywordindiapermanentaccountnumber"></a><span data-ttu-id="a7f02-2052">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="a7f02-2052">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="a7f02-2053">Permanent Account Number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2053">Permanent Account Number</span></span> 
- <span data-ttu-id="a7f02-2054">PAN
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2054">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="a7f02-2055">India Unique Identification (Aadhaar) Number</span><span class="sxs-lookup"><span data-stu-id="a7f02-2055">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2056">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2056">Format</span></span>

<span data-ttu-id="a7f02-2057">12 个数字（包含可选空格或短划线）</span><span class="sxs-lookup"><span data-stu-id="a7f02-2057">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2058">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2058">Pattern</span></span>

<span data-ttu-id="a7f02-2059">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2059">12 digits:</span></span>
- <span data-ttu-id="a7f02-2060">四个数字 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2060">Four digits</span></span> 
- <span data-ttu-id="a7f02-2061">一个可选空格或短划线 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2061">An optional space or dash</span></span> 
- <span data-ttu-id="a7f02-2062">四个数字 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2062">Four digits</span></span> 
- <span data-ttu-id="a7f02-2063">一个可选空格或短划线 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2063">An optional space or dash</span></span> 
- <span data-ttu-id="a7f02-2064">最后一个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="a7f02-2064">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2065">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2065">Checksum</span></span>

<span data-ttu-id="a7f02-2066">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-2066">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2067">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2067">Definition</span></span>

<span data-ttu-id="a7f02-p133">DLP 策略是 85%相信它已检测到此类型的敏感信息 if、 内 300 个字符的邻近度： 函数 Func_india_aadhaar 查找与模式匹配的内容。找到从 Keyword_india_aadhar 关键字。将传递校验和。DLP 策略是相信它已检测到此类型的敏感信息的 75 %if、 内 300 个字符的邻近度： 函数 Func_india_aadhaar 查找与模式匹配的内容。将传递校验和。<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="a7f02-p133">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern. A keyword from Keyword_india_aadhar is found. The checksum passes. A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern. The checksum passes. <!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span></span>

### <a name="keywords"></a><span data-ttu-id="a7f02-2074">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2074">Keywords</span></span>
   
#### <a name="keywordindiaaadhar"></a><span data-ttu-id="a7f02-2075">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="a7f02-2075">Keyword_india_aadhar</span></span>
- <span data-ttu-id="a7f02-2076">Aadhar</span><span class="sxs-lookup"><span data-stu-id="a7f02-2076">Aadhar</span></span>
- <span data-ttu-id="a7f02-2077">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="a7f02-2077">Aadhaar</span></span>
- <span data-ttu-id="a7f02-2078">UID</span><span class="sxs-lookup"><span data-stu-id="a7f02-2078">UID</span></span>
- <span data-ttu-id="a7f02-2079">आधार</span><span class="sxs-lookup"><span data-stu-id="a7f02-2079">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="a7f02-2080">印度尼西亚身份证 (KTP) 号</span><span class="sxs-lookup"><span data-stu-id="a7f02-2080">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2081">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2081">Format</span></span>

<span data-ttu-id="a7f02-2082">16 个数字（包含可选点）</span><span class="sxs-lookup"><span data-stu-id="a7f02-2082">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2083">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2083">Pattern</span></span>

<span data-ttu-id="a7f02-2084">16 个数字：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2084">16 digits:</span></span>
- <span data-ttu-id="a7f02-2085">两位省代码 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2085">Two-digit province code</span></span> 
- <span data-ttu-id="a7f02-2086">一个点（可选） </span><span class="sxs-lookup"><span data-stu-id="a7f02-2086">A period (optional)</span></span> 
- <span data-ttu-id="a7f02-2087">两位摄政统治区或城市代码 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2087">Two-digit regency or city code</span></span> 
- <span data-ttu-id="a7f02-2088">两位住宅小区代码 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2088">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="a7f02-2089">一个点（可选） </span><span class="sxs-lookup"><span data-stu-id="a7f02-2089">A period (optional)</span></span> 
- <span data-ttu-id="a7f02-2090">六个数字，采用  DDMMYY 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2090">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="a7f02-2091">一个点（可选） </span><span class="sxs-lookup"><span data-stu-id="a7f02-2091">A period (optional)</span></span> 
- <span data-ttu-id="a7f02-2092">四个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2092">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2093">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2093">Checksum</span></span>

<span data-ttu-id="a7f02-2094">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-2094">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2095">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2095">Definition</span></span>

<span data-ttu-id="a7f02-2096">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2096">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2097">正则表达式 Regex_indonesia_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2097">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2098">找到 Keyword_indonesia_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2098">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="a7f02-2099">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2099">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2100">正则表达式 Regex_indonesia_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2100">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-2101">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2101">Keywords</span></span>
   
#### <a name="keywordindonesiaidcard"></a><span data-ttu-id="a7f02-2102">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="a7f02-2102">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="a7f02-2103">KTP</span><span class="sxs-lookup"><span data-stu-id="a7f02-2103">KTP</span></span>
- <span data-ttu-id="a7f02-2104">Kartu Tanda Penduduk
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2104">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="a7f02-2105">Nomor Induk Kependudukan
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2105">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="a7f02-2106">国际银行帐号 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="a7f02-2106">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2107">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2107">Format</span></span>

<span data-ttu-id="a7f02-2108">国家/地区代码（两个字母）加校验位（两个数字）以及 bban 号码（最多 30 个字符）</span><span class="sxs-lookup"><span data-stu-id="a7f02-2108">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2109">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2109">Pattern</span></span>

<span data-ttu-id="a7f02-2110">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2110">Pattern must include all of the following:</span></span>

- <span data-ttu-id="a7f02-2111">两个字母的国家/地区代码</span><span class="sxs-lookup"><span data-stu-id="a7f02-2111">Two-letter country code</span></span>
- <span data-ttu-id="a7f02-2112">两个校验位（后跟一个可选空间） </span><span class="sxs-lookup"><span data-stu-id="a7f02-2112">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="a7f02-2113">1-7 个包含 4 个字母或数字的组（可以使用空格进行分隔）</span><span class="sxs-lookup"><span data-stu-id="a7f02-2113">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="a7f02-2114">1-3 个字母或数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2114">1-3 letters or digits</span></span>

<span data-ttu-id="a7f02-p134">每个国家/地区的格式稍有不同。IBAN 敏感信息类型涵盖这 60 个国家/地区：</span><span class="sxs-lookup"><span data-stu-id="a7f02-p134">The format for each country is slightly different. The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="a7f02-2117">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span><span class="sxs-lookup"><span data-stu-id="a7f02-2117">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2118">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2118">Checksum</span></span>

<span data-ttu-id="a7f02-2119">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-2119">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2120">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2120">Definition</span></span>

<span data-ttu-id="a7f02-2121">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2121">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2122">函数 Func_iban 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2122">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2123">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2123">The checksum passes.</span></span>

```
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7f02-2124">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2124">Keywords</span></span>

<span data-ttu-id="a7f02-2125">无</span><span class="sxs-lookup"><span data-stu-id="a7f02-2125">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="a7f02-2126">IP 地址</span><span class="sxs-lookup"><span data-stu-id="a7f02-2126">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2127">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2127">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="a7f02-2128">IPv4：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2128">IPv4:</span></span>
<span data-ttu-id="a7f02-2129">解释 IPv4 地址格式化（点）版本或非格式化（没有点）版本的复杂模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2129">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="a7f02-2130">IPv6：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2130">IPv6:</span></span>
<span data-ttu-id="a7f02-2131"> 解释格式化 IPv6 号码（包含冒号）的复杂模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2131">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2132">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2132">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2133">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2133">Checksum</span></span>

<span data-ttu-id="a7f02-2134">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-2134">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2135">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2135">Definition</span></span>

<span data-ttu-id="a7f02-2136">对于 IPv6，在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2136">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2137">正则表达式 Regex_ipv6_address 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2137">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2138">未找到 Keyword_ipaddress 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2138">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="a7f02-2139">对于 IPv4，在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2139">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2140">正则表达式 Regex_ipv4_address 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2140">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2141">找到 Keyword_ipaddress 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2141">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="a7f02-2142">对于 IPv6，在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2142">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2143">正则表达式 Regex_ipv6_address 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2143">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2144">未找到 Keyword_ipaddress 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2144">No keyword from Keyword_ipaddress is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-2145">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2145">Keywords</span></span>

#### <a name="keywordipaddress"></a><span data-ttu-id="a7f02-2146">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="a7f02-2146">Keyword_ipaddress</span></span>

- <span data-ttu-id="a7f02-2147">IP（此关键字区分大小写）</span><span class="sxs-lookup"><span data-stu-id="a7f02-2147">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="a7f02-2148">ip address
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2148">ip address</span></span> 
- <span data-ttu-id="a7f02-2149">ip addresses</span><span class="sxs-lookup"><span data-stu-id="a7f02-2149">ip addresses</span></span>
- <span data-ttu-id="a7f02-2150">internet protocol</span><span class="sxs-lookup"><span data-stu-id="a7f02-2150">internet protocol</span></span>
- <span data-ttu-id="a7f02-2151">
IP-כתובת ה
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2151">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="a7f02-2152">国际分类的科 （ICD-10-厘米）</span><span class="sxs-lookup"><span data-stu-id="a7f02-2152">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2153">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2153">Format</span></span>

<span data-ttu-id="a7f02-2154">词典</span><span class="sxs-lookup"><span data-stu-id="a7f02-2154">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2155">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2155">Pattern</span></span>

<span data-ttu-id="a7f02-2156">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2156">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2157">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2157">Checksum</span></span>

<span data-ttu-id="a7f02-2158">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-2158">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2159">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2159">Definition</span></span>

<span data-ttu-id="a7f02-2160">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2160">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2161">找到从 Dictionary_icd_10_cm 关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2161">A keyword from Dictionary_icd_10_cm is found.</span></span>

```
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

<span data-ttu-id="a7f02-2162">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2162">Keywords</span></span>

<span data-ttu-id="a7f02-p135">Dictionary_icd_10_cm 关键字字典中的任何术语的基于[国际分类的科、 第十修订，临床修改 （ICD-10-厘米）](https://go.microsoft.com/fwlink/?linkid=852604)。此类型仅查找术语，不保险代码。</span><span class="sxs-lookup"><span data-stu-id="a7f02-p135">Any term from the Dictionary_icd_10_cm keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604). This type looks only for the term, not the insurance codes.</span></span>

   
## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="a7f02-2165">国际分类的科 （ICD-9-厘米）</span><span class="sxs-lookup"><span data-stu-id="a7f02-2165">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2166">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2166">Format</span></span>

<span data-ttu-id="a7f02-2167">词典</span><span class="sxs-lookup"><span data-stu-id="a7f02-2167">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2168">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2168">Pattern</span></span>

<span data-ttu-id="a7f02-2169">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2169">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2170">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2170">Checksum</span></span>

<span data-ttu-id="a7f02-2171">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-2171">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2172">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2172">Definition</span></span>

<span data-ttu-id="a7f02-2173">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2173">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2174">找到从 Dictionary_icd_9_cm 关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2174">A keyword from Dictionary_icd_9_cm is found.</span></span>

```
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7f02-2175">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2175">Keywords</span></span>

<span data-ttu-id="a7f02-p136">Dictionary_icd_9_cm 关键字字典中的任何术语的基于[国际分类的科、 第九个修订，临床修改 （ICD-9-厘米）](https://go.microsoft.com/fwlink/?linkid=852605)。此类型仅查找术语，不保险代码。</span><span class="sxs-lookup"><span data-stu-id="a7f02-p136">Any term from the Dictionary_icd_9_cm keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605). This type looks only for the term, not the insurance codes.</span></span>
   
## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="a7f02-2178">爱尔兰个人公共服务 (PPS) 号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-2178">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2179">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2179">Format</span></span>

<span data-ttu-id="a7f02-2180">（到 Dec 2012 年 31） 的旧格式：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2180">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="a7f02-2181">七位数字后跟 1-2  个字母 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2181">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="a7f02-2182">新的格式 (2013 年 1 月 1 和之后):</span><span class="sxs-lookup"><span data-stu-id="a7f02-2182">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="a7f02-2183">七位数字后跟两个字母</span><span class="sxs-lookup"><span data-stu-id="a7f02-2183">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2184">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2184">Pattern</span></span>

<span data-ttu-id="a7f02-2185">（到 Dec 2012 年 31） 的旧格式：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2185">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="a7f02-2186">七个数字 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2186">Seven digits</span></span> 
- <span data-ttu-id="a7f02-2187">1-2 个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="a7f02-2187">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="a7f02-2188">新的格式 (2013 年 1 月 1 和之后):</span><span class="sxs-lookup"><span data-stu-id="a7f02-2188">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="a7f02-2189">七个数字 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2189">Seven digits</span></span> 
- <span data-ttu-id="a7f02-2190">一个字母（不区分大小写），是字母校验位 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2190">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="a7f02-2191">字母“A”或“H”（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="a7f02-2191">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2192">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2192">Checksum</span></span>

<span data-ttu-id="a7f02-2193">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-2193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2194">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2194">Definition</span></span>

<span data-ttu-id="a7f02-2195">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2196">函数 Func_ireland_pps 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2196">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2197">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2197">One of the following is true:</span></span>
    - <span data-ttu-id="a7f02-2198">找到 Keyword_ireland_pps 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2198">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="a7f02-2199">函数 Func_eu_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2199">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="a7f02-2200">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2200">The checksum passes.</span></span>

<span data-ttu-id="a7f02-2201">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2201">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2202">函数 Func_ireland_pps 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2202">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2203">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2203">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-2204">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2204">Keywords</span></span>

#### <a name="keywordirelandpps"></a><span data-ttu-id="a7f02-2205">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="a7f02-2205">Keyword_ireland_pps</span></span>

- <span data-ttu-id="a7f02-2206">Personal Public Service Number 
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2206">Personal Public Service Number</span></span> 
- <span data-ttu-id="a7f02-2207">PPS Number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2207">PPS Number</span></span> 
- <span data-ttu-id="a7f02-2208">PPS Num
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2208">PPS Num</span></span> 
- <span data-ttu-id="a7f02-2209">PPS No.
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2209">PPS No.</span></span> 
- <span data-ttu-id="a7f02-2210">PPS #
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2210">PPS #</span></span> 
- <span data-ttu-id="a7f02-2211">PPS #</span><span class="sxs-lookup"><span data-stu-id="a7f02-2211">PPS#</span></span> 
- <span data-ttu-id="a7f02-2212">PPSN
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2212">PPSN</span></span> 
- <span data-ttu-id="a7f02-2213">Public Services Card
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2213">Public Services Card</span></span> 
- <span data-ttu-id="a7f02-2214">Uimhir Phearsanta Seirbhíse Poiblí
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2214">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="a7f02-p137">Uimh.PSP
</span><span class="sxs-lookup"><span data-stu-id="a7f02-p137">Uimh. PSP</span></span> 
- <span data-ttu-id="a7f02-2217">PSP
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2217">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="a7f02-2218">以色列银行帐号</span><span class="sxs-lookup"><span data-stu-id="a7f02-2218">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2219">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2219">Format</span></span>

<span data-ttu-id="a7f02-2220">13 位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2220">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2221">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2221">Pattern</span></span>

<span data-ttu-id="a7f02-2222">有格式模式：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2222">Formatted:</span></span>
- <span data-ttu-id="a7f02-2223">两位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2223">Two digits</span></span> 
- <span data-ttu-id="a7f02-2224">破折号</span><span class="sxs-lookup"><span data-stu-id="a7f02-2224">A dash</span></span> 
- <span data-ttu-id="a7f02-2225">三位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2225">Three digits</span></span> 
- <span data-ttu-id="a7f02-2226">破折号</span><span class="sxs-lookup"><span data-stu-id="a7f02-2226">A dash</span></span> 
- <span data-ttu-id="a7f02-2227">八个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2227">Eight digits</span></span>

<span data-ttu-id="a7f02-2228">无格式模式：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2228">Unformatted:</span></span>
- <span data-ttu-id="a7f02-2229">	13 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2229">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2230">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2230">Checksum</span></span>

<span data-ttu-id="a7f02-2231">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-2231">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2232">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2232">Definition</span></span>

<span data-ttu-id="a7f02-2233">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2234">正则表达式 Regex_israel_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2234">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2235">找到 Keyword_israel_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2235">A keyword from Keyword_israel_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-2236">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2236">Keywords</span></span>

#### <a name="keywordisraelbankaccountnumber"></a><span data-ttu-id="a7f02-2237">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="a7f02-2237">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="a7f02-2238">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2238">Bank Account Number</span></span> 
- <span data-ttu-id="a7f02-2239">Bank Account
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2239">Bank Account</span></span> 
- <span data-ttu-id="a7f02-2240">Account Number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2240">Account Number</span></span> 
- <span data-ttu-id="a7f02-2241">מספר חשבון בנק
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2241">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="a7f02-2242">以色列国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="a7f02-2242">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2243">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2243">Format</span></span>

<span data-ttu-id="a7f02-2244">九个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2244">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2245">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2245">Pattern</span></span>

<span data-ttu-id="a7f02-2246">九个连续的数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2246">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2247">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2247">Checksum</span></span>

<span data-ttu-id="a7f02-2248">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-2248">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2249">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2249">Definition</span></span>

<span data-ttu-id="a7f02-2250">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2251">函数 Func_israeli_national_id_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2251">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2252">找到 Keyword_Israel_National_ID 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2252">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="a7f02-2253">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2253">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-2254">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2254">Keywords</span></span>

#### <a name="keywordisraelnationalid"></a><span data-ttu-id="a7f02-2255">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="a7f02-2255">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="a7f02-2256">מספר זהות
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2256">מספר זהות</span></span> 
- <span data-ttu-id="a7f02-2257">National ID Number</span><span class="sxs-lookup"><span data-stu-id="a7f02-2257">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="a7f02-2258">意大利驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-2258">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2259">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2259">Format</span></span>

<span data-ttu-id="a7f02-2260">10 个字母和数字的组合</span><span class="sxs-lookup"><span data-stu-id="a7f02-2260">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2261">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2261">Pattern</span></span>

- <span data-ttu-id="a7f02-2262">10 个字母和数字的组合：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2262">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="a7f02-2263">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="a7f02-2263">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="a7f02-2264">字母“A”或者“V”（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="a7f02-2264">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="a7f02-2265">七个字母（不区分大小写）、数字或下划线字符</span><span class="sxs-lookup"><span data-stu-id="a7f02-2265">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="a7f02-2266">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="a7f02-2266">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2267">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2267">Checksum</span></span>

<span data-ttu-id="a7f02-2268">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-2268">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2269">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2269">Definition</span></span>

<span data-ttu-id="a7f02-2270">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2270">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2271">正则表达式 Regex_italy_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2271">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2272">找到 Keyword_italy_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2272">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-2273">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2273">Keywords</span></span>

#### <a name="keyworditalydriverslicensenumber"></a><span data-ttu-id="a7f02-2274">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="a7f02-2274">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="a7f02-2275">numero di patente di guida
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2275">numero di patente di guida</span></span> 
- <span data-ttu-id="a7f02-2276">patente di guida
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2276">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="a7f02-2277">日本银行帐号</span><span class="sxs-lookup"><span data-stu-id="a7f02-2277">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2278">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2278">Format</span></span>

<span data-ttu-id="a7f02-2279">七个或八个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2279">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2280">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2280">Pattern</span></span>

<span data-ttu-id="a7f02-2281">银行帐号：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2281">Bank account number:</span></span>
- <span data-ttu-id="a7f02-2282">七个或八个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2282">Seven or eight digits</span></span>
- <span data-ttu-id="a7f02-2283">银行帐户分支代码：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2283">Bank account branch code:</span></span>
- <span data-ttu-id="a7f02-2284">四位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2284">Four digits</span></span> 
- <span data-ttu-id="a7f02-2285">空格或破折号（可选）</span><span class="sxs-lookup"><span data-stu-id="a7f02-2285">A space or dash (optional)</span></span> 
- <span data-ttu-id="a7f02-2286">三位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2286">Three digits</span></span>

<span data-ttu-id="a7f02-2287">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2287">Checksum</span></span>

<span data-ttu-id="a7f02-2288">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-2288">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2289">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2289">Definition</span></span>

<span data-ttu-id="a7f02-2290">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2290">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2291">函数 Func_jp_bank_account 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2291">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2292">找到 Keyword_jp_bank_account 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2292">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="a7f02-2293">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2293">One of the following is true:</span></span>
- <span data-ttu-id="a7f02-2294">函数 Func_jp_bank_account_branch_code 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2294">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2295">找到 Keyword_jp_bank_branch_code 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2295">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="a7f02-2296">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2296">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2297">函数 Func_jp_bank_account 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2297">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2298">找到 Keyword_jp_bank_account 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2298">A keyword from Keyword_jp_bank_account is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-2299">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2299">Keywords</span></span>

#### <a name="keywordjpbankaccount"></a><span data-ttu-id="a7f02-2300">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="a7f02-2300">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="a7f02-2301">Checking Account Number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2301">Checking Account Number</span></span> 
- <span data-ttu-id="a7f02-2302">Checking Account
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2302">Checking Account</span></span> 
- <span data-ttu-id="a7f02-2303">Checking Account #
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2303">Checking Account #</span></span> 
- <span data-ttu-id="a7f02-2304">Checking Acct Number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2304">Checking Acct Number</span></span> 
- <span data-ttu-id="a7f02-2305">Checking Acct #
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2305">Checking Acct #</span></span> 
- <span data-ttu-id="a7f02-2306">Checking Acct No.
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2306">Checking Acct No.</span></span> 
- <span data-ttu-id="a7f02-2307">Checking Account No.
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2307">Checking Account No.</span></span> 
- <span data-ttu-id="a7f02-2308">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2308">Bank Account Number</span></span> 
- <span data-ttu-id="a7f02-2309">Bank Account
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2309">Bank Account</span></span> 
- <span data-ttu-id="a7f02-2310">Bank Account #
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2310">Bank Account #</span></span> 
- <span data-ttu-id="a7f02-2311">Bank Acct Number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2311">Bank Acct Number</span></span> 
- <span data-ttu-id="a7f02-2312">Bank Acct #
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2312">Bank Acct #</span></span> 
- <span data-ttu-id="a7f02-2313">Bank Acct No.
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2313">Bank Acct No.</span></span> 
- <span data-ttu-id="a7f02-2314">Bank Account No.
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2314">Bank Account No.</span></span> 
- <span data-ttu-id="a7f02-2315">Savings Account Number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2315">Savings Account Number</span></span> 
- <span data-ttu-id="a7f02-2316">节省帐户</span><span class="sxs-lookup"><span data-stu-id="a7f02-2316">Savings Account</span></span> 
- <span data-ttu-id="a7f02-2317">Savings Account #
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2317">Savings Account #</span></span> 
- <span data-ttu-id="a7f02-2318">Savings Acct Number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2318">Savings Acct Number</span></span> 
- <span data-ttu-id="a7f02-2319">Savings Acct #
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2319">Savings Acct #</span></span> 
- <span data-ttu-id="a7f02-2320">Savings Acct No.
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2320">Savings Acct No.</span></span> 
- <span data-ttu-id="a7f02-2321">Savings Account No.
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2321">Savings Account No.</span></span> 
- <span data-ttu-id="a7f02-2322">Debit Account Number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2322">Debit Account Number</span></span> 
- <span data-ttu-id="a7f02-2323">Debit Account
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2323">Debit Account</span></span> 
- <span data-ttu-id="a7f02-2324">Debit Account #
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2324">Debit Account #</span></span> 
- <span data-ttu-id="a7f02-2325">Debit Acct Number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2325">Debit Acct Number</span></span> 
- <span data-ttu-id="a7f02-2326">Debit Acct #
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2326">Debit Acct #</span></span> 
- <span data-ttu-id="a7f02-2327">Debit Acct No.
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2327">Debit Acct No.</span></span> 
- <span data-ttu-id="a7f02-2328">Debit Account No.
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2328">Debit Account No.</span></span> 
- <span data-ttu-id="a7f02-2329">口座番号を当座預金口座の確認
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2329">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="a7f02-2330">＃アカウントの確認、勘定番号の確認
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2330">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="a7f02-2331">＃勘定の確認
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2331">＃勘定の確認</span></span> 
- <span data-ttu-id="a7f02-2332">勘定番号の確認
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2332">勘定番号の確認</span></span> 
- <span data-ttu-id="a7f02-2333">口座番号の確認
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2333">口座番号の確認</span></span> 
- <span data-ttu-id="a7f02-2334">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="a7f02-2334">銀行口座番号</span></span> 
- <span data-ttu-id="a7f02-2335">銀行口座</span><span class="sxs-lookup"><span data-stu-id="a7f02-2335">銀行口座</span></span> 
- <span data-ttu-id="a7f02-2336">銀行口座＃
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2336">銀行口座＃</span></span> 
- <span data-ttu-id="a7f02-2337">銀行の勘定番号
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2337">銀行の勘定番号</span></span> 
- <span data-ttu-id="a7f02-2338">銀行のacct＃
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2338">銀行のacct＃</span></span> 
- <span data-ttu-id="a7f02-2339">銀行の勘定いいえ
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2339">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="a7f02-2340">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="a7f02-2340">銀行口座番号</span></span>
- <span data-ttu-id="a7f02-2341">
普通預金口座番号
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2341">普通預金口座番号</span></span> 
- <span data-ttu-id="a7f02-2342">預金口座
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2342">預金口座</span></span> 
- <span data-ttu-id="a7f02-2343">貯蓄口座＃
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2343">貯蓄口座＃</span></span> 
- <span data-ttu-id="a7f02-2344">貯蓄勘定の数
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2344">貯蓄勘定の数</span></span> 
- <span data-ttu-id="a7f02-2345">貯蓄勘定＃
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2345">貯蓄勘定＃</span></span> 
- <span data-ttu-id="a7f02-2346">貯蓄勘定番号
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2346">貯蓄勘定番号</span></span> 
- <span data-ttu-id="a7f02-2347">普通預金口座番号
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2347">普通預金口座番号</span></span> 
- <span data-ttu-id="a7f02-2348">引き落とし口座番号
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2348">引き落とし口座番号</span></span> 
- <span data-ttu-id="a7f02-2349">口座番号</span><span class="sxs-lookup"><span data-stu-id="a7f02-2349">口座番号</span></span> 
- <span data-ttu-id="a7f02-2350">口座番号＃
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2350">口座番号＃</span></span> 
- <span data-ttu-id="a7f02-2351">デビットのacct番号
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2351">デビットのacct番号</span></span> 
- <span data-ttu-id="a7f02-2352">デビット勘定＃
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2352">デビット勘定＃</span></span> 
- <span data-ttu-id="a7f02-2353">デビットACCTの番号
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2353">デビットACCTの番号</span></span> 
- <span data-ttu-id="a7f02-2354">デビット口座番号
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2354">デビット口座番号</span></span> 

#### <a name="keywordjpbankbranchcode"></a><span data-ttu-id="a7f02-2355">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="a7f02-2355">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="a7f02-2356">Otemachi</span><span class="sxs-lookup"><span data-stu-id="a7f02-2356">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="a7f02-2357">日本驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-2357">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2358">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2358">Format</span></span>

<span data-ttu-id="a7f02-2359">12 个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2359">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2360">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2360">Pattern</span></span>

<span data-ttu-id="a7f02-2361">12 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2361">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2362">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2362">Checksum</span></span>

<span data-ttu-id="a7f02-2363">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-2363">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2364">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2364">Definition</span></span>

<span data-ttu-id="a7f02-2365">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2365">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2366">函数 Func_jp_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2366">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2367">找到 Keyword_jp_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2367">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7f02-2368">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2368">Keywords</span></span>

#### <a name="keywordjpdriverslicensenumber"></a><span data-ttu-id="a7f02-2369">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="a7f02-2369">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="a7f02-2370">dl#</span><span class="sxs-lookup"><span data-stu-id="a7f02-2370">dl#</span></span> 
- <span data-ttu-id="a7f02-2371">DL #</span><span class="sxs-lookup"><span data-stu-id="a7f02-2371">DL＃</span></span> 
- <span data-ttu-id="a7f02-2372">dls#</span><span class="sxs-lookup"><span data-stu-id="a7f02-2372">dls#</span></span> 
- <span data-ttu-id="a7f02-2373">DL #</span><span class="sxs-lookup"><span data-stu-id="a7f02-2373">DLS＃</span></span> 
- <span data-ttu-id="a7f02-2374">driver license</span><span class="sxs-lookup"><span data-stu-id="a7f02-2374">driver license</span></span> 
- <span data-ttu-id="a7f02-2375">driver licenses</span><span class="sxs-lookup"><span data-stu-id="a7f02-2375">driver licenses</span></span> 
- <span data-ttu-id="a7f02-2376">drivers license</span><span class="sxs-lookup"><span data-stu-id="a7f02-2376">drivers license</span></span> 
- <span data-ttu-id="a7f02-2377">driver's license</span><span class="sxs-lookup"><span data-stu-id="a7f02-2377">driver's license</span></span> 
- <span data-ttu-id="a7f02-2378">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="a7f02-2378">drivers licenses</span></span> 
- <span data-ttu-id="a7f02-2379">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="a7f02-2379">driver's licenses</span></span> 
- <span data-ttu-id="a7f02-2380">driving licence
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2380">driving licence</span></span> 
- <span data-ttu-id="a7f02-2381">lic#</span><span class="sxs-lookup"><span data-stu-id="a7f02-2381">lic#</span></span> 
- <span data-ttu-id="a7f02-2382">LIC #</span><span class="sxs-lookup"><span data-stu-id="a7f02-2382">LIC＃</span></span> 
- <span data-ttu-id="a7f02-2383">lics#</span><span class="sxs-lookup"><span data-stu-id="a7f02-2383">lics#</span></span> 
- <span data-ttu-id="a7f02-2384">状态 id</span><span class="sxs-lookup"><span data-stu-id="a7f02-2384">state id</span></span> 
- <span data-ttu-id="a7f02-2385">state identification
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2385">state identification</span></span> 
- <span data-ttu-id="a7f02-2386">state identification number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2386">state identification number</span></span> 
- <span data-ttu-id="a7f02-2387">低所得国＃
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2387">低所得国＃</span></span> 
- <span data-ttu-id="a7f02-2388">免許証</span><span class="sxs-lookup"><span data-stu-id="a7f02-2388">免許証</span></span> 
- <span data-ttu-id="a7f02-2389">状態ID</span><span class="sxs-lookup"><span data-stu-id="a7f02-2389">状態ID</span></span>
- <span data-ttu-id="a7f02-2390">
状態の識別
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2390">状態の識別</span></span> 
- <span data-ttu-id="a7f02-2391">状態の識別番号
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2391">状態の識別番号</span></span> 
- <span data-ttu-id="a7f02-2392">運転免許</span><span class="sxs-lookup"><span data-stu-id="a7f02-2392">運転免許</span></span> 
- <span data-ttu-id="a7f02-2393">運転免許証</span><span class="sxs-lookup"><span data-stu-id="a7f02-2393">運転免許証</span></span> 
- <span data-ttu-id="a7f02-2394">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="a7f02-2394">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="a7f02-2395">日本护照号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-2395">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2396">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2396">Format</span></span>

<span data-ttu-id="a7f02-2397">两个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2397">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2398">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2398">Pattern</span></span>

<span data-ttu-id="a7f02-2399">两个字母（不区分大小写）后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2399">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2400">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2400">Checksum</span></span>

<span data-ttu-id="a7f02-2401">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-2401">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2402">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2402">Definition</span></span>

<span data-ttu-id="a7f02-2403">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2403">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2404">函数 Func_jp_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2404">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2405">找到 Keyword_jp_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2405">A keyword from Keyword_jp_passport is found.</span></span>

```
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7f02-2406">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2406">Keywords</span></span>

#### <a name="keywordjppassport"></a><span data-ttu-id="a7f02-2407">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="a7f02-2407">Keyword_jp_passport</span></span>

- <span data-ttu-id="a7f02-2408">パスポート
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2408">パスポート</span></span> 
- <span data-ttu-id="a7f02-2409">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2409">パスポート番号</span></span> 
- <span data-ttu-id="a7f02-2410">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2410">パスポートのNum</span></span> 
- <span data-ttu-id="a7f02-2411">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2411">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="a7f02-2412">日本居民登记号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-2412">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2413">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2413">Format</span></span>

<span data-ttu-id="a7f02-2414">11 个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2414">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2415">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2415">Pattern</span></span>

<span data-ttu-id="a7f02-2416">11 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2416">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2417">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2417">Checksum</span></span>

<span data-ttu-id="a7f02-2418">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-2418">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2419">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2419">Definition</span></span>

<span data-ttu-id="a7f02-2420">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2420">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2421">函数 Func_jp_resident_registration_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2421">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2422">找到 Keyword_jp_resident_registration_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2422">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7f02-2423">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2423">Keywords</span></span>

#### <a name="keywordjpresidentregistrationnumber"></a><span data-ttu-id="a7f02-2424">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="a7f02-2424">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="a7f02-2425">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="a7f02-2425">Resident Registration Number</span></span>
- <span data-ttu-id="a7f02-2426">Resident Register Number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2426">Resident Register Number</span></span> 
- <span data-ttu-id="a7f02-2427">Residents Basic Registry Number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2427">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="a7f02-2428">Resident Registration No.
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2428">Resident Registration No.</span></span> 
- <span data-ttu-id="a7f02-2429">Resident Register No.
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2429">Resident Register No.</span></span> 
- <span data-ttu-id="a7f02-2430">Residents Basic Registry No.
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2430">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="a7f02-2431">Basic Resident Register No.
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2431">Basic Resident Register No.</span></span> 
- <span data-ttu-id="a7f02-2432">住民登録番号、登録番号をレジデント
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2432">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="a7f02-2433">住民基本登録番号、登録番号
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2433">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="a7f02-2434">住民基本レジストリ番号を常駐
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2434">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="a7f02-2435">登録番号を常駐住民基本台帳登録番号
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2435">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="a7f02-2436">日本社会保险号码 (SIN)</span><span class="sxs-lookup"><span data-stu-id="a7f02-2436">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2437">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2437">Format</span></span>

<span data-ttu-id="a7f02-2438">7-12 个数字 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2438">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2439">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2439">Pattern</span></span>

<span data-ttu-id="a7f02-2440">7-12 位数字：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2440">7-12 digits:</span></span>
- <span data-ttu-id="a7f02-2441">四位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2441">Four digits</span></span> 
- <span data-ttu-id="a7f02-2442">一个连字符（可选）</span><span class="sxs-lookup"><span data-stu-id="a7f02-2442">A hyphen (optional)</span></span> 
- <span data-ttu-id="a7f02-2443">6 个数字或</span><span class="sxs-lookup"><span data-stu-id="a7f02-2443">Six digits OR</span></span>
- <span data-ttu-id="a7f02-2444">7-12 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2444">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2445">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2445">Checksum</span></span>

<span data-ttu-id="a7f02-2446">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-2446">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2447">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2447">Definition</span></span>

<span data-ttu-id="a7f02-2448">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2448">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2449">函数 Func_jp_sin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2449">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2450">找到 Keyword_jp_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2450">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="a7f02-2451">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2451">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2452">函数 Func_jp_sin_pre_1997 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2452">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2453">找到 Keyword_jp_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2453">A keyword from Keyword_jp_sin is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-2454">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2454">Keywords</span></span>

#### <a name="keywordjpsin"></a><span data-ttu-id="a7f02-2455">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="a7f02-2455">Keyword_jp_sin</span></span>

- <span data-ttu-id="a7f02-2456">Social Insurance No.
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2456">Social Insurance No.</span></span> 
- <span data-ttu-id="a7f02-2457">Social Insurance Num
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2457">Social Insurance Num</span></span> 
- <span data-ttu-id="a7f02-2458">Social Insurance Number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2458">Social Insurance Number</span></span> 
- <span data-ttu-id="a7f02-2459">社会保険のテンキー
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2459">社会保険のテンキー</span></span> 
- <span data-ttu-id="a7f02-2460">社会保険番号
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2460">社会保険番号</span></span> 
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="a7f02-2461">马拉西亚身份证号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-2461">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2462">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2462">Format</span></span>

<span data-ttu-id="a7f02-2463">12 个数字（包含可选连字符）</span><span class="sxs-lookup"><span data-stu-id="a7f02-2463">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2464">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2464">Pattern</span></span>

<span data-ttu-id="a7f02-2465">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2465">12 digits:</span></span>
- <span data-ttu-id="a7f02-2466">六个数字，采用  YYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2466">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="a7f02-2467">一个短划线（可选） </span><span class="sxs-lookup"><span data-stu-id="a7f02-2467">A dash (optional)</span></span> 
- <span data-ttu-id="a7f02-2468">两个字母的出生地代码 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2468">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="a7f02-2469">一个短划线（可选） </span><span class="sxs-lookup"><span data-stu-id="a7f02-2469">A dash (optional)</span></span> 
- <span data-ttu-id="a7f02-2470">三个随机数字 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2470">Three random digits</span></span> 
- <span data-ttu-id="a7f02-2471">一位性别代码</span><span class="sxs-lookup"><span data-stu-id="a7f02-2471">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2472">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2472">Checksum</span></span>

<span data-ttu-id="a7f02-2473">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-2473">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2474">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2474">Definition</span></span>

<span data-ttu-id="a7f02-2475">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2475">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2476">正则表达式 Regex_malaysia_id_card_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2476">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2477">找到 Keyword_malaysia_id_card_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2477">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-2478">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2478">Keywords</span></span>
   
#### <a name="keywordmalaysiaidcardnumber"></a><span data-ttu-id="a7f02-2479">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="a7f02-2479">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="a7f02-2480">MyKad</span><span class="sxs-lookup"><span data-stu-id="a7f02-2480">MyKad</span></span> 
- <span data-ttu-id="a7f02-2481">Identity Card</span><span class="sxs-lookup"><span data-stu-id="a7f02-2481">Identity Card</span></span> 
- <span data-ttu-id="a7f02-2482">身份证</span><span class="sxs-lookup"><span data-stu-id="a7f02-2482">ID Card</span></span> 
- <span data-ttu-id="a7f02-2483">身份证</span><span class="sxs-lookup"><span data-stu-id="a7f02-2483">Identification Card</span></span> 
- <span data-ttu-id="a7f02-2484">Digital Application Card
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2484">Digital Application Card</span></span> 
- <span data-ttu-id="a7f02-2485">Kad Akuan Diri
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2485">Kad Akuan Diri</span></span> 
- <span data-ttu-id="a7f02-2486">Kad Aplikasi Digital
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2486">Kad Aplikasi Digital</span></span> 
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="a7f02-2487">荷兰公民服务 (BSN) 号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-2487">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2488">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2488">Format</span></span>

<span data-ttu-id="a7f02-2489">8-9 个数字（包含可选空格）</span><span class="sxs-lookup"><span data-stu-id="a7f02-2489">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2490">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2490">Pattern</span></span>

<span data-ttu-id="a7f02-2491">8-9 个数字：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2491">8-9 digits:</span></span>
- <span data-ttu-id="a7f02-2492">三个数字 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2492">Three digits</span></span> 
- <span data-ttu-id="a7f02-2493">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="a7f02-2493">A space (optional)</span></span> 
- <span data-ttu-id="a7f02-2494">三个数字 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2494">Three digits</span></span> 
- <span data-ttu-id="a7f02-2495">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="a7f02-2495">A space (optional)</span></span> 
- <span data-ttu-id="a7f02-2496">2-3 个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2496">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2497">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2497">Checksum</span></span>

<span data-ttu-id="a7f02-2498">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-2498">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2499">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2499">Definition</span></span>

<span data-ttu-id="a7f02-2500">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2500">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2501">函数 Func_netherlands_bsn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2501">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2502">找到 Keyword_netherlands_bsn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2502">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="a7f02-2503">函数 Func_eu_date2 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2503">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="a7f02-2504">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2504">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-2505">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2505">Keywords</span></span>

#### <a name="keywordnetherlandsbsn"></a><span data-ttu-id="a7f02-2506">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="a7f02-2506">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="a7f02-2507">Citizen service number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2507">Citizen service number</span></span> 
- <span data-ttu-id="a7f02-2508">BSN

</span><span class="sxs-lookup"><span data-stu-id="a7f02-2508">BSN</span></span> 
- <span data-ttu-id="a7f02-2509">Burgerservicenummer
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2509">Burgerservicenummer</span></span> 
- <span data-ttu-id="a7f02-2510">Sofinummer
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2510">Sofinummer</span></span> 
- <span data-ttu-id="a7f02-2511">Persoonsgebonden nummer
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2511">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="a7f02-2512">Persoonsnummer
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2512">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="a7f02-2513">新西兰卫生部号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-2513">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2514">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2514">Format</span></span>

<span data-ttu-id="a7f02-2515">三个字母、一个空格（可选）以及四个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2515">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2516">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2516">Pattern</span></span>

<span data-ttu-id="a7f02-2517">三个字母 （不区分大小写） 空间 （可选） 四位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2517">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2518">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2518">Checksum</span></span>

<span data-ttu-id="a7f02-2519">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-2519">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2520">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2520">Definition</span></span>

<span data-ttu-id="a7f02-2521">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2521">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2522">函数 Func_new_zealand_ministry_of_health_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2522">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2523">找到 Keyword_nz_terms 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2523">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="a7f02-2524">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2524">The checksum passes.</span></span>

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

<span data-ttu-id="a7f02-2525">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2525">Keywords</span></span>

<span data-ttu-id="a7f02-2526">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="a7f02-2526">Keyword_nz_terms</span></span>

- <span data-ttu-id="a7f02-2527">NHI
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2527">NHI</span></span> 
- <span data-ttu-id="a7f02-2528">新西兰</span><span class="sxs-lookup"><span data-stu-id="a7f02-2528">New Zealand</span></span> 
- <span data-ttu-id="a7f02-2529">运行状况</span><span class="sxs-lookup"><span data-stu-id="a7f02-2529">Health</span></span> 
- <span data-ttu-id="a7f02-2530">treatment
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2530">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="a7f02-2531">挪威身份证号</span><span class="sxs-lookup"><span data-stu-id="a7f02-2531">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2532">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2532">Format</span></span>

<span data-ttu-id="a7f02-2533">11 个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2533">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2534">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2534">Pattern</span></span>

<span data-ttu-id="a7f02-2535">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2535">11 digits:</span></span>
- <span data-ttu-id="a7f02-2536">六个数字，采用  DDMMYY 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2536">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="a7f02-2537">三位个人号码 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2537">Three-digit individual number</span></span> 
- <span data-ttu-id="a7f02-2538">两个校验位</span><span class="sxs-lookup"><span data-stu-id="a7f02-2538">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2539">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2539">Checksum</span></span>

<span data-ttu-id="a7f02-2540">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-2540">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2541">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2541">Definition</span></span>

<span data-ttu-id="a7f02-2542">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2542">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2543">函数 Func_norway_id_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2543">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2544">找到 Keyword_norway_id_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2544">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="a7f02-2545">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2545">The checksum passes.</span></span>
- <span data-ttu-id="a7f02-2546">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2546">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2547">函数 Func_norway_id_numbe 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2547">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2548">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2548">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-2549">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2549">Keywords</span></span>

#### <a name="keywordnorwayidnumber"></a><span data-ttu-id="a7f02-2550">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="a7f02-2550">Keyword_norway_id_number</span></span>

- <span data-ttu-id="a7f02-2551">Personal identification number</span><span class="sxs-lookup"><span data-stu-id="a7f02-2551">Personal identification number</span></span>
- <span data-ttu-id="a7f02-2552">Norwegian ID Number</span><span class="sxs-lookup"><span data-stu-id="a7f02-2552">Norwegian ID Number</span></span>
- <span data-ttu-id="a7f02-2553">ID Number</span><span class="sxs-lookup"><span data-stu-id="a7f02-2553">ID Number</span></span>
- <span data-ttu-id="a7f02-2554">Identification</span><span class="sxs-lookup"><span data-stu-id="a7f02-2554">Identification</span></span>
- <span data-ttu-id="a7f02-2555">Personnummer</span><span class="sxs-lookup"><span data-stu-id="a7f02-2555">Personnummer</span></span>
- <span data-ttu-id="a7f02-2556">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="a7f02-2556">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="a7f02-2557">菲律宾统一多用途身份证号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-2557">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2558">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2558">Format</span></span>

<span data-ttu-id="a7f02-2559">12 个数字，通过连字符分隔 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2559">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2560">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2560">Pattern</span></span>

<span data-ttu-id="a7f02-2561">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2561">12 digits:</span></span>
- <span data-ttu-id="a7f02-2562">四个数字 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2562">Four digits</span></span> 
- <span data-ttu-id="a7f02-2563">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2563">A hyphen</span></span> 
- <span data-ttu-id="a7f02-2564">七个数字 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2564">Seven digits</span></span> 
- <span data-ttu-id="a7f02-2565">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2565">A hyphen</span></span> 
- <span data-ttu-id="a7f02-2566">一个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2566">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2567">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2567">Checksum</span></span>

<span data-ttu-id="a7f02-2568">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-2568">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2569">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2569">Definition</span></span>

<span data-ttu-id="a7f02-2570">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2570">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2571">正则表达式 Regex_philippines_unified_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2571">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2572">找到 Keyword_philippines_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2572">A keyword from Keyword_philippines_id is found.</span></span>

```
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7f02-2573">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2573">Keywords</span></span>
   
#### <a name="keywordphilippinesid"></a><span data-ttu-id="a7f02-2574">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="a7f02-2574">Keyword_philippines_id</span></span>

- <span data-ttu-id="a7f02-2575">Unified Multi-Purpose ID
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2575">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="a7f02-2576">UMID
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2576">UMID</span></span> 
- <span data-ttu-id="a7f02-2577">Identity Card</span><span class="sxs-lookup"><span data-stu-id="a7f02-2577">Identity Card</span></span> 
- <span data-ttu-id="a7f02-2578">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="a7f02-2578">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="a7f02-2579">波兰身份证</span><span class="sxs-lookup"><span data-stu-id="a7f02-2579">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2580">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2580">Format</span></span>

<span data-ttu-id="a7f02-2581">三个字母和六个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2581">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2582">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2582">Pattern</span></span>

<span data-ttu-id="a7f02-2583">三个字母（不区分大小写）后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2583">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2584">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2584">Checksum</span></span>

<span data-ttu-id="a7f02-2585">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-2585">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2586">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2586">Definition</span></span>

<span data-ttu-id="a7f02-p138">DLP 策略是相信它已检测到此类型的敏感信息的 75 %if、 内 300 个字符的邻近度： 函数 Func_polish_national_id 查找与模式匹配的内容。找到从 Keyword_polish_national_id_passport_number 关键字。将传递校验和。</span><span class="sxs-lookup"><span data-stu-id="a7f02-p138">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern. A keyword from Keyword_polish_national_id_passport_number is found. The checksum passes.</span></span>

```
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7f02-2590">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2590">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="a7f02-2591">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="a7f02-2591">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="a7f02-2592">Nazwa i nr dowodu tożsamości
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2592">Nazwa i nr dowodu tożsamości</span></span> 
- <span data-ttu-id="a7f02-2593">Dowód Tożsamości
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2593">Dowód Tożsamości</span></span> 
- <span data-ttu-id="a7f02-p139">dow. os.
</span><span class="sxs-lookup"><span data-stu-id="a7f02-p139">dow. os.</span></span> 

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="a7f02-2596">波兰国家/地区 ID (PESEL)</span><span class="sxs-lookup"><span data-stu-id="a7f02-2596">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2597">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2597">Format</span></span>

<span data-ttu-id="a7f02-2598">11 个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2598">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2599">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2599">Pattern</span></span>

<span data-ttu-id="a7f02-2600">11 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2600">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2601">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2601">Checksum</span></span>

<span data-ttu-id="a7f02-2602">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-2602">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2603">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2603">Definition</span></span>

<span data-ttu-id="a7f02-2604">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2604">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2605">函数 Func_pesel_identification_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2605">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2606">找到 Keyword_pesel_identification_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2606">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="a7f02-2607">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2607">The checksum passes.</span></span>

```
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7f02-2608">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2608">Keywords</span></span>

#### <a name="keywordpeselidentificationnumber"></a><span data-ttu-id="a7f02-2609">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="a7f02-2609">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="a7f02-2610">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="a7f02-2610">Nr PESEL</span></span>
- <span data-ttu-id="a7f02-2611">PESEL</span><span class="sxs-lookup"><span data-stu-id="a7f02-2611">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="a7f02-2612">波兰护照</span><span class="sxs-lookup"><span data-stu-id="a7f02-2612">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2613">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2613">Format</span></span>

<span data-ttu-id="a7f02-2614">两个字母和七个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2614">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2615">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2615">Pattern</span></span>

<span data-ttu-id="a7f02-2616">两个字母（不区分大小写）后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2616">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2617">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2617">Checksum</span></span>

<span data-ttu-id="a7f02-2618">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-2618">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2619">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2619">Definition</span></span>

<span data-ttu-id="a7f02-2620">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2620">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2621">函数 Func_polish_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2621">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2622">找到 Keyword_polish_national_id_passport_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2622">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="a7f02-2623">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2623">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-2624">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2624">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="a7f02-2625">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="a7f02-2625">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="a7f02-2626">Nazwa i nr dowodu tożsamości
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2626">Nazwa i nr dowodu tożsamości</span></span> 
- <span data-ttu-id="a7f02-2627">Dowód Tożsamości
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2627">Dowód Tożsamości</span></span> 
- <span data-ttu-id="a7f02-p140">dow. os.
</span><span class="sxs-lookup"><span data-stu-id="a7f02-p140">dow. os.</span></span> 

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="a7f02-2630">葡萄牙公民身份证号</span><span class="sxs-lookup"><span data-stu-id="a7f02-2630">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2631">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2631">Format</span></span>

<span data-ttu-id="a7f02-2632">八个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2632">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2633">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2633">Pattern</span></span>

<span data-ttu-id="a7f02-2634">八个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2634">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2635">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2635">Checksum</span></span>

<span data-ttu-id="a7f02-2636">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-2636">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2637">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2637">Definition</span></span>

<span data-ttu-id="a7f02-2638">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2638">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2639">正则表达式 Regex_portugal_citizen_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2639">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2640">找到 Keyword_portugal_citizen_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2640">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7f02-2641">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2641">Keywords</span></span>

#### <a name="keywordportugalcitizencard"></a><span data-ttu-id="a7f02-2642">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="a7f02-2642">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="a7f02-2643">Citizen Card</span><span class="sxs-lookup"><span data-stu-id="a7f02-2643">Citizen Card</span></span>
- <span data-ttu-id="a7f02-2644">National ID Card</span><span class="sxs-lookup"><span data-stu-id="a7f02-2644">National ID Card</span></span>
- <span data-ttu-id="a7f02-2645">CC</span><span class="sxs-lookup"><span data-stu-id="a7f02-2645">CC</span></span>
- <span data-ttu-id="a7f02-2646">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="a7f02-2646">Cartão de Cidadão</span></span>
- <span data-ttu-id="a7f02-2647">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="a7f02-2647">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="a7f02-2648">沙特阿拉伯国家 ID</span><span class="sxs-lookup"><span data-stu-id="a7f02-2648">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2649">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2649">Format</span></span>

<span data-ttu-id="a7f02-2650">10 个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2650">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2651">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2651">Pattern</span></span>

<span data-ttu-id="a7f02-2652">10 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2652">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2653">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2653">Checksum</span></span>

<span data-ttu-id="a7f02-2654">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-2654">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2655">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2655">Definition</span></span>

<span data-ttu-id="a7f02-2656">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2656">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2657">正则表达式 Regex_saudi_arabia_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2657">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2658">找到 Keyword_saudi_arabia_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2658">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-2659">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2659">Keywords</span></span>

#### <a name="keywordsaudiarabianationalid"></a><span data-ttu-id="a7f02-2660">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="a7f02-2660">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="a7f02-2661">Identification Card
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2661">Identification Card</span></span> 
- <span data-ttu-id="a7f02-2662">I card number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2662">I card number</span></span> 
- <span data-ttu-id="a7f02-2663">ID 号</span><span class="sxs-lookup"><span data-stu-id="a7f02-2663">ID number</span></span> 
- <span data-ttu-id="a7f02-2664">الوطنية الهوية بطاقة رقم
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2664">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="a7f02-2665">新加坡国家登记身份证 (NRIC) 号</span><span class="sxs-lookup"><span data-stu-id="a7f02-2665">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2666">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2666">Format</span></span>

<span data-ttu-id="a7f02-2667">九个字母和数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2667">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2668">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2668">Pattern</span></span>

- <span data-ttu-id="a7f02-2669">九个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2669">Nine letters and digits:</span></span>
- <span data-ttu-id="a7f02-2670">字母“F”、“G”、“S”或“T”（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="a7f02-2670">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="a7f02-2671">七个数字 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2671">Seven digits</span></span> 
- <span data-ttu-id="a7f02-2672">一个字母校验位</span><span class="sxs-lookup"><span data-stu-id="a7f02-2672">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2673">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2673">Checksum</span></span>

<span data-ttu-id="a7f02-2674">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-2674">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2675">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2675">Definition</span></span>

<span data-ttu-id="a7f02-2676">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2676">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2677">正则表达式 Regex_singapore_nric 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2677">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2678">找到 Keyword_singapore_nric 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2678">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="a7f02-2679">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2679">The checksum passes.</span></span>

<span data-ttu-id="a7f02-2680">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2680">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2681">正则表达式 Regex_singapore_nric 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2681">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2682">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2682">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-2683">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2683">Keywords</span></span>
   
#### <a name="keywordsingaporenric"></a><span data-ttu-id="a7f02-2684">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="a7f02-2684">Keyword_singapore_nric</span></span>

- <span data-ttu-id="a7f02-2685">National Registration Identity Card
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2685">National Registration Identity Card</span></span> 
- <span data-ttu-id="a7f02-2686">Identity Card Number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2686">Identity Card Number</span></span> 
- <span data-ttu-id="a7f02-2687">NRIC
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2687">NRIC</span></span> 
- <span data-ttu-id="a7f02-2688">IC
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2688">IC</span></span> 
- <span data-ttu-id="a7f02-2689">Foreign Identification Number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2689">Foreign Identification Number</span></span> 
- <span data-ttu-id="a7f02-2690">FIN
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2690">FIN</span></span> 
- <span data-ttu-id="a7f02-2691">身份证 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2691">身份证</span></span> 
- <span data-ttu-id="a7f02-2692">身份證
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2692">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="a7f02-2693">南非身份证号</span><span class="sxs-lookup"><span data-stu-id="a7f02-2693">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2694">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2694">Format</span></span>

<span data-ttu-id="a7f02-2695">13 个数字（可能包含空格）</span><span class="sxs-lookup"><span data-stu-id="a7f02-2695">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2696">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2696">Pattern</span></span>

<span data-ttu-id="a7f02-2697">13 个数字：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2697">13 digits:</span></span>
- <span data-ttu-id="a7f02-2698">六个数字，采用  YYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2698">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="a7f02-2699">四个数字 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2699">Four digits</span></span> 
- <span data-ttu-id="a7f02-2700">一位公民指示码 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2700">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="a7f02-2701">数字“8”或“9” </span><span class="sxs-lookup"><span data-stu-id="a7f02-2701">The digit "8" or "9"</span></span> 
- <span data-ttu-id="a7f02-2702">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="a7f02-2702">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2703">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2703">Checksum</span></span>

<span data-ttu-id="a7f02-2704">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-2704">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2705">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2705">Definition</span></span>

<span data-ttu-id="a7f02-2706">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2706">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2707">函数 Func_south_africa_identification_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2707">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2708">找到 Keyword_south_africa_identification_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2708">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="a7f02-2709">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2709">The checksum passes.</span></span>

```
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7f02-2710">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2710">Keywords</span></span>
   
#### <a name="keywordsouthafricaidentificationnumber"></a><span data-ttu-id="a7f02-2711">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="a7f02-2711">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="a7f02-2712">Identity card</span><span class="sxs-lookup"><span data-stu-id="a7f02-2712">Identity card</span></span>
- <span data-ttu-id="a7f02-2713">ID</span><span class="sxs-lookup"><span data-stu-id="a7f02-2713">ID</span></span>
- <span data-ttu-id="a7f02-2714">Identification</span><span class="sxs-lookup"><span data-stu-id="a7f02-2714">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="a7f02-2715">韩国居民注册号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-2715">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2716">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2716">Format</span></span>

<span data-ttu-id="a7f02-2717">13 个数字（包含连字符）</span><span class="sxs-lookup"><span data-stu-id="a7f02-2717">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2718">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2718">Pattern</span></span>

<span data-ttu-id="a7f02-2719">13 个数字：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2719">13 digits:</span></span>
- <span data-ttu-id="a7f02-2720">六个数字，采用  YYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2720">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="a7f02-2721">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2721">A hyphen</span></span> 
- <span data-ttu-id="a7f02-2722">一个数字，由世纪和性别 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2722">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="a7f02-2723">四位数字的出生地区代码 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2723">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="a7f02-2724">一个数字，用于区分前面数字均相同的人 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2724">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="a7f02-2725">一个校验位。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2725">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2726">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2726">Checksum</span></span>

<span data-ttu-id="a7f02-2727">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-2727">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2728">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2728">Definition</span></span>

<span data-ttu-id="a7f02-2729">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2729">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2730">函数 Func_south_korea_resident_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2730">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2731">找到 Keyword_south_korea_resident_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2731">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="a7f02-2732">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2732">The checksum passes.</span></span>

<span data-ttu-id="a7f02-2733">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2733">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2734">函数 Func_south_korea_resident_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2734">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2735">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2735">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-2736">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2736">Keywords</span></span>
   
#### <a name="keywordsouthkorearesidentnumber"></a><span data-ttu-id="a7f02-2737">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="a7f02-2737">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="a7f02-2738">National ID card
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2738">National ID card</span></span> 
- <span data-ttu-id="a7f02-2739">Citizen's Registration Number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2739">Citizen's Registration Number</span></span> 
- <span data-ttu-id="a7f02-2740">Jumin deungnok beonho
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2740">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="a7f02-2741">RRN
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2741">RRN</span></span> 
- <span data-ttu-id="a7f02-2742">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="a7f02-2742">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="a7f02-2743">西班牙社会保险号码 (SSN)</span><span class="sxs-lookup"><span data-stu-id="a7f02-2743">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2744">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2744">Format</span></span>

<span data-ttu-id="a7f02-2745">11-12 个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2745">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2746">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2746">Pattern</span></span>

<span data-ttu-id="a7f02-2747">11-12 数字：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2747">11-12 digits:</span></span>
- <span data-ttu-id="a7f02-2748">两位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2748">Two digits</span></span> 
- <span data-ttu-id="a7f02-2749">正斜杠（可选）</span><span class="sxs-lookup"><span data-stu-id="a7f02-2749">A forward slash (optional)</span></span> 
- <span data-ttu-id="a7f02-2750">7-8 位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2750">7-8 digits</span></span> 
- <span data-ttu-id="a7f02-2751">正斜杠（可选）</span><span class="sxs-lookup"><span data-stu-id="a7f02-2751">A forward slash (optional)</span></span> 
- <span data-ttu-id="a7f02-2752">两位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2752">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2753">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2753">Checksum</span></span>

<span data-ttu-id="a7f02-2754">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-2754">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2755">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2755">Definition</span></span>

<span data-ttu-id="a7f02-2756">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2756">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2757">函数 Func_spanish_social_security_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2757">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2758">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2758">The checksum passes.</span></span>

```
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7f02-2759">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2759">Keywords</span></span>

<span data-ttu-id="a7f02-2760">无</span><span class="sxs-lookup"><span data-stu-id="a7f02-2760">None</span></span>
   
## <a name="sweden-national-id"></a><span data-ttu-id="a7f02-2761">瑞典国家 ID</span><span class="sxs-lookup"><span data-stu-id="a7f02-2761">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2762">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2762">Format</span></span>

<span data-ttu-id="a7f02-2763">10 个或 12 个数字和一个可选分隔符</span><span class="sxs-lookup"><span data-stu-id="a7f02-2763">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2764">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2764">Pattern</span></span>

<span data-ttu-id="a7f02-2765">10 或 12 位数字和可选的分隔符：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2765">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="a7f02-2766">2-4 位数字（可选）</span><span class="sxs-lookup"><span data-stu-id="a7f02-2766">2-4 digits (optional)</span></span> 
- <span data-ttu-id="a7f02-2767">采用日期格式 YYMMDD 的六位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2767">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="a7f02-2768">“-”或“+”（可选）的分隔符，加</span><span class="sxs-lookup"><span data-stu-id="a7f02-2768">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="a7f02-2769">四位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2769">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2770">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2770">Checksum</span></span>

<span data-ttu-id="a7f02-2771">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-2771">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2772">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2772">Definition</span></span>

<span data-ttu-id="a7f02-2773">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2773">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2774">函数 Func_swedish_national_identifier 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2774">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2775">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2775">The checksum passes.</span></span>

```
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7f02-2776">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2776">Keywords</span></span>

<span data-ttu-id="a7f02-2777">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-2777">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="a7f02-2778">瑞典护照号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-2778">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2779">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2779">Format</span></span>

<span data-ttu-id="a7f02-2780">八个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2780">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2781">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2781">Pattern</span></span>

<span data-ttu-id="a7f02-2782">八个连续的数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2782">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2783">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2783">Checksum</span></span>

<span data-ttu-id="a7f02-2784">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-2784">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2785">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2785">Definition</span></span>

<span data-ttu-id="a7f02-2786">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2786">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2787">正则表达式 Regex_sweden_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2787">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2788">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2788">One of the following is true:</span></span>
    - <span data-ttu-id="a7f02-2789">找到 Keyword_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2789">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="a7f02-2790">找到 Keyword_sweden_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2790">A keyword from Keyword_sweden_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-2791">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2791">Keywords</span></span>
   
#### <a name="keywordswedenpassport"></a><span data-ttu-id="a7f02-2792">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="a7f02-2792">Keyword_sweden_passport</span></span>

- <span data-ttu-id="a7f02-2793">visa requirements
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2793">visa requirements</span></span> 
- <span data-ttu-id="a7f02-2794">Alien Registration Card
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2794">Alien Registration Card</span></span> 
- <span data-ttu-id="a7f02-2795">Schengen visas
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2795">Schengen visas</span></span> 
- <span data-ttu-id="a7f02-2796">Schengen visa
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2796">Schengen visa</span></span> 
- <span data-ttu-id="a7f02-2797">Visa Processing
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2797">Visa Processing</span></span> 
- <span data-ttu-id="a7f02-2798">Visa Type
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2798">Visa Type</span></span> 
- <span data-ttu-id="a7f02-2799">Single Entry
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2799">Single Entry</span></span> 
- <span data-ttu-id="a7f02-2800">Multiple Entry
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2800">Multiple Entry</span></span> 
- <span data-ttu-id="a7f02-2801">G3 Processing Fees

</span><span class="sxs-lookup"><span data-stu-id="a7f02-2801">G3 Processing Fees</span></span> 

#### <a name="keywordpassport"></a><span data-ttu-id="a7f02-2802">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="a7f02-2802">Keyword_passport</span></span>

- <span data-ttu-id="a7f02-2803">Passport Number</span><span class="sxs-lookup"><span data-stu-id="a7f02-2803">Passport Number</span></span> 
- <span data-ttu-id="a7f02-2804">
Passport No</span><span class="sxs-lookup"><span data-stu-id="a7f02-2804">Passport No</span></span> 
- <span data-ttu-id="a7f02-2805">Passport #
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2805">Passport #</span></span> 
- <span data-ttu-id="a7f02-2806">Passport#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2806">Passport#</span></span> 
- <span data-ttu-id="a7f02-2807">PassportID</span><span class="sxs-lookup"><span data-stu-id="a7f02-2807">PassportID</span></span> 
- <span data-ttu-id="a7f02-2808">Passportno
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2808">Passportno</span></span> 
- <span data-ttu-id="a7f02-2809">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2809">passportnumber</span></span> 
- <span data-ttu-id="a7f02-2810">パスポート</span><span class="sxs-lookup"><span data-stu-id="a7f02-2810">パスポート</span></span> 
- <span data-ttu-id="a7f02-2811">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2811">パスポート番号</span></span> 
- <span data-ttu-id="a7f02-2812">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2812">パスポートのNum</span></span> 
- <span data-ttu-id="a7f02-2813">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2813">パスポート＃</span></span> 
- <span data-ttu-id="a7f02-2814">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="a7f02-2814">Numéro de passeport</span></span> 
- <span data-ttu-id="a7f02-2815">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="a7f02-2815">Passeport n °</span></span> 
- <span data-ttu-id="a7f02-2816">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2816">Passeport Non</span></span> 
- <span data-ttu-id="a7f02-2817">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2817">Passeport #</span></span> 
- <span data-ttu-id="a7f02-2818">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2818">Passeport#</span></span> 
- <span data-ttu-id="a7f02-2819">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="a7f02-2819">PasseportNon</span></span> 
- <span data-ttu-id="a7f02-2820">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2820">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="a7f02-2821">SWIFT 代码</span><span class="sxs-lookup"><span data-stu-id="a7f02-2821">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2822">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2822">Format</span></span>

<span data-ttu-id="a7f02-2823">四个字母后跟 5-31 个字母或数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2823">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2824">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2824">Pattern</span></span>

<span data-ttu-id="a7f02-2825">四个字母后跟 5-31 个字母或数字：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2825">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="a7f02-2826">四个字母的银行代码（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="a7f02-2826">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="a7f02-2827">可选空格</span><span class="sxs-lookup"><span data-stu-id="a7f02-2827">An optional space</span></span> 
- <span data-ttu-id="a7f02-2828">4-28 个字母或数字（基本银行账号 (BBAN)）</span><span class="sxs-lookup"><span data-stu-id="a7f02-2828">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="a7f02-2829">可选空格</span><span class="sxs-lookup"><span data-stu-id="a7f02-2829">An optional space</span></span> 
- <span data-ttu-id="a7f02-2830">1-3 个字母或数字（BBAN 的剩余内容）</span><span class="sxs-lookup"><span data-stu-id="a7f02-2830">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2831">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2831">Checksum</span></span>

<span data-ttu-id="a7f02-2832">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-2832">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2833">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2833">Definition</span></span>

<span data-ttu-id="a7f02-2834">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2834">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2835">正则表达式 Regex_swift 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2835">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2836">找到 Keyword_swift 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2836">A keyword from Keyword_swift is found.</span></span>

```
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7f02-2837">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2837">Keywords</span></span>
   
#### <a name="keywordswift"></a><span data-ttu-id="a7f02-2838">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="a7f02-2838">Keyword_swift</span></span>

- <span data-ttu-id="a7f02-2839">international organization for standardization 9362
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2839">international organization for standardization 9362</span></span> 
- <span data-ttu-id="a7f02-2840">iso 9362
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2840">iso 9362</span></span> 
- <span data-ttu-id="a7f02-2841">iso9362</span><span class="sxs-lookup"><span data-stu-id="a7f02-2841">iso9362</span></span> 
- <span data-ttu-id="a7f02-2842">swift\#</span><span class="sxs-lookup"><span data-stu-id="a7f02-2842">swift\#</span></span> 
- <span data-ttu-id="a7f02-2843">swiftcode
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2843">swiftcode</span></span> 
- <span data-ttu-id="a7f02-2844">swiftnumber
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2844">swiftnumber</span></span> 
- <span data-ttu-id="a7f02-2845">swiftroutingnumber
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2845">swiftroutingnumber</span></span> 
- <span data-ttu-id="a7f02-2846">swift 代码</span><span class="sxs-lookup"><span data-stu-id="a7f02-2846">swift code</span></span> 
- <span data-ttu-id="a7f02-2847">swift number #
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2847">swift number #</span></span> 
- <span data-ttu-id="a7f02-2848">swift routing number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2848">swift routing number</span></span> 
- <span data-ttu-id="a7f02-2849">bic number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2849">bic number</span></span> 
- <span data-ttu-id="a7f02-2850">bic code
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2850">bic code</span></span> 
- <span data-ttu-id="a7f02-2851">bic\#</span><span class="sxs-lookup"><span data-stu-id="a7f02-2851">bic \#</span></span> 
- <span data-ttu-id="a7f02-2852">bic\#</span><span class="sxs-lookup"><span data-stu-id="a7f02-2852">bic\#</span></span> 
- <span data-ttu-id="a7f02-2853">bank identifier code
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2853">bank identifier code</span></span> 
- <span data-ttu-id="a7f02-2854">標準化9362</span><span class="sxs-lookup"><span data-stu-id="a7f02-2854">標準化9362</span></span> 
- <span data-ttu-id="a7f02-2855">迅速＃
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2855">迅速＃</span></span> 
- <span data-ttu-id="a7f02-2856">SWIFTコード
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2856">SWIFTコード</span></span> 
- <span data-ttu-id="a7f02-2857">SWIFT番号
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2857">SWIFT番号</span></span> 
- <span data-ttu-id="a7f02-2858">迅速なルーティング番号
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2858">迅速なルーティング番号</span></span> 
- <span data-ttu-id="a7f02-2859">BIC番号
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2859">BIC番号</span></span> 
- <span data-ttu-id="a7f02-2860">BICコード
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2860">BICコード</span></span> 
- <span data-ttu-id="a7f02-2861">銀行識別コードのための国際組織
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2861">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="a7f02-2862">Organisation internationale de normalisation 9362
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2862">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="a7f02-2863">rapide\#</span><span class="sxs-lookup"><span data-stu-id="a7f02-2863">rapide \#</span></span> 
- <span data-ttu-id="a7f02-2864">code SWIFT
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2864">code SWIFT</span></span> 
- <span data-ttu-id="a7f02-2865">le numéro de swift
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2865">le numéro de swift</span></span> 
- <span data-ttu-id="a7f02-2866">swift numéro d'acheminement
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2866">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="a7f02-2867">le numéro BIC
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2867">le numéro BIC</span></span> 
- <span data-ttu-id="a7f02-2868">\#BIC</span><span class="sxs-lookup"><span data-stu-id="a7f02-2868">\# BIC</span></span> 
- <span data-ttu-id="a7f02-2869">code identificateur de banque
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2869">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="a7f02-2870">台湾国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="a7f02-2870">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2871">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2871">Format</span></span>

<span data-ttu-id="a7f02-2872">一个字母后跟九个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2872">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2873">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2873">Pattern</span></span>

<span data-ttu-id="a7f02-2874">一个字母后跟 9 位数字：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2874">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="a7f02-2875">一个字母（英文，不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="a7f02-2875">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="a7f02-2876">数字“1”或“2”</span><span class="sxs-lookup"><span data-stu-id="a7f02-2876">The digit "1" or "2"</span></span> 
- <span data-ttu-id="a7f02-2877">八个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2877">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2878">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2878">Checksum</span></span>

<span data-ttu-id="a7f02-2879">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-2879">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2880">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2880">Definition</span></span>

<span data-ttu-id="a7f02-2881">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2881">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2882">函数 Func_taiwanese_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2882">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2883">找到 Keyword_taiwanese_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2883">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="a7f02-2884">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2884">The checksum passes.</span></span>

```
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7f02-2885">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2885">Keywords</span></span>

#### <a name="keywordtaiwanesenationalid"></a><span data-ttu-id="a7f02-2886">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="a7f02-2886">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="a7f02-2887">身份證字號
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2887">身份證字號</span></span> 
- <span data-ttu-id="a7f02-2888">身份證
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2888">身份證</span></span> 
- <span data-ttu-id="a7f02-2889">身份證號碼
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2889">身份證號碼</span></span> 
- <span data-ttu-id="a7f02-2890">身份證號
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2890">身份證號</span></span> 
- <span data-ttu-id="a7f02-2891">身分證字號
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2891">身分證字號</span></span> 
- <span data-ttu-id="a7f02-2892">身分證 </span><span class="sxs-lookup"><span data-stu-id="a7f02-2892">身分證</span></span> 
- <span data-ttu-id="a7f02-2893">身分證號碼
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2893">身分證號碼</span></span> 
- <span data-ttu-id="a7f02-2894">身份證號
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2894">身份證號</span></span> 
- <span data-ttu-id="a7f02-2895">身分證統一編號
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2895">身分證統一編號</span></span> 
- <span data-ttu-id="a7f02-2896">國民身分證統一編號
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2896">國民身分證統一編號</span></span> 
- <span data-ttu-id="a7f02-2897">簽名
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2897">簽名</span></span> 
- <span data-ttu-id="a7f02-2898">蓋章
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2898">蓋章</span></span> 
- <span data-ttu-id="a7f02-2899">簽名或蓋章

</span><span class="sxs-lookup"><span data-stu-id="a7f02-2899">簽名或蓋章</span></span> 
- <span data-ttu-id="a7f02-2900">簽章</span><span class="sxs-lookup"><span data-stu-id="a7f02-2900">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="a7f02-2901">	台湾护照号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-2901">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2902">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2902">Format</span></span>

- <span data-ttu-id="a7f02-2903">生物护照号码： 九个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2903">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="a7f02-2904">非生物护照号码： 九个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2904">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2905">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2905">Pattern</span></span>
<span data-ttu-id="a7f02-2906">生物护照号码：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2906">Biometric passport number:</span></span>
- <span data-ttu-id="a7f02-2907">数字“3” </span><span class="sxs-lookup"><span data-stu-id="a7f02-2907">The digit "3"</span></span> 
- <span data-ttu-id="a7f02-2908">八个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2908">Eight digits</span></span>

<span data-ttu-id="a7f02-2909">非生物护照号码：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2909">Non-biometric passport number:</span></span>
- <span data-ttu-id="a7f02-2910">九个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2910">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2911">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2911">Checksum</span></span>

<span data-ttu-id="a7f02-2912">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-2912">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2913">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2913">Definition</span></span>

<span data-ttu-id="a7f02-2914">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2914">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2915">正则表达式 Regex_taiwan_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2915">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2916">找到 Keyword_taiwan_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2916">A keyword from Keyword_taiwan_passport is found.</span></span>

```
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7f02-2917">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2917">Keywords</span></span>

#### <a name="keywordtaiwanpassport"></a><span data-ttu-id="a7f02-2918">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="a7f02-2918">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="a7f02-2919">台湾 passport number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2919">ROC passport number</span></span> 
- <span data-ttu-id="a7f02-2920">护照号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-2920">Passport number</span></span> 
- <span data-ttu-id="a7f02-2921">Passport 没有</span><span class="sxs-lookup"><span data-stu-id="a7f02-2921">Passport no</span></span> 
- <span data-ttu-id="a7f02-2922">Passport Num
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2922">Passport Num</span></span> 
- <span data-ttu-id="a7f02-2923">Passport #
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2923">Passport #</span></span> 
- <span data-ttu-id="a7f02-2924">护照
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2924">护照</span></span> 
- <span data-ttu-id="a7f02-2925">中華民國護照
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2925">中華民國護照</span></span> 
- <span data-ttu-id="a7f02-2926">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="a7f02-2926">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="a7f02-2927">台湾居民证 (ARC/TARC) 号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-2927">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2928">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2928">Format</span></span>

<span data-ttu-id="a7f02-2929">10 letters and digits</span><span class="sxs-lookup"><span data-stu-id="a7f02-2929">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2930">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2930">Pattern</span></span>

<span data-ttu-id="a7f02-2931">10 个字母和数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2931">10 letters and digits:</span></span>
- <span data-ttu-id="a7f02-2932">两个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="a7f02-2932">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="a7f02-2933">八个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2933">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2934">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2934">Checksum</span></span>

<span data-ttu-id="a7f02-2935">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-2935">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2936">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2936">Definition</span></span>

<span data-ttu-id="a7f02-2937">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2937">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2938">正则表达式 Regex_taiwan_resident_certificate 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2938">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2939">找到 Keyword_taiwan_resident_certificate 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2939">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7f02-2940">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2940">Keywords</span></span>

#### <a name="keywordtaiwanresidentcertificate"></a><span data-ttu-id="a7f02-2941">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="a7f02-2941">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="a7f02-2942">Resident Certificate
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2942">Resident Certificate</span></span> 
- <span data-ttu-id="a7f02-2943">驻留的证书</span><span class="sxs-lookup"><span data-stu-id="a7f02-2943">Resident Cert</span></span> 
- <span data-ttu-id="a7f02-2944">Resident Cert.
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2944">Resident Cert.</span></span> 
- <span data-ttu-id="a7f02-2945">身份证</span><span class="sxs-lookup"><span data-stu-id="a7f02-2945">Identification card</span></span> 
- <span data-ttu-id="a7f02-2946">Alien Resident Certificate
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2946">Alien Resident Certificate</span></span> 
- <span data-ttu-id="a7f02-2947">ARC
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2947">ARC</span></span> 
- <span data-ttu-id="a7f02-2948">Taiwan Area Resident Certificate
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2948">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="a7f02-2949">TARC
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2949">TARC</span></span> 
- <span data-ttu-id="a7f02-2950">居留證
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2950">居留證</span></span> 
- <span data-ttu-id="a7f02-2951">外僑居留證
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2951">外僑居留證</span></span> 
- <span data-ttu-id="a7f02-2952">台灣地區居留證
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2952">台灣地區居留證</span></span> 
   
## <a name="uk-drivers-license-number"></a><span data-ttu-id="a7f02-p141">英国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-p141">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2955">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2955">Format</span></span>

<span data-ttu-id="a7f02-2956">特定格式的 18 个字母和数字组合</span><span class="sxs-lookup"><span data-stu-id="a7f02-2956">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2957">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2957">Pattern</span></span>

<span data-ttu-id="a7f02-2958">18 个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2958">18 letters and digits:</span></span>
- <span data-ttu-id="a7f02-2959">用五个字母（不区分大小写）或数字“9”来代替一个字母</span><span class="sxs-lookup"><span data-stu-id="a7f02-2959">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="a7f02-2960">一位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2960">One digit</span></span> 
- <span data-ttu-id="a7f02-2961">采用日期格式 DDMMY 的五位数字，表示出生日期</span><span class="sxs-lookup"><span data-stu-id="a7f02-2961">Five digits in the date format DDMMY for date of birth</span></span> 
- <span data-ttu-id="a7f02-2962">用两个字母（不区分大小写）或数字“9”来代替一个字母</span><span class="sxs-lookup"><span data-stu-id="a7f02-2962">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="a7f02-2963">五位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2963">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2964">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2964">Checksum</span></span>

<span data-ttu-id="a7f02-2965">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-2965">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2966">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2966">Definition</span></span>

<span data-ttu-id="a7f02-2967">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2967">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2968">函数 Func_uk_drivers_license 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2968">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2969">找到 Keyword_uk_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2969">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="a7f02-2970">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2970">The checksum passes.</span></span>

```
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7f02-2971">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2971">Keywords</span></span>

#### <a name="keywordukdriverslicense"></a><span data-ttu-id="a7f02-2972">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="a7f02-2972">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="a7f02-2973">DVLA
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2973">DVLA</span></span> 
- <span data-ttu-id="a7f02-2974">light vans
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2974">light vans</span></span> 
- <span data-ttu-id="a7f02-2975">quadbikes
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2975">quadbikes</span></span> 
- <span data-ttu-id="a7f02-2976">motor cars
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2976">motor cars</span></span> 
- <span data-ttu-id="a7f02-2977">125cc</span><span class="sxs-lookup"><span data-stu-id="a7f02-2977">125cc</span></span> 
- <span data-ttu-id="a7f02-2978">sidecar
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2978">sidecar</span></span> 
- <span data-ttu-id="a7f02-2979">tricycles
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2979">tricycles</span></span> 
- <span data-ttu-id="a7f02-2980">motorcycles
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2980">motorcycles</span></span> 
- <span data-ttu-id="a7f02-2981">photocard licence
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2981">photocard licence</span></span> 
- <span data-ttu-id="a7f02-2982">learner drivers
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2982">learner drivers</span></span> 
- <span data-ttu-id="a7f02-2983">licence holder
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2983">licence holder</span></span> 
- <span data-ttu-id="a7f02-2984">licence holders
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2984">licence holders</span></span> 
- <span data-ttu-id="a7f02-2985">driving licences
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2985">driving licences</span></span> 
- <span data-ttu-id="a7f02-2986">driving licence
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2986">driving licence</span></span> 
- <span data-ttu-id="a7f02-2987">dual control car
</span><span class="sxs-lookup"><span data-stu-id="a7f02-2987">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="a7f02-p142">英国选民名册号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-p142">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-2990">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2990">Format</span></span>

<span data-ttu-id="a7f02-2991">两个字母后跟 1-4 个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2991">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-2992">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-2992">Pattern</span></span>

<span data-ttu-id="a7f02-2993">两个字母（不区分大小写）后跟 1-4 个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-2993">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-2994">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-2994">Checksum</span></span>

<span data-ttu-id="a7f02-2995">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-2995">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-2996">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-2996">Definition</span></span>

<span data-ttu-id="a7f02-2997">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-2997">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-2998">正则表达式 Regex_uk_electoral 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2998">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-2999">找到 Keyword_uk_electoral 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-2999">A keyword from Keyword_uk_electoral is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-3000">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-3000">Keywords</span></span>

#### <a name="keywordukelectoral"></a><span data-ttu-id="a7f02-3001">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="a7f02-3001">Keyword_uk_electoral</span></span>

- <span data-ttu-id="a7f02-3002">council nomination
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3002">council nomination</span></span> 
- <span data-ttu-id="a7f02-3003">nomination form
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3003">nomination form</span></span> 
- <span data-ttu-id="a7f02-3004">electoral register

</span><span class="sxs-lookup"><span data-stu-id="a7f02-3004">electoral register</span></span> 
- <span data-ttu-id="a7f02-3005">electoral roll</span><span class="sxs-lookup"><span data-stu-id="a7f02-3005">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="a7f02-p143">英国国家卫生服务号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-p143">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-3008">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-3008">Format</span></span>

<span data-ttu-id="a7f02-3009">10-17 个数字，通过空格分隔 </span><span class="sxs-lookup"><span data-stu-id="a7f02-3009">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-3010">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-3010">Pattern</span></span>

<span data-ttu-id="a7f02-3011">10-17 位数字：</span><span class="sxs-lookup"><span data-stu-id="a7f02-3011">10-17 digits:</span></span>
- <span data-ttu-id="a7f02-3012">3 或 10 位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-3012">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="a7f02-3013">一个空格</span><span class="sxs-lookup"><span data-stu-id="a7f02-3013">A space</span></span> 
- <span data-ttu-id="a7f02-3014">三位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-3014">Three digits</span></span> 
- <span data-ttu-id="a7f02-3015">一个空格</span><span class="sxs-lookup"><span data-stu-id="a7f02-3015">A space</span></span> 
- <span data-ttu-id="a7f02-3016">四位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-3016">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-3017">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-3017">Checksum</span></span>

<span data-ttu-id="a7f02-3018">是</span><span class="sxs-lookup"><span data-stu-id="a7f02-3018">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-3019">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-3019">Definition</span></span>

<span data-ttu-id="a7f02-3020">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-3020">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-3021">函数 Func_uk_nhs_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3021">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-3022">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="a7f02-3022">One of the following is true:</span></span>
    - <span data-ttu-id="a7f02-3023">找到 Keyword_uk_nhs_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3023">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="a7f02-3024">找到 Keyword_uk_nhs_number1 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3024">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="a7f02-3025">找到 Keyword_uk_nhs_number_dob 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3025">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="a7f02-3026">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3026">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-3027">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-3027">Keywords</span></span>
   
#### <a name="keyworduknhsnumber"></a><span data-ttu-id="a7f02-3028">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="a7f02-3028">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="a7f02-3029">national health service
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3029">national health service</span></span> 
- <span data-ttu-id="a7f02-3030">nhs
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3030">nhs</span></span> 
- <span data-ttu-id="a7f02-3031">health services authority

</span><span class="sxs-lookup"><span data-stu-id="a7f02-3031">health services authority</span></span> 
- <span data-ttu-id="a7f02-3032">health authority</span><span class="sxs-lookup"><span data-stu-id="a7f02-3032">health authority</span></span>

#### <a name="keyworduknhsnumber1"></a><span data-ttu-id="a7f02-3033">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="a7f02-3033">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="a7f02-3034">patient id
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3034">patient id</span></span> 
- <span data-ttu-id="a7f02-3035">patient identification
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3035">patient identification</span></span> 
- <span data-ttu-id="a7f02-3036">patient no

</span><span class="sxs-lookup"><span data-stu-id="a7f02-3036">patient no</span></span> 
- <span data-ttu-id="a7f02-3037">patient number</span><span class="sxs-lookup"><span data-stu-id="a7f02-3037">patient number</span></span>

#### <a name="keyworduknhsnumberdob"></a><span data-ttu-id="a7f02-3038">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="a7f02-3038">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="a7f02-3039">GP</span><span class="sxs-lookup"><span data-stu-id="a7f02-3039">GP</span></span> 
- <span data-ttu-id="a7f02-3040">DOB
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3040">DOB</span></span> 
- <span data-ttu-id="a7f02-3041">D.O.B</span><span class="sxs-lookup"><span data-stu-id="a7f02-3041">D.O.B</span></span> 
- <span data-ttu-id="a7f02-3042">Date of Birth
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3042">Date of Birth</span></span> 
- <span data-ttu-id="a7f02-3043">Birth Date
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3043">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="a7f02-p144">英国国家保险号码 (NINO)</span><span class="sxs-lookup"><span data-stu-id="a7f02-p144">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-3046">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-3046">Format</span></span>

<span data-ttu-id="a7f02-3047">7 个字符或 9 个字符，并用空格或短划线</span><span class="sxs-lookup"><span data-stu-id="a7f02-3047">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-3048">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-3048">Pattern</span></span>

<span data-ttu-id="a7f02-3049">两种可能的模式：</span><span class="sxs-lookup"><span data-stu-id="a7f02-3049">Two possible patterns:</span></span>

- <span data-ttu-id="a7f02-3050">两个字母 (有效 NINOs 使用此前缀，此模式中验证; 中只有某些字符不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="a7f02-3050">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="a7f02-3051">六位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-3051">Six digits</span></span>
- <span data-ttu-id="a7f02-3052">任一 'A'，'B'，'C'，或具有 （如前缀，只某些字符允许在后缀; 不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="a7f02-3052">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="a7f02-3053">OR</span><span class="sxs-lookup"><span data-stu-id="a7f02-3053">OR</span></span>

- <span data-ttu-id="a7f02-3054">两个字母</span><span class="sxs-lookup"><span data-stu-id="a7f02-3054">Two letters</span></span>
- <span data-ttu-id="a7f02-3055">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="a7f02-3055">A space or dash</span></span>
- <span data-ttu-id="a7f02-3056">两位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-3056">Two digits</span></span>
- <span data-ttu-id="a7f02-3057">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="a7f02-3057">A space or dash</span></span>
- <span data-ttu-id="a7f02-3058">两位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-3058">Two digits</span></span>
- <span data-ttu-id="a7f02-3059">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="a7f02-3059">A space or dash</span></span>
- <span data-ttu-id="a7f02-3060">两位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-3060">Two digits</span></span>
- <span data-ttu-id="a7f02-3061">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="a7f02-3061">A space or dash</span></span>
- <span data-ttu-id="a7f02-3062">任一 'A'，'B'，'C'，或具有</span><span class="sxs-lookup"><span data-stu-id="a7f02-3062">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-3063">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-3063">Checksum</span></span>

<span data-ttu-id="a7f02-3064">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-3064">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-3065">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-3065">Definition</span></span>

<span data-ttu-id="a7f02-3066">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-3066">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-3067">函数 Func_uk_nino 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3067">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-3068">找到 Keyword_uk_nino 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3068">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="a7f02-3069">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-3069">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-3070">函数 Func_uk_nino 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3070">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-3071">未找到 Keyword_uk_nino 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3071">No keyword from Keyword_uk_nino is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-3072">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-3072">Keywords</span></span>

#### <a name="keyworduknino"></a><span data-ttu-id="a7f02-3073">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="a7f02-3073">Keyword_uk_nino</span></span>

- <span data-ttu-id="a7f02-3074">national insurance number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3074">national insurance number</span></span> 
- <span data-ttu-id="a7f02-3075">national insurance contributions
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3075">national insurance contributions</span></span> 
- <span data-ttu-id="a7f02-3076">protection act
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3076">protection act</span></span> 
- <span data-ttu-id="a7f02-3077">insurance
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3077">insurance</span></span> 
- <span data-ttu-id="a7f02-3078">social security number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3078">social security number</span></span> 
- <span data-ttu-id="a7f02-3079">insurance application
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3079">insurance application</span></span> 
- <span data-ttu-id="a7f02-3080">medical application
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3080">medical application</span></span> 
- <span data-ttu-id="a7f02-3081">social insurance
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3081">social insurance</span></span> 
- <span data-ttu-id="a7f02-3082">medical attention
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3082">medical attention</span></span> 
- <span data-ttu-id="a7f02-3083">社会安全</span><span class="sxs-lookup"><span data-stu-id="a7f02-3083">social security</span></span> 
- <span data-ttu-id="a7f02-3084">great britain
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3084">great britain</span></span> 
- <span data-ttu-id="a7f02-3085">insurance
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3085">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="a7f02-p145">美国/英国护照号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-p145">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-3088">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-3088">Format</span></span>

<span data-ttu-id="a7f02-3089">九个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-3089">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-3090">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-3090">Pattern</span></span>

<span data-ttu-id="a7f02-3091">九个连续的数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-3091">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-3092">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-3092">Checksum</span></span>

<span data-ttu-id="a7f02-3093">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-3093">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-3094">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-3094">Definition</span></span>

<span data-ttu-id="a7f02-3095">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-3095">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-3096">函数 Func_usa_uk_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3096">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-3097">找到 Keyword_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3097">A keyword from Keyword_passport is found.</span></span>

```
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7f02-3098">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-3098">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="a7f02-3099">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="a7f02-3099">Keyword_passport</span></span>

- <span data-ttu-id="a7f02-3100">Passport Number</span><span class="sxs-lookup"><span data-stu-id="a7f02-3100">Passport Number</span></span> 
- <span data-ttu-id="a7f02-3101">
Passport No</span><span class="sxs-lookup"><span data-stu-id="a7f02-3101">Passport No</span></span> 
- <span data-ttu-id="a7f02-3102">Passport #
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3102">Passport #</span></span> 
- <span data-ttu-id="a7f02-3103">Passport#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3103">Passport#</span></span> 
- <span data-ttu-id="a7f02-3104">PassportID</span><span class="sxs-lookup"><span data-stu-id="a7f02-3104">PassportID</span></span> 
- <span data-ttu-id="a7f02-3105">Passportno
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3105">Passportno</span></span> 
- <span data-ttu-id="a7f02-3106">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3106">passportnumber</span></span> 
- <span data-ttu-id="a7f02-3107">パスポート</span><span class="sxs-lookup"><span data-stu-id="a7f02-3107">パスポート</span></span> 
- <span data-ttu-id="a7f02-3108">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3108">パスポート番号</span></span> 
- <span data-ttu-id="a7f02-3109">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3109">パスポートのNum</span></span> 
- <span data-ttu-id="a7f02-3110">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3110">パスポート＃</span></span> 
- <span data-ttu-id="a7f02-3111">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="a7f02-3111">Numéro de passeport</span></span> 
- <span data-ttu-id="a7f02-3112">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="a7f02-3112">Passeport n °</span></span> 
- <span data-ttu-id="a7f02-3113">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3113">Passeport Non</span></span> 
- <span data-ttu-id="a7f02-3114">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3114">Passeport #</span></span> 
- <span data-ttu-id="a7f02-3115">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3115">Passeport#</span></span> 
- <span data-ttu-id="a7f02-3116">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="a7f02-3116">PasseportNon</span></span> 
- <span data-ttu-id="a7f02-3117">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3117">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="a7f02-3118">美国银行帐号</span><span class="sxs-lookup"><span data-stu-id="a7f02-3118">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-3119">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-3119">Format</span></span>

<span data-ttu-id="a7f02-3120">8-17 个数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-3120">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-3121">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-3121">Pattern</span></span>

<span data-ttu-id="a7f02-3122">8-17 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-3122">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-3123">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-3123">Checksum</span></span>

<span data-ttu-id="a7f02-3124">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-3124">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-3125">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-3125">Definition</span></span>

<span data-ttu-id="a7f02-3126">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-3126">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-3127">正则表达式 Regex_usa_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3127">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-3128">找到 Keyword_usa_Bank_Account 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3128">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7f02-3129">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-3129">Keywords</span></span>

#### <a name="keywordusabankaccount"></a><span data-ttu-id="a7f02-3130">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="a7f02-3130">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="a7f02-3131">Checking Account Number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3131">Checking Account Number</span></span> 
- <span data-ttu-id="a7f02-3132">Checking Account
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3132">Checking Account</span></span> 
- <span data-ttu-id="a7f02-3133">Checking Account #
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3133">Checking Account #</span></span> 
- <span data-ttu-id="a7f02-3134">Checking Acct Number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3134">Checking Acct Number</span></span> 
- <span data-ttu-id="a7f02-3135">Checking Acct #
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3135">Checking Acct #</span></span> 
- <span data-ttu-id="a7f02-3136">Checking Acct No.
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3136">Checking Acct No.</span></span> 
- <span data-ttu-id="a7f02-3137">Checking Account No.
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3137">Checking Account No.</span></span> 
- <span data-ttu-id="a7f02-3138">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3138">Bank Account Number</span></span> 
- <span data-ttu-id="a7f02-3139">Bank Account #
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3139">Bank Account #</span></span> 
- <span data-ttu-id="a7f02-3140">Bank Acct Number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3140">Bank Acct Number</span></span> 
- <span data-ttu-id="a7f02-3141">Bank Acct #
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3141">Bank Acct #</span></span> 
- <span data-ttu-id="a7f02-3142">Bank Acct No.
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3142">Bank Acct No.</span></span> 
- <span data-ttu-id="a7f02-3143">Bank Account No.
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3143">Bank Account No.</span></span> 
- <span data-ttu-id="a7f02-3144">Savings Account Number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3144">Savings Account Number</span></span> 
- <span data-ttu-id="a7f02-3145">Savings Account.
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3145">Savings Account.</span></span> 
- <span data-ttu-id="a7f02-3146">Savings Account #
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3146">Savings Account #</span></span> 
- <span data-ttu-id="a7f02-3147">Savings Acct Number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3147">Savings Acct Number</span></span> 
- <span data-ttu-id="a7f02-3148">Savings Acct #
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3148">Savings Acct #</span></span> 
- <span data-ttu-id="a7f02-3149">Savings Acct No.
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3149">Savings Acct No.</span></span> 
- <span data-ttu-id="a7f02-3150">Savings Account No.
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3150">Savings Account No.</span></span> 
- <span data-ttu-id="a7f02-3151">Debit Account Number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3151">Debit Account Number</span></span> 
- <span data-ttu-id="a7f02-3152">Debit Account
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3152">Debit Account</span></span> 
- <span data-ttu-id="a7f02-3153">Debit Account #
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3153">Debit Account #</span></span> 
- <span data-ttu-id="a7f02-3154">Debit Acct Number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3154">Debit Acct Number</span></span> 
- <span data-ttu-id="a7f02-3155">Debit Acct #
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3155">Debit Acct #</span></span> 
- <span data-ttu-id="a7f02-3156">Debit Acct No.
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3156">Debit Acct No.</span></span> 
- <span data-ttu-id="a7f02-3157">Debit Account No.
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3157">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="a7f02-3158">美国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a7f02-3158">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-3159">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-3159">Format</span></span>

<span data-ttu-id="a7f02-3160">取决于州</span><span class="sxs-lookup"><span data-stu-id="a7f02-3160">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-3161">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-3161">Pattern</span></span>

<span data-ttu-id="a7f02-3162">取决于州 — 例如，纽约：</span><span class="sxs-lookup"><span data-stu-id="a7f02-3162">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="a7f02-3163">诸如 ddd ddd ddd 的 9 个数字的格式将匹配。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3163">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="a7f02-3164">诸如 dddddddd 的 9 个数字将不匹配。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3164">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-3165">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-3165">Checksum</span></span>

<span data-ttu-id="a7f02-3166">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-3166">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-3167">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-3167">Definition</span></span>

<span data-ttu-id="a7f02-3168">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-3168">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-3169">函数 Func_new_york_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3169">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-3170">找到 Keyword_[state_name]_drivers_license_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3170">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="a7f02-3171">找到 Keyword_us_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3171">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="a7f02-3172">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-3172">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-3173">函数 Func_new_york_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3173">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-3174">找到 Keyword_[state_name]_drivers_license_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3174">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="a7f02-3175">找到 Keyword_us_drivers_license_abbreviations 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3175">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="a7f02-3176">未找到 Keyword_us_drivers_license 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3176">No keyword from Keyword_us_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-3177">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-3177">Keywords</span></span>

#### <a name="keywordusdriverslicenseabbreviations"></a><span data-ttu-id="a7f02-3178">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="a7f02-3178">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="a7f02-3179">DL</span><span class="sxs-lookup"><span data-stu-id="a7f02-3179">DL</span></span> 
- <span data-ttu-id="a7f02-3180">DLS</span><span class="sxs-lookup"><span data-stu-id="a7f02-3180">DLS</span></span> 
- <span data-ttu-id="a7f02-3181">CDL</span><span class="sxs-lookup"><span data-stu-id="a7f02-3181">CDL</span></span> 
- <span data-ttu-id="a7f02-3182">CDL</span><span class="sxs-lookup"><span data-stu-id="a7f02-3182">CDLS</span></span> 
- <span data-ttu-id="a7f02-3183">ID</span><span class="sxs-lookup"><span data-stu-id="a7f02-3183">ID</span></span> 
- <span data-ttu-id="a7f02-3184">Id</span><span class="sxs-lookup"><span data-stu-id="a7f02-3184">IDs</span></span> 
- <span data-ttu-id="a7f02-3185">DL#</span><span class="sxs-lookup"><span data-stu-id="a7f02-3185">DL#</span></span> 
- <span data-ttu-id="a7f02-3186">
DLS#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3186">DLS#</span></span> 
- <span data-ttu-id="a7f02-3187">CDL#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3187">CDL#</span></span> 
- <span data-ttu-id="a7f02-3188">CDLS#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3188">CDLS#</span></span> 
- <span data-ttu-id="a7f02-3189">ID#</span><span class="sxs-lookup"><span data-stu-id="a7f02-3189">ID#</span></span>
- <span data-ttu-id="a7f02-3190">
IDs#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3190">IDs#</span></span> 
- <span data-ttu-id="a7f02-3191">ID 号</span><span class="sxs-lookup"><span data-stu-id="a7f02-3191">ID number</span></span> 
- <span data-ttu-id="a7f02-3192">ID numbers
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3192">ID numbers</span></span> 
- <span data-ttu-id="a7f02-3193">LIC</span><span class="sxs-lookup"><span data-stu-id="a7f02-3193">LIC</span></span> 
- <span data-ttu-id="a7f02-3194">LIC#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3194">LIC#</span></span> 

#### <a name="keywordusdriverslicense"></a><span data-ttu-id="a7f02-3195">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="a7f02-3195">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="a7f02-3196">DriverLic</span><span class="sxs-lookup"><span data-stu-id="a7f02-3196">DriverLic</span></span> 
- <span data-ttu-id="a7f02-3197">DriverLics</span><span class="sxs-lookup"><span data-stu-id="a7f02-3197">DriverLics</span></span> 
- <span data-ttu-id="a7f02-3198">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="a7f02-3198">DriverLicense</span></span> 
- <span data-ttu-id="a7f02-3199">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="a7f02-3199">DriverLicenses</span></span> 
- <span data-ttu-id="a7f02-3200">驱动程序 Lic</span><span class="sxs-lookup"><span data-stu-id="a7f02-3200">Driver Lic</span></span> 
- <span data-ttu-id="a7f02-3201">驱动程序 Lics</span><span class="sxs-lookup"><span data-stu-id="a7f02-3201">Driver Lics</span></span> 
- <span data-ttu-id="a7f02-3202">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="a7f02-3202">Driver License</span></span> 
- <span data-ttu-id="a7f02-3203">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="a7f02-3203">Driver Licenses</span></span> 
- <span data-ttu-id="a7f02-3204">DriversLic</span><span class="sxs-lookup"><span data-stu-id="a7f02-3204">DriversLic</span></span> 
- <span data-ttu-id="a7f02-3205">DriversLics</span><span class="sxs-lookup"><span data-stu-id="a7f02-3205">DriversLics</span></span> 
- <span data-ttu-id="a7f02-3206">驾驶员</span><span class="sxs-lookup"><span data-stu-id="a7f02-3206">DriversLicense</span></span> 
- <span data-ttu-id="a7f02-3207">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="a7f02-3207">DriversLicenses</span></span> 
- <span data-ttu-id="a7f02-3208">驱动因素 Lic</span><span class="sxs-lookup"><span data-stu-id="a7f02-3208">Drivers Lic</span></span> 
- <span data-ttu-id="a7f02-3209">驱动因素 Lics</span><span class="sxs-lookup"><span data-stu-id="a7f02-3209">Drivers Lics</span></span> 
- <span data-ttu-id="a7f02-3210">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="a7f02-3210">Drivers License</span></span> 
- <span data-ttu-id="a7f02-3211">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="a7f02-3211">Drivers Licenses</span></span> 
- <span data-ttu-id="a7f02-3212">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="a7f02-3212">Driver'Lic</span></span> 
- <span data-ttu-id="a7f02-3213">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="a7f02-3213">Driver'Lics</span></span> 
- <span data-ttu-id="a7f02-3214">Driver'License</span><span class="sxs-lookup"><span data-stu-id="a7f02-3214">Driver'License</span></span> 
- <span data-ttu-id="a7f02-3215">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="a7f02-3215">Driver'Licenses</span></span> 
- <span data-ttu-id="a7f02-3216">驱动因素 Lic</span><span class="sxs-lookup"><span data-stu-id="a7f02-3216">Driver' Lic</span></span> 
- <span data-ttu-id="a7f02-3217">驱动因素 Lics</span><span class="sxs-lookup"><span data-stu-id="a7f02-3217">Driver' Lics</span></span> 
- <span data-ttu-id="a7f02-3218">驱动因素许可证</span><span class="sxs-lookup"><span data-stu-id="a7f02-3218">Driver' License</span></span> 
- <span data-ttu-id="a7f02-3219">驱动因素许可证</span><span class="sxs-lookup"><span data-stu-id="a7f02-3219">Driver' Licenses</span></span>
- <span data-ttu-id="a7f02-3220">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="a7f02-3220">Driver'sLic</span></span> 
- <span data-ttu-id="a7f02-3221">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="a7f02-3221">Driver'sLics</span></span> 
- <span data-ttu-id="a7f02-3222">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="a7f02-3222">Driver'sLicense</span></span> 
- <span data-ttu-id="a7f02-3223">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="a7f02-3223">Driver'sLicenses</span></span> 
- <span data-ttu-id="a7f02-3224">驱动因素的 Lic</span><span class="sxs-lookup"><span data-stu-id="a7f02-3224">Driver's Lic</span></span> 
- <span data-ttu-id="a7f02-3225">驱动因素的 Lics</span><span class="sxs-lookup"><span data-stu-id="a7f02-3225">Driver's Lics</span></span> 
- <span data-ttu-id="a7f02-3226">驱动程序的许可证</span><span class="sxs-lookup"><span data-stu-id="a7f02-3226">Driver's License</span></span> 
- <span data-ttu-id="a7f02-3227">驱动程序的许可证</span><span class="sxs-lookup"><span data-stu-id="a7f02-3227">Driver's Licenses</span></span> 
- <span data-ttu-id="a7f02-3228">identification number
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3228">identification number</span></span> 
- <span data-ttu-id="a7f02-3229">identification numbers
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3229">identification numbers</span></span> 
- <span data-ttu-id="a7f02-3230">identification #
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3230">identification #</span></span> 
- <span data-ttu-id="a7f02-3231">身份证</span><span class="sxs-lookup"><span data-stu-id="a7f02-3231">id card</span></span> 
- <span data-ttu-id="a7f02-3232">id 卡</span><span class="sxs-lookup"><span data-stu-id="a7f02-3232">id cards</span></span> 
- <span data-ttu-id="a7f02-3233">身份证</span><span class="sxs-lookup"><span data-stu-id="a7f02-3233">identification card</span></span> 
- <span data-ttu-id="a7f02-3234">身份证</span><span class="sxs-lookup"><span data-stu-id="a7f02-3234">identification cards</span></span> 
- <span data-ttu-id="a7f02-3235">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="a7f02-3235">DriverLic#</span></span> 
- <span data-ttu-id="a7f02-3236">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="a7f02-3236">DriverLics#</span></span> 
- <span data-ttu-id="a7f02-3237">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="a7f02-3237">DriverLicense#</span></span> 
- <span data-ttu-id="a7f02-3238">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="a7f02-3238">DriverLicenses#</span></span> 
- <span data-ttu-id="a7f02-3239">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="a7f02-3239">Driver Lic#</span></span> 
- <span data-ttu-id="a7f02-3240">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3240">Driver Lics#</span></span> 
- <span data-ttu-id="a7f02-3241">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="a7f02-3241">Driver License#</span></span> 
- <span data-ttu-id="a7f02-3242">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="a7f02-3242">Driver Licenses#</span></span> 
- <span data-ttu-id="a7f02-3243">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="a7f02-3243">DriversLic#</span></span> 
- <span data-ttu-id="a7f02-3244">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="a7f02-3244">DriversLics#</span></span> 
- <span data-ttu-id="a7f02-3245">驾驶员 #</span><span class="sxs-lookup"><span data-stu-id="a7f02-3245">DriversLicense#</span></span> 
- <span data-ttu-id="a7f02-3246">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="a7f02-3246">DriversLicenses#</span></span> 
- <span data-ttu-id="a7f02-3247">驱动因素 Lic #</span><span class="sxs-lookup"><span data-stu-id="a7f02-3247">Drivers Lic#</span></span> 
- <span data-ttu-id="a7f02-3248">驱动因素 Lics #</span><span class="sxs-lookup"><span data-stu-id="a7f02-3248">Drivers Lics#</span></span> 
- <span data-ttu-id="a7f02-3249">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="a7f02-3249">Drivers License#</span></span> 
- <span data-ttu-id="a7f02-3250">驱动因素许可证 #</span><span class="sxs-lookup"><span data-stu-id="a7f02-3250">Drivers Licenses#</span></span> 
- <span data-ttu-id="a7f02-3251">Driver'Lic#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3251">Driver'Lic#</span></span> 
- <span data-ttu-id="a7f02-3252">Driver'Lics#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3252">Driver'Lics#</span></span> 
- <span data-ttu-id="a7f02-3253">Driver'License#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3253">Driver'License#</span></span> 
- <span data-ttu-id="a7f02-3254">Driver'Licenses#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3254">Driver'Licenses#</span></span> 
- <span data-ttu-id="a7f02-3255">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3255">Driver' Lic#</span></span> 
- <span data-ttu-id="a7f02-3256">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3256">Driver' Lics#</span></span> 
- <span data-ttu-id="a7f02-3257">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3257">Driver' License#</span></span> 
- <span data-ttu-id="a7f02-3258">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3258">Driver' Licenses#</span></span> 
- <span data-ttu-id="a7f02-3259">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="a7f02-3259">Driver'sLic#</span></span> 
- <span data-ttu-id="a7f02-3260">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="a7f02-3260">Driver'sLics#</span></span> 
- <span data-ttu-id="a7f02-3261">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="a7f02-3261">Driver'sLicense#</span></span> 
- <span data-ttu-id="a7f02-3262">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="a7f02-3262">Driver'sLicenses#</span></span> 
- <span data-ttu-id="a7f02-3263">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3263">Driver's Lic#</span></span> 
- <span data-ttu-id="a7f02-3264">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3264">Driver's Lics#</span></span> 
- <span data-ttu-id="a7f02-3265">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3265">Driver's License#</span></span> 
- <span data-ttu-id="a7f02-3266">Driver's Licenses#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3266">Driver's Licenses#</span></span> 
- <span data-ttu-id="a7f02-3267">id 卡 #</span><span class="sxs-lookup"><span data-stu-id="a7f02-3267">id card#</span></span> 
- <span data-ttu-id="a7f02-3268">id cards#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3268">id cards#</span></span> 
- <span data-ttu-id="a7f02-3269">identification card#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3269">identification card#</span></span> 
- <span data-ttu-id="a7f02-3270">identification cards#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3270">identification cards#</span></span> 


#### <a name="keywordstatenamedriverslicensename"></a><span data-ttu-id="a7f02-3271">Keyword_[state_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="a7f02-3271">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="a7f02-3272">州缩写（例如，“NY”）
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3272">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="a7f02-3273">州名称（例如，“New York”）
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3273">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="a7f02-3274">美国单独的纳税人标识号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="a7f02-3274">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-3275">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-3275">Format</span></span>

<span data-ttu-id="a7f02-3276">九个数字，以“9”开头，“7”或“8”作为第四个数字，可以采用空格或短划线格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-3276">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-3277">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-3277">Pattern</span></span>

<span data-ttu-id="a7f02-3278">有格式模式：</span><span class="sxs-lookup"><span data-stu-id="a7f02-3278">Formatted:</span></span>
- <span data-ttu-id="a7f02-3279">数字“9”</span><span class="sxs-lookup"><span data-stu-id="a7f02-3279">The digit "9"</span></span> 
- <span data-ttu-id="a7f02-3280">两位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-3280">Two digits</span></span> 
- <span data-ttu-id="a7f02-3281">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="a7f02-3281">A space or dash</span></span> 
- <span data-ttu-id="a7f02-3282">“7”或“8”</span><span class="sxs-lookup"><span data-stu-id="a7f02-3282">A "7" or "8"</span></span> 
- <span data-ttu-id="a7f02-3283">一位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-3283">A digit</span></span> 
- <span data-ttu-id="a7f02-3284">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="a7f02-3284">A space, or dash</span></span> 
- <span data-ttu-id="a7f02-3285">四位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-3285">Four digits</span></span>

<span data-ttu-id="a7f02-3286">无格式模式：</span><span class="sxs-lookup"><span data-stu-id="a7f02-3286">Unformatted:</span></span>
- <span data-ttu-id="a7f02-3287">数字“9”</span><span class="sxs-lookup"><span data-stu-id="a7f02-3287">The digit "9"</span></span> 
- <span data-ttu-id="a7f02-3288">两位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-3288">Two digits</span></span> 
- <span data-ttu-id="a7f02-3289">“7”或“8”</span><span class="sxs-lookup"><span data-stu-id="a7f02-3289">A "7" or "8"</span></span> 
- <span data-ttu-id="a7f02-3290">五位数字</span><span class="sxs-lookup"><span data-stu-id="a7f02-3290">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-3291">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-3291">Checksum</span></span>

<span data-ttu-id="a7f02-3292">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-3292">No</span></span>

### <a name="definition"></a><span data-ttu-id="a7f02-3293">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-3293">Definition</span></span>

<span data-ttu-id="a7f02-3294">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-3294">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-3295">函数 Func_formatted_itin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3295">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-3296">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="a7f02-3296">At least one of the following is true:</span></span>
    - <span data-ttu-id="a7f02-3297">找到 Keyword_itin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3297">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="a7f02-3298">函数 Func_us_address 找到正确日期格式的地址。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3298">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="a7f02-3299">函数 Func_us_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3299">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="a7f02-3300">找到 Keyword_itin_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3300">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="a7f02-3301">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-3301">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-3302">函数 Func_unformatted_itin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3302">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-3303">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="a7f02-3303">At least one of the following is true:</span></span>
    - <span data-ttu-id="a7f02-3304">找到 Keyword_itin_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3304">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="a7f02-3305">函数 Func_us_address 找到正确日期格式的地址。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3305">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="a7f02-3306">函数 Func_us_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3306">The function Func_us_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-3307">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-3307">Keywords</span></span>

#### <a name="keyworditin"></a><span data-ttu-id="a7f02-3308">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="a7f02-3308">Keyword_itin</span></span>

- <span data-ttu-id="a7f02-3309">taxpayer
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3309">taxpayer</span></span> 
- <span data-ttu-id="a7f02-3310">tax id
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3310">tax id</span></span> 
- <span data-ttu-id="a7f02-3311">tax identification
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3311">tax identification</span></span> 
- <span data-ttu-id="a7f02-3312">itin
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3312">itin</span></span> 
- <span data-ttu-id="a7f02-3313">ssn</span><span class="sxs-lookup"><span data-stu-id="a7f02-3313">ssn</span></span> 
- <span data-ttu-id="a7f02-3314">tin
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3314">tin</span></span> 
- <span data-ttu-id="a7f02-3315">社会安全</span><span class="sxs-lookup"><span data-stu-id="a7f02-3315">social security</span></span> 
- <span data-ttu-id="a7f02-3316">tax payer
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3316">tax payer</span></span> 
- <span data-ttu-id="a7f02-3317">itins
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3317">itins</span></span> 
- <span data-ttu-id="a7f02-3318">taxid

</span><span class="sxs-lookup"><span data-stu-id="a7f02-3318">taxid</span></span> 
- <span data-ttu-id="a7f02-3319">individual taxpayer
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3319">individual taxpayer</span></span> 

#### <a name="keyworditincollaborative"></a><span data-ttu-id="a7f02-3320">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="a7f02-3320">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="a7f02-3321">License</span><span class="sxs-lookup"><span data-stu-id="a7f02-3321">License</span></span> 
- <span data-ttu-id="a7f02-3322">DL</span><span class="sxs-lookup"><span data-stu-id="a7f02-3322">DL</span></span> 
- <span data-ttu-id="a7f02-3323">DOB
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3323">DOB</span></span> 
- <span data-ttu-id="a7f02-3324">出生日期</span><span class="sxs-lookup"><span data-stu-id="a7f02-3324">Birthdate</span></span> 
- <span data-ttu-id="a7f02-3325">生日 </span><span class="sxs-lookup"><span data-stu-id="a7f02-3325">Birthday</span></span> 
- <span data-ttu-id="a7f02-3326">Date of Birth
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3326">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="a7f02-3327">美国社会保险号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="a7f02-3327">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="a7f02-3328">格式</span><span class="sxs-lookup"><span data-stu-id="a7f02-3328">Format</span></span>

<span data-ttu-id="a7f02-3329">9 个数字，可以是格式化模式，也可以是非格式化模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-3329">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="a7f02-3330">如果在 2011 年中旬前发布，则 SSN 具有强格式，即数字的某部分必须介于某个有效的范围中（但是没有校验和）。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3330">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="a7f02-3331">模式</span><span class="sxs-lookup"><span data-stu-id="a7f02-3331">Pattern</span></span>

<span data-ttu-id="a7f02-3332">四种不同模式中的 SSN 的四种函数外观：</span><span class="sxs-lookup"><span data-stu-id="a7f02-3332">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="a7f02-3333">Func_ssn 查找具有 2011 年以前使用短划线或空格格式化的强格式的 SSN（ddd-dd-dddd 或 ddd dd dddd）</span><span class="sxs-lookup"><span data-stu-id="a7f02-3333">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="a7f02-3334">Func_unformatted_ssn 查找具有 2011 年以前未格式化为 9 个连续数字的强格式的 SSN (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="a7f02-3334">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="a7f02-3335">Func_randomized_formatted_ssn 查找 2011 年后使用短划线或空格（ddd-dd-dddd 或 ddd dd dddd）格式化的 SSN</span><span class="sxs-lookup"><span data-stu-id="a7f02-3335">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="a7f02-3336">Func_randomized_unformatted_ssn 查找 2011 年后未格式化为 9 个连续数字 (ddddddddd) 的 SSN</span><span class="sxs-lookup"><span data-stu-id="a7f02-3336">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="a7f02-3337">校验和</span><span class="sxs-lookup"><span data-stu-id="a7f02-3337">Checksum</span></span>

<span data-ttu-id="a7f02-3338">否</span><span class="sxs-lookup"><span data-stu-id="a7f02-3338">No</span></span>


### <a name="definition"></a><span data-ttu-id="a7f02-3339">定义</span><span class="sxs-lookup"><span data-stu-id="a7f02-3339">Definition</span></span>

<span data-ttu-id="a7f02-3340">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-3340">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-3341">函数 Func_ssn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3341">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-3342">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3342">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="a7f02-3343">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-3343">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-3344">函数 Func_unformatted_ssn 查找与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3344">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-3345">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3345">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="a7f02-3346">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-3346">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-3347">函数 Func_randomized_formatted_ssn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3347">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-3348">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3348">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="a7f02-3349">函数 Func_ssn 未找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3349">The function Func_ssn does not find content that matches the pattern.</span></span>

<span data-ttu-id="a7f02-3350">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 55% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a7f02-3350">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a7f02-3351">函数 Func_randomized_unformatted_ssn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3351">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="a7f02-3352">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3352">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="a7f02-3353">函数 Func_unformatted_ssn 未找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a7f02-3353">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a7f02-3354">关键字</span><span class="sxs-lookup"><span data-stu-id="a7f02-3354">Keywords</span></span>

#### <a name="keywordssn"></a><span data-ttu-id="a7f02-3355">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="a7f02-3355">Keyword_ssn</span></span>

- <span data-ttu-id="a7f02-3356">Social Security
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3356">Social Security</span></span> 
- <span data-ttu-id="a7f02-3357">Social Security#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3357">Social Security#</span></span> 
- <span data-ttu-id="a7f02-3358">Soc Sec
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3358">Soc Sec</span></span> 
- <span data-ttu-id="a7f02-3359">SSN</span><span class="sxs-lookup"><span data-stu-id="a7f02-3359">SSN</span></span> 
- <span data-ttu-id="a7f02-3360">SSNS
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3360">SSNS</span></span> 
- <span data-ttu-id="a7f02-3361">SSN#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3361">SSN#</span></span> 
- <span data-ttu-id="a7f02-3362">SS#
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3362">SS#</span></span> 
- <span data-ttu-id="a7f02-3363">SSID
</span><span class="sxs-lookup"><span data-stu-id="a7f02-3363">SSID</span></span> 
   

