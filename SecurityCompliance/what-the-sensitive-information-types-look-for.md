---
title: 使用敏感信息类型查找什么
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 05/20/2019
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Office 365 安全&amp;合规中心中的数据丢失防护 (DLP) 包括可供您在 DLP 策略中使用的80敏感信息类型。 本主题列出了所有这些敏感信息类型，并显示 DLP 策略在检测到每种类型时查找的内容。
ms.openlocfilehash: 1e1aeea164c15bb64c6040f7821bf006ee8ff42f
ms.sourcegitcommit: b8737e52724a343d99082961bc113bba819d5681
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34247295"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="484f6-104">使用敏感信息类型查找什么</span><span class="sxs-lookup"><span data-stu-id="484f6-104">What the sensitive information types look for</span></span>

<span data-ttu-id="484f6-105">Office 365 安全&amp;合规中心中的数据丢失防护 (DLP) 包括许多可供您在 DLP 策略中使用的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="484f6-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="484f6-106">本主题列出了所有这些敏感信息类型，并显示 DLP 策略在检测到每种类型时查找的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="484f6-107">敏感信息类型通过正则表达式或函数可以识别的模式定义。</span><span class="sxs-lookup"><span data-stu-id="484f6-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="484f6-108">此外，关键字和校验和等确凿的证据可用于识别敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="484f6-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="484f6-109">可信度和相似度也会在评估过程中使用。</span><span class="sxs-lookup"><span data-stu-id="484f6-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="484f6-110">ABA 银行代号</span><span class="sxs-lookup"><span data-stu-id="484f6-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-111">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-111">Format</span></span>

<span data-ttu-id="484f6-112">9 个数字，可以是格式化模式，也可以是非格式化模式 </span><span class="sxs-lookup"><span data-stu-id="484f6-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-113">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-113">Pattern</span></span>

<span data-ttu-id="484f6-114">格式</span><span class="sxs-lookup"><span data-stu-id="484f6-114">Formatted:</span></span>
- <span data-ttu-id="484f6-115">四个数字，以 0、 1、 2、 3、 6、 7 或 8 开头</span><span class="sxs-lookup"><span data-stu-id="484f6-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="484f6-116">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="484f6-116">A hyphen</span></span>
- <span data-ttu-id="484f6-117">四个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-117">Four digits</span></span>
- <span data-ttu-id="484f6-118">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="484f6-118">A hyphen</span></span>
- <span data-ttu-id="484f6-119">一个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-119">A digit</span></span>

<span data-ttu-id="484f6-120">无格式: 9 个连续的数字, 以0、1、2、3、6、7或8开头</span><span class="sxs-lookup"><span data-stu-id="484f6-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="484f6-121">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-121">Checksum</span></span>

<span data-ttu-id="484f6-122">否</span><span class="sxs-lookup"><span data-stu-id="484f6-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-123">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-123">Definition</span></span>

<span data-ttu-id="484f6-124">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-125">函数 Func_aba_routing 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-126">找到 Keyword_ABA_Routing 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="484f6-127">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-127">Keywords</span></span>

#### <a name="keywordabarouting"></a><span data-ttu-id="484f6-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="484f6-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="484f6-129">aba</span><span class="sxs-lookup"><span data-stu-id="484f6-129">aba</span></span>
- <span data-ttu-id="484f6-130">aba #</span><span class="sxs-lookup"><span data-stu-id="484f6-130">aba #</span></span>
- <span data-ttu-id="484f6-131">aba routing #</span><span class="sxs-lookup"><span data-stu-id="484f6-131">aba routing #</span></span>
- <span data-ttu-id="484f6-132">aba routing number</span><span class="sxs-lookup"><span data-stu-id="484f6-132">aba routing number</span></span>
- <span data-ttu-id="484f6-133">aba</span><span class="sxs-lookup"><span data-stu-id="484f6-133">aba#</span></span>
- <span data-ttu-id="484f6-134">abarouting#</span><span class="sxs-lookup"><span data-stu-id="484f6-134">abarouting#</span></span>
- <span data-ttu-id="484f6-135">aba number</span><span class="sxs-lookup"><span data-stu-id="484f6-135">aba number</span></span>
- <span data-ttu-id="484f6-136">abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="484f6-136">abaroutingnumber</span></span>
- <span data-ttu-id="484f6-137">american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="484f6-137">american bank association routing #</span></span>
- <span data-ttu-id="484f6-138">american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="484f6-138">american bank association routing number</span></span>
- <span data-ttu-id="484f6-139">americanbankassociationrouting#</span><span class="sxs-lookup"><span data-stu-id="484f6-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="484f6-140">americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="484f6-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="484f6-141">bank routing number</span><span class="sxs-lookup"><span data-stu-id="484f6-141">bank routing number</span></span>
- <span data-ttu-id="484f6-142">bankrouting#</span><span class="sxs-lookup"><span data-stu-id="484f6-142">bankrouting#</span></span>
- <span data-ttu-id="484f6-143">bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="484f6-143">bankroutingnumber</span></span>
- <span data-ttu-id="484f6-144">routing transit number</span><span class="sxs-lookup"><span data-stu-id="484f6-144">routing transit number</span></span>
- <span data-ttu-id="484f6-145">RTN</span><span class="sxs-lookup"><span data-stu-id="484f6-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="484f6-146">阿根廷国家身份证 (DNI) 号</span><span class="sxs-lookup"><span data-stu-id="484f6-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-147">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-147">Format</span></span>

<span data-ttu-id="484f6-148">八个数字，用点分隔</span><span class="sxs-lookup"><span data-stu-id="484f6-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-149">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-149">Pattern</span></span>

<span data-ttu-id="484f6-150">八个数字：</span><span class="sxs-lookup"><span data-stu-id="484f6-150">Eight digits:</span></span>
- <span data-ttu-id="484f6-151">两个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-151">Two digits</span></span>
- <span data-ttu-id="484f6-152">一个点 </span><span class="sxs-lookup"><span data-stu-id="484f6-152">A period</span></span>
- <span data-ttu-id="484f6-153">三个数字 </span><span class="sxs-lookup"><span data-stu-id="484f6-153">Three digits</span></span>
- <span data-ttu-id="484f6-154">一个点 </span><span class="sxs-lookup"><span data-stu-id="484f6-154">A period</span></span>
- <span data-ttu-id="484f6-155">三位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-156">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-156">Checksum</span></span>

<span data-ttu-id="484f6-157">否</span><span class="sxs-lookup"><span data-stu-id="484f6-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-158">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-158">Definition</span></span>

<span data-ttu-id="484f6-159">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-160">正则表达式 Regex_argentina_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-161">找到 Keyword_argentina_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="484f6-162">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-162">Keywords</span></span>

#### <a name="keywordargentinanationalid"></a><span data-ttu-id="484f6-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="484f6-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="484f6-164">Argentina National Identity number</span><span class="sxs-lookup"><span data-stu-id="484f6-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="484f6-165">标识</span><span class="sxs-lookup"><span data-stu-id="484f6-165">Identity</span></span> 
- <span data-ttu-id="484f6-166">标识国家/地区身份卡片</span><span class="sxs-lookup"><span data-stu-id="484f6-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="484f6-167">DNI</span><span class="sxs-lookup"><span data-stu-id="484f6-167">DNI</span></span> 
- <span data-ttu-id="484f6-168">个人的网络国家注册表</span><span class="sxs-lookup"><span data-stu-id="484f6-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="484f6-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="484f6-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="484f6-170">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="484f6-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="484f6-171">Identidad</span><span class="sxs-lookup"><span data-stu-id="484f6-171">Identidad</span></span> 
- <span data-ttu-id="484f6-172">Identificación</span><span class="sxs-lookup"><span data-stu-id="484f6-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="484f6-173">澳大利亚银行帐号</span><span class="sxs-lookup"><span data-stu-id="484f6-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-174">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-174">Format</span></span>

<span data-ttu-id="484f6-175">6-10 个数字，带或不带 BSB 号码 </span><span class="sxs-lookup"><span data-stu-id="484f6-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-176">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-176">Pattern</span></span>

<span data-ttu-id="484f6-177">帐号为 6-10 个数字。</span><span class="sxs-lookup"><span data-stu-id="484f6-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="484f6-178">澳大利亚银行州级分部编号：</span><span class="sxs-lookup"><span data-stu-id="484f6-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="484f6-179">三个数字 </span><span class="sxs-lookup"><span data-stu-id="484f6-179">Three digits</span></span> 
- <span data-ttu-id="484f6-180">连字符</span><span class="sxs-lookup"><span data-stu-id="484f6-180">A hyphen</span></span> 
- <span data-ttu-id="484f6-181">三位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-182">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-182">Checksum</span></span>

<span data-ttu-id="484f6-183">否</span><span class="sxs-lookup"><span data-stu-id="484f6-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-184">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-184">Definition</span></span>

<span data-ttu-id="484f6-185">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-186">正则表达式 Regex_australia_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="484f6-187">找到 Keyword_australia_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="484f6-188">正则表达式 Regex_australia_bank_account_number_bsb 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="484f6-189">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-190">正则表达式 Regex_australia_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="484f6-191">找到 Keyword_australia_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-192">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-192">Keywords</span></span>

#### <a name="keywordaustraliabankaccountnumber"></a><span data-ttu-id="484f6-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="484f6-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="484f6-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="484f6-194">swift bank code</span></span>
- <span data-ttu-id="484f6-195">correspondent bank</span><span class="sxs-lookup"><span data-stu-id="484f6-195">correspondent bank</span></span>
- <span data-ttu-id="484f6-196">base currency</span><span class="sxs-lookup"><span data-stu-id="484f6-196">base currency</span></span>
- <span data-ttu-id="484f6-197">usa account</span><span class="sxs-lookup"><span data-stu-id="484f6-197">usa account</span></span>
- <span data-ttu-id="484f6-198">holder address</span><span class="sxs-lookup"><span data-stu-id="484f6-198">holder address</span></span>
- <span data-ttu-id="484f6-199">bank address</span><span class="sxs-lookup"><span data-stu-id="484f6-199">bank address</span></span>
- <span data-ttu-id="484f6-200">information account</span><span class="sxs-lookup"><span data-stu-id="484f6-200">information account</span></span>
- <span data-ttu-id="484f6-201">fund transfers</span><span class="sxs-lookup"><span data-stu-id="484f6-201">fund transfers</span></span>
- <span data-ttu-id="484f6-202">bank charges</span><span class="sxs-lookup"><span data-stu-id="484f6-202">bank charges</span></span>
- <span data-ttu-id="484f6-203">bank details</span><span class="sxs-lookup"><span data-stu-id="484f6-203">bank details</span></span>
- <span data-ttu-id="484f6-204">banking information</span><span class="sxs-lookup"><span data-stu-id="484f6-204">banking information</span></span>
- <span data-ttu-id="484f6-205">full names</span><span class="sxs-lookup"><span data-stu-id="484f6-205">full names</span></span>
- <span data-ttu-id="484f6-206">iaea</span><span class="sxs-lookup"><span data-stu-id="484f6-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="484f6-207">澳大利亚驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="484f6-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-208">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-208">Format</span></span>

<span data-ttu-id="484f6-209">九个字母和数字</span><span class="sxs-lookup"><span data-stu-id="484f6-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-210">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-210">Pattern</span></span>

<span data-ttu-id="484f6-211">九个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="484f6-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="484f6-212">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="484f6-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="484f6-213">两位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-213">Two digits</span></span> 
- <span data-ttu-id="484f6-214">五位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="484f6-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="484f6-215">OR</span><span class="sxs-lookup"><span data-stu-id="484f6-215">OR</span></span>

- <span data-ttu-id="484f6-216">1-2 个可选字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="484f6-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="484f6-217">4-9 位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-217">4-9 digits</span></span>

<span data-ttu-id="484f6-218">OR</span><span class="sxs-lookup"><span data-stu-id="484f6-218">OR</span></span>

- <span data-ttu-id="484f6-219">九个数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="484f6-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-220">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-220">Checksum</span></span>

<span data-ttu-id="484f6-221">否</span><span class="sxs-lookup"><span data-stu-id="484f6-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-222">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-222">Definition</span></span>

<span data-ttu-id="484f6-223">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-224">正则表达式 Regex_australia_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-225">找到 Keyword_australia_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="484f6-226">未找到 Keyword_australia_drivers_license_number_exclusions 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-227">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-227">Keywords</span></span>

#### <a name="keywordaustraliadriverslicensenumber"></a><span data-ttu-id="484f6-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="484f6-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="484f6-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="484f6-229">international driving permits</span></span>
- <span data-ttu-id="484f6-230">australian automobile association</span><span class="sxs-lookup"><span data-stu-id="484f6-230">australian automobile association</span></span>
- <span data-ttu-id="484f6-231">international driving permit</span><span class="sxs-lookup"><span data-stu-id="484f6-231">international driving permit</span></span>
- <span data-ttu-id="484f6-232">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="484f6-232">DriverLicence</span></span>
- <span data-ttu-id="484f6-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="484f6-233">DriverLicences</span></span>
- <span data-ttu-id="484f6-234">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="484f6-234">Driver Lic</span></span>
- <span data-ttu-id="484f6-235">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="484f6-235">Driver Licence</span></span>
- <span data-ttu-id="484f6-236">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="484f6-236">Driver Licences</span></span>
- <span data-ttu-id="484f6-237">DriversLic</span><span class="sxs-lookup"><span data-stu-id="484f6-237">DriversLic</span></span>
- <span data-ttu-id="484f6-238">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="484f6-238">DriversLicence</span></span>
- <span data-ttu-id="484f6-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="484f6-239">DriversLicences</span></span>
- <span data-ttu-id="484f6-240">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="484f6-240">Drivers Lic</span></span>
- <span data-ttu-id="484f6-241">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="484f6-241">Drivers Lics</span></span>
- <span data-ttu-id="484f6-242">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="484f6-242">Drivers Licence</span></span>
- <span data-ttu-id="484f6-243">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="484f6-243">Drivers Licences</span></span>
- <span data-ttu-id="484f6-244">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="484f6-244">Driver'Lic</span></span>
- <span data-ttu-id="484f6-245">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="484f6-245">Driver'Lics</span></span>
- <span data-ttu-id="484f6-246">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="484f6-246">Driver'Licence</span></span>
- <span data-ttu-id="484f6-247">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="484f6-247">Driver'Licences</span></span>
- <span data-ttu-id="484f6-248">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="484f6-248">Driver' Lic</span></span>
- <span data-ttu-id="484f6-249">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="484f6-249">Driver' Lics</span></span>
- <span data-ttu-id="484f6-250">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="484f6-250">Driver' Licence</span></span>
- <span data-ttu-id="484f6-251">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="484f6-251">Driver' Licences</span></span>
- <span data-ttu-id="484f6-252">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="484f6-252">Driver'sLic</span></span>
- <span data-ttu-id="484f6-253">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="484f6-253">Driver'sLics</span></span>
- <span data-ttu-id="484f6-254">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="484f6-254">Driver'sLicence</span></span>
- <span data-ttu-id="484f6-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="484f6-255">Driver'sLicences</span></span>
- <span data-ttu-id="484f6-256">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="484f6-256">Driver's Lic</span></span>
- <span data-ttu-id="484f6-257">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="484f6-257">Driver's Lics</span></span>
- <span data-ttu-id="484f6-258">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="484f6-258">Driver's Licence</span></span>
- <span data-ttu-id="484f6-259">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="484f6-259">Driver's Licences</span></span>
- <span data-ttu-id="484f6-260">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="484f6-260">DriverLic#</span></span>
- <span data-ttu-id="484f6-261">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="484f6-261">DriverLics#</span></span>
- <span data-ttu-id="484f6-262">DriverLicence#</span><span class="sxs-lookup"><span data-stu-id="484f6-262">DriverLicence#</span></span>
- <span data-ttu-id="484f6-263">DriverLicences#</span><span class="sxs-lookup"><span data-stu-id="484f6-263">DriverLicences#</span></span>
- <span data-ttu-id="484f6-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="484f6-264">Driver Lic#</span></span>
- <span data-ttu-id="484f6-265">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="484f6-265">Driver Lics#</span></span>
- <span data-ttu-id="484f6-266">Driver Licence#</span><span class="sxs-lookup"><span data-stu-id="484f6-266">Driver Licence#</span></span>
- <span data-ttu-id="484f6-267">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="484f6-267">Driver Licences#</span></span>
- <span data-ttu-id="484f6-268">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="484f6-268">DriversLic#</span></span>
- <span data-ttu-id="484f6-269">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="484f6-269">DriversLics#</span></span>
- <span data-ttu-id="484f6-270">DriversLicence#</span><span class="sxs-lookup"><span data-stu-id="484f6-270">DriversLicence#</span></span>
- <span data-ttu-id="484f6-271">DriversLicences#</span><span class="sxs-lookup"><span data-stu-id="484f6-271">DriversLicences#</span></span>
- <span data-ttu-id="484f6-272">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="484f6-272">Drivers Lic#</span></span>
- <span data-ttu-id="484f6-273">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="484f6-273">Drivers Lics#</span></span>
- <span data-ttu-id="484f6-274">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="484f6-274">Drivers Licence#</span></span>
- <span data-ttu-id="484f6-275">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="484f6-275">Drivers Licences#</span></span>
- <span data-ttu-id="484f6-276">Driver'Lic#</span><span class="sxs-lookup"><span data-stu-id="484f6-276">Driver'Lic#</span></span>
- <span data-ttu-id="484f6-277">Driver'Lics#</span><span class="sxs-lookup"><span data-stu-id="484f6-277">Driver'Lics#</span></span>
- <span data-ttu-id="484f6-278">Driver'Licence#</span><span class="sxs-lookup"><span data-stu-id="484f6-278">Driver'Licence#</span></span>
- <span data-ttu-id="484f6-279">Driver'Licences#</span><span class="sxs-lookup"><span data-stu-id="484f6-279">Driver'Licences#</span></span>
- <span data-ttu-id="484f6-280">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="484f6-280">Driver' Lic#</span></span>
- <span data-ttu-id="484f6-281">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="484f6-281">Driver' Lics#</span></span>
- <span data-ttu-id="484f6-282">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="484f6-282">Driver' Licence#</span></span>
- <span data-ttu-id="484f6-283">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="484f6-283">Driver' Licences#</span></span>
- <span data-ttu-id="484f6-284">Driver'sLic#</span><span class="sxs-lookup"><span data-stu-id="484f6-284">Driver'sLic#</span></span>
- <span data-ttu-id="484f6-285">Driver'sLics#</span><span class="sxs-lookup"><span data-stu-id="484f6-285">Driver'sLics#</span></span>
- <span data-ttu-id="484f6-286">Driver'sLicence#</span><span class="sxs-lookup"><span data-stu-id="484f6-286">Driver'sLicence#</span></span>
- <span data-ttu-id="484f6-287">Driver'sLicences#</span><span class="sxs-lookup"><span data-stu-id="484f6-287">Driver'sLicences#</span></span>
- <span data-ttu-id="484f6-288">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="484f6-288">Driver's Lic#</span></span>
- <span data-ttu-id="484f6-289">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="484f6-289">Driver's Lics#</span></span>
- <span data-ttu-id="484f6-290">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="484f6-290">Driver's Licence#</span></span>
- <span data-ttu-id="484f6-291">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="484f6-291">Driver's Licences#</span></span> 

#### <a name="keywordaustraliadriverslicensenumberexclusions"></a><span data-ttu-id="484f6-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="484f6-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="484f6-293">aaa</span><span class="sxs-lookup"><span data-stu-id="484f6-293">aaa</span></span>
- <span data-ttu-id="484f6-294">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="484f6-294">DriverLicense</span></span>
- <span data-ttu-id="484f6-295">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="484f6-295">DriverLicenses</span></span>
- <span data-ttu-id="484f6-296">Driver License</span><span class="sxs-lookup"><span data-stu-id="484f6-296">Driver License</span></span>
- <span data-ttu-id="484f6-297">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="484f6-297">Driver Licenses</span></span>
- <span data-ttu-id="484f6-298">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="484f6-298">DriversLicense</span></span>
- <span data-ttu-id="484f6-299">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="484f6-299">DriversLicenses</span></span>
- <span data-ttu-id="484f6-300">Drivers License</span><span class="sxs-lookup"><span data-stu-id="484f6-300">Drivers License</span></span>
- <span data-ttu-id="484f6-301">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="484f6-301">Drivers Licenses</span></span>
- <span data-ttu-id="484f6-302">Driver'License</span><span class="sxs-lookup"><span data-stu-id="484f6-302">Driver'License</span></span>
- <span data-ttu-id="484f6-303">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="484f6-303">Driver'Licenses</span></span>
- <span data-ttu-id="484f6-304">Driver' License</span><span class="sxs-lookup"><span data-stu-id="484f6-304">Driver' License</span></span>
- <span data-ttu-id="484f6-305">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="484f6-305">Driver' Licenses</span></span>
- <span data-ttu-id="484f6-306">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="484f6-306">Driver'sLicense</span></span>
- <span data-ttu-id="484f6-307">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="484f6-307">Driver'sLicenses</span></span>
- <span data-ttu-id="484f6-308">Driver's License</span><span class="sxs-lookup"><span data-stu-id="484f6-308">Driver's License</span></span>
- <span data-ttu-id="484f6-309">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="484f6-309">Driver's Licenses</span></span>
- <span data-ttu-id="484f6-310">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="484f6-310">DriverLicense#</span></span>
- <span data-ttu-id="484f6-311">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="484f6-311">DriverLicenses#</span></span>
- <span data-ttu-id="484f6-312">Driver License#</span><span class="sxs-lookup"><span data-stu-id="484f6-312">Driver License#</span></span>
- <span data-ttu-id="484f6-313">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="484f6-313">Driver Licenses#</span></span>
- <span data-ttu-id="484f6-314">DriversLicense#</span><span class="sxs-lookup"><span data-stu-id="484f6-314">DriversLicense#</span></span>
- <span data-ttu-id="484f6-315">DriversLicenses#</span><span class="sxs-lookup"><span data-stu-id="484f6-315">DriversLicenses#</span></span>
- <span data-ttu-id="484f6-316">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="484f6-316">Drivers License#</span></span>
- <span data-ttu-id="484f6-317">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="484f6-317">Drivers Licenses#</span></span>
- <span data-ttu-id="484f6-318">Driver'License#</span><span class="sxs-lookup"><span data-stu-id="484f6-318">Driver'License#</span></span>
- <span data-ttu-id="484f6-319">Driver'Licenses#</span><span class="sxs-lookup"><span data-stu-id="484f6-319">Driver'Licenses#</span></span>
- <span data-ttu-id="484f6-320">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="484f6-320">Driver' License#</span></span>
- <span data-ttu-id="484f6-321">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="484f6-321">Driver' Licenses#</span></span>
- <span data-ttu-id="484f6-322">Driver'sLicense#</span><span class="sxs-lookup"><span data-stu-id="484f6-322">Driver'sLicense#</span></span>
- <span data-ttu-id="484f6-323">Driver'sLicenses#</span><span class="sxs-lookup"><span data-stu-id="484f6-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="484f6-324">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="484f6-324">Driver's License#</span></span>
- <span data-ttu-id="484f6-325">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="484f6-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="484f6-326">澳大利亚医疗帐号</span><span class="sxs-lookup"><span data-stu-id="484f6-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-327">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-327">Format</span></span>

<span data-ttu-id="484f6-328">10-11 个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-329">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-329">Pattern</span></span>

<span data-ttu-id="484f6-330">10-11 个数字：</span><span class="sxs-lookup"><span data-stu-id="484f6-330">10-11 digits:</span></span>
- <span data-ttu-id="484f6-331">第一个数字范围为 2-6</span><span class="sxs-lookup"><span data-stu-id="484f6-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="484f6-332">第九个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="484f6-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="484f6-333">第十个数字是问题数字</span><span class="sxs-lookup"><span data-stu-id="484f6-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="484f6-334">第十一个数字（可选）是个人号码</span><span class="sxs-lookup"><span data-stu-id="484f6-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-335">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-335">Checksum</span></span>

<span data-ttu-id="484f6-336">是</span><span class="sxs-lookup"><span data-stu-id="484f6-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-337">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-337">Definition</span></span>

<span data-ttu-id="484f6-338">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-339">函数 Func_australian_medical_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-340">找到 Keyword_Australia_Medical_Account_Number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="484f6-341">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-341">The checksum passes.</span></span>

<span data-ttu-id="484f6-342">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-343">函数 Func_australian_medical_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-344">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-344">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-345">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-345">Keywords</span></span>

#### <a name="keywordaustraliamedicalaccountnumber"></a><span data-ttu-id="484f6-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="484f6-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="484f6-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="484f6-347">bank account details</span></span>
- <span data-ttu-id="484f6-348">medicare payments</span><span class="sxs-lookup"><span data-stu-id="484f6-348">medicare payments</span></span>
- <span data-ttu-id="484f6-349">mortgage account</span><span class="sxs-lookup"><span data-stu-id="484f6-349">mortgage account</span></span>
- <span data-ttu-id="484f6-350">bank payments</span><span class="sxs-lookup"><span data-stu-id="484f6-350">bank payments</span></span>
- <span data-ttu-id="484f6-351">information branch</span><span class="sxs-lookup"><span data-stu-id="484f6-351">information branch</span></span>
- <span data-ttu-id="484f6-352">credit card loan</span><span class="sxs-lookup"><span data-stu-id="484f6-352">credit card loan</span></span>
- <span data-ttu-id="484f6-353">department of human services</span><span class="sxs-lookup"><span data-stu-id="484f6-353">department of human services</span></span>
- <span data-ttu-id="484f6-354">local service</span><span class="sxs-lookup"><span data-stu-id="484f6-354">local service</span></span>
- <span data-ttu-id="484f6-355">medicare</span><span class="sxs-lookup"><span data-stu-id="484f6-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="484f6-356">澳大利亚护照号</span><span class="sxs-lookup"><span data-stu-id="484f6-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-357">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-357">Format</span></span>

<span data-ttu-id="484f6-358">一个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-359">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-359">Pattern</span></span>

<span data-ttu-id="484f6-360">一个字母（不区分大小写）后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-361">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-361">Checksum</span></span>

<span data-ttu-id="484f6-362">否</span><span class="sxs-lookup"><span data-stu-id="484f6-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-363">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-363">Definition</span></span>

<span data-ttu-id="484f6-364">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-365">正则表达式 Regex_australia_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-366">找到来自 Keyword_passport 或 Keyword_australia_passport_number 的关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-367">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-367">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="484f6-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="484f6-368">Keyword_passport</span></span>

- <span data-ttu-id="484f6-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="484f6-369">Passport Number</span></span>
- <span data-ttu-id="484f6-370">Passport No</span><span class="sxs-lookup"><span data-stu-id="484f6-370">Passport No</span></span>
- <span data-ttu-id="484f6-371">Passport #</span><span class="sxs-lookup"><span data-stu-id="484f6-371">Passport #</span></span>
- <span data-ttu-id="484f6-372">登记卡</span><span class="sxs-lookup"><span data-stu-id="484f6-372">Passport#</span></span>
- <span data-ttu-id="484f6-373">PassportID</span><span class="sxs-lookup"><span data-stu-id="484f6-373">PassportID</span></span>
- <span data-ttu-id="484f6-374">Passportno</span><span class="sxs-lookup"><span data-stu-id="484f6-374">Passportno</span></span>
- <span data-ttu-id="484f6-375">passportnumber</span><span class="sxs-lookup"><span data-stu-id="484f6-375">passportnumber</span></span>
- <span data-ttu-id="484f6-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="484f6-376">パスポート</span></span>
- <span data-ttu-id="484f6-377">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="484f6-377">パスポート番号</span></span>
- <span data-ttu-id="484f6-378">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="484f6-378">パスポートのNum</span></span>
- <span data-ttu-id="484f6-379">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="484f6-379">パスポート ＃</span></span> 
- <span data-ttu-id="484f6-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="484f6-380">Numéro de passeport</span></span>
- <span data-ttu-id="484f6-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="484f6-381">Passeport n °</span></span>
- <span data-ttu-id="484f6-382">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="484f6-382">Passeport Non</span></span>
- <span data-ttu-id="484f6-383">Passeport #</span><span class="sxs-lookup"><span data-stu-id="484f6-383">Passeport #</span></span>
- <span data-ttu-id="484f6-384">Passeport#</span><span class="sxs-lookup"><span data-stu-id="484f6-384">Passeport#</span></span>
- <span data-ttu-id="484f6-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="484f6-385">PasseportNon</span></span>
- <span data-ttu-id="484f6-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="484f6-386">Passeportn °</span></span>

#### <a name="keywordaustraliapassportnumber"></a><span data-ttu-id="484f6-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="484f6-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="484f6-388">登记卡</span><span class="sxs-lookup"><span data-stu-id="484f6-388">passport</span></span>
- <span data-ttu-id="484f6-389">passport details</span><span class="sxs-lookup"><span data-stu-id="484f6-389">passport details</span></span>
- <span data-ttu-id="484f6-390">immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="484f6-390">immigration and citizenship</span></span>
- <span data-ttu-id="484f6-391">commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="484f6-391">commonwealth of australia</span></span>
- <span data-ttu-id="484f6-392">department of immigration</span><span class="sxs-lookup"><span data-stu-id="484f6-392">department of immigration</span></span>
- <span data-ttu-id="484f6-393">residential address</span><span class="sxs-lookup"><span data-stu-id="484f6-393">residential address</span></span>
- <span data-ttu-id="484f6-394">department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="484f6-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="484f6-395">反之</span><span class="sxs-lookup"><span data-stu-id="484f6-395">visa</span></span>
- <span data-ttu-id="484f6-396">national identity card</span><span class="sxs-lookup"><span data-stu-id="484f6-396">national identity card</span></span>
- <span data-ttu-id="484f6-397">passport number</span><span class="sxs-lookup"><span data-stu-id="484f6-397">passport number</span></span>
- <span data-ttu-id="484f6-398">travel document</span><span class="sxs-lookup"><span data-stu-id="484f6-398">travel document</span></span>
- <span data-ttu-id="484f6-399">issuing authority</span><span class="sxs-lookup"><span data-stu-id="484f6-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="484f6-400">澳大利亚税号</span><span class="sxs-lookup"><span data-stu-id="484f6-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-401">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-401">Format</span></span>

<span data-ttu-id="484f6-402">8-9 个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-403">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-403">Pattern</span></span>

<span data-ttu-id="484f6-404">通常 8-9 位数字，显示中包含空格，如下所示：</span><span class="sxs-lookup"><span data-stu-id="484f6-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="484f6-405">三位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-405">Three digits</span></span> 
- <span data-ttu-id="484f6-406">可选空格</span><span class="sxs-lookup"><span data-stu-id="484f6-406">An optional space</span></span> 
- <span data-ttu-id="484f6-407">三位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-407">Three digits</span></span> 
- <span data-ttu-id="484f6-408">可选空格</span><span class="sxs-lookup"><span data-stu-id="484f6-408">An optional space</span></span> 
- <span data-ttu-id="484f6-409">2-3 位数字，最后一位数字是校验位</span><span class="sxs-lookup"><span data-stu-id="484f6-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-410">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-410">Checksum</span></span>

<span data-ttu-id="484f6-411">是</span><span class="sxs-lookup"><span data-stu-id="484f6-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-412">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-412">Definition</span></span>

<span data-ttu-id="484f6-413">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-414">函数 Func_australian_tax_file_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-415">未找到 Keyword_Australia_Tax_File_Number 或 Keyword_number_exclusions 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="484f6-416">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-416">The checksum passes.</span></span>

```
   <!-- Australia Tax File Number -->
    <Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Match idRef="Keyword_Australia_Tax_File_Number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_number_exclusions" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="484f6-417">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-417">Keywords</span></span>

#### <a name="keywordaustraliataxfilenumber"></a><span data-ttu-id="484f6-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="484f6-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="484f6-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="484f6-419">australian business number</span></span>
- <span data-ttu-id="484f6-420">marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="484f6-420">marginal tax rate</span></span>
- <span data-ttu-id="484f6-421">medicare levy</span><span class="sxs-lookup"><span data-stu-id="484f6-421">medicare levy</span></span>
- <span data-ttu-id="484f6-422">portfolio number</span><span class="sxs-lookup"><span data-stu-id="484f6-422">portfolio number</span></span>
- <span data-ttu-id="484f6-423">service veterans</span><span class="sxs-lookup"><span data-stu-id="484f6-423">service veterans</span></span>
- <span data-ttu-id="484f6-424">withholding tax</span><span class="sxs-lookup"><span data-stu-id="484f6-424">withholding tax</span></span>
- <span data-ttu-id="484f6-425">individual tax return</span><span class="sxs-lookup"><span data-stu-id="484f6-425">individual tax return</span></span>
- <span data-ttu-id="484f6-426">tax file number</span><span class="sxs-lookup"><span data-stu-id="484f6-426">tax file number</span></span>

#### <a name="keywordnumberexclusions"></a><span data-ttu-id="484f6-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="484f6-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="484f6-428">00000000</span><span class="sxs-lookup"><span data-stu-id="484f6-428">00000000</span></span>
- <span data-ttu-id="484f6-429">11111111</span><span class="sxs-lookup"><span data-stu-id="484f6-429">11111111</span></span>
- <span data-ttu-id="484f6-430">22222222</span><span class="sxs-lookup"><span data-stu-id="484f6-430">22222222</span></span>
- <span data-ttu-id="484f6-431">33333333</span><span class="sxs-lookup"><span data-stu-id="484f6-431">33333333</span></span>
- <span data-ttu-id="484f6-432">44444444</span><span class="sxs-lookup"><span data-stu-id="484f6-432">44444444</span></span>
- <span data-ttu-id="484f6-433">55555555</span><span class="sxs-lookup"><span data-stu-id="484f6-433">55555555</span></span>
- <span data-ttu-id="484f6-434">66666666</span><span class="sxs-lookup"><span data-stu-id="484f6-434">66666666</span></span>
- <span data-ttu-id="484f6-435">77777777</span><span class="sxs-lookup"><span data-stu-id="484f6-435">77777777</span></span>
- <span data-ttu-id="484f6-436">88888888</span><span class="sxs-lookup"><span data-stu-id="484f6-436">88888888</span></span>
- <span data-ttu-id="484f6-437">99999999</span><span class="sxs-lookup"><span data-stu-id="484f6-437">99999999</span></span>
- <span data-ttu-id="484f6-438">000000000</span><span class="sxs-lookup"><span data-stu-id="484f6-438">000000000</span></span>
- <span data-ttu-id="484f6-439">111111111</span><span class="sxs-lookup"><span data-stu-id="484f6-439">111111111</span></span>
- <span data-ttu-id="484f6-440">222222222</span><span class="sxs-lookup"><span data-stu-id="484f6-440">222222222</span></span>
- <span data-ttu-id="484f6-441">333333333</span><span class="sxs-lookup"><span data-stu-id="484f6-441">333333333</span></span>
- <span data-ttu-id="484f6-442">444444444</span><span class="sxs-lookup"><span data-stu-id="484f6-442">444444444</span></span>
- <span data-ttu-id="484f6-443">555555555</span><span class="sxs-lookup"><span data-stu-id="484f6-443">555555555</span></span>
- <span data-ttu-id="484f6-444">666666666</span><span class="sxs-lookup"><span data-stu-id="484f6-444">666666666</span></span>
- <span data-ttu-id="484f6-445">777777777</span><span class="sxs-lookup"><span data-stu-id="484f6-445">777777777</span></span>
- <span data-ttu-id="484f6-446">888888888</span><span class="sxs-lookup"><span data-stu-id="484f6-446">888888888</span></span>
- <span data-ttu-id="484f6-447">999999999</span><span class="sxs-lookup"><span data-stu-id="484f6-447">999999999</span></span>
- <span data-ttu-id="484f6-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="484f6-448">0000000000</span></span>
- <span data-ttu-id="484f6-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="484f6-449">1111111111</span></span>
- <span data-ttu-id="484f6-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="484f6-450">2222222222</span></span>
- <span data-ttu-id="484f6-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="484f6-451">3333333333</span></span>
- <span data-ttu-id="484f6-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="484f6-452">4444444444</span></span>
- <span data-ttu-id="484f6-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="484f6-453">5555555555</span></span>
- <span data-ttu-id="484f6-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="484f6-454">6666666666</span></span>
- <span data-ttu-id="484f6-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="484f6-455">7777777777</span></span>
- <span data-ttu-id="484f6-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="484f6-456">8888888888</span></span>
- <span data-ttu-id="484f6-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="484f6-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="484f6-458">Azure DocumentDB 身份验证密钥</span><span class="sxs-lookup"><span data-stu-id="484f6-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="484f6-459">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-459">Format</span></span>

<span data-ttu-id="484f6-460">字符串 "DocumentDb", 后跟下面模式中所示的字符和字符串。</span><span class="sxs-lookup"><span data-stu-id="484f6-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-461">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-461">Pattern</span></span>

- <span data-ttu-id="484f6-462">字符串 "DocumentDb"</span><span class="sxs-lookup"><span data-stu-id="484f6-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="484f6-463">介于3-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="484f6-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="484f6-464">大于号 (>)、等号 (=)、引号 (") 或撇号 (')</span><span class="sxs-lookup"><span data-stu-id="484f6-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="484f6-465">86字母、数字、数字、正斜杠 (/) 或加号 (+) 的任意组合</span><span class="sxs-lookup"><span data-stu-id="484f6-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="484f6-466">两个等号 (=)</span><span class="sxs-lookup"><span data-stu-id="484f6-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-467">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-467">Checksum</span></span>

<span data-ttu-id="484f6-468">否</span><span class="sxs-lookup"><span data-stu-id="484f6-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-469">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-469">Definition</span></span>

<span data-ttu-id="484f6-470">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-471">正则表达式 CEP_Regex_AzureDocumentDBAuthKey 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-472">正则表达式 CEP_CommonExampleKeywords**未**找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-473">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-473">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="484f6-474">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="484f6-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="484f6-475">(请注意, 从技术上讲, 此敏感信息类型通过使用正则表达式 (而不是关键字列表) 来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="484f6-476">尚未</span><span class="sxs-lookup"><span data-stu-id="484f6-476">contoso</span></span>
- <span data-ttu-id="484f6-477">送交</span><span class="sxs-lookup"><span data-stu-id="484f6-477">fabrikam</span></span>
- <span data-ttu-id="484f6-478">罗斯</span><span class="sxs-lookup"><span data-stu-id="484f6-478">northwind</span></span>
- <span data-ttu-id="484f6-479">沙盒</span><span class="sxs-lookup"><span data-stu-id="484f6-479">sandbox</span></span>
- <span data-ttu-id="484f6-480">onebox</span><span class="sxs-lookup"><span data-stu-id="484f6-480">onebox</span></span>
- <span data-ttu-id="484f6-481">localhost</span><span class="sxs-lookup"><span data-stu-id="484f6-481">localhost</span></span>
- <span data-ttu-id="484f6-482">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="484f6-482">127.0.0.1</span></span>
- <span data-ttu-id="484f6-483">testacs.</span><span class="sxs-lookup"><span data-stu-id="484f6-483">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="484f6-484">com</span><span class="sxs-lookup"><span data-stu-id="484f6-484">com</span></span>
- <span data-ttu-id="484f6-485">s-int。</span><span class="sxs-lookup"><span data-stu-id="484f6-485">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="484f6-486">netmeeting</span><span class="sxs-lookup"><span data-stu-id="484f6-486">net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="484f6-487">Azure IAAS 数据库连接字符串和 Azure SQL 连接字符串</span><span class="sxs-lookup"><span data-stu-id="484f6-487">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="484f6-488">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-488">Format</span></span>

<span data-ttu-id="484f6-489">字符串 "Server"、"server" 或 "data source", 后跟下面模式中所述的字符和字符串, 包括字符串 "cloudapp"。</span><span class="sxs-lookup"><span data-stu-id="484f6-489">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="484f6-490">com "或" cloudapp "。</span><span class="sxs-lookup"><span data-stu-id="484f6-490">com" or "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="484f6-491">net "或" database。</span><span class="sxs-lookup"><span data-stu-id="484f6-491">net" or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="484f6-492">net "和字符串" Password "或" password "或" pwd "。</span><span class="sxs-lookup"><span data-stu-id="484f6-492">net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-493">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-493">Pattern</span></span>

- <span data-ttu-id="484f6-494">字符串 "Server"、"server" 或 "data source"</span><span class="sxs-lookup"><span data-stu-id="484f6-494">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="484f6-495">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="484f6-495">0-2 whitespace characters</span></span>
- <span data-ttu-id="484f6-496">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="484f6-496">An equal sign (=)</span></span>
- <span data-ttu-id="484f6-497">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="484f6-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="484f6-498">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="484f6-498">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="484f6-499">字符串 "cloudapp"。</span><span class="sxs-lookup"><span data-stu-id="484f6-499">The string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="484f6-500">com "," cloudapp。</span><span class="sxs-lookup"><span data-stu-id="484f6-500">com", "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="484f6-501">net "或" database。</span><span class="sxs-lookup"><span data-stu-id="484f6-501">net", or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="484f6-502">netmeeting</span><span class="sxs-lookup"><span data-stu-id="484f6-502">net"</span></span>
- <span data-ttu-id="484f6-503">介于1-300 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="484f6-503">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="484f6-504">字符串 "Password"、"password" 或 "pwd"</span><span class="sxs-lookup"><span data-stu-id="484f6-504">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="484f6-505">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="484f6-505">0-2 whitespace characters</span></span>
- <span data-ttu-id="484f6-506">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="484f6-506">An equal sign (=)</span></span>
- <span data-ttu-id="484f6-507">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="484f6-507">0-2 whitespace characters</span></span>
- <span data-ttu-id="484f6-508">一个或多个不是分号 (;)、引号 (") 或撇号 (') 的字符</span><span class="sxs-lookup"><span data-stu-id="484f6-508">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="484f6-509">分号 (;)、引号 (") 或撇号 (')</span><span class="sxs-lookup"><span data-stu-id="484f6-509">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-510">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-510">Checksum</span></span>

<span data-ttu-id="484f6-511">否</span><span class="sxs-lookup"><span data-stu-id="484f6-511">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-512">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-512">Definition</span></span>

<span data-ttu-id="484f6-513">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-513">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-514">正则表达式 CEP_Regex_AzureConnectionString 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-514">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-515">正则表达式 CEP_CommonExampleKeywords**未**找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-515">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-516">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-516">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="484f6-517">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="484f6-517">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="484f6-518">(请注意, 从技术上讲, 此敏感信息类型通过使用正则表达式 (而不是关键字列表) 来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-518">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="484f6-519">尚未</span><span class="sxs-lookup"><span data-stu-id="484f6-519">contoso</span></span>
- <span data-ttu-id="484f6-520">送交</span><span class="sxs-lookup"><span data-stu-id="484f6-520">fabrikam</span></span>
- <span data-ttu-id="484f6-521">罗斯</span><span class="sxs-lookup"><span data-stu-id="484f6-521">northwind</span></span>
- <span data-ttu-id="484f6-522">沙盒</span><span class="sxs-lookup"><span data-stu-id="484f6-522">sandbox</span></span>
- <span data-ttu-id="484f6-523">onebox</span><span class="sxs-lookup"><span data-stu-id="484f6-523">onebox</span></span>
- <span data-ttu-id="484f6-524">localhost</span><span class="sxs-lookup"><span data-stu-id="484f6-524">localhost</span></span>
- <span data-ttu-id="484f6-525">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="484f6-525">127.0.0.1</span></span>
- <span data-ttu-id="484f6-526">testacs.</span><span class="sxs-lookup"><span data-stu-id="484f6-526">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="484f6-527">com</span><span class="sxs-lookup"><span data-stu-id="484f6-527">com</span></span>
- <span data-ttu-id="484f6-528">s-int。</span><span class="sxs-lookup"><span data-stu-id="484f6-528">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="484f6-529">netmeeting</span><span class="sxs-lookup"><span data-stu-id="484f6-529">net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="484f6-530">Azure IoT 连接字符串</span><span class="sxs-lookup"><span data-stu-id="484f6-530">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="484f6-531">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-531">Format</span></span>

<span data-ttu-id="484f6-532">字符串 "HostName", 后跟下面模式中所示的字符和字符串, 包括字符串 "azure 设备"。</span><span class="sxs-lookup"><span data-stu-id="484f6-532">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="484f6-533">net "和" SharedAccessKey "。</span><span class="sxs-lookup"><span data-stu-id="484f6-533">net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-534">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-534">Pattern</span></span>

- <span data-ttu-id="484f6-535">字符串 "HostName"</span><span class="sxs-lookup"><span data-stu-id="484f6-535">The string "HostName"</span></span>
- <span data-ttu-id="484f6-536">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="484f6-536">0-2 whitespace characters</span></span>
- <span data-ttu-id="484f6-537">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="484f6-537">An equal sign (=)</span></span>
- <span data-ttu-id="484f6-538">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="484f6-538">0-2 whitespace characters</span></span>
- <span data-ttu-id="484f6-539">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="484f6-539">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="484f6-540">字符串 "azure 设备。</span><span class="sxs-lookup"><span data-stu-id="484f6-540">The string "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="484f6-541">netmeeting</span><span class="sxs-lookup"><span data-stu-id="484f6-541">net"</span></span>
- <span data-ttu-id="484f6-542">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="484f6-542">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="484f6-543">字符串 "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="484f6-543">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="484f6-544">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="484f6-544">0-2 whitespace characters</span></span>
- <span data-ttu-id="484f6-545">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="484f6-545">An equal sign (=)</span></span>
- <span data-ttu-id="484f6-546">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="484f6-546">0-2 whitespace characters</span></span>
- <span data-ttu-id="484f6-547">43字母、数字、数字、正斜杠 (/) 或加号 (+) 的任意组合</span><span class="sxs-lookup"><span data-stu-id="484f6-547">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="484f6-548">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="484f6-548">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-549">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-549">Checksum</span></span>

<span data-ttu-id="484f6-550">否</span><span class="sxs-lookup"><span data-stu-id="484f6-550">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-551">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-551">Definition</span></span>

<span data-ttu-id="484f6-552">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-552">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-553">正则表达式 CEP_Regex_AzureIoTConnectionString 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-553">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-554">正则表达式 CEP_CommonExampleKeywords**未**找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-554">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-555">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-555">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="484f6-556">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="484f6-556">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="484f6-557">(请注意, 从技术上讲, 此敏感信息类型通过使用正则表达式 (而不是关键字列表) 来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-557">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="484f6-558">尚未</span><span class="sxs-lookup"><span data-stu-id="484f6-558">contoso</span></span>
- <span data-ttu-id="484f6-559">送交</span><span class="sxs-lookup"><span data-stu-id="484f6-559">fabrikam</span></span>
- <span data-ttu-id="484f6-560">罗斯</span><span class="sxs-lookup"><span data-stu-id="484f6-560">northwind</span></span>
- <span data-ttu-id="484f6-561">沙盒</span><span class="sxs-lookup"><span data-stu-id="484f6-561">sandbox</span></span>
- <span data-ttu-id="484f6-562">onebox</span><span class="sxs-lookup"><span data-stu-id="484f6-562">onebox</span></span>
- <span data-ttu-id="484f6-563">localhost</span><span class="sxs-lookup"><span data-stu-id="484f6-563">localhost</span></span>
- <span data-ttu-id="484f6-564">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="484f6-564">127.0.0.1</span></span>
- <span data-ttu-id="484f6-565">testacs.</span><span class="sxs-lookup"><span data-stu-id="484f6-565">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="484f6-566">com</span><span class="sxs-lookup"><span data-stu-id="484f6-566">com</span></span>
- <span data-ttu-id="484f6-567">s-int。</span><span class="sxs-lookup"><span data-stu-id="484f6-567">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="484f6-568">netmeeting</span><span class="sxs-lookup"><span data-stu-id="484f6-568">net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="484f6-569">Azure 发布设置密码</span><span class="sxs-lookup"><span data-stu-id="484f6-569">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="484f6-570">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-570">Format</span></span>

<span data-ttu-id="484f6-571">字符串 "userpwd =", 后跟一个字母数字字符串。</span><span class="sxs-lookup"><span data-stu-id="484f6-571">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-572">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-572">Pattern</span></span>

- <span data-ttu-id="484f6-573">字符串 "userpwd ="</span><span class="sxs-lookup"><span data-stu-id="484f6-573">The string "userpwd="</span></span>
- <span data-ttu-id="484f6-574">任何60小写字母或数字的组合</span><span class="sxs-lookup"><span data-stu-id="484f6-574">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="484f6-575">一个引号 (")</span><span class="sxs-lookup"><span data-stu-id="484f6-575">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-576">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-576">Checksum</span></span>

<span data-ttu-id="484f6-577">否</span><span class="sxs-lookup"><span data-stu-id="484f6-577">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-578">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-578">Definition</span></span>

<span data-ttu-id="484f6-579">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-580">正则表达式 CEP_Regex_AzurePublishSettingPasswords 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-580">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-581">正则表达式 CEP_CommonExampleKeywords**未**找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-581">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


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

### <a name="keywords"></a><span data-ttu-id="484f6-582">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-582">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="484f6-583">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="484f6-583">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="484f6-584">(请注意, 从技术上讲, 此敏感信息类型通过使用正则表达式 (而不是关键字列表) 来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-584">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="484f6-585">尚未</span><span class="sxs-lookup"><span data-stu-id="484f6-585">contoso</span></span>
- <span data-ttu-id="484f6-586">送交</span><span class="sxs-lookup"><span data-stu-id="484f6-586">fabrikam</span></span>
- <span data-ttu-id="484f6-587">罗斯</span><span class="sxs-lookup"><span data-stu-id="484f6-587">northwind</span></span>
- <span data-ttu-id="484f6-588">沙盒</span><span class="sxs-lookup"><span data-stu-id="484f6-588">sandbox</span></span>
- <span data-ttu-id="484f6-589">onebox</span><span class="sxs-lookup"><span data-stu-id="484f6-589">onebox</span></span>
- <span data-ttu-id="484f6-590">localhost</span><span class="sxs-lookup"><span data-stu-id="484f6-590">localhost</span></span>
- <span data-ttu-id="484f6-591">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="484f6-591">127.0.0.1</span></span>
- <span data-ttu-id="484f6-592">testacs.</span><span class="sxs-lookup"><span data-stu-id="484f6-592">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="484f6-593">com</span><span class="sxs-lookup"><span data-stu-id="484f6-593">com</span></span>
- <span data-ttu-id="484f6-594">s-int。</span><span class="sxs-lookup"><span data-stu-id="484f6-594">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="484f6-595">netmeeting</span><span class="sxs-lookup"><span data-stu-id="484f6-595">net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="484f6-596">Azure Redis 缓存连接字符串</span><span class="sxs-lookup"><span data-stu-id="484f6-596">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="484f6-597">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-597">Format</span></span>

<span data-ttu-id="484f6-598">字符串 "redis"。</span><span class="sxs-lookup"><span data-stu-id="484f6-598">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="484f6-599">net ", 后跟下面的模式中所述的字符和字符串, 包括字符串" password "或" pwd "。</span><span class="sxs-lookup"><span data-stu-id="484f6-599">net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-600">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-600">Pattern</span></span>

- <span data-ttu-id="484f6-601">字符串 "redis"。</span><span class="sxs-lookup"><span data-stu-id="484f6-601">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="484f6-602">netmeeting</span><span class="sxs-lookup"><span data-stu-id="484f6-602">net"</span></span>
- <span data-ttu-id="484f6-603">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="484f6-603">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="484f6-604">字符串 "password" 或 "pwd"</span><span class="sxs-lookup"><span data-stu-id="484f6-604">The string "password" or "pwd"</span></span>
- <span data-ttu-id="484f6-605">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="484f6-605">0-2 whitespace characters</span></span>
- <span data-ttu-id="484f6-606">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="484f6-606">An equal sign (=)</span></span>
- <span data-ttu-id="484f6-607">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="484f6-607">0-2 whitespace characters</span></span>
- <span data-ttu-id="484f6-608">43个字符的任意组合, 这些字符为小写字母、数字、斜杠 (/) 或加号 (+)</span><span class="sxs-lookup"><span data-stu-id="484f6-608">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="484f6-609">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="484f6-609">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-610">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-610">Checksum</span></span>

<span data-ttu-id="484f6-611">否</span><span class="sxs-lookup"><span data-stu-id="484f6-611">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-612">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-612">Definition</span></span>

<span data-ttu-id="484f6-613">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-614">正则表达式 CEP_Regex_AzureRedisCacheConnectionString 找到与该模式匹配的内容。。</span><span class="sxs-lookup"><span data-stu-id="484f6-614">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="484f6-615">正则表达式 CEP_CommonExampleKeywords**未**找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-615">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-616">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-616">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="484f6-617">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="484f6-617">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="484f6-618">(请注意, 从技术上讲, 此敏感信息类型通过使用正则表达式 (而不是关键字列表) 来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-618">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="484f6-619">尚未</span><span class="sxs-lookup"><span data-stu-id="484f6-619">contoso</span></span>
- <span data-ttu-id="484f6-620">送交</span><span class="sxs-lookup"><span data-stu-id="484f6-620">fabrikam</span></span>
- <span data-ttu-id="484f6-621">罗斯</span><span class="sxs-lookup"><span data-stu-id="484f6-621">northwind</span></span>
- <span data-ttu-id="484f6-622">沙盒</span><span class="sxs-lookup"><span data-stu-id="484f6-622">sandbox</span></span>
- <span data-ttu-id="484f6-623">onebox</span><span class="sxs-lookup"><span data-stu-id="484f6-623">onebox</span></span>
- <span data-ttu-id="484f6-624">localhost</span><span class="sxs-lookup"><span data-stu-id="484f6-624">localhost</span></span>
- <span data-ttu-id="484f6-625">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="484f6-625">127.0.0.1</span></span>
- <span data-ttu-id="484f6-626">testacs.</span><span class="sxs-lookup"><span data-stu-id="484f6-626">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="484f6-627">com</span><span class="sxs-lookup"><span data-stu-id="484f6-627">com</span></span>
- <span data-ttu-id="484f6-628">s-int。</span><span class="sxs-lookup"><span data-stu-id="484f6-628">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="484f6-629">netmeeting</span><span class="sxs-lookup"><span data-stu-id="484f6-629">net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="484f6-630">Azure SA</span><span class="sxs-lookup"><span data-stu-id="484f6-630">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="484f6-631">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-631">Format</span></span>

<span data-ttu-id="484f6-632">字符串 "sig", 后跟下面模式中所示的字符和字符串。</span><span class="sxs-lookup"><span data-stu-id="484f6-632">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-633">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-633">Pattern</span></span>

- <span data-ttu-id="484f6-634">字符串 "sig"</span><span class="sxs-lookup"><span data-stu-id="484f6-634">The string "sig"</span></span>
- <span data-ttu-id="484f6-635">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="484f6-635">0-2 whitespace characters</span></span>
- <span data-ttu-id="484f6-636">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="484f6-636">An equal sign (=)</span></span>
- <span data-ttu-id="484f6-637">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="484f6-637">0-2 whitespace characters</span></span>
- <span data-ttu-id="484f6-638">介于43-53 个字符和小写字母、数字或百分比符号 (%) 之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="484f6-638">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="484f6-639">字符串 "% 3d"</span><span class="sxs-lookup"><span data-stu-id="484f6-639">The string "%3d"</span></span>
- <span data-ttu-id="484f6-640">不是字母或大写字符、数字或百分号 (%) 的任何字符</span><span class="sxs-lookup"><span data-stu-id="484f6-640">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-641">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-641">Checksum</span></span>

<span data-ttu-id="484f6-642">否</span><span class="sxs-lookup"><span data-stu-id="484f6-642">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-643">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-643">Definition</span></span>

<span data-ttu-id="484f6-644">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-644">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-645">正则表达式 CEP_Regex_AzureSAS 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-645">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="484f6-646">Azure 服务总线连接字符串</span><span class="sxs-lookup"><span data-stu-id="484f6-646">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="484f6-647">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-647">Format</span></span>

<span data-ttu-id="484f6-648">字符串 "终结点", 后跟下面模式中所示的字符和字符串, 包括字符串 "</span><span class="sxs-lookup"><span data-stu-id="484f6-648">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="484f6-649">net "和" SharedAccesKey "。</span><span class="sxs-lookup"><span data-stu-id="484f6-649">net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-650">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-650">Pattern</span></span>

- <span data-ttu-id="484f6-651">字符串 "EndPoint"</span><span class="sxs-lookup"><span data-stu-id="484f6-651">The string "EndPoint"</span></span>
- <span data-ttu-id="484f6-652">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="484f6-652">0-2 whitespace characters</span></span>
- <span data-ttu-id="484f6-653">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="484f6-653">An equal sign (=)</span></span>
- <span data-ttu-id="484f6-654">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="484f6-654">0-2 whitespace characters</span></span>
- <span data-ttu-id="484f6-655">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="484f6-655">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="484f6-656">字符串 "</span><span class="sxs-lookup"><span data-stu-id="484f6-656">The string "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="484f6-657">netmeeting</span><span class="sxs-lookup"><span data-stu-id="484f6-657">net"</span></span>
- <span data-ttu-id="484f6-658">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="484f6-658">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="484f6-659">字符串 "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="484f6-659">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="484f6-660">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="484f6-660">0-2 whitespace characters</span></span>
- <span data-ttu-id="484f6-661">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="484f6-661">An equal sign (=)</span></span>
- <span data-ttu-id="484f6-662">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="484f6-662">0-2 whitespace characters</span></span>
- <span data-ttu-id="484f6-663">43个字符的任意组合, 这些字符为小写字母、数字、斜杠 (/) 或加号 (+)</span><span class="sxs-lookup"><span data-stu-id="484f6-663">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="484f6-664">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="484f6-664">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-665">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-665">Checksum</span></span>

<span data-ttu-id="484f6-666">否</span><span class="sxs-lookup"><span data-stu-id="484f6-666">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-667">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-667">Definition</span></span>

<span data-ttu-id="484f6-668">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-668">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-669">正则表达式 CEP_Regex_AzureServiceBusConnectionString 找到与该模式匹配的内容。。</span><span class="sxs-lookup"><span data-stu-id="484f6-669">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="484f6-670">正则表达式 CEP_CommonExampleKeywords**未**找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-670">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-671">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-671">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="484f6-672">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="484f6-672">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="484f6-673">(请注意, 从技术上讲, 此敏感信息类型通过使用正则表达式 (而不是关键字列表) 来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-673">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="484f6-674">尚未</span><span class="sxs-lookup"><span data-stu-id="484f6-674">contoso</span></span>
- <span data-ttu-id="484f6-675">送交</span><span class="sxs-lookup"><span data-stu-id="484f6-675">fabrikam</span></span>
- <span data-ttu-id="484f6-676">罗斯</span><span class="sxs-lookup"><span data-stu-id="484f6-676">northwind</span></span>
- <span data-ttu-id="484f6-677">沙盒</span><span class="sxs-lookup"><span data-stu-id="484f6-677">sandbox</span></span>
- <span data-ttu-id="484f6-678">onebox</span><span class="sxs-lookup"><span data-stu-id="484f6-678">onebox</span></span>
- <span data-ttu-id="484f6-679">localhost</span><span class="sxs-lookup"><span data-stu-id="484f6-679">localhost</span></span>
- <span data-ttu-id="484f6-680">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="484f6-680">127.0.0.1</span></span>
- <span data-ttu-id="484f6-681">testacs.</span><span class="sxs-lookup"><span data-stu-id="484f6-681">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="484f6-682">com</span><span class="sxs-lookup"><span data-stu-id="484f6-682">com</span></span>
- <span data-ttu-id="484f6-683">s-int。</span><span class="sxs-lookup"><span data-stu-id="484f6-683">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="484f6-684">netmeeting</span><span class="sxs-lookup"><span data-stu-id="484f6-684">net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="484f6-685">Azure 存储帐户密钥</span><span class="sxs-lookup"><span data-stu-id="484f6-685">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="484f6-686">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-686">Format</span></span>

<span data-ttu-id="484f6-687">字符串 "DefaultEndpointsProtocol", 后跟下面模式中所述的字符和字符串, 包括字符串 "AccountKey"。</span><span class="sxs-lookup"><span data-stu-id="484f6-687">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-688">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-688">Pattern</span></span>

- <span data-ttu-id="484f6-689">字符串 "DefaultEndpointsProtocol"</span><span class="sxs-lookup"><span data-stu-id="484f6-689">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="484f6-690">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="484f6-690">0-2 whitespace characters</span></span>
- <span data-ttu-id="484f6-691">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="484f6-691">An equal sign (=)</span></span>
- <span data-ttu-id="484f6-692">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="484f6-692">0-2 whitespace characters</span></span>
- <span data-ttu-id="484f6-693">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="484f6-693">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="484f6-694">字符串 "AccountKey"</span><span class="sxs-lookup"><span data-stu-id="484f6-694">The string "AccountKey"</span></span>
- <span data-ttu-id="484f6-695">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="484f6-695">0-2 whitespace characters</span></span>
- <span data-ttu-id="484f6-696">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="484f6-696">An equal sign (=)</span></span>
- <span data-ttu-id="484f6-697">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="484f6-697">0-2 whitespace characters</span></span>
- <span data-ttu-id="484f6-698">86个字符的任意组合, 这些字符为小写字母、数字、斜杠 (/) 或加号 (+)</span><span class="sxs-lookup"><span data-stu-id="484f6-698">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="484f6-699">两个等号 (=)</span><span class="sxs-lookup"><span data-stu-id="484f6-699">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-700">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-700">Checksum</span></span>

<span data-ttu-id="484f6-701">否</span><span class="sxs-lookup"><span data-stu-id="484f6-701">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-702">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-702">Definition</span></span>

<span data-ttu-id="484f6-703">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-703">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-704">正则表达式 CEP_Regex_AzureStorageAccountKey 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-704">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-705">正则表达式 CEP_AzureEmulatorStorageAccountFilter**未**找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-705">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-706">正则表达式 CEP_CommonExampleKeywords**未**找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-706">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-707">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-707">Keywords</span></span>

#### <a name="cepazureemulatorstorageaccountfilter"></a><span data-ttu-id="484f6-708">CEP_AzureEmulatorStorageAccountFilter</span><span class="sxs-lookup"><span data-stu-id="484f6-708">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="484f6-709">(请注意, 从技术上讲, 此敏感信息类型通过使用正则表达式 (而不是关键字列表) 来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-709">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="484f6-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =</span><span class="sxs-lookup"><span data-stu-id="484f6-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="484f6-711">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="484f6-711">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="484f6-712">(请注意, 从技术上讲, 此敏感信息类型通过使用正则表达式 (而不是关键字列表) 来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-712">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="484f6-713">尚未</span><span class="sxs-lookup"><span data-stu-id="484f6-713">contoso</span></span>
- <span data-ttu-id="484f6-714">送交</span><span class="sxs-lookup"><span data-stu-id="484f6-714">fabrikam</span></span>
- <span data-ttu-id="484f6-715">罗斯</span><span class="sxs-lookup"><span data-stu-id="484f6-715">northwind</span></span>
- <span data-ttu-id="484f6-716">沙盒</span><span class="sxs-lookup"><span data-stu-id="484f6-716">sandbox</span></span>
- <span data-ttu-id="484f6-717">onebox</span><span class="sxs-lookup"><span data-stu-id="484f6-717">onebox</span></span>
- <span data-ttu-id="484f6-718">localhost</span><span class="sxs-lookup"><span data-stu-id="484f6-718">localhost</span></span>
- <span data-ttu-id="484f6-719">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="484f6-719">127.0.0.1</span></span>
- <span data-ttu-id="484f6-720">testacs.</span><span class="sxs-lookup"><span data-stu-id="484f6-720">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="484f6-721">com</span><span class="sxs-lookup"><span data-stu-id="484f6-721">com</span></span>
- <span data-ttu-id="484f6-722">s-int。</span><span class="sxs-lookup"><span data-stu-id="484f6-722">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="484f6-723">netmeeting</span><span class="sxs-lookup"><span data-stu-id="484f6-723">net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="484f6-724">Azure 存储帐户密钥 (常规)</span><span class="sxs-lookup"><span data-stu-id="484f6-724">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="484f6-725">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-725">Format</span></span>

<span data-ttu-id="484f6-726">任何86位或大写字母、数字、正斜杠 (/) 或加号 (+) 的任意组合, 前面或后面是下面模式中所述的字符。</span><span class="sxs-lookup"><span data-stu-id="484f6-726">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-727">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-727">Pattern</span></span>

- <span data-ttu-id="484f6-728">大于号 (>)、撇号 (')、等号 (=)、引号 (") 或数字符号 (#) 的0-1</span><span class="sxs-lookup"><span data-stu-id="484f6-728">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="484f6-729">86个字符的任意组合, 这些字符为小写字母、数字、斜杠 (/) 或加号 (+)</span><span class="sxs-lookup"><span data-stu-id="484f6-729">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="484f6-730">两个等号 (=)</span><span class="sxs-lookup"><span data-stu-id="484f6-730">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="484f6-731">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-731">Checksum</span></span>

<span data-ttu-id="484f6-732">否</span><span class="sxs-lookup"><span data-stu-id="484f6-732">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-733">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-733">Definition</span></span>

<span data-ttu-id="484f6-734">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-734">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-735">正则表达式 CEP_Regex_AzureStorageAccountKeyGeneric 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-735">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="484f6-736">比利时国家号码</span><span class="sxs-lookup"><span data-stu-id="484f6-736">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-737">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-737">Format</span></span>

<span data-ttu-id="484f6-738">11 个数字加分隔符</span><span class="sxs-lookup"><span data-stu-id="484f6-738">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-739">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-739">Pattern</span></span>

<span data-ttu-id="484f6-740">11 个数字加分隔符：</span><span class="sxs-lookup"><span data-stu-id="484f6-740">11 digits plus delimiters:</span></span>
- <span data-ttu-id="484f6-741">六个数字加两个点，采用格式  YY.MM.DD，代表出生日期  </span><span class="sxs-lookup"><span data-stu-id="484f6-741">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="484f6-742">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="484f6-742">A hyphen</span></span> 
- <span data-ttu-id="484f6-743">三个连续的数字（男性用奇数，女性用偶数） </span><span class="sxs-lookup"><span data-stu-id="484f6-743">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="484f6-744">一个点</span><span class="sxs-lookup"><span data-stu-id="484f6-744">A period</span></span> 
- <span data-ttu-id="484f6-745">两个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="484f6-745">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-746">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-746">Checksum</span></span>

<span data-ttu-id="484f6-747">是</span><span class="sxs-lookup"><span data-stu-id="484f6-747">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-748">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-748">Definition</span></span>

<span data-ttu-id="484f6-749">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-749">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-750">函数 Func_belgium_national_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-750">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-751">找到 Keyword_belgium_national_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-751">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="484f6-752">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-752">The checksum passes.</span></span>

```
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="484f6-753">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-753">Keywords</span></span>

#### <a name="keywordbelgiumnationalnumber"></a><span data-ttu-id="484f6-754">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="484f6-754">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="484f6-755">标识</span><span class="sxs-lookup"><span data-stu-id="484f6-755">Identity</span></span>
- <span data-ttu-id="484f6-756">注册</span><span class="sxs-lookup"><span data-stu-id="484f6-756">Registration</span></span>
- <span data-ttu-id="484f6-757">Id</span><span class="sxs-lookup"><span data-stu-id="484f6-757">Identification</span></span> 
- <span data-ttu-id="484f6-758">ID</span><span class="sxs-lookup"><span data-stu-id="484f6-758">ID</span></span> 
- <span data-ttu-id="484f6-759">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="484f6-759">Identiteitskaart</span></span>
- <span data-ttu-id="484f6-760">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="484f6-760">Registratie nummer</span></span> 
- <span data-ttu-id="484f6-761">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="484f6-761">Identificatie nummer</span></span> 
- <span data-ttu-id="484f6-762">Identiteit</span><span class="sxs-lookup"><span data-stu-id="484f6-762">Identiteit</span></span>
- <span data-ttu-id="484f6-763">Registratie</span><span class="sxs-lookup"><span data-stu-id="484f6-763">Registratie</span></span>
- <span data-ttu-id="484f6-764">Identificatie</span><span class="sxs-lookup"><span data-stu-id="484f6-764">Identificatie</span></span> 
- <span data-ttu-id="484f6-765">Carte d’identité</span><span class="sxs-lookup"><span data-stu-id="484f6-765">Carte d’identité</span></span> 
- <span data-ttu-id="484f6-766">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="484f6-766">numéro d'immatriculation</span></span>
- <span data-ttu-id="484f6-767">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="484f6-767">numéro d'identification</span></span>
- <span data-ttu-id="484f6-768">identité</span><span class="sxs-lookup"><span data-stu-id="484f6-768">identité</span></span> 
- <span data-ttu-id="484f6-769">inscription</span><span class="sxs-lookup"><span data-stu-id="484f6-769">inscription</span></span> 
- <span data-ttu-id="484f6-770">Identifikation</span><span class="sxs-lookup"><span data-stu-id="484f6-770">Identifikation</span></span>
- <span data-ttu-id="484f6-771">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="484f6-771">Identifizierung</span></span>
- <span data-ttu-id="484f6-772">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="484f6-772">Identifikationsnummer</span></span>
- <span data-ttu-id="484f6-773">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="484f6-773">Personalausweis</span></span>
- <span data-ttu-id="484f6-774">Registrierung</span><span class="sxs-lookup"><span data-stu-id="484f6-774">Registrierung</span></span>
- <span data-ttu-id="484f6-775">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="484f6-775">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="484f6-776">巴西 CPF 号码</span><span class="sxs-lookup"><span data-stu-id="484f6-776">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-777">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-777">Format</span></span>

<span data-ttu-id="484f6-778">11 个数字（包括校验位），可以格式化，也可以非格式化</span><span class="sxs-lookup"><span data-stu-id="484f6-778">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-779">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-779">Pattern</span></span>

<span data-ttu-id="484f6-780">格式</span><span class="sxs-lookup"><span data-stu-id="484f6-780">Formatted:</span></span>
- <span data-ttu-id="484f6-781">三位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-781">Three digits</span></span> 
- <span data-ttu-id="484f6-782">一个点 </span><span class="sxs-lookup"><span data-stu-id="484f6-782">A period</span></span> 
- <span data-ttu-id="484f6-783">三位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-783">Three digits</span></span> 
- <span data-ttu-id="484f6-784">一个点 </span><span class="sxs-lookup"><span data-stu-id="484f6-784">A period</span></span> 
- <span data-ttu-id="484f6-785">三位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-785">Three digits</span></span> 
- <span data-ttu-id="484f6-786">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="484f6-786">A hyphen</span></span> 
- <span data-ttu-id="484f6-787">两个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="484f6-787">Two digits which are check digits</span></span>

<span data-ttu-id="484f6-788">纯</span><span class="sxs-lookup"><span data-stu-id="484f6-788">Unformatted:</span></span>
- <span data-ttu-id="484f6-789">11 个数字，其中最后两个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="484f6-789">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-790">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-790">Checksum</span></span>

<span data-ttu-id="484f6-791">是</span><span class="sxs-lookup"><span data-stu-id="484f6-791">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-792">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-792">Definition</span></span>

<span data-ttu-id="484f6-793">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-794">函数 Func_brazil_cpf 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-794">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-795">找到 Keyword_brazil_cpf 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-795">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="484f6-796">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-796">The checksum passes.</span></span>

<span data-ttu-id="484f6-797">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-797">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-798">函数 Func_brazil_cpf 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-798">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-799">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-799">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-800">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-800">Keywords</span></span>

#### <a name="keywordbrazilcpf"></a><span data-ttu-id="484f6-801">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="484f6-801">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="484f6-802">CPF</span><span class="sxs-lookup"><span data-stu-id="484f6-802">CPF</span></span>
- <span data-ttu-id="484f6-803">Id</span><span class="sxs-lookup"><span data-stu-id="484f6-803">Identification</span></span>
- <span data-ttu-id="484f6-804">注册</span><span class="sxs-lookup"><span data-stu-id="484f6-804">Registration</span></span>
- <span data-ttu-id="484f6-805">营业</span><span class="sxs-lookup"><span data-stu-id="484f6-805">Revenue</span></span>
- <span data-ttu-id="484f6-806">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="484f6-806">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="484f6-807">Imposto</span><span class="sxs-lookup"><span data-stu-id="484f6-807">Imposto</span></span> 
- <span data-ttu-id="484f6-808">Identificação</span><span class="sxs-lookup"><span data-stu-id="484f6-808">Identificação</span></span> 
- <span data-ttu-id="484f6-809">Inscrição</span><span class="sxs-lookup"><span data-stu-id="484f6-809">Inscrição</span></span> 
- <span data-ttu-id="484f6-810">Receita</span><span class="sxs-lookup"><span data-stu-id="484f6-810">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="484f6-811">巴西法律实体编号 (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="484f6-811">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="484f6-812">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-812">Format</span></span>

<span data-ttu-id="484f6-813">14 个数字（包括注册号、分行号码和校验位），再加上分隔符</span><span class="sxs-lookup"><span data-stu-id="484f6-813">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-814">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-814">Pattern</span></span>
<span data-ttu-id="484f6-815">14 个数字，再加上分隔符：</span><span class="sxs-lookup"><span data-stu-id="484f6-815">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="484f6-816">两个数字 </span><span class="sxs-lookup"><span data-stu-id="484f6-816">Two digits</span></span> 
- <span data-ttu-id="484f6-817">一个点 </span><span class="sxs-lookup"><span data-stu-id="484f6-817">A period</span></span> 
- <span data-ttu-id="484f6-818">三个数字 </span><span class="sxs-lookup"><span data-stu-id="484f6-818">Three digits</span></span> 
- <span data-ttu-id="484f6-819">一个点 </span><span class="sxs-lookup"><span data-stu-id="484f6-819">A period</span></span> 
- <span data-ttu-id="484f6-820">三个数字（前 8 位数是注册号） </span><span class="sxs-lookup"><span data-stu-id="484f6-820">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="484f6-821">正斜杠 </span><span class="sxs-lookup"><span data-stu-id="484f6-821">A forward slash</span></span> 
- <span data-ttu-id="484f6-822">四位分行号码 </span><span class="sxs-lookup"><span data-stu-id="484f6-822">Four-digit branch number</span></span> 
- <span data-ttu-id="484f6-823">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="484f6-823">A hyphen</span></span> 
- <span data-ttu-id="484f6-824">两个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="484f6-824">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-825">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-825">Checksum</span></span>

<span data-ttu-id="484f6-826">是</span><span class="sxs-lookup"><span data-stu-id="484f6-826">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-827">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-827">Definition</span></span>

<span data-ttu-id="484f6-828">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-828">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-829">函数 Func_brazil_cnpj 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-829">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-830">找到 Keyword_brazil_cnpj 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-830">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="484f6-831">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-831">The checksum passes.</span></span>

<span data-ttu-id="484f6-832">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-833">函数 Func_brazil_cnpj 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-833">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-834">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-834">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-835">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-835">Keywords</span></span>

#### <a name="keywordbrazilcnpj"></a><span data-ttu-id="484f6-836">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="484f6-836">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="484f6-837">CNPJ</span><span class="sxs-lookup"><span data-stu-id="484f6-837">CNPJ</span></span> 
- <span data-ttu-id="484f6-838">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="484f6-838">CNPJ/MF</span></span> 
- <span data-ttu-id="484f6-839">CNPJ-MF</span><span class="sxs-lookup"><span data-stu-id="484f6-839">CNPJ-MF</span></span> 
- <span data-ttu-id="484f6-840">National Registry of Legal Entities</span><span class="sxs-lookup"><span data-stu-id="484f6-840">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="484f6-841">Taxpayers Registry</span><span class="sxs-lookup"><span data-stu-id="484f6-841">Taxpayers Registry</span></span> 
- <span data-ttu-id="484f6-842">Legal entity</span><span class="sxs-lookup"><span data-stu-id="484f6-842">Legal entity</span></span> 
- <span data-ttu-id="484f6-843">Legal entities</span><span class="sxs-lookup"><span data-stu-id="484f6-843">Legal entities</span></span> 
- <span data-ttu-id="484f6-844">Registration Status</span><span class="sxs-lookup"><span data-stu-id="484f6-844">Registration Status</span></span> 
- <span data-ttu-id="484f6-845">商业版</span><span class="sxs-lookup"><span data-stu-id="484f6-845">Business</span></span> 
- <span data-ttu-id="484f6-846">Company</span><span class="sxs-lookup"><span data-stu-id="484f6-846">Company</span></span>
- <span data-ttu-id="484f6-847">CNPJ</span><span class="sxs-lookup"><span data-stu-id="484f6-847">CNPJ</span></span> 
- <span data-ttu-id="484f6-848">Cadastro Nacional da Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="484f6-848">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="484f6-849">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="484f6-849">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="484f6-850">CGC</span><span class="sxs-lookup"><span data-stu-id="484f6-850">CGC</span></span> 
- <span data-ttu-id="484f6-851">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="484f6-851">Pessoa jurídica</span></span> 
- <span data-ttu-id="484f6-852">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="484f6-852">Pessoas jurídicas</span></span> 
- <span data-ttu-id="484f6-853">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="484f6-853">Situação cadastral</span></span> 
- <span data-ttu-id="484f6-854">Inscrição</span><span class="sxs-lookup"><span data-stu-id="484f6-854">Inscrição</span></span> 
- <span data-ttu-id="484f6-855">Empresa</span><span class="sxs-lookup"><span data-stu-id="484f6-855">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="484f6-856">	巴西国家身份证 (RG)</span><span class="sxs-lookup"><span data-stu-id="484f6-856">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="484f6-857">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-857">Format</span></span>

<span data-ttu-id="484f6-858">Registro Geral (旧格式): 9 个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-858">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="484f6-859">Registro de Identidade (RIC) (新格式):11 个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-859">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-860">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-860">Pattern</span></span>

<span data-ttu-id="484f6-861">Registro Geral（旧格式）：</span><span class="sxs-lookup"><span data-stu-id="484f6-861">Registro Geral (old format):</span></span>
- <span data-ttu-id="484f6-862">两个数字 </span><span class="sxs-lookup"><span data-stu-id="484f6-862">Two digits</span></span> 
- <span data-ttu-id="484f6-863">一个点 </span><span class="sxs-lookup"><span data-stu-id="484f6-863">A period</span></span> 
- <span data-ttu-id="484f6-864">三个数字 </span><span class="sxs-lookup"><span data-stu-id="484f6-864">Three digits</span></span> 
- <span data-ttu-id="484f6-865">一个点 </span><span class="sxs-lookup"><span data-stu-id="484f6-865">A period</span></span> 
- <span data-ttu-id="484f6-866">三个数字 </span><span class="sxs-lookup"><span data-stu-id="484f6-866">Three digits</span></span> 
- <span data-ttu-id="484f6-867">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="484f6-867">A hyphen</span></span> 
- <span data-ttu-id="484f6-868">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="484f6-868">One digit which is a check digit</span></span>

<span data-ttu-id="484f6-869">Registro de Identidade (RIC) (新格式):</span><span class="sxs-lookup"><span data-stu-id="484f6-869">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="484f6-870">10 个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-870">10 digits</span></span> 
- <span data-ttu-id="484f6-871">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="484f6-871">A hyphen</span></span> 
- <span data-ttu-id="484f6-872">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="484f6-872">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-873">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-873">Checksum</span></span>

<span data-ttu-id="484f6-874">是</span><span class="sxs-lookup"><span data-stu-id="484f6-874">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-875">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-875">Definition</span></span>

<span data-ttu-id="484f6-876">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-876">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-877">函数 Func_brazil_rg 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-877">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-878">找到 Keyword_brazil_rg 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-878">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="484f6-879">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-879">The checksum passes.</span></span>

<span data-ttu-id="484f6-880">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-880">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-881">函数 Func_brazil_rg 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-881">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-882">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-882">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-883">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-883">Keywords</span></span>

#### <a name="keywordbrazilrg"></a><span data-ttu-id="484f6-884">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="484f6-884">Keyword_brazil_rg</span></span>

<span data-ttu-id="484f6-885">Cédula de identidade identity 卡片国家 id número de rregistro registro de Iidentidade registro geral RG (此关键字区分大小写) RIC (此关键字区分大小写)</span><span class="sxs-lookup"><span data-stu-id="484f6-885">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="484f6-886">加拿大银行帐号</span><span class="sxs-lookup"><span data-stu-id="484f6-886">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-887">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-887">Format</span></span>

<span data-ttu-id="484f6-888">七个或十二个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-888">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-889">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-889">Pattern</span></span>

<span data-ttu-id="484f6-890">加拿大银行帐号是七个或十二个数字。</span><span class="sxs-lookup"><span data-stu-id="484f6-890">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="484f6-891">加拿大银行帐户的银行代号是：</span><span class="sxs-lookup"><span data-stu-id="484f6-891">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="484f6-892">五位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-892">Five digits</span></span> 
- <span data-ttu-id="484f6-893">连字符</span><span class="sxs-lookup"><span data-stu-id="484f6-893">A hyphen</span></span> 
- <span data-ttu-id="484f6-894">三位数字或</span><span class="sxs-lookup"><span data-stu-id="484f6-894">Three digits OR</span></span>
- <span data-ttu-id="484f6-895">一个零“0” </span><span class="sxs-lookup"><span data-stu-id="484f6-895">A zero "0"</span></span> 
- <span data-ttu-id="484f6-896">八位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-896">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-897">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-897">Checksum</span></span>

<span data-ttu-id="484f6-898">否</span><span class="sxs-lookup"><span data-stu-id="484f6-898">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-899">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-899">Definition</span></span>

<span data-ttu-id="484f6-900">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-900">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-901">正则表达式 Regex_canada_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-901">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-902">找到 Keyword_canada_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-902">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="484f6-903">正则表达式 Regex_canada_bank_account_transit_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-903">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="484f6-904">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-904">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-905">正则表达式 Regex_canada_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-905">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-906">找到 Keyword_canada_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-906">A keyword from Keyword_canada_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-907">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-907">Keywords</span></span>

#### <a name="keywordcanadabankaccountnumber"></a><span data-ttu-id="484f6-908">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="484f6-908">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="484f6-909">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="484f6-909">canada savings bonds</span></span>
- <span data-ttu-id="484f6-910">canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="484f6-910">canada revenue agency</span></span>
- <span data-ttu-id="484f6-911">canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="484f6-911">canadian financial institution</span></span>
- <span data-ttu-id="484f6-912">direct deposit form</span><span class="sxs-lookup"><span data-stu-id="484f6-912">direct deposit form</span></span>
- <span data-ttu-id="484f6-913">canadian citizen</span><span class="sxs-lookup"><span data-stu-id="484f6-913">canadian citizen</span></span>
- <span data-ttu-id="484f6-914">legal representative</span><span class="sxs-lookup"><span data-stu-id="484f6-914">legal representative</span></span>
- <span data-ttu-id="484f6-915">notary public</span><span class="sxs-lookup"><span data-stu-id="484f6-915">notary public</span></span>
- <span data-ttu-id="484f6-916">commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="484f6-916">commissioner for oaths</span></span>
- <span data-ttu-id="484f6-917">child care benefit</span><span class="sxs-lookup"><span data-stu-id="484f6-917">child care benefit</span></span>
- <span data-ttu-id="484f6-918">universal child care</span><span class="sxs-lookup"><span data-stu-id="484f6-918">universal child care</span></span>
- <span data-ttu-id="484f6-919">canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="484f6-919">canada child tax benefit</span></span>
- <span data-ttu-id="484f6-920">income tax benefit</span><span class="sxs-lookup"><span data-stu-id="484f6-920">income tax benefit</span></span>
- <span data-ttu-id="484f6-921">harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="484f6-921">harmonized sales tax</span></span>
- <span data-ttu-id="484f6-922">social insurance number</span><span class="sxs-lookup"><span data-stu-id="484f6-922">social insurance number</span></span>
- <span data-ttu-id="484f6-923">income tax refund</span><span class="sxs-lookup"><span data-stu-id="484f6-923">income tax refund</span></span>
- <span data-ttu-id="484f6-924">child tax benefit</span><span class="sxs-lookup"><span data-stu-id="484f6-924">child tax benefit</span></span>
- <span data-ttu-id="484f6-925">territorial payments</span><span class="sxs-lookup"><span data-stu-id="484f6-925">territorial payments</span></span>
- <span data-ttu-id="484f6-926">institution number</span><span class="sxs-lookup"><span data-stu-id="484f6-926">institution number</span></span>
- <span data-ttu-id="484f6-927">deposit request</span><span class="sxs-lookup"><span data-stu-id="484f6-927">deposit request</span></span>
- <span data-ttu-id="484f6-928">banking information</span><span class="sxs-lookup"><span data-stu-id="484f6-928">banking information</span></span>
- <span data-ttu-id="484f6-929">direct deposit</span><span class="sxs-lookup"><span data-stu-id="484f6-929">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="484f6-930">加拿大驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="484f6-930">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-931">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-931">Format</span></span>

<span data-ttu-id="484f6-932">因省而异</span><span class="sxs-lookup"><span data-stu-id="484f6-932">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-933">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-933">Pattern</span></span>

<span data-ttu-id="484f6-934">各种模式，涵盖艾伯塔、 不列颠哥伦比亚、 马尼托巴、 新不伦瑞克、 纽芬兰/拉布拉多、 新斯科舍、 安大略、 爱德华王子岛，魁北克和萨斯喀彻温</span><span class="sxs-lookup"><span data-stu-id="484f6-934">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-935">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-935">Checksum</span></span>

<span data-ttu-id="484f6-936">否</span><span class="sxs-lookup"><span data-stu-id="484f6-936">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-937">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-937">Definition</span></span>

<span data-ttu-id="484f6-938">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-938">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-939">函数 Func_[province_name]_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-939">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-940">找到 Keyword_[province_name]_drivers_license_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-940">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="484f6-941">找到 Keyword_canada_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-941">A keyword from Keyword_canada_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-942">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-942">Keywords</span></span>

#### <a name="keywordprovincenamedriverslicensename"></a><span data-ttu-id="484f6-943">Keyword_[province_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="484f6-943">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="484f6-944">省/市/自治区的缩写，例如 AB</span><span class="sxs-lookup"><span data-stu-id="484f6-944">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="484f6-945">省名称，例如 Alberta</span><span class="sxs-lookup"><span data-stu-id="484f6-945">The province name, for example Alberta</span></span>

#### <a name="keywordcanadadriverslicense"></a><span data-ttu-id="484f6-946">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="484f6-946">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="484f6-947">通讯</span><span class="sxs-lookup"><span data-stu-id="484f6-947">DL</span></span>
- <span data-ttu-id="484f6-948">DLS</span><span class="sxs-lookup"><span data-stu-id="484f6-948">DLS</span></span>
- <span data-ttu-id="484f6-949">采用</span><span class="sxs-lookup"><span data-stu-id="484f6-949">CDL</span></span>
- <span data-ttu-id="484f6-950">CDLS</span><span class="sxs-lookup"><span data-stu-id="484f6-950">CDLS</span></span>
- <span data-ttu-id="484f6-951">DriverLic</span><span class="sxs-lookup"><span data-stu-id="484f6-951">DriverLic</span></span>
- <span data-ttu-id="484f6-952">DriverLics</span><span class="sxs-lookup"><span data-stu-id="484f6-952">DriverLics</span></span>
- <span data-ttu-id="484f6-953">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="484f6-953">DriverLicense</span></span>
- <span data-ttu-id="484f6-954">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="484f6-954">DriverLicenses</span></span>
- <span data-ttu-id="484f6-955">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="484f6-955">DriverLicence</span></span>
- <span data-ttu-id="484f6-956">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="484f6-956">DriverLicences</span></span>
- <span data-ttu-id="484f6-957">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="484f6-957">Driver Lic</span></span>
- <span data-ttu-id="484f6-958">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="484f6-958">Driver Lics</span></span>
- <span data-ttu-id="484f6-959">Driver License</span><span class="sxs-lookup"><span data-stu-id="484f6-959">Driver License</span></span>
- <span data-ttu-id="484f6-960">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="484f6-960">Driver Licenses</span></span>
- <span data-ttu-id="484f6-961">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="484f6-961">Driver Licence</span></span>
- <span data-ttu-id="484f6-962">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="484f6-962">Driver Licences</span></span>
- <span data-ttu-id="484f6-963">DriversLic</span><span class="sxs-lookup"><span data-stu-id="484f6-963">DriversLic</span></span>
- <span data-ttu-id="484f6-964">DriversLics</span><span class="sxs-lookup"><span data-stu-id="484f6-964">DriversLics</span></span>
- <span data-ttu-id="484f6-965">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="484f6-965">DriversLicence</span></span>
- <span data-ttu-id="484f6-966">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="484f6-966">DriversLicences</span></span>
- <span data-ttu-id="484f6-967">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="484f6-967">DriversLicense</span></span>
- <span data-ttu-id="484f6-968">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="484f6-968">DriversLicenses</span></span>
- <span data-ttu-id="484f6-969">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="484f6-969">Drivers Lic</span></span>
- <span data-ttu-id="484f6-970">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="484f6-970">Drivers Lics</span></span>
- <span data-ttu-id="484f6-971">Drivers License</span><span class="sxs-lookup"><span data-stu-id="484f6-971">Drivers License</span></span>
- <span data-ttu-id="484f6-972">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="484f6-972">Drivers Licenses</span></span>
- <span data-ttu-id="484f6-973">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="484f6-973">Drivers Licence</span></span>
- <span data-ttu-id="484f6-974">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="484f6-974">Drivers Licences</span></span>
- <span data-ttu-id="484f6-975">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="484f6-975">Driver'Lic</span></span>
- <span data-ttu-id="484f6-976">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="484f6-976">Driver'Lics</span></span>
- <span data-ttu-id="484f6-977">Driver'License</span><span class="sxs-lookup"><span data-stu-id="484f6-977">Driver'License</span></span>
- <span data-ttu-id="484f6-978">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="484f6-978">Driver'Licenses</span></span>
- <span data-ttu-id="484f6-979">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="484f6-979">Driver'Licence</span></span>
- <span data-ttu-id="484f6-980">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="484f6-980">Driver'Licences</span></span>
- <span data-ttu-id="484f6-981">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="484f6-981">Driver' Lic</span></span>
- <span data-ttu-id="484f6-982">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="484f6-982">Driver' Lics</span></span>
- <span data-ttu-id="484f6-983">Driver' License</span><span class="sxs-lookup"><span data-stu-id="484f6-983">Driver' License</span></span>
- <span data-ttu-id="484f6-984">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="484f6-984">Driver' Licenses</span></span>
- <span data-ttu-id="484f6-985">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="484f6-985">Driver' Licence</span></span>
- <span data-ttu-id="484f6-986">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="484f6-986">Driver' Licences</span></span>
- <span data-ttu-id="484f6-987">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="484f6-987">Driver'sLic</span></span>
- <span data-ttu-id="484f6-988">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="484f6-988">Driver'sLics</span></span>
- <span data-ttu-id="484f6-989">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="484f6-989">Driver'sLicense</span></span>
- <span data-ttu-id="484f6-990">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="484f6-990">Driver'sLicenses</span></span>
- <span data-ttu-id="484f6-991">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="484f6-991">Driver'sLicence</span></span>
- <span data-ttu-id="484f6-992">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="484f6-992">Driver'sLicences</span></span>
- <span data-ttu-id="484f6-993">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="484f6-993">Driver's Lic</span></span>
- <span data-ttu-id="484f6-994">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="484f6-994">Driver's Lics</span></span>
- <span data-ttu-id="484f6-995">Driver's License</span><span class="sxs-lookup"><span data-stu-id="484f6-995">Driver's License</span></span>
- <span data-ttu-id="484f6-996">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="484f6-996">Driver's Licenses</span></span>
- <span data-ttu-id="484f6-997">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="484f6-997">Driver's Licence</span></span>
- <span data-ttu-id="484f6-998">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="484f6-998">Driver's Licences</span></span>
- <span data-ttu-id="484f6-999">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="484f6-999">Permis de Conduire</span></span>
- <span data-ttu-id="484f6-1000">id</span><span class="sxs-lookup"><span data-stu-id="484f6-1000">id</span></span>
- <span data-ttu-id="484f6-1001">ids</span><span class="sxs-lookup"><span data-stu-id="484f6-1001">ids</span></span>
- <span data-ttu-id="484f6-1002">idcard number</span><span class="sxs-lookup"><span data-stu-id="484f6-1002">idcard number</span></span>
- <span data-ttu-id="484f6-1003">idcard numbers</span><span class="sxs-lookup"><span data-stu-id="484f6-1003">idcard numbers</span></span>
- <span data-ttu-id="484f6-1004">idcard #</span><span class="sxs-lookup"><span data-stu-id="484f6-1004">idcard #</span></span>
- <span data-ttu-id="484f6-1005">idcard #s</span><span class="sxs-lookup"><span data-stu-id="484f6-1005">idcard #s</span></span>
- <span data-ttu-id="484f6-1006">idcard card</span><span class="sxs-lookup"><span data-stu-id="484f6-1006">idcard card</span></span>
- <span data-ttu-id="484f6-1007">idcard cards</span><span class="sxs-lookup"><span data-stu-id="484f6-1007">idcard cards</span></span>
- <span data-ttu-id="484f6-1008">idcard</span><span class="sxs-lookup"><span data-stu-id="484f6-1008">idcard</span></span>
- <span data-ttu-id="484f6-1009">identification number</span><span class="sxs-lookup"><span data-stu-id="484f6-1009">identification number</span></span>
- <span data-ttu-id="484f6-1010">identification numbers</span><span class="sxs-lookup"><span data-stu-id="484f6-1010">identification numbers</span></span>
- <span data-ttu-id="484f6-1011">identification #</span><span class="sxs-lookup"><span data-stu-id="484f6-1011">identification #</span></span>
- <span data-ttu-id="484f6-1012">identification #s</span><span class="sxs-lookup"><span data-stu-id="484f6-1012">identification #s</span></span>
- <span data-ttu-id="484f6-1013">identification card</span><span class="sxs-lookup"><span data-stu-id="484f6-1013">identification card</span></span>
- <span data-ttu-id="484f6-1014">identification cards</span><span class="sxs-lookup"><span data-stu-id="484f6-1014">identification cards</span></span>
- <span data-ttu-id="484f6-1015">id</span><span class="sxs-lookup"><span data-stu-id="484f6-1015">identification</span></span> 
- <span data-ttu-id="484f6-1016">通讯</span><span class="sxs-lookup"><span data-stu-id="484f6-1016">DL#</span></span>
- <span data-ttu-id="484f6-1017">DLS</span><span class="sxs-lookup"><span data-stu-id="484f6-1017">DLS#</span></span> 
- <span data-ttu-id="484f6-1018">采用</span><span class="sxs-lookup"><span data-stu-id="484f6-1018">CDL#</span></span> 
- <span data-ttu-id="484f6-1019">CDLS#</span><span class="sxs-lookup"><span data-stu-id="484f6-1019">CDLS#</span></span> 
- <span data-ttu-id="484f6-1020">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="484f6-1020">DriverLic#</span></span> 
- <span data-ttu-id="484f6-1021">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="484f6-1021">DriverLics#</span></span> 
- <span data-ttu-id="484f6-1022">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="484f6-1022">DriverLicense#</span></span> 
- <span data-ttu-id="484f6-1023">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="484f6-1023">DriverLicenses#</span></span> 
- <span data-ttu-id="484f6-1024">DriverLicence#</span><span class="sxs-lookup"><span data-stu-id="484f6-1024">DriverLicence#</span></span> 
- <span data-ttu-id="484f6-1025">DriverLicences#</span><span class="sxs-lookup"><span data-stu-id="484f6-1025">DriverLicences#</span></span> 
- <span data-ttu-id="484f6-1026">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="484f6-1026">Driver Lic#</span></span>
- <span data-ttu-id="484f6-1027">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="484f6-1027">Driver Lics#</span></span> 
- <span data-ttu-id="484f6-1028">Driver License#</span><span class="sxs-lookup"><span data-stu-id="484f6-1028">Driver License#</span></span> 
- <span data-ttu-id="484f6-1029">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="484f6-1029">Driver Licenses#</span></span> 
- <span data-ttu-id="484f6-1030">Driver License#</span><span class="sxs-lookup"><span data-stu-id="484f6-1030">Driver License#</span></span> 
- <span data-ttu-id="484f6-1031">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="484f6-1031">Driver Licences#</span></span> 
- <span data-ttu-id="484f6-1032">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="484f6-1032">DriversLic#</span></span> 
- <span data-ttu-id="484f6-1033">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="484f6-1033">DriversLics#</span></span> 
- <span data-ttu-id="484f6-1034">DriversLicense#</span><span class="sxs-lookup"><span data-stu-id="484f6-1034">DriversLicense#</span></span> 
- <span data-ttu-id="484f6-1035">DriversLicenses#</span><span class="sxs-lookup"><span data-stu-id="484f6-1035">DriversLicenses#</span></span> 
- <span data-ttu-id="484f6-1036">DriversLicence#</span><span class="sxs-lookup"><span data-stu-id="484f6-1036">DriversLicence#</span></span> 
- <span data-ttu-id="484f6-1037">DriversLicences#</span><span class="sxs-lookup"><span data-stu-id="484f6-1037">DriversLicences#</span></span> 
- <span data-ttu-id="484f6-1038">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="484f6-1038">Drivers Lic#</span></span> 
- <span data-ttu-id="484f6-1039">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="484f6-1039">Drivers Lics#</span></span> 
- <span data-ttu-id="484f6-1040">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="484f6-1040">Drivers License#</span></span> 
- <span data-ttu-id="484f6-1041">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="484f6-1041">Drivers Licenses#</span></span> 
- <span data-ttu-id="484f6-1042">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="484f6-1042">Drivers Licence#</span></span> 
- <span data-ttu-id="484f6-1043">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="484f6-1043">Drivers Licences#</span></span> 
- <span data-ttu-id="484f6-1044">Driver'Lic#</span><span class="sxs-lookup"><span data-stu-id="484f6-1044">Driver'Lic#</span></span> 
- <span data-ttu-id="484f6-1045">Driver'Lics#</span><span class="sxs-lookup"><span data-stu-id="484f6-1045">Driver'Lics#</span></span> 
- <span data-ttu-id="484f6-1046">Driver'License#</span><span class="sxs-lookup"><span data-stu-id="484f6-1046">Driver'License#</span></span> 
- <span data-ttu-id="484f6-1047">Driver'Licenses#</span><span class="sxs-lookup"><span data-stu-id="484f6-1047">Driver'Licenses#</span></span> 
- <span data-ttu-id="484f6-1048">Driver'Licence#</span><span class="sxs-lookup"><span data-stu-id="484f6-1048">Driver'Licence#</span></span> 
- <span data-ttu-id="484f6-1049">Driver'Licences#</span><span class="sxs-lookup"><span data-stu-id="484f6-1049">Driver'Licences#</span></span> 
- <span data-ttu-id="484f6-1050">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="484f6-1050">Driver' Lic#</span></span> 
- <span data-ttu-id="484f6-1051">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="484f6-1051">Driver' Lics#</span></span> 
- <span data-ttu-id="484f6-1052">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="484f6-1052">Driver' License#</span></span> 
- <span data-ttu-id="484f6-1053">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="484f6-1053">Driver' Licenses#</span></span> 
- <span data-ttu-id="484f6-1054">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="484f6-1054">Driver' Licence#</span></span> 
- <span data-ttu-id="484f6-1055">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="484f6-1055">Driver' Licences#</span></span> 
- <span data-ttu-id="484f6-1056">Driver'sLic#</span><span class="sxs-lookup"><span data-stu-id="484f6-1056">Driver'sLic#</span></span> 
- <span data-ttu-id="484f6-1057">Driver'sLics#</span><span class="sxs-lookup"><span data-stu-id="484f6-1057">Driver'sLics#</span></span> 
- <span data-ttu-id="484f6-1058">Driver'sLicense#</span><span class="sxs-lookup"><span data-stu-id="484f6-1058">Driver'sLicense#</span></span> 
- <span data-ttu-id="484f6-1059">Driver'sLicenses#</span><span class="sxs-lookup"><span data-stu-id="484f6-1059">Driver'sLicenses#</span></span> 
- <span data-ttu-id="484f6-1060">Driver'sLicence#</span><span class="sxs-lookup"><span data-stu-id="484f6-1060">Driver'sLicence#</span></span> 
- <span data-ttu-id="484f6-1061">Driver'sLicences#</span><span class="sxs-lookup"><span data-stu-id="484f6-1061">Driver'sLicences#</span></span> 
- <span data-ttu-id="484f6-1062">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="484f6-1062">Driver's Lic#</span></span> 
- <span data-ttu-id="484f6-1063">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="484f6-1063">Driver's Lics#</span></span> 
- <span data-ttu-id="484f6-1064">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="484f6-1064">Driver's License#</span></span> 
- <span data-ttu-id="484f6-1065">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="484f6-1065">Driver's Licenses#</span></span> 
- <span data-ttu-id="484f6-1066">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="484f6-1066">Driver's Licence#</span></span> 
- <span data-ttu-id="484f6-1067">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="484f6-1067">Driver's Licences#</span></span> 
- <span data-ttu-id="484f6-1068">Permis de Conduire#</span><span class="sxs-lookup"><span data-stu-id="484f6-1068">Permis de Conduire#</span></span> 
- <span data-ttu-id="484f6-1069">号</span><span class="sxs-lookup"><span data-stu-id="484f6-1069">id#</span></span> 
- <span data-ttu-id="484f6-1070">id</span><span class="sxs-lookup"><span data-stu-id="484f6-1070">ids#</span></span> 
- <span data-ttu-id="484f6-1071">idcard card#</span><span class="sxs-lookup"><span data-stu-id="484f6-1071">idcard card#</span></span> 
- <span data-ttu-id="484f6-1072">idcard cards#</span><span class="sxs-lookup"><span data-stu-id="484f6-1072">idcard cards#</span></span> 
- <span data-ttu-id="484f6-1073">idcard#</span><span class="sxs-lookup"><span data-stu-id="484f6-1073">idcard#</span></span> 
- <span data-ttu-id="484f6-1074">identification card#</span><span class="sxs-lookup"><span data-stu-id="484f6-1074">identification card#</span></span> 
- <span data-ttu-id="484f6-1075">identification cards#</span><span class="sxs-lookup"><span data-stu-id="484f6-1075">identification cards#</span></span> 
- <span data-ttu-id="484f6-1076">id</span><span class="sxs-lookup"><span data-stu-id="484f6-1076">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="484f6-1077">加拿大卫生服务号</span><span class="sxs-lookup"><span data-stu-id="484f6-1077">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-1078">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-1078">Format</span></span>

<span data-ttu-id="484f6-1079">10 个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-1079">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-1080">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-1080">Pattern</span></span>

<span data-ttu-id="484f6-1081">10 个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-1081">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-1082">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-1082">Checksum</span></span>

<span data-ttu-id="484f6-1083">否</span><span class="sxs-lookup"><span data-stu-id="484f6-1083">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-1084">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-1084">Definition</span></span>

<span data-ttu-id="484f6-1085">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-1085">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-1086">正则表达式 Regex_canada_health_service_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-1086">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-1087">找到 Keyword_canada_health_service_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-1087">A keyword from Keyword_canada_health_service_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-1088">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-1088">Keywords</span></span>

#### <a name="keywordcanadahealthservicenumber"></a><span data-ttu-id="484f6-1089">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="484f6-1089">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="484f6-1090">personal health number</span><span class="sxs-lookup"><span data-stu-id="484f6-1090">personal health number</span></span>
- <span data-ttu-id="484f6-1091">patient information</span><span class="sxs-lookup"><span data-stu-id="484f6-1091">patient information</span></span>
- <span data-ttu-id="484f6-1092">health services</span><span class="sxs-lookup"><span data-stu-id="484f6-1092">health services</span></span>
- <span data-ttu-id="484f6-1093">speciality services</span><span class="sxs-lookup"><span data-stu-id="484f6-1093">speciality services</span></span>
- <span data-ttu-id="484f6-1094">automobile accident</span><span class="sxs-lookup"><span data-stu-id="484f6-1094">automobile accident</span></span>
- <span data-ttu-id="484f6-1095">patient hospital</span><span class="sxs-lookup"><span data-stu-id="484f6-1095">patient hospital</span></span>
- <span data-ttu-id="484f6-1096">psychiatrist</span><span class="sxs-lookup"><span data-stu-id="484f6-1096">psychiatrist</span></span>
- <span data-ttu-id="484f6-1097">workers compensation</span><span class="sxs-lookup"><span data-stu-id="484f6-1097">workers compensation</span></span>
- <span data-ttu-id="484f6-1098">障碍</span><span class="sxs-lookup"><span data-stu-id="484f6-1098">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="484f6-1099">加拿大护照号码</span><span class="sxs-lookup"><span data-stu-id="484f6-1099">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-1100">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-1100">Format</span></span>

<span data-ttu-id="484f6-1101">两个大写字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-1101">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-1102">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-1102">Pattern</span></span>

<span data-ttu-id="484f6-1103">两个大写字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-1103">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-1104">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-1104">Checksum</span></span>

<span data-ttu-id="484f6-1105">否</span><span class="sxs-lookup"><span data-stu-id="484f6-1105">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-1106">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-1106">Definition</span></span>

<span data-ttu-id="484f6-1107">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-1107">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-1108">正则表达式 Regex_canada_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-1108">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-1109">找到来自 Keyword_canada_passport_number 或 Keyword_passport 的关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-1109">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-1110">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-1110">Keywords</span></span>

#### <a name="keywordcanadapassportnumber"></a><span data-ttu-id="484f6-1111">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="484f6-1111">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="484f6-1112">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="484f6-1112">canadian citizenship</span></span>
- <span data-ttu-id="484f6-1113">canadian passport</span><span class="sxs-lookup"><span data-stu-id="484f6-1113">canadian passport</span></span>
- <span data-ttu-id="484f6-1114">passport application</span><span class="sxs-lookup"><span data-stu-id="484f6-1114">passport application</span></span>
- <span data-ttu-id="484f6-1115">passport photos</span><span class="sxs-lookup"><span data-stu-id="484f6-1115">passport photos</span></span>
- <span data-ttu-id="484f6-1116">certified translator</span><span class="sxs-lookup"><span data-stu-id="484f6-1116">certified translator</span></span>
- <span data-ttu-id="484f6-1117">canadian citizens</span><span class="sxs-lookup"><span data-stu-id="484f6-1117">canadian citizens</span></span>
- <span data-ttu-id="484f6-1118">processing times</span><span class="sxs-lookup"><span data-stu-id="484f6-1118">processing times</span></span>
- <span data-ttu-id="484f6-1119">renewal application</span><span class="sxs-lookup"><span data-stu-id="484f6-1119">renewal application</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="484f6-1120">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="484f6-1120">Keyword_passport</span></span>

- <span data-ttu-id="484f6-1121">Passport Number</span><span class="sxs-lookup"><span data-stu-id="484f6-1121">Passport Number</span></span>
- <span data-ttu-id="484f6-1122">Passport No</span><span class="sxs-lookup"><span data-stu-id="484f6-1122">Passport No</span></span>
- <span data-ttu-id="484f6-1123">Passport #</span><span class="sxs-lookup"><span data-stu-id="484f6-1123">Passport #</span></span>
- <span data-ttu-id="484f6-1124">登记卡</span><span class="sxs-lookup"><span data-stu-id="484f6-1124">Passport#</span></span>
- <span data-ttu-id="484f6-1125">PassportID</span><span class="sxs-lookup"><span data-stu-id="484f6-1125">PassportID</span></span>
- <span data-ttu-id="484f6-1126">Passportno</span><span class="sxs-lookup"><span data-stu-id="484f6-1126">Passportno</span></span>
- <span data-ttu-id="484f6-1127">passportnumber</span><span class="sxs-lookup"><span data-stu-id="484f6-1127">passportnumber</span></span>
- <span data-ttu-id="484f6-1128">パスポート</span><span class="sxs-lookup"><span data-stu-id="484f6-1128">パスポート</span></span>
- <span data-ttu-id="484f6-1129">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="484f6-1129">パスポート番号</span></span>
- <span data-ttu-id="484f6-1130">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="484f6-1130">パスポートのNum</span></span>
- <span data-ttu-id="484f6-1131">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="484f6-1131">パスポート＃</span></span>
- <span data-ttu-id="484f6-1132">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="484f6-1132">Numéro de passeport</span></span>
- <span data-ttu-id="484f6-1133">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="484f6-1133">Passeport n °</span></span>
- <span data-ttu-id="484f6-1134">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="484f6-1134">Passeport Non</span></span>
- <span data-ttu-id="484f6-1135">Passeport #</span><span class="sxs-lookup"><span data-stu-id="484f6-1135">Passeport #</span></span>
- <span data-ttu-id="484f6-1136">Passeport#</span><span class="sxs-lookup"><span data-stu-id="484f6-1136">Passeport#</span></span>
- <span data-ttu-id="484f6-1137">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="484f6-1137">PasseportNon</span></span>
- <span data-ttu-id="484f6-1138">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="484f6-1138">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="484f6-1139">加拿大个人健康标识号 (PHIN)</span><span class="sxs-lookup"><span data-stu-id="484f6-1139">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="484f6-1140">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-1140">Format</span></span>

<span data-ttu-id="484f6-1141">九个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-1141">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-1142">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-1142">Pattern</span></span>

<span data-ttu-id="484f6-1143">九个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-1143">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-1144">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-1144">Checksum</span></span>

<span data-ttu-id="484f6-1145">否</span><span class="sxs-lookup"><span data-stu-id="484f6-1145">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-1146">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-1146">Definition</span></span>

<span data-ttu-id="484f6-1147">DLP 策略 75% 确信在300个字符的邻近度内检测到此类型的敏感信息: 正则表达式 Regex_canada_phin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-1147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="484f6-1148">找到 Keyword_canada_phin 或 Keyword_canada_provinces 中至少有两个关键字。。</span><span class="sxs-lookup"><span data-stu-id="484f6-1148">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-1149">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-1149">Keywords</span></span>

#### <a name="keywordcanadaphin"></a><span data-ttu-id="484f6-1150">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="484f6-1150">Keyword_canada_phin</span></span>

- <span data-ttu-id="484f6-1151">social insurance number</span><span class="sxs-lookup"><span data-stu-id="484f6-1151">social insurance number</span></span>
- <span data-ttu-id="484f6-1152">health information act</span><span class="sxs-lookup"><span data-stu-id="484f6-1152">health information act</span></span>
- <span data-ttu-id="484f6-1153">income tax information</span><span class="sxs-lookup"><span data-stu-id="484f6-1153">income tax information</span></span>
- <span data-ttu-id="484f6-1154">manitoba health</span><span class="sxs-lookup"><span data-stu-id="484f6-1154">manitoba health</span></span>
- <span data-ttu-id="484f6-1155">health registration</span><span class="sxs-lookup"><span data-stu-id="484f6-1155">health registration</span></span>
- <span data-ttu-id="484f6-1156">prescription purchases</span><span class="sxs-lookup"><span data-stu-id="484f6-1156">prescription purchases</span></span>
- <span data-ttu-id="484f6-1157">benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="484f6-1157">benefit eligibility</span></span>
- <span data-ttu-id="484f6-1158">personal health</span><span class="sxs-lookup"><span data-stu-id="484f6-1158">personal health</span></span>
- <span data-ttu-id="484f6-1159">power of attorney</span><span class="sxs-lookup"><span data-stu-id="484f6-1159">power of attorney</span></span>
- <span data-ttu-id="484f6-1160">registration number</span><span class="sxs-lookup"><span data-stu-id="484f6-1160">registration number</span></span>
- <span data-ttu-id="484f6-1161">personal health number</span><span class="sxs-lookup"><span data-stu-id="484f6-1161">personal health number</span></span>
- <span data-ttu-id="484f6-1162">practitioner referral</span><span class="sxs-lookup"><span data-stu-id="484f6-1162">practitioner referral</span></span>
- <span data-ttu-id="484f6-1163">wellness professional</span><span class="sxs-lookup"><span data-stu-id="484f6-1163">wellness professional</span></span>
- <span data-ttu-id="484f6-1164">patient referral</span><span class="sxs-lookup"><span data-stu-id="484f6-1164">patient referral</span></span>
- <span data-ttu-id="484f6-1165">health and wellness</span><span class="sxs-lookup"><span data-stu-id="484f6-1165">health and wellness</span></span>

#### <a name="keywordcanadaprovinces"></a><span data-ttu-id="484f6-1166">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="484f6-1166">Keyword_canada_provinces</span></span>

- <span data-ttu-id="484f6-1167">Nunavut</span><span class="sxs-lookup"><span data-stu-id="484f6-1167">Nunavut</span></span>
- <span data-ttu-id="484f6-1168">省</span><span class="sxs-lookup"><span data-stu-id="484f6-1168">Quebec</span></span>
- <span data-ttu-id="484f6-1169">Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="484f6-1169">Northwest Territories</span></span>
- <span data-ttu-id="484f6-1170">省</span><span class="sxs-lookup"><span data-stu-id="484f6-1170">Ontario</span></span>
- <span data-ttu-id="484f6-1171">British Columbia</span><span class="sxs-lookup"><span data-stu-id="484f6-1171">British Columbia</span></span>
- <span data-ttu-id="484f6-1172">Alberta</span><span class="sxs-lookup"><span data-stu-id="484f6-1172">Alberta</span></span>
- <span data-ttu-id="484f6-1173">彻</span><span class="sxs-lookup"><span data-stu-id="484f6-1173">Saskatchewan</span></span>
- <span data-ttu-id="484f6-1174">Manitoba</span><span class="sxs-lookup"><span data-stu-id="484f6-1174">Manitoba</span></span>
- <span data-ttu-id="484f6-1175">Yukon</span><span class="sxs-lookup"><span data-stu-id="484f6-1175">Yukon</span></span>
- <span data-ttu-id="484f6-1176">Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="484f6-1176">Newfoundland and Labrador</span></span>
- <span data-ttu-id="484f6-1177">New Brunswick</span><span class="sxs-lookup"><span data-stu-id="484f6-1177">New Brunswick</span></span>
- <span data-ttu-id="484f6-1178">Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="484f6-1178">Nova Scotia</span></span>
- <span data-ttu-id="484f6-1179">Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="484f6-1179">Prince Edward Island</span></span>
- <span data-ttu-id="484f6-1180">加拿大</span><span class="sxs-lookup"><span data-stu-id="484f6-1180">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="484f6-1181">加拿大社会保险号码</span><span class="sxs-lookup"><span data-stu-id="484f6-1181">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-1182">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-1182">Format</span></span>

<span data-ttu-id="484f6-1183">九个数字，包含可选连字符或空格</span><span class="sxs-lookup"><span data-stu-id="484f6-1183">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-1184">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-1184">Pattern</span></span>

<span data-ttu-id="484f6-1185">格式</span><span class="sxs-lookup"><span data-stu-id="484f6-1185">Formatted:</span></span>
- <span data-ttu-id="484f6-1186">三位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-1186">Three digits</span></span> 
- <span data-ttu-id="484f6-1187">连字符或空格</span><span class="sxs-lookup"><span data-stu-id="484f6-1187">A hyphen or space</span></span> 
- <span data-ttu-id="484f6-1188">三位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-1188">Three digits</span></span> 
- <span data-ttu-id="484f6-1189">连字符或空格</span><span class="sxs-lookup"><span data-stu-id="484f6-1189">A hyphen or space</span></span> 
- <span data-ttu-id="484f6-1190">三位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-1190">Three digits</span></span>

<span data-ttu-id="484f6-1191">未格式化: 9 个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-1191">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-1192">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-1192">Checksum</span></span>

<span data-ttu-id="484f6-1193">是</span><span class="sxs-lookup"><span data-stu-id="484f6-1193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-1194">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-1194">Definition</span></span>

<span data-ttu-id="484f6-1195">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-1195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-1196">函数 Func_canadian_sin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-1196">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-1197">至少两个以下任意组合：</span><span class="sxs-lookup"><span data-stu-id="484f6-1197">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="484f6-1198">找到 Keyword_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-1198">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="484f6-1199">找到 Keyword_sin_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-1199">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="484f6-1200">函数 Func_eu_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="484f6-1200">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="484f6-1201">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-1201">The checksum passes.</span></span>

<span data-ttu-id="484f6-1202">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-1202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-1203">函数 Func_unformatted_canadian_sin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-1203">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-1204">找到 Keyword_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-1204">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="484f6-1205">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-1205">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-1206">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-1206">Keywords</span></span>

#### <a name="keywordsin"></a><span data-ttu-id="484f6-1207">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="484f6-1207">Keyword_sin</span></span>

- <span data-ttu-id="484f6-1208">sin</span><span class="sxs-lookup"><span data-stu-id="484f6-1208">sin</span></span> 
- <span data-ttu-id="484f6-1209">social insurance</span><span class="sxs-lookup"><span data-stu-id="484f6-1209">social insurance</span></span> 
- <span data-ttu-id="484f6-1210">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="484f6-1210">numero d'assurance sociale</span></span> 
- <span data-ttu-id="484f6-1211">罪</span><span class="sxs-lookup"><span data-stu-id="484f6-1211">sins</span></span> 
- <span data-ttu-id="484f6-1212">ssn</span><span class="sxs-lookup"><span data-stu-id="484f6-1212">ssn</span></span> 
- <span data-ttu-id="484f6-1213">ssn</span><span class="sxs-lookup"><span data-stu-id="484f6-1213">ssns</span></span> 
- <span data-ttu-id="484f6-1214">social security</span><span class="sxs-lookup"><span data-stu-id="484f6-1214">social security</span></span> 
- <span data-ttu-id="484f6-1215">numero d'assurance social</span><span class="sxs-lookup"><span data-stu-id="484f6-1215">numero d'assurance social</span></span> 
- <span data-ttu-id="484f6-1216">national identification number</span><span class="sxs-lookup"><span data-stu-id="484f6-1216">national identification number</span></span> 
- <span data-ttu-id="484f6-1217">national id</span><span class="sxs-lookup"><span data-stu-id="484f6-1217">national id</span></span> 
- <span data-ttu-id="484f6-1218">sin</span><span class="sxs-lookup"><span data-stu-id="484f6-1218">sin#</span></span> 
- <span data-ttu-id="484f6-1219">soc ins</span><span class="sxs-lookup"><span data-stu-id="484f6-1219">soc ins</span></span> 
- <span data-ttu-id="484f6-1220">social ins</span><span class="sxs-lookup"><span data-stu-id="484f6-1220">social ins</span></span> 

#### <a name="keywordsincollaborative"></a><span data-ttu-id="484f6-1221">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="484f6-1221">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="484f6-1222">driver's license</span><span class="sxs-lookup"><span data-stu-id="484f6-1222">driver's license</span></span> 
- <span data-ttu-id="484f6-1223">drivers license</span><span class="sxs-lookup"><span data-stu-id="484f6-1223">drivers license</span></span> 
- <span data-ttu-id="484f6-1224">driver's licence</span><span class="sxs-lookup"><span data-stu-id="484f6-1224">driver's licence</span></span> 
- <span data-ttu-id="484f6-1225">drivers licence</span><span class="sxs-lookup"><span data-stu-id="484f6-1225">drivers licence</span></span> 
- <span data-ttu-id="484f6-1226">DOB</span><span class="sxs-lookup"><span data-stu-id="484f6-1226">DOB</span></span> 
- <span data-ttu-id="484f6-1227">出生日期</span><span class="sxs-lookup"><span data-stu-id="484f6-1227">Birthdate</span></span> 
- <span data-ttu-id="484f6-1228">生日</span><span class="sxs-lookup"><span data-stu-id="484f6-1228">Birthday</span></span> 
- <span data-ttu-id="484f6-1229">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="484f6-1229">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="484f6-1230">	智利身份证号</span><span class="sxs-lookup"><span data-stu-id="484f6-1230">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-1231">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-1231">Format</span></span>

<span data-ttu-id="484f6-1232">7-8 位数加上分隔符一个校验位或字母</span><span class="sxs-lookup"><span data-stu-id="484f6-1232">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-1233">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-1233">Pattern</span></span>

<span data-ttu-id="484f6-1234">7-8 个数字加分隔符：</span><span class="sxs-lookup"><span data-stu-id="484f6-1234">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="484f6-1235">1-2 个数字 </span><span class="sxs-lookup"><span data-stu-id="484f6-1235">1-2 digits</span></span> 
- <span data-ttu-id="484f6-1236">一个点 </span><span class="sxs-lookup"><span data-stu-id="484f6-1236">A period</span></span> 
- <span data-ttu-id="484f6-1237">三个数字 </span><span class="sxs-lookup"><span data-stu-id="484f6-1237">Three digits</span></span> 
- <span data-ttu-id="484f6-1238">一个点 </span><span class="sxs-lookup"><span data-stu-id="484f6-1238">A period</span></span> 
- <span data-ttu-id="484f6-1239">三个数字 </span><span class="sxs-lookup"><span data-stu-id="484f6-1239">Three digits</span></span> 
- <span data-ttu-id="484f6-1240">一个短划线 </span><span class="sxs-lookup"><span data-stu-id="484f6-1240">A dash</span></span> 
- <span data-ttu-id="484f6-1241">一个数字或字母（不区分大小写），是校验位</span><span class="sxs-lookup"><span data-stu-id="484f6-1241">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-1242">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-1242">Checksum</span></span>

<span data-ttu-id="484f6-1243">是</span><span class="sxs-lookup"><span data-stu-id="484f6-1243">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-1244">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-1244">Definition</span></span>

<span data-ttu-id="484f6-1245">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-1245">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-1246">函数 Func_chile_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-1246">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-1247">找到 Keyword_chile_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-1247">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="484f6-1248">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-1248">The checksum passes.</span></span>

<span data-ttu-id="484f6-1249">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-1249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-1250">函数 Func_chile_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-1250">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-1251">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-1251">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-1252">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-1252">Keywords</span></span>

#### <a name="keywordchileidcard"></a><span data-ttu-id="484f6-1253">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="484f6-1253">Keyword_chile_id_card</span></span>

- <span data-ttu-id="484f6-1254">National Identification Number</span><span class="sxs-lookup"><span data-stu-id="484f6-1254">National Identification Number</span></span> 
- <span data-ttu-id="484f6-1255">Identity card</span><span class="sxs-lookup"><span data-stu-id="484f6-1255">Identity card</span></span> 
- <span data-ttu-id="484f6-1256">ID</span><span class="sxs-lookup"><span data-stu-id="484f6-1256">ID</span></span> 
- <span data-ttu-id="484f6-1257">Id</span><span class="sxs-lookup"><span data-stu-id="484f6-1257">Identification</span></span> 
- <span data-ttu-id="484f6-1258">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="484f6-1258">Rol Único Nacional</span></span> 
- <span data-ttu-id="484f6-1259">以</span><span class="sxs-lookup"><span data-stu-id="484f6-1259">RUN</span></span> 
- <span data-ttu-id="484f6-1260">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="484f6-1260">Rol Único Tributario</span></span> 
- <span data-ttu-id="484f6-1261">墨守成规</span><span class="sxs-lookup"><span data-stu-id="484f6-1261">RUT</span></span> 
- <span data-ttu-id="484f6-1262">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="484f6-1262">Cédula de Identidad</span></span> 
- <span data-ttu-id="484f6-1263">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="484f6-1263">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="484f6-1264">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="484f6-1264">Tarjeta de identificación</span></span> 
- <span data-ttu-id="484f6-1265">Identificación</span><span class="sxs-lookup"><span data-stu-id="484f6-1265">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="484f6-1266">	中国居民身份证号</span><span class="sxs-lookup"><span data-stu-id="484f6-1266">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-1267">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-1267">Format</span></span>

<span data-ttu-id="484f6-1268">18 个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-1268">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-1269">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-1269">Pattern</span></span>

<span data-ttu-id="484f6-1270">18 个数字：</span><span class="sxs-lookup"><span data-stu-id="484f6-1270">18 digits:</span></span>
- <span data-ttu-id="484f6-1271">其中六个数字是地址代码 </span><span class="sxs-lookup"><span data-stu-id="484f6-1271">Six digits which are an address code</span></span> 
- <span data-ttu-id="484f6-1272">八个数字，采用  YYYYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="484f6-1272">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="484f6-1273">三个数字，是顺序代码 </span><span class="sxs-lookup"><span data-stu-id="484f6-1273">Three digits which are an order code</span></span> 
- <span data-ttu-id="484f6-1274">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="484f6-1274">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-1275">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-1275">Checksum</span></span>

<span data-ttu-id="484f6-1276">是</span><span class="sxs-lookup"><span data-stu-id="484f6-1276">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-1277">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-1277">Definition</span></span>

<span data-ttu-id="484f6-1278">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-1278">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-1279">函数 Func_china_resident_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-1279">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-1280">找到 Keyword_china_resident_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-1280">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="484f6-1281">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-1281">The checksum passes.</span></span>

<span data-ttu-id="484f6-1282">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-1282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-1283">函数 Func_china_resident_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-1283">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-1284">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-1284">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-1285">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-1285">Keywords</span></span>

### <a name="keywordchinaresidentid"></a><span data-ttu-id="484f6-1286">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="484f6-1286">Keyword_china_resident_id</span></span>

- <span data-ttu-id="484f6-1287">Resident Identity Card</span><span class="sxs-lookup"><span data-stu-id="484f6-1287">Resident Identity Card</span></span> 
- <span data-ttu-id="484f6-1288">台湾</span><span class="sxs-lookup"><span data-stu-id="484f6-1288">PRC</span></span> 
- <span data-ttu-id="484f6-1289">National Identification Card</span><span class="sxs-lookup"><span data-stu-id="484f6-1289">National Identification Card</span></span> 
- <span data-ttu-id="484f6-1290">身份证</span><span class="sxs-lookup"><span data-stu-id="484f6-1290">身份证</span></span> 
- <span data-ttu-id="484f6-1291">居民 身份证</span><span class="sxs-lookup"><span data-stu-id="484f6-1291">居民 身份证</span></span> 
- <span data-ttu-id="484f6-1292">居民身份证</span><span class="sxs-lookup"><span data-stu-id="484f6-1292">居民身份证</span></span> 
- <span data-ttu-id="484f6-1293">鉴定</span><span class="sxs-lookup"><span data-stu-id="484f6-1293">鉴定</span></span> 
- <span data-ttu-id="484f6-1294">身分證</span><span class="sxs-lookup"><span data-stu-id="484f6-1294">身分證</span></span> 
- <span data-ttu-id="484f6-1295">居民身份證</span><span class="sxs-lookup"><span data-stu-id="484f6-1295">居民 身份證</span></span>
- <span data-ttu-id="484f6-1296">鑑定</span><span class="sxs-lookup"><span data-stu-id="484f6-1296">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="484f6-1297">信用卡号</span><span class="sxs-lookup"><span data-stu-id="484f6-1297">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-1298">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-1298">Format</span></span>

<span data-ttu-id="484f6-1299">16个数字, 可以是格式化或无格式 (dddddddddddddddd), 并且必须通过 Luhn 测试。</span><span class="sxs-lookup"><span data-stu-id="484f6-1299">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-1300">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-1300">Pattern</span></span>

<span data-ttu-id="484f6-1301">非常复杂且强大的模式，检测到来自世界各地所有重要品牌的卡，包括 Visa、万事达卡、发现卡、JCB卡、美国运通卡、礼品卡以及大莱卡。</span><span class="sxs-lookup"><span data-stu-id="484f6-1301">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-1302">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-1302">Checksum</span></span>

<span data-ttu-id="484f6-1303">是，Luhn 校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-1303">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-1304">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-1304">Definition</span></span>

<span data-ttu-id="484f6-1305">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-1305">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-1306">函数 Func_credit_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-1306">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-1307">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="484f6-1307">One of the following is true:</span></span>
    - <span data-ttu-id="484f6-1308">找到 Keyword_cc_verification 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-1308">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="484f6-1309">找到 Keyword_cc_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-1309">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="484f6-1310">函数 Func_expiration_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="484f6-1310">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="484f6-1311">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-1311">The checksum passes.</span></span>

<span data-ttu-id="484f6-1312">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-1312">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-1313">函数 Func_credit_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-1313">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-1314">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-1314">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-1315">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-1315">Keywords</span></span>

#### <a name="keywordccverification"></a><span data-ttu-id="484f6-1316">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="484f6-1316">Keyword_cc_verification</span></span>

- <span data-ttu-id="484f6-1317">card verification</span><span class="sxs-lookup"><span data-stu-id="484f6-1317">card verification</span></span>
- <span data-ttu-id="484f6-1318">card identification number</span><span class="sxs-lookup"><span data-stu-id="484f6-1318">card identification number</span></span>
- <span data-ttu-id="484f6-1319">cvn</span><span class="sxs-lookup"><span data-stu-id="484f6-1319">cvn</span></span>
- <span data-ttu-id="484f6-1320">cid</span><span class="sxs-lookup"><span data-stu-id="484f6-1320">cid</span></span>
- <span data-ttu-id="484f6-1321">cvc2</span><span class="sxs-lookup"><span data-stu-id="484f6-1321">cvc2</span></span>
- <span data-ttu-id="484f6-1322">cvv2</span><span class="sxs-lookup"><span data-stu-id="484f6-1322">cvv2</span></span>
- <span data-ttu-id="484f6-1323">pin block</span><span class="sxs-lookup"><span data-stu-id="484f6-1323">pin block</span></span>
- <span data-ttu-id="484f6-1324">security code</span><span class="sxs-lookup"><span data-stu-id="484f6-1324">security code</span></span>
- <span data-ttu-id="484f6-1325">security number</span><span class="sxs-lookup"><span data-stu-id="484f6-1325">security number</span></span>
- <span data-ttu-id="484f6-1326">security no</span><span class="sxs-lookup"><span data-stu-id="484f6-1326">security no</span></span>
- <span data-ttu-id="484f6-1327">issue number</span><span class="sxs-lookup"><span data-stu-id="484f6-1327">issue number</span></span>
- <span data-ttu-id="484f6-1328">issue no</span><span class="sxs-lookup"><span data-stu-id="484f6-1328">issue no</span></span>
- <span data-ttu-id="484f6-1329">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="484f6-1329">cryptogramme</span></span>
- <span data-ttu-id="484f6-1330">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="484f6-1330">numéro de sécurité</span></span>
- <span data-ttu-id="484f6-1331">numero de securite</span><span class="sxs-lookup"><span data-stu-id="484f6-1331">numero de securite</span></span>
- <span data-ttu-id="484f6-1332">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="484f6-1332">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="484f6-1333">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="484f6-1333">kreditkartenprufnummer</span></span>
- <span data-ttu-id="484f6-1334">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="484f6-1334">prüfziffer</span></span>
- <span data-ttu-id="484f6-1335">prufziffer</span><span class="sxs-lookup"><span data-stu-id="484f6-1335">prufziffer</span></span>
- <span data-ttu-id="484f6-1336">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="484f6-1336">sicherheits Kode</span></span>
- <span data-ttu-id="484f6-1337">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="484f6-1337">sicherheitscode</span></span>
- <span data-ttu-id="484f6-1338">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="484f6-1338">sicherheitsnummer</span></span>
- <span data-ttu-id="484f6-1339">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="484f6-1339">verfalldatum</span></span>
- <span data-ttu-id="484f6-1340">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="484f6-1340">codice di verifica</span></span>
- <span data-ttu-id="484f6-1341">货.</span><span class="sxs-lookup"><span data-stu-id="484f6-1341">cod.</span></span> <span data-ttu-id="484f6-1342">sicurezza</span><span class="sxs-lookup"><span data-stu-id="484f6-1342">sicurezza</span></span>
- <span data-ttu-id="484f6-1343">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="484f6-1343">cod sicurezza</span></span>
- <span data-ttu-id="484f6-1344">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="484f6-1344">n autorizzazione</span></span>
- <span data-ttu-id="484f6-1345">código</span><span class="sxs-lookup"><span data-stu-id="484f6-1345">código</span></span>
- <span data-ttu-id="484f6-1346">codigo</span><span class="sxs-lookup"><span data-stu-id="484f6-1346">codigo</span></span>
- <span data-ttu-id="484f6-1347">货.</span><span class="sxs-lookup"><span data-stu-id="484f6-1347">cod.</span></span> <span data-ttu-id="484f6-1348">seg</span><span class="sxs-lookup"><span data-stu-id="484f6-1348">seg</span></span>
- <span data-ttu-id="484f6-1349">cod seg</span><span class="sxs-lookup"><span data-stu-id="484f6-1349">cod seg</span></span>
- <span data-ttu-id="484f6-1350">código de segurança</span><span class="sxs-lookup"><span data-stu-id="484f6-1350">código de segurança</span></span>
- <span data-ttu-id="484f6-1351">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="484f6-1351">codigo de seguranca</span></span>
- <span data-ttu-id="484f6-1352">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="484f6-1352">codigo de segurança</span></span>
- <span data-ttu-id="484f6-1353">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="484f6-1353">código de seguranca</span></span>
- <span data-ttu-id="484f6-1354">cód.</span><span class="sxs-lookup"><span data-stu-id="484f6-1354">cód.</span></span> <span data-ttu-id="484f6-1355">segurança</span><span class="sxs-lookup"><span data-stu-id="484f6-1355">segurança</span></span>
- <span data-ttu-id="484f6-1356">货.</span><span class="sxs-lookup"><span data-stu-id="484f6-1356">cod.</span></span> <span data-ttu-id="484f6-1357">seguranca 货到付款。</span><span class="sxs-lookup"><span data-stu-id="484f6-1357">seguranca cod.</span></span> <span data-ttu-id="484f6-1358">segurança</span><span class="sxs-lookup"><span data-stu-id="484f6-1358">segurança</span></span>
- <span data-ttu-id="484f6-1359">cód.</span><span class="sxs-lookup"><span data-stu-id="484f6-1359">cód.</span></span> <span data-ttu-id="484f6-1360">seguranca</span><span class="sxs-lookup"><span data-stu-id="484f6-1360">seguranca</span></span>
- <span data-ttu-id="484f6-1361">cód segurança</span><span class="sxs-lookup"><span data-stu-id="484f6-1361">cód segurança</span></span>
- <span data-ttu-id="484f6-1362">货到付款 seguranca 货到付款 segurança</span><span class="sxs-lookup"><span data-stu-id="484f6-1362">cod seguranca cod segurança</span></span>
- <span data-ttu-id="484f6-1363">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="484f6-1363">cód seguranca</span></span>
- <span data-ttu-id="484f6-1364">número de verificação</span><span class="sxs-lookup"><span data-stu-id="484f6-1364">número de verificação</span></span>
- <span data-ttu-id="484f6-1365">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="484f6-1365">numero de verificacao</span></span>
- <span data-ttu-id="484f6-1366">ablauf</span><span class="sxs-lookup"><span data-stu-id="484f6-1366">ablauf</span></span>
- <span data-ttu-id="484f6-1367">gültig bis</span><span class="sxs-lookup"><span data-stu-id="484f6-1367">gültig bis</span></span>
- <span data-ttu-id="484f6-1368">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="484f6-1368">gültigkeitsdatum</span></span>
- <span data-ttu-id="484f6-1369">gultig bis</span><span class="sxs-lookup"><span data-stu-id="484f6-1369">gultig bis</span></span>
- <span data-ttu-id="484f6-1370">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="484f6-1370">gultigkeitsdatum</span></span>
- <span data-ttu-id="484f6-1371">scadenza</span><span class="sxs-lookup"><span data-stu-id="484f6-1371">scadenza</span></span>
- <span data-ttu-id="484f6-1372">data scad</span><span class="sxs-lookup"><span data-stu-id="484f6-1372">data scad</span></span>
- <span data-ttu-id="484f6-1373">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="484f6-1373">fecha de expiracion</span></span>
- <span data-ttu-id="484f6-1374">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="484f6-1374">fecha de venc</span></span>
- <span data-ttu-id="484f6-1375">vencimiento</span><span class="sxs-lookup"><span data-stu-id="484f6-1375">vencimiento</span></span>
- <span data-ttu-id="484f6-1376">válido hasta</span><span class="sxs-lookup"><span data-stu-id="484f6-1376">válido hasta</span></span>
- <span data-ttu-id="484f6-1377">valido hasta</span><span class="sxs-lookup"><span data-stu-id="484f6-1377">valido hasta</span></span>
- <span data-ttu-id="484f6-1378">vto</span><span class="sxs-lookup"><span data-stu-id="484f6-1378">vto</span></span>
- <span data-ttu-id="484f6-1379">data de expiração</span><span class="sxs-lookup"><span data-stu-id="484f6-1379">data de expiração</span></span>
- <span data-ttu-id="484f6-1380">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="484f6-1380">data de expiracao</span></span>
- <span data-ttu-id="484f6-1381">data em que expira</span><span class="sxs-lookup"><span data-stu-id="484f6-1381">data em que expira</span></span>
- <span data-ttu-id="484f6-1382">validade</span><span class="sxs-lookup"><span data-stu-id="484f6-1382">validade</span></span>
- <span data-ttu-id="484f6-1383">valor</span><span class="sxs-lookup"><span data-stu-id="484f6-1383">valor</span></span>
- <span data-ttu-id="484f6-1384">vencimento</span><span class="sxs-lookup"><span data-stu-id="484f6-1384">vencimento</span></span>
- <span data-ttu-id="484f6-1385">Venc</span><span class="sxs-lookup"><span data-stu-id="484f6-1385">Venc</span></span> 

#### <a name="keywordccname"></a><span data-ttu-id="484f6-1386">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="484f6-1386">Keyword_cc_name</span></span>

- <span data-ttu-id="484f6-1387">amex</span><span class="sxs-lookup"><span data-stu-id="484f6-1387">amex</span></span>
- <span data-ttu-id="484f6-1388">american express</span><span class="sxs-lookup"><span data-stu-id="484f6-1388">american express</span></span>
- <span data-ttu-id="484f6-1389">americanexpress</span><span class="sxs-lookup"><span data-stu-id="484f6-1389">americanexpress</span></span>
- <span data-ttu-id="484f6-1390">反之</span><span class="sxs-lookup"><span data-stu-id="484f6-1390">Visa</span></span>
- <span data-ttu-id="484f6-1391">mastercard</span><span class="sxs-lookup"><span data-stu-id="484f6-1391">mastercard</span></span>
- <span data-ttu-id="484f6-1392">Master Card</span><span class="sxs-lookup"><span data-stu-id="484f6-1392">master card</span></span>
- <span data-ttu-id="484f6-1393">emc</span><span class="sxs-lookup"><span data-stu-id="484f6-1393">mc</span></span> 
- <span data-ttu-id="484f6-1394">mastercards</span><span class="sxs-lookup"><span data-stu-id="484f6-1394">mastercards</span></span>
- <span data-ttu-id="484f6-1395">master cards</span><span class="sxs-lookup"><span data-stu-id="484f6-1395">master cards</span></span>
- <span data-ttu-id="484f6-1396">diner's Club</span><span class="sxs-lookup"><span data-stu-id="484f6-1396">diner's Club</span></span>
- <span data-ttu-id="484f6-1397">diners club</span><span class="sxs-lookup"><span data-stu-id="484f6-1397">diners club</span></span>
- <span data-ttu-id="484f6-1398">dinersclub</span><span class="sxs-lookup"><span data-stu-id="484f6-1398">dinersclub</span></span>
- <span data-ttu-id="484f6-1399">discover card</span><span class="sxs-lookup"><span data-stu-id="484f6-1399">discover card</span></span>
- <span data-ttu-id="484f6-1400">discovercard</span><span class="sxs-lookup"><span data-stu-id="484f6-1400">discovercard</span></span>
- <span data-ttu-id="484f6-1401">discover cards</span><span class="sxs-lookup"><span data-stu-id="484f6-1401">discover cards</span></span>
- <span data-ttu-id="484f6-1402">JCB</span><span class="sxs-lookup"><span data-stu-id="484f6-1402">JCB</span></span>
- <span data-ttu-id="484f6-1403">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="484f6-1403">japanese card bureau</span></span>
- <span data-ttu-id="484f6-1404">carte blanche</span><span class="sxs-lookup"><span data-stu-id="484f6-1404">carte blanche</span></span>
- <span data-ttu-id="484f6-1405">carteblanche</span><span class="sxs-lookup"><span data-stu-id="484f6-1405">carteblanche</span></span>
- <span data-ttu-id="484f6-1406">credit card</span><span class="sxs-lookup"><span data-stu-id="484f6-1406">credit card</span></span>
- <span data-ttu-id="484f6-1407">收件人</span><span class="sxs-lookup"><span data-stu-id="484f6-1407">cc#</span></span>
- <span data-ttu-id="484f6-1408">cc #:</span><span class="sxs-lookup"><span data-stu-id="484f6-1408">cc#:</span></span>
- <span data-ttu-id="484f6-1409">expiration date</span><span class="sxs-lookup"><span data-stu-id="484f6-1409">expiration date</span></span>
- <span data-ttu-id="484f6-1410">exp date</span><span class="sxs-lookup"><span data-stu-id="484f6-1410">exp date</span></span>
- <span data-ttu-id="484f6-1411">expiry date</span><span class="sxs-lookup"><span data-stu-id="484f6-1411">expiry date</span></span>
- <span data-ttu-id="484f6-1412">date d’expiration</span><span class="sxs-lookup"><span data-stu-id="484f6-1412">date d’expiration</span></span>
- <span data-ttu-id="484f6-1413">date d'exp</span><span class="sxs-lookup"><span data-stu-id="484f6-1413">date d'exp</span></span>
- <span data-ttu-id="484f6-1414">date expiration</span><span class="sxs-lookup"><span data-stu-id="484f6-1414">date expiration</span></span>
- <span data-ttu-id="484f6-1415">bank card</span><span class="sxs-lookup"><span data-stu-id="484f6-1415">bank card</span></span>
- <span data-ttu-id="484f6-1416">bankcard</span><span class="sxs-lookup"><span data-stu-id="484f6-1416">bankcard</span></span>
- <span data-ttu-id="484f6-1417">card number</span><span class="sxs-lookup"><span data-stu-id="484f6-1417">card number</span></span>
- <span data-ttu-id="484f6-1418">card num</span><span class="sxs-lookup"><span data-stu-id="484f6-1418">card num</span></span>
- <span data-ttu-id="484f6-1419">cardnumber</span><span class="sxs-lookup"><span data-stu-id="484f6-1419">cardnumber</span></span>
- <span data-ttu-id="484f6-1420">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="484f6-1420">cardnumbers</span></span>
- <span data-ttu-id="484f6-1421">card numbers</span><span class="sxs-lookup"><span data-stu-id="484f6-1421">card numbers</span></span>
- <span data-ttu-id="484f6-1422">creditcard</span><span class="sxs-lookup"><span data-stu-id="484f6-1422">creditcard</span></span>
- <span data-ttu-id="484f6-1423">credit cards</span><span class="sxs-lookup"><span data-stu-id="484f6-1423">credit cards</span></span>
- <span data-ttu-id="484f6-1424">creditcards</span><span class="sxs-lookup"><span data-stu-id="484f6-1424">creditcards</span></span>
- <span data-ttu-id="484f6-1425">ccn</span><span class="sxs-lookup"><span data-stu-id="484f6-1425">ccn</span></span>
- <span data-ttu-id="484f6-1426">card holder</span><span class="sxs-lookup"><span data-stu-id="484f6-1426">card holder</span></span>
- <span data-ttu-id="484f6-1427">持卡人</span><span class="sxs-lookup"><span data-stu-id="484f6-1427">cardholder</span></span>
- <span data-ttu-id="484f6-1428">card holders</span><span class="sxs-lookup"><span data-stu-id="484f6-1428">card holders</span></span>
- <span data-ttu-id="484f6-1429">cardholders</span><span class="sxs-lookup"><span data-stu-id="484f6-1429">cardholders</span></span>
- <span data-ttu-id="484f6-1430">check card</span><span class="sxs-lookup"><span data-stu-id="484f6-1430">check card</span></span>
- <span data-ttu-id="484f6-1431">checkcard</span><span class="sxs-lookup"><span data-stu-id="484f6-1431">checkcard</span></span>
- <span data-ttu-id="484f6-1432">check cards</span><span class="sxs-lookup"><span data-stu-id="484f6-1432">check cards</span></span>
- <span data-ttu-id="484f6-1433">checkcards</span><span class="sxs-lookup"><span data-stu-id="484f6-1433">checkcards</span></span>
- <span data-ttu-id="484f6-1434">debit card</span><span class="sxs-lookup"><span data-stu-id="484f6-1434">debit card</span></span>
- <span data-ttu-id="484f6-1435">debitcard</span><span class="sxs-lookup"><span data-stu-id="484f6-1435">debitcard</span></span>
- <span data-ttu-id="484f6-1436">debit cards</span><span class="sxs-lookup"><span data-stu-id="484f6-1436">debit cards</span></span>
- <span data-ttu-id="484f6-1437">debitcards</span><span class="sxs-lookup"><span data-stu-id="484f6-1437">debitcards</span></span>
- <span data-ttu-id="484f6-1438">atm card</span><span class="sxs-lookup"><span data-stu-id="484f6-1438">atm card</span></span>
- <span data-ttu-id="484f6-1439">atmcard</span><span class="sxs-lookup"><span data-stu-id="484f6-1439">atmcard</span></span>
- <span data-ttu-id="484f6-1440">atm cards</span><span class="sxs-lookup"><span data-stu-id="484f6-1440">atm cards</span></span>
- <span data-ttu-id="484f6-1441">atmcards</span><span class="sxs-lookup"><span data-stu-id="484f6-1441">atmcards</span></span>
- <span data-ttu-id="484f6-1442">enroute</span><span class="sxs-lookup"><span data-stu-id="484f6-1442">enroute</span></span>
- <span data-ttu-id="484f6-1443">en route</span><span class="sxs-lookup"><span data-stu-id="484f6-1443">en route</span></span>
- <span data-ttu-id="484f6-1444">card type</span><span class="sxs-lookup"><span data-stu-id="484f6-1444">card type</span></span>
- <span data-ttu-id="484f6-1445">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="484f6-1445">carte bancaire</span></span>
- <span data-ttu-id="484f6-1446">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="484f6-1446">carte de crédit</span></span>
- <span data-ttu-id="484f6-1447">carte de credit</span><span class="sxs-lookup"><span data-stu-id="484f6-1447">carte de credit</span></span>
- <span data-ttu-id="484f6-1448">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="484f6-1448">numéro de carte</span></span>
- <span data-ttu-id="484f6-1449">numero de carte</span><span class="sxs-lookup"><span data-stu-id="484f6-1449">numero de carte</span></span>
- <span data-ttu-id="484f6-1450">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="484f6-1450">nº de la carte</span></span>
- <span data-ttu-id="484f6-1451">nº de carte</span><span class="sxs-lookup"><span data-stu-id="484f6-1451">nº de carte</span></span>
- <span data-ttu-id="484f6-1452">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="484f6-1452">kreditkarte</span></span>
- <span data-ttu-id="484f6-1453">karte</span><span class="sxs-lookup"><span data-stu-id="484f6-1453">karte</span></span>
- <span data-ttu-id="484f6-1454">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="484f6-1454">karteninhaber</span></span>
- <span data-ttu-id="484f6-1455">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="484f6-1455">karteninhabers</span></span>
- <span data-ttu-id="484f6-1456">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="484f6-1456">kreditkarteninhaber</span></span>
- <span data-ttu-id="484f6-1457">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="484f6-1457">kreditkarteninstitut</span></span>
- <span data-ttu-id="484f6-1458">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="484f6-1458">kreditkartentyp</span></span>
- <span data-ttu-id="484f6-1459">eigentümername</span><span class="sxs-lookup"><span data-stu-id="484f6-1459">eigentümername</span></span>
- <span data-ttu-id="484f6-1460">kartennr</span><span class="sxs-lookup"><span data-stu-id="484f6-1460">kartennr</span></span> 
- <span data-ttu-id="484f6-1461">kartennummer</span><span class="sxs-lookup"><span data-stu-id="484f6-1461">kartennummer</span></span>
- <span data-ttu-id="484f6-1462">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="484f6-1462">kreditkartennummer</span></span>
- <span data-ttu-id="484f6-1463">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="484f6-1463">kreditkarten-nummer</span></span>
- <span data-ttu-id="484f6-1464">carta di credito</span><span class="sxs-lookup"><span data-stu-id="484f6-1464">carta di credito</span></span>
- <span data-ttu-id="484f6-1465">carta credito</span><span class="sxs-lookup"><span data-stu-id="484f6-1465">carta credito</span></span>
- <span data-ttu-id="484f6-1466">carta</span><span class="sxs-lookup"><span data-stu-id="484f6-1466">carta</span></span>
- <span data-ttu-id="484f6-1467">n carta</span><span class="sxs-lookup"><span data-stu-id="484f6-1467">n carta</span></span>
- <span data-ttu-id="484f6-1468">führerschein-nr.</span><span class="sxs-lookup"><span data-stu-id="484f6-1468">nr.</span></span> <span data-ttu-id="484f6-1469">carta</span><span class="sxs-lookup"><span data-stu-id="484f6-1469">carta</span></span>
- <span data-ttu-id="484f6-1470">nr carta</span><span class="sxs-lookup"><span data-stu-id="484f6-1470">nr carta</span></span>
- <span data-ttu-id="484f6-1471">numero carta</span><span class="sxs-lookup"><span data-stu-id="484f6-1471">numero carta</span></span>
- <span data-ttu-id="484f6-1472">numero della carta</span><span class="sxs-lookup"><span data-stu-id="484f6-1472">numero della carta</span></span>
- <span data-ttu-id="484f6-1473">numero di carta</span><span class="sxs-lookup"><span data-stu-id="484f6-1473">numero di carta</span></span>
- <span data-ttu-id="484f6-1474">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="484f6-1474">tarjeta credito</span></span>
- <span data-ttu-id="484f6-1475">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="484f6-1475">tarjeta de credito</span></span>
- <span data-ttu-id="484f6-1476">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="484f6-1476">tarjeta crédito</span></span>
- <span data-ttu-id="484f6-1477">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="484f6-1477">tarjeta de crédito</span></span>
- <span data-ttu-id="484f6-1478">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="484f6-1478">tarjeta de atm</span></span>
- <span data-ttu-id="484f6-1479">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="484f6-1479">tarjeta atm</span></span>
- <span data-ttu-id="484f6-1480">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="484f6-1480">tarjeta debito</span></span>
- <span data-ttu-id="484f6-1481">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="484f6-1481">tarjeta de debito</span></span>
- <span data-ttu-id="484f6-1482">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="484f6-1482">tarjeta débito</span></span>
- <span data-ttu-id="484f6-1483">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="484f6-1483">tarjeta de débito</span></span>
- <span data-ttu-id="484f6-1484">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="484f6-1484">nº de tarjeta</span></span>
- <span data-ttu-id="484f6-1485">不。</span><span class="sxs-lookup"><span data-stu-id="484f6-1485">no.</span></span> <span data-ttu-id="484f6-1486">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="484f6-1486">de tarjeta</span></span>
- <span data-ttu-id="484f6-1487">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="484f6-1487">no de tarjeta</span></span>
- <span data-ttu-id="484f6-1488">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="484f6-1488">numero de tarjeta</span></span>
- <span data-ttu-id="484f6-1489">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="484f6-1489">número de tarjeta</span></span>
- <span data-ttu-id="484f6-1490">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="484f6-1490">tarjeta no</span></span>
- <span data-ttu-id="484f6-1491">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="484f6-1491">tarjetahabiente</span></span>
- <span data-ttu-id="484f6-1492">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="484f6-1492">cartão de crédito</span></span>
- <span data-ttu-id="484f6-1493">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="484f6-1493">cartão de credito</span></span>
- <span data-ttu-id="484f6-1494">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="484f6-1494">cartao de crédito</span></span>
- <span data-ttu-id="484f6-1495">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="484f6-1495">cartao de credito</span></span>
- <span data-ttu-id="484f6-1496">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="484f6-1496">cartão de débito</span></span>
- <span data-ttu-id="484f6-1497">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="484f6-1497">cartao de débito</span></span>
- <span data-ttu-id="484f6-1498">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="484f6-1498">cartão de debito</span></span>
- <span data-ttu-id="484f6-1499">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="484f6-1499">cartao de debito</span></span>
- <span data-ttu-id="484f6-1500">débito automático</span><span class="sxs-lookup"><span data-stu-id="484f6-1500">débito automático</span></span>
- <span data-ttu-id="484f6-1501">debito automatico</span><span class="sxs-lookup"><span data-stu-id="484f6-1501">debito automatico</span></span>
- <span data-ttu-id="484f6-1502">número do cartão</span><span class="sxs-lookup"><span data-stu-id="484f6-1502">número do cartão</span></span>
- <span data-ttu-id="484f6-1503">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="484f6-1503">numero do cartão</span></span> 
- <span data-ttu-id="484f6-1504">número do cartao</span><span class="sxs-lookup"><span data-stu-id="484f6-1504">número do cartao</span></span>
- <span data-ttu-id="484f6-1505">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="484f6-1505">numero do cartao</span></span>
- <span data-ttu-id="484f6-1506">número de cartão</span><span class="sxs-lookup"><span data-stu-id="484f6-1506">número de cartão</span></span>
- <span data-ttu-id="484f6-1507">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="484f6-1507">numero de cartão</span></span>
- <span data-ttu-id="484f6-1508">número de cartao</span><span class="sxs-lookup"><span data-stu-id="484f6-1508">número de cartao</span></span>
- <span data-ttu-id="484f6-1509">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="484f6-1509">numero de cartao</span></span>
- <span data-ttu-id="484f6-1510">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="484f6-1510">nº do cartão</span></span>
- <span data-ttu-id="484f6-1511">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="484f6-1511">nº do cartao</span></span>
- <span data-ttu-id="484f6-1512">n º。</span><span class="sxs-lookup"><span data-stu-id="484f6-1512">nº.</span></span> <span data-ttu-id="484f6-1513">do cartão</span><span class="sxs-lookup"><span data-stu-id="484f6-1513">do cartão</span></span>
- <span data-ttu-id="484f6-1514">no do cartão</span><span class="sxs-lookup"><span data-stu-id="484f6-1514">no do cartão</span></span>
- <span data-ttu-id="484f6-1515">no do cartao</span><span class="sxs-lookup"><span data-stu-id="484f6-1515">no do cartao</span></span>
- <span data-ttu-id="484f6-1516">不。</span><span class="sxs-lookup"><span data-stu-id="484f6-1516">no.</span></span> <span data-ttu-id="484f6-1517">do cartão</span><span class="sxs-lookup"><span data-stu-id="484f6-1517">do cartão</span></span>
- <span data-ttu-id="484f6-1518">不。</span><span class="sxs-lookup"><span data-stu-id="484f6-1518">no.</span></span> <span data-ttu-id="484f6-1519">do cartao</span><span class="sxs-lookup"><span data-stu-id="484f6-1519">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="484f6-1520">	克罗地亚身份证号</span><span class="sxs-lookup"><span data-stu-id="484f6-1520">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-1521">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-1521">Format</span></span>

<span data-ttu-id="484f6-1522">九个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-1522">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-1523">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-1523">Pattern</span></span>

<span data-ttu-id="484f6-1524">九个连续的数字</span><span class="sxs-lookup"><span data-stu-id="484f6-1524">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-1525">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-1525">Checksum</span></span>

<span data-ttu-id="484f6-1526">否</span><span class="sxs-lookup"><span data-stu-id="484f6-1526">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-1527">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-1527">Definition</span></span>

<span data-ttu-id="484f6-1528">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-1528">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-1529">函数 Func_croatia_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-1529">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-1530">找到 Keyword_croatia_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-1530">A keyword from Keyword_croatia_id_card is found.</span></span>

```
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="484f6-1531">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-1531">Keywords</span></span>

#### <a name="keywordcroatiaidcard"></a><span data-ttu-id="484f6-1532">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="484f6-1532">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="484f6-1533">Croatian identity card</span><span class="sxs-lookup"><span data-stu-id="484f6-1533">Croatian identity card</span></span>
- <span data-ttu-id="484f6-1534">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="484f6-1534">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="484f6-1535">	Croatia Personal Identification (OIB) Number</span><span class="sxs-lookup"><span data-stu-id="484f6-1535">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-1536">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-1536">Format</span></span>

<span data-ttu-id="484f6-1537">11 个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-1537">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-1538">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-1538">Pattern</span></span>

<span data-ttu-id="484f6-1539">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="484f6-1539">11 digits:</span></span>
- <span data-ttu-id="484f6-1540">10 个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-1540">10 digits</span></span> 
- <span data-ttu-id="484f6-1541">最后一个数字是用于国际数据交换目的的校验位, 字母 HR 将加上11位数字。</span><span class="sxs-lookup"><span data-stu-id="484f6-1541">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-1542">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-1542">Checksum</span></span>

<span data-ttu-id="484f6-1543">是</span><span class="sxs-lookup"><span data-stu-id="484f6-1543">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-1544">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-1544">Definition</span></span>

<span data-ttu-id="484f6-1545">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-1545">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-1546">函数 Func_croatia_oib_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-1546">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-1547">找到 Keyword_croatia_oib_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-1547">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="484f6-1548">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-1548">The checksum passes.</span></span>

<span data-ttu-id="484f6-1549">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-1549">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-1550">函数 Func_croatia_oib_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-1550">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-1551">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-1551">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-1552">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-1552">Keywords</span></span>

#### <a name="keywordcroatiaoibnumber"></a><span data-ttu-id="484f6-1553">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="484f6-1553">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="484f6-1554">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="484f6-1554">Personal Identification Number</span></span>
- <span data-ttu-id="484f6-1555">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="484f6-1555">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="484f6-1556">OIB</span><span class="sxs-lookup"><span data-stu-id="484f6-1556">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="484f6-1557">捷克个人识别码</span><span class="sxs-lookup"><span data-stu-id="484f6-1557">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-1558">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-1558">Format</span></span>

<span data-ttu-id="484f6-1559">9个带可选正斜杠 (旧格式) 的数字, 带可选正斜杠的10个数字 (新的格式)</span><span class="sxs-lookup"><span data-stu-id="484f6-1559">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-1560">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-1560">Pattern</span></span>

<span data-ttu-id="484f6-1561">9个数字 (旧格式):</span><span class="sxs-lookup"><span data-stu-id="484f6-1561">Nine digits (old format):</span></span>
- <span data-ttu-id="484f6-1562">九个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-1562">Nine digits</span></span>

<span data-ttu-id="484f6-1563">OR</span><span class="sxs-lookup"><span data-stu-id="484f6-1563">OR</span></span>

- <span data-ttu-id="484f6-1564">代表出生日期的六个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-1564">Six digits that represent date of birth</span></span>
- <span data-ttu-id="484f6-1565">一个正斜杠 </span><span class="sxs-lookup"><span data-stu-id="484f6-1565">A forward slash</span></span>
- <span data-ttu-id="484f6-1566">三位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-1566">Three digits</span></span>

<span data-ttu-id="484f6-1567">10个数字 (新格式):</span><span class="sxs-lookup"><span data-stu-id="484f6-1567">10 digits (new format):</span></span>
- <span data-ttu-id="484f6-1568">10 个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-1568">10 digits</span></span>

<span data-ttu-id="484f6-1569">OR</span><span class="sxs-lookup"><span data-stu-id="484f6-1569">OR</span></span>

- <span data-ttu-id="484f6-1570">代表出生日期的六个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-1570">Six digits that represent date of birth</span></span>
- <span data-ttu-id="484f6-1571">一个正斜杠 </span><span class="sxs-lookup"><span data-stu-id="484f6-1571">A forward slash</span></span> 
- <span data-ttu-id="484f6-1572">四个数字, 其中最后一个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="484f6-1572">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-1573">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-1573">Checksum</span></span>

<span data-ttu-id="484f6-1574">是</span><span class="sxs-lookup"><span data-stu-id="484f6-1574">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-1575">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-1575">Definition</span></span>

<span data-ttu-id="484f6-1576">DLP 策略 85% 确信在300个字符的邻近度内检测到此类型的敏感信息: 函数 Func_czech_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-1576">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="484f6-1577">找到 Keyword_czech_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-1577">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="484f6-1578">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-1578">The checksum passes.</span></span>

```
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="484f6-1579">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-1579">Keywords</span></span>

- <span data-ttu-id="484f6-1580">捷克个人识别码</span><span class="sxs-lookup"><span data-stu-id="484f6-1580">czech personal identity number</span></span>
- <span data-ttu-id="484f6-1581">Rodné číslo</span><span class="sxs-lookup"><span data-stu-id="484f6-1581">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="484f6-1582">	丹麦个人身份号码</span><span class="sxs-lookup"><span data-stu-id="484f6-1582">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-1583">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-1583">Format</span></span>

<span data-ttu-id="484f6-1584">10 个数字，包含连字符</span><span class="sxs-lookup"><span data-stu-id="484f6-1584">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-1585">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-1585">Pattern</span></span>

<span data-ttu-id="484f6-1586">10 个数字：</span><span class="sxs-lookup"><span data-stu-id="484f6-1586">10 digits:</span></span>
- <span data-ttu-id="484f6-1587">六个数字，采用  DDMMYY 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="484f6-1587">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="484f6-1588">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="484f6-1588">A hyphen</span></span> 
- <span data-ttu-id="484f6-1589">四个数字，最后一位数字是校验位</span><span class="sxs-lookup"><span data-stu-id="484f6-1589">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-1590">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-1590">Checksum</span></span>

<span data-ttu-id="484f6-1591">是</span><span class="sxs-lookup"><span data-stu-id="484f6-1591">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-1592">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-1592">Definition</span></span>

<span data-ttu-id="484f6-1593">DLP 策略 75% 确信在300个字符的邻近度内检测到此类型的敏感信息: 正则表达式 Regex_denmark_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-1593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="484f6-1594">找到 Keyword_denmark_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-1594">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="484f6-1595">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-1595">The checksum passes.</span></span>

```
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="484f6-1596">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-1596">Keywords</span></span>

#### <a name="keyworddenmarkid"></a><span data-ttu-id="484f6-1597">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="484f6-1597">Keyword_denmark_id</span></span>

- <span data-ttu-id="484f6-1598">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="484f6-1598">Personal Identification Number</span></span>
- <span data-ttu-id="484f6-1599">CPR</span><span class="sxs-lookup"><span data-stu-id="484f6-1599">CPR</span></span>
- <span data-ttu-id="484f6-1600">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="484f6-1600">Det Centrale Personregister</span></span>
- <span data-ttu-id="484f6-1601">Personnummer</span><span class="sxs-lookup"><span data-stu-id="484f6-1601">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="484f6-1602">药品管制局 (DEA) 号码</span><span class="sxs-lookup"><span data-stu-id="484f6-1602">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-1603">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-1603">Format</span></span>

<span data-ttu-id="484f6-1604">两个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-1604">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-1605">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-1605">Pattern</span></span>

<span data-ttu-id="484f6-1606">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="484f6-1606">Pattern must include all of the following:</span></span>
- <span data-ttu-id="484f6-1607">这一组可能的字母（不区分大小写）中的一个字母：abcdefghjklmnprstux，这是注册人代码</span><span class="sxs-lookup"><span data-stu-id="484f6-1607">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="484f6-1608">一个字母（不区分大小写），这是注册人姓氏的第一个字母</span><span class="sxs-lookup"><span data-stu-id="484f6-1608">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="484f6-1609">七位数字，最后一个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="484f6-1609">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-1610">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-1610">Checksum</span></span>

<span data-ttu-id="484f6-1611">是</span><span class="sxs-lookup"><span data-stu-id="484f6-1611">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-1612">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-1612">Definition</span></span>

<span data-ttu-id="484f6-1613">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-1613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-1614">函数 Func_dea_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-1614">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-1615">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-1615">The checksum passes.</span></span>

```
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="484f6-1616">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-1616">Keywords</span></span>

<span data-ttu-id="484f6-1617">无</span><span class="sxs-lookup"><span data-stu-id="484f6-1617">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="484f6-1618">欧盟借记卡号</span><span class="sxs-lookup"><span data-stu-id="484f6-1618">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-1619">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-1619">Format</span></span>

<span data-ttu-id="484f6-1620">16 个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-1620">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-1621">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-1621">Pattern</span></span>

<span data-ttu-id="484f6-1622">非常复杂且强大的模式</span><span class="sxs-lookup"><span data-stu-id="484f6-1622">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-1623">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-1623">Checksum</span></span>

<span data-ttu-id="484f6-1624">是</span><span class="sxs-lookup"><span data-stu-id="484f6-1624">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-1625">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-1625">Definition</span></span>

<span data-ttu-id="484f6-1626">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-1626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-1627">函数 Func_eu_debit_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-1627">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-1628">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="484f6-1628">At least one of the following is true:</span></span>
    - <span data-ttu-id="484f6-1629">找到 Keyword_eu_debit_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-1629">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="484f6-1630">找到 Keyword_card_terms_dict 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-1630">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="484f6-1631">找到 Keyword_card_security_terms_dict 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-1631">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="484f6-1632">找到 Keyword_card_expiration_terms_dict 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-1632">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="484f6-1633">函数 Func_expiration_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="484f6-1633">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="484f6-1634">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-1634">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-1635">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-1635">Keywords</span></span>

#### <a name="keywordeudebitcard"></a><span data-ttu-id="484f6-1636">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="484f6-1636">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="484f6-1637">account number</span><span class="sxs-lookup"><span data-stu-id="484f6-1637">account number</span></span> 
- <span data-ttu-id="484f6-1638">card number</span><span class="sxs-lookup"><span data-stu-id="484f6-1638">card number</span></span> 
- <span data-ttu-id="484f6-1639">card no.</span><span class="sxs-lookup"><span data-stu-id="484f6-1639">card no.</span></span> 
- <span data-ttu-id="484f6-1640">security number</span><span class="sxs-lookup"><span data-stu-id="484f6-1640">security number</span></span> 
- <span data-ttu-id="484f6-1641">收件人</span><span class="sxs-lookup"><span data-stu-id="484f6-1641">cc#</span></span> 

#### <a name="keywordcardtermsdict"></a><span data-ttu-id="484f6-1642">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="484f6-1642">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="484f6-1643">acct nbr</span><span class="sxs-lookup"><span data-stu-id="484f6-1643">acct nbr</span></span> 
- <span data-ttu-id="484f6-1644">acct num</span><span class="sxs-lookup"><span data-stu-id="484f6-1644">acct num</span></span> 
- <span data-ttu-id="484f6-1645">acct no</span><span class="sxs-lookup"><span data-stu-id="484f6-1645">acct no</span></span> 
- <span data-ttu-id="484f6-1646">american express</span><span class="sxs-lookup"><span data-stu-id="484f6-1646">american express</span></span> 
- <span data-ttu-id="484f6-1647">americanexpress</span><span class="sxs-lookup"><span data-stu-id="484f6-1647">americanexpress</span></span> 
- <span data-ttu-id="484f6-1648">americano espresso</span><span class="sxs-lookup"><span data-stu-id="484f6-1648">americano espresso</span></span> 
- <span data-ttu-id="484f6-1649">amex</span><span class="sxs-lookup"><span data-stu-id="484f6-1649">amex</span></span> 
- <span data-ttu-id="484f6-1650">atm card</span><span class="sxs-lookup"><span data-stu-id="484f6-1650">atm card</span></span> 
- <span data-ttu-id="484f6-1651">atm cards</span><span class="sxs-lookup"><span data-stu-id="484f6-1651">atm cards</span></span> 
- <span data-ttu-id="484f6-1652">atm kaart</span><span class="sxs-lookup"><span data-stu-id="484f6-1652">atm kaart</span></span> 
- <span data-ttu-id="484f6-1653">atmcard</span><span class="sxs-lookup"><span data-stu-id="484f6-1653">atmcard</span></span> 
- <span data-ttu-id="484f6-1654">atmcards</span><span class="sxs-lookup"><span data-stu-id="484f6-1654">atmcards</span></span> 
- <span data-ttu-id="484f6-1655">atmkaart</span><span class="sxs-lookup"><span data-stu-id="484f6-1655">atmkaart</span></span> 
- <span data-ttu-id="484f6-1656">atmkaarten</span><span class="sxs-lookup"><span data-stu-id="484f6-1656">atmkaarten</span></span> 
- <span data-ttu-id="484f6-1657">bancontact</span><span class="sxs-lookup"><span data-stu-id="484f6-1657">bancontact</span></span> 
- <span data-ttu-id="484f6-1658">bank card</span><span class="sxs-lookup"><span data-stu-id="484f6-1658">bank card</span></span> 
- <span data-ttu-id="484f6-1659">bankkaart</span><span class="sxs-lookup"><span data-stu-id="484f6-1659">bankkaart</span></span> 
- <span data-ttu-id="484f6-1660">card holder</span><span class="sxs-lookup"><span data-stu-id="484f6-1660">card holder</span></span> 
- <span data-ttu-id="484f6-1661">card holders</span><span class="sxs-lookup"><span data-stu-id="484f6-1661">card holders</span></span> 
- <span data-ttu-id="484f6-1662">card num</span><span class="sxs-lookup"><span data-stu-id="484f6-1662">card num</span></span> 
- <span data-ttu-id="484f6-1663">card number</span><span class="sxs-lookup"><span data-stu-id="484f6-1663">card number</span></span> 
- <span data-ttu-id="484f6-1664">card numbers</span><span class="sxs-lookup"><span data-stu-id="484f6-1664">card numbers</span></span> 
- <span data-ttu-id="484f6-1665">card type</span><span class="sxs-lookup"><span data-stu-id="484f6-1665">card type</span></span> 
- <span data-ttu-id="484f6-1666">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="484f6-1666">cardano numerico</span></span> 
- <span data-ttu-id="484f6-1667">持卡人</span><span class="sxs-lookup"><span data-stu-id="484f6-1667">cardholder</span></span> 
- <span data-ttu-id="484f6-1668">cardholders</span><span class="sxs-lookup"><span data-stu-id="484f6-1668">cardholders</span></span> 
- <span data-ttu-id="484f6-1669">cardnumber</span><span class="sxs-lookup"><span data-stu-id="484f6-1669">cardnumber</span></span> 
- <span data-ttu-id="484f6-1670">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="484f6-1670">cardnumbers</span></span> 
- <span data-ttu-id="484f6-1671">carta bianca</span><span class="sxs-lookup"><span data-stu-id="484f6-1671">carta bianca</span></span> 
- <span data-ttu-id="484f6-1672">carta credito</span><span class="sxs-lookup"><span data-stu-id="484f6-1672">carta credito</span></span> 
- <span data-ttu-id="484f6-1673">carta di credito</span><span class="sxs-lookup"><span data-stu-id="484f6-1673">carta di credito</span></span> 
- <span data-ttu-id="484f6-1674">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="484f6-1674">cartao de credito</span></span> 
- <span data-ttu-id="484f6-1675">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="484f6-1675">cartao de crédito</span></span> 
- <span data-ttu-id="484f6-1676">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="484f6-1676">cartao de debito</span></span> 
- <span data-ttu-id="484f6-1677">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="484f6-1677">cartao de débito</span></span> 
- <span data-ttu-id="484f6-1678">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="484f6-1678">carte bancaire</span></span> 
- <span data-ttu-id="484f6-1679">carte blanche</span><span class="sxs-lookup"><span data-stu-id="484f6-1679">carte blanche</span></span> 
- <span data-ttu-id="484f6-1680">carte bleue</span><span class="sxs-lookup"><span data-stu-id="484f6-1680">carte bleue</span></span> 
- <span data-ttu-id="484f6-1681">carte de credit</span><span class="sxs-lookup"><span data-stu-id="484f6-1681">carte de credit</span></span> 
- <span data-ttu-id="484f6-1682">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="484f6-1682">carte de crédit</span></span> 
- <span data-ttu-id="484f6-1683">carte di credito</span><span class="sxs-lookup"><span data-stu-id="484f6-1683">carte di credito</span></span> 
- <span data-ttu-id="484f6-1684">carteblanche</span><span class="sxs-lookup"><span data-stu-id="484f6-1684">carteblanche</span></span> 
- <span data-ttu-id="484f6-1685">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="484f6-1685">cartão de credito</span></span> 
- <span data-ttu-id="484f6-1686">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="484f6-1686">cartão de crédito</span></span> 
- <span data-ttu-id="484f6-1687">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="484f6-1687">cartão de debito</span></span> 
- <span data-ttu-id="484f6-1688">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="484f6-1688">cartão de débito</span></span> 
- <span data-ttu-id="484f6-1689">cb</span><span class="sxs-lookup"><span data-stu-id="484f6-1689">cb</span></span> 
- <span data-ttu-id="484f6-1690">ccn</span><span class="sxs-lookup"><span data-stu-id="484f6-1690">ccn</span></span> 
- <span data-ttu-id="484f6-1691">check card</span><span class="sxs-lookup"><span data-stu-id="484f6-1691">check card</span></span> 
- <span data-ttu-id="484f6-1692">check cards</span><span class="sxs-lookup"><span data-stu-id="484f6-1692">check cards</span></span> 
- <span data-ttu-id="484f6-1693">checkcard</span><span class="sxs-lookup"><span data-stu-id="484f6-1693">checkcard</span></span>
- <span data-ttu-id="484f6-1694">checkcards</span><span class="sxs-lookup"><span data-stu-id="484f6-1694">checkcards</span></span> 
- <span data-ttu-id="484f6-1695">chequekaart</span><span class="sxs-lookup"><span data-stu-id="484f6-1695">chequekaart</span></span> 
- <span data-ttu-id="484f6-1696">cirrus</span><span class="sxs-lookup"><span data-stu-id="484f6-1696">cirrus</span></span> 
- <span data-ttu-id="484f6-1697">cirrus-edc-maestro</span><span class="sxs-lookup"><span data-stu-id="484f6-1697">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="484f6-1698">controlekaart</span><span class="sxs-lookup"><span data-stu-id="484f6-1698">controlekaart</span></span> 
- <span data-ttu-id="484f6-1699">controlekaarten</span><span class="sxs-lookup"><span data-stu-id="484f6-1699">controlekaarten</span></span> 
- <span data-ttu-id="484f6-1700">credit card</span><span class="sxs-lookup"><span data-stu-id="484f6-1700">credit card</span></span> 
- <span data-ttu-id="484f6-1701">credit cards</span><span class="sxs-lookup"><span data-stu-id="484f6-1701">credit cards</span></span> 
- <span data-ttu-id="484f6-1702">creditcard</span><span class="sxs-lookup"><span data-stu-id="484f6-1702">creditcard</span></span> 
- <span data-ttu-id="484f6-1703">creditcards</span><span class="sxs-lookup"><span data-stu-id="484f6-1703">creditcards</span></span> 
- <span data-ttu-id="484f6-1704">debetkaart</span><span class="sxs-lookup"><span data-stu-id="484f6-1704">debetkaart</span></span> 
- <span data-ttu-id="484f6-1705">debetkaarten</span><span class="sxs-lookup"><span data-stu-id="484f6-1705">debetkaarten</span></span> 
- <span data-ttu-id="484f6-1706">debit card</span><span class="sxs-lookup"><span data-stu-id="484f6-1706">debit card</span></span> 
- <span data-ttu-id="484f6-1707">debit cards</span><span class="sxs-lookup"><span data-stu-id="484f6-1707">debit cards</span></span> 
- <span data-ttu-id="484f6-1708">debitcard</span><span class="sxs-lookup"><span data-stu-id="484f6-1708">debitcard</span></span> 
- <span data-ttu-id="484f6-1709">debitcards</span><span class="sxs-lookup"><span data-stu-id="484f6-1709">debitcards</span></span> 
- <span data-ttu-id="484f6-1710">debito automatico</span><span class="sxs-lookup"><span data-stu-id="484f6-1710">debito automatico</span></span> 
- <span data-ttu-id="484f6-1711">diners club</span><span class="sxs-lookup"><span data-stu-id="484f6-1711">diners club</span></span> 
- <span data-ttu-id="484f6-1712">dinersclub</span><span class="sxs-lookup"><span data-stu-id="484f6-1712">dinersclub</span></span> 
- <span data-ttu-id="484f6-1713">确定</span><span class="sxs-lookup"><span data-stu-id="484f6-1713">discover</span></span> 
- <span data-ttu-id="484f6-1714">discover card</span><span class="sxs-lookup"><span data-stu-id="484f6-1714">discover card</span></span> 
- <span data-ttu-id="484f6-1715">discover cards</span><span class="sxs-lookup"><span data-stu-id="484f6-1715">discover cards</span></span> 
- <span data-ttu-id="484f6-1716">discovercard</span><span class="sxs-lookup"><span data-stu-id="484f6-1716">discovercard</span></span> 
- <span data-ttu-id="484f6-1717">discovercards</span><span class="sxs-lookup"><span data-stu-id="484f6-1717">discovercards</span></span> 
- <span data-ttu-id="484f6-1718">débito automático</span><span class="sxs-lookup"><span data-stu-id="484f6-1718">débito automático</span></span>
- <span data-ttu-id="484f6-1719">edc</span><span class="sxs-lookup"><span data-stu-id="484f6-1719">edc</span></span> 
- <span data-ttu-id="484f6-1720">eigentümername</span><span class="sxs-lookup"><span data-stu-id="484f6-1720">eigentümername</span></span> 
- <span data-ttu-id="484f6-1721">european debit card</span><span class="sxs-lookup"><span data-stu-id="484f6-1721">european debit card</span></span> 
- <span data-ttu-id="484f6-1722">hoofdkaart</span><span class="sxs-lookup"><span data-stu-id="484f6-1722">hoofdkaart</span></span> 
- <span data-ttu-id="484f6-1723">hoofdkaarten</span><span class="sxs-lookup"><span data-stu-id="484f6-1723">hoofdkaarten</span></span> 
- <span data-ttu-id="484f6-1724">in viaggio</span><span class="sxs-lookup"><span data-stu-id="484f6-1724">in viaggio</span></span> 
- <span data-ttu-id="484f6-1725">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="484f6-1725">japanese card bureau</span></span> 
- <span data-ttu-id="484f6-1726">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="484f6-1726">japanse kaartdienst</span></span> 
- <span data-ttu-id="484f6-1727">jcb</span><span class="sxs-lookup"><span data-stu-id="484f6-1727">jcb</span></span> 
- <span data-ttu-id="484f6-1728">kaart</span><span class="sxs-lookup"><span data-stu-id="484f6-1728">kaart</span></span> 
- <span data-ttu-id="484f6-1729">kaart num</span><span class="sxs-lookup"><span data-stu-id="484f6-1729">kaart num</span></span> 
- <span data-ttu-id="484f6-1730">kaartaantal</span><span class="sxs-lookup"><span data-stu-id="484f6-1730">kaartaantal</span></span> 
- <span data-ttu-id="484f6-1731">kaartaantallen</span><span class="sxs-lookup"><span data-stu-id="484f6-1731">kaartaantallen</span></span> 
- <span data-ttu-id="484f6-1732">kaarthouder</span><span class="sxs-lookup"><span data-stu-id="484f6-1732">kaarthouder</span></span> 
- <span data-ttu-id="484f6-1733">kaarthouders</span><span class="sxs-lookup"><span data-stu-id="484f6-1733">kaarthouders</span></span> 
- <span data-ttu-id="484f6-1734">karte</span><span class="sxs-lookup"><span data-stu-id="484f6-1734">karte</span></span>  
- <span data-ttu-id="484f6-1735">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="484f6-1735">karteninhaber</span></span> 
- <span data-ttu-id="484f6-1736">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="484f6-1736">karteninhabers</span></span>
- <span data-ttu-id="484f6-1737">kartennr</span><span class="sxs-lookup"><span data-stu-id="484f6-1737">kartennr</span></span> 
- <span data-ttu-id="484f6-1738">kartennummer</span><span class="sxs-lookup"><span data-stu-id="484f6-1738">kartennummer</span></span> 
- <span data-ttu-id="484f6-1739">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="484f6-1739">kreditkarte</span></span> 
- <span data-ttu-id="484f6-1740">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="484f6-1740">kreditkarten-nummer</span></span> 
- <span data-ttu-id="484f6-1741">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="484f6-1741">kreditkarteninhaber</span></span> 
- <span data-ttu-id="484f6-1742">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="484f6-1742">kreditkarteninstitut</span></span> 
- <span data-ttu-id="484f6-1743">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="484f6-1743">kreditkartennummer</span></span> 
- <span data-ttu-id="484f6-1744">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="484f6-1744">kreditkartentyp</span></span> 
- <span data-ttu-id="484f6-1745">maestro</span><span class="sxs-lookup"><span data-stu-id="484f6-1745">maestro</span></span> 
- <span data-ttu-id="484f6-1746">Master Card</span><span class="sxs-lookup"><span data-stu-id="484f6-1746">master card</span></span> 
- <span data-ttu-id="484f6-1747">master cards</span><span class="sxs-lookup"><span data-stu-id="484f6-1747">master cards</span></span> 
- <span data-ttu-id="484f6-1748">mastercard</span><span class="sxs-lookup"><span data-stu-id="484f6-1748">mastercard</span></span> 
- <span data-ttu-id="484f6-1749">mastercards</span><span class="sxs-lookup"><span data-stu-id="484f6-1749">mastercards</span></span> 
- <span data-ttu-id="484f6-1750">emc</span><span class="sxs-lookup"><span data-stu-id="484f6-1750">mc</span></span> 
- <span data-ttu-id="484f6-1751">mister cash</span><span class="sxs-lookup"><span data-stu-id="484f6-1751">mister cash</span></span> 
- <span data-ttu-id="484f6-1752">n carta</span><span class="sxs-lookup"><span data-stu-id="484f6-1752">n carta</span></span> 
- <span data-ttu-id="484f6-1753">carta</span><span class="sxs-lookup"><span data-stu-id="484f6-1753">carta</span></span> 
- <span data-ttu-id="484f6-1754">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="484f6-1754">no de tarjeta</span></span> 
- <span data-ttu-id="484f6-1755">no do cartao</span><span class="sxs-lookup"><span data-stu-id="484f6-1755">no do cartao</span></span> 
- <span data-ttu-id="484f6-1756">no do cartão</span><span class="sxs-lookup"><span data-stu-id="484f6-1756">no do cartão</span></span> 
- <span data-ttu-id="484f6-1757">不。</span><span class="sxs-lookup"><span data-stu-id="484f6-1757">no.</span></span> <span data-ttu-id="484f6-1758">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="484f6-1758">de tarjeta</span></span> 
- <span data-ttu-id="484f6-1759">不。</span><span class="sxs-lookup"><span data-stu-id="484f6-1759">no.</span></span> <span data-ttu-id="484f6-1760">do cartao</span><span class="sxs-lookup"><span data-stu-id="484f6-1760">do cartao</span></span> 
- <span data-ttu-id="484f6-1761">不。</span><span class="sxs-lookup"><span data-stu-id="484f6-1761">no.</span></span> <span data-ttu-id="484f6-1762">do cartão</span><span class="sxs-lookup"><span data-stu-id="484f6-1762">do cartão</span></span> 
- <span data-ttu-id="484f6-1763">nr carta</span><span class="sxs-lookup"><span data-stu-id="484f6-1763">nr carta</span></span> 
- <span data-ttu-id="484f6-1764">führerschein-nr.</span><span class="sxs-lookup"><span data-stu-id="484f6-1764">nr.</span></span> <span data-ttu-id="484f6-1765">carta</span><span class="sxs-lookup"><span data-stu-id="484f6-1765">carta</span></span> 
- <span data-ttu-id="484f6-1766">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="484f6-1766">numeri di scheda</span></span> 
- <span data-ttu-id="484f6-1767">numero carta</span><span class="sxs-lookup"><span data-stu-id="484f6-1767">numero carta</span></span> 
- <span data-ttu-id="484f6-1768">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="484f6-1768">numero de cartao</span></span> 
- <span data-ttu-id="484f6-1769">numero de carte</span><span class="sxs-lookup"><span data-stu-id="484f6-1769">numero de carte</span></span> 
- <span data-ttu-id="484f6-1770">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="484f6-1770">numero de cartão</span></span> 
- <span data-ttu-id="484f6-1771">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="484f6-1771">numero de tarjeta</span></span>
- <span data-ttu-id="484f6-1772">numero della carta</span><span class="sxs-lookup"><span data-stu-id="484f6-1772">numero della carta</span></span> 
- <span data-ttu-id="484f6-1773">numero di carta</span><span class="sxs-lookup"><span data-stu-id="484f6-1773">numero di carta</span></span> 
- <span data-ttu-id="484f6-1774">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="484f6-1774">numero di scheda</span></span> 
- <span data-ttu-id="484f6-1775">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="484f6-1775">numero do cartao</span></span> 
- <span data-ttu-id="484f6-1776">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="484f6-1776">numero do cartão</span></span> 
- <span data-ttu-id="484f6-1777">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="484f6-1777">numéro de carte</span></span> 
- <span data-ttu-id="484f6-1778">nº carta</span><span class="sxs-lookup"><span data-stu-id="484f6-1778">nº carta</span></span> 
- <span data-ttu-id="484f6-1779">nº de carte</span><span class="sxs-lookup"><span data-stu-id="484f6-1779">nº de carte</span></span> 
- <span data-ttu-id="484f6-1780">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="484f6-1780">nº de la carte</span></span> 
- <span data-ttu-id="484f6-1781">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="484f6-1781">nº de tarjeta</span></span> 
- <span data-ttu-id="484f6-1782">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="484f6-1782">nº do cartao</span></span> 
- <span data-ttu-id="484f6-1783">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="484f6-1783">nº do cartão</span></span> 
- <span data-ttu-id="484f6-1784">n º。</span><span class="sxs-lookup"><span data-stu-id="484f6-1784">nº.</span></span> <span data-ttu-id="484f6-1785">do cartão</span><span class="sxs-lookup"><span data-stu-id="484f6-1785">do cartão</span></span> 
- <span data-ttu-id="484f6-1786">número de cartao</span><span class="sxs-lookup"><span data-stu-id="484f6-1786">número de cartao</span></span> 
- <span data-ttu-id="484f6-1787">número de cartão</span><span class="sxs-lookup"><span data-stu-id="484f6-1787">número de cartão</span></span> 
- <span data-ttu-id="484f6-1788">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="484f6-1788">número de tarjeta</span></span> 
- <span data-ttu-id="484f6-1789">número do cartao</span><span class="sxs-lookup"><span data-stu-id="484f6-1789">número do cartao</span></span> 
- <span data-ttu-id="484f6-1790">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="484f6-1790">scheda dell'assegno</span></span> 
- <span data-ttu-id="484f6-1791">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="484f6-1791">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="484f6-1792">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="484f6-1792">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="484f6-1793">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="484f6-1793">scheda della banca</span></span> 
- <span data-ttu-id="484f6-1794">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="484f6-1794">scheda di controllo</span></span> 
- <span data-ttu-id="484f6-1795">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="484f6-1795">scheda di debito</span></span> 
- <span data-ttu-id="484f6-1796">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="484f6-1796">scheda matrice</span></span> 
- <span data-ttu-id="484f6-1797">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="484f6-1797">schede dell'atmosfera</span></span> 
- <span data-ttu-id="484f6-1798">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="484f6-1798">schede di controllo</span></span> 
- <span data-ttu-id="484f6-1799">schede di debito</span><span class="sxs-lookup"><span data-stu-id="484f6-1799">schede di debito</span></span> 
- <span data-ttu-id="484f6-1800">schede matrici</span><span class="sxs-lookup"><span data-stu-id="484f6-1800">schede matrici</span></span> 
- <span data-ttu-id="484f6-1801">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="484f6-1801">scoprono la scheda</span></span> 
- <span data-ttu-id="484f6-1802">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="484f6-1802">scoprono le schede</span></span> 
- <span data-ttu-id="484f6-1803">solo</span><span class="sxs-lookup"><span data-stu-id="484f6-1803">solo</span></span> 
- <span data-ttu-id="484f6-1804">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="484f6-1804">supporti di scheda</span></span> 
- <span data-ttu-id="484f6-1805">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="484f6-1805">supporto di scheda</span></span> 
- <span data-ttu-id="484f6-1806">器</span><span class="sxs-lookup"><span data-stu-id="484f6-1806">switch</span></span> 
- <span data-ttu-id="484f6-1807">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="484f6-1807">tarjeta atm</span></span> 
- <span data-ttu-id="484f6-1808">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="484f6-1808">tarjeta credito</span></span> 
- <span data-ttu-id="484f6-1809">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="484f6-1809">tarjeta de atm</span></span> 
- <span data-ttu-id="484f6-1810">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="484f6-1810">tarjeta de credito</span></span> 
- <span data-ttu-id="484f6-1811">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="484f6-1811">tarjeta de debito</span></span> 
- <span data-ttu-id="484f6-1812">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="484f6-1812">tarjeta debito</span></span> 
- <span data-ttu-id="484f6-1813">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="484f6-1813">tarjeta no</span></span>
- <span data-ttu-id="484f6-1814">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="484f6-1814">tarjetahabiente</span></span> 
- <span data-ttu-id="484f6-1815">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="484f6-1815">tipo della scheda</span></span> 
- <span data-ttu-id="484f6-1816">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="484f6-1816">ufficio giapponese della</span></span> 
- <span data-ttu-id="484f6-1817">scheda</span><span class="sxs-lookup"><span data-stu-id="484f6-1817">scheda</span></span> 
- <span data-ttu-id="484f6-1818">v pay</span><span class="sxs-lookup"><span data-stu-id="484f6-1818">v pay</span></span> 
- <span data-ttu-id="484f6-1819">v-支付</span><span class="sxs-lookup"><span data-stu-id="484f6-1819">v-pay</span></span> 
- <span data-ttu-id="484f6-1820">反之</span><span class="sxs-lookup"><span data-stu-id="484f6-1820">visa</span></span> 
- <span data-ttu-id="484f6-1821">visa plus</span><span class="sxs-lookup"><span data-stu-id="484f6-1821">visa plus</span></span> 
- <span data-ttu-id="484f6-1822">visa electron</span><span class="sxs-lookup"><span data-stu-id="484f6-1822">visa electron</span></span> 
- <span data-ttu-id="484f6-1823">visto</span><span class="sxs-lookup"><span data-stu-id="484f6-1823">visto</span></span> 
- <span data-ttu-id="484f6-1824">visum</span><span class="sxs-lookup"><span data-stu-id="484f6-1824">visum</span></span> 
- <span data-ttu-id="484f6-1825">vpay</span><span class="sxs-lookup"><span data-stu-id="484f6-1825">vpay</span></span>   

#### <a name="keywordcardsecuritytermsdict"></a><span data-ttu-id="484f6-1826">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="484f6-1826">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="484f6-1827">card identification number</span><span class="sxs-lookup"><span data-stu-id="484f6-1827">card identification number</span></span>
- <span data-ttu-id="484f6-1828">card verification</span><span class="sxs-lookup"><span data-stu-id="484f6-1828">card verification</span></span> 
- <span data-ttu-id="484f6-1829">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="484f6-1829">cardi la verifica</span></span> 
- <span data-ttu-id="484f6-1830">cid</span><span class="sxs-lookup"><span data-stu-id="484f6-1830">cid</span></span> 
- <span data-ttu-id="484f6-1831">cod seg</span><span class="sxs-lookup"><span data-stu-id="484f6-1831">cod seg</span></span> 
- <span data-ttu-id="484f6-1832">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="484f6-1832">cod seguranca</span></span> 
- <span data-ttu-id="484f6-1833">cod segurança</span><span class="sxs-lookup"><span data-stu-id="484f6-1833">cod segurança</span></span> 
- <span data-ttu-id="484f6-1834">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="484f6-1834">cod sicurezza</span></span> 
- <span data-ttu-id="484f6-1835">货.</span><span class="sxs-lookup"><span data-stu-id="484f6-1835">cod.</span></span> <span data-ttu-id="484f6-1836">seg</span><span class="sxs-lookup"><span data-stu-id="484f6-1836">seg</span></span> 
- <span data-ttu-id="484f6-1837">货.</span><span class="sxs-lookup"><span data-stu-id="484f6-1837">cod.</span></span> <span data-ttu-id="484f6-1838">seguranca</span><span class="sxs-lookup"><span data-stu-id="484f6-1838">seguranca</span></span> 
- <span data-ttu-id="484f6-1839">货.</span><span class="sxs-lookup"><span data-stu-id="484f6-1839">cod.</span></span> <span data-ttu-id="484f6-1840">segurança</span><span class="sxs-lookup"><span data-stu-id="484f6-1840">segurança</span></span> 
- <span data-ttu-id="484f6-1841">货.</span><span class="sxs-lookup"><span data-stu-id="484f6-1841">cod.</span></span> <span data-ttu-id="484f6-1842">sicurezza</span><span class="sxs-lookup"><span data-stu-id="484f6-1842">sicurezza</span></span> 
- <span data-ttu-id="484f6-1843">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="484f6-1843">codice di sicurezza</span></span> 
- <span data-ttu-id="484f6-1844">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="484f6-1844">codice di verifica</span></span> 
- <span data-ttu-id="484f6-1845">codigo</span><span class="sxs-lookup"><span data-stu-id="484f6-1845">codigo</span></span> 
- <span data-ttu-id="484f6-1846">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="484f6-1846">codigo de seguranca</span></span> 
- <span data-ttu-id="484f6-1847">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="484f6-1847">codigo de segurança</span></span> 
- <span data-ttu-id="484f6-1848">crittogramma</span><span class="sxs-lookup"><span data-stu-id="484f6-1848">crittogramma</span></span> 
- <span data-ttu-id="484f6-1849">cryptogram</span><span class="sxs-lookup"><span data-stu-id="484f6-1849">cryptogram</span></span> 
- <span data-ttu-id="484f6-1850">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="484f6-1850">cryptogramme</span></span> 
- <span data-ttu-id="484f6-1851">cv2</span><span class="sxs-lookup"><span data-stu-id="484f6-1851">cv2</span></span> 
- <span data-ttu-id="484f6-1852">cvc</span><span class="sxs-lookup"><span data-stu-id="484f6-1852">cvc</span></span> 
- <span data-ttu-id="484f6-1853">cvc2</span><span class="sxs-lookup"><span data-stu-id="484f6-1853">cvc2</span></span> 
- <span data-ttu-id="484f6-1854">cvn</span><span class="sxs-lookup"><span data-stu-id="484f6-1854">cvn</span></span> 
- <span data-ttu-id="484f6-1855">cvv</span><span class="sxs-lookup"><span data-stu-id="484f6-1855">cvv</span></span> 
- <span data-ttu-id="484f6-1856">cvv2</span><span class="sxs-lookup"><span data-stu-id="484f6-1856">cvv2</span></span> 
- <span data-ttu-id="484f6-1857">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="484f6-1857">cód seguranca</span></span> 
- <span data-ttu-id="484f6-1858">cód segurança</span><span class="sxs-lookup"><span data-stu-id="484f6-1858">cód segurança</span></span> 
- <span data-ttu-id="484f6-1859">cód.</span><span class="sxs-lookup"><span data-stu-id="484f6-1859">cód.</span></span> <span data-ttu-id="484f6-1860">seguranca</span><span class="sxs-lookup"><span data-stu-id="484f6-1860">seguranca</span></span> 
- <span data-ttu-id="484f6-1861">cód.</span><span class="sxs-lookup"><span data-stu-id="484f6-1861">cód.</span></span> <span data-ttu-id="484f6-1862">segurança</span><span class="sxs-lookup"><span data-stu-id="484f6-1862">segurança</span></span> 
- <span data-ttu-id="484f6-1863">código</span><span class="sxs-lookup"><span data-stu-id="484f6-1863">código</span></span> 
- <span data-ttu-id="484f6-1864">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="484f6-1864">código de seguranca</span></span> 
- <span data-ttu-id="484f6-1865">código de segurança</span><span class="sxs-lookup"><span data-stu-id="484f6-1865">código de segurança</span></span> 
- <span data-ttu-id="484f6-1866">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="484f6-1866">de kaart controle</span></span> 
- <span data-ttu-id="484f6-1867">geeft nr uit</span><span class="sxs-lookup"><span data-stu-id="484f6-1867">geeft nr uit</span></span> 
- <span data-ttu-id="484f6-1868">issue no</span><span class="sxs-lookup"><span data-stu-id="484f6-1868">issue no</span></span> 
- <span data-ttu-id="484f6-1869">issue number</span><span class="sxs-lookup"><span data-stu-id="484f6-1869">issue number</span></span> 
- <span data-ttu-id="484f6-1870">kaartidentificatienummer</span><span class="sxs-lookup"><span data-stu-id="484f6-1870">kaartidentificatienummer</span></span> 
- <span data-ttu-id="484f6-1871">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="484f6-1871">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="484f6-1872">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="484f6-1872">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="484f6-1873">kwestieaantal</span><span class="sxs-lookup"><span data-stu-id="484f6-1873">kwestieaantal</span></span> 
- <span data-ttu-id="484f6-1874">不。</span><span class="sxs-lookup"><span data-stu-id="484f6-1874">no.</span></span> <span data-ttu-id="484f6-1875">dell'edizione</span><span class="sxs-lookup"><span data-stu-id="484f6-1875">dell'edizione</span></span> 
- <span data-ttu-id="484f6-1876">不。</span><span class="sxs-lookup"><span data-stu-id="484f6-1876">no.</span></span> <span data-ttu-id="484f6-1877">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="484f6-1877">di sicurezza</span></span> 
- <span data-ttu-id="484f6-1878">numero de securite</span><span class="sxs-lookup"><span data-stu-id="484f6-1878">numero de securite</span></span> 
- <span data-ttu-id="484f6-1879">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="484f6-1879">numero de verificacao</span></span> 
- <span data-ttu-id="484f6-1880">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="484f6-1880">numero dell'edizione</span></span> 
- <span data-ttu-id="484f6-1881">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="484f6-1881">numero di identificazione della</span></span> 
- <span data-ttu-id="484f6-1882">scheda</span><span class="sxs-lookup"><span data-stu-id="484f6-1882">scheda</span></span> 
- <span data-ttu-id="484f6-1883">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="484f6-1883">numero di sicurezza</span></span> 
- <span data-ttu-id="484f6-1884">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="484f6-1884">numero van veiligheid</span></span> 
- <span data-ttu-id="484f6-1885">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="484f6-1885">numéro de sécurité</span></span> 
- <span data-ttu-id="484f6-1886">nº autorizzazione</span><span class="sxs-lookup"><span data-stu-id="484f6-1886">nº autorizzazione</span></span> 
- <span data-ttu-id="484f6-1887">número de verificação</span><span class="sxs-lookup"><span data-stu-id="484f6-1887">número de verificação</span></span> 
- <span data-ttu-id="484f6-1888">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="484f6-1888">perno il blocco</span></span> 
- <span data-ttu-id="484f6-1889">pin block</span><span class="sxs-lookup"><span data-stu-id="484f6-1889">pin block</span></span> 
- <span data-ttu-id="484f6-1890">prufziffer</span><span class="sxs-lookup"><span data-stu-id="484f6-1890">prufziffer</span></span> 
- <span data-ttu-id="484f6-1891">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="484f6-1891">prüfziffer</span></span> 
- <span data-ttu-id="484f6-1892">security code</span><span class="sxs-lookup"><span data-stu-id="484f6-1892">security code</span></span> 
- <span data-ttu-id="484f6-1893">security no</span><span class="sxs-lookup"><span data-stu-id="484f6-1893">security no</span></span> 
- <span data-ttu-id="484f6-1894">security number</span><span class="sxs-lookup"><span data-stu-id="484f6-1894">security number</span></span> 
- <span data-ttu-id="484f6-1895">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="484f6-1895">sicherheits kode</span></span> 
- <span data-ttu-id="484f6-1896">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="484f6-1896">sicherheitscode</span></span> 
- <span data-ttu-id="484f6-1897">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="484f6-1897">sicherheitsnummer</span></span> 
- <span data-ttu-id="484f6-1898">speldblok</span><span class="sxs-lookup"><span data-stu-id="484f6-1898">speldblok</span></span> 
- <span data-ttu-id="484f6-1899">veiligheid nr</span><span class="sxs-lookup"><span data-stu-id="484f6-1899">veiligheid nr</span></span> 
- <span data-ttu-id="484f6-1900">veiligheidsaantal</span><span class="sxs-lookup"><span data-stu-id="484f6-1900">veiligheidsaantal</span></span> 
- <span data-ttu-id="484f6-1901">veiligheidscode</span><span class="sxs-lookup"><span data-stu-id="484f6-1901">veiligheidscode</span></span> 
- <span data-ttu-id="484f6-1902">veiligheidsnummer</span><span class="sxs-lookup"><span data-stu-id="484f6-1902">veiligheidsnummer</span></span> 
- <span data-ttu-id="484f6-1903">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="484f6-1903">verfalldatum</span></span> 

#### <a name="keywordcardexpirationtermsdict"></a><span data-ttu-id="484f6-1904">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="484f6-1904">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="484f6-1905">ablauf</span><span class="sxs-lookup"><span data-stu-id="484f6-1905">ablauf</span></span> 
- <span data-ttu-id="484f6-1906">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="484f6-1906">data de expiracao</span></span> 
- <span data-ttu-id="484f6-1907">data de expiração</span><span class="sxs-lookup"><span data-stu-id="484f6-1907">data de expiração</span></span> 
- <span data-ttu-id="484f6-1908">data del exp</span><span class="sxs-lookup"><span data-stu-id="484f6-1908">data del exp</span></span> 
- <span data-ttu-id="484f6-1909">data di exp</span><span class="sxs-lookup"><span data-stu-id="484f6-1909">data di exp</span></span> 
- <span data-ttu-id="484f6-1910">data di scadenza</span><span class="sxs-lookup"><span data-stu-id="484f6-1910">data di scadenza</span></span> 
- <span data-ttu-id="484f6-1911">data em que expira</span><span class="sxs-lookup"><span data-stu-id="484f6-1911">data em que expira</span></span> 
- <span data-ttu-id="484f6-1912">data scad</span><span class="sxs-lookup"><span data-stu-id="484f6-1912">data scad</span></span> 
- <span data-ttu-id="484f6-1913">data scadenza</span><span class="sxs-lookup"><span data-stu-id="484f6-1913">data scadenza</span></span> 
- <span data-ttu-id="484f6-1914">date de validité</span><span class="sxs-lookup"><span data-stu-id="484f6-1914">date de validité</span></span> 
- <span data-ttu-id="484f6-1915">datum afloop</span><span class="sxs-lookup"><span data-stu-id="484f6-1915">datum afloop</span></span> 
- <span data-ttu-id="484f6-1916">datum van exp</span><span class="sxs-lookup"><span data-stu-id="484f6-1916">datum van exp</span></span> 
- <span data-ttu-id="484f6-1917">de afloop</span><span class="sxs-lookup"><span data-stu-id="484f6-1917">de afloop</span></span> 
- <span data-ttu-id="484f6-1918">espira</span><span class="sxs-lookup"><span data-stu-id="484f6-1918">espira</span></span> 
- <span data-ttu-id="484f6-1919">espira</span><span class="sxs-lookup"><span data-stu-id="484f6-1919">espira</span></span> 
- <span data-ttu-id="484f6-1920">exp date</span><span class="sxs-lookup"><span data-stu-id="484f6-1920">exp date</span></span> 
- <span data-ttu-id="484f6-1921">exp datum</span><span class="sxs-lookup"><span data-stu-id="484f6-1921">exp datum</span></span> 
- <span data-ttu-id="484f6-1922">时间</span><span class="sxs-lookup"><span data-stu-id="484f6-1922">expiration</span></span> 
- <span data-ttu-id="484f6-1923">何时</span><span class="sxs-lookup"><span data-stu-id="484f6-1923">expire</span></span> 
- <span data-ttu-id="484f6-1924">不久</span><span class="sxs-lookup"><span data-stu-id="484f6-1924">expires</span></span> 
- <span data-ttu-id="484f6-1925">过期</span><span class="sxs-lookup"><span data-stu-id="484f6-1925">expiry</span></span> 
- <span data-ttu-id="484f6-1926">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="484f6-1926">fecha de expiracion</span></span> 
- <span data-ttu-id="484f6-1927">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="484f6-1927">fecha de venc</span></span> 
- <span data-ttu-id="484f6-1928">gultig bis</span><span class="sxs-lookup"><span data-stu-id="484f6-1928">gultig bis</span></span> 
- <span data-ttu-id="484f6-1929">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="484f6-1929">gultigkeitsdatum</span></span> 
- <span data-ttu-id="484f6-1930">gültig bis</span><span class="sxs-lookup"><span data-stu-id="484f6-1930">gültig bis</span></span> 
- <span data-ttu-id="484f6-1931">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="484f6-1931">gültigkeitsdatum</span></span> 
- <span data-ttu-id="484f6-1932">la scadenza</span><span class="sxs-lookup"><span data-stu-id="484f6-1932">la scadenza</span></span> 
- <span data-ttu-id="484f6-1933">scadenza</span><span class="sxs-lookup"><span data-stu-id="484f6-1933">scadenza</span></span> 
- <span data-ttu-id="484f6-1934">valable</span><span class="sxs-lookup"><span data-stu-id="484f6-1934">valable</span></span> 
- <span data-ttu-id="484f6-1935">validade</span><span class="sxs-lookup"><span data-stu-id="484f6-1935">validade</span></span> 
- <span data-ttu-id="484f6-1936">valido hasta</span><span class="sxs-lookup"><span data-stu-id="484f6-1936">valido hasta</span></span> 
- <span data-ttu-id="484f6-1937">valor</span><span class="sxs-lookup"><span data-stu-id="484f6-1937">valor</span></span> 
- <span data-ttu-id="484f6-1938">venc</span><span class="sxs-lookup"><span data-stu-id="484f6-1938">venc</span></span> 
- <span data-ttu-id="484f6-1939">vencimento</span><span class="sxs-lookup"><span data-stu-id="484f6-1939">vencimento</span></span> 
- <span data-ttu-id="484f6-1940">vencimiento</span><span class="sxs-lookup"><span data-stu-id="484f6-1940">vencimiento</span></span> 
- <span data-ttu-id="484f6-1941">verloopt</span><span class="sxs-lookup"><span data-stu-id="484f6-1941">verloopt</span></span> 
- <span data-ttu-id="484f6-1942">vervaldag</span><span class="sxs-lookup"><span data-stu-id="484f6-1942">vervaldag</span></span> 
- <span data-ttu-id="484f6-1943">vervaldatum</span><span class="sxs-lookup"><span data-stu-id="484f6-1943">vervaldatum</span></span> 
- <span data-ttu-id="484f6-1944">vto</span><span class="sxs-lookup"><span data-stu-id="484f6-1944">vto</span></span> 
- <span data-ttu-id="484f6-1945">válido hasta</span><span class="sxs-lookup"><span data-stu-id="484f6-1945">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="484f6-1946">欧盟驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="484f6-1946">EU Driver's License Number</span></span>

<span data-ttu-id="484f6-1947">若要了解详细信息, 请参阅[EU 驱动程序的许可号敏感信息类型](eu-driver-s-license-number.md)。</span><span class="sxs-lookup"><span data-stu-id="484f6-1947">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="484f6-1948">欧盟国家身份证号</span><span class="sxs-lookup"><span data-stu-id="484f6-1948">EU National Identification Number</span></span>

<span data-ttu-id="484f6-1949">若要了解详细信息, 请参阅[EU 国家身份证号敏感信息类型](eu-national-identification-number.md)。</span><span class="sxs-lookup"><span data-stu-id="484f6-1949">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="484f6-1950">EU 护照号码</span><span class="sxs-lookup"><span data-stu-id="484f6-1950">EU Passport Number</span></span>

<span data-ttu-id="484f6-1951">若要了解详细信息, 请参阅[EU 护照号敏感信息类型](eu-passport-number.md)。</span><span class="sxs-lookup"><span data-stu-id="484f6-1951">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="484f6-1952">欧盟社会安全号码或等效 ID</span><span class="sxs-lookup"><span data-stu-id="484f6-1952">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="484f6-1953">若要了解详细信息, 请参阅[EU 社会保险号或等效 ID 敏感信息类型](eu-social-security-number-or-equivalent-id.md)。</span><span class="sxs-lookup"><span data-stu-id="484f6-1953">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="484f6-1954">EU 税标识号</span><span class="sxs-lookup"><span data-stu-id="484f6-1954">EU Tax Identification Number</span></span>

<span data-ttu-id="484f6-1955">若要了解详细信息, 请参阅[EU 纳税识别号敏感信息类型](eu-tax-identification-number.md)。</span><span class="sxs-lookup"><span data-stu-id="484f6-1955">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="484f6-1956">芬兰国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="484f6-1956">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="484f6-1957">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-1957">Format</span></span>

<span data-ttu-id="484f6-1958">六个数字加一个字符（表示一个世纪），加三个数字再加一个校验位</span><span class="sxs-lookup"><span data-stu-id="484f6-1958">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-1959">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-1959">Pattern</span></span>

<span data-ttu-id="484f6-1960">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="484f6-1960">Pattern must include all of the following:</span></span>
- <span data-ttu-id="484f6-1961">采用 DDMMYY 格式的六位数字，表示出生日期</span><span class="sxs-lookup"><span data-stu-id="484f6-1961">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="484f6-1962">世纪标记（“-”、“+”或“a”）</span><span class="sxs-lookup"><span data-stu-id="484f6-1962">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="484f6-1963">三位个人标识号</span><span class="sxs-lookup"><span data-stu-id="484f6-1963">Three-digit personal identification number</span></span> 
- <span data-ttu-id="484f6-1964">一个数字或字母（区分大小写），是校验位</span><span class="sxs-lookup"><span data-stu-id="484f6-1964">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-1965">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-1965">Checksum</span></span>

<span data-ttu-id="484f6-1966">是</span><span class="sxs-lookup"><span data-stu-id="484f6-1966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-1967">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-1967">Definition</span></span>

<span data-ttu-id="484f6-1968">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-1968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-1969">函数 Func_finnish_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-1969">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-1970">找到 Keyword_finnish_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-1970">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="484f6-1971">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-1971">The checksum passes.</span></span>

```
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="484f6-1972">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-1972">Keywords</span></span>

- <span data-ttu-id="484f6-1973">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="484f6-1973">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="484f6-1974">Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="484f6-1974">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="484f6-1975">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="484f6-1975">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="484f6-1976">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="484f6-1976">Personbeteckning</span></span>
- <span data-ttu-id="484f6-1977">Personnummer</span><span class="sxs-lookup"><span data-stu-id="484f6-1977">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="484f6-1978">芬兰护照号</span><span class="sxs-lookup"><span data-stu-id="484f6-1978">Finland Passport Number</span></span>

<span data-ttu-id="484f6-1979">设置九个字母和数字的组合的组合九个字母和数字的组合: 两个字母 (不区分大小写) 七个数字校验和无定义 DLP 策略是 75% 确信它检测到这种类型的敏感信息, 如果在300个字符的邻近性: 正则表达式 Regex_finland_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-1979">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
<span data-ttu-id="484f6-1980">找到 Keyword_finland_passport_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-1980">A keyword from Keyword_finland_passport_number is found.</span></span>
<!-- Finland Passport Number -->
<span data-ttu-id="484f6-1981"><Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="484f6-1981"></span></span>
<span data-ttu-id="484f6-1982">关键字 Keyword_finland_passport_number Passport Passi</span><span class="sxs-lookup"><span data-stu-id="484f6-1982">Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="484f6-1983">法国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="484f6-1983">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-1984">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-1984">Format</span></span>

<span data-ttu-id="484f6-1985">12 个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-1985">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-1986">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-1986">Pattern</span></span>

<span data-ttu-id="484f6-1987">12 个数字，会对类似模式（如法国电话号码）进行验证</span><span class="sxs-lookup"><span data-stu-id="484f6-1987">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-1988">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-1988">Checksum</span></span>

<span data-ttu-id="484f6-1989">否</span><span class="sxs-lookup"><span data-stu-id="484f6-1989">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-1990">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-1990">Definition</span></span>

<span data-ttu-id="484f6-1991">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-1991">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-1992">函数 Func_french_drivers_license 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-1992">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-1993">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="484f6-1993">At least one of the following is true:</span></span>
- <span data-ttu-id="484f6-1994">找到 Keyword_french_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-1994">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="484f6-1995">函数 Func_eu_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="484f6-1995">The function Func_eu_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-1996">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-1996">Keywords</span></span>

#### <a name="keywordfrenchdriverslicense"></a><span data-ttu-id="484f6-1997">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="484f6-1997">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="484f6-1998">drivers licence</span><span class="sxs-lookup"><span data-stu-id="484f6-1998">drivers licence</span></span>
- <span data-ttu-id="484f6-1999">drivers license</span><span class="sxs-lookup"><span data-stu-id="484f6-1999">drivers license</span></span>
- <span data-ttu-id="484f6-2000">driving licence</span><span class="sxs-lookup"><span data-stu-id="484f6-2000">driving licence</span></span>
- <span data-ttu-id="484f6-2001">driving license</span><span class="sxs-lookup"><span data-stu-id="484f6-2001">driving license</span></span>
- <span data-ttu-id="484f6-2002">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="484f6-2002">permis de conduire</span></span>
- <span data-ttu-id="484f6-2003">licence number</span><span class="sxs-lookup"><span data-stu-id="484f6-2003">licence number</span></span>
- <span data-ttu-id="484f6-2004">license number</span><span class="sxs-lookup"><span data-stu-id="484f6-2004">license number</span></span>
- <span data-ttu-id="484f6-2005">licence numbers</span><span class="sxs-lookup"><span data-stu-id="484f6-2005">licence numbers</span></span>
- <span data-ttu-id="484f6-2006">license numbers</span><span class="sxs-lookup"><span data-stu-id="484f6-2006">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="484f6-2007">法国国家/地区 ID 卡 (CNI)</span><span class="sxs-lookup"><span data-stu-id="484f6-2007">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="484f6-2008">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-2008">Format</span></span>

<span data-ttu-id="484f6-2009">12 个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2009">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-2010">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2010">Pattern</span></span>

<span data-ttu-id="484f6-2011">12 个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2011">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-2012">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-2012">Checksum</span></span>

<span data-ttu-id="484f6-2013">否</span><span class="sxs-lookup"><span data-stu-id="484f6-2013">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-2014">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-2014">Definition</span></span>

<span data-ttu-id="484f6-2015">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2015">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2016">正则表达式 Regex_france_cni 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2016">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="484f6-2017">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2017">Keywords</span></span>

<span data-ttu-id="484f6-2018">无</span><span class="sxs-lookup"><span data-stu-id="484f6-2018">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="484f6-2019">法国护照号码</span><span class="sxs-lookup"><span data-stu-id="484f6-2019">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-2020">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-2020">Format</span></span>

<span data-ttu-id="484f6-2021">9 个数字和字母</span><span class="sxs-lookup"><span data-stu-id="484f6-2021">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-2022">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2022">Pattern</span></span>

<span data-ttu-id="484f6-2023">九位数字和字母：</span><span class="sxs-lookup"><span data-stu-id="484f6-2023">Nine digits and letters:</span></span>
- <span data-ttu-id="484f6-2024">两位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2024">Two digits</span></span> 
- <span data-ttu-id="484f6-2025">两个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="484f6-2025">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="484f6-2026">五位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2026">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-2027">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-2027">Checksum</span></span>

<span data-ttu-id="484f6-2028">否</span><span class="sxs-lookup"><span data-stu-id="484f6-2028">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-2029">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-2029">Definition</span></span>

<span data-ttu-id="484f6-2030">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2030">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2031">函数 Func_fr_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2031">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2032">找到 Keyword_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2032">A keyword from Keyword_passport is found.</span></span>

```
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="484f6-2033">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2033">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="484f6-2034">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="484f6-2034">Keyword_passport</span></span>

- <span data-ttu-id="484f6-2035">Passport Number</span><span class="sxs-lookup"><span data-stu-id="484f6-2035">Passport Number</span></span>
- <span data-ttu-id="484f6-2036">Passport No</span><span class="sxs-lookup"><span data-stu-id="484f6-2036">Passport No</span></span>
- <span data-ttu-id="484f6-2037">Passport #</span><span class="sxs-lookup"><span data-stu-id="484f6-2037">Passport #</span></span>
- <span data-ttu-id="484f6-2038">登记卡</span><span class="sxs-lookup"><span data-stu-id="484f6-2038">Passport#</span></span>
- <span data-ttu-id="484f6-2039">PassportID</span><span class="sxs-lookup"><span data-stu-id="484f6-2039">PassportID</span></span>
- <span data-ttu-id="484f6-2040">Passportno</span><span class="sxs-lookup"><span data-stu-id="484f6-2040">Passportno</span></span>
- <span data-ttu-id="484f6-2041">passportnumber</span><span class="sxs-lookup"><span data-stu-id="484f6-2041">passportnumber</span></span>
- <span data-ttu-id="484f6-2042">パスポート</span><span class="sxs-lookup"><span data-stu-id="484f6-2042">パスポート</span></span>
- <span data-ttu-id="484f6-2043">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="484f6-2043">パスポート番号</span></span>
- <span data-ttu-id="484f6-2044">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="484f6-2044">パスポートのNum</span></span>
- <span data-ttu-id="484f6-2045">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="484f6-2045">パスポート ＃</span></span> 
- <span data-ttu-id="484f6-2046">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="484f6-2046">Numéro de passeport</span></span>
- <span data-ttu-id="484f6-2047">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="484f6-2047">Passeport n °</span></span>
- <span data-ttu-id="484f6-2048">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="484f6-2048">Passeport Non</span></span>
- <span data-ttu-id="484f6-2049">Passeport #</span><span class="sxs-lookup"><span data-stu-id="484f6-2049">Passeport #</span></span>
- <span data-ttu-id="484f6-2050">Passeport#</span><span class="sxs-lookup"><span data-stu-id="484f6-2050">Passeport#</span></span>
- <span data-ttu-id="484f6-2051">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="484f6-2051">PasseportNon</span></span>
- <span data-ttu-id="484f6-2052">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="484f6-2052">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="484f6-2053">法国社会保险号 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="484f6-2053">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="484f6-2054">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-2054">Format</span></span>

<span data-ttu-id="484f6-2055">15 个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2055">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-2056">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2056">Pattern</span></span>

<span data-ttu-id="484f6-2057">必须匹配两种模式之一：</span><span class="sxs-lookup"><span data-stu-id="484f6-2057">Must match one of two patterns:</span></span>
- <span data-ttu-id="484f6-2058">13位数, 后跟一个空格, 后跟两个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2058">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="484f6-2059">或</span><span class="sxs-lookup"><span data-stu-id="484f6-2059">or</span></span>
- <span data-ttu-id="484f6-2060">15 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2060">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-2061">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-2061">Checksum</span></span>

<span data-ttu-id="484f6-2062">是</span><span class="sxs-lookup"><span data-stu-id="484f6-2062">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-2063">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-2063">Definition</span></span>

<span data-ttu-id="484f6-2064">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2064">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2065">函数 Func_french_insee 或 Func_fr_insee 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2065">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2066">找到 Keyword_fr_insee 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2066">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="484f6-2067">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-2067">The checksum passes.</span></span>

<span data-ttu-id="484f6-2068">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2068">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2069">函数 Func_french_insee 或 Func_fr_insee 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2069">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2070">未找到 Keyword_fr_insee 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2070">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="484f6-2071">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-2071">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-2072">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2072">Keywords</span></span>

#### <a name="keywordfrinsee"></a><span data-ttu-id="484f6-2073">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="484f6-2073">Keyword_fr_insee</span></span>

- <span data-ttu-id="484f6-2074">insee</span><span class="sxs-lookup"><span data-stu-id="484f6-2074">insee</span></span>
- <span data-ttu-id="484f6-2075">securité sociale</span><span class="sxs-lookup"><span data-stu-id="484f6-2075">securité sociale</span></span>
- <span data-ttu-id="484f6-2076">securite sociale</span><span class="sxs-lookup"><span data-stu-id="484f6-2076">securite sociale</span></span>
- <span data-ttu-id="484f6-2077">national id</span><span class="sxs-lookup"><span data-stu-id="484f6-2077">national id</span></span>
- <span data-ttu-id="484f6-2078">national identification</span><span class="sxs-lookup"><span data-stu-id="484f6-2078">national identification</span></span>
- <span data-ttu-id="484f6-2079">numéro d identité</span><span class="sxs-lookup"><span data-stu-id="484f6-2079">numéro d'identité</span></span>
- <span data-ttu-id="484f6-2080">no d'identité</span><span class="sxs-lookup"><span data-stu-id="484f6-2080">no d'identité</span></span>
- <span data-ttu-id="484f6-2081">不。</span><span class="sxs-lookup"><span data-stu-id="484f6-2081">no.</span></span> <span data-ttu-id="484f6-2082">d'identité</span><span class="sxs-lookup"><span data-stu-id="484f6-2082">d'identité</span></span>
- <span data-ttu-id="484f6-2083">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="484f6-2083">numero d'identite</span></span>
- <span data-ttu-id="484f6-2084">no d'identite</span><span class="sxs-lookup"><span data-stu-id="484f6-2084">no d'identite</span></span>
- <span data-ttu-id="484f6-2085">不。</span><span class="sxs-lookup"><span data-stu-id="484f6-2085">no.</span></span> <span data-ttu-id="484f6-2086">d'identite</span><span class="sxs-lookup"><span data-stu-id="484f6-2086">d'identite</span></span>
- <span data-ttu-id="484f6-2087">social security number</span><span class="sxs-lookup"><span data-stu-id="484f6-2087">social security number</span></span>
- <span data-ttu-id="484f6-2088">social security code</span><span class="sxs-lookup"><span data-stu-id="484f6-2088">social security code</span></span>
- <span data-ttu-id="484f6-2089">social insurance number</span><span class="sxs-lookup"><span data-stu-id="484f6-2089">social insurance number</span></span>
- <span data-ttu-id="484f6-2090">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="484f6-2090">le numéro d'identification nationale</span></span>
- <span data-ttu-id="484f6-2091">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="484f6-2091">d'identité nationale</span></span>
- <span data-ttu-id="484f6-2092">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="484f6-2092">numéro de sécurité sociale</span></span>
- <span data-ttu-id="484f6-2093">le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="484f6-2093">le code de la sécurité sociale</span></span>
- <span data-ttu-id="484f6-2094">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="484f6-2094">numéro d'assurance sociale</span></span>
- <span data-ttu-id="484f6-2095">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="484f6-2095">numéro de sécu</span></span>
- <span data-ttu-id="484f6-2096">code sécu</span><span class="sxs-lookup"><span data-stu-id="484f6-2096">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="484f6-2097">德国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="484f6-2097">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-2098">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-2098">Format</span></span>

<span data-ttu-id="484f6-2099">11 个数字和字母组合</span><span class="sxs-lookup"><span data-stu-id="484f6-2099">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-2100">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2100">Pattern</span></span>

<span data-ttu-id="484f6-2101">11 位数字和字母（不区分大小写）：</span><span class="sxs-lookup"><span data-stu-id="484f6-2101">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="484f6-2102">一个数字或字母</span><span class="sxs-lookup"><span data-stu-id="484f6-2102">A digit or letter</span></span> 
- <span data-ttu-id="484f6-2103">两位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2103">Two digits</span></span> 
- <span data-ttu-id="484f6-2104">六位数字或字母</span><span class="sxs-lookup"><span data-stu-id="484f6-2104">Six digits or letters</span></span> 
- <span data-ttu-id="484f6-2105">一位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2105">A digit</span></span> 
- <span data-ttu-id="484f6-2106">一个数字或字母</span><span class="sxs-lookup"><span data-stu-id="484f6-2106">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-2107">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-2107">Checksum</span></span>

<span data-ttu-id="484f6-2108">是</span><span class="sxs-lookup"><span data-stu-id="484f6-2108">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-2109">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-2109">Definition</span></span>

<span data-ttu-id="484f6-2110">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2110">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2111">函数 Func_german_drivers_license 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2111">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2112">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="484f6-2112">At least one of the following is true:</span></span>
    - <span data-ttu-id="484f6-2113">找到 Keyword_german_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2113">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="484f6-2114">找到 Keyword_german_drivers_license_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2114">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="484f6-2115">找到 Keyword_german_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2115">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="484f6-2116">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-2116">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-2117">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2117">Keywords</span></span>

#### <a name="keywordgermandriverslicensenumber"></a><span data-ttu-id="484f6-2118">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="484f6-2118">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="484f6-2119">Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="484f6-2119">Führerschein</span></span>
- <span data-ttu-id="484f6-2120">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="484f6-2120">Fuhrerschein</span></span>
- <span data-ttu-id="484f6-2121">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="484f6-2121">Fuehrerschein</span></span>
- <span data-ttu-id="484f6-2122">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="484f6-2122">Führerscheinnummer</span></span>
- <span data-ttu-id="484f6-2123">Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="484f6-2123">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="484f6-2124">Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="484f6-2124">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="484f6-2125">Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="484f6-2125">Führerschein-</span></span> 
- <span data-ttu-id="484f6-2126">Fuhrerschein-</span><span class="sxs-lookup"><span data-stu-id="484f6-2126">Fuhrerschein-</span></span> 
- <span data-ttu-id="484f6-2127">Fuehrerschein-</span><span class="sxs-lookup"><span data-stu-id="484f6-2127">Fuehrerschein-</span></span> 
- <span data-ttu-id="484f6-2128">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="484f6-2128">FührerscheinnummerNr</span></span>
- <span data-ttu-id="484f6-2129">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="484f6-2129">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="484f6-2130">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="484f6-2130">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="484f6-2131">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="484f6-2131">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="484f6-2132">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="484f6-2132">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="484f6-2133">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="484f6-2133">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="484f6-2134">Führerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="484f6-2134">Führerschein- Nr</span></span>
- <span data-ttu-id="484f6-2135">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="484f6-2135">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="484f6-2136">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="484f6-2136">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="484f6-2137">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="484f6-2137">Führerschein- Klasse</span></span> 
- <span data-ttu-id="484f6-2138">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="484f6-2138">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="484f6-2139">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="484f6-2139">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="484f6-2140">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="484f6-2140">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="484f6-2141">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="484f6-2141">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="484f6-2142">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="484f6-2142">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="484f6-2143">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="484f6-2143">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="484f6-2144">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="484f6-2144">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="484f6-2145">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="484f6-2145">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="484f6-2146">Führerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="484f6-2146">Führerschein- Nr</span></span> 
- <span data-ttu-id="484f6-2147">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="484f6-2147">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="484f6-2148">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="484f6-2148">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="484f6-2149">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="484f6-2149">Führerschein- Klasse</span></span> 
- <span data-ttu-id="484f6-2150">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="484f6-2150">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="484f6-2151">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="484f6-2151">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="484f6-2152">通讯</span><span class="sxs-lookup"><span data-stu-id="484f6-2152">DL</span></span> 
- <span data-ttu-id="484f6-2153">DLS</span><span class="sxs-lookup"><span data-stu-id="484f6-2153">DLS</span></span>
- <span data-ttu-id="484f6-2154">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="484f6-2154">Driv Lic</span></span> 
- <span data-ttu-id="484f6-2155">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="484f6-2155">Driv Licen</span></span> 
- <span data-ttu-id="484f6-2156">Driv License</span><span class="sxs-lookup"><span data-stu-id="484f6-2156">Driv License</span></span>
- <span data-ttu-id="484f6-2157">Driv Licenses</span><span class="sxs-lookup"><span data-stu-id="484f6-2157">Driv Licenses</span></span> 
- <span data-ttu-id="484f6-2158">Driv Licence</span><span class="sxs-lookup"><span data-stu-id="484f6-2158">Driv Licence</span></span> 
- <span data-ttu-id="484f6-2159">Driv Licences</span><span class="sxs-lookup"><span data-stu-id="484f6-2159">Driv Licences</span></span> 
- <span data-ttu-id="484f6-2160">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="484f6-2160">Driv Lic</span></span> 
- <span data-ttu-id="484f6-2161">Driver Licen</span><span class="sxs-lookup"><span data-stu-id="484f6-2161">Driver Licen</span></span> 
- <span data-ttu-id="484f6-2162">Driver License</span><span class="sxs-lookup"><span data-stu-id="484f6-2162">Driver License</span></span> 
- <span data-ttu-id="484f6-2163">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="484f6-2163">Driver Licenses</span></span> 
- <span data-ttu-id="484f6-2164">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="484f6-2164">Driver Licence</span></span> 
- <span data-ttu-id="484f6-2165">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="484f6-2165">Driver Licences</span></span> 
- <span data-ttu-id="484f6-2166">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="484f6-2166">Drivers Lic</span></span> 
- <span data-ttu-id="484f6-2167">Drivers Licen</span><span class="sxs-lookup"><span data-stu-id="484f6-2167">Drivers Licen</span></span> 
- <span data-ttu-id="484f6-2168">Drivers License</span><span class="sxs-lookup"><span data-stu-id="484f6-2168">Drivers License</span></span> 
- <span data-ttu-id="484f6-2169">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="484f6-2169">Drivers Licenses</span></span> 
- <span data-ttu-id="484f6-2170">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="484f6-2170">Drivers Licence</span></span> 
- <span data-ttu-id="484f6-2171">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="484f6-2171">Drivers Licences</span></span> 
- <span data-ttu-id="484f6-2172">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="484f6-2172">Driver's Lic</span></span> 
- <span data-ttu-id="484f6-2173">Driver's Licen</span><span class="sxs-lookup"><span data-stu-id="484f6-2173">Driver's Licen</span></span> 
- <span data-ttu-id="484f6-2174">Driver's License</span><span class="sxs-lookup"><span data-stu-id="484f6-2174">Driver's License</span></span> 
- <span data-ttu-id="484f6-2175">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="484f6-2175">Driver's Licenses</span></span> 
- <span data-ttu-id="484f6-2176">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="484f6-2176">Driver's Licence</span></span> 
- <span data-ttu-id="484f6-2177">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="484f6-2177">Driver's Licences</span></span> 
- <span data-ttu-id="484f6-2178">Driving Lic</span><span class="sxs-lookup"><span data-stu-id="484f6-2178">Driving Lic</span></span> 
- <span data-ttu-id="484f6-2179">Driving Licen</span><span class="sxs-lookup"><span data-stu-id="484f6-2179">Driving Licen</span></span> 
- <span data-ttu-id="484f6-2180">Driving License</span><span class="sxs-lookup"><span data-stu-id="484f6-2180">Driving License</span></span> 
- <span data-ttu-id="484f6-2181">Driving Licenses</span><span class="sxs-lookup"><span data-stu-id="484f6-2181">Driving Licenses</span></span> 
- <span data-ttu-id="484f6-2182">Driving Licence</span><span class="sxs-lookup"><span data-stu-id="484f6-2182">Driving Licence</span></span> 
- <span data-ttu-id="484f6-2183">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="484f6-2183">Driving Licences</span></span>

#### <a name="keywordgermandriverslicensecollaborative"></a><span data-ttu-id="484f6-2184">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="484f6-2184">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="484f6-2185">Nr-Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="484f6-2185">Nr-Führerschein</span></span> 
- <span data-ttu-id="484f6-2186">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="484f6-2186">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="484f6-2187">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="484f6-2187">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="484f6-2188">Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="484f6-2188">No-Führerschein</span></span> 
- <span data-ttu-id="484f6-2189">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="484f6-2189">No-Fuhrerschein</span></span> 
- <span data-ttu-id="484f6-2190">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="484f6-2190">No-Fuehrerschein</span></span> 
- <span data-ttu-id="484f6-2191">N-Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="484f6-2191">N-Führerschein</span></span> 
- <span data-ttu-id="484f6-2192">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="484f6-2192">N-Fuhrerschein</span></span> 
- <span data-ttu-id="484f6-2193">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="484f6-2193">N-Fuehrerschein</span></span>
- <span data-ttu-id="484f6-2194">Nr-Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="484f6-2194">Nr-Führerschein</span></span> 
- <span data-ttu-id="484f6-2195">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="484f6-2195">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="484f6-2196">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="484f6-2196">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="484f6-2197">Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="484f6-2197">No-Führerschein</span></span> 
- <span data-ttu-id="484f6-2198">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="484f6-2198">No-Fuhrerschein</span></span> 
- <span data-ttu-id="484f6-2199">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="484f6-2199">No-Fuehrerschein</span></span> 
- <span data-ttu-id="484f6-2200">N-Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="484f6-2200">N-Führerschein</span></span> 
- <span data-ttu-id="484f6-2201">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="484f6-2201">N-Fuhrerschein</span></span> 
- <span data-ttu-id="484f6-2202">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="484f6-2202">N-Fuehrerschein</span></span> 

#### <a name="keywordgermandriverslicense"></a><span data-ttu-id="484f6-2203">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="484f6-2203">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="484f6-2204">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="484f6-2204">ausstellungsdatum</span></span>
- <span data-ttu-id="484f6-2205">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="484f6-2205">ausstellungsort</span></span>
- <span data-ttu-id="484f6-2206">ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="484f6-2206">ausstellende behöde</span></span>
- <span data-ttu-id="484f6-2207">ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="484f6-2207">ausstellende behorde</span></span>
- <span data-ttu-id="484f6-2208">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="484f6-2208">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="484f6-2209">德国护照号码</span><span class="sxs-lookup"><span data-stu-id="484f6-2209">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-2210">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-2210">Format</span></span>

<span data-ttu-id="484f6-2211">10 个数字或字母</span><span class="sxs-lookup"><span data-stu-id="484f6-2211">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-2212">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2212">Pattern</span></span>

<span data-ttu-id="484f6-2213">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="484f6-2213">Pattern must include all of the following:</span></span>
- <span data-ttu-id="484f6-2214">第一个字符是这一组（C、F、G、H、J、K）中的数字或字母</span><span class="sxs-lookup"><span data-stu-id="484f6-2214">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="484f6-2215">三位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2215">Three digits</span></span> 
- <span data-ttu-id="484f6-2216">五位数字或字母都来源于这一组（C、-H、J-N、P、R、T，V-Z）</span><span class="sxs-lookup"><span data-stu-id="484f6-2216">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="484f6-2217">一位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2217">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-2218">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-2218">Checksum</span></span>

<span data-ttu-id="484f6-2219">是</span><span class="sxs-lookup"><span data-stu-id="484f6-2219">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-2220">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-2220">Definition</span></span>

<span data-ttu-id="484f6-2221">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2221">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2222">函数 Func_german_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2222">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2223">找到以下任意五个关键字列表中的关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2223">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="484f6-2224">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-2224">The checksum passes.</span></span>

<span data-ttu-id="484f6-2225">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2226">函数 Func_german_passport_data 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2226">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2227">找到以下任意五个关键字列表中的关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2227">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="484f6-2228">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-2228">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-2229">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2229">Keywords</span></span>

#### <a name="keywordgermanpassport"></a><span data-ttu-id="484f6-2230">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="484f6-2230">Keyword_german_passport</span></span>

- <span data-ttu-id="484f6-2231">reisepass</span><span class="sxs-lookup"><span data-stu-id="484f6-2231">reisepass</span></span>
- <span data-ttu-id="484f6-2232">reisepasse</span><span class="sxs-lookup"><span data-stu-id="484f6-2232">reisepasse</span></span>
- <span data-ttu-id="484f6-2233">reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="484f6-2233">reisepassnummer</span></span>
- <span data-ttu-id="484f6-2234">登记卡</span><span class="sxs-lookup"><span data-stu-id="484f6-2234">passport</span></span>
- <span data-ttu-id="484f6-2235">passports</span><span class="sxs-lookup"><span data-stu-id="484f6-2235">passports</span></span>

#### <a name="keywordgermanpassportcollaborative"></a><span data-ttu-id="484f6-2236">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="484f6-2236">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="484f6-2237">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="484f6-2237">geburtsdatum</span></span>
- <span data-ttu-id="484f6-2238">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="484f6-2238">ausstellungsdatum</span></span>
- <span data-ttu-id="484f6-2239">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="484f6-2239">ausstellungsort</span></span>

#### <a name="keywordgermanpassportnumber"></a><span data-ttu-id="484f6-2240">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="484f6-2240">Keyword_german_passport_number</span></span>

<span data-ttu-id="484f6-2241">Reisepass Nr-Reisepass</span><span class="sxs-lookup"><span data-stu-id="484f6-2241">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keywordgermanpassport1"></a><span data-ttu-id="484f6-2242">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="484f6-2242">Keyword_german_passport1</span></span>

<span data-ttu-id="484f6-2243">Reisepass-Nr</span><span class="sxs-lookup"><span data-stu-id="484f6-2243">Reisepass-Nr</span></span>

#### <a name="keywordgermanpassport2"></a><span data-ttu-id="484f6-2244">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="484f6-2244">Keyword_german_passport2</span></span>

<span data-ttu-id="484f6-2245">bnationalit</span><span class="sxs-lookup"><span data-stu-id="484f6-2245">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="484f6-2246">德国身份证号码</span><span class="sxs-lookup"><span data-stu-id="484f6-2246">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-2247">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-2247">Format</span></span>

<span data-ttu-id="484f6-2248">自2010年11月1日起: 九个字母和数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2248">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="484f6-2249">从1年4月1987至31年10月 2010:10 位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2249">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-2250">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2250">Pattern</span></span>

<span data-ttu-id="484f6-2251">自 2010 年 11 月 1 日起：</span><span class="sxs-lookup"><span data-stu-id="484f6-2251">Since 1 November 2010:</span></span>
- <span data-ttu-id="484f6-2252">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="484f6-2252">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="484f6-2253">八个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2253">Eight digits</span></span>

<span data-ttu-id="484f6-2254">介于1年4月1987至 31 10 月 2010:</span><span class="sxs-lookup"><span data-stu-id="484f6-2254">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="484f6-2255">10 个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2255">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-2256">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-2256">Checksum</span></span>

<span data-ttu-id="484f6-2257">否</span><span class="sxs-lookup"><span data-stu-id="484f6-2257">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-2258">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-2258">Definition</span></span>

<span data-ttu-id="484f6-2259">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2259">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2260">正则表达式 Regex_germany_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2260">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2261">找到 Keyword_germany_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2261">A keyword from Keyword_germany_id_card is found.</span></span>

```
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="484f6-2262">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2262">Keywords</span></span>

#### <a name="keywordgermanyidcard"></a><span data-ttu-id="484f6-2263">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="484f6-2263">Keyword_germany_id_card</span></span>

- <span data-ttu-id="484f6-2264">Identity Card</span><span class="sxs-lookup"><span data-stu-id="484f6-2264">Identity Card</span></span>
- <span data-ttu-id="484f6-2265">ID</span><span class="sxs-lookup"><span data-stu-id="484f6-2265">ID</span></span>
- <span data-ttu-id="484f6-2266">Id</span><span class="sxs-lookup"><span data-stu-id="484f6-2266">Identification</span></span>
- <span data-ttu-id="484f6-2267">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="484f6-2267">Personalausweis</span></span>
- <span data-ttu-id="484f6-2268">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="484f6-2268">Identifizierungsnummer</span></span>
- <span data-ttu-id="484f6-2269">Ausweis</span><span class="sxs-lookup"><span data-stu-id="484f6-2269">Ausweis</span></span>
- <span data-ttu-id="484f6-2270">Identifikation</span><span class="sxs-lookup"><span data-stu-id="484f6-2270">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="484f6-2271">希腊国家 ID 卡</span><span class="sxs-lookup"><span data-stu-id="484f6-2271">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="484f6-2272">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-2272">Format</span></span>

<span data-ttu-id="484f6-2273">7-8 个字母和数字组合加一个短划线</span><span class="sxs-lookup"><span data-stu-id="484f6-2273">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-2274">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2274">Pattern</span></span>

<span data-ttu-id="484f6-2275">七个字母和数字（旧格式）：</span><span class="sxs-lookup"><span data-stu-id="484f6-2275">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="484f6-2276">一个字母（希腊字母表中的任一字母） </span><span class="sxs-lookup"><span data-stu-id="484f6-2276">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="484f6-2277">一个短划线 </span><span class="sxs-lookup"><span data-stu-id="484f6-2277">A dash</span></span> 
- <span data-ttu-id="484f6-2278">六位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2278">Six digits</span></span>

<span data-ttu-id="484f6-2279">八个字母和数字（新格式）：</span><span class="sxs-lookup"><span data-stu-id="484f6-2279">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="484f6-2280">大写字符同时出现在希腊和拉丁字母表中的两个字母 (ABEZHIKMNOPTYX) </span><span class="sxs-lookup"><span data-stu-id="484f6-2280">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="484f6-2281">一个短划线 </span><span class="sxs-lookup"><span data-stu-id="484f6-2281">A dash</span></span> 
- <span data-ttu-id="484f6-2282">六位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2282">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-2283">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-2283">Checksum</span></span>

<span data-ttu-id="484f6-2284">否</span><span class="sxs-lookup"><span data-stu-id="484f6-2284">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-2285">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-2285">Definition</span></span>

<span data-ttu-id="484f6-2286">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2286">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2287">正则表达式 Regex_greece_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2287">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2288">找到 Keyword_greece_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2288">A keyword from Keyword_greece_id_card is found.</span></span>

```
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="484f6-2289">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2289">Keywords</span></span>

#### <a name="keywordgreeceidcard"></a><span data-ttu-id="484f6-2290">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="484f6-2290">Keyword_greece_id_card</span></span>

- <span data-ttu-id="484f6-2291">Greek identity Card</span><span class="sxs-lookup"><span data-stu-id="484f6-2291">Greek identity Card</span></span>
- <span data-ttu-id="484f6-2292">Tautotita</span><span class="sxs-lookup"><span data-stu-id="484f6-2292">Tautotita</span></span>
- <span data-ttu-id="484f6-2293">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="484f6-2293">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="484f6-2294">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="484f6-2294">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="484f6-2295">香港身份证 (HKID) 号</span><span class="sxs-lookup"><span data-stu-id="484f6-2295">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-2296">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-2296">Format</span></span>

<span data-ttu-id="484f6-2297">8-9 个字母和数字组合，最后一个字符两边可选择加括号</span><span class="sxs-lookup"><span data-stu-id="484f6-2297">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-2298">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2298">Pattern</span></span>

<span data-ttu-id="484f6-2299">8-9 个字母组合：</span><span class="sxs-lookup"><span data-stu-id="484f6-2299">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="484f6-2300">1-2 个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="484f6-2300">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="484f6-2301">六个数字 </span><span class="sxs-lookup"><span data-stu-id="484f6-2301">Six digits</span></span> 
- <span data-ttu-id="484f6-2302">最后一个字符（任意数字或字母 A）是校验位，两边可以选择加括号。</span><span class="sxs-lookup"><span data-stu-id="484f6-2302">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-2303">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-2303">Checksum</span></span>

<span data-ttu-id="484f6-2304">是</span><span class="sxs-lookup"><span data-stu-id="484f6-2304">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-2305">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-2305">Definition</span></span>

<span data-ttu-id="484f6-2306">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2306">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2307">函数 Func_hong_kong_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2307">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2308">找到 Keyword_hong_kong_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2308">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="484f6-2309">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-2309">The checksum passes.</span></span>

<span data-ttu-id="484f6-2310">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2310">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2311">函数 Func_hong_kong_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2311">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2312">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-2312">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-2313">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2313">Keywords</span></span>

#### <a name="keywordhongkongidcard"></a><span data-ttu-id="484f6-2314">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="484f6-2314">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="484f6-2315">中国香港恒等卡片</span><span class="sxs-lookup"><span data-stu-id="484f6-2315">hong kong identity card</span></span>
- <span data-ttu-id="484f6-2316">HKIDC</span><span class="sxs-lookup"><span data-stu-id="484f6-2316">HKIDC</span></span>
- <span data-ttu-id="484f6-2317">id card</span><span class="sxs-lookup"><span data-stu-id="484f6-2317">id card</span></span>
- <span data-ttu-id="484f6-2318">identity card</span><span class="sxs-lookup"><span data-stu-id="484f6-2318">identity card</span></span>
- <span data-ttu-id="484f6-2319">hk identity 卡片</span><span class="sxs-lookup"><span data-stu-id="484f6-2319">hk identity card</span></span>
- <span data-ttu-id="484f6-2320">香港 id</span><span class="sxs-lookup"><span data-stu-id="484f6-2320">hong kong id</span></span>
- <span data-ttu-id="484f6-2321">香港身份證</span><span class="sxs-lookup"><span data-stu-id="484f6-2321">香港身份證</span></span>
- <span data-ttu-id="484f6-2322">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="484f6-2322">香港永久性居民身份證</span></span>
- <span data-ttu-id="484f6-2323">證</span><span class="sxs-lookup"><span data-stu-id="484f6-2323">身份證</span></span>
- <span data-ttu-id="484f6-2324">身份証</span><span class="sxs-lookup"><span data-stu-id="484f6-2324">身份証</span></span>
- <span data-ttu-id="484f6-2325">身分證</span><span class="sxs-lookup"><span data-stu-id="484f6-2325">身分證</span></span>
- <span data-ttu-id="484f6-2326">身分証</span><span class="sxs-lookup"><span data-stu-id="484f6-2326">身分証</span></span>
- <span data-ttu-id="484f6-2327">香港身份証</span><span class="sxs-lookup"><span data-stu-id="484f6-2327">香港身份証</span></span>
- <span data-ttu-id="484f6-2328">香港身分證</span><span class="sxs-lookup"><span data-stu-id="484f6-2328">香港身分證</span></span>
- <span data-ttu-id="484f6-2329">香港身分証</span><span class="sxs-lookup"><span data-stu-id="484f6-2329">香港身分証</span></span>
- <span data-ttu-id="484f6-2330">香港身份證</span><span class="sxs-lookup"><span data-stu-id="484f6-2330">香港身份證</span></span>
- <span data-ttu-id="484f6-2331">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="484f6-2331">香港居民身份證</span></span>
- <span data-ttu-id="484f6-2332">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="484f6-2332">香港居民身份証</span></span>
- <span data-ttu-id="484f6-2333">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="484f6-2333">香港居民身分證</span></span>
- <span data-ttu-id="484f6-2334">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="484f6-2334">香港居民身分証</span></span>
- <span data-ttu-id="484f6-2335">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="484f6-2335">香港永久性居民身份証</span></span>
- <span data-ttu-id="484f6-2336">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="484f6-2336">香港永久性居民身分證</span></span>
- <span data-ttu-id="484f6-2337">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="484f6-2337">香港永久性居民身分証</span></span>
- <span data-ttu-id="484f6-2338">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="484f6-2338">香港永久性居民身份證</span></span>
- <span data-ttu-id="484f6-2339">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="484f6-2339">香港非永久性居民身份證</span></span>
- <span data-ttu-id="484f6-2340">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="484f6-2340">香港非永久性居民身份証</span></span>
- <span data-ttu-id="484f6-2341">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="484f6-2341">香港非永久性居民身分證</span></span>
- <span data-ttu-id="484f6-2342">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="484f6-2342">香港非永久性居民身分証</span></span>
- <span data-ttu-id="484f6-2343">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="484f6-2343">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="484f6-2344">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="484f6-2344">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="484f6-2345">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="484f6-2345">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="484f6-2346">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="484f6-2346">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="484f6-2347">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="484f6-2347">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="484f6-2348">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="484f6-2348">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="484f6-2349">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="484f6-2349">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="484f6-2350">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="484f6-2350">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="484f6-2351">印度永久帐号 (PAN)</span><span class="sxs-lookup"><span data-stu-id="484f6-2351">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="484f6-2352">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-2352">Format</span></span>

<span data-ttu-id="484f6-2353">10 个字母或数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2353">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-2354">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2354">Pattern</span></span>

<span data-ttu-id="484f6-2355">10 个字母或数字：</span><span class="sxs-lookup"><span data-stu-id="484f6-2355">10 letters or digits:</span></span>
- <span data-ttu-id="484f6-2356">五个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="484f6-2356">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="484f6-2357">四位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2357">Four digits</span></span> 
- <span data-ttu-id="484f6-2358">一个字母，是字母校验位</span><span class="sxs-lookup"><span data-stu-id="484f6-2358">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-2359">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-2359">Checksum</span></span>

<span data-ttu-id="484f6-2360">是</span><span class="sxs-lookup"><span data-stu-id="484f6-2360">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-2361">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-2361">Definition</span></span>

<span data-ttu-id="484f6-2362">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2362">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2363">正则表达式 Regex_india_permanent_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2363">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2364">找到 Keyword_india_permanent_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2364">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="484f6-2365">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-2365">The checksum passes.</span></span>

```
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="484f6-2366">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2366">Keywords</span></span>

#### <a name="keywordindiapermanentaccountnumber"></a><span data-ttu-id="484f6-2367">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="484f6-2367">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="484f6-2368">Permanent Account Number</span><span class="sxs-lookup"><span data-stu-id="484f6-2368">Permanent Account Number</span></span> 
- <span data-ttu-id="484f6-2369">蛋糕</span><span class="sxs-lookup"><span data-stu-id="484f6-2369">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="484f6-2370">India Unique Identification (Aadhaar) Number</span><span class="sxs-lookup"><span data-stu-id="484f6-2370">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-2371">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-2371">Format</span></span>

<span data-ttu-id="484f6-2372">12 个数字（包含可选空格或短划线）</span><span class="sxs-lookup"><span data-stu-id="484f6-2372">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-2373">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2373">Pattern</span></span>

<span data-ttu-id="484f6-2374">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="484f6-2374">12 digits:</span></span>
- <span data-ttu-id="484f6-2375">四个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2375">Four digits</span></span> 
- <span data-ttu-id="484f6-2376">一个可选空格或短划线 </span><span class="sxs-lookup"><span data-stu-id="484f6-2376">An optional space or dash</span></span> 
- <span data-ttu-id="484f6-2377">四个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2377">Four digits</span></span> 
- <span data-ttu-id="484f6-2378">一个可选空格或短划线 </span><span class="sxs-lookup"><span data-stu-id="484f6-2378">An optional space or dash</span></span> 
- <span data-ttu-id="484f6-2379">最后一个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="484f6-2379">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-2380">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-2380">Checksum</span></span>

<span data-ttu-id="484f6-2381">是</span><span class="sxs-lookup"><span data-stu-id="484f6-2381">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-2382">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-2382">Definition</span></span>

<span data-ttu-id="484f6-2383">DLP 策略 85% 确信在300个字符的邻近度内检测到此类型的敏感信息: 函数 Func_india_aadhaar 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2383">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="484f6-2384">找到 Keyword_india_aadhar 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2384">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="484f6-2385">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-2385">The checksum passes.</span></span>
<span data-ttu-id="484f6-2386">DLP 策略 75% 确信在300个字符的邻近度内检测到此类型的敏感信息: 函数 Func_india_aadhaar 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2386">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="484f6-2387">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-2387">The checksum passes.</span></span>
<!-- India Unique Identification (Aadhaar) number -->
<span data-ttu-id="484f6-2388"><Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="484f6-2388"></span></span>

### <a name="keywords"></a><span data-ttu-id="484f6-2389">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2389">Keywords</span></span>
   
#### <a name="keywordindiaaadhar"></a><span data-ttu-id="484f6-2390">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="484f6-2390">Keyword_india_aadhar</span></span>
- <span data-ttu-id="484f6-2391">Aadhar</span><span class="sxs-lookup"><span data-stu-id="484f6-2391">Aadhar</span></span>
- <span data-ttu-id="484f6-2392">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="484f6-2392">Aadhaar</span></span>
- <span data-ttu-id="484f6-2393">UID</span><span class="sxs-lookup"><span data-stu-id="484f6-2393">UID</span></span>
- <span data-ttu-id="484f6-2394">आधार</span><span class="sxs-lookup"><span data-stu-id="484f6-2394">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="484f6-2395">印度尼西亚身份证 (KTP) 号</span><span class="sxs-lookup"><span data-stu-id="484f6-2395">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-2396">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-2396">Format</span></span>

<span data-ttu-id="484f6-2397">16 个数字（包含可选点）</span><span class="sxs-lookup"><span data-stu-id="484f6-2397">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-2398">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2398">Pattern</span></span>

<span data-ttu-id="484f6-2399">16 个数字：</span><span class="sxs-lookup"><span data-stu-id="484f6-2399">16 digits:</span></span>
- <span data-ttu-id="484f6-2400">两位省代码 </span><span class="sxs-lookup"><span data-stu-id="484f6-2400">Two-digit province code</span></span> 
- <span data-ttu-id="484f6-2401">一个点（可选） </span><span class="sxs-lookup"><span data-stu-id="484f6-2401">A period (optional)</span></span> 
- <span data-ttu-id="484f6-2402">两位摄政统治区或城市代码 </span><span class="sxs-lookup"><span data-stu-id="484f6-2402">Two-digit regency or city code</span></span> 
- <span data-ttu-id="484f6-2403">两位住宅小区代码 </span><span class="sxs-lookup"><span data-stu-id="484f6-2403">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="484f6-2404">一个点（可选） </span><span class="sxs-lookup"><span data-stu-id="484f6-2404">A period (optional)</span></span> 
- <span data-ttu-id="484f6-2405">六个数字，采用  DDMMYY 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="484f6-2405">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="484f6-2406">一个点（可选） </span><span class="sxs-lookup"><span data-stu-id="484f6-2406">A period (optional)</span></span> 
- <span data-ttu-id="484f6-2407">四个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2407">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-2408">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-2408">Checksum</span></span>

<span data-ttu-id="484f6-2409">否</span><span class="sxs-lookup"><span data-stu-id="484f6-2409">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-2410">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-2410">Definition</span></span>

<span data-ttu-id="484f6-2411">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2412">正则表达式 Regex_indonesia_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2412">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2413">找到 Keyword_indonesia_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2413">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="484f6-2414">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2415">正则表达式 Regex_indonesia_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2415">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-2416">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2416">Keywords</span></span>
   
#### <a name="keywordindonesiaidcard"></a><span data-ttu-id="484f6-2417">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="484f6-2417">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="484f6-2418">KTP</span><span class="sxs-lookup"><span data-stu-id="484f6-2418">KTP</span></span>
- <span data-ttu-id="484f6-2419">Kartu Tanda Penduduk</span><span class="sxs-lookup"><span data-stu-id="484f6-2419">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="484f6-2420">Nomor Induk Kependudukan</span><span class="sxs-lookup"><span data-stu-id="484f6-2420">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="484f6-2421">国际银行帐号 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="484f6-2421">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="484f6-2422">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-2422">Format</span></span>

<span data-ttu-id="484f6-2423">国家/地区代码（两个字母）加校验位（两个数字）以及 bban 号码（最多 30 个字符）</span><span class="sxs-lookup"><span data-stu-id="484f6-2423">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-2424">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2424">Pattern</span></span>

<span data-ttu-id="484f6-2425">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="484f6-2425">Pattern must include all of the following:</span></span>

- <span data-ttu-id="484f6-2426">两个字母的国家/地区代码</span><span class="sxs-lookup"><span data-stu-id="484f6-2426">Two-letter country code</span></span>
- <span data-ttu-id="484f6-2427">两个校验位（后跟一个可选空间） </span><span class="sxs-lookup"><span data-stu-id="484f6-2427">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="484f6-2428">1-7 个包含 4 个字母或数字的组（可以使用空格进行分隔）</span><span class="sxs-lookup"><span data-stu-id="484f6-2428">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="484f6-2429">1-3 个字母或数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2429">1-3 letters or digits</span></span>

<span data-ttu-id="484f6-p135">每个国家/地区的格式稍有不同。IBAN 敏感信息类型涵盖这 60 个国家/地区：</span><span class="sxs-lookup"><span data-stu-id="484f6-p135">The format for each country is slightly different. The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="484f6-2432">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span><span class="sxs-lookup"><span data-stu-id="484f6-2432">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-2433">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-2433">Checksum</span></span>

<span data-ttu-id="484f6-2434">是</span><span class="sxs-lookup"><span data-stu-id="484f6-2434">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-2435">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-2435">Definition</span></span>

<span data-ttu-id="484f6-2436">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2436">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2437">函数 Func_iban 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2437">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2438">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-2438">The checksum passes.</span></span>

```
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="484f6-2439">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2439">Keywords</span></span>

<span data-ttu-id="484f6-2440">无</span><span class="sxs-lookup"><span data-stu-id="484f6-2440">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="484f6-2441">IP 地址</span><span class="sxs-lookup"><span data-stu-id="484f6-2441">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="484f6-2442">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-2442">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="484f6-2443">IPv4</span><span class="sxs-lookup"><span data-stu-id="484f6-2443">IPv4:</span></span>
<span data-ttu-id="484f6-2444">解释 IPv4 地址格式化（点）版本或非格式化（没有点）版本的复杂模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2444">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="484f6-2445">Ipv4</span><span class="sxs-lookup"><span data-stu-id="484f6-2445">IPv6:</span></span>
<span data-ttu-id="484f6-2446"> 解释格式化 IPv6 号码（包含冒号）的复杂模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2446">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-2447">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2447">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-2448">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-2448">Checksum</span></span>

<span data-ttu-id="484f6-2449">否</span><span class="sxs-lookup"><span data-stu-id="484f6-2449">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-2450">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-2450">Definition</span></span>

<span data-ttu-id="484f6-2451">对于 IPv6，在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2451">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2452">正则表达式 Regex_ipv6_address 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2452">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2453">未找到 Keyword_ipaddress 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2453">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="484f6-2454">对于 IPv4，在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2454">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2455">正则表达式 Regex_ipv4_address 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2455">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2456">找到 Keyword_ipaddress 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2456">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="484f6-2457">对于 IPv6，在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2457">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2458">正则表达式 Regex_ipv6_address 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2458">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2459">未找到 Keyword_ipaddress 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2459">No keyword from Keyword_ipaddress is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-2460">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2460">Keywords</span></span>

#### <a name="keywordipaddress"></a><span data-ttu-id="484f6-2461">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="484f6-2461">Keyword_ipaddress</span></span>

- <span data-ttu-id="484f6-2462">IP（此关键字区分大小写）</span><span class="sxs-lookup"><span data-stu-id="484f6-2462">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="484f6-2463">ip address</span><span class="sxs-lookup"><span data-stu-id="484f6-2463">ip address</span></span> 
- <span data-ttu-id="484f6-2464">ip addresses</span><span class="sxs-lookup"><span data-stu-id="484f6-2464">ip addresses</span></span>
- <span data-ttu-id="484f6-2465">internet protocol</span><span class="sxs-lookup"><span data-stu-id="484f6-2465">internet protocol</span></span>
- <span data-ttu-id="484f6-2466">IP-כתובת ה</span><span class="sxs-lookup"><span data-stu-id="484f6-2466">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="484f6-2467">国际分类的 Diseases (ICD-10 CM)</span><span class="sxs-lookup"><span data-stu-id="484f6-2467">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="484f6-2468">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-2468">Format</span></span>

<span data-ttu-id="484f6-2469">Dictionary</span><span class="sxs-lookup"><span data-stu-id="484f6-2469">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-2470">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2470">Pattern</span></span>

<span data-ttu-id="484f6-2471">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2471">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-2472">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-2472">Checksum</span></span>

<span data-ttu-id="484f6-2473">否</span><span class="sxs-lookup"><span data-stu-id="484f6-2473">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-2474">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-2474">Definition</span></span>

<span data-ttu-id="484f6-2475">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2475">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2476">找到 Dictionary_icd_10_cm 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2476">A keyword from Dictionary_icd_10_cm is found.</span></span>

```
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

<span data-ttu-id="484f6-2477">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2477">Keywords</span></span>

<span data-ttu-id="484f6-2478">Dictionary_icd_10_cm 关键字词典中的任何术语, 它基于[Diseases 的国际分类、第十个修订、临床修改 (icd-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604)。</span><span class="sxs-lookup"><span data-stu-id="484f6-2478">Any term from the Dictionary_icd_10_cm keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="484f6-2479">此类型仅查找术语, 而不是保险代码。</span><span class="sxs-lookup"><span data-stu-id="484f6-2479">This type looks only for the term, not the insurance codes.</span></span>

   
## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="484f6-2480">国际分类的 Diseases (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="484f6-2480">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="484f6-2481">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-2481">Format</span></span>

<span data-ttu-id="484f6-2482">Dictionary</span><span class="sxs-lookup"><span data-stu-id="484f6-2482">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-2483">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2483">Pattern</span></span>

<span data-ttu-id="484f6-2484">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2484">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-2485">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-2485">Checksum</span></span>

<span data-ttu-id="484f6-2486">否</span><span class="sxs-lookup"><span data-stu-id="484f6-2486">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-2487">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-2487">Definition</span></span>

<span data-ttu-id="484f6-2488">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2488">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2489">找到 Dictionary_icd_9_cm 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2489">A keyword from Dictionary_icd_9_cm is found.</span></span>

```
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="484f6-2490">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2490">Keywords</span></span>

<span data-ttu-id="484f6-2491">Dictionary_icd_9_cm 关键字词典中的任何术语, 基于[Diseases 的国际分类、第九修订版、临床修改 (icd-9 cm)](https://go.microsoft.com/fwlink/?linkid=852605)。</span><span class="sxs-lookup"><span data-stu-id="484f6-2491">Any term from the Dictionary_icd_9_cm keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="484f6-2492">此类型仅查找术语, 而不是保险代码。</span><span class="sxs-lookup"><span data-stu-id="484f6-2492">This type looks only for the term, not the insurance codes.</span></span>
   
## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="484f6-2493">爱尔兰个人公共服务 (PPS) 号码</span><span class="sxs-lookup"><span data-stu-id="484f6-2493">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-2494">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-2494">Format</span></span>

<span data-ttu-id="484f6-2495">旧格式 (到 31 Dec 2012):</span><span class="sxs-lookup"><span data-stu-id="484f6-2495">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="484f6-2496">七位数字后跟 1-2  个字母 </span><span class="sxs-lookup"><span data-stu-id="484f6-2496">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="484f6-2497">新格式 (2013 年1月1日和之后):</span><span class="sxs-lookup"><span data-stu-id="484f6-2497">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="484f6-2498">七位数字后跟两个字母</span><span class="sxs-lookup"><span data-stu-id="484f6-2498">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-2499">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2499">Pattern</span></span>

<span data-ttu-id="484f6-2500">旧格式 (到 31 Dec 2012):</span><span class="sxs-lookup"><span data-stu-id="484f6-2500">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="484f6-2501">七个数字 </span><span class="sxs-lookup"><span data-stu-id="484f6-2501">Seven digits</span></span> 
- <span data-ttu-id="484f6-2502">1-2 个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="484f6-2502">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="484f6-2503">新格式 (2013 年1月1日和之后):</span><span class="sxs-lookup"><span data-stu-id="484f6-2503">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="484f6-2504">七个数字 </span><span class="sxs-lookup"><span data-stu-id="484f6-2504">Seven digits</span></span> 
- <span data-ttu-id="484f6-2505">一个字母（不区分大小写），是字母校验位 </span><span class="sxs-lookup"><span data-stu-id="484f6-2505">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="484f6-2506">字母“A”或“H”（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="484f6-2506">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-2507">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-2507">Checksum</span></span>

<span data-ttu-id="484f6-2508">是</span><span class="sxs-lookup"><span data-stu-id="484f6-2508">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-2509">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-2509">Definition</span></span>

<span data-ttu-id="484f6-2510">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2510">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2511">函数 Func_ireland_pps 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2511">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2512">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="484f6-2512">One of the following is true:</span></span>
    - <span data-ttu-id="484f6-2513">找到 Keyword_ireland_pps 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2513">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="484f6-2514">函数 Func_eu_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="484f6-2514">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="484f6-2515">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-2515">The checksum passes.</span></span>

<span data-ttu-id="484f6-2516">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2516">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2517">函数 Func_ireland_pps 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2517">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2518">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-2518">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-2519">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2519">Keywords</span></span>

#### <a name="keywordirelandpps"></a><span data-ttu-id="484f6-2520">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="484f6-2520">Keyword_ireland_pps</span></span>

- <span data-ttu-id="484f6-2521">Personal Public Service Number</span><span class="sxs-lookup"><span data-stu-id="484f6-2521">Personal Public Service Number</span></span> 
- <span data-ttu-id="484f6-2522">PPS Number</span><span class="sxs-lookup"><span data-stu-id="484f6-2522">PPS Number</span></span> 
- <span data-ttu-id="484f6-2523">PPS Num</span><span class="sxs-lookup"><span data-stu-id="484f6-2523">PPS Num</span></span> 
- <span data-ttu-id="484f6-2524">PPS No.</span><span class="sxs-lookup"><span data-stu-id="484f6-2524">PPS No.</span></span> 
- <span data-ttu-id="484f6-2525">PPS #</span><span class="sxs-lookup"><span data-stu-id="484f6-2525">PPS #</span></span> 
- <span data-ttu-id="484f6-2526">.PPS</span><span class="sxs-lookup"><span data-stu-id="484f6-2526">PPS#</span></span> 
- <span data-ttu-id="484f6-2527">PPSN</span><span class="sxs-lookup"><span data-stu-id="484f6-2527">PPSN</span></span> 
- <span data-ttu-id="484f6-2528">Public Services Card</span><span class="sxs-lookup"><span data-stu-id="484f6-2528">Public Services Card</span></span> 
- <span data-ttu-id="484f6-2529">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="484f6-2529">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="484f6-2530">Uimh.</span><span class="sxs-lookup"><span data-stu-id="484f6-2530">Uimh.</span></span> <span data-ttu-id="484f6-2531">PSP</span><span class="sxs-lookup"><span data-stu-id="484f6-2531">PSP</span></span> 
- <span data-ttu-id="484f6-2532">PSP</span><span class="sxs-lookup"><span data-stu-id="484f6-2532">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="484f6-2533">以色列银行帐号</span><span class="sxs-lookup"><span data-stu-id="484f6-2533">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-2534">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-2534">Format</span></span>

<span data-ttu-id="484f6-2535">13 位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2535">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-2536">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2536">Pattern</span></span>

<span data-ttu-id="484f6-2537">格式</span><span class="sxs-lookup"><span data-stu-id="484f6-2537">Formatted:</span></span>
- <span data-ttu-id="484f6-2538">两位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2538">Two digits</span></span> 
- <span data-ttu-id="484f6-2539">破折号</span><span class="sxs-lookup"><span data-stu-id="484f6-2539">A dash</span></span> 
- <span data-ttu-id="484f6-2540">三位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2540">Three digits</span></span> 
- <span data-ttu-id="484f6-2541">破折号</span><span class="sxs-lookup"><span data-stu-id="484f6-2541">A dash</span></span> 
- <span data-ttu-id="484f6-2542">八位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2542">Eight digits</span></span>

<span data-ttu-id="484f6-2543">纯</span><span class="sxs-lookup"><span data-stu-id="484f6-2543">Unformatted:</span></span>
- <span data-ttu-id="484f6-2544">	13 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2544">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-2545">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-2545">Checksum</span></span>

<span data-ttu-id="484f6-2546">否</span><span class="sxs-lookup"><span data-stu-id="484f6-2546">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-2547">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-2547">Definition</span></span>

<span data-ttu-id="484f6-2548">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2548">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2549">正则表达式 Regex_israel_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2549">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2550">找到 Keyword_israel_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2550">A keyword from Keyword_israel_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-2551">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2551">Keywords</span></span>

#### <a name="keywordisraelbankaccountnumber"></a><span data-ttu-id="484f6-2552">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="484f6-2552">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="484f6-2553">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="484f6-2553">Bank Account Number</span></span> 
- <span data-ttu-id="484f6-2554">Bank Account</span><span class="sxs-lookup"><span data-stu-id="484f6-2554">Bank Account</span></span> 
- <span data-ttu-id="484f6-2555">Account Number</span><span class="sxs-lookup"><span data-stu-id="484f6-2555">Account Number</span></span> 
- <span data-ttu-id="484f6-2556">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="484f6-2556">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="484f6-2557">以色列国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="484f6-2557">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="484f6-2558">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-2558">Format</span></span>

<span data-ttu-id="484f6-2559">九个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2559">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-2560">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2560">Pattern</span></span>

<span data-ttu-id="484f6-2561">九个连续的数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2561">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-2562">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-2562">Checksum</span></span>

<span data-ttu-id="484f6-2563">是</span><span class="sxs-lookup"><span data-stu-id="484f6-2563">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-2564">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-2564">Definition</span></span>

<span data-ttu-id="484f6-2565">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2565">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2566">函数 Func_israeli_national_id_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2566">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2567">找到 Keyword_Israel_National_ID 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2567">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="484f6-2568">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-2568">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-2569">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2569">Keywords</span></span>

#### <a name="keywordisraelnationalid"></a><span data-ttu-id="484f6-2570">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="484f6-2570">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="484f6-2571">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="484f6-2571">מספר זהות</span></span> 
- <span data-ttu-id="484f6-2572">National ID Number</span><span class="sxs-lookup"><span data-stu-id="484f6-2572">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="484f6-2573">意大利驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="484f6-2573">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-2574">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-2574">Format</span></span>

<span data-ttu-id="484f6-2575">10 个字母和数字的组合</span><span class="sxs-lookup"><span data-stu-id="484f6-2575">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-2576">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2576">Pattern</span></span>

- <span data-ttu-id="484f6-2577">10 个字母和数字的组合：</span><span class="sxs-lookup"><span data-stu-id="484f6-2577">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="484f6-2578">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="484f6-2578">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="484f6-2579">字母“A”或者“V”（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="484f6-2579">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="484f6-2580">七个字母（不区分大小写）、数字或下划线字符</span><span class="sxs-lookup"><span data-stu-id="484f6-2580">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="484f6-2581">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="484f6-2581">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-2582">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-2582">Checksum</span></span>

<span data-ttu-id="484f6-2583">否</span><span class="sxs-lookup"><span data-stu-id="484f6-2583">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-2584">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-2584">Definition</span></span>

<span data-ttu-id="484f6-2585">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2585">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2586">正则表达式 Regex_italy_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2586">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2587">找到 Keyword_italy_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2587">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-2588">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2588">Keywords</span></span>

#### <a name="keyworditalydriverslicensenumber"></a><span data-ttu-id="484f6-2589">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="484f6-2589">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="484f6-2590">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="484f6-2590">numero di patente di guida</span></span> 
- <span data-ttu-id="484f6-2591">patente di guida</span><span class="sxs-lookup"><span data-stu-id="484f6-2591">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="484f6-2592">日本银行帐号</span><span class="sxs-lookup"><span data-stu-id="484f6-2592">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-2593">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-2593">Format</span></span>

<span data-ttu-id="484f6-2594">七个或八个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2594">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-2595">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2595">Pattern</span></span>

<span data-ttu-id="484f6-2596">银行帐号：</span><span class="sxs-lookup"><span data-stu-id="484f6-2596">Bank account number:</span></span>
- <span data-ttu-id="484f6-2597">七个或八个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2597">Seven or eight digits</span></span>
- <span data-ttu-id="484f6-2598">银行帐户分支代码：</span><span class="sxs-lookup"><span data-stu-id="484f6-2598">Bank account branch code:</span></span>
- <span data-ttu-id="484f6-2599">四位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2599">Four digits</span></span> 
- <span data-ttu-id="484f6-2600">空格或破折号（可选）</span><span class="sxs-lookup"><span data-stu-id="484f6-2600">A space or dash (optional)</span></span> 
- <span data-ttu-id="484f6-2601">三位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2601">Three digits</span></span>

<span data-ttu-id="484f6-2602">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-2602">Checksum</span></span>

<span data-ttu-id="484f6-2603">否</span><span class="sxs-lookup"><span data-stu-id="484f6-2603">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-2604">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-2604">Definition</span></span>

<span data-ttu-id="484f6-2605">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2605">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2606">函数 Func_jp_bank_account 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2606">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2607">找到 Keyword_jp_bank_account 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2607">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="484f6-2608">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="484f6-2608">One of the following is true:</span></span>
- <span data-ttu-id="484f6-2609">函数 Func_jp_bank_account_branch_code 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2609">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2610">找到 Keyword_jp_bank_branch_code 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2610">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="484f6-2611">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2611">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2612">函数 Func_jp_bank_account 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2612">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2613">找到 Keyword_jp_bank_account 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2613">A keyword from Keyword_jp_bank_account is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-2614">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2614">Keywords</span></span>

#### <a name="keywordjpbankaccount"></a><span data-ttu-id="484f6-2615">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="484f6-2615">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="484f6-2616">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="484f6-2616">Checking Account Number</span></span> 
- <span data-ttu-id="484f6-2617">Checking Account</span><span class="sxs-lookup"><span data-stu-id="484f6-2617">Checking Account</span></span> 
- <span data-ttu-id="484f6-2618">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="484f6-2618">Checking Account #</span></span> 
- <span data-ttu-id="484f6-2619">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="484f6-2619">Checking Acct Number</span></span> 
- <span data-ttu-id="484f6-2620">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="484f6-2620">Checking Acct #</span></span> 
- <span data-ttu-id="484f6-2621">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="484f6-2621">Checking Acct No.</span></span> 
- <span data-ttu-id="484f6-2622">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="484f6-2622">Checking Account No.</span></span> 
- <span data-ttu-id="484f6-2623">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="484f6-2623">Bank Account Number</span></span> 
- <span data-ttu-id="484f6-2624">Bank Account</span><span class="sxs-lookup"><span data-stu-id="484f6-2624">Bank Account</span></span> 
- <span data-ttu-id="484f6-2625">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="484f6-2625">Bank Account #</span></span> 
- <span data-ttu-id="484f6-2626">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="484f6-2626">Bank Acct Number</span></span> 
- <span data-ttu-id="484f6-2627">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="484f6-2627">Bank Acct #</span></span> 
- <span data-ttu-id="484f6-2628">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="484f6-2628">Bank Acct No.</span></span> 
- <span data-ttu-id="484f6-2629">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="484f6-2629">Bank Account No.</span></span> 
- <span data-ttu-id="484f6-2630">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="484f6-2630">Savings Account Number</span></span> 
- <span data-ttu-id="484f6-2631">Savings Account</span><span class="sxs-lookup"><span data-stu-id="484f6-2631">Savings Account</span></span> 
- <span data-ttu-id="484f6-2632">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="484f6-2632">Savings Account #</span></span> 
- <span data-ttu-id="484f6-2633">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="484f6-2633">Savings Acct Number</span></span> 
- <span data-ttu-id="484f6-2634">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="484f6-2634">Savings Acct #</span></span> 
- <span data-ttu-id="484f6-2635">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="484f6-2635">Savings Acct No.</span></span> 
- <span data-ttu-id="484f6-2636">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="484f6-2636">Savings Account No.</span></span> 
- <span data-ttu-id="484f6-2637">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="484f6-2637">Debit Account Number</span></span> 
- <span data-ttu-id="484f6-2638">Debit Account</span><span class="sxs-lookup"><span data-stu-id="484f6-2638">Debit Account</span></span> 
- <span data-ttu-id="484f6-2639">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="484f6-2639">Debit Account #</span></span> 
- <span data-ttu-id="484f6-2640">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="484f6-2640">Debit Acct Number</span></span> 
- <span data-ttu-id="484f6-2641">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="484f6-2641">Debit Acct #</span></span> 
- <span data-ttu-id="484f6-2642">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="484f6-2642">Debit Acct No.</span></span> 
- <span data-ttu-id="484f6-2643">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="484f6-2643">Debit Account No.</span></span> 
- <span data-ttu-id="484f6-2644">口座番号を当座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="484f6-2644">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="484f6-2645">#アカウントの確認、勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="484f6-2645">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="484f6-2646">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="484f6-2646">＃勘定の確認</span></span> 
- <span data-ttu-id="484f6-2647">勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="484f6-2647">勘定番号の確認</span></span> 
- <span data-ttu-id="484f6-2648">口座番号の確認</span><span class="sxs-lookup"><span data-stu-id="484f6-2648">口座番号の確認</span></span> 
- <span data-ttu-id="484f6-2649">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="484f6-2649">銀行口座番号</span></span> 
- <span data-ttu-id="484f6-2650">銀行口座</span><span class="sxs-lookup"><span data-stu-id="484f6-2650">銀行口座</span></span> 
- <span data-ttu-id="484f6-2651">銀行口座＃</span><span class="sxs-lookup"><span data-stu-id="484f6-2651">銀行口座＃</span></span> 
- <span data-ttu-id="484f6-2652">銀行の勘定番号</span><span class="sxs-lookup"><span data-stu-id="484f6-2652">銀行の勘定番号</span></span> 
- <span data-ttu-id="484f6-2653">銀行のacct＃</span><span class="sxs-lookup"><span data-stu-id="484f6-2653">銀行のacct＃</span></span> 
- <span data-ttu-id="484f6-2654">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="484f6-2654">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="484f6-2655">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="484f6-2655">銀行口座番号</span></span>
- <span data-ttu-id="484f6-2656">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="484f6-2656">普通預金口座番号</span></span> 
- <span data-ttu-id="484f6-2657">預金口座</span><span class="sxs-lookup"><span data-stu-id="484f6-2657">預金口座</span></span> 
- <span data-ttu-id="484f6-2658">貯蓄口座＃</span><span class="sxs-lookup"><span data-stu-id="484f6-2658">貯蓄口座＃</span></span> 
- <span data-ttu-id="484f6-2659">貯蓄勘定の数</span><span class="sxs-lookup"><span data-stu-id="484f6-2659">貯蓄勘定の数</span></span> 
- <span data-ttu-id="484f6-2660">貯蓄勘定＃</span><span class="sxs-lookup"><span data-stu-id="484f6-2660">貯蓄勘定＃</span></span> 
- <span data-ttu-id="484f6-2661">貯蓄勘定番号</span><span class="sxs-lookup"><span data-stu-id="484f6-2661">貯蓄勘定番号</span></span> 
- <span data-ttu-id="484f6-2662">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="484f6-2662">普通預金口座番号</span></span> 
- <span data-ttu-id="484f6-2663">引き落とし口座番号</span><span class="sxs-lookup"><span data-stu-id="484f6-2663">引き落とし口座番号</span></span> 
- <span data-ttu-id="484f6-2664">口座番号</span><span class="sxs-lookup"><span data-stu-id="484f6-2664">口座番号</span></span> 
- <span data-ttu-id="484f6-2665">口座番号＃</span><span class="sxs-lookup"><span data-stu-id="484f6-2665">口座番号＃</span></span> 
- <span data-ttu-id="484f6-2666">デビットのacct番号</span><span class="sxs-lookup"><span data-stu-id="484f6-2666">デビットのacct番号</span></span> 
- <span data-ttu-id="484f6-2667">デビット勘定＃</span><span class="sxs-lookup"><span data-stu-id="484f6-2667">デビット勘定＃</span></span> 
- <span data-ttu-id="484f6-2668">デビットACCTの番号</span><span class="sxs-lookup"><span data-stu-id="484f6-2668">デビットACCTの番号</span></span> 
- <span data-ttu-id="484f6-2669">デビット口座番号</span><span class="sxs-lookup"><span data-stu-id="484f6-2669">デビット口座番号</span></span> 

#### <a name="keywordjpbankbranchcode"></a><span data-ttu-id="484f6-2670">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="484f6-2670">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="484f6-2671">Otemachi</span><span class="sxs-lookup"><span data-stu-id="484f6-2671">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="484f6-2672">日本驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="484f6-2672">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-2673">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-2673">Format</span></span>

<span data-ttu-id="484f6-2674">12 个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2674">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-2675">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2675">Pattern</span></span>

<span data-ttu-id="484f6-2676">12 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2676">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-2677">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-2677">Checksum</span></span>

<span data-ttu-id="484f6-2678">否</span><span class="sxs-lookup"><span data-stu-id="484f6-2678">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-2679">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-2679">Definition</span></span>

<span data-ttu-id="484f6-2680">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2680">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2681">函数 Func_jp_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2681">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2682">找到 Keyword_jp_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2682">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="484f6-2683">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2683">Keywords</span></span>

#### <a name="keywordjpdriverslicensenumber"></a><span data-ttu-id="484f6-2684">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="484f6-2684">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="484f6-2685">通讯</span><span class="sxs-lookup"><span data-stu-id="484f6-2685">dl#</span></span> 
- <span data-ttu-id="484f6-2686">通讯</span><span class="sxs-lookup"><span data-stu-id="484f6-2686">DL＃</span></span> 
- <span data-ttu-id="484f6-2687">dls</span><span class="sxs-lookup"><span data-stu-id="484f6-2687">dls#</span></span> 
- <span data-ttu-id="484f6-2688">DLS</span><span class="sxs-lookup"><span data-stu-id="484f6-2688">DLS＃</span></span> 
- <span data-ttu-id="484f6-2689">driver license</span><span class="sxs-lookup"><span data-stu-id="484f6-2689">driver license</span></span> 
- <span data-ttu-id="484f6-2690">driver licenses</span><span class="sxs-lookup"><span data-stu-id="484f6-2690">driver licenses</span></span> 
- <span data-ttu-id="484f6-2691">drivers license</span><span class="sxs-lookup"><span data-stu-id="484f6-2691">drivers license</span></span> 
- <span data-ttu-id="484f6-2692">driver's license</span><span class="sxs-lookup"><span data-stu-id="484f6-2692">driver's license</span></span> 
- <span data-ttu-id="484f6-2693">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="484f6-2693">drivers licenses</span></span> 
- <span data-ttu-id="484f6-2694">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="484f6-2694">driver's licenses</span></span> 
- <span data-ttu-id="484f6-2695">driving licence</span><span class="sxs-lookup"><span data-stu-id="484f6-2695">driving licence</span></span> 
- <span data-ttu-id="484f6-2696">.lic</span><span class="sxs-lookup"><span data-stu-id="484f6-2696">lic#</span></span> 
- <span data-ttu-id="484f6-2697">.LIC</span><span class="sxs-lookup"><span data-stu-id="484f6-2697">LIC＃</span></span> 
- <span data-ttu-id="484f6-2698">driver'lics</span><span class="sxs-lookup"><span data-stu-id="484f6-2698">lics#</span></span> 
- <span data-ttu-id="484f6-2699">state id</span><span class="sxs-lookup"><span data-stu-id="484f6-2699">state id</span></span> 
- <span data-ttu-id="484f6-2700">state identification</span><span class="sxs-lookup"><span data-stu-id="484f6-2700">state identification</span></span> 
- <span data-ttu-id="484f6-2701">state identification number</span><span class="sxs-lookup"><span data-stu-id="484f6-2701">state identification number</span></span> 
- <span data-ttu-id="484f6-2702">低所得国＃</span><span class="sxs-lookup"><span data-stu-id="484f6-2702">低所得国＃</span></span> 
- <span data-ttu-id="484f6-2703">免許証</span><span class="sxs-lookup"><span data-stu-id="484f6-2703">免許証</span></span> 
- <span data-ttu-id="484f6-2704">状態ID</span><span class="sxs-lookup"><span data-stu-id="484f6-2704">状態ID</span></span>
- <span data-ttu-id="484f6-2705">状態の識別</span><span class="sxs-lookup"><span data-stu-id="484f6-2705">状態の識別</span></span> 
- <span data-ttu-id="484f6-2706">状態の識別番号</span><span class="sxs-lookup"><span data-stu-id="484f6-2706">状態の識別番号</span></span> 
- <span data-ttu-id="484f6-2707">運転免許</span><span class="sxs-lookup"><span data-stu-id="484f6-2707">運転免許</span></span> 
- <span data-ttu-id="484f6-2708">運転免許証</span><span class="sxs-lookup"><span data-stu-id="484f6-2708">運転免許証</span></span> 
- <span data-ttu-id="484f6-2709">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="484f6-2709">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="484f6-2710">日本护照号码</span><span class="sxs-lookup"><span data-stu-id="484f6-2710">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-2711">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-2711">Format</span></span>

<span data-ttu-id="484f6-2712">两个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2712">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-2713">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2713">Pattern</span></span>

<span data-ttu-id="484f6-2714">两个字母（不区分大小写）后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2714">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-2715">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-2715">Checksum</span></span>

<span data-ttu-id="484f6-2716">否</span><span class="sxs-lookup"><span data-stu-id="484f6-2716">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-2717">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-2717">Definition</span></span>

<span data-ttu-id="484f6-2718">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2718">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2719">函数 Func_jp_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2719">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2720">找到 Keyword_jp_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2720">A keyword from Keyword_jp_passport is found.</span></span>

```
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="484f6-2721">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2721">Keywords</span></span>

#### <a name="keywordjppassport"></a><span data-ttu-id="484f6-2722">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="484f6-2722">Keyword_jp_passport</span></span>

- <span data-ttu-id="484f6-2723">パスポート</span><span class="sxs-lookup"><span data-stu-id="484f6-2723">パスポート</span></span> 
- <span data-ttu-id="484f6-2724">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="484f6-2724">パスポート番号</span></span> 
- <span data-ttu-id="484f6-2725">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="484f6-2725">パスポートのNum</span></span> 
- <span data-ttu-id="484f6-2726">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="484f6-2726">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="484f6-2727">日本居民登记号码</span><span class="sxs-lookup"><span data-stu-id="484f6-2727">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-2728">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-2728">Format</span></span>

<span data-ttu-id="484f6-2729">11 个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2729">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-2730">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2730">Pattern</span></span>

<span data-ttu-id="484f6-2731">11 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2731">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-2732">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-2732">Checksum</span></span>

<span data-ttu-id="484f6-2733">否</span><span class="sxs-lookup"><span data-stu-id="484f6-2733">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-2734">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-2734">Definition</span></span>

<span data-ttu-id="484f6-2735">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2736">函数 Func_jp_resident_registration_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2736">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2737">找到 Keyword_jp_resident_registration_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2737">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="484f6-2738">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2738">Keywords</span></span>

#### <a name="keywordjpresidentregistrationnumber"></a><span data-ttu-id="484f6-2739">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="484f6-2739">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="484f6-2740">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="484f6-2740">Resident Registration Number</span></span>
- <span data-ttu-id="484f6-2741">Resident Register Number</span><span class="sxs-lookup"><span data-stu-id="484f6-2741">Resident Register Number</span></span> 
- <span data-ttu-id="484f6-2742">Residents Basic Registry Number</span><span class="sxs-lookup"><span data-stu-id="484f6-2742">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="484f6-2743">Resident Registration No.</span><span class="sxs-lookup"><span data-stu-id="484f6-2743">Resident Registration No.</span></span> 
- <span data-ttu-id="484f6-2744">Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="484f6-2744">Resident Register No.</span></span> 
- <span data-ttu-id="484f6-2745">Residents Basic Registry No.</span><span class="sxs-lookup"><span data-stu-id="484f6-2745">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="484f6-2746">Basic Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="484f6-2746">Basic Resident Register No.</span></span> 
- <span data-ttu-id="484f6-2747">住民登録番号、登録番号をレジデント</span><span class="sxs-lookup"><span data-stu-id="484f6-2747">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="484f6-2748">住民基本登録番号、登録番号</span><span class="sxs-lookup"><span data-stu-id="484f6-2748">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="484f6-2749">住民基本レジストリ番号を常駐</span><span class="sxs-lookup"><span data-stu-id="484f6-2749">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="484f6-2750">登録番号を常駐住民基本台帳登録番号</span><span class="sxs-lookup"><span data-stu-id="484f6-2750">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="484f6-2751">日本社会保险号码 (SIN)</span><span class="sxs-lookup"><span data-stu-id="484f6-2751">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="484f6-2752">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-2752">Format</span></span>

<span data-ttu-id="484f6-2753">7-12 个数字 </span><span class="sxs-lookup"><span data-stu-id="484f6-2753">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-2754">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2754">Pattern</span></span>

<span data-ttu-id="484f6-2755">7-12 位数字：</span><span class="sxs-lookup"><span data-stu-id="484f6-2755">7-12 digits:</span></span>
- <span data-ttu-id="484f6-2756">四位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2756">Four digits</span></span> 
- <span data-ttu-id="484f6-2757">一个连字符（可选）</span><span class="sxs-lookup"><span data-stu-id="484f6-2757">A hyphen (optional)</span></span> 
- <span data-ttu-id="484f6-2758">六位数字或</span><span class="sxs-lookup"><span data-stu-id="484f6-2758">Six digits OR</span></span>
- <span data-ttu-id="484f6-2759">7-12 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2759">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-2760">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-2760">Checksum</span></span>

<span data-ttu-id="484f6-2761">否</span><span class="sxs-lookup"><span data-stu-id="484f6-2761">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-2762">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-2762">Definition</span></span>

<span data-ttu-id="484f6-2763">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2763">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2764">函数 Func_jp_sin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2764">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2765">找到 Keyword_jp_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2765">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="484f6-2766">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2766">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2767">函数 Func_jp_sin_pre_1997 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2767">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2768">找到 Keyword_jp_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2768">A keyword from Keyword_jp_sin is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-2769">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2769">Keywords</span></span>

#### <a name="keywordjpsin"></a><span data-ttu-id="484f6-2770">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="484f6-2770">Keyword_jp_sin</span></span>

- <span data-ttu-id="484f6-2771">Social Insurance No.</span><span class="sxs-lookup"><span data-stu-id="484f6-2771">Social Insurance No.</span></span> 
- <span data-ttu-id="484f6-2772">Social Insurance Num</span><span class="sxs-lookup"><span data-stu-id="484f6-2772">Social Insurance Num</span></span> 
- <span data-ttu-id="484f6-2773">Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="484f6-2773">Social Insurance Number</span></span> 
- <span data-ttu-id="484f6-2774">社会保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="484f6-2774">社会保険のテンキー</span></span> 
- <span data-ttu-id="484f6-2775">社会保険番号</span><span class="sxs-lookup"><span data-stu-id="484f6-2775">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="484f6-2776">日本住宅电话卡号</span><span class="sxs-lookup"><span data-stu-id="484f6-2776">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-2777">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-2777">Format</span></span>

<span data-ttu-id="484f6-2778">12个字母和数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2778">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-2779">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2779">Pattern</span></span>

<span data-ttu-id="484f6-2780">12个字母和数字:</span><span class="sxs-lookup"><span data-stu-id="484f6-2780">12 letters and digits:</span></span>
- <span data-ttu-id="484f6-2781">两个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="484f6-2781">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="484f6-2782">八个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2782">Eight digits</span></span> 
- <span data-ttu-id="484f6-2783">两个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="484f6-2783">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-2784">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-2784">Checksum</span></span>

<span data-ttu-id="484f6-2785">否</span><span class="sxs-lookup"><span data-stu-id="484f6-2785">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-2786">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-2786">Definition</span></span>

<span data-ttu-id="484f6-2787">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2787">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2788">正则表达式 Regex_jp_residence_card_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2788">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2789">找到 Keyword_jp_residence_card_number 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2789">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="484f6-2790">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2790">Keywords</span></span>

#### <a name="keywordjpresidencecardnumber"></a><span data-ttu-id="484f6-2791">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="484f6-2791">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="484f6-2792">住宅电话卡号</span><span class="sxs-lookup"><span data-stu-id="484f6-2792">Residence card number</span></span>
- <span data-ttu-id="484f6-2793">住宅卡编号</span><span class="sxs-lookup"><span data-stu-id="484f6-2793">Residence card no</span></span>
- <span data-ttu-id="484f6-2794">住宅卡片 #</span><span class="sxs-lookup"><span data-stu-id="484f6-2794">Residence card #</span></span>
- <span data-ttu-id="484f6-2795">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="484f6-2795">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="484f6-2796">马拉西亚身份证号码</span><span class="sxs-lookup"><span data-stu-id="484f6-2796">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-2797">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-2797">Format</span></span>

<span data-ttu-id="484f6-2798">12 个数字（包含可选连字符）</span><span class="sxs-lookup"><span data-stu-id="484f6-2798">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-2799">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2799">Pattern</span></span>

<span data-ttu-id="484f6-2800">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="484f6-2800">12 digits:</span></span>
- <span data-ttu-id="484f6-2801">六个数字，采用  YYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="484f6-2801">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="484f6-2802">一个短划线（可选） </span><span class="sxs-lookup"><span data-stu-id="484f6-2802">A dash (optional)</span></span> 
- <span data-ttu-id="484f6-2803">两个字母的出生地代码 </span><span class="sxs-lookup"><span data-stu-id="484f6-2803">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="484f6-2804">一个短划线（可选） </span><span class="sxs-lookup"><span data-stu-id="484f6-2804">A dash (optional)</span></span> 
- <span data-ttu-id="484f6-2805">三个随机数字 </span><span class="sxs-lookup"><span data-stu-id="484f6-2805">Three random digits</span></span> 
- <span data-ttu-id="484f6-2806">一位性别代码</span><span class="sxs-lookup"><span data-stu-id="484f6-2806">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-2807">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-2807">Checksum</span></span>

<span data-ttu-id="484f6-2808">否</span><span class="sxs-lookup"><span data-stu-id="484f6-2808">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-2809">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-2809">Definition</span></span>

<span data-ttu-id="484f6-2810">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2810">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2811">正则表达式 Regex_malaysia_id_card_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2811">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2812">找到 Keyword_malaysia_id_card_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2812">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-2813">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2813">Keywords</span></span>
   
#### <a name="keywordmalaysiaidcardnumber"></a><span data-ttu-id="484f6-2814">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="484f6-2814">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="484f6-2815">数字应用程序卡</span><span class="sxs-lookup"><span data-stu-id="484f6-2815">digital application card</span></span>
- <span data-ttu-id="484f6-2816">i/c</span><span class="sxs-lookup"><span data-stu-id="484f6-2816">i/c</span></span>
- <span data-ttu-id="484f6-2817">i/c 否</span><span class="sxs-lookup"><span data-stu-id="484f6-2817">i/c no</span></span>
- <span data-ttu-id="484f6-2818">ic</span><span class="sxs-lookup"><span data-stu-id="484f6-2818">ic</span></span>
- <span data-ttu-id="484f6-2819">内部公司编号</span><span class="sxs-lookup"><span data-stu-id="484f6-2819">ic no</span></span>
- <span data-ttu-id="484f6-2820">id card</span><span class="sxs-lookup"><span data-stu-id="484f6-2820">id card</span></span>
- <span data-ttu-id="484f6-2821">标识卡</span><span class="sxs-lookup"><span data-stu-id="484f6-2821">identification Card</span></span>
- <span data-ttu-id="484f6-2822">identity card</span><span class="sxs-lookup"><span data-stu-id="484f6-2822">identity card</span></span>
- <span data-ttu-id="484f6-2823">k/p</span><span class="sxs-lookup"><span data-stu-id="484f6-2823">k/p</span></span>
- <span data-ttu-id="484f6-2824">k/p no</span><span class="sxs-lookup"><span data-stu-id="484f6-2824">k/p no</span></span>
- <span data-ttu-id="484f6-2825">kad akuan diri</span><span class="sxs-lookup"><span data-stu-id="484f6-2825">kad akuan diri</span></span>
- <span data-ttu-id="484f6-2826">kad aplikasi 数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2826">kad aplikasi digital</span></span>
- <span data-ttu-id="484f6-2827">kad pengenalan 马来西亚</span><span class="sxs-lookup"><span data-stu-id="484f6-2827">kad pengenalan malaysia</span></span>
- <span data-ttu-id="484f6-2828">kp</span><span class="sxs-lookup"><span data-stu-id="484f6-2828">kp</span></span>
- <span data-ttu-id="484f6-2829">kp no</span><span class="sxs-lookup"><span data-stu-id="484f6-2829">kp no</span></span>
- <span data-ttu-id="484f6-2830">mykad</span><span class="sxs-lookup"><span data-stu-id="484f6-2830">mykad</span></span>
- <span data-ttu-id="484f6-2831">mykas</span><span class="sxs-lookup"><span data-stu-id="484f6-2831">mykas</span></span>
- <span data-ttu-id="484f6-2832">mykid</span><span class="sxs-lookup"><span data-stu-id="484f6-2832">mykid</span></span>
- <span data-ttu-id="484f6-2833">mypr</span><span class="sxs-lookup"><span data-stu-id="484f6-2833">mypr</span></span>
- <span data-ttu-id="484f6-2834">mytentera</span><span class="sxs-lookup"><span data-stu-id="484f6-2834">mytentera</span></span>
- <span data-ttu-id="484f6-2835">马来西亚身份卡片</span><span class="sxs-lookup"><span data-stu-id="484f6-2835">malaysia identity card</span></span>
- <span data-ttu-id="484f6-2836">马来西亚身份卡片</span><span class="sxs-lookup"><span data-stu-id="484f6-2836">malaysian identity card</span></span>
- <span data-ttu-id="484f6-2837">nric</span><span class="sxs-lookup"><span data-stu-id="484f6-2837">nric</span></span>
- <span data-ttu-id="484f6-2838">个人标识卡</span><span class="sxs-lookup"><span data-stu-id="484f6-2838">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="484f6-2839">荷兰公民服务 (BSN) 号码</span><span class="sxs-lookup"><span data-stu-id="484f6-2839">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-2840">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-2840">Format</span></span>

<span data-ttu-id="484f6-2841">8-9 个数字（包含可选空格）</span><span class="sxs-lookup"><span data-stu-id="484f6-2841">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-2842">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2842">Pattern</span></span>

<span data-ttu-id="484f6-2843">8-9 个数字：</span><span class="sxs-lookup"><span data-stu-id="484f6-2843">8-9 digits:</span></span>
- <span data-ttu-id="484f6-2844">三个数字 </span><span class="sxs-lookup"><span data-stu-id="484f6-2844">Three digits</span></span> 
- <span data-ttu-id="484f6-2845">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="484f6-2845">A space (optional)</span></span> 
- <span data-ttu-id="484f6-2846">三个数字 </span><span class="sxs-lookup"><span data-stu-id="484f6-2846">Three digits</span></span> 
- <span data-ttu-id="484f6-2847">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="484f6-2847">A space (optional)</span></span> 
- <span data-ttu-id="484f6-2848">2-3 个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2848">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-2849">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-2849">Checksum</span></span>

<span data-ttu-id="484f6-2850">是</span><span class="sxs-lookup"><span data-stu-id="484f6-2850">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-2851">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-2851">Definition</span></span>

<span data-ttu-id="484f6-2852">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2852">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2853">函数 Func_netherlands_bsn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2853">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2854">找到 Keyword_netherlands_bsn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2854">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="484f6-2855">函数 Func_eu_date2 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="484f6-2855">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="484f6-2856">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-2856">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-2857">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2857">Keywords</span></span>

#### <a name="keywordnetherlandsbsn"></a><span data-ttu-id="484f6-2858">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="484f6-2858">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="484f6-2859">Citizen service number</span><span class="sxs-lookup"><span data-stu-id="484f6-2859">Citizen service number</span></span> 
- <span data-ttu-id="484f6-2860">BSN</span><span class="sxs-lookup"><span data-stu-id="484f6-2860">BSN</span></span> 
- <span data-ttu-id="484f6-2861">Burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="484f6-2861">Burgerservicenummer</span></span> 
- <span data-ttu-id="484f6-2862">Sofinummer</span><span class="sxs-lookup"><span data-stu-id="484f6-2862">Sofinummer</span></span> 
- <span data-ttu-id="484f6-2863">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="484f6-2863">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="484f6-2864">Persoonsnummer</span><span class="sxs-lookup"><span data-stu-id="484f6-2864">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="484f6-2865">新西兰卫生部号码</span><span class="sxs-lookup"><span data-stu-id="484f6-2865">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-2866">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-2866">Format</span></span>

<span data-ttu-id="484f6-2867">三个字母、一个空格（可选）以及四个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2867">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-2868">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2868">Pattern</span></span>

<span data-ttu-id="484f6-2869">三个字母 (不区分大小写) 一个空格 (可选) 四个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2869">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-2870">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-2870">Checksum</span></span>

<span data-ttu-id="484f6-2871">是</span><span class="sxs-lookup"><span data-stu-id="484f6-2871">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-2872">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-2872">Definition</span></span>

<span data-ttu-id="484f6-2873">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2873">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2874">函数 Func_new_zealand_ministry_of_health_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2874">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2875">找到 Keyword_nz_terms 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2875">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="484f6-2876">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-2876">The checksum passes.</span></span>

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

<span data-ttu-id="484f6-2877">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2877">Keywords</span></span>

<span data-ttu-id="484f6-2878">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="484f6-2878">Keyword_nz_terms</span></span>

- <span data-ttu-id="484f6-2879">NHI</span><span class="sxs-lookup"><span data-stu-id="484f6-2879">NHI</span></span> 
- <span data-ttu-id="484f6-2880">New Zealand</span><span class="sxs-lookup"><span data-stu-id="484f6-2880">New Zealand</span></span> 
- <span data-ttu-id="484f6-2881">运行状况</span><span class="sxs-lookup"><span data-stu-id="484f6-2881">Health</span></span> 
- <span data-ttu-id="484f6-2882">治疗</span><span class="sxs-lookup"><span data-stu-id="484f6-2882">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="484f6-2883">挪威身份证号</span><span class="sxs-lookup"><span data-stu-id="484f6-2883">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-2884">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-2884">Format</span></span>

<span data-ttu-id="484f6-2885">11 个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2885">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-2886">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2886">Pattern</span></span>

<span data-ttu-id="484f6-2887">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="484f6-2887">11 digits:</span></span>
- <span data-ttu-id="484f6-2888">六个数字，采用  DDMMYY 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="484f6-2888">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="484f6-2889">三位个人号码 </span><span class="sxs-lookup"><span data-stu-id="484f6-2889">Three-digit individual number</span></span> 
- <span data-ttu-id="484f6-2890">两个校验位</span><span class="sxs-lookup"><span data-stu-id="484f6-2890">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-2891">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-2891">Checksum</span></span>

<span data-ttu-id="484f6-2892">是</span><span class="sxs-lookup"><span data-stu-id="484f6-2892">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-2893">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-2893">Definition</span></span>

<span data-ttu-id="484f6-2894">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2894">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2895">函数 Func_norway_id_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2895">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2896">找到 Keyword_norway_id_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2896">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="484f6-2897">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-2897">The checksum passes.</span></span>
- <span data-ttu-id="484f6-2898">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2898">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2899">函数 Func_norway_id_numbe 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2899">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2900">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-2900">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-2901">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2901">Keywords</span></span>

#### <a name="keywordnorwayidnumber"></a><span data-ttu-id="484f6-2902">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="484f6-2902">Keyword_norway_id_number</span></span>

- <span data-ttu-id="484f6-2903">Personal identification number</span><span class="sxs-lookup"><span data-stu-id="484f6-2903">Personal identification number</span></span>
- <span data-ttu-id="484f6-2904">Norwegian ID Number</span><span class="sxs-lookup"><span data-stu-id="484f6-2904">Norwegian ID Number</span></span>
- <span data-ttu-id="484f6-2905">ID Number</span><span class="sxs-lookup"><span data-stu-id="484f6-2905">ID Number</span></span>
- <span data-ttu-id="484f6-2906">Id</span><span class="sxs-lookup"><span data-stu-id="484f6-2906">Identification</span></span>
- <span data-ttu-id="484f6-2907">Personnummer</span><span class="sxs-lookup"><span data-stu-id="484f6-2907">Personnummer</span></span>
- <span data-ttu-id="484f6-2908">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="484f6-2908">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="484f6-2909">菲律宾统一多用途身份证号码</span><span class="sxs-lookup"><span data-stu-id="484f6-2909">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-2910">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-2910">Format</span></span>

<span data-ttu-id="484f6-2911">12 个数字，通过连字符分隔 </span><span class="sxs-lookup"><span data-stu-id="484f6-2911">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-2912">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2912">Pattern</span></span>

<span data-ttu-id="484f6-2913">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="484f6-2913">12 digits:</span></span>
- <span data-ttu-id="484f6-2914">四个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2914">Four digits</span></span> 
- <span data-ttu-id="484f6-2915">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="484f6-2915">A hyphen</span></span> 
- <span data-ttu-id="484f6-2916">七个数字 </span><span class="sxs-lookup"><span data-stu-id="484f6-2916">Seven digits</span></span> 
- <span data-ttu-id="484f6-2917">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="484f6-2917">A hyphen</span></span> 
- <span data-ttu-id="484f6-2918">一个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2918">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-2919">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-2919">Checksum</span></span>

<span data-ttu-id="484f6-2920">否</span><span class="sxs-lookup"><span data-stu-id="484f6-2920">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-2921">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-2921">Definition</span></span>

<span data-ttu-id="484f6-2922">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2922">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2923">正则表达式 Regex_philippines_unified_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2923">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2924">找到 Keyword_philippines_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2924">A keyword from Keyword_philippines_id is found.</span></span>

```
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="484f6-2925">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2925">Keywords</span></span>
   
#### <a name="keywordphilippinesid"></a><span data-ttu-id="484f6-2926">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="484f6-2926">Keyword_philippines_id</span></span>

- <span data-ttu-id="484f6-2927">Unified Multi-Purpose ID</span><span class="sxs-lookup"><span data-stu-id="484f6-2927">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="484f6-2928">UMID</span><span class="sxs-lookup"><span data-stu-id="484f6-2928">UMID</span></span> 
- <span data-ttu-id="484f6-2929">Identity Card</span><span class="sxs-lookup"><span data-stu-id="484f6-2929">Identity Card</span></span> 
- <span data-ttu-id="484f6-2930">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="484f6-2930">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="484f6-2931">波兰身份证</span><span class="sxs-lookup"><span data-stu-id="484f6-2931">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="484f6-2932">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-2932">Format</span></span>

<span data-ttu-id="484f6-2933">三个字母和六个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2933">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-2934">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2934">Pattern</span></span>

<span data-ttu-id="484f6-2935">三个字母（不区分大小写）后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2935">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-2936">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-2936">Checksum</span></span>

<span data-ttu-id="484f6-2937">是</span><span class="sxs-lookup"><span data-stu-id="484f6-2937">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-2938">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-2938">Definition</span></span>

<span data-ttu-id="484f6-2939">DLP 策略 75% 确信在300个字符的邻近度内检测到此类型的敏感信息: 函数 Func_polish_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2939">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="484f6-2940">找到 Keyword_polish_national_id_passport_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2940">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="484f6-2941">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-2941">The checksum passes.</span></span>

```
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="484f6-2942">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2942">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="484f6-2943">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="484f6-2943">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="484f6-2944">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="484f6-2944">Dowód osobisty</span></span>
- <span data-ttu-id="484f6-2945">器 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="484f6-2945">Numer dowodu osobistego</span></span>
- <span data-ttu-id="484f6-2946">Nazwa i 器 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="484f6-2946">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="484f6-2947">Nazwa i nr dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="484f6-2947">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="484f6-2948">Nazwa i nr dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="484f6-2948">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="484f6-2949">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="484f6-2949">Dowód Tożsamości</span></span>
- <span data-ttu-id="484f6-2950">dow.</span><span class="sxs-lookup"><span data-stu-id="484f6-2950">dow.</span></span> <span data-ttu-id="484f6-2951">os.</span><span class="sxs-lookup"><span data-stu-id="484f6-2951">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="484f6-2952">波兰国家/地区 ID (PESEL)</span><span class="sxs-lookup"><span data-stu-id="484f6-2952">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="484f6-2953">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-2953">Format</span></span>

<span data-ttu-id="484f6-2954">11 个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2954">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-2955">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2955">Pattern</span></span>

<span data-ttu-id="484f6-2956">11 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2956">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-2957">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-2957">Checksum</span></span>

<span data-ttu-id="484f6-2958">是</span><span class="sxs-lookup"><span data-stu-id="484f6-2958">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-2959">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-2959">Definition</span></span>

<span data-ttu-id="484f6-2960">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2960">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2961">函数 Func_pesel_identification_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2961">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2962">找到 Keyword_pesel_identification_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2962">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="484f6-2963">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-2963">The checksum passes.</span></span>

```
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="484f6-2964">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2964">Keywords</span></span>

#### <a name="keywordpeselidentificationnumber"></a><span data-ttu-id="484f6-2965">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="484f6-2965">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="484f6-2966">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="484f6-2966">Nr PESEL</span></span>
- <span data-ttu-id="484f6-2967">PESEL</span><span class="sxs-lookup"><span data-stu-id="484f6-2967">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="484f6-2968">波兰护照</span><span class="sxs-lookup"><span data-stu-id="484f6-2968">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="484f6-2969">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-2969">Format</span></span>

<span data-ttu-id="484f6-2970">两个字母和七个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2970">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-2971">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2971">Pattern</span></span>

<span data-ttu-id="484f6-2972">两个字母（不区分大小写）后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2972">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-2973">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-2973">Checksum</span></span>

<span data-ttu-id="484f6-2974">是</span><span class="sxs-lookup"><span data-stu-id="484f6-2974">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-2975">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-2975">Definition</span></span>

<span data-ttu-id="484f6-2976">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2976">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2977">函数 Func_polish_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2977">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2978">找到 Keyword_polish_national_id_passport_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2978">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="484f6-2979">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-2979">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-2980">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2980">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="484f6-2981">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="484f6-2981">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="484f6-2982">器 paszportu</span><span class="sxs-lookup"><span data-stu-id="484f6-2982">Numer paszportu</span></span>
- <span data-ttu-id="484f6-2983">Führerschein-nr.</span><span class="sxs-lookup"><span data-stu-id="484f6-2983">Nr.</span></span> <span data-ttu-id="484f6-2984">Paszportu</span><span class="sxs-lookup"><span data-stu-id="484f6-2984">Paszportu</span></span>
- <span data-ttu-id="484f6-2985">Paszport</span><span class="sxs-lookup"><span data-stu-id="484f6-2985">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="484f6-2986">葡萄牙公民身份证号</span><span class="sxs-lookup"><span data-stu-id="484f6-2986">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-2987">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-2987">Format</span></span>

<span data-ttu-id="484f6-2988">八个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2988">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-2989">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-2989">Pattern</span></span>

<span data-ttu-id="484f6-2990">八个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-2990">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-2991">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-2991">Checksum</span></span>

<span data-ttu-id="484f6-2992">否</span><span class="sxs-lookup"><span data-stu-id="484f6-2992">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-2993">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-2993">Definition</span></span>

<span data-ttu-id="484f6-2994">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-2994">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-2995">正则表达式 Regex_portugal_citizen_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-2995">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-2996">找到 Keyword_portugal_citizen_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-2996">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="484f6-2997">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-2997">Keywords</span></span>

#### <a name="keywordportugalcitizencard"></a><span data-ttu-id="484f6-2998">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="484f6-2998">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="484f6-2999">Citizen Card</span><span class="sxs-lookup"><span data-stu-id="484f6-2999">Citizen Card</span></span>
- <span data-ttu-id="484f6-3000">National ID Card</span><span class="sxs-lookup"><span data-stu-id="484f6-3000">National ID Card</span></span>
- <span data-ttu-id="484f6-3001">CC</span><span class="sxs-lookup"><span data-stu-id="484f6-3001">CC</span></span>
- <span data-ttu-id="484f6-3002">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="484f6-3002">Cartão de Cidadão</span></span>
- <span data-ttu-id="484f6-3003">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="484f6-3003">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="484f6-3004">沙特阿拉伯国家 ID</span><span class="sxs-lookup"><span data-stu-id="484f6-3004">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="484f6-3005">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-3005">Format</span></span>

<span data-ttu-id="484f6-3006">10 个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3006">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-3007">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-3007">Pattern</span></span>

<span data-ttu-id="484f6-3008">10 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3008">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-3009">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-3009">Checksum</span></span>

<span data-ttu-id="484f6-3010">否</span><span class="sxs-lookup"><span data-stu-id="484f6-3010">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-3011">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-3011">Definition</span></span>

<span data-ttu-id="484f6-3012">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-3012">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-3013">正则表达式 Regex_saudi_arabia_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3013">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-3014">找到 Keyword_saudi_arabia_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3014">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-3015">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-3015">Keywords</span></span>

#### <a name="keywordsaudiarabianationalid"></a><span data-ttu-id="484f6-3016">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="484f6-3016">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="484f6-3017">Identification Card</span><span class="sxs-lookup"><span data-stu-id="484f6-3017">Identification Card</span></span> 
- <span data-ttu-id="484f6-3018">I card number</span><span class="sxs-lookup"><span data-stu-id="484f6-3018">I card number</span></span> 
- <span data-ttu-id="484f6-3019">ID number</span><span class="sxs-lookup"><span data-stu-id="484f6-3019">ID number</span></span> 
- <span data-ttu-id="484f6-3020">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="484f6-3020">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="484f6-3021">新加坡国家登记身份证 (NRIC) 号</span><span class="sxs-lookup"><span data-stu-id="484f6-3021">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-3022">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-3022">Format</span></span>

<span data-ttu-id="484f6-3023">九个字母和数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3023">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-3024">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-3024">Pattern</span></span>

- <span data-ttu-id="484f6-3025">九个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="484f6-3025">Nine letters and digits:</span></span>
- <span data-ttu-id="484f6-3026">字母“F”、“G”、“S”或“T”（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="484f6-3026">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="484f6-3027">七个数字 </span><span class="sxs-lookup"><span data-stu-id="484f6-3027">Seven digits</span></span> 
- <span data-ttu-id="484f6-3028">一个字母校验位</span><span class="sxs-lookup"><span data-stu-id="484f6-3028">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-3029">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-3029">Checksum</span></span>

<span data-ttu-id="484f6-3030">是</span><span class="sxs-lookup"><span data-stu-id="484f6-3030">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-3031">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-3031">Definition</span></span>

<span data-ttu-id="484f6-3032">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-3032">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-3033">正则表达式 Regex_singapore_nric 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3033">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-3034">找到 Keyword_singapore_nric 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3034">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="484f6-3035">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-3035">The checksum passes.</span></span>

<span data-ttu-id="484f6-3036">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-3036">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-3037">正则表达式 Regex_singapore_nric 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3037">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-3038">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-3038">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-3039">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-3039">Keywords</span></span>
   
#### <a name="keywordsingaporenric"></a><span data-ttu-id="484f6-3040">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="484f6-3040">Keyword_singapore_nric</span></span>

- <span data-ttu-id="484f6-3041">National Registration Identity Card</span><span class="sxs-lookup"><span data-stu-id="484f6-3041">National Registration Identity Card</span></span> 
- <span data-ttu-id="484f6-3042">Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="484f6-3042">Identity Card Number</span></span> 
- <span data-ttu-id="484f6-3043">NRIC</span><span class="sxs-lookup"><span data-stu-id="484f6-3043">NRIC</span></span> 
- <span data-ttu-id="484f6-3044">IC</span><span class="sxs-lookup"><span data-stu-id="484f6-3044">IC</span></span> 
- <span data-ttu-id="484f6-3045">Foreign Identification Number</span><span class="sxs-lookup"><span data-stu-id="484f6-3045">Foreign Identification Number</span></span> 
- <span data-ttu-id="484f6-3046">FIN</span><span class="sxs-lookup"><span data-stu-id="484f6-3046">FIN</span></span> 
- <span data-ttu-id="484f6-3047">身份证</span><span class="sxs-lookup"><span data-stu-id="484f6-3047">身份证</span></span> 
- <span data-ttu-id="484f6-3048">證</span><span class="sxs-lookup"><span data-stu-id="484f6-3048">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="484f6-3049">南非身份证号</span><span class="sxs-lookup"><span data-stu-id="484f6-3049">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-3050">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-3050">Format</span></span>

<span data-ttu-id="484f6-3051">13 个数字（可能包含空格）</span><span class="sxs-lookup"><span data-stu-id="484f6-3051">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-3052">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-3052">Pattern</span></span>

<span data-ttu-id="484f6-3053">13 个数字：</span><span class="sxs-lookup"><span data-stu-id="484f6-3053">13 digits:</span></span>
- <span data-ttu-id="484f6-3054">六个数字，采用  YYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="484f6-3054">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="484f6-3055">四个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3055">Four digits</span></span> 
- <span data-ttu-id="484f6-3056">一位公民指示码 </span><span class="sxs-lookup"><span data-stu-id="484f6-3056">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="484f6-3057">数字“8”或“9” </span><span class="sxs-lookup"><span data-stu-id="484f6-3057">The digit "8" or "9"</span></span> 
- <span data-ttu-id="484f6-3058">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="484f6-3058">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-3059">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-3059">Checksum</span></span>

<span data-ttu-id="484f6-3060">是</span><span class="sxs-lookup"><span data-stu-id="484f6-3060">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-3061">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-3061">Definition</span></span>

<span data-ttu-id="484f6-3062">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-3062">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-3063">函数 Func_south_africa_identification_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3063">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-3064">找到 Keyword_south_africa_identification_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3064">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="484f6-3065">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-3065">The checksum passes.</span></span>

```
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="484f6-3066">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-3066">Keywords</span></span>
   
#### <a name="keywordsouthafricaidentificationnumber"></a><span data-ttu-id="484f6-3067">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="484f6-3067">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="484f6-3068">Identity card</span><span class="sxs-lookup"><span data-stu-id="484f6-3068">Identity card</span></span>
- <span data-ttu-id="484f6-3069">ID</span><span class="sxs-lookup"><span data-stu-id="484f6-3069">ID</span></span>
- <span data-ttu-id="484f6-3070">Id</span><span class="sxs-lookup"><span data-stu-id="484f6-3070">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="484f6-3071">韩国居民注册号码</span><span class="sxs-lookup"><span data-stu-id="484f6-3071">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-3072">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-3072">Format</span></span>

<span data-ttu-id="484f6-3073">13 个数字（包含连字符）</span><span class="sxs-lookup"><span data-stu-id="484f6-3073">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-3074">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-3074">Pattern</span></span>

<span data-ttu-id="484f6-3075">13 个数字：</span><span class="sxs-lookup"><span data-stu-id="484f6-3075">13 digits:</span></span>
- <span data-ttu-id="484f6-3076">六个数字，采用  YYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="484f6-3076">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="484f6-3077">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="484f6-3077">A hyphen</span></span> 
- <span data-ttu-id="484f6-3078">一个数字，由世纪和性别 </span><span class="sxs-lookup"><span data-stu-id="484f6-3078">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="484f6-3079">四位数字的出生地区代码 </span><span class="sxs-lookup"><span data-stu-id="484f6-3079">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="484f6-3080">一个数字，用于区分前面数字均相同的人 </span><span class="sxs-lookup"><span data-stu-id="484f6-3080">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="484f6-3081">一个校验位。</span><span class="sxs-lookup"><span data-stu-id="484f6-3081">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-3082">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-3082">Checksum</span></span>

<span data-ttu-id="484f6-3083">是</span><span class="sxs-lookup"><span data-stu-id="484f6-3083">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-3084">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-3084">Definition</span></span>

<span data-ttu-id="484f6-3085">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-3085">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-3086">函数 Func_south_korea_resident_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3086">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-3087">找到 Keyword_south_korea_resident_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3087">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="484f6-3088">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-3088">The checksum passes.</span></span>

<span data-ttu-id="484f6-3089">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-3089">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-3090">函数 Func_south_korea_resident_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3090">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-3091">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-3091">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-3092">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-3092">Keywords</span></span>
   
#### <a name="keywordsouthkorearesidentnumber"></a><span data-ttu-id="484f6-3093">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="484f6-3093">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="484f6-3094">National ID card</span><span class="sxs-lookup"><span data-stu-id="484f6-3094">National ID card</span></span> 
- <span data-ttu-id="484f6-3095">Citizen's Registration Number</span><span class="sxs-lookup"><span data-stu-id="484f6-3095">Citizen's Registration Number</span></span> 
- <span data-ttu-id="484f6-3096">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="484f6-3096">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="484f6-3097">RRN</span><span class="sxs-lookup"><span data-stu-id="484f6-3097">RRN</span></span> 
- <span data-ttu-id="484f6-3098">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="484f6-3098">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="484f6-3099">西班牙社会保险号码 (SSN)</span><span class="sxs-lookup"><span data-stu-id="484f6-3099">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="484f6-3100">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-3100">Format</span></span>

<span data-ttu-id="484f6-3101">11-12 个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3101">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-3102">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-3102">Pattern</span></span>

<span data-ttu-id="484f6-3103">11-12 位数:</span><span class="sxs-lookup"><span data-stu-id="484f6-3103">11-12 digits:</span></span>
- <span data-ttu-id="484f6-3104">两位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3104">Two digits</span></span> 
- <span data-ttu-id="484f6-3105">正斜杠（可选）</span><span class="sxs-lookup"><span data-stu-id="484f6-3105">A forward slash (optional)</span></span> 
- <span data-ttu-id="484f6-3106">7-8 位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3106">7-8 digits</span></span> 
- <span data-ttu-id="484f6-3107">正斜杠（可选）</span><span class="sxs-lookup"><span data-stu-id="484f6-3107">A forward slash (optional)</span></span> 
- <span data-ttu-id="484f6-3108">两位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3108">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-3109">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-3109">Checksum</span></span>

<span data-ttu-id="484f6-3110">是</span><span class="sxs-lookup"><span data-stu-id="484f6-3110">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-3111">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-3111">Definition</span></span>

<span data-ttu-id="484f6-3112">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-3112">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-3113">函数 Func_spanish_social_security_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3113">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-3114">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-3114">The checksum passes.</span></span>

```
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="484f6-3115">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-3115">Keywords</span></span>

<span data-ttu-id="484f6-3116">无</span><span class="sxs-lookup"><span data-stu-id="484f6-3116">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="484f6-3117">SQL Server 连接字符串</span><span class="sxs-lookup"><span data-stu-id="484f6-3117">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="484f6-3118">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-3118">Format</span></span>

<span data-ttu-id="484f6-3119">字符串 "User Id"、"User ID"、"uid" 或 "UserId", 后跟下面模式中所述的字符和字符串。</span><span class="sxs-lookup"><span data-stu-id="484f6-3119">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-3120">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-3120">Pattern</span></span>

- <span data-ttu-id="484f6-3121">字符串 "User Id"、"User ID"、"uid" 或 "UserId"</span><span class="sxs-lookup"><span data-stu-id="484f6-3121">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="484f6-3122">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="484f6-3122">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="484f6-3123">字符串 "Password" 或 "pwd", 其中 "pwd" 不以小写字母开头</span><span class="sxs-lookup"><span data-stu-id="484f6-3123">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="484f6-3124">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="484f6-3124">An equal sign (=)</span></span>
- <span data-ttu-id="484f6-3125">任何不是美元符号 ($)、百分比符号 (%)、大于号 (>)、符号 (@)、引号 (")、分号 (;)、左大括号 ([) 或左中括号 ({) 的字符</span><span class="sxs-lookup"><span data-stu-id="484f6-3125">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="484f6-3126">7-128 个字符的任意组合, 不是分号 (;)、正斜杠 (/) 或引号 (")</span><span class="sxs-lookup"><span data-stu-id="484f6-3126">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="484f6-3127">一个分号 (;)或引号 (")</span><span class="sxs-lookup"><span data-stu-id="484f6-3127">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-3128">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-3128">Checksum</span></span>

<span data-ttu-id="484f6-3129">否</span><span class="sxs-lookup"><span data-stu-id="484f6-3129">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-3130">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-3130">Definition</span></span>

<span data-ttu-id="484f6-3131">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-3131">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-3132">正则表达式 CEP_Regex_SQLServerConnectionString 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3132">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-3133">找**不**到 CEP_GlobalFilter 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3133">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="484f6-3134">正则表达式 CEP_PasswordPlaceHolder**未**找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3134">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-3135">正则表达式 CEP_CommonExampleKeywords**未**找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3135">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-3136">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-3136">Keywords</span></span>

#### <a name="cepglobalfilter"></a><span data-ttu-id="484f6-3137">CEP_GlobalFilter</span><span class="sxs-lookup"><span data-stu-id="484f6-3137">CEP_GlobalFilter</span></span>

- <span data-ttu-id="484f6-3138">部分密码</span><span class="sxs-lookup"><span data-stu-id="484f6-3138">some-password</span></span>
- <span data-ttu-id="484f6-3139">somepassword</span><span class="sxs-lookup"><span data-stu-id="484f6-3139">somepassword</span></span>
- <span data-ttu-id="484f6-3140">secretPassword</span><span class="sxs-lookup"><span data-stu-id="484f6-3140">secretPassword</span></span>
- <span data-ttu-id="484f6-3141">采用</span><span class="sxs-lookup"><span data-stu-id="484f6-3141">sample</span></span>

#### <a name="ceppasswordplaceholder"></a><span data-ttu-id="484f6-3142">CEP_PasswordPlaceHolder</span><span class="sxs-lookup"><span data-stu-id="484f6-3142">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="484f6-3143">(请注意, 从技术上讲, 此敏感信息类型通过使用正则表达式 (而不是关键字列表) 来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3143">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="484f6-3144">密码或密码后跟0-2 个空格、一个等号 (=)、0-2 个空格和一个星号 (\*)--或--</span><span class="sxs-lookup"><span data-stu-id="484f6-3144">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="484f6-3145">密码或密码后跟:</span><span class="sxs-lookup"><span data-stu-id="484f6-3145">Password or pwd followed by:</span></span>
    - <span data-ttu-id="484f6-3146">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="484f6-3146">Equal sign (=)</span></span>
    - <span data-ttu-id="484f6-3147">小于号 (<)</span><span class="sxs-lookup"><span data-stu-id="484f6-3147">Less than symbol (<)</span></span>
    - <span data-ttu-id="484f6-3148">1-200 个字符的任意组合, 这些字符为大写或小写字母、数字、星号 (\*)、连字符 (-)、下划线 (_) 或空白字符</span><span class="sxs-lookup"><span data-stu-id="484f6-3148">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="484f6-3149">大于号 (>)</span><span class="sxs-lookup"><span data-stu-id="484f6-3149">Greater than symbol (>)</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="484f6-3150">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="484f6-3150">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="484f6-3151">(请注意, 从技术上讲, 此敏感信息类型通过使用正则表达式 (而不是关键字列表) 来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3151">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="484f6-3152">尚未</span><span class="sxs-lookup"><span data-stu-id="484f6-3152">contoso</span></span>
- <span data-ttu-id="484f6-3153">送交</span><span class="sxs-lookup"><span data-stu-id="484f6-3153">fabrikam</span></span>
- <span data-ttu-id="484f6-3154">罗斯</span><span class="sxs-lookup"><span data-stu-id="484f6-3154">northwind</span></span>
- <span data-ttu-id="484f6-3155">沙盒</span><span class="sxs-lookup"><span data-stu-id="484f6-3155">sandbox</span></span>
- <span data-ttu-id="484f6-3156">onebox</span><span class="sxs-lookup"><span data-stu-id="484f6-3156">onebox</span></span>
- <span data-ttu-id="484f6-3157">localhost</span><span class="sxs-lookup"><span data-stu-id="484f6-3157">localhost</span></span>
- <span data-ttu-id="484f6-3158">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="484f6-3158">127.0.0.1</span></span>
- <span data-ttu-id="484f6-3159">testacs.</span><span class="sxs-lookup"><span data-stu-id="484f6-3159">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="484f6-3160">com</span><span class="sxs-lookup"><span data-stu-id="484f6-3160">com</span></span>
- <span data-ttu-id="484f6-3161">s-int。</span><span class="sxs-lookup"><span data-stu-id="484f6-3161">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="484f6-3162">netmeeting</span><span class="sxs-lookup"><span data-stu-id="484f6-3162">net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="484f6-3163">瑞典国家 ID</span><span class="sxs-lookup"><span data-stu-id="484f6-3163">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="484f6-3164">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-3164">Format</span></span>

<span data-ttu-id="484f6-3165">10 个或 12 个数字和一个可选分隔符</span><span class="sxs-lookup"><span data-stu-id="484f6-3165">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-3166">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-3166">Pattern</span></span>

<span data-ttu-id="484f6-3167">10 或 12 位数字和可选的分隔符：</span><span class="sxs-lookup"><span data-stu-id="484f6-3167">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="484f6-3168">2-4 位数字（可选）</span><span class="sxs-lookup"><span data-stu-id="484f6-3168">2-4 digits (optional)</span></span> 
- <span data-ttu-id="484f6-3169">采用日期格式 YYMMDD 的六位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3169">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="484f6-3170">“-”或“+”（可选）的分隔符，加</span><span class="sxs-lookup"><span data-stu-id="484f6-3170">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="484f6-3171">四个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3171">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-3172">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-3172">Checksum</span></span>

<span data-ttu-id="484f6-3173">是</span><span class="sxs-lookup"><span data-stu-id="484f6-3173">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-3174">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-3174">Definition</span></span>

<span data-ttu-id="484f6-3175">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-3175">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-3176">函数 Func_swedish_national_identifier 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3176">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-3177">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-3177">The checksum passes.</span></span>

```
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="484f6-3178">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-3178">Keywords</span></span>

<span data-ttu-id="484f6-3179">否</span><span class="sxs-lookup"><span data-stu-id="484f6-3179">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="484f6-3180">瑞典护照号码</span><span class="sxs-lookup"><span data-stu-id="484f6-3180">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-3181">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-3181">Format</span></span>

<span data-ttu-id="484f6-3182">八个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3182">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-3183">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-3183">Pattern</span></span>

<span data-ttu-id="484f6-3184">八个连续的数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3184">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-3185">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-3185">Checksum</span></span>

<span data-ttu-id="484f6-3186">否</span><span class="sxs-lookup"><span data-stu-id="484f6-3186">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-3187">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-3187">Definition</span></span>

<span data-ttu-id="484f6-3188">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-3188">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-3189">正则表达式 Regex_sweden_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3189">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-3190">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="484f6-3190">One of the following is true:</span></span>
    - <span data-ttu-id="484f6-3191">找到 Keyword_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3191">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="484f6-3192">找到 Keyword_sweden_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3192">A keyword from Keyword_sweden_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-3193">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-3193">Keywords</span></span>
   
#### <a name="keywordswedenpassport"></a><span data-ttu-id="484f6-3194">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="484f6-3194">Keyword_sweden_passport</span></span>

- <span data-ttu-id="484f6-3195">visa requirements</span><span class="sxs-lookup"><span data-stu-id="484f6-3195">visa requirements</span></span> 
- <span data-ttu-id="484f6-3196">Alien Registration Card</span><span class="sxs-lookup"><span data-stu-id="484f6-3196">Alien Registration Card</span></span> 
- <span data-ttu-id="484f6-3197">Schengen visas</span><span class="sxs-lookup"><span data-stu-id="484f6-3197">Schengen visas</span></span> 
- <span data-ttu-id="484f6-3198">Schengen visa</span><span class="sxs-lookup"><span data-stu-id="484f6-3198">Schengen visa</span></span> 
- <span data-ttu-id="484f6-3199">Visa Processing</span><span class="sxs-lookup"><span data-stu-id="484f6-3199">Visa Processing</span></span> 
- <span data-ttu-id="484f6-3200">Visa Type</span><span class="sxs-lookup"><span data-stu-id="484f6-3200">Visa Type</span></span> 
- <span data-ttu-id="484f6-3201">Single Entry</span><span class="sxs-lookup"><span data-stu-id="484f6-3201">Single Entry</span></span> 
- <span data-ttu-id="484f6-3202">Multiple Entry</span><span class="sxs-lookup"><span data-stu-id="484f6-3202">Multiple Entry</span></span> 
- <span data-ttu-id="484f6-3203">G3 Processing Fees</span><span class="sxs-lookup"><span data-stu-id="484f6-3203">G3 Processing Fees</span></span> 

#### <a name="keywordpassport"></a><span data-ttu-id="484f6-3204">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="484f6-3204">Keyword_passport</span></span>

- <span data-ttu-id="484f6-3205">Passport Number</span><span class="sxs-lookup"><span data-stu-id="484f6-3205">Passport Number</span></span> 
- <span data-ttu-id="484f6-3206">Passport No</span><span class="sxs-lookup"><span data-stu-id="484f6-3206">Passport No</span></span> 
- <span data-ttu-id="484f6-3207">Passport #</span><span class="sxs-lookup"><span data-stu-id="484f6-3207">Passport #</span></span> 
- <span data-ttu-id="484f6-3208">登记卡</span><span class="sxs-lookup"><span data-stu-id="484f6-3208">Passport#</span></span> 
- <span data-ttu-id="484f6-3209">PassportID</span><span class="sxs-lookup"><span data-stu-id="484f6-3209">PassportID</span></span> 
- <span data-ttu-id="484f6-3210">Passportno</span><span class="sxs-lookup"><span data-stu-id="484f6-3210">Passportno</span></span> 
- <span data-ttu-id="484f6-3211">passportnumber</span><span class="sxs-lookup"><span data-stu-id="484f6-3211">passportnumber</span></span> 
- <span data-ttu-id="484f6-3212">パスポート</span><span class="sxs-lookup"><span data-stu-id="484f6-3212">パスポート</span></span> 
- <span data-ttu-id="484f6-3213">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="484f6-3213">パスポート番号</span></span> 
- <span data-ttu-id="484f6-3214">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="484f6-3214">パスポートのNum</span></span> 
- <span data-ttu-id="484f6-3215">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="484f6-3215">パスポート＃</span></span> 
- <span data-ttu-id="484f6-3216">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="484f6-3216">Numéro de passeport</span></span> 
- <span data-ttu-id="484f6-3217">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="484f6-3217">Passeport n °</span></span> 
- <span data-ttu-id="484f6-3218">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="484f6-3218">Passeport Non</span></span> 
- <span data-ttu-id="484f6-3219">Passeport #</span><span class="sxs-lookup"><span data-stu-id="484f6-3219">Passeport #</span></span> 
- <span data-ttu-id="484f6-3220">Passeport#</span><span class="sxs-lookup"><span data-stu-id="484f6-3220">Passeport#</span></span> 
- <span data-ttu-id="484f6-3221">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="484f6-3221">PasseportNon</span></span> 
- <span data-ttu-id="484f6-3222">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="484f6-3222">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="484f6-3223">SWIFT 代码</span><span class="sxs-lookup"><span data-stu-id="484f6-3223">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="484f6-3224">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-3224">Format</span></span>

<span data-ttu-id="484f6-3225">四个字母后跟 5-31 个字母或数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3225">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-3226">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-3226">Pattern</span></span>

<span data-ttu-id="484f6-3227">四个字母后跟 5-31 个字母或数字：</span><span class="sxs-lookup"><span data-stu-id="484f6-3227">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="484f6-3228">四个字母的银行代码（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="484f6-3228">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="484f6-3229">可选空格</span><span class="sxs-lookup"><span data-stu-id="484f6-3229">An optional space</span></span> 
- <span data-ttu-id="484f6-3230">4-28 个字母或数字（基本银行账号 (BBAN)）</span><span class="sxs-lookup"><span data-stu-id="484f6-3230">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="484f6-3231">可选空格</span><span class="sxs-lookup"><span data-stu-id="484f6-3231">An optional space</span></span> 
- <span data-ttu-id="484f6-3232">1-3 个字母或数字（BBAN 的剩余内容）</span><span class="sxs-lookup"><span data-stu-id="484f6-3232">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-3233">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-3233">Checksum</span></span>

<span data-ttu-id="484f6-3234">否</span><span class="sxs-lookup"><span data-stu-id="484f6-3234">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-3235">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-3235">Definition</span></span>

<span data-ttu-id="484f6-3236">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-3236">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-3237">正则表达式 Regex_swift 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3237">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-3238">找到 Keyword_swift 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3238">A keyword from Keyword_swift is found.</span></span>

```
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="484f6-3239">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-3239">Keywords</span></span>
   
#### <a name="keywordswift"></a><span data-ttu-id="484f6-3240">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="484f6-3240">Keyword_swift</span></span>

- <span data-ttu-id="484f6-3241">international organization for standardization 9362</span><span class="sxs-lookup"><span data-stu-id="484f6-3241">international organization for standardization 9362</span></span> 
- <span data-ttu-id="484f6-3242">iso 9362</span><span class="sxs-lookup"><span data-stu-id="484f6-3242">iso 9362</span></span> 
- <span data-ttu-id="484f6-3243">iso9362</span><span class="sxs-lookup"><span data-stu-id="484f6-3243">iso9362</span></span> 
- <span data-ttu-id="484f6-3244">反应\#</span><span class="sxs-lookup"><span data-stu-id="484f6-3244">swift\#</span></span> 
- <span data-ttu-id="484f6-3245">swiftcode</span><span class="sxs-lookup"><span data-stu-id="484f6-3245">swiftcode</span></span> 
- <span data-ttu-id="484f6-3246">swiftnumber</span><span class="sxs-lookup"><span data-stu-id="484f6-3246">swiftnumber</span></span> 
- <span data-ttu-id="484f6-3247">swiftroutingnumber</span><span class="sxs-lookup"><span data-stu-id="484f6-3247">swiftroutingnumber</span></span> 
- <span data-ttu-id="484f6-3248">swift code</span><span class="sxs-lookup"><span data-stu-id="484f6-3248">swift code</span></span> 
- <span data-ttu-id="484f6-3249">swift number #</span><span class="sxs-lookup"><span data-stu-id="484f6-3249">swift number #</span></span> 
- <span data-ttu-id="484f6-3250">swift routing number</span><span class="sxs-lookup"><span data-stu-id="484f6-3250">swift routing number</span></span> 
- <span data-ttu-id="484f6-3251">bic number</span><span class="sxs-lookup"><span data-stu-id="484f6-3251">bic number</span></span> 
- <span data-ttu-id="484f6-3252">bic code</span><span class="sxs-lookup"><span data-stu-id="484f6-3252">bic code</span></span> 
- <span data-ttu-id="484f6-3253">numéro\#</span><span class="sxs-lookup"><span data-stu-id="484f6-3253">bic \#</span></span> 
- <span data-ttu-id="484f6-3254">numéro\#</span><span class="sxs-lookup"><span data-stu-id="484f6-3254">bic\#</span></span> 
- <span data-ttu-id="484f6-3255">bank identifier code</span><span class="sxs-lookup"><span data-stu-id="484f6-3255">bank identifier code</span></span> 
- <span data-ttu-id="484f6-3256">標準化9362</span><span class="sxs-lookup"><span data-stu-id="484f6-3256">標準化9362</span></span> 
- <span data-ttu-id="484f6-3257">迅速＃</span><span class="sxs-lookup"><span data-stu-id="484f6-3257">迅速＃</span></span> 
- <span data-ttu-id="484f6-3258">SWIFTコード</span><span class="sxs-lookup"><span data-stu-id="484f6-3258">SWIFTコード</span></span> 
- <span data-ttu-id="484f6-3259">SWIFT番号</span><span class="sxs-lookup"><span data-stu-id="484f6-3259">SWIFT番号</span></span> 
- <span data-ttu-id="484f6-3260">迅速なルーティング番号</span><span class="sxs-lookup"><span data-stu-id="484f6-3260">迅速なルーティング番号</span></span> 
- <span data-ttu-id="484f6-3261">BIC番号</span><span class="sxs-lookup"><span data-stu-id="484f6-3261">BIC番号</span></span> 
- <span data-ttu-id="484f6-3262">BICコード</span><span class="sxs-lookup"><span data-stu-id="484f6-3262">BICコード</span></span> 
- <span data-ttu-id="484f6-3263">銀行識別コードのための国際組織</span><span class="sxs-lookup"><span data-stu-id="484f6-3263">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="484f6-3264">Organisation internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="484f6-3264">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="484f6-3265">rapide\#</span><span class="sxs-lookup"><span data-stu-id="484f6-3265">rapide \#</span></span> 
- <span data-ttu-id="484f6-3266">code SWIFT</span><span class="sxs-lookup"><span data-stu-id="484f6-3266">code SWIFT</span></span> 
- <span data-ttu-id="484f6-3267">le numéro de swift</span><span class="sxs-lookup"><span data-stu-id="484f6-3267">le numéro de swift</span></span> 
- <span data-ttu-id="484f6-3268">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="484f6-3268">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="484f6-3269">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="484f6-3269">le numéro BIC</span></span> 
- <span data-ttu-id="484f6-3270">\#NUMÉRO</span><span class="sxs-lookup"><span data-stu-id="484f6-3270">\# BIC</span></span> 
- <span data-ttu-id="484f6-3271">code identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="484f6-3271">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="484f6-3272">台湾国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="484f6-3272">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="484f6-3273">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-3273">Format</span></span>

<span data-ttu-id="484f6-3274">一个字母后跟九个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3274">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-3275">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-3275">Pattern</span></span>

<span data-ttu-id="484f6-3276">一个字母后跟 9 位数字：</span><span class="sxs-lookup"><span data-stu-id="484f6-3276">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="484f6-3277">一个字母（英文，不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="484f6-3277">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="484f6-3278">数字“1”或“2”</span><span class="sxs-lookup"><span data-stu-id="484f6-3278">The digit "1" or "2"</span></span> 
- <span data-ttu-id="484f6-3279">八位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3279">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-3280">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-3280">Checksum</span></span>

<span data-ttu-id="484f6-3281">是</span><span class="sxs-lookup"><span data-stu-id="484f6-3281">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-3282">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-3282">Definition</span></span>

<span data-ttu-id="484f6-3283">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-3283">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-3284">函数 Func_taiwanese_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3284">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-3285">找到 Keyword_taiwanese_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3285">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="484f6-3286">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-3286">The checksum passes.</span></span>

```
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="484f6-3287">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-3287">Keywords</span></span>

#### <a name="keywordtaiwanesenationalid"></a><span data-ttu-id="484f6-3288">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="484f6-3288">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="484f6-3289">身份證字號</span><span class="sxs-lookup"><span data-stu-id="484f6-3289">身份證字號</span></span> 
- <span data-ttu-id="484f6-3290">證</span><span class="sxs-lookup"><span data-stu-id="484f6-3290">身份證</span></span> 
- <span data-ttu-id="484f6-3291">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="484f6-3291">身份證號碼</span></span> 
- <span data-ttu-id="484f6-3292">身份證號</span><span class="sxs-lookup"><span data-stu-id="484f6-3292">身份證號</span></span> 
- <span data-ttu-id="484f6-3293">身分證字號</span><span class="sxs-lookup"><span data-stu-id="484f6-3293">身分證字號</span></span> 
- <span data-ttu-id="484f6-3294">身分證</span><span class="sxs-lookup"><span data-stu-id="484f6-3294">身分證</span></span> 
- <span data-ttu-id="484f6-3295">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="484f6-3295">身分證號碼</span></span> 
- <span data-ttu-id="484f6-3296">身份證號</span><span class="sxs-lookup"><span data-stu-id="484f6-3296">身份證號</span></span> 
- <span data-ttu-id="484f6-3297">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="484f6-3297">身分證統一編號</span></span> 
- <span data-ttu-id="484f6-3298">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="484f6-3298">國民身分證統一編號</span></span> 
- <span data-ttu-id="484f6-3299">簽名</span><span class="sxs-lookup"><span data-stu-id="484f6-3299">簽名</span></span> 
- <span data-ttu-id="484f6-3300">蓋章</span><span class="sxs-lookup"><span data-stu-id="484f6-3300">蓋章</span></span> 
- <span data-ttu-id="484f6-3301">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="484f6-3301">簽名或蓋章</span></span> 
- <span data-ttu-id="484f6-3302">簽章</span><span class="sxs-lookup"><span data-stu-id="484f6-3302">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="484f6-3303">	台湾护照号码</span><span class="sxs-lookup"><span data-stu-id="484f6-3303">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-3304">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-3304">Format</span></span>

- <span data-ttu-id="484f6-3305">生物识别护照号码: 9 个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3305">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="484f6-3306">不带生物的护照号码: 9 个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3306">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-3307">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-3307">Pattern</span></span>
<span data-ttu-id="484f6-3308">生物识别护照号码:</span><span class="sxs-lookup"><span data-stu-id="484f6-3308">Biometric passport number:</span></span>
- <span data-ttu-id="484f6-3309">数字“3” </span><span class="sxs-lookup"><span data-stu-id="484f6-3309">The digit "3"</span></span> 
- <span data-ttu-id="484f6-3310">八个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3310">Eight digits</span></span>

<span data-ttu-id="484f6-3311">不带生物的护照号码:</span><span class="sxs-lookup"><span data-stu-id="484f6-3311">Non-biometric passport number:</span></span>
- <span data-ttu-id="484f6-3312">九个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3312">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-3313">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-3313">Checksum</span></span>

<span data-ttu-id="484f6-3314">否</span><span class="sxs-lookup"><span data-stu-id="484f6-3314">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-3315">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-3315">Definition</span></span>

<span data-ttu-id="484f6-3316">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-3316">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-3317">正则表达式 Regex_taiwan_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3317">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-3318">找到 Keyword_taiwan_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3318">A keyword from Keyword_taiwan_passport is found.</span></span>

```
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="484f6-3319">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-3319">Keywords</span></span>

#### <a name="keywordtaiwanpassport"></a><span data-ttu-id="484f6-3320">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="484f6-3320">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="484f6-3321">ROC passport number</span><span class="sxs-lookup"><span data-stu-id="484f6-3321">ROC passport number</span></span> 
- <span data-ttu-id="484f6-3322">Passport number</span><span class="sxs-lookup"><span data-stu-id="484f6-3322">Passport number</span></span> 
- <span data-ttu-id="484f6-3323">Passport no</span><span class="sxs-lookup"><span data-stu-id="484f6-3323">Passport no</span></span> 
- <span data-ttu-id="484f6-3324">Passport Num</span><span class="sxs-lookup"><span data-stu-id="484f6-3324">Passport Num</span></span> 
- <span data-ttu-id="484f6-3325">Passport #</span><span class="sxs-lookup"><span data-stu-id="484f6-3325">Passport #</span></span> 
- <span data-ttu-id="484f6-3326">护照</span><span class="sxs-lookup"><span data-stu-id="484f6-3326">护照</span></span> 
- <span data-ttu-id="484f6-3327">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="484f6-3327">中華民國護照</span></span> 
- <span data-ttu-id="484f6-3328">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="484f6-3328">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="484f6-3329">台湾居民证 (ARC/TARC) 号码</span><span class="sxs-lookup"><span data-stu-id="484f6-3329">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-3330">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-3330">Format</span></span>

<span data-ttu-id="484f6-3331">10 letters and digits</span><span class="sxs-lookup"><span data-stu-id="484f6-3331">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-3332">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-3332">Pattern</span></span>

<span data-ttu-id="484f6-3333">10 个字母和数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3333">10 letters and digits:</span></span>
- <span data-ttu-id="484f6-3334">两个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="484f6-3334">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="484f6-3335">八个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3335">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-3336">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-3336">Checksum</span></span>

<span data-ttu-id="484f6-3337">否</span><span class="sxs-lookup"><span data-stu-id="484f6-3337">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-3338">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-3338">Definition</span></span>

<span data-ttu-id="484f6-3339">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-3339">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-3340">正则表达式 Regex_taiwan_resident_certificate 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3340">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-3341">找到 Keyword_taiwan_resident_certificate 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3341">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="484f6-3342">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-3342">Keywords</span></span>

#### <a name="keywordtaiwanresidentcertificate"></a><span data-ttu-id="484f6-3343">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="484f6-3343">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="484f6-3344">Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="484f6-3344">Resident Certificate</span></span> 
- <span data-ttu-id="484f6-3345">Resident Cert</span><span class="sxs-lookup"><span data-stu-id="484f6-3345">Resident Cert</span></span> 
- <span data-ttu-id="484f6-3346">Resident Cert.</span><span class="sxs-lookup"><span data-stu-id="484f6-3346">Resident Cert.</span></span> 
- <span data-ttu-id="484f6-3347">Identification card</span><span class="sxs-lookup"><span data-stu-id="484f6-3347">Identification card</span></span> 
- <span data-ttu-id="484f6-3348">Alien Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="484f6-3348">Alien Resident Certificate</span></span> 
- <span data-ttu-id="484f6-3349">ARC</span><span class="sxs-lookup"><span data-stu-id="484f6-3349">ARC</span></span> 
- <span data-ttu-id="484f6-3350">Taiwan Area Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="484f6-3350">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="484f6-3351">TARC</span><span class="sxs-lookup"><span data-stu-id="484f6-3351">TARC</span></span> 
- <span data-ttu-id="484f6-3352">居留證</span><span class="sxs-lookup"><span data-stu-id="484f6-3352">居留證</span></span> 
- <span data-ttu-id="484f6-3353">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="484f6-3353">外僑居留證</span></span> 
- <span data-ttu-id="484f6-3354">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="484f6-3354">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="484f6-3355">泰语填充标识代码</span><span class="sxs-lookup"><span data-stu-id="484f6-3355">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="484f6-3356">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-3356">Format</span></span>

<span data-ttu-id="484f6-3357">13 位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3357">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-3358">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-3358">Pattern</span></span>

<span data-ttu-id="484f6-3359">13 个数字：</span><span class="sxs-lookup"><span data-stu-id="484f6-3359">13 digits:</span></span>
- <span data-ttu-id="484f6-3360">第一个数字不是0或9</span><span class="sxs-lookup"><span data-stu-id="484f6-3360">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="484f6-3361">12 个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3361">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-3362">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-3362">Checksum</span></span>

<span data-ttu-id="484f6-3363">是</span><span class="sxs-lookup"><span data-stu-id="484f6-3363">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-3364">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-3364">Definition</span></span>

<span data-ttu-id="484f6-3365">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-3365">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-3366">函数 Func_Thai_Citizen_Id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3366">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-3367">找到 Keyword_Thai_Citizen_Id 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3367">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="484f6-3368">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-3368">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-3369">函数 Func_Thai_Citizen_Id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3369">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-3370">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-3370">Keywords</span></span>

#### <a name="keywordthaicitizenid"></a><span data-ttu-id="484f6-3371">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="484f6-3371">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="484f6-3372">ID Number</span><span class="sxs-lookup"><span data-stu-id="484f6-3372">ID Number</span></span>
- <span data-ttu-id="484f6-3373">标识号码</span><span class="sxs-lookup"><span data-stu-id="484f6-3373">Identification Number</span></span>
- <span data-ttu-id="484f6-3374">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="484f6-3374">บัตรประชาชน</span></span>
- <span data-ttu-id="484f6-3375">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="484f6-3375">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="484f6-3376">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="484f6-3376">บัตรประชาชน</span></span>
- <span data-ttu-id="484f6-3377">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="484f6-3377">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="484f6-3378">土耳其国家标识号码</span><span class="sxs-lookup"><span data-stu-id="484f6-3378">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-3379">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-3379">Format</span></span>

<span data-ttu-id="484f6-3380">11 个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3380">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-3381">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-3381">Pattern</span></span>

<span data-ttu-id="484f6-3382">11 个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3382">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-3383">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-3383">Checksum</span></span>

<span data-ttu-id="484f6-3384">是</span><span class="sxs-lookup"><span data-stu-id="484f6-3384">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-3385">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-3385">Definition</span></span>

<span data-ttu-id="484f6-3386">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-3386">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-3387">函数 Func_Turkish_National_Id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3387">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-3388">找到 Keyword_Turkish_National_Id 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3388">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="484f6-3389">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-3389">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-3390">函数 Func_Turkish_National_Id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3390">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-3391">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-3391">Keywords</span></span>

#### <a name="keywordturkishnationalid"></a><span data-ttu-id="484f6-3392">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="484f6-3392">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="484f6-3393">TC Kimlik No</span><span class="sxs-lookup"><span data-stu-id="484f6-3393">TC Kimlik No</span></span>
- <span data-ttu-id="484f6-3394">TC Kimlik numarası</span><span class="sxs-lookup"><span data-stu-id="484f6-3394">TC Kimlik numarası</span></span>
- <span data-ttu-id="484f6-3395">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="484f6-3395">Vatandaşlık numarası</span></span>
- <span data-ttu-id="484f6-3396">Vatandaşlık no</span><span class="sxs-lookup"><span data-stu-id="484f6-3396">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="484f6-p142">英国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="484f6-p142">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-3399">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-3399">Format</span></span>

<span data-ttu-id="484f6-3400">特定格式的 18 个字母和数字组合</span><span class="sxs-lookup"><span data-stu-id="484f6-3400">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-3401">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-3401">Pattern</span></span>

<span data-ttu-id="484f6-3402">18 个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="484f6-3402">18 letters and digits:</span></span>
- <span data-ttu-id="484f6-3403">用五个字母（不区分大小写）或数字“9”来代替一个字母</span><span class="sxs-lookup"><span data-stu-id="484f6-3403">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="484f6-3404">一位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3404">One digit</span></span> 
- <span data-ttu-id="484f6-3405">采用日期格式 DDMMY 的五位数字，表示出生日期</span><span class="sxs-lookup"><span data-stu-id="484f6-3405">Five digits in the date format DDMMY for date of birth</span></span> 
- <span data-ttu-id="484f6-3406">用两个字母（不区分大小写）或数字“9”来代替一个字母</span><span class="sxs-lookup"><span data-stu-id="484f6-3406">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="484f6-3407">五位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3407">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-3408">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-3408">Checksum</span></span>

<span data-ttu-id="484f6-3409">是</span><span class="sxs-lookup"><span data-stu-id="484f6-3409">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-3410">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-3410">Definition</span></span>

<span data-ttu-id="484f6-3411">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-3411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-3412">函数 Func_uk_drivers_license 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3412">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-3413">找到 Keyword_uk_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3413">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="484f6-3414">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-3414">The checksum passes.</span></span>

```
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="484f6-3415">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-3415">Keywords</span></span>

#### <a name="keywordukdriverslicense"></a><span data-ttu-id="484f6-3416">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="484f6-3416">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="484f6-3417">DVLA</span><span class="sxs-lookup"><span data-stu-id="484f6-3417">DVLA</span></span> 
- <span data-ttu-id="484f6-3418">light vans</span><span class="sxs-lookup"><span data-stu-id="484f6-3418">light vans</span></span> 
- <span data-ttu-id="484f6-3419">quadbikes</span><span class="sxs-lookup"><span data-stu-id="484f6-3419">quadbikes</span></span> 
- <span data-ttu-id="484f6-3420">motor cars</span><span class="sxs-lookup"><span data-stu-id="484f6-3420">motor cars</span></span> 
- <span data-ttu-id="484f6-3421">125cc</span><span class="sxs-lookup"><span data-stu-id="484f6-3421">125cc</span></span> 
- <span data-ttu-id="484f6-3422">sidecar</span><span class="sxs-lookup"><span data-stu-id="484f6-3422">sidecar</span></span> 
- <span data-ttu-id="484f6-3423">tricycles</span><span class="sxs-lookup"><span data-stu-id="484f6-3423">tricycles</span></span> 
- <span data-ttu-id="484f6-3424">motorcycles</span><span class="sxs-lookup"><span data-stu-id="484f6-3424">motorcycles</span></span> 
- <span data-ttu-id="484f6-3425">photocard licence</span><span class="sxs-lookup"><span data-stu-id="484f6-3425">photocard licence</span></span> 
- <span data-ttu-id="484f6-3426">learner drivers</span><span class="sxs-lookup"><span data-stu-id="484f6-3426">learner drivers</span></span> 
- <span data-ttu-id="484f6-3427">licence holder</span><span class="sxs-lookup"><span data-stu-id="484f6-3427">licence holder</span></span> 
- <span data-ttu-id="484f6-3428">licence holders</span><span class="sxs-lookup"><span data-stu-id="484f6-3428">licence holders</span></span> 
- <span data-ttu-id="484f6-3429">driving licences</span><span class="sxs-lookup"><span data-stu-id="484f6-3429">driving licences</span></span> 
- <span data-ttu-id="484f6-3430">driving licence</span><span class="sxs-lookup"><span data-stu-id="484f6-3430">driving licence</span></span> 
- <span data-ttu-id="484f6-3431">dual control car</span><span class="sxs-lookup"><span data-stu-id="484f6-3431">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="484f6-p143">英国选民名册号码</span><span class="sxs-lookup"><span data-stu-id="484f6-p143">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-3434">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-3434">Format</span></span>

<span data-ttu-id="484f6-3435">两个字母后跟 1-4 个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3435">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-3436">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-3436">Pattern</span></span>

<span data-ttu-id="484f6-3437">两个字母（不区分大小写）后跟 1-4 个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3437">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-3438">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-3438">Checksum</span></span>

<span data-ttu-id="484f6-3439">否</span><span class="sxs-lookup"><span data-stu-id="484f6-3439">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-3440">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-3440">Definition</span></span>

<span data-ttu-id="484f6-3441">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-3441">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-3442">正则表达式 Regex_uk_electoral 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3442">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-3443">找到 Keyword_uk_electoral 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3443">A keyword from Keyword_uk_electoral is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-3444">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-3444">Keywords</span></span>

#### <a name="keywordukelectoral"></a><span data-ttu-id="484f6-3445">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="484f6-3445">Keyword_uk_electoral</span></span>

- <span data-ttu-id="484f6-3446">council nomination</span><span class="sxs-lookup"><span data-stu-id="484f6-3446">council nomination</span></span> 
- <span data-ttu-id="484f6-3447">nomination form</span><span class="sxs-lookup"><span data-stu-id="484f6-3447">nomination form</span></span> 
- <span data-ttu-id="484f6-3448">electoral register</span><span class="sxs-lookup"><span data-stu-id="484f6-3448">electoral register</span></span> 
- <span data-ttu-id="484f6-3449">electoral roll</span><span class="sxs-lookup"><span data-stu-id="484f6-3449">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="484f6-p144">英国国家卫生服务号码</span><span class="sxs-lookup"><span data-stu-id="484f6-p144">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-3452">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-3452">Format</span></span>

<span data-ttu-id="484f6-3453">10-17 个数字，通过空格分隔 </span><span class="sxs-lookup"><span data-stu-id="484f6-3453">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-3454">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-3454">Pattern</span></span>

<span data-ttu-id="484f6-3455">10-17 位数字：</span><span class="sxs-lookup"><span data-stu-id="484f6-3455">10-17 digits:</span></span>
- <span data-ttu-id="484f6-3456">3 或 10 位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3456">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="484f6-3457">一个空格</span><span class="sxs-lookup"><span data-stu-id="484f6-3457">A space</span></span> 
- <span data-ttu-id="484f6-3458">三位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3458">Three digits</span></span> 
- <span data-ttu-id="484f6-3459">一个空格</span><span class="sxs-lookup"><span data-stu-id="484f6-3459">A space</span></span> 
- <span data-ttu-id="484f6-3460">四位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3460">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-3461">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-3461">Checksum</span></span>

<span data-ttu-id="484f6-3462">是</span><span class="sxs-lookup"><span data-stu-id="484f6-3462">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-3463">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-3463">Definition</span></span>

<span data-ttu-id="484f6-3464">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-3464">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-3465">函数 Func_uk_nhs_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3465">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-3466">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="484f6-3466">One of the following is true:</span></span>
    - <span data-ttu-id="484f6-3467">找到 Keyword_uk_nhs_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3467">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="484f6-3468">找到 Keyword_uk_nhs_number1 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3468">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="484f6-3469">找到 Keyword_uk_nhs_number_dob 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3469">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="484f6-3470">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="484f6-3470">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-3471">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-3471">Keywords</span></span>
   
#### <a name="keyworduknhsnumber"></a><span data-ttu-id="484f6-3472">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="484f6-3472">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="484f6-3473">national health service</span><span class="sxs-lookup"><span data-stu-id="484f6-3473">national health service</span></span> 
- <span data-ttu-id="484f6-3474">nhs</span><span class="sxs-lookup"><span data-stu-id="484f6-3474">nhs</span></span> 
- <span data-ttu-id="484f6-3475">health services authority</span><span class="sxs-lookup"><span data-stu-id="484f6-3475">health services authority</span></span> 
- <span data-ttu-id="484f6-3476">health authority</span><span class="sxs-lookup"><span data-stu-id="484f6-3476">health authority</span></span>

#### <a name="keyworduknhsnumber1"></a><span data-ttu-id="484f6-3477">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="484f6-3477">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="484f6-3478">patient id</span><span class="sxs-lookup"><span data-stu-id="484f6-3478">patient id</span></span> 
- <span data-ttu-id="484f6-3479">patient identification</span><span class="sxs-lookup"><span data-stu-id="484f6-3479">patient identification</span></span> 
- <span data-ttu-id="484f6-3480">patient no</span><span class="sxs-lookup"><span data-stu-id="484f6-3480">patient no</span></span> 
- <span data-ttu-id="484f6-3481">patient number</span><span class="sxs-lookup"><span data-stu-id="484f6-3481">patient number</span></span>

#### <a name="keyworduknhsnumberdob"></a><span data-ttu-id="484f6-3482">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="484f6-3482">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="484f6-3483">GP</span><span class="sxs-lookup"><span data-stu-id="484f6-3483">GP</span></span> 
- <span data-ttu-id="484f6-3484">DOB</span><span class="sxs-lookup"><span data-stu-id="484f6-3484">DOB</span></span> 
- <span data-ttu-id="484f6-3485">D. B。</span><span class="sxs-lookup"><span data-stu-id="484f6-3485">D.O.B</span></span> 
- <span data-ttu-id="484f6-3486">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="484f6-3486">Date of Birth</span></span> 
- <span data-ttu-id="484f6-3487">Birth Date</span><span class="sxs-lookup"><span data-stu-id="484f6-3487">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="484f6-p145">英国国家保险号码 (NINO)</span><span class="sxs-lookup"><span data-stu-id="484f6-p145">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="484f6-3490">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-3490">Format</span></span>

<span data-ttu-id="484f6-3491">由空格或短划线分隔的7个字符或9个字符</span><span class="sxs-lookup"><span data-stu-id="484f6-3491">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-3492">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-3492">Pattern</span></span>

<span data-ttu-id="484f6-3493">两种可能的模式:</span><span class="sxs-lookup"><span data-stu-id="484f6-3493">Two possible patterns:</span></span>

- <span data-ttu-id="484f6-3494">两个字母 (有效 NINOs 仅使用此前缀中的特定字符, 此格式将对此进行验证; 不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="484f6-3494">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="484f6-3495">六位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3495">Six digits</span></span>
- <span data-ttu-id="484f6-3496">"A"、"B"、"C" 或 "d" (与前缀一样, 后缀中只允许有某些字符; 不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="484f6-3496">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="484f6-3497">OR</span><span class="sxs-lookup"><span data-stu-id="484f6-3497">OR</span></span>

- <span data-ttu-id="484f6-3498">两个字母</span><span class="sxs-lookup"><span data-stu-id="484f6-3498">Two letters</span></span>
- <span data-ttu-id="484f6-3499">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="484f6-3499">A space or dash</span></span>
- <span data-ttu-id="484f6-3500">两位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3500">Two digits</span></span>
- <span data-ttu-id="484f6-3501">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="484f6-3501">A space or dash</span></span>
- <span data-ttu-id="484f6-3502">两位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3502">Two digits</span></span>
- <span data-ttu-id="484f6-3503">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="484f6-3503">A space or dash</span></span>
- <span data-ttu-id="484f6-3504">两位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3504">Two digits</span></span>
- <span data-ttu-id="484f6-3505">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="484f6-3505">A space or dash</span></span>
- <span data-ttu-id="484f6-3506">要么是 "A"、"B"、"C", 要么 ' d '</span><span class="sxs-lookup"><span data-stu-id="484f6-3506">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-3507">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-3507">Checksum</span></span>

<span data-ttu-id="484f6-3508">否</span><span class="sxs-lookup"><span data-stu-id="484f6-3508">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-3509">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-3509">Definition</span></span>

<span data-ttu-id="484f6-3510">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-3510">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-3511">函数 Func_uk_nino 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3511">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-3512">找到 Keyword_uk_nino 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3512">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="484f6-3513">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-3513">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-3514">函数 Func_uk_nino 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3514">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-3515">未找到 Keyword_uk_nino 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3515">No keyword from Keyword_uk_nino is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-3516">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-3516">Keywords</span></span>

#### <a name="keyworduknino"></a><span data-ttu-id="484f6-3517">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="484f6-3517">Keyword_uk_nino</span></span>

- <span data-ttu-id="484f6-3518">national insurance number</span><span class="sxs-lookup"><span data-stu-id="484f6-3518">national insurance number</span></span> 
- <span data-ttu-id="484f6-3519">national insurance contributions</span><span class="sxs-lookup"><span data-stu-id="484f6-3519">national insurance contributions</span></span> 
- <span data-ttu-id="484f6-3520">protection act</span><span class="sxs-lookup"><span data-stu-id="484f6-3520">protection act</span></span> 
- <span data-ttu-id="484f6-3521">方面</span><span class="sxs-lookup"><span data-stu-id="484f6-3521">insurance</span></span> 
- <span data-ttu-id="484f6-3522">social security number</span><span class="sxs-lookup"><span data-stu-id="484f6-3522">social security number</span></span> 
- <span data-ttu-id="484f6-3523">insurance application</span><span class="sxs-lookup"><span data-stu-id="484f6-3523">insurance application</span></span> 
- <span data-ttu-id="484f6-3524">medical application</span><span class="sxs-lookup"><span data-stu-id="484f6-3524">medical application</span></span> 
- <span data-ttu-id="484f6-3525">social insurance</span><span class="sxs-lookup"><span data-stu-id="484f6-3525">social insurance</span></span> 
- <span data-ttu-id="484f6-3526">medical attention</span><span class="sxs-lookup"><span data-stu-id="484f6-3526">medical attention</span></span> 
- <span data-ttu-id="484f6-3527">social security</span><span class="sxs-lookup"><span data-stu-id="484f6-3527">social security</span></span> 
- <span data-ttu-id="484f6-3528">great britain</span><span class="sxs-lookup"><span data-stu-id="484f6-3528">great britain</span></span> 
- <span data-ttu-id="484f6-3529">方面</span><span class="sxs-lookup"><span data-stu-id="484f6-3529">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="484f6-p146">美国/英国护照号码</span><span class="sxs-lookup"><span data-stu-id="484f6-p146">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-3532">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-3532">Format</span></span>

<span data-ttu-id="484f6-3533">九个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3533">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-3534">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-3534">Pattern</span></span>

<span data-ttu-id="484f6-3535">九个连续的数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3535">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-3536">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-3536">Checksum</span></span>

<span data-ttu-id="484f6-3537">否</span><span class="sxs-lookup"><span data-stu-id="484f6-3537">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-3538">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-3538">Definition</span></span>

<span data-ttu-id="484f6-3539">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-3539">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-3540">函数 Func_usa_uk_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3540">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-3541">找到 Keyword_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3541">A keyword from Keyword_passport is found.</span></span>

```
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="484f6-3542">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-3542">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="484f6-3543">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="484f6-3543">Keyword_passport</span></span>

- <span data-ttu-id="484f6-3544">Passport Number</span><span class="sxs-lookup"><span data-stu-id="484f6-3544">Passport Number</span></span> 
- <span data-ttu-id="484f6-3545">Passport No</span><span class="sxs-lookup"><span data-stu-id="484f6-3545">Passport No</span></span> 
- <span data-ttu-id="484f6-3546">Passport #</span><span class="sxs-lookup"><span data-stu-id="484f6-3546">Passport #</span></span> 
- <span data-ttu-id="484f6-3547">登记卡</span><span class="sxs-lookup"><span data-stu-id="484f6-3547">Passport#</span></span> 
- <span data-ttu-id="484f6-3548">PassportID</span><span class="sxs-lookup"><span data-stu-id="484f6-3548">PassportID</span></span> 
- <span data-ttu-id="484f6-3549">Passportno</span><span class="sxs-lookup"><span data-stu-id="484f6-3549">Passportno</span></span> 
- <span data-ttu-id="484f6-3550">passportnumber</span><span class="sxs-lookup"><span data-stu-id="484f6-3550">passportnumber</span></span> 
- <span data-ttu-id="484f6-3551">パスポート</span><span class="sxs-lookup"><span data-stu-id="484f6-3551">パスポート</span></span> 
- <span data-ttu-id="484f6-3552">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="484f6-3552">パスポート番号</span></span> 
- <span data-ttu-id="484f6-3553">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="484f6-3553">パスポートのNum</span></span> 
- <span data-ttu-id="484f6-3554">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="484f6-3554">パスポート＃</span></span> 
- <span data-ttu-id="484f6-3555">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="484f6-3555">Numéro de passeport</span></span> 
- <span data-ttu-id="484f6-3556">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="484f6-3556">Passeport n °</span></span> 
- <span data-ttu-id="484f6-3557">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="484f6-3557">Passeport Non</span></span> 
- <span data-ttu-id="484f6-3558">Passeport #</span><span class="sxs-lookup"><span data-stu-id="484f6-3558">Passeport #</span></span> 
- <span data-ttu-id="484f6-3559">Passeport#</span><span class="sxs-lookup"><span data-stu-id="484f6-3559">Passeport#</span></span> 
- <span data-ttu-id="484f6-3560">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="484f6-3560">PasseportNon</span></span> 
- <span data-ttu-id="484f6-3561">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="484f6-3561">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="484f6-3562">美国银行帐号</span><span class="sxs-lookup"><span data-stu-id="484f6-3562">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-3563">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-3563">Format</span></span>

<span data-ttu-id="484f6-3564">8-17 个数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3564">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-3565">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-3565">Pattern</span></span>

<span data-ttu-id="484f6-3566">8-17 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3566">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-3567">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-3567">Checksum</span></span>

<span data-ttu-id="484f6-3568">否</span><span class="sxs-lookup"><span data-stu-id="484f6-3568">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-3569">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-3569">Definition</span></span>

<span data-ttu-id="484f6-3570">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-3570">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-3571">正则表达式 Regex_usa_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3571">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-3572">找到 Keyword_usa_Bank_Account 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3572">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="484f6-3573">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-3573">Keywords</span></span>

#### <a name="keywordusabankaccount"></a><span data-ttu-id="484f6-3574">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="484f6-3574">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="484f6-3575">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="484f6-3575">Checking Account Number</span></span> 
- <span data-ttu-id="484f6-3576">Checking Account</span><span class="sxs-lookup"><span data-stu-id="484f6-3576">Checking Account</span></span> 
- <span data-ttu-id="484f6-3577">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="484f6-3577">Checking Account #</span></span> 
- <span data-ttu-id="484f6-3578">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="484f6-3578">Checking Acct Number</span></span> 
- <span data-ttu-id="484f6-3579">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="484f6-3579">Checking Acct #</span></span> 
- <span data-ttu-id="484f6-3580">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="484f6-3580">Checking Acct No.</span></span> 
- <span data-ttu-id="484f6-3581">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="484f6-3581">Checking Account No.</span></span> 
- <span data-ttu-id="484f6-3582">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="484f6-3582">Bank Account Number</span></span> 
- <span data-ttu-id="484f6-3583">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="484f6-3583">Bank Account #</span></span> 
- <span data-ttu-id="484f6-3584">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="484f6-3584">Bank Acct Number</span></span> 
- <span data-ttu-id="484f6-3585">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="484f6-3585">Bank Acct #</span></span> 
- <span data-ttu-id="484f6-3586">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="484f6-3586">Bank Acct No.</span></span> 
- <span data-ttu-id="484f6-3587">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="484f6-3587">Bank Account No.</span></span> 
- <span data-ttu-id="484f6-3588">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="484f6-3588">Savings Account Number</span></span> 
- <span data-ttu-id="484f6-3589">Savings Account.</span><span class="sxs-lookup"><span data-stu-id="484f6-3589">Savings Account.</span></span> 
- <span data-ttu-id="484f6-3590">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="484f6-3590">Savings Account #</span></span> 
- <span data-ttu-id="484f6-3591">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="484f6-3591">Savings Acct Number</span></span> 
- <span data-ttu-id="484f6-3592">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="484f6-3592">Savings Acct #</span></span> 
- <span data-ttu-id="484f6-3593">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="484f6-3593">Savings Acct No.</span></span> 
- <span data-ttu-id="484f6-3594">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="484f6-3594">Savings Account No.</span></span> 
- <span data-ttu-id="484f6-3595">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="484f6-3595">Debit Account Number</span></span> 
- <span data-ttu-id="484f6-3596">Debit Account</span><span class="sxs-lookup"><span data-stu-id="484f6-3596">Debit Account</span></span> 
- <span data-ttu-id="484f6-3597">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="484f6-3597">Debit Account #</span></span> 
- <span data-ttu-id="484f6-3598">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="484f6-3598">Debit Acct Number</span></span> 
- <span data-ttu-id="484f6-3599">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="484f6-3599">Debit Acct #</span></span> 
- <span data-ttu-id="484f6-3600">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="484f6-3600">Debit Acct No.</span></span> 
- <span data-ttu-id="484f6-3601">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="484f6-3601">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="484f6-3602">美国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="484f6-3602">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="484f6-3603">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-3603">Format</span></span>

<span data-ttu-id="484f6-3604">取决于州</span><span class="sxs-lookup"><span data-stu-id="484f6-3604">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-3605">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-3605">Pattern</span></span>

<span data-ttu-id="484f6-3606">取决于州 — 例如，纽约：</span><span class="sxs-lookup"><span data-stu-id="484f6-3606">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="484f6-3607">与 ddd ddd ddd 相匹配的9个数字的格式将会匹配。</span><span class="sxs-lookup"><span data-stu-id="484f6-3607">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="484f6-3608">诸如 dddddddd 的 9 个数字将不匹配。</span><span class="sxs-lookup"><span data-stu-id="484f6-3608">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-3609">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-3609">Checksum</span></span>

<span data-ttu-id="484f6-3610">否</span><span class="sxs-lookup"><span data-stu-id="484f6-3610">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-3611">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-3611">Definition</span></span>

<span data-ttu-id="484f6-3612">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-3612">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-3613">函数 Func_new_york_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3613">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-3614">找到 Keyword_[state_name]_drivers_license_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3614">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="484f6-3615">找到 Keyword_us_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3615">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="484f6-3616">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-3616">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-3617">函数 Func_new_york_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3617">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-3618">找到 Keyword_[state_name]_drivers_license_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3618">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="484f6-3619">找到 Keyword_us_drivers_license_abbreviations 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3619">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="484f6-3620">未找到 Keyword_us_drivers_license 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3620">No keyword from Keyword_us_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-3621">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-3621">Keywords</span></span>

#### <a name="keywordusdriverslicenseabbreviations"></a><span data-ttu-id="484f6-3622">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="484f6-3622">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="484f6-3623">通讯</span><span class="sxs-lookup"><span data-stu-id="484f6-3623">DL</span></span> 
- <span data-ttu-id="484f6-3624">DLS</span><span class="sxs-lookup"><span data-stu-id="484f6-3624">DLS</span></span> 
- <span data-ttu-id="484f6-3625">采用</span><span class="sxs-lookup"><span data-stu-id="484f6-3625">CDL</span></span> 
- <span data-ttu-id="484f6-3626">CDLS</span><span class="sxs-lookup"><span data-stu-id="484f6-3626">CDLS</span></span> 
- <span data-ttu-id="484f6-3627">ID</span><span class="sxs-lookup"><span data-stu-id="484f6-3627">ID</span></span> 
- <span data-ttu-id="484f6-3628">Id</span><span class="sxs-lookup"><span data-stu-id="484f6-3628">IDs</span></span> 
- <span data-ttu-id="484f6-3629">通讯</span><span class="sxs-lookup"><span data-stu-id="484f6-3629">DL#</span></span> 
- <span data-ttu-id="484f6-3630">DLS</span><span class="sxs-lookup"><span data-stu-id="484f6-3630">DLS#</span></span> 
- <span data-ttu-id="484f6-3631">采用</span><span class="sxs-lookup"><span data-stu-id="484f6-3631">CDL#</span></span> 
- <span data-ttu-id="484f6-3632">CDLS#</span><span class="sxs-lookup"><span data-stu-id="484f6-3632">CDLS#</span></span> 
- <span data-ttu-id="484f6-3633">号</span><span class="sxs-lookup"><span data-stu-id="484f6-3633">ID#</span></span>
- <span data-ttu-id="484f6-3634">Id</span><span class="sxs-lookup"><span data-stu-id="484f6-3634">IDs#</span></span> 
- <span data-ttu-id="484f6-3635">ID number</span><span class="sxs-lookup"><span data-stu-id="484f6-3635">ID number</span></span> 
- <span data-ttu-id="484f6-3636">ID numbers</span><span class="sxs-lookup"><span data-stu-id="484f6-3636">ID numbers</span></span> 
- <span data-ttu-id="484f6-3637">.LIC</span><span class="sxs-lookup"><span data-stu-id="484f6-3637">LIC</span></span> 
- <span data-ttu-id="484f6-3638">.LIC</span><span class="sxs-lookup"><span data-stu-id="484f6-3638">LIC#</span></span> 

#### <a name="keywordusdriverslicense"></a><span data-ttu-id="484f6-3639">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="484f6-3639">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="484f6-3640">DriverLic</span><span class="sxs-lookup"><span data-stu-id="484f6-3640">DriverLic</span></span> 
- <span data-ttu-id="484f6-3641">DriverLics</span><span class="sxs-lookup"><span data-stu-id="484f6-3641">DriverLics</span></span> 
- <span data-ttu-id="484f6-3642">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="484f6-3642">DriverLicense</span></span> 
- <span data-ttu-id="484f6-3643">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="484f6-3643">DriverLicenses</span></span> 
- <span data-ttu-id="484f6-3644">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="484f6-3644">Driver Lic</span></span> 
- <span data-ttu-id="484f6-3645">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="484f6-3645">Driver Lics</span></span> 
- <span data-ttu-id="484f6-3646">Driver License</span><span class="sxs-lookup"><span data-stu-id="484f6-3646">Driver License</span></span> 
- <span data-ttu-id="484f6-3647">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="484f6-3647">Driver Licenses</span></span> 
- <span data-ttu-id="484f6-3648">DriversLic</span><span class="sxs-lookup"><span data-stu-id="484f6-3648">DriversLic</span></span> 
- <span data-ttu-id="484f6-3649">DriversLics</span><span class="sxs-lookup"><span data-stu-id="484f6-3649">DriversLics</span></span> 
- <span data-ttu-id="484f6-3650">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="484f6-3650">DriversLicense</span></span> 
- <span data-ttu-id="484f6-3651">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="484f6-3651">DriversLicenses</span></span> 
- <span data-ttu-id="484f6-3652">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="484f6-3652">Drivers Lic</span></span> 
- <span data-ttu-id="484f6-3653">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="484f6-3653">Drivers Lics</span></span> 
- <span data-ttu-id="484f6-3654">Drivers License</span><span class="sxs-lookup"><span data-stu-id="484f6-3654">Drivers License</span></span> 
- <span data-ttu-id="484f6-3655">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="484f6-3655">Drivers Licenses</span></span> 
- <span data-ttu-id="484f6-3656">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="484f6-3656">Driver'Lic</span></span> 
- <span data-ttu-id="484f6-3657">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="484f6-3657">Driver'Lics</span></span> 
- <span data-ttu-id="484f6-3658">Driver'License</span><span class="sxs-lookup"><span data-stu-id="484f6-3658">Driver'License</span></span> 
- <span data-ttu-id="484f6-3659">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="484f6-3659">Driver'Licenses</span></span> 
- <span data-ttu-id="484f6-3660">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="484f6-3660">Driver' Lic</span></span> 
- <span data-ttu-id="484f6-3661">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="484f6-3661">Driver' Lics</span></span> 
- <span data-ttu-id="484f6-3662">Driver' License</span><span class="sxs-lookup"><span data-stu-id="484f6-3662">Driver' License</span></span> 
- <span data-ttu-id="484f6-3663">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="484f6-3663">Driver' Licenses</span></span>
- <span data-ttu-id="484f6-3664">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="484f6-3664">Driver'sLic</span></span> 
- <span data-ttu-id="484f6-3665">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="484f6-3665">Driver'sLics</span></span> 
- <span data-ttu-id="484f6-3666">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="484f6-3666">Driver'sLicense</span></span> 
- <span data-ttu-id="484f6-3667">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="484f6-3667">Driver'sLicenses</span></span> 
- <span data-ttu-id="484f6-3668">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="484f6-3668">Driver's Lic</span></span> 
- <span data-ttu-id="484f6-3669">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="484f6-3669">Driver's Lics</span></span> 
- <span data-ttu-id="484f6-3670">Driver's License</span><span class="sxs-lookup"><span data-stu-id="484f6-3670">Driver's License</span></span> 
- <span data-ttu-id="484f6-3671">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="484f6-3671">Driver's Licenses</span></span> 
- <span data-ttu-id="484f6-3672">identification number</span><span class="sxs-lookup"><span data-stu-id="484f6-3672">identification number</span></span> 
- <span data-ttu-id="484f6-3673">identification numbers</span><span class="sxs-lookup"><span data-stu-id="484f6-3673">identification numbers</span></span> 
- <span data-ttu-id="484f6-3674">identification #</span><span class="sxs-lookup"><span data-stu-id="484f6-3674">identification #</span></span> 
- <span data-ttu-id="484f6-3675">id card</span><span class="sxs-lookup"><span data-stu-id="484f6-3675">id card</span></span> 
- <span data-ttu-id="484f6-3676">id cards</span><span class="sxs-lookup"><span data-stu-id="484f6-3676">id cards</span></span> 
- <span data-ttu-id="484f6-3677">identification card</span><span class="sxs-lookup"><span data-stu-id="484f6-3677">identification card</span></span> 
- <span data-ttu-id="484f6-3678">identification cards</span><span class="sxs-lookup"><span data-stu-id="484f6-3678">identification cards</span></span> 
- <span data-ttu-id="484f6-3679">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="484f6-3679">DriverLic#</span></span> 
- <span data-ttu-id="484f6-3680">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="484f6-3680">DriverLics#</span></span> 
- <span data-ttu-id="484f6-3681">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="484f6-3681">DriverLicense#</span></span> 
- <span data-ttu-id="484f6-3682">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="484f6-3682">DriverLicenses#</span></span> 
- <span data-ttu-id="484f6-3683">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="484f6-3683">Driver Lic#</span></span> 
- <span data-ttu-id="484f6-3684">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="484f6-3684">Driver Lics#</span></span> 
- <span data-ttu-id="484f6-3685">Driver License#</span><span class="sxs-lookup"><span data-stu-id="484f6-3685">Driver License#</span></span> 
- <span data-ttu-id="484f6-3686">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="484f6-3686">Driver Licenses#</span></span> 
- <span data-ttu-id="484f6-3687">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="484f6-3687">DriversLic#</span></span> 
- <span data-ttu-id="484f6-3688">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="484f6-3688">DriversLics#</span></span> 
- <span data-ttu-id="484f6-3689">DriversLicense#</span><span class="sxs-lookup"><span data-stu-id="484f6-3689">DriversLicense#</span></span> 
- <span data-ttu-id="484f6-3690">DriversLicenses#</span><span class="sxs-lookup"><span data-stu-id="484f6-3690">DriversLicenses#</span></span> 
- <span data-ttu-id="484f6-3691">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="484f6-3691">Drivers Lic#</span></span> 
- <span data-ttu-id="484f6-3692">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="484f6-3692">Drivers Lics#</span></span> 
- <span data-ttu-id="484f6-3693">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="484f6-3693">Drivers License#</span></span> 
- <span data-ttu-id="484f6-3694">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="484f6-3694">Drivers Licenses#</span></span> 
- <span data-ttu-id="484f6-3695">Driver'Lic#</span><span class="sxs-lookup"><span data-stu-id="484f6-3695">Driver'Lic#</span></span> 
- <span data-ttu-id="484f6-3696">Driver'Lics#</span><span class="sxs-lookup"><span data-stu-id="484f6-3696">Driver'Lics#</span></span> 
- <span data-ttu-id="484f6-3697">Driver'License#</span><span class="sxs-lookup"><span data-stu-id="484f6-3697">Driver'License#</span></span> 
- <span data-ttu-id="484f6-3698">Driver'Licenses#</span><span class="sxs-lookup"><span data-stu-id="484f6-3698">Driver'Licenses#</span></span> 
- <span data-ttu-id="484f6-3699">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="484f6-3699">Driver' Lic#</span></span> 
- <span data-ttu-id="484f6-3700">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="484f6-3700">Driver' Lics#</span></span> 
- <span data-ttu-id="484f6-3701">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="484f6-3701">Driver' License#</span></span> 
- <span data-ttu-id="484f6-3702">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="484f6-3702">Driver' Licenses#</span></span> 
- <span data-ttu-id="484f6-3703">Driver'sLic#</span><span class="sxs-lookup"><span data-stu-id="484f6-3703">Driver'sLic#</span></span> 
- <span data-ttu-id="484f6-3704">Driver'sLics#</span><span class="sxs-lookup"><span data-stu-id="484f6-3704">Driver'sLics#</span></span> 
- <span data-ttu-id="484f6-3705">Driver'sLicense#</span><span class="sxs-lookup"><span data-stu-id="484f6-3705">Driver'sLicense#</span></span> 
- <span data-ttu-id="484f6-3706">Driver'sLicenses#</span><span class="sxs-lookup"><span data-stu-id="484f6-3706">Driver'sLicenses#</span></span> 
- <span data-ttu-id="484f6-3707">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="484f6-3707">Driver's Lic#</span></span> 
- <span data-ttu-id="484f6-3708">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="484f6-3708">Driver's Lics#</span></span> 
- <span data-ttu-id="484f6-3709">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="484f6-3709">Driver's License#</span></span> 
- <span data-ttu-id="484f6-3710">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="484f6-3710">Driver's Licenses#</span></span> 
- <span data-ttu-id="484f6-3711">id card#</span><span class="sxs-lookup"><span data-stu-id="484f6-3711">id card#</span></span> 
- <span data-ttu-id="484f6-3712">id cards#</span><span class="sxs-lookup"><span data-stu-id="484f6-3712">id cards#</span></span> 
- <span data-ttu-id="484f6-3713">identification card#</span><span class="sxs-lookup"><span data-stu-id="484f6-3713">identification card#</span></span> 
- <span data-ttu-id="484f6-3714">identification cards#</span><span class="sxs-lookup"><span data-stu-id="484f6-3714">identification cards#</span></span> 


#### <a name="keywordstatenamedriverslicensename"></a><span data-ttu-id="484f6-3715">Keyword_[state_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="484f6-3715">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="484f6-3716">州缩写（例如，“NY”）</span><span class="sxs-lookup"><span data-stu-id="484f6-3716">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="484f6-3717">州名称（例如，“New York”）</span><span class="sxs-lookup"><span data-stu-id="484f6-3717">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="484f6-3718">美国单独的纳税人标识号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="484f6-3718">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="484f6-3719">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-3719">Format</span></span>

<span data-ttu-id="484f6-3720">九个数字，以“9”开头，“7”或“8”作为第四个数字，可以采用空格或短划线格式</span><span class="sxs-lookup"><span data-stu-id="484f6-3720">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-3721">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-3721">Pattern</span></span>

<span data-ttu-id="484f6-3722">格式</span><span class="sxs-lookup"><span data-stu-id="484f6-3722">Formatted:</span></span>
- <span data-ttu-id="484f6-3723">数字“9”</span><span class="sxs-lookup"><span data-stu-id="484f6-3723">The digit "9"</span></span> 
- <span data-ttu-id="484f6-3724">两位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3724">Two digits</span></span> 
- <span data-ttu-id="484f6-3725">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="484f6-3725">A space or dash</span></span> 
- <span data-ttu-id="484f6-3726">“7”或“8”</span><span class="sxs-lookup"><span data-stu-id="484f6-3726">A "7" or "8"</span></span> 
- <span data-ttu-id="484f6-3727">一位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3727">A digit</span></span> 
- <span data-ttu-id="484f6-3728">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="484f6-3728">A space, or dash</span></span> 
- <span data-ttu-id="484f6-3729">四位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3729">Four digits</span></span>

<span data-ttu-id="484f6-3730">纯</span><span class="sxs-lookup"><span data-stu-id="484f6-3730">Unformatted:</span></span>
- <span data-ttu-id="484f6-3731">数字“9”</span><span class="sxs-lookup"><span data-stu-id="484f6-3731">The digit "9"</span></span> 
- <span data-ttu-id="484f6-3732">两位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3732">Two digits</span></span> 
- <span data-ttu-id="484f6-3733">“7”或“8”</span><span class="sxs-lookup"><span data-stu-id="484f6-3733">A "7" or "8"</span></span> 
- <span data-ttu-id="484f6-3734">五位数字</span><span class="sxs-lookup"><span data-stu-id="484f6-3734">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-3735">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-3735">Checksum</span></span>

<span data-ttu-id="484f6-3736">否</span><span class="sxs-lookup"><span data-stu-id="484f6-3736">No</span></span>

### <a name="definition"></a><span data-ttu-id="484f6-3737">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-3737">Definition</span></span>

<span data-ttu-id="484f6-3738">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-3738">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-3739">函数 Func_formatted_itin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3739">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-3740">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="484f6-3740">At least one of the following is true:</span></span>
    - <span data-ttu-id="484f6-3741">找到 Keyword_itin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3741">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="484f6-3742">函数 Func_us_address 找到正确日期格式的地址。</span><span class="sxs-lookup"><span data-stu-id="484f6-3742">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="484f6-3743">函数 Func_us_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="484f6-3743">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="484f6-3744">找到 Keyword_itin_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3744">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="484f6-3745">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-3745">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-3746">函数 Func_unformatted_itin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3746">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-3747">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="484f6-3747">At least one of the following is true:</span></span>
    - <span data-ttu-id="484f6-3748">找到 Keyword_itin_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3748">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="484f6-3749">函数 Func_us_address 找到正确日期格式的地址。</span><span class="sxs-lookup"><span data-stu-id="484f6-3749">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="484f6-3750">函数 Func_us_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="484f6-3750">The function Func_us_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-3751">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-3751">Keywords</span></span>

#### <a name="keyworditin"></a><span data-ttu-id="484f6-3752">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="484f6-3752">Keyword_itin</span></span>

- <span data-ttu-id="484f6-3753">报税</span><span class="sxs-lookup"><span data-stu-id="484f6-3753">taxpayer</span></span> 
- <span data-ttu-id="484f6-3754">tax id</span><span class="sxs-lookup"><span data-stu-id="484f6-3754">tax id</span></span> 
- <span data-ttu-id="484f6-3755">tax identification</span><span class="sxs-lookup"><span data-stu-id="484f6-3755">tax identification</span></span> 
- <span data-ttu-id="484f6-3756">itin</span><span class="sxs-lookup"><span data-stu-id="484f6-3756">itin</span></span> 
- <span data-ttu-id="484f6-3757">ssn</span><span class="sxs-lookup"><span data-stu-id="484f6-3757">ssn</span></span> 
- <span data-ttu-id="484f6-3758">锡</span><span class="sxs-lookup"><span data-stu-id="484f6-3758">tin</span></span> 
- <span data-ttu-id="484f6-3759">social security</span><span class="sxs-lookup"><span data-stu-id="484f6-3759">social security</span></span> 
- <span data-ttu-id="484f6-3760">tax payer</span><span class="sxs-lookup"><span data-stu-id="484f6-3760">tax payer</span></span> 
- <span data-ttu-id="484f6-3761">itins</span><span class="sxs-lookup"><span data-stu-id="484f6-3761">itins</span></span> 
- <span data-ttu-id="484f6-3762">taxid</span><span class="sxs-lookup"><span data-stu-id="484f6-3762">taxid</span></span> 
- <span data-ttu-id="484f6-3763">individual taxpayer</span><span class="sxs-lookup"><span data-stu-id="484f6-3763">individual taxpayer</span></span> 

#### <a name="keyworditincollaborative"></a><span data-ttu-id="484f6-3764">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="484f6-3764">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="484f6-3765">许可证</span><span class="sxs-lookup"><span data-stu-id="484f6-3765">License</span></span> 
- <span data-ttu-id="484f6-3766">通讯</span><span class="sxs-lookup"><span data-stu-id="484f6-3766">DL</span></span> 
- <span data-ttu-id="484f6-3767">DOB</span><span class="sxs-lookup"><span data-stu-id="484f6-3767">DOB</span></span> 
- <span data-ttu-id="484f6-3768">出生日期</span><span class="sxs-lookup"><span data-stu-id="484f6-3768">Birthdate</span></span> 
- <span data-ttu-id="484f6-3769">生日</span><span class="sxs-lookup"><span data-stu-id="484f6-3769">Birthday</span></span> 
- <span data-ttu-id="484f6-3770">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="484f6-3770">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="484f6-3771">美国社会保险号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="484f6-3771">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="484f6-3772">Format</span><span class="sxs-lookup"><span data-stu-id="484f6-3772">Format</span></span>

<span data-ttu-id="484f6-3773">9 个数字，可以是格式化模式，也可以是非格式化模式</span><span class="sxs-lookup"><span data-stu-id="484f6-3773">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="484f6-3774">如果在 2011 年中旬前发布，则 SSN 具有强格式，即数字的某部分必须介于某个有效的范围中（但是没有校验和）。</span><span class="sxs-lookup"><span data-stu-id="484f6-3774">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="484f6-3775">模式</span><span class="sxs-lookup"><span data-stu-id="484f6-3775">Pattern</span></span>

<span data-ttu-id="484f6-3776">四种不同模式中的 SSN 的四种函数外观：</span><span class="sxs-lookup"><span data-stu-id="484f6-3776">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="484f6-3777">Func_ssn 查找具有 2011 年以前使用短划线或空格格式化的强格式的 SSN（ddd-dd-dddd 或 ddd dd dddd）</span><span class="sxs-lookup"><span data-stu-id="484f6-3777">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="484f6-3778">Func_unformatted_ssn 查找具有 2011 年以前未格式化为 9 个连续数字的强格式的 SSN (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="484f6-3778">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="484f6-3779">Func_randomized_formatted_ssn 查找 2011 年后使用短划线或空格（ddd-dd-dddd 或 ddd dd dddd）格式化的 SSN</span><span class="sxs-lookup"><span data-stu-id="484f6-3779">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="484f6-3780">Func_randomized_unformatted_ssn 查找 2011 年后未格式化为 9 个连续数字 (ddddddddd) 的 SSN</span><span class="sxs-lookup"><span data-stu-id="484f6-3780">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="484f6-3781">校验和</span><span class="sxs-lookup"><span data-stu-id="484f6-3781">Checksum</span></span>

<span data-ttu-id="484f6-3782">否</span><span class="sxs-lookup"><span data-stu-id="484f6-3782">No</span></span>


### <a name="definition"></a><span data-ttu-id="484f6-3783">定义</span><span class="sxs-lookup"><span data-stu-id="484f6-3783">Definition</span></span>

<span data-ttu-id="484f6-3784">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-3784">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-3785">函数 Func_ssn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3785">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-3786">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3786">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="484f6-3787">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-3787">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-3788">函数 Func_unformatted_ssn 查找与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3788">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-3789">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3789">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="484f6-3790">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-3790">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-3791">函数 Func_randomized_formatted_ssn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3791">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-3792">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3792">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="484f6-3793">函数 Func_ssn 未找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3793">The function Func_ssn does not find content that matches the pattern.</span></span>

<span data-ttu-id="484f6-3794">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 55% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="484f6-3794">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="484f6-3795">函数 Func_randomized_unformatted_ssn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3795">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="484f6-3796">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="484f6-3796">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="484f6-3797">函数 Func_unformatted_ssn 未找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="484f6-3797">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="484f6-3798">关键字</span><span class="sxs-lookup"><span data-stu-id="484f6-3798">Keywords</span></span>

#### <a name="keywordssn"></a><span data-ttu-id="484f6-3799">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="484f6-3799">Keyword_ssn</span></span>

- <span data-ttu-id="484f6-3800">Social Security</span><span class="sxs-lookup"><span data-stu-id="484f6-3800">Social Security</span></span> 
- <span data-ttu-id="484f6-3801">Social Security#</span><span class="sxs-lookup"><span data-stu-id="484f6-3801">Social Security#</span></span> 
- <span data-ttu-id="484f6-3802">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="484f6-3802">Soc Sec</span></span> 
- <span data-ttu-id="484f6-3803">SSN</span><span class="sxs-lookup"><span data-stu-id="484f6-3803">SSN</span></span> 
- <span data-ttu-id="484f6-3804">SSN</span><span class="sxs-lookup"><span data-stu-id="484f6-3804">SSNS</span></span> 
- <span data-ttu-id="484f6-3805">SSN</span><span class="sxs-lookup"><span data-stu-id="484f6-3805">SSN#</span></span> 
- <span data-ttu-id="484f6-3806">SS</span><span class="sxs-lookup"><span data-stu-id="484f6-3806">SS#</span></span> 
- <span data-ttu-id="484f6-3807">SSID</span><span class="sxs-lookup"><span data-stu-id="484f6-3807">SSID</span></span> 
   

