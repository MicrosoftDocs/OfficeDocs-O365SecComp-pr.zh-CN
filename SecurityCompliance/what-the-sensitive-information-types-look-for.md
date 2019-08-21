---
title: 使用敏感信息类型查找什么
ms.author: chrfox
author: chrfox
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
ms.openlocfilehash: d486510c35aaf147e6d63e28d1df36ef689e3975
ms.sourcegitcommit: a5a7e43822336ed18d8f5879167766686cf6b2a3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2019
ms.locfileid: "36478251"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="d7f91-104">使用敏感信息类型查找什么</span><span class="sxs-lookup"><span data-stu-id="d7f91-104">What the sensitive information types look for</span></span>

<span data-ttu-id="d7f91-105">Office 365 安全&amp;合规中心中的数据丢失防护 (DLP) 包括许多可供您在 DLP 策略中使用的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="d7f91-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="d7f91-106">本主题列出了所有这些敏感信息类型，并显示 DLP 策略在检测到每种类型时查找的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="d7f91-107">敏感信息类型通过正则表达式或函数可以识别的模式定义。</span><span class="sxs-lookup"><span data-stu-id="d7f91-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="d7f91-108">此外，关键字和校验和等确凿的证据可用于识别敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="d7f91-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="d7f91-109">可信度和相似度也会在评估过程中使用。</span><span class="sxs-lookup"><span data-stu-id="d7f91-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="d7f91-110">ABA 银行代号</span><span class="sxs-lookup"><span data-stu-id="d7f91-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-111">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-111">Format</span></span>

<span data-ttu-id="d7f91-112">9 个数字，可以是格式化模式，也可以是非格式化模式 </span><span class="sxs-lookup"><span data-stu-id="d7f91-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-113">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-113">Pattern</span></span>

<span data-ttu-id="d7f91-114">格式</span><span class="sxs-lookup"><span data-stu-id="d7f91-114">Formatted:</span></span>
- <span data-ttu-id="d7f91-115">四个数字，以 0、 1、 2、 3、 6、 7 或 8 开头</span><span class="sxs-lookup"><span data-stu-id="d7f91-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="d7f91-116">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="d7f91-116">A hyphen</span></span>
- <span data-ttu-id="d7f91-117">四个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-117">Four digits</span></span>
- <span data-ttu-id="d7f91-118">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="d7f91-118">A hyphen</span></span>
- <span data-ttu-id="d7f91-119">一个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-119">A digit</span></span>

<span data-ttu-id="d7f91-120">无格式: 9 个连续的数字, 以0、1、2、3、6、7或8开头</span><span class="sxs-lookup"><span data-stu-id="d7f91-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="d7f91-121">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-121">Checksum</span></span>

<span data-ttu-id="d7f91-122">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-123">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-123">Definition</span></span>

<span data-ttu-id="d7f91-124">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-125">函数 Func_aba_routing 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-126">找到 Keyword_ABA_Routing 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```xml
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="d7f91-127">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-127">Keywords</span></span>

#### <a name="keyword_aba_routing"></a><span data-ttu-id="d7f91-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="d7f91-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="d7f91-129">aba</span><span class="sxs-lookup"><span data-stu-id="d7f91-129">aba</span></span>
- <span data-ttu-id="d7f91-130">aba #</span><span class="sxs-lookup"><span data-stu-id="d7f91-130">aba #</span></span>
- <span data-ttu-id="d7f91-131">aba routing #</span><span class="sxs-lookup"><span data-stu-id="d7f91-131">aba routing #</span></span>
- <span data-ttu-id="d7f91-132">aba routing number</span><span class="sxs-lookup"><span data-stu-id="d7f91-132">aba routing number</span></span>
- <span data-ttu-id="d7f91-133">aba#</span><span class="sxs-lookup"><span data-stu-id="d7f91-133">aba#</span></span>
- <span data-ttu-id="d7f91-134">abarouting#</span><span class="sxs-lookup"><span data-stu-id="d7f91-134">abarouting#</span></span>
- <span data-ttu-id="d7f91-135">aba number</span><span class="sxs-lookup"><span data-stu-id="d7f91-135">aba number</span></span>
- <span data-ttu-id="d7f91-136">abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="d7f91-136">abaroutingnumber</span></span>
- <span data-ttu-id="d7f91-137">american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="d7f91-137">american bank association routing #</span></span>
- <span data-ttu-id="d7f91-138">american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="d7f91-138">american bank association routing number</span></span>
- <span data-ttu-id="d7f91-139">americanbankassociationrouting#</span><span class="sxs-lookup"><span data-stu-id="d7f91-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="d7f91-140">americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="d7f91-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="d7f91-141">bank routing number</span><span class="sxs-lookup"><span data-stu-id="d7f91-141">bank routing number</span></span>
- <span data-ttu-id="d7f91-142">bankrouting#</span><span class="sxs-lookup"><span data-stu-id="d7f91-142">bankrouting#</span></span>
- <span data-ttu-id="d7f91-143">bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="d7f91-143">bankroutingnumber</span></span>
- <span data-ttu-id="d7f91-144">routing transit number</span><span class="sxs-lookup"><span data-stu-id="d7f91-144">routing transit number</span></span>
- <span data-ttu-id="d7f91-145">RTN</span><span class="sxs-lookup"><span data-stu-id="d7f91-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="d7f91-146">阿根廷国家身份证 (DNI) 号</span><span class="sxs-lookup"><span data-stu-id="d7f91-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-147">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-147">Format</span></span>

<span data-ttu-id="d7f91-148">八个数字，用点分隔</span><span class="sxs-lookup"><span data-stu-id="d7f91-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-149">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-149">Pattern</span></span>

<span data-ttu-id="d7f91-150">八个数字：</span><span class="sxs-lookup"><span data-stu-id="d7f91-150">Eight digits:</span></span>
- <span data-ttu-id="d7f91-151">两个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-151">Two digits</span></span>
- <span data-ttu-id="d7f91-152">一个点 </span><span class="sxs-lookup"><span data-stu-id="d7f91-152">A period</span></span>
- <span data-ttu-id="d7f91-153">三个数字 </span><span class="sxs-lookup"><span data-stu-id="d7f91-153">Three digits</span></span>
- <span data-ttu-id="d7f91-154">一个点 </span><span class="sxs-lookup"><span data-stu-id="d7f91-154">A period</span></span>
- <span data-ttu-id="d7f91-155">三位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-156">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-156">Checksum</span></span>

<span data-ttu-id="d7f91-157">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-158">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-158">Definition</span></span>

<span data-ttu-id="d7f91-159">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-160">正则表达式 Regex_argentina_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-161">找到 Keyword_argentina_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-162">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-162">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="d7f91-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="d7f91-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="d7f91-164">Argentina National Identity number</span><span class="sxs-lookup"><span data-stu-id="d7f91-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="d7f91-165">标识</span><span class="sxs-lookup"><span data-stu-id="d7f91-165">Identity</span></span> 
- <span data-ttu-id="d7f91-166">标识国家/地区身份卡片</span><span class="sxs-lookup"><span data-stu-id="d7f91-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="d7f91-167">DNI</span><span class="sxs-lookup"><span data-stu-id="d7f91-167">DNI</span></span> 
- <span data-ttu-id="d7f91-168">个人的网络国家注册表</span><span class="sxs-lookup"><span data-stu-id="d7f91-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="d7f91-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="d7f91-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="d7f91-170">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="d7f91-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="d7f91-171">Identidad</span><span class="sxs-lookup"><span data-stu-id="d7f91-171">Identidad</span></span> 
- <span data-ttu-id="d7f91-172">Identificación</span><span class="sxs-lookup"><span data-stu-id="d7f91-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="d7f91-173">澳大利亚银行帐号</span><span class="sxs-lookup"><span data-stu-id="d7f91-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-174">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-174">Format</span></span>

<span data-ttu-id="d7f91-175">6-10 个数字，带或不带 BSB 号码 </span><span class="sxs-lookup"><span data-stu-id="d7f91-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-176">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-176">Pattern</span></span>

<span data-ttu-id="d7f91-177">帐号为 6-10 个数字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="d7f91-178">澳大利亚银行州级分部编号：</span><span class="sxs-lookup"><span data-stu-id="d7f91-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="d7f91-179">三个数字 </span><span class="sxs-lookup"><span data-stu-id="d7f91-179">Three digits</span></span> 
- <span data-ttu-id="d7f91-180">连字符</span><span class="sxs-lookup"><span data-stu-id="d7f91-180">A hyphen</span></span> 
- <span data-ttu-id="d7f91-181">三位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-182">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-182">Checksum</span></span>

<span data-ttu-id="d7f91-183">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-184">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-184">Definition</span></span>

<span data-ttu-id="d7f91-185">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-186">正则表达式 Regex_australia_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="d7f91-187">找到 Keyword_australia_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="d7f91-188">正则表达式 Regex_australia_bank_account_number_bsb 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="d7f91-189">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-190">正则表达式 Regex_australia_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="d7f91-191">找到 Keyword_australia_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-192">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-192">Keywords</span></span>

#### <a name="keyword_australia_bank_account_number"></a><span data-ttu-id="d7f91-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="d7f91-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="d7f91-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="d7f91-194">swift bank code</span></span>
- <span data-ttu-id="d7f91-195">correspondent bank</span><span class="sxs-lookup"><span data-stu-id="d7f91-195">correspondent bank</span></span>
- <span data-ttu-id="d7f91-196">base currency</span><span class="sxs-lookup"><span data-stu-id="d7f91-196">base currency</span></span>
- <span data-ttu-id="d7f91-197">usa account</span><span class="sxs-lookup"><span data-stu-id="d7f91-197">usa account</span></span>
- <span data-ttu-id="d7f91-198">holder address</span><span class="sxs-lookup"><span data-stu-id="d7f91-198">holder address</span></span>
- <span data-ttu-id="d7f91-199">bank address</span><span class="sxs-lookup"><span data-stu-id="d7f91-199">bank address</span></span>
- <span data-ttu-id="d7f91-200">information account</span><span class="sxs-lookup"><span data-stu-id="d7f91-200">information account</span></span>
- <span data-ttu-id="d7f91-201">fund transfers</span><span class="sxs-lookup"><span data-stu-id="d7f91-201">fund transfers</span></span>
- <span data-ttu-id="d7f91-202">bank charges</span><span class="sxs-lookup"><span data-stu-id="d7f91-202">bank charges</span></span>
- <span data-ttu-id="d7f91-203">bank details</span><span class="sxs-lookup"><span data-stu-id="d7f91-203">bank details</span></span>
- <span data-ttu-id="d7f91-204">banking information</span><span class="sxs-lookup"><span data-stu-id="d7f91-204">banking information</span></span>
- <span data-ttu-id="d7f91-205">full names</span><span class="sxs-lookup"><span data-stu-id="d7f91-205">full names</span></span>
- <span data-ttu-id="d7f91-206">iaea</span><span class="sxs-lookup"><span data-stu-id="d7f91-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="d7f91-207">澳大利亚驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-208">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-208">Format</span></span>

<span data-ttu-id="d7f91-209">九个字母和数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-210">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-210">Pattern</span></span>

<span data-ttu-id="d7f91-211">九个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="d7f91-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="d7f91-212">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="d7f91-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="d7f91-213">两位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-213">Two digits</span></span> 
- <span data-ttu-id="d7f91-214">五位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="d7f91-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="d7f91-215">OR</span><span class="sxs-lookup"><span data-stu-id="d7f91-215">OR</span></span>

- <span data-ttu-id="d7f91-216">1-2 个可选字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="d7f91-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="d7f91-217">4-9 位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-217">4-9 digits</span></span>

<span data-ttu-id="d7f91-218">OR</span><span class="sxs-lookup"><span data-stu-id="d7f91-218">OR</span></span>

- <span data-ttu-id="d7f91-219">九个数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="d7f91-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-220">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-220">Checksum</span></span>

<span data-ttu-id="d7f91-221">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-222">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-222">Definition</span></span>

<span data-ttu-id="d7f91-223">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-224">正则表达式 Regex_australia_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-225">找到 Keyword_australia_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="d7f91-226">未找到 Keyword_australia_drivers_license_number_exclusions 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-227">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-227">Keywords</span></span>

#### <a name="keyword_australia_drivers_license_number"></a><span data-ttu-id="d7f91-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="d7f91-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="d7f91-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="d7f91-229">international driving permits</span></span>
- <span data-ttu-id="d7f91-230">australian automobile association</span><span class="sxs-lookup"><span data-stu-id="d7f91-230">australian automobile association</span></span>
- <span data-ttu-id="d7f91-231">international driving permit</span><span class="sxs-lookup"><span data-stu-id="d7f91-231">international driving permit</span></span>
- <span data-ttu-id="d7f91-232">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="d7f91-232">DriverLicence</span></span>
- <span data-ttu-id="d7f91-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="d7f91-233">DriverLicences</span></span>
- <span data-ttu-id="d7f91-234">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="d7f91-234">Driver Lic</span></span>
- <span data-ttu-id="d7f91-235">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="d7f91-235">Driver Licence</span></span>
- <span data-ttu-id="d7f91-236">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="d7f91-236">Driver Licences</span></span>
- <span data-ttu-id="d7f91-237">DriversLic</span><span class="sxs-lookup"><span data-stu-id="d7f91-237">DriversLic</span></span>
- <span data-ttu-id="d7f91-238">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="d7f91-238">DriversLicence</span></span>
- <span data-ttu-id="d7f91-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="d7f91-239">DriversLicences</span></span>
- <span data-ttu-id="d7f91-240">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="d7f91-240">Drivers Lic</span></span>
- <span data-ttu-id="d7f91-241">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="d7f91-241">Drivers Lics</span></span>
- <span data-ttu-id="d7f91-242">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="d7f91-242">Drivers Licence</span></span>
- <span data-ttu-id="d7f91-243">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="d7f91-243">Drivers Licences</span></span>
- <span data-ttu-id="d7f91-244">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="d7f91-244">Driver'Lic</span></span>
- <span data-ttu-id="d7f91-245">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="d7f91-245">Driver'Lics</span></span>
- <span data-ttu-id="d7f91-246">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="d7f91-246">Driver'Licence</span></span>
- <span data-ttu-id="d7f91-247">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="d7f91-247">Driver'Licences</span></span>
- <span data-ttu-id="d7f91-248">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="d7f91-248">Driver' Lic</span></span>
- <span data-ttu-id="d7f91-249">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="d7f91-249">Driver' Lics</span></span>
- <span data-ttu-id="d7f91-250">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="d7f91-250">Driver' Licence</span></span>
- <span data-ttu-id="d7f91-251">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="d7f91-251">Driver' Licences</span></span>
- <span data-ttu-id="d7f91-252">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="d7f91-252">Driver'sLic</span></span>
- <span data-ttu-id="d7f91-253">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="d7f91-253">Driver'sLics</span></span>
- <span data-ttu-id="d7f91-254">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="d7f91-254">Driver'sLicence</span></span>
- <span data-ttu-id="d7f91-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="d7f91-255">Driver'sLicences</span></span>
- <span data-ttu-id="d7f91-256">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="d7f91-256">Driver's Lic</span></span>
- <span data-ttu-id="d7f91-257">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="d7f91-257">Driver's Lics</span></span>
- <span data-ttu-id="d7f91-258">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="d7f91-258">Driver's Licence</span></span>
- <span data-ttu-id="d7f91-259">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="d7f91-259">Driver's Licences</span></span>
- <span data-ttu-id="d7f91-260">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="d7f91-260">DriverLic#</span></span>
- <span data-ttu-id="d7f91-261">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="d7f91-261">DriverLics#</span></span>
- <span data-ttu-id="d7f91-262">DriverLicence#</span><span class="sxs-lookup"><span data-stu-id="d7f91-262">DriverLicence#</span></span>
- <span data-ttu-id="d7f91-263">DriverLicences#</span><span class="sxs-lookup"><span data-stu-id="d7f91-263">DriverLicences#</span></span>
- <span data-ttu-id="d7f91-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="d7f91-264">Driver Lic#</span></span>
- <span data-ttu-id="d7f91-265">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="d7f91-265">Driver Lics#</span></span>
- <span data-ttu-id="d7f91-266">Driver Licence#</span><span class="sxs-lookup"><span data-stu-id="d7f91-266">Driver Licence#</span></span>
- <span data-ttu-id="d7f91-267">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="d7f91-267">Driver Licences#</span></span>
- <span data-ttu-id="d7f91-268">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="d7f91-268">DriversLic#</span></span>
- <span data-ttu-id="d7f91-269">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="d7f91-269">DriversLics#</span></span>
- <span data-ttu-id="d7f91-270">DriversLicence#</span><span class="sxs-lookup"><span data-stu-id="d7f91-270">DriversLicence#</span></span>
- <span data-ttu-id="d7f91-271">DriversLicences#</span><span class="sxs-lookup"><span data-stu-id="d7f91-271">DriversLicences#</span></span>
- <span data-ttu-id="d7f91-272">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="d7f91-272">Drivers Lic#</span></span>
- <span data-ttu-id="d7f91-273">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="d7f91-273">Drivers Lics#</span></span>
- <span data-ttu-id="d7f91-274">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="d7f91-274">Drivers Licence#</span></span>
- <span data-ttu-id="d7f91-275">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="d7f91-275">Drivers Licences#</span></span>
- <span data-ttu-id="d7f91-276">Driver'Lic#</span><span class="sxs-lookup"><span data-stu-id="d7f91-276">Driver'Lic#</span></span>
- <span data-ttu-id="d7f91-277">Driver'Lics#</span><span class="sxs-lookup"><span data-stu-id="d7f91-277">Driver'Lics#</span></span>
- <span data-ttu-id="d7f91-278">Driver'Licence#</span><span class="sxs-lookup"><span data-stu-id="d7f91-278">Driver'Licence#</span></span>
- <span data-ttu-id="d7f91-279">Driver'Licences#</span><span class="sxs-lookup"><span data-stu-id="d7f91-279">Driver'Licences#</span></span>
- <span data-ttu-id="d7f91-280">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="d7f91-280">Driver' Lic#</span></span>
- <span data-ttu-id="d7f91-281">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="d7f91-281">Driver' Lics#</span></span>
- <span data-ttu-id="d7f91-282">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="d7f91-282">Driver' Licence#</span></span>
- <span data-ttu-id="d7f91-283">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="d7f91-283">Driver' Licences#</span></span>
- <span data-ttu-id="d7f91-284">Driver'sLic#</span><span class="sxs-lookup"><span data-stu-id="d7f91-284">Driver'sLic#</span></span>
- <span data-ttu-id="d7f91-285">Driver'sLics#</span><span class="sxs-lookup"><span data-stu-id="d7f91-285">Driver'sLics#</span></span>
- <span data-ttu-id="d7f91-286">Driver'sLicence#</span><span class="sxs-lookup"><span data-stu-id="d7f91-286">Driver'sLicence#</span></span>
- <span data-ttu-id="d7f91-287">Driver'sLicences#</span><span class="sxs-lookup"><span data-stu-id="d7f91-287">Driver'sLicences#</span></span>
- <span data-ttu-id="d7f91-288">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="d7f91-288">Driver's Lic#</span></span>
- <span data-ttu-id="d7f91-289">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="d7f91-289">Driver's Lics#</span></span>
- <span data-ttu-id="d7f91-290">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="d7f91-290">Driver's Licence#</span></span>
- <span data-ttu-id="d7f91-291">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="d7f91-291">Driver's Licences#</span></span> 

#### <a name="keyword_australia_drivers_license_number_exclusions"></a><span data-ttu-id="d7f91-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="d7f91-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="d7f91-293">aaa</span><span class="sxs-lookup"><span data-stu-id="d7f91-293">aaa</span></span>
- <span data-ttu-id="d7f91-294">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="d7f91-294">DriverLicense</span></span>
- <span data-ttu-id="d7f91-295">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="d7f91-295">DriverLicenses</span></span>
- <span data-ttu-id="d7f91-296">Driver License</span><span class="sxs-lookup"><span data-stu-id="d7f91-296">Driver License</span></span>
- <span data-ttu-id="d7f91-297">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="d7f91-297">Driver Licenses</span></span>
- <span data-ttu-id="d7f91-298">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="d7f91-298">DriversLicense</span></span>
- <span data-ttu-id="d7f91-299">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="d7f91-299">DriversLicenses</span></span>
- <span data-ttu-id="d7f91-300">Drivers License</span><span class="sxs-lookup"><span data-stu-id="d7f91-300">Drivers License</span></span>
- <span data-ttu-id="d7f91-301">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="d7f91-301">Drivers Licenses</span></span>
- <span data-ttu-id="d7f91-302">Driver'License</span><span class="sxs-lookup"><span data-stu-id="d7f91-302">Driver'License</span></span>
- <span data-ttu-id="d7f91-303">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="d7f91-303">Driver'Licenses</span></span>
- <span data-ttu-id="d7f91-304">Driver' License</span><span class="sxs-lookup"><span data-stu-id="d7f91-304">Driver' License</span></span>
- <span data-ttu-id="d7f91-305">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="d7f91-305">Driver' Licenses</span></span>
- <span data-ttu-id="d7f91-306">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="d7f91-306">Driver'sLicense</span></span>
- <span data-ttu-id="d7f91-307">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="d7f91-307">Driver'sLicenses</span></span>
- <span data-ttu-id="d7f91-308">Driver's License</span><span class="sxs-lookup"><span data-stu-id="d7f91-308">Driver's License</span></span>
- <span data-ttu-id="d7f91-309">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="d7f91-309">Driver's Licenses</span></span>
- <span data-ttu-id="d7f91-310">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="d7f91-310">DriverLicense#</span></span>
- <span data-ttu-id="d7f91-311">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="d7f91-311">DriverLicenses#</span></span>
- <span data-ttu-id="d7f91-312">Driver License#</span><span class="sxs-lookup"><span data-stu-id="d7f91-312">Driver License#</span></span>
- <span data-ttu-id="d7f91-313">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="d7f91-313">Driver Licenses#</span></span>
- <span data-ttu-id="d7f91-314">DriversLicense#</span><span class="sxs-lookup"><span data-stu-id="d7f91-314">DriversLicense#</span></span>
- <span data-ttu-id="d7f91-315">DriversLicenses#</span><span class="sxs-lookup"><span data-stu-id="d7f91-315">DriversLicenses#</span></span>
- <span data-ttu-id="d7f91-316">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="d7f91-316">Drivers License#</span></span>
- <span data-ttu-id="d7f91-317">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="d7f91-317">Drivers Licenses#</span></span>
- <span data-ttu-id="d7f91-318">Driver'License#</span><span class="sxs-lookup"><span data-stu-id="d7f91-318">Driver'License#</span></span>
- <span data-ttu-id="d7f91-319">Driver'Licenses#</span><span class="sxs-lookup"><span data-stu-id="d7f91-319">Driver'Licenses#</span></span>
- <span data-ttu-id="d7f91-320">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="d7f91-320">Driver' License#</span></span>
- <span data-ttu-id="d7f91-321">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="d7f91-321">Driver' Licenses#</span></span>
- <span data-ttu-id="d7f91-322">Driver'sLicense#</span><span class="sxs-lookup"><span data-stu-id="d7f91-322">Driver'sLicense#</span></span>
- <span data-ttu-id="d7f91-323">Driver'sLicenses#</span><span class="sxs-lookup"><span data-stu-id="d7f91-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="d7f91-324">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="d7f91-324">Driver's License#</span></span>
- <span data-ttu-id="d7f91-325">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="d7f91-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="d7f91-326">澳大利亚医疗帐号</span><span class="sxs-lookup"><span data-stu-id="d7f91-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-327">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-327">Format</span></span>

<span data-ttu-id="d7f91-328">10-11 个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-329">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-329">Pattern</span></span>

<span data-ttu-id="d7f91-330">10-11 个数字：</span><span class="sxs-lookup"><span data-stu-id="d7f91-330">10-11 digits:</span></span>
- <span data-ttu-id="d7f91-331">第一个数字范围为 2-6</span><span class="sxs-lookup"><span data-stu-id="d7f91-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="d7f91-332">第九个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="d7f91-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="d7f91-333">第十个数字是问题数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="d7f91-334">第十一个数字（可选）是个人号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-335">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-335">Checksum</span></span>

<span data-ttu-id="d7f91-336">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-337">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-337">Definition</span></span>

<span data-ttu-id="d7f91-338">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-339">函数 Func_australian_medical_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-340">找到 Keyword_Australia_Medical_Account_Number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="d7f91-341">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-341">The checksum passes.</span></span>

<span data-ttu-id="d7f91-342">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-343">函数 Func_australian_medical_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-344">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-344">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-345">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-345">Keywords</span></span>

#### <a name="keyword_australia_medical_account_number"></a><span data-ttu-id="d7f91-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="d7f91-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="d7f91-347">bank account details</span></span>
- <span data-ttu-id="d7f91-348">medicare payments</span><span class="sxs-lookup"><span data-stu-id="d7f91-348">medicare payments</span></span>
- <span data-ttu-id="d7f91-349">mortgage account</span><span class="sxs-lookup"><span data-stu-id="d7f91-349">mortgage account</span></span>
- <span data-ttu-id="d7f91-350">bank payments</span><span class="sxs-lookup"><span data-stu-id="d7f91-350">bank payments</span></span>
- <span data-ttu-id="d7f91-351">information branch</span><span class="sxs-lookup"><span data-stu-id="d7f91-351">information branch</span></span>
- <span data-ttu-id="d7f91-352">credit card loan</span><span class="sxs-lookup"><span data-stu-id="d7f91-352">credit card loan</span></span>
- <span data-ttu-id="d7f91-353">department of human services</span><span class="sxs-lookup"><span data-stu-id="d7f91-353">department of human services</span></span>
- <span data-ttu-id="d7f91-354">local service</span><span class="sxs-lookup"><span data-stu-id="d7f91-354">local service</span></span>
- <span data-ttu-id="d7f91-355">medicare</span><span class="sxs-lookup"><span data-stu-id="d7f91-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="d7f91-356">澳大利亚护照号</span><span class="sxs-lookup"><span data-stu-id="d7f91-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-357">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-357">Format</span></span>

<span data-ttu-id="d7f91-358">一个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-359">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-359">Pattern</span></span>

<span data-ttu-id="d7f91-360">一个字母（不区分大小写）后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-361">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-361">Checksum</span></span>

<span data-ttu-id="d7f91-362">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-363">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-363">Definition</span></span>

<span data-ttu-id="d7f91-364">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-365">正则表达式 Regex_australia_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-366">找到来自 Keyword_passport 或 Keyword_australia_passport_number 的关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-367">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-367">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="d7f91-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="d7f91-368">Keyword_passport</span></span>

- <span data-ttu-id="d7f91-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-369">Passport Number</span></span>
- <span data-ttu-id="d7f91-370">Passport No</span><span class="sxs-lookup"><span data-stu-id="d7f91-370">Passport No</span></span>
- <span data-ttu-id="d7f91-371">Passport #</span><span class="sxs-lookup"><span data-stu-id="d7f91-371">Passport #</span></span>
- <span data-ttu-id="d7f91-372">登记卡#</span><span class="sxs-lookup"><span data-stu-id="d7f91-372">Passport#</span></span>
- <span data-ttu-id="d7f91-373">PassportID</span><span class="sxs-lookup"><span data-stu-id="d7f91-373">PassportID</span></span>
- <span data-ttu-id="d7f91-374">Passportno</span><span class="sxs-lookup"><span data-stu-id="d7f91-374">Passportno</span></span>
- <span data-ttu-id="d7f91-375">passportnumber</span><span class="sxs-lookup"><span data-stu-id="d7f91-375">passportnumber</span></span>
- <span data-ttu-id="d7f91-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="d7f91-376">パスポート</span></span>
- <span data-ttu-id="d7f91-377">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="d7f91-377">パスポート番号</span></span>
- <span data-ttu-id="d7f91-378">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="d7f91-378">パスポートのNum</span></span>
- <span data-ttu-id="d7f91-379">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="d7f91-379">パスポート ＃</span></span> 
- <span data-ttu-id="d7f91-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="d7f91-380">Numéro de passeport</span></span>
- <span data-ttu-id="d7f91-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="d7f91-381">Passeport n °</span></span>
- <span data-ttu-id="d7f91-382">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="d7f91-382">Passeport Non</span></span>
- <span data-ttu-id="d7f91-383">Passeport #</span><span class="sxs-lookup"><span data-stu-id="d7f91-383">Passeport #</span></span>
- <span data-ttu-id="d7f91-384">Passeport#</span><span class="sxs-lookup"><span data-stu-id="d7f91-384">Passeport#</span></span>
- <span data-ttu-id="d7f91-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="d7f91-385">PasseportNon</span></span>
- <span data-ttu-id="d7f91-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="d7f91-386">Passeportn °</span></span>

#### <a name="keyword_australia_passport_number"></a><span data-ttu-id="d7f91-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="d7f91-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="d7f91-388">登记卡</span><span class="sxs-lookup"><span data-stu-id="d7f91-388">passport</span></span>
- <span data-ttu-id="d7f91-389">passport details</span><span class="sxs-lookup"><span data-stu-id="d7f91-389">passport details</span></span>
- <span data-ttu-id="d7f91-390">immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="d7f91-390">immigration and citizenship</span></span>
- <span data-ttu-id="d7f91-391">commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="d7f91-391">commonwealth of australia</span></span>
- <span data-ttu-id="d7f91-392">department of immigration</span><span class="sxs-lookup"><span data-stu-id="d7f91-392">department of immigration</span></span>
- <span data-ttu-id="d7f91-393">residential address</span><span class="sxs-lookup"><span data-stu-id="d7f91-393">residential address</span></span>
- <span data-ttu-id="d7f91-394">department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="d7f91-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="d7f91-395">反之</span><span class="sxs-lookup"><span data-stu-id="d7f91-395">visa</span></span>
- <span data-ttu-id="d7f91-396">national identity card</span><span class="sxs-lookup"><span data-stu-id="d7f91-396">national identity card</span></span>
- <span data-ttu-id="d7f91-397">passport number</span><span class="sxs-lookup"><span data-stu-id="d7f91-397">passport number</span></span>
- <span data-ttu-id="d7f91-398">travel document</span><span class="sxs-lookup"><span data-stu-id="d7f91-398">travel document</span></span>
- <span data-ttu-id="d7f91-399">issuing authority</span><span class="sxs-lookup"><span data-stu-id="d7f91-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="d7f91-400">澳大利亚税号</span><span class="sxs-lookup"><span data-stu-id="d7f91-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-401">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-401">Format</span></span>

<span data-ttu-id="d7f91-402">8-9 个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-403">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-403">Pattern</span></span>

<span data-ttu-id="d7f91-404">通常 8-9 位数字，显示中包含空格，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d7f91-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="d7f91-405">三位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-405">Three digits</span></span> 
- <span data-ttu-id="d7f91-406">可选空格</span><span class="sxs-lookup"><span data-stu-id="d7f91-406">An optional space</span></span> 
- <span data-ttu-id="d7f91-407">三位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-407">Three digits</span></span> 
- <span data-ttu-id="d7f91-408">可选空格</span><span class="sxs-lookup"><span data-stu-id="d7f91-408">An optional space</span></span> 
- <span data-ttu-id="d7f91-409">2-3 位数字，最后一位数字是校验位</span><span class="sxs-lookup"><span data-stu-id="d7f91-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-410">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-410">Checksum</span></span>

<span data-ttu-id="d7f91-411">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-412">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-412">Definition</span></span>

<span data-ttu-id="d7f91-413">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-414">函数 Func_australian_tax_file_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-415">未找到 Keyword_Australia_Tax_File_Number 或 Keyword_number_exclusions 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="d7f91-416">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-416">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-417">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-417">Keywords</span></span>

#### <a name="keyword_australia_tax_file_number"></a><span data-ttu-id="d7f91-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="d7f91-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="d7f91-419">australian business number</span></span>
- <span data-ttu-id="d7f91-420">marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="d7f91-420">marginal tax rate</span></span>
- <span data-ttu-id="d7f91-421">medicare levy</span><span class="sxs-lookup"><span data-stu-id="d7f91-421">medicare levy</span></span>
- <span data-ttu-id="d7f91-422">portfolio number</span><span class="sxs-lookup"><span data-stu-id="d7f91-422">portfolio number</span></span>
- <span data-ttu-id="d7f91-423">service veterans</span><span class="sxs-lookup"><span data-stu-id="d7f91-423">service veterans</span></span>
- <span data-ttu-id="d7f91-424">withholding tax</span><span class="sxs-lookup"><span data-stu-id="d7f91-424">withholding tax</span></span>
- <span data-ttu-id="d7f91-425">individual tax return</span><span class="sxs-lookup"><span data-stu-id="d7f91-425">individual tax return</span></span>
- <span data-ttu-id="d7f91-426">tax file number</span><span class="sxs-lookup"><span data-stu-id="d7f91-426">tax file number</span></span>

#### <a name="keyword_number_exclusions"></a><span data-ttu-id="d7f91-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="d7f91-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="d7f91-428">00000000</span><span class="sxs-lookup"><span data-stu-id="d7f91-428">00000000</span></span>
- <span data-ttu-id="d7f91-429">11111111</span><span class="sxs-lookup"><span data-stu-id="d7f91-429">11111111</span></span>
- <span data-ttu-id="d7f91-430">22222222</span><span class="sxs-lookup"><span data-stu-id="d7f91-430">22222222</span></span>
- <span data-ttu-id="d7f91-431">33333333</span><span class="sxs-lookup"><span data-stu-id="d7f91-431">33333333</span></span>
- <span data-ttu-id="d7f91-432">44444444</span><span class="sxs-lookup"><span data-stu-id="d7f91-432">44444444</span></span>
- <span data-ttu-id="d7f91-433">55555555</span><span class="sxs-lookup"><span data-stu-id="d7f91-433">55555555</span></span>
- <span data-ttu-id="d7f91-434">66666666</span><span class="sxs-lookup"><span data-stu-id="d7f91-434">66666666</span></span>
- <span data-ttu-id="d7f91-435">77777777</span><span class="sxs-lookup"><span data-stu-id="d7f91-435">77777777</span></span>
- <span data-ttu-id="d7f91-436">88888888</span><span class="sxs-lookup"><span data-stu-id="d7f91-436">88888888</span></span>
- <span data-ttu-id="d7f91-437">99999999</span><span class="sxs-lookup"><span data-stu-id="d7f91-437">99999999</span></span>
- <span data-ttu-id="d7f91-438">000000000</span><span class="sxs-lookup"><span data-stu-id="d7f91-438">000000000</span></span>
- <span data-ttu-id="d7f91-439">111111111</span><span class="sxs-lookup"><span data-stu-id="d7f91-439">111111111</span></span>
- <span data-ttu-id="d7f91-440">222222222</span><span class="sxs-lookup"><span data-stu-id="d7f91-440">222222222</span></span>
- <span data-ttu-id="d7f91-441">333333333</span><span class="sxs-lookup"><span data-stu-id="d7f91-441">333333333</span></span>
- <span data-ttu-id="d7f91-442">444444444</span><span class="sxs-lookup"><span data-stu-id="d7f91-442">444444444</span></span>
- <span data-ttu-id="d7f91-443">555555555</span><span class="sxs-lookup"><span data-stu-id="d7f91-443">555555555</span></span>
- <span data-ttu-id="d7f91-444">666666666</span><span class="sxs-lookup"><span data-stu-id="d7f91-444">666666666</span></span>
- <span data-ttu-id="d7f91-445">777777777</span><span class="sxs-lookup"><span data-stu-id="d7f91-445">777777777</span></span>
- <span data-ttu-id="d7f91-446">888888888</span><span class="sxs-lookup"><span data-stu-id="d7f91-446">888888888</span></span>
- <span data-ttu-id="d7f91-447">999999999</span><span class="sxs-lookup"><span data-stu-id="d7f91-447">999999999</span></span>
- <span data-ttu-id="d7f91-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="d7f91-448">0000000000</span></span>
- <span data-ttu-id="d7f91-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="d7f91-449">1111111111</span></span>
- <span data-ttu-id="d7f91-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="d7f91-450">2222222222</span></span>
- <span data-ttu-id="d7f91-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="d7f91-451">3333333333</span></span>
- <span data-ttu-id="d7f91-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="d7f91-452">4444444444</span></span>
- <span data-ttu-id="d7f91-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="d7f91-453">5555555555</span></span>
- <span data-ttu-id="d7f91-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="d7f91-454">6666666666</span></span>
- <span data-ttu-id="d7f91-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="d7f91-455">7777777777</span></span>
- <span data-ttu-id="d7f91-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="d7f91-456">8888888888</span></span>
- <span data-ttu-id="d7f91-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="d7f91-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="d7f91-458">Azure DocumentDB 身份验证密钥</span><span class="sxs-lookup"><span data-stu-id="d7f91-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-459">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-459">Format</span></span>

<span data-ttu-id="d7f91-460">字符串 "DocumentDb", 后跟下面模式中所示的字符和字符串。</span><span class="sxs-lookup"><span data-stu-id="d7f91-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-461">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-461">Pattern</span></span>

- <span data-ttu-id="d7f91-462">字符串 "DocumentDb"</span><span class="sxs-lookup"><span data-stu-id="d7f91-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="d7f91-463">介于3-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="d7f91-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="d7f91-464">大于号 (>)、等号 (=)、引号 (") 或撇号 (')</span><span class="sxs-lookup"><span data-stu-id="d7f91-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="d7f91-465">86字母、数字、数字、正斜杠 (/) 或加号 (+) 的任意组合</span><span class="sxs-lookup"><span data-stu-id="d7f91-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="d7f91-466">两个等号 (=)</span><span class="sxs-lookup"><span data-stu-id="d7f91-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-467">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-467">Checksum</span></span>

<span data-ttu-id="d7f91-468">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-469">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-469">Definition</span></span>

<span data-ttu-id="d7f91-470">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-471">正则表达式 CEP_Regex_AzureDocumentDBAuthKey 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-472">正则表达式 CEP_CommonExampleKeywords**未**找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-473">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-473">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="d7f91-474">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="d7f91-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="d7f91-475">(请注意, 从技术上讲, 此敏感信息类型通过使用正则表达式 (而不是关键字列表) 来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="d7f91-476">尚未</span><span class="sxs-lookup"><span data-stu-id="d7f91-476">contoso</span></span>
- <span data-ttu-id="d7f91-477">送交</span><span class="sxs-lookup"><span data-stu-id="d7f91-477">fabrikam</span></span>
- <span data-ttu-id="d7f91-478">罗斯</span><span class="sxs-lookup"><span data-stu-id="d7f91-478">northwind</span></span>
- <span data-ttu-id="d7f91-479">沙盒</span><span class="sxs-lookup"><span data-stu-id="d7f91-479">sandbox</span></span>
- <span data-ttu-id="d7f91-480">onebox</span><span class="sxs-lookup"><span data-stu-id="d7f91-480">onebox</span></span>
- <span data-ttu-id="d7f91-481">localhost</span><span class="sxs-lookup"><span data-stu-id="d7f91-481">localhost</span></span>
- <span data-ttu-id="d7f91-482">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="d7f91-482">127.0.0.1</span></span>
- <span data-ttu-id="d7f91-483">testacs.</span><span class="sxs-lookup"><span data-stu-id="d7f91-483">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="d7f91-484">com</span><span class="sxs-lookup"><span data-stu-id="d7f91-484">com</span></span>
- <span data-ttu-id="d7f91-485">s-int。</span><span class="sxs-lookup"><span data-stu-id="d7f91-485">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="d7f91-486">netmeeting</span><span class="sxs-lookup"><span data-stu-id="d7f91-486">net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="d7f91-487">Azure IAAS 数据库连接字符串和 Azure SQL 连接字符串</span><span class="sxs-lookup"><span data-stu-id="d7f91-487">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-488">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-488">Format</span></span>

<span data-ttu-id="d7f91-489">字符串 "Server"、"server" 或 "data source", 后跟下面模式中所述的字符和字符串, 包括字符串 "cloudapp"。</span><span class="sxs-lookup"><span data-stu-id="d7f91-489">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="d7f91-490">com "或" cloudapp "。</span><span class="sxs-lookup"><span data-stu-id="d7f91-490">com" or "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="d7f91-491">net "或" database。</span><span class="sxs-lookup"><span data-stu-id="d7f91-491">net" or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="d7f91-492">net "和字符串" Password "或" password "或" pwd "。</span><span class="sxs-lookup"><span data-stu-id="d7f91-492">net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-493">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-493">Pattern</span></span>

- <span data-ttu-id="d7f91-494">字符串 "Server"、"server" 或 "data source"</span><span class="sxs-lookup"><span data-stu-id="d7f91-494">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="d7f91-495">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="d7f91-495">0-2 whitespace characters</span></span>
- <span data-ttu-id="d7f91-496">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="d7f91-496">An equal sign (=)</span></span>
- <span data-ttu-id="d7f91-497">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="d7f91-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="d7f91-498">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="d7f91-498">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="d7f91-499">字符串 "cloudapp"。</span><span class="sxs-lookup"><span data-stu-id="d7f91-499">The string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="d7f91-500">com "," cloudapp。</span><span class="sxs-lookup"><span data-stu-id="d7f91-500">com", "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="d7f91-501">net "或" database。</span><span class="sxs-lookup"><span data-stu-id="d7f91-501">net", or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="d7f91-502">netmeeting</span><span class="sxs-lookup"><span data-stu-id="d7f91-502">net"</span></span>
- <span data-ttu-id="d7f91-503">介于1-300 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="d7f91-503">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="d7f91-504">字符串 "Password"、"password" 或 "pwd"</span><span class="sxs-lookup"><span data-stu-id="d7f91-504">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="d7f91-505">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="d7f91-505">0-2 whitespace characters</span></span>
- <span data-ttu-id="d7f91-506">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="d7f91-506">An equal sign (=)</span></span>
- <span data-ttu-id="d7f91-507">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="d7f91-507">0-2 whitespace characters</span></span>
- <span data-ttu-id="d7f91-508">一个或多个不是分号 (;)、引号 (") 或撇号 (') 的字符</span><span class="sxs-lookup"><span data-stu-id="d7f91-508">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="d7f91-509">分号 (;)、引号 (") 或撇号 (')</span><span class="sxs-lookup"><span data-stu-id="d7f91-509">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-510">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-510">Checksum</span></span>

<span data-ttu-id="d7f91-511">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-511">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-512">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-512">Definition</span></span>

<span data-ttu-id="d7f91-513">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-513">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-514">正则表达式 CEP_Regex_AzureConnectionString 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-514">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-515">正则表达式 CEP_CommonExampleKeywords**未**找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-515">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-516">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-516">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="d7f91-517">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="d7f91-517">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="d7f91-518">(请注意, 从技术上讲, 此敏感信息类型通过使用正则表达式 (而不是关键字列表) 来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-518">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="d7f91-519">尚未</span><span class="sxs-lookup"><span data-stu-id="d7f91-519">contoso</span></span>
- <span data-ttu-id="d7f91-520">送交</span><span class="sxs-lookup"><span data-stu-id="d7f91-520">fabrikam</span></span>
- <span data-ttu-id="d7f91-521">罗斯</span><span class="sxs-lookup"><span data-stu-id="d7f91-521">northwind</span></span>
- <span data-ttu-id="d7f91-522">沙盒</span><span class="sxs-lookup"><span data-stu-id="d7f91-522">sandbox</span></span>
- <span data-ttu-id="d7f91-523">onebox</span><span class="sxs-lookup"><span data-stu-id="d7f91-523">onebox</span></span>
- <span data-ttu-id="d7f91-524">localhost</span><span class="sxs-lookup"><span data-stu-id="d7f91-524">localhost</span></span>
- <span data-ttu-id="d7f91-525">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="d7f91-525">127.0.0.1</span></span>
- <span data-ttu-id="d7f91-526">testacs.</span><span class="sxs-lookup"><span data-stu-id="d7f91-526">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="d7f91-527">com</span><span class="sxs-lookup"><span data-stu-id="d7f91-527">com</span></span>
- <span data-ttu-id="d7f91-528">s-int。</span><span class="sxs-lookup"><span data-stu-id="d7f91-528">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="d7f91-529">netmeeting</span><span class="sxs-lookup"><span data-stu-id="d7f91-529">net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="d7f91-530">Azure IoT 连接字符串</span><span class="sxs-lookup"><span data-stu-id="d7f91-530">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-531">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-531">Format</span></span>

<span data-ttu-id="d7f91-532">字符串 "HostName", 后跟下面模式中所示的字符和字符串, 包括字符串 "azure 设备"。</span><span class="sxs-lookup"><span data-stu-id="d7f91-532">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="d7f91-533">net "和" SharedAccessKey "。</span><span class="sxs-lookup"><span data-stu-id="d7f91-533">net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-534">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-534">Pattern</span></span>

- <span data-ttu-id="d7f91-535">字符串 "HostName"</span><span class="sxs-lookup"><span data-stu-id="d7f91-535">The string "HostName"</span></span>
- <span data-ttu-id="d7f91-536">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="d7f91-536">0-2 whitespace characters</span></span>
- <span data-ttu-id="d7f91-537">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="d7f91-537">An equal sign (=)</span></span>
- <span data-ttu-id="d7f91-538">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="d7f91-538">0-2 whitespace characters</span></span>
- <span data-ttu-id="d7f91-539">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="d7f91-539">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="d7f91-540">字符串 "azure 设备。</span><span class="sxs-lookup"><span data-stu-id="d7f91-540">The string "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="d7f91-541">netmeeting</span><span class="sxs-lookup"><span data-stu-id="d7f91-541">net"</span></span>
- <span data-ttu-id="d7f91-542">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="d7f91-542">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="d7f91-543">字符串 "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="d7f91-543">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="d7f91-544">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="d7f91-544">0-2 whitespace characters</span></span>
- <span data-ttu-id="d7f91-545">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="d7f91-545">An equal sign (=)</span></span>
- <span data-ttu-id="d7f91-546">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="d7f91-546">0-2 whitespace characters</span></span>
- <span data-ttu-id="d7f91-547">43字母、数字、数字、正斜杠 (/) 或加号 (+) 的任意组合</span><span class="sxs-lookup"><span data-stu-id="d7f91-547">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="d7f91-548">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="d7f91-548">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-549">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-549">Checksum</span></span>

<span data-ttu-id="d7f91-550">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-550">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-551">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-551">Definition</span></span>

<span data-ttu-id="d7f91-552">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-552">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-553">正则表达式 CEP_Regex_AzureIoTConnectionString 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-553">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-554">正则表达式 CEP_CommonExampleKeywords**未**找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-554">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-555">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-555">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="d7f91-556">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="d7f91-556">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="d7f91-557">(请注意, 从技术上讲, 此敏感信息类型通过使用正则表达式 (而不是关键字列表) 来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-557">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="d7f91-558">尚未</span><span class="sxs-lookup"><span data-stu-id="d7f91-558">contoso</span></span>
- <span data-ttu-id="d7f91-559">送交</span><span class="sxs-lookup"><span data-stu-id="d7f91-559">fabrikam</span></span>
- <span data-ttu-id="d7f91-560">罗斯</span><span class="sxs-lookup"><span data-stu-id="d7f91-560">northwind</span></span>
- <span data-ttu-id="d7f91-561">沙盒</span><span class="sxs-lookup"><span data-stu-id="d7f91-561">sandbox</span></span>
- <span data-ttu-id="d7f91-562">onebox</span><span class="sxs-lookup"><span data-stu-id="d7f91-562">onebox</span></span>
- <span data-ttu-id="d7f91-563">localhost</span><span class="sxs-lookup"><span data-stu-id="d7f91-563">localhost</span></span>
- <span data-ttu-id="d7f91-564">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="d7f91-564">127.0.0.1</span></span>
- <span data-ttu-id="d7f91-565">testacs.</span><span class="sxs-lookup"><span data-stu-id="d7f91-565">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="d7f91-566">com</span><span class="sxs-lookup"><span data-stu-id="d7f91-566">com</span></span>
- <span data-ttu-id="d7f91-567">s-int。</span><span class="sxs-lookup"><span data-stu-id="d7f91-567">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="d7f91-568">netmeeting</span><span class="sxs-lookup"><span data-stu-id="d7f91-568">net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="d7f91-569">Azure 发布设置密码</span><span class="sxs-lookup"><span data-stu-id="d7f91-569">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-570">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-570">Format</span></span>

<span data-ttu-id="d7f91-571">字符串 "userpwd =", 后跟一个字母数字字符串。</span><span class="sxs-lookup"><span data-stu-id="d7f91-571">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-572">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-572">Pattern</span></span>

- <span data-ttu-id="d7f91-573">字符串 "userpwd ="</span><span class="sxs-lookup"><span data-stu-id="d7f91-573">The string "userpwd="</span></span>
- <span data-ttu-id="d7f91-574">任何60小写字母或数字的组合</span><span class="sxs-lookup"><span data-stu-id="d7f91-574">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="d7f91-575">一个引号 (")</span><span class="sxs-lookup"><span data-stu-id="d7f91-575">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-576">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-576">Checksum</span></span>

<span data-ttu-id="d7f91-577">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-577">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-578">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-578">Definition</span></span>

<span data-ttu-id="d7f91-579">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-580">正则表达式 CEP_Regex_AzurePublishSettingPasswords 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-580">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-581">正则表达式 CEP_CommonExampleKeywords**未**找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-581">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-582">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-582">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="d7f91-583">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="d7f91-583">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="d7f91-584">(请注意, 从技术上讲, 此敏感信息类型通过使用正则表达式 (而不是关键字列表) 来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-584">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="d7f91-585">尚未</span><span class="sxs-lookup"><span data-stu-id="d7f91-585">contoso</span></span>
- <span data-ttu-id="d7f91-586">送交</span><span class="sxs-lookup"><span data-stu-id="d7f91-586">fabrikam</span></span>
- <span data-ttu-id="d7f91-587">罗斯</span><span class="sxs-lookup"><span data-stu-id="d7f91-587">northwind</span></span>
- <span data-ttu-id="d7f91-588">沙盒</span><span class="sxs-lookup"><span data-stu-id="d7f91-588">sandbox</span></span>
- <span data-ttu-id="d7f91-589">onebox</span><span class="sxs-lookup"><span data-stu-id="d7f91-589">onebox</span></span>
- <span data-ttu-id="d7f91-590">localhost</span><span class="sxs-lookup"><span data-stu-id="d7f91-590">localhost</span></span>
- <span data-ttu-id="d7f91-591">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="d7f91-591">127.0.0.1</span></span>
- <span data-ttu-id="d7f91-592">testacs.</span><span class="sxs-lookup"><span data-stu-id="d7f91-592">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="d7f91-593">com</span><span class="sxs-lookup"><span data-stu-id="d7f91-593">com</span></span>
- <span data-ttu-id="d7f91-594">s-int。</span><span class="sxs-lookup"><span data-stu-id="d7f91-594">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="d7f91-595">netmeeting</span><span class="sxs-lookup"><span data-stu-id="d7f91-595">net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="d7f91-596">Azure Redis 缓存连接字符串</span><span class="sxs-lookup"><span data-stu-id="d7f91-596">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-597">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-597">Format</span></span>

<span data-ttu-id="d7f91-598">字符串 "redis"。</span><span class="sxs-lookup"><span data-stu-id="d7f91-598">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="d7f91-599">net ", 后跟下面的模式中所述的字符和字符串, 包括字符串" password "或" pwd "。</span><span class="sxs-lookup"><span data-stu-id="d7f91-599">net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-600">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-600">Pattern</span></span>

- <span data-ttu-id="d7f91-601">字符串 "redis"。</span><span class="sxs-lookup"><span data-stu-id="d7f91-601">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="d7f91-602">netmeeting</span><span class="sxs-lookup"><span data-stu-id="d7f91-602">net"</span></span>
- <span data-ttu-id="d7f91-603">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="d7f91-603">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="d7f91-604">字符串 "password" 或 "pwd"</span><span class="sxs-lookup"><span data-stu-id="d7f91-604">The string "password" or "pwd"</span></span>
- <span data-ttu-id="d7f91-605">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="d7f91-605">0-2 whitespace characters</span></span>
- <span data-ttu-id="d7f91-606">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="d7f91-606">An equal sign (=)</span></span>
- <span data-ttu-id="d7f91-607">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="d7f91-607">0-2 whitespace characters</span></span>
- <span data-ttu-id="d7f91-608">43个字符的任意组合, 这些字符为小写字母、数字、斜杠 (/) 或加号 (+)</span><span class="sxs-lookup"><span data-stu-id="d7f91-608">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="d7f91-609">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="d7f91-609">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-610">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-610">Checksum</span></span>

<span data-ttu-id="d7f91-611">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-611">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-612">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-612">Definition</span></span>

<span data-ttu-id="d7f91-613">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-614">正则表达式 CEP_Regex_AzureRedisCacheConnectionString 找到与该模式匹配的内容。。</span><span class="sxs-lookup"><span data-stu-id="d7f91-614">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="d7f91-615">正则表达式 CEP_CommonExampleKeywords**未**找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-615">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-616">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-616">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="d7f91-617">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="d7f91-617">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="d7f91-618">(请注意, 从技术上讲, 此敏感信息类型通过使用正则表达式 (而不是关键字列表) 来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-618">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="d7f91-619">尚未</span><span class="sxs-lookup"><span data-stu-id="d7f91-619">contoso</span></span>
- <span data-ttu-id="d7f91-620">送交</span><span class="sxs-lookup"><span data-stu-id="d7f91-620">fabrikam</span></span>
- <span data-ttu-id="d7f91-621">罗斯</span><span class="sxs-lookup"><span data-stu-id="d7f91-621">northwind</span></span>
- <span data-ttu-id="d7f91-622">沙盒</span><span class="sxs-lookup"><span data-stu-id="d7f91-622">sandbox</span></span>
- <span data-ttu-id="d7f91-623">onebox</span><span class="sxs-lookup"><span data-stu-id="d7f91-623">onebox</span></span>
- <span data-ttu-id="d7f91-624">localhost</span><span class="sxs-lookup"><span data-stu-id="d7f91-624">localhost</span></span>
- <span data-ttu-id="d7f91-625">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="d7f91-625">127.0.0.1</span></span>
- <span data-ttu-id="d7f91-626">testacs.</span><span class="sxs-lookup"><span data-stu-id="d7f91-626">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="d7f91-627">com</span><span class="sxs-lookup"><span data-stu-id="d7f91-627">com</span></span>
- <span data-ttu-id="d7f91-628">s-int。</span><span class="sxs-lookup"><span data-stu-id="d7f91-628">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="d7f91-629">netmeeting</span><span class="sxs-lookup"><span data-stu-id="d7f91-629">net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="d7f91-630">Azure SA</span><span class="sxs-lookup"><span data-stu-id="d7f91-630">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-631">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-631">Format</span></span>

<span data-ttu-id="d7f91-632">字符串 "sig", 后跟下面模式中所示的字符和字符串。</span><span class="sxs-lookup"><span data-stu-id="d7f91-632">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-633">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-633">Pattern</span></span>

- <span data-ttu-id="d7f91-634">字符串 "sig"</span><span class="sxs-lookup"><span data-stu-id="d7f91-634">The string "sig"</span></span>
- <span data-ttu-id="d7f91-635">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="d7f91-635">0-2 whitespace characters</span></span>
- <span data-ttu-id="d7f91-636">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="d7f91-636">An equal sign (=)</span></span>
- <span data-ttu-id="d7f91-637">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="d7f91-637">0-2 whitespace characters</span></span>
- <span data-ttu-id="d7f91-638">介于43-53 个字符和小写字母、数字或百分比符号 (%) 之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="d7f91-638">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="d7f91-639">字符串 "% 3d"</span><span class="sxs-lookup"><span data-stu-id="d7f91-639">The string "%3d"</span></span>
- <span data-ttu-id="d7f91-640">不是字母或大写字符、数字或百分号 (%) 的任何字符</span><span class="sxs-lookup"><span data-stu-id="d7f91-640">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-641">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-641">Checksum</span></span>

<span data-ttu-id="d7f91-642">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-642">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-643">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-643">Definition</span></span>

<span data-ttu-id="d7f91-644">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-644">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-645">正则表达式 CEP_Regex_AzureSAS 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-645">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="d7f91-646">Azure 服务总线连接字符串</span><span class="sxs-lookup"><span data-stu-id="d7f91-646">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-647">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-647">Format</span></span>

<span data-ttu-id="d7f91-648">字符串 "终结点", 后跟下面模式中所示的字符和字符串, 包括字符串 "</span><span class="sxs-lookup"><span data-stu-id="d7f91-648">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="d7f91-649">net "和" SharedAccesKey "。</span><span class="sxs-lookup"><span data-stu-id="d7f91-649">net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-650">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-650">Pattern</span></span>

- <span data-ttu-id="d7f91-651">字符串 "EndPoint"</span><span class="sxs-lookup"><span data-stu-id="d7f91-651">The string "EndPoint"</span></span>
- <span data-ttu-id="d7f91-652">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="d7f91-652">0-2 whitespace characters</span></span>
- <span data-ttu-id="d7f91-653">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="d7f91-653">An equal sign (=)</span></span>
- <span data-ttu-id="d7f91-654">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="d7f91-654">0-2 whitespace characters</span></span>
- <span data-ttu-id="d7f91-655">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="d7f91-655">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="d7f91-656">字符串 "</span><span class="sxs-lookup"><span data-stu-id="d7f91-656">The string "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="d7f91-657">netmeeting</span><span class="sxs-lookup"><span data-stu-id="d7f91-657">net"</span></span>
- <span data-ttu-id="d7f91-658">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="d7f91-658">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="d7f91-659">字符串 "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="d7f91-659">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="d7f91-660">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="d7f91-660">0-2 whitespace characters</span></span>
- <span data-ttu-id="d7f91-661">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="d7f91-661">An equal sign (=)</span></span>
- <span data-ttu-id="d7f91-662">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="d7f91-662">0-2 whitespace characters</span></span>
- <span data-ttu-id="d7f91-663">43个字符的任意组合, 这些字符为小写字母、数字、斜杠 (/) 或加号 (+)</span><span class="sxs-lookup"><span data-stu-id="d7f91-663">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="d7f91-664">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="d7f91-664">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-665">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-665">Checksum</span></span>

<span data-ttu-id="d7f91-666">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-666">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-667">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-667">Definition</span></span>

<span data-ttu-id="d7f91-668">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-668">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-669">正则表达式 CEP_Regex_AzureServiceBusConnectionString 找到与该模式匹配的内容。。</span><span class="sxs-lookup"><span data-stu-id="d7f91-669">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="d7f91-670">正则表达式 CEP_CommonExampleKeywords**未**找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-670">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-671">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-671">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="d7f91-672">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="d7f91-672">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="d7f91-673">(请注意, 从技术上讲, 此敏感信息类型通过使用正则表达式 (而不是关键字列表) 来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-673">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="d7f91-674">尚未</span><span class="sxs-lookup"><span data-stu-id="d7f91-674">contoso</span></span>
- <span data-ttu-id="d7f91-675">送交</span><span class="sxs-lookup"><span data-stu-id="d7f91-675">fabrikam</span></span>
- <span data-ttu-id="d7f91-676">罗斯</span><span class="sxs-lookup"><span data-stu-id="d7f91-676">northwind</span></span>
- <span data-ttu-id="d7f91-677">沙盒</span><span class="sxs-lookup"><span data-stu-id="d7f91-677">sandbox</span></span>
- <span data-ttu-id="d7f91-678">onebox</span><span class="sxs-lookup"><span data-stu-id="d7f91-678">onebox</span></span>
- <span data-ttu-id="d7f91-679">localhost</span><span class="sxs-lookup"><span data-stu-id="d7f91-679">localhost</span></span>
- <span data-ttu-id="d7f91-680">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="d7f91-680">127.0.0.1</span></span>
- <span data-ttu-id="d7f91-681">testacs.</span><span class="sxs-lookup"><span data-stu-id="d7f91-681">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="d7f91-682">com</span><span class="sxs-lookup"><span data-stu-id="d7f91-682">com</span></span>
- <span data-ttu-id="d7f91-683">s-int。</span><span class="sxs-lookup"><span data-stu-id="d7f91-683">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="d7f91-684">netmeeting</span><span class="sxs-lookup"><span data-stu-id="d7f91-684">net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="d7f91-685">Azure 存储帐户密钥</span><span class="sxs-lookup"><span data-stu-id="d7f91-685">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-686">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-686">Format</span></span>

<span data-ttu-id="d7f91-687">字符串 "DefaultEndpointsProtocol", 后跟下面模式中所述的字符和字符串, 包括字符串 "AccountKey"。</span><span class="sxs-lookup"><span data-stu-id="d7f91-687">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-688">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-688">Pattern</span></span>

- <span data-ttu-id="d7f91-689">字符串 "DefaultEndpointsProtocol"</span><span class="sxs-lookup"><span data-stu-id="d7f91-689">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="d7f91-690">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="d7f91-690">0-2 whitespace characters</span></span>
- <span data-ttu-id="d7f91-691">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="d7f91-691">An equal sign (=)</span></span>
- <span data-ttu-id="d7f91-692">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="d7f91-692">0-2 whitespace characters</span></span>
- <span data-ttu-id="d7f91-693">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="d7f91-693">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="d7f91-694">字符串 "AccountKey"</span><span class="sxs-lookup"><span data-stu-id="d7f91-694">The string "AccountKey"</span></span>
- <span data-ttu-id="d7f91-695">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="d7f91-695">0-2 whitespace characters</span></span>
- <span data-ttu-id="d7f91-696">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="d7f91-696">An equal sign (=)</span></span>
- <span data-ttu-id="d7f91-697">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="d7f91-697">0-2 whitespace characters</span></span>
- <span data-ttu-id="d7f91-698">86个字符的任意组合, 这些字符为小写字母、数字、斜杠 (/) 或加号 (+)</span><span class="sxs-lookup"><span data-stu-id="d7f91-698">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="d7f91-699">两个等号 (=)</span><span class="sxs-lookup"><span data-stu-id="d7f91-699">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-700">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-700">Checksum</span></span>

<span data-ttu-id="d7f91-701">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-701">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-702">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-702">Definition</span></span>

<span data-ttu-id="d7f91-703">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-703">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-704">正则表达式 CEP_Regex_AzureStorageAccountKey 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-704">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-705">正则表达式 CEP_AzureEmulatorStorageAccountFilter**未**找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-705">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-706">正则表达式 CEP_CommonExampleKeywords**未**找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-706">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-707">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-707">Keywords</span></span>

#### <a name="cep_azureemulatorstorageaccountfilter"></a><span data-ttu-id="d7f91-708">CEP_AzureEmulatorStorageAccountFilter</span><span class="sxs-lookup"><span data-stu-id="d7f91-708">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="d7f91-709">(请注意, 从技术上讲, 此敏感信息类型通过使用正则表达式 (而不是关键字列表) 来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-709">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="d7f91-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =</span><span class="sxs-lookup"><span data-stu-id="d7f91-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="d7f91-711">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="d7f91-711">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="d7f91-712">(请注意, 从技术上讲, 此敏感信息类型通过使用正则表达式 (而不是关键字列表) 来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-712">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="d7f91-713">尚未</span><span class="sxs-lookup"><span data-stu-id="d7f91-713">contoso</span></span>
- <span data-ttu-id="d7f91-714">送交</span><span class="sxs-lookup"><span data-stu-id="d7f91-714">fabrikam</span></span>
- <span data-ttu-id="d7f91-715">罗斯</span><span class="sxs-lookup"><span data-stu-id="d7f91-715">northwind</span></span>
- <span data-ttu-id="d7f91-716">沙盒</span><span class="sxs-lookup"><span data-stu-id="d7f91-716">sandbox</span></span>
- <span data-ttu-id="d7f91-717">onebox</span><span class="sxs-lookup"><span data-stu-id="d7f91-717">onebox</span></span>
- <span data-ttu-id="d7f91-718">localhost</span><span class="sxs-lookup"><span data-stu-id="d7f91-718">localhost</span></span>
- <span data-ttu-id="d7f91-719">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="d7f91-719">127.0.0.1</span></span>
- <span data-ttu-id="d7f91-720">testacs.</span><span class="sxs-lookup"><span data-stu-id="d7f91-720">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="d7f91-721">com</span><span class="sxs-lookup"><span data-stu-id="d7f91-721">com</span></span>
- <span data-ttu-id="d7f91-722">s-int。</span><span class="sxs-lookup"><span data-stu-id="d7f91-722">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="d7f91-723">netmeeting</span><span class="sxs-lookup"><span data-stu-id="d7f91-723">net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="d7f91-724">Azure 存储帐户密钥 (常规)</span><span class="sxs-lookup"><span data-stu-id="d7f91-724">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-725">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-725">Format</span></span>

<span data-ttu-id="d7f91-726">任何86位或大写字母、数字、正斜杠 (/) 或加号 (+) 的任意组合, 前面或后面是下面模式中所述的字符。</span><span class="sxs-lookup"><span data-stu-id="d7f91-726">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-727">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-727">Pattern</span></span>

- <span data-ttu-id="d7f91-728">大于号 (>)、撇号 (')、等号 (=)、引号 (") 或数字符号 (#) 的0-1</span><span class="sxs-lookup"><span data-stu-id="d7f91-728">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="d7f91-729">86个字符的任意组合, 这些字符为小写字母、数字、斜杠 (/) 或加号 (+)</span><span class="sxs-lookup"><span data-stu-id="d7f91-729">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="d7f91-730">两个等号 (=)</span><span class="sxs-lookup"><span data-stu-id="d7f91-730">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="d7f91-731">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-731">Checksum</span></span>

<span data-ttu-id="d7f91-732">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-732">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-733">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-733">Definition</span></span>

<span data-ttu-id="d7f91-734">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-734">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-735">正则表达式 CEP_Regex_AzureStorageAccountKeyGeneric 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-735">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="d7f91-736">比利时国家号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-736">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-737">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-737">Format</span></span>

<span data-ttu-id="d7f91-738">11 个数字加分隔符</span><span class="sxs-lookup"><span data-stu-id="d7f91-738">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-739">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-739">Pattern</span></span>

<span data-ttu-id="d7f91-740">11 个数字加分隔符：</span><span class="sxs-lookup"><span data-stu-id="d7f91-740">11 digits plus delimiters:</span></span>
- <span data-ttu-id="d7f91-741">六个数字加两个点，采用格式  YY.MM.DD，代表出生日期  </span><span class="sxs-lookup"><span data-stu-id="d7f91-741">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="d7f91-742">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="d7f91-742">A hyphen</span></span> 
- <span data-ttu-id="d7f91-743">三个连续的数字（男性用奇数，女性用偶数） </span><span class="sxs-lookup"><span data-stu-id="d7f91-743">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="d7f91-744">一个点</span><span class="sxs-lookup"><span data-stu-id="d7f91-744">A period</span></span> 
- <span data-ttu-id="d7f91-745">两个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="d7f91-745">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-746">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-746">Checksum</span></span>

<span data-ttu-id="d7f91-747">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-747">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-748">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-748">Definition</span></span>

<span data-ttu-id="d7f91-749">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-749">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-750">函数 Func_belgium_national_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-750">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-751">找到 Keyword_belgium_national_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-751">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="d7f91-752">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-752">The checksum passes.</span></span>

```xml
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-753">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-753">Keywords</span></span>

#### <a name="keyword_belgium_national_number"></a><span data-ttu-id="d7f91-754">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="d7f91-754">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="d7f91-755">标识</span><span class="sxs-lookup"><span data-stu-id="d7f91-755">Identity</span></span>
- <span data-ttu-id="d7f91-756">注册</span><span class="sxs-lookup"><span data-stu-id="d7f91-756">Registration</span></span>
- <span data-ttu-id="d7f91-757">Id</span><span class="sxs-lookup"><span data-stu-id="d7f91-757">Identification</span></span> 
- <span data-ttu-id="d7f91-758">ID</span><span class="sxs-lookup"><span data-stu-id="d7f91-758">ID</span></span> 
- <span data-ttu-id="d7f91-759">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="d7f91-759">Identiteitskaart</span></span>
- <span data-ttu-id="d7f91-760">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="d7f91-760">Registratie nummer</span></span> 
- <span data-ttu-id="d7f91-761">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="d7f91-761">Identificatie nummer</span></span> 
- <span data-ttu-id="d7f91-762">Identiteit</span><span class="sxs-lookup"><span data-stu-id="d7f91-762">Identiteit</span></span>
- <span data-ttu-id="d7f91-763">Registratie</span><span class="sxs-lookup"><span data-stu-id="d7f91-763">Registratie</span></span>
- <span data-ttu-id="d7f91-764">Identificatie</span><span class="sxs-lookup"><span data-stu-id="d7f91-764">Identificatie</span></span> 
- <span data-ttu-id="d7f91-765">Carte d’identité</span><span class="sxs-lookup"><span data-stu-id="d7f91-765">Carte d’identité</span></span> 
- <span data-ttu-id="d7f91-766">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="d7f91-766">numéro d'immatriculation</span></span>
- <span data-ttu-id="d7f91-767">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="d7f91-767">numéro d'identification</span></span>
- <span data-ttu-id="d7f91-768">identité</span><span class="sxs-lookup"><span data-stu-id="d7f91-768">identité</span></span> 
- <span data-ttu-id="d7f91-769">inscription</span><span class="sxs-lookup"><span data-stu-id="d7f91-769">inscription</span></span> 
- <span data-ttu-id="d7f91-770">Identifikation</span><span class="sxs-lookup"><span data-stu-id="d7f91-770">Identifikation</span></span>
- <span data-ttu-id="d7f91-771">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="d7f91-771">Identifizierung</span></span>
- <span data-ttu-id="d7f91-772">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="d7f91-772">Identifikationsnummer</span></span>
- <span data-ttu-id="d7f91-773">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="d7f91-773">Personalausweis</span></span>
- <span data-ttu-id="d7f91-774">Registrierung</span><span class="sxs-lookup"><span data-stu-id="d7f91-774">Registrierung</span></span>
- <span data-ttu-id="d7f91-775">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="d7f91-775">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="d7f91-776">巴西 CPF 号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-776">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-777">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-777">Format</span></span>

<span data-ttu-id="d7f91-778">11 个数字（包括校验位），可以格式化，也可以非格式化</span><span class="sxs-lookup"><span data-stu-id="d7f91-778">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-779">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-779">Pattern</span></span>

<span data-ttu-id="d7f91-780">格式</span><span class="sxs-lookup"><span data-stu-id="d7f91-780">Formatted:</span></span>
- <span data-ttu-id="d7f91-781">三位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-781">Three digits</span></span> 
- <span data-ttu-id="d7f91-782">一个点 </span><span class="sxs-lookup"><span data-stu-id="d7f91-782">A period</span></span> 
- <span data-ttu-id="d7f91-783">三位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-783">Three digits</span></span> 
- <span data-ttu-id="d7f91-784">一个点 </span><span class="sxs-lookup"><span data-stu-id="d7f91-784">A period</span></span> 
- <span data-ttu-id="d7f91-785">三位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-785">Three digits</span></span> 
- <span data-ttu-id="d7f91-786">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="d7f91-786">A hyphen</span></span> 
- <span data-ttu-id="d7f91-787">两个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="d7f91-787">Two digits which are check digits</span></span>

<span data-ttu-id="d7f91-788">纯</span><span class="sxs-lookup"><span data-stu-id="d7f91-788">Unformatted:</span></span>
- <span data-ttu-id="d7f91-789">11 个数字，其中最后两个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="d7f91-789">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-790">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-790">Checksum</span></span>

<span data-ttu-id="d7f91-791">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-791">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-792">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-792">Definition</span></span>

<span data-ttu-id="d7f91-793">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-794">函数 Func_brazil_cpf 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-794">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-795">找到 Keyword_brazil_cpf 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-795">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="d7f91-796">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-796">The checksum passes.</span></span>

<span data-ttu-id="d7f91-797">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-797">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-798">函数 Func_brazil_cpf 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-798">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-799">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-799">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-800">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-800">Keywords</span></span>

#### <a name="keyword_brazil_cpf"></a><span data-ttu-id="d7f91-801">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="d7f91-801">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="d7f91-802">CPF</span><span class="sxs-lookup"><span data-stu-id="d7f91-802">CPF</span></span>
- <span data-ttu-id="d7f91-803">Id</span><span class="sxs-lookup"><span data-stu-id="d7f91-803">Identification</span></span>
- <span data-ttu-id="d7f91-804">注册</span><span class="sxs-lookup"><span data-stu-id="d7f91-804">Registration</span></span>
- <span data-ttu-id="d7f91-805">营业</span><span class="sxs-lookup"><span data-stu-id="d7f91-805">Revenue</span></span>
- <span data-ttu-id="d7f91-806">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="d7f91-806">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="d7f91-807">Imposto</span><span class="sxs-lookup"><span data-stu-id="d7f91-807">Imposto</span></span> 
- <span data-ttu-id="d7f91-808">Identificação</span><span class="sxs-lookup"><span data-stu-id="d7f91-808">Identificação</span></span> 
- <span data-ttu-id="d7f91-809">Inscrição</span><span class="sxs-lookup"><span data-stu-id="d7f91-809">Inscrição</span></span> 
- <span data-ttu-id="d7f91-810">Receita</span><span class="sxs-lookup"><span data-stu-id="d7f91-810">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="d7f91-811">巴西法律实体编号 (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="d7f91-811">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-812">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-812">Format</span></span>

<span data-ttu-id="d7f91-813">14 个数字（包括注册号、分行号码和校验位），再加上分隔符</span><span class="sxs-lookup"><span data-stu-id="d7f91-813">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-814">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-814">Pattern</span></span>
<span data-ttu-id="d7f91-815">14 个数字，再加上分隔符：</span><span class="sxs-lookup"><span data-stu-id="d7f91-815">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="d7f91-816">两个数字 </span><span class="sxs-lookup"><span data-stu-id="d7f91-816">Two digits</span></span> 
- <span data-ttu-id="d7f91-817">一个点 </span><span class="sxs-lookup"><span data-stu-id="d7f91-817">A period</span></span> 
- <span data-ttu-id="d7f91-818">三个数字 </span><span class="sxs-lookup"><span data-stu-id="d7f91-818">Three digits</span></span> 
- <span data-ttu-id="d7f91-819">一个点 </span><span class="sxs-lookup"><span data-stu-id="d7f91-819">A period</span></span> 
- <span data-ttu-id="d7f91-820">三个数字（前 8 位数是注册号） </span><span class="sxs-lookup"><span data-stu-id="d7f91-820">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="d7f91-821">正斜杠 </span><span class="sxs-lookup"><span data-stu-id="d7f91-821">A forward slash</span></span> 
- <span data-ttu-id="d7f91-822">四位分行号码 </span><span class="sxs-lookup"><span data-stu-id="d7f91-822">Four-digit branch number</span></span> 
- <span data-ttu-id="d7f91-823">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="d7f91-823">A hyphen</span></span> 
- <span data-ttu-id="d7f91-824">两个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="d7f91-824">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-825">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-825">Checksum</span></span>

<span data-ttu-id="d7f91-826">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-826">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-827">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-827">Definition</span></span>

<span data-ttu-id="d7f91-828">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-828">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-829">函数 Func_brazil_cnpj 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-829">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-830">找到 Keyword_brazil_cnpj 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-830">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="d7f91-831">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-831">The checksum passes.</span></span>

<span data-ttu-id="d7f91-832">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-833">函数 Func_brazil_cnpj 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-833">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-834">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-834">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-835">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-835">Keywords</span></span>

#### <a name="keyword_brazil_cnpj"></a><span data-ttu-id="d7f91-836">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="d7f91-836">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="d7f91-837">CNPJ</span><span class="sxs-lookup"><span data-stu-id="d7f91-837">CNPJ</span></span> 
- <span data-ttu-id="d7f91-838">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="d7f91-838">CNPJ/MF</span></span> 
- <span data-ttu-id="d7f91-839">CNPJ-MF</span><span class="sxs-lookup"><span data-stu-id="d7f91-839">CNPJ-MF</span></span> 
- <span data-ttu-id="d7f91-840">National Registry of Legal Entities</span><span class="sxs-lookup"><span data-stu-id="d7f91-840">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="d7f91-841">Taxpayers Registry</span><span class="sxs-lookup"><span data-stu-id="d7f91-841">Taxpayers Registry</span></span> 
- <span data-ttu-id="d7f91-842">Legal entity</span><span class="sxs-lookup"><span data-stu-id="d7f91-842">Legal entity</span></span> 
- <span data-ttu-id="d7f91-843">Legal entities</span><span class="sxs-lookup"><span data-stu-id="d7f91-843">Legal entities</span></span> 
- <span data-ttu-id="d7f91-844">Registration Status</span><span class="sxs-lookup"><span data-stu-id="d7f91-844">Registration Status</span></span> 
- <span data-ttu-id="d7f91-845">商业版</span><span class="sxs-lookup"><span data-stu-id="d7f91-845">Business</span></span> 
- <span data-ttu-id="d7f91-846">Company</span><span class="sxs-lookup"><span data-stu-id="d7f91-846">Company</span></span>
- <span data-ttu-id="d7f91-847">CNPJ</span><span class="sxs-lookup"><span data-stu-id="d7f91-847">CNPJ</span></span> 
- <span data-ttu-id="d7f91-848">Cadastro Nacional da Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="d7f91-848">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="d7f91-849">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="d7f91-849">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="d7f91-850">CGC</span><span class="sxs-lookup"><span data-stu-id="d7f91-850">CGC</span></span> 
- <span data-ttu-id="d7f91-851">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="d7f91-851">Pessoa jurídica</span></span> 
- <span data-ttu-id="d7f91-852">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="d7f91-852">Pessoas jurídicas</span></span> 
- <span data-ttu-id="d7f91-853">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="d7f91-853">Situação cadastral</span></span> 
- <span data-ttu-id="d7f91-854">Inscrição</span><span class="sxs-lookup"><span data-stu-id="d7f91-854">Inscrição</span></span> 
- <span data-ttu-id="d7f91-855">Empresa</span><span class="sxs-lookup"><span data-stu-id="d7f91-855">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="d7f91-856">	巴西国家身份证 (RG)</span><span class="sxs-lookup"><span data-stu-id="d7f91-856">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-857">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-857">Format</span></span>

<span data-ttu-id="d7f91-858">Registro Geral (旧格式): 9 个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-858">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="d7f91-859">Registro de Identidade (RIC) (新格式):11 个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-859">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-860">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-860">Pattern</span></span>

<span data-ttu-id="d7f91-861">Registro Geral（旧格式）：</span><span class="sxs-lookup"><span data-stu-id="d7f91-861">Registro Geral (old format):</span></span>
- <span data-ttu-id="d7f91-862">两个数字 </span><span class="sxs-lookup"><span data-stu-id="d7f91-862">Two digits</span></span> 
- <span data-ttu-id="d7f91-863">一个点 </span><span class="sxs-lookup"><span data-stu-id="d7f91-863">A period</span></span> 
- <span data-ttu-id="d7f91-864">三个数字 </span><span class="sxs-lookup"><span data-stu-id="d7f91-864">Three digits</span></span> 
- <span data-ttu-id="d7f91-865">一个点 </span><span class="sxs-lookup"><span data-stu-id="d7f91-865">A period</span></span> 
- <span data-ttu-id="d7f91-866">三个数字 </span><span class="sxs-lookup"><span data-stu-id="d7f91-866">Three digits</span></span> 
- <span data-ttu-id="d7f91-867">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="d7f91-867">A hyphen</span></span> 
- <span data-ttu-id="d7f91-868">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="d7f91-868">One digit which is a check digit</span></span>

<span data-ttu-id="d7f91-869">Registro de Identidade (RIC) (新格式):</span><span class="sxs-lookup"><span data-stu-id="d7f91-869">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="d7f91-870">10 个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-870">10 digits</span></span> 
- <span data-ttu-id="d7f91-871">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="d7f91-871">A hyphen</span></span> 
- <span data-ttu-id="d7f91-872">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="d7f91-872">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-873">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-873">Checksum</span></span>

<span data-ttu-id="d7f91-874">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-874">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-875">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-875">Definition</span></span>

<span data-ttu-id="d7f91-876">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-876">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-877">函数 Func_brazil_rg 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-877">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-878">找到 Keyword_brazil_rg 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-878">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="d7f91-879">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-879">The checksum passes.</span></span>

<span data-ttu-id="d7f91-880">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-880">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-881">函数 Func_brazil_rg 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-881">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-882">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-882">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-883">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-883">Keywords</span></span>

#### <a name="keyword_brazil_rg"></a><span data-ttu-id="d7f91-884">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="d7f91-884">Keyword_brazil_rg</span></span>

<span data-ttu-id="d7f91-885">Cédula de identidade identity 卡片国家 id número de rregistro registro de Iidentidade registro geral RG (此关键字区分大小写) RIC (此关键字区分大小写)</span><span class="sxs-lookup"><span data-stu-id="d7f91-885">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="d7f91-886">加拿大银行帐号</span><span class="sxs-lookup"><span data-stu-id="d7f91-886">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-887">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-887">Format</span></span>

<span data-ttu-id="d7f91-888">七个或十二个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-888">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-889">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-889">Pattern</span></span>

<span data-ttu-id="d7f91-890">加拿大银行帐号是七个或十二个数字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-890">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="d7f91-891">加拿大银行帐户的银行代号是：</span><span class="sxs-lookup"><span data-stu-id="d7f91-891">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="d7f91-892">五位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-892">Five digits</span></span> 
- <span data-ttu-id="d7f91-893">连字符</span><span class="sxs-lookup"><span data-stu-id="d7f91-893">A hyphen</span></span> 
- <span data-ttu-id="d7f91-894">三位数字或</span><span class="sxs-lookup"><span data-stu-id="d7f91-894">Three digits OR</span></span>
- <span data-ttu-id="d7f91-895">一个零“0” </span><span class="sxs-lookup"><span data-stu-id="d7f91-895">A zero "0"</span></span> 
- <span data-ttu-id="d7f91-896">八位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-896">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-897">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-897">Checksum</span></span>

<span data-ttu-id="d7f91-898">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-898">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-899">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-899">Definition</span></span>

<span data-ttu-id="d7f91-900">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-900">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-901">正则表达式 Regex_canada_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-901">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-902">找到 Keyword_canada_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-902">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="d7f91-903">正则表达式 Regex_canada_bank_account_transit_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-903">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="d7f91-904">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-904">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-905">正则表达式 Regex_canada_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-905">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-906">找到 Keyword_canada_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-906">A keyword from Keyword_canada_bank_account_number is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-907">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-907">Keywords</span></span>

#### <a name="keyword_canada_bank_account_number"></a><span data-ttu-id="d7f91-908">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="d7f91-908">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="d7f91-909">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="d7f91-909">canada savings bonds</span></span>
- <span data-ttu-id="d7f91-910">canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="d7f91-910">canada revenue agency</span></span>
- <span data-ttu-id="d7f91-911">canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="d7f91-911">canadian financial institution</span></span>
- <span data-ttu-id="d7f91-912">direct deposit form</span><span class="sxs-lookup"><span data-stu-id="d7f91-912">direct deposit form</span></span>
- <span data-ttu-id="d7f91-913">canadian citizen</span><span class="sxs-lookup"><span data-stu-id="d7f91-913">canadian citizen</span></span>
- <span data-ttu-id="d7f91-914">legal representative</span><span class="sxs-lookup"><span data-stu-id="d7f91-914">legal representative</span></span>
- <span data-ttu-id="d7f91-915">notary public</span><span class="sxs-lookup"><span data-stu-id="d7f91-915">notary public</span></span>
- <span data-ttu-id="d7f91-916">commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="d7f91-916">commissioner for oaths</span></span>
- <span data-ttu-id="d7f91-917">child care benefit</span><span class="sxs-lookup"><span data-stu-id="d7f91-917">child care benefit</span></span>
- <span data-ttu-id="d7f91-918">universal child care</span><span class="sxs-lookup"><span data-stu-id="d7f91-918">universal child care</span></span>
- <span data-ttu-id="d7f91-919">canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="d7f91-919">canada child tax benefit</span></span>
- <span data-ttu-id="d7f91-920">income tax benefit</span><span class="sxs-lookup"><span data-stu-id="d7f91-920">income tax benefit</span></span>
- <span data-ttu-id="d7f91-921">harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="d7f91-921">harmonized sales tax</span></span>
- <span data-ttu-id="d7f91-922">social insurance number</span><span class="sxs-lookup"><span data-stu-id="d7f91-922">social insurance number</span></span>
- <span data-ttu-id="d7f91-923">income tax refund</span><span class="sxs-lookup"><span data-stu-id="d7f91-923">income tax refund</span></span>
- <span data-ttu-id="d7f91-924">child tax benefit</span><span class="sxs-lookup"><span data-stu-id="d7f91-924">child tax benefit</span></span>
- <span data-ttu-id="d7f91-925">territorial payments</span><span class="sxs-lookup"><span data-stu-id="d7f91-925">territorial payments</span></span>
- <span data-ttu-id="d7f91-926">institution number</span><span class="sxs-lookup"><span data-stu-id="d7f91-926">institution number</span></span>
- <span data-ttu-id="d7f91-927">deposit request</span><span class="sxs-lookup"><span data-stu-id="d7f91-927">deposit request</span></span>
- <span data-ttu-id="d7f91-928">banking information</span><span class="sxs-lookup"><span data-stu-id="d7f91-928">banking information</span></span>
- <span data-ttu-id="d7f91-929">direct deposit</span><span class="sxs-lookup"><span data-stu-id="d7f91-929">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="d7f91-930">加拿大驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-930">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-931">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-931">Format</span></span>

<span data-ttu-id="d7f91-932">因省而异</span><span class="sxs-lookup"><span data-stu-id="d7f91-932">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-933">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-933">Pattern</span></span>

<span data-ttu-id="d7f91-934">各种模式，涵盖艾伯塔、 不列颠哥伦比亚、 马尼托巴、 新不伦瑞克、 纽芬兰/拉布拉多、 新斯科舍、 安大略、 爱德华王子岛，魁北克和萨斯喀彻温</span><span class="sxs-lookup"><span data-stu-id="d7f91-934">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-935">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-935">Checksum</span></span>

<span data-ttu-id="d7f91-936">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-936">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-937">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-937">Definition</span></span>

<span data-ttu-id="d7f91-938">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-938">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-939">函数 Func_[province_name]_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-939">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-940">找到 Keyword_[province_name]_drivers_license_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-940">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="d7f91-941">找到 Keyword_canada_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-941">A keyword from Keyword_canada_drivers_license is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-942">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-942">Keywords</span></span>

#### <a name="keyword_province_name_drivers_license_name"></a><span data-ttu-id="d7f91-943">Keyword_[province_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="d7f91-943">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="d7f91-944">省/市/自治区的缩写，例如 AB</span><span class="sxs-lookup"><span data-stu-id="d7f91-944">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="d7f91-945">省名称，例如 Alberta</span><span class="sxs-lookup"><span data-stu-id="d7f91-945">The province name, for example Alberta</span></span>

#### <a name="keyword_canada_drivers_license"></a><span data-ttu-id="d7f91-946">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="d7f91-946">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="d7f91-947">通讯</span><span class="sxs-lookup"><span data-stu-id="d7f91-947">DL</span></span>
- <span data-ttu-id="d7f91-948">DLS</span><span class="sxs-lookup"><span data-stu-id="d7f91-948">DLS</span></span>
- <span data-ttu-id="d7f91-949">采用</span><span class="sxs-lookup"><span data-stu-id="d7f91-949">CDL</span></span>
- <span data-ttu-id="d7f91-950">CDLS</span><span class="sxs-lookup"><span data-stu-id="d7f91-950">CDLS</span></span>
- <span data-ttu-id="d7f91-951">DriverLic</span><span class="sxs-lookup"><span data-stu-id="d7f91-951">DriverLic</span></span>
- <span data-ttu-id="d7f91-952">DriverLics</span><span class="sxs-lookup"><span data-stu-id="d7f91-952">DriverLics</span></span>
- <span data-ttu-id="d7f91-953">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="d7f91-953">DriverLicense</span></span>
- <span data-ttu-id="d7f91-954">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="d7f91-954">DriverLicenses</span></span>
- <span data-ttu-id="d7f91-955">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="d7f91-955">DriverLicence</span></span>
- <span data-ttu-id="d7f91-956">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="d7f91-956">DriverLicences</span></span>
- <span data-ttu-id="d7f91-957">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="d7f91-957">Driver Lic</span></span>
- <span data-ttu-id="d7f91-958">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="d7f91-958">Driver Lics</span></span>
- <span data-ttu-id="d7f91-959">Driver License</span><span class="sxs-lookup"><span data-stu-id="d7f91-959">Driver License</span></span>
- <span data-ttu-id="d7f91-960">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="d7f91-960">Driver Licenses</span></span>
- <span data-ttu-id="d7f91-961">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="d7f91-961">Driver Licence</span></span>
- <span data-ttu-id="d7f91-962">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="d7f91-962">Driver Licences</span></span>
- <span data-ttu-id="d7f91-963">DriversLic</span><span class="sxs-lookup"><span data-stu-id="d7f91-963">DriversLic</span></span>
- <span data-ttu-id="d7f91-964">DriversLics</span><span class="sxs-lookup"><span data-stu-id="d7f91-964">DriversLics</span></span>
- <span data-ttu-id="d7f91-965">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="d7f91-965">DriversLicence</span></span>
- <span data-ttu-id="d7f91-966">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="d7f91-966">DriversLicences</span></span>
- <span data-ttu-id="d7f91-967">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="d7f91-967">DriversLicense</span></span>
- <span data-ttu-id="d7f91-968">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="d7f91-968">DriversLicenses</span></span>
- <span data-ttu-id="d7f91-969">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="d7f91-969">Drivers Lic</span></span>
- <span data-ttu-id="d7f91-970">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="d7f91-970">Drivers Lics</span></span>
- <span data-ttu-id="d7f91-971">Drivers License</span><span class="sxs-lookup"><span data-stu-id="d7f91-971">Drivers License</span></span>
- <span data-ttu-id="d7f91-972">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="d7f91-972">Drivers Licenses</span></span>
- <span data-ttu-id="d7f91-973">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="d7f91-973">Drivers Licence</span></span>
- <span data-ttu-id="d7f91-974">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="d7f91-974">Drivers Licences</span></span>
- <span data-ttu-id="d7f91-975">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="d7f91-975">Driver'Lic</span></span>
- <span data-ttu-id="d7f91-976">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="d7f91-976">Driver'Lics</span></span>
- <span data-ttu-id="d7f91-977">Driver'License</span><span class="sxs-lookup"><span data-stu-id="d7f91-977">Driver'License</span></span>
- <span data-ttu-id="d7f91-978">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="d7f91-978">Driver'Licenses</span></span>
- <span data-ttu-id="d7f91-979">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="d7f91-979">Driver'Licence</span></span>
- <span data-ttu-id="d7f91-980">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="d7f91-980">Driver'Licences</span></span>
- <span data-ttu-id="d7f91-981">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="d7f91-981">Driver' Lic</span></span>
- <span data-ttu-id="d7f91-982">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="d7f91-982">Driver' Lics</span></span>
- <span data-ttu-id="d7f91-983">Driver' License</span><span class="sxs-lookup"><span data-stu-id="d7f91-983">Driver' License</span></span>
- <span data-ttu-id="d7f91-984">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="d7f91-984">Driver' Licenses</span></span>
- <span data-ttu-id="d7f91-985">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="d7f91-985">Driver' Licence</span></span>
- <span data-ttu-id="d7f91-986">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="d7f91-986">Driver' Licences</span></span>
- <span data-ttu-id="d7f91-987">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="d7f91-987">Driver'sLic</span></span>
- <span data-ttu-id="d7f91-988">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="d7f91-988">Driver'sLics</span></span>
- <span data-ttu-id="d7f91-989">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="d7f91-989">Driver'sLicense</span></span>
- <span data-ttu-id="d7f91-990">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="d7f91-990">Driver'sLicenses</span></span>
- <span data-ttu-id="d7f91-991">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="d7f91-991">Driver'sLicence</span></span>
- <span data-ttu-id="d7f91-992">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="d7f91-992">Driver'sLicences</span></span>
- <span data-ttu-id="d7f91-993">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="d7f91-993">Driver's Lic</span></span>
- <span data-ttu-id="d7f91-994">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="d7f91-994">Driver's Lics</span></span>
- <span data-ttu-id="d7f91-995">Driver's License</span><span class="sxs-lookup"><span data-stu-id="d7f91-995">Driver's License</span></span>
- <span data-ttu-id="d7f91-996">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="d7f91-996">Driver's Licenses</span></span>
- <span data-ttu-id="d7f91-997">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="d7f91-997">Driver's Licence</span></span>
- <span data-ttu-id="d7f91-998">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="d7f91-998">Driver's Licences</span></span>
- <span data-ttu-id="d7f91-999">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="d7f91-999">Permis de Conduire</span></span>
- <span data-ttu-id="d7f91-1000">id</span><span class="sxs-lookup"><span data-stu-id="d7f91-1000">id</span></span>
- <span data-ttu-id="d7f91-1001">ids</span><span class="sxs-lookup"><span data-stu-id="d7f91-1001">ids</span></span>
- <span data-ttu-id="d7f91-1002">idcard number</span><span class="sxs-lookup"><span data-stu-id="d7f91-1002">idcard number</span></span>
- <span data-ttu-id="d7f91-1003">idcard numbers</span><span class="sxs-lookup"><span data-stu-id="d7f91-1003">idcard numbers</span></span>
- <span data-ttu-id="d7f91-1004">idcard #</span><span class="sxs-lookup"><span data-stu-id="d7f91-1004">idcard #</span></span>
- <span data-ttu-id="d7f91-1005">idcard #s</span><span class="sxs-lookup"><span data-stu-id="d7f91-1005">idcard #s</span></span>
- <span data-ttu-id="d7f91-1006">idcard card</span><span class="sxs-lookup"><span data-stu-id="d7f91-1006">idcard card</span></span>
- <span data-ttu-id="d7f91-1007">idcard cards</span><span class="sxs-lookup"><span data-stu-id="d7f91-1007">idcard cards</span></span>
- <span data-ttu-id="d7f91-1008">idcard</span><span class="sxs-lookup"><span data-stu-id="d7f91-1008">idcard</span></span>
- <span data-ttu-id="d7f91-1009">identification number</span><span class="sxs-lookup"><span data-stu-id="d7f91-1009">identification number</span></span>
- <span data-ttu-id="d7f91-1010">identification numbers</span><span class="sxs-lookup"><span data-stu-id="d7f91-1010">identification numbers</span></span>
- <span data-ttu-id="d7f91-1011">identification #</span><span class="sxs-lookup"><span data-stu-id="d7f91-1011">identification #</span></span>
- <span data-ttu-id="d7f91-1012">identification #s</span><span class="sxs-lookup"><span data-stu-id="d7f91-1012">identification #s</span></span>
- <span data-ttu-id="d7f91-1013">identification card</span><span class="sxs-lookup"><span data-stu-id="d7f91-1013">identification card</span></span>
- <span data-ttu-id="d7f91-1014">identification cards</span><span class="sxs-lookup"><span data-stu-id="d7f91-1014">identification cards</span></span>
- <span data-ttu-id="d7f91-1015">id</span><span class="sxs-lookup"><span data-stu-id="d7f91-1015">identification</span></span> 
- <span data-ttu-id="d7f91-1016">通讯#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1016">DL#</span></span>
- <span data-ttu-id="d7f91-1017">DLS#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1017">DLS#</span></span> 
- <span data-ttu-id="d7f91-1018">采用#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1018">CDL#</span></span> 
- <span data-ttu-id="d7f91-1019">CDLS#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1019">CDLS#</span></span> 
- <span data-ttu-id="d7f91-1020">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1020">DriverLic#</span></span> 
- <span data-ttu-id="d7f91-1021">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1021">DriverLics#</span></span> 
- <span data-ttu-id="d7f91-1022">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1022">DriverLicense#</span></span> 
- <span data-ttu-id="d7f91-1023">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1023">DriverLicenses#</span></span> 
- <span data-ttu-id="d7f91-1024">DriverLicence#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1024">DriverLicence#</span></span> 
- <span data-ttu-id="d7f91-1025">DriverLicences#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1025">DriverLicences#</span></span> 
- <span data-ttu-id="d7f91-1026">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1026">Driver Lic#</span></span>
- <span data-ttu-id="d7f91-1027">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1027">Driver Lics#</span></span> 
- <span data-ttu-id="d7f91-1028">Driver License#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1028">Driver License#</span></span> 
- <span data-ttu-id="d7f91-1029">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1029">Driver Licenses#</span></span> 
- <span data-ttu-id="d7f91-1030">Driver License#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1030">Driver License#</span></span> 
- <span data-ttu-id="d7f91-1031">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1031">Driver Licences#</span></span> 
- <span data-ttu-id="d7f91-1032">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1032">DriversLic#</span></span> 
- <span data-ttu-id="d7f91-1033">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1033">DriversLics#</span></span> 
- <span data-ttu-id="d7f91-1034">DriversLicense#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1034">DriversLicense#</span></span> 
- <span data-ttu-id="d7f91-1035">DriversLicenses#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1035">DriversLicenses#</span></span> 
- <span data-ttu-id="d7f91-1036">DriversLicence#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1036">DriversLicence#</span></span> 
- <span data-ttu-id="d7f91-1037">DriversLicences#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1037">DriversLicences#</span></span> 
- <span data-ttu-id="d7f91-1038">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1038">Drivers Lic#</span></span> 
- <span data-ttu-id="d7f91-1039">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1039">Drivers Lics#</span></span> 
- <span data-ttu-id="d7f91-1040">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1040">Drivers License#</span></span> 
- <span data-ttu-id="d7f91-1041">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1041">Drivers Licenses#</span></span> 
- <span data-ttu-id="d7f91-1042">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1042">Drivers Licence#</span></span> 
- <span data-ttu-id="d7f91-1043">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1043">Drivers Licences#</span></span> 
- <span data-ttu-id="d7f91-1044">Driver'Lic#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1044">Driver'Lic#</span></span> 
- <span data-ttu-id="d7f91-1045">Driver'Lics#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1045">Driver'Lics#</span></span> 
- <span data-ttu-id="d7f91-1046">Driver'License#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1046">Driver'License#</span></span> 
- <span data-ttu-id="d7f91-1047">Driver'Licenses#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1047">Driver'Licenses#</span></span> 
- <span data-ttu-id="d7f91-1048">Driver'Licence#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1048">Driver'Licence#</span></span> 
- <span data-ttu-id="d7f91-1049">Driver'Licences#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1049">Driver'Licences#</span></span> 
- <span data-ttu-id="d7f91-1050">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1050">Driver' Lic#</span></span> 
- <span data-ttu-id="d7f91-1051">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1051">Driver' Lics#</span></span> 
- <span data-ttu-id="d7f91-1052">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1052">Driver' License#</span></span> 
- <span data-ttu-id="d7f91-1053">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1053">Driver' Licenses#</span></span> 
- <span data-ttu-id="d7f91-1054">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1054">Driver' Licence#</span></span> 
- <span data-ttu-id="d7f91-1055">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1055">Driver' Licences#</span></span> 
- <span data-ttu-id="d7f91-1056">Driver'sLic#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1056">Driver'sLic#</span></span> 
- <span data-ttu-id="d7f91-1057">Driver'sLics#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1057">Driver'sLics#</span></span> 
- <span data-ttu-id="d7f91-1058">Driver'sLicense#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1058">Driver'sLicense#</span></span> 
- <span data-ttu-id="d7f91-1059">Driver'sLicenses#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1059">Driver'sLicenses#</span></span> 
- <span data-ttu-id="d7f91-1060">Driver'sLicence#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1060">Driver'sLicence#</span></span> 
- <span data-ttu-id="d7f91-1061">Driver'sLicences#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1061">Driver'sLicences#</span></span> 
- <span data-ttu-id="d7f91-1062">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1062">Driver's Lic#</span></span> 
- <span data-ttu-id="d7f91-1063">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1063">Driver's Lics#</span></span> 
- <span data-ttu-id="d7f91-1064">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1064">Driver's License#</span></span> 
- <span data-ttu-id="d7f91-1065">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1065">Driver's Licenses#</span></span> 
- <span data-ttu-id="d7f91-1066">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1066">Driver's Licence#</span></span> 
- <span data-ttu-id="d7f91-1067">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1067">Driver's Licences#</span></span> 
- <span data-ttu-id="d7f91-1068">Permis de Conduire#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1068">Permis de Conduire#</span></span> 
- <span data-ttu-id="d7f91-1069">号#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1069">id#</span></span> 
- <span data-ttu-id="d7f91-1070">id#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1070">ids#</span></span> 
- <span data-ttu-id="d7f91-1071">idcard card#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1071">idcard card#</span></span> 
- <span data-ttu-id="d7f91-1072">idcard cards#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1072">idcard cards#</span></span> 
- <span data-ttu-id="d7f91-1073">idcard#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1073">idcard#</span></span> 
- <span data-ttu-id="d7f91-1074">identification card#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1074">identification card#</span></span> 
- <span data-ttu-id="d7f91-1075">identification cards#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1075">identification cards#</span></span> 
- <span data-ttu-id="d7f91-1076">id#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1076">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="d7f91-1077">加拿大卫生服务号</span><span class="sxs-lookup"><span data-stu-id="d7f91-1077">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-1078">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-1078">Format</span></span>

<span data-ttu-id="d7f91-1079">10 个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1079">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-1080">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-1080">Pattern</span></span>

<span data-ttu-id="d7f91-1081">10 个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1081">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-1082">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-1082">Checksum</span></span>

<span data-ttu-id="d7f91-1083">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-1083">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-1084">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-1084">Definition</span></span>

<span data-ttu-id="d7f91-1085">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-1085">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-1086">正则表达式 Regex_canada_health_service_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1086">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-1087">找到 Keyword_canada_health_service_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1087">A keyword from Keyword_canada_health_service_number is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-1088">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1088">Keywords</span></span>

#### <a name="keyword_canada_health_service_number"></a><span data-ttu-id="d7f91-1089">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="d7f91-1089">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="d7f91-1090">personal health number</span><span class="sxs-lookup"><span data-stu-id="d7f91-1090">personal health number</span></span>
- <span data-ttu-id="d7f91-1091">patient information</span><span class="sxs-lookup"><span data-stu-id="d7f91-1091">patient information</span></span>
- <span data-ttu-id="d7f91-1092">health services</span><span class="sxs-lookup"><span data-stu-id="d7f91-1092">health services</span></span>
- <span data-ttu-id="d7f91-1093">speciality services</span><span class="sxs-lookup"><span data-stu-id="d7f91-1093">speciality services</span></span>
- <span data-ttu-id="d7f91-1094">automobile accident</span><span class="sxs-lookup"><span data-stu-id="d7f91-1094">automobile accident</span></span>
- <span data-ttu-id="d7f91-1095">patient hospital</span><span class="sxs-lookup"><span data-stu-id="d7f91-1095">patient hospital</span></span>
- <span data-ttu-id="d7f91-1096">psychiatrist</span><span class="sxs-lookup"><span data-stu-id="d7f91-1096">psychiatrist</span></span>
- <span data-ttu-id="d7f91-1097">workers compensation</span><span class="sxs-lookup"><span data-stu-id="d7f91-1097">workers compensation</span></span>
- <span data-ttu-id="d7f91-1098">障碍</span><span class="sxs-lookup"><span data-stu-id="d7f91-1098">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="d7f91-1099">加拿大护照号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-1099">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-1100">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-1100">Format</span></span>

<span data-ttu-id="d7f91-1101">两个大写字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1101">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-1102">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-1102">Pattern</span></span>

<span data-ttu-id="d7f91-1103">两个大写字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1103">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-1104">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-1104">Checksum</span></span>

<span data-ttu-id="d7f91-1105">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-1105">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-1106">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-1106">Definition</span></span>

<span data-ttu-id="d7f91-1107">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-1107">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-1108">正则表达式 Regex_canada_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1108">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-1109">找到来自 Keyword_canada_passport_number 或 Keyword_passport 的关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1109">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

```xml 
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

### <a name="keywords"></a><span data-ttu-id="d7f91-1110">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1110">Keywords</span></span>

#### <a name="keyword_canada_passport_number"></a><span data-ttu-id="d7f91-1111">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="d7f91-1111">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="d7f91-1112">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="d7f91-1112">canadian citizenship</span></span>
- <span data-ttu-id="d7f91-1113">canadian passport</span><span class="sxs-lookup"><span data-stu-id="d7f91-1113">canadian passport</span></span>
- <span data-ttu-id="d7f91-1114">passport application</span><span class="sxs-lookup"><span data-stu-id="d7f91-1114">passport application</span></span>
- <span data-ttu-id="d7f91-1115">passport photos</span><span class="sxs-lookup"><span data-stu-id="d7f91-1115">passport photos</span></span>
- <span data-ttu-id="d7f91-1116">certified translator</span><span class="sxs-lookup"><span data-stu-id="d7f91-1116">certified translator</span></span>
- <span data-ttu-id="d7f91-1117">canadian citizens</span><span class="sxs-lookup"><span data-stu-id="d7f91-1117">canadian citizens</span></span>
- <span data-ttu-id="d7f91-1118">processing times</span><span class="sxs-lookup"><span data-stu-id="d7f91-1118">processing times</span></span>
- <span data-ttu-id="d7f91-1119">renewal application</span><span class="sxs-lookup"><span data-stu-id="d7f91-1119">renewal application</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="d7f91-1120">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="d7f91-1120">Keyword_passport</span></span>

- <span data-ttu-id="d7f91-1121">Passport Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-1121">Passport Number</span></span>
- <span data-ttu-id="d7f91-1122">Passport No</span><span class="sxs-lookup"><span data-stu-id="d7f91-1122">Passport No</span></span>
- <span data-ttu-id="d7f91-1123">Passport #</span><span class="sxs-lookup"><span data-stu-id="d7f91-1123">Passport #</span></span>
- <span data-ttu-id="d7f91-1124">登记卡#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1124">Passport#</span></span>
- <span data-ttu-id="d7f91-1125">PassportID</span><span class="sxs-lookup"><span data-stu-id="d7f91-1125">PassportID</span></span>
- <span data-ttu-id="d7f91-1126">Passportno</span><span class="sxs-lookup"><span data-stu-id="d7f91-1126">Passportno</span></span>
- <span data-ttu-id="d7f91-1127">passportnumber</span><span class="sxs-lookup"><span data-stu-id="d7f91-1127">passportnumber</span></span>
- <span data-ttu-id="d7f91-1128">パスポート</span><span class="sxs-lookup"><span data-stu-id="d7f91-1128">パスポート</span></span>
- <span data-ttu-id="d7f91-1129">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="d7f91-1129">パスポート番号</span></span>
- <span data-ttu-id="d7f91-1130">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="d7f91-1130">パスポートのNum</span></span>
- <span data-ttu-id="d7f91-1131">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="d7f91-1131">パスポート＃</span></span>
- <span data-ttu-id="d7f91-1132">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="d7f91-1132">Numéro de passeport</span></span>
- <span data-ttu-id="d7f91-1133">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="d7f91-1133">Passeport n °</span></span>
- <span data-ttu-id="d7f91-1134">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="d7f91-1134">Passeport Non</span></span>
- <span data-ttu-id="d7f91-1135">Passeport #</span><span class="sxs-lookup"><span data-stu-id="d7f91-1135">Passeport #</span></span>
- <span data-ttu-id="d7f91-1136">Passeport#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1136">Passeport#</span></span>
- <span data-ttu-id="d7f91-1137">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="d7f91-1137">PasseportNon</span></span>
- <span data-ttu-id="d7f91-1138">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="d7f91-1138">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="d7f91-1139">加拿大个人健康标识号 (PHIN)</span><span class="sxs-lookup"><span data-stu-id="d7f91-1139">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-1140">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-1140">Format</span></span>

<span data-ttu-id="d7f91-1141">九个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1141">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-1142">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-1142">Pattern</span></span>

<span data-ttu-id="d7f91-1143">九个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1143">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-1144">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-1144">Checksum</span></span>

<span data-ttu-id="d7f91-1145">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-1145">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-1146">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-1146">Definition</span></span>

<span data-ttu-id="d7f91-1147">DLP 策略 75% 确信在300个字符的邻近度内检测到此类型的敏感信息: 正则表达式 Regex_canada_phin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="d7f91-1148">找到 Keyword_canada_phin 或 Keyword_canada_provinces 中至少有两个关键字。。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1148">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-1149">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1149">Keywords</span></span>

#### <a name="keyword_canada_phin"></a><span data-ttu-id="d7f91-1150">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="d7f91-1150">Keyword_canada_phin</span></span>

- <span data-ttu-id="d7f91-1151">social insurance number</span><span class="sxs-lookup"><span data-stu-id="d7f91-1151">social insurance number</span></span>
- <span data-ttu-id="d7f91-1152">health information act</span><span class="sxs-lookup"><span data-stu-id="d7f91-1152">health information act</span></span>
- <span data-ttu-id="d7f91-1153">income tax information</span><span class="sxs-lookup"><span data-stu-id="d7f91-1153">income tax information</span></span>
- <span data-ttu-id="d7f91-1154">manitoba health</span><span class="sxs-lookup"><span data-stu-id="d7f91-1154">manitoba health</span></span>
- <span data-ttu-id="d7f91-1155">health registration</span><span class="sxs-lookup"><span data-stu-id="d7f91-1155">health registration</span></span>
- <span data-ttu-id="d7f91-1156">prescription purchases</span><span class="sxs-lookup"><span data-stu-id="d7f91-1156">prescription purchases</span></span>
- <span data-ttu-id="d7f91-1157">benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="d7f91-1157">benefit eligibility</span></span>
- <span data-ttu-id="d7f91-1158">personal health</span><span class="sxs-lookup"><span data-stu-id="d7f91-1158">personal health</span></span>
- <span data-ttu-id="d7f91-1159">power of attorney</span><span class="sxs-lookup"><span data-stu-id="d7f91-1159">power of attorney</span></span>
- <span data-ttu-id="d7f91-1160">registration number</span><span class="sxs-lookup"><span data-stu-id="d7f91-1160">registration number</span></span>
- <span data-ttu-id="d7f91-1161">personal health number</span><span class="sxs-lookup"><span data-stu-id="d7f91-1161">personal health number</span></span>
- <span data-ttu-id="d7f91-1162">practitioner referral</span><span class="sxs-lookup"><span data-stu-id="d7f91-1162">practitioner referral</span></span>
- <span data-ttu-id="d7f91-1163">wellness professional</span><span class="sxs-lookup"><span data-stu-id="d7f91-1163">wellness professional</span></span>
- <span data-ttu-id="d7f91-1164">patient referral</span><span class="sxs-lookup"><span data-stu-id="d7f91-1164">patient referral</span></span>
- <span data-ttu-id="d7f91-1165">health and wellness</span><span class="sxs-lookup"><span data-stu-id="d7f91-1165">health and wellness</span></span>

#### <a name="keyword_canada_provinces"></a><span data-ttu-id="d7f91-1166">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="d7f91-1166">Keyword_canada_provinces</span></span>

- <span data-ttu-id="d7f91-1167">Nunavut</span><span class="sxs-lookup"><span data-stu-id="d7f91-1167">Nunavut</span></span>
- <span data-ttu-id="d7f91-1168">省</span><span class="sxs-lookup"><span data-stu-id="d7f91-1168">Quebec</span></span>
- <span data-ttu-id="d7f91-1169">Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="d7f91-1169">Northwest Territories</span></span>
- <span data-ttu-id="d7f91-1170">省</span><span class="sxs-lookup"><span data-stu-id="d7f91-1170">Ontario</span></span>
- <span data-ttu-id="d7f91-1171">British Columbia</span><span class="sxs-lookup"><span data-stu-id="d7f91-1171">British Columbia</span></span>
- <span data-ttu-id="d7f91-1172">Alberta</span><span class="sxs-lookup"><span data-stu-id="d7f91-1172">Alberta</span></span>
- <span data-ttu-id="d7f91-1173">彻</span><span class="sxs-lookup"><span data-stu-id="d7f91-1173">Saskatchewan</span></span>
- <span data-ttu-id="d7f91-1174">Manitoba</span><span class="sxs-lookup"><span data-stu-id="d7f91-1174">Manitoba</span></span>
- <span data-ttu-id="d7f91-1175">Yukon</span><span class="sxs-lookup"><span data-stu-id="d7f91-1175">Yukon</span></span>
- <span data-ttu-id="d7f91-1176">Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="d7f91-1176">Newfoundland and Labrador</span></span>
- <span data-ttu-id="d7f91-1177">New Brunswick</span><span class="sxs-lookup"><span data-stu-id="d7f91-1177">New Brunswick</span></span>
- <span data-ttu-id="d7f91-1178">Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="d7f91-1178">Nova Scotia</span></span>
- <span data-ttu-id="d7f91-1179">Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="d7f91-1179">Prince Edward Island</span></span>
- <span data-ttu-id="d7f91-1180">加拿大</span><span class="sxs-lookup"><span data-stu-id="d7f91-1180">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="d7f91-1181">加拿大社会保险号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-1181">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-1182">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-1182">Format</span></span>

<span data-ttu-id="d7f91-1183">九个数字，包含可选连字符或空格</span><span class="sxs-lookup"><span data-stu-id="d7f91-1183">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-1184">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-1184">Pattern</span></span>

<span data-ttu-id="d7f91-1185">格式</span><span class="sxs-lookup"><span data-stu-id="d7f91-1185">Formatted:</span></span>
- <span data-ttu-id="d7f91-1186">三位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1186">Three digits</span></span> 
- <span data-ttu-id="d7f91-1187">连字符或空格</span><span class="sxs-lookup"><span data-stu-id="d7f91-1187">A hyphen or space</span></span> 
- <span data-ttu-id="d7f91-1188">三位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1188">Three digits</span></span> 
- <span data-ttu-id="d7f91-1189">连字符或空格</span><span class="sxs-lookup"><span data-stu-id="d7f91-1189">A hyphen or space</span></span> 
- <span data-ttu-id="d7f91-1190">三位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1190">Three digits</span></span>

<span data-ttu-id="d7f91-1191">未格式化: 9 个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1191">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-1192">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-1192">Checksum</span></span>

<span data-ttu-id="d7f91-1193">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-1193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-1194">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-1194">Definition</span></span>

<span data-ttu-id="d7f91-1195">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-1195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-1196">函数 Func_canadian_sin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1196">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-1197">至少两个以下任意组合：</span><span class="sxs-lookup"><span data-stu-id="d7f91-1197">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="d7f91-1198">找到 Keyword_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1198">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="d7f91-1199">找到 Keyword_sin_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1199">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="d7f91-1200">函数 Func_eu_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1200">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="d7f91-1201">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1201">The checksum passes.</span></span>

<span data-ttu-id="d7f91-1202">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-1202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-1203">函数 Func_unformatted_canadian_sin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1203">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-1204">找到 Keyword_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1204">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="d7f91-1205">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1205">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-1206">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1206">Keywords</span></span>

#### <a name="keyword_sin"></a><span data-ttu-id="d7f91-1207">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="d7f91-1207">Keyword_sin</span></span>

- <span data-ttu-id="d7f91-1208">sin</span><span class="sxs-lookup"><span data-stu-id="d7f91-1208">sin</span></span> 
- <span data-ttu-id="d7f91-1209">social insurance</span><span class="sxs-lookup"><span data-stu-id="d7f91-1209">social insurance</span></span> 
- <span data-ttu-id="d7f91-1210">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="d7f91-1210">numero d'assurance sociale</span></span> 
- <span data-ttu-id="d7f91-1211">罪</span><span class="sxs-lookup"><span data-stu-id="d7f91-1211">sins</span></span> 
- <span data-ttu-id="d7f91-1212">ssn</span><span class="sxs-lookup"><span data-stu-id="d7f91-1212">ssn</span></span> 
- <span data-ttu-id="d7f91-1213">ssn</span><span class="sxs-lookup"><span data-stu-id="d7f91-1213">ssns</span></span> 
- <span data-ttu-id="d7f91-1214">social security</span><span class="sxs-lookup"><span data-stu-id="d7f91-1214">social security</span></span> 
- <span data-ttu-id="d7f91-1215">numero d'assurance social</span><span class="sxs-lookup"><span data-stu-id="d7f91-1215">numero d'assurance social</span></span> 
- <span data-ttu-id="d7f91-1216">national identification number</span><span class="sxs-lookup"><span data-stu-id="d7f91-1216">national identification number</span></span> 
- <span data-ttu-id="d7f91-1217">national id</span><span class="sxs-lookup"><span data-stu-id="d7f91-1217">national id</span></span> 
- <span data-ttu-id="d7f91-1218">sin#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1218">sin#</span></span> 
- <span data-ttu-id="d7f91-1219">soc ins</span><span class="sxs-lookup"><span data-stu-id="d7f91-1219">soc ins</span></span> 
- <span data-ttu-id="d7f91-1220">social ins</span><span class="sxs-lookup"><span data-stu-id="d7f91-1220">social ins</span></span> 

#### <a name="keyword_sin_collaborative"></a><span data-ttu-id="d7f91-1221">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="d7f91-1221">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="d7f91-1222">driver's license</span><span class="sxs-lookup"><span data-stu-id="d7f91-1222">driver's license</span></span> 
- <span data-ttu-id="d7f91-1223">drivers license</span><span class="sxs-lookup"><span data-stu-id="d7f91-1223">drivers license</span></span> 
- <span data-ttu-id="d7f91-1224">driver's licence</span><span class="sxs-lookup"><span data-stu-id="d7f91-1224">driver's licence</span></span> 
- <span data-ttu-id="d7f91-1225">drivers licence</span><span class="sxs-lookup"><span data-stu-id="d7f91-1225">drivers licence</span></span> 
- <span data-ttu-id="d7f91-1226">DOB</span><span class="sxs-lookup"><span data-stu-id="d7f91-1226">DOB</span></span> 
- <span data-ttu-id="d7f91-1227">出生日期</span><span class="sxs-lookup"><span data-stu-id="d7f91-1227">Birthdate</span></span> 
- <span data-ttu-id="d7f91-1228">生日</span><span class="sxs-lookup"><span data-stu-id="d7f91-1228">Birthday</span></span> 
- <span data-ttu-id="d7f91-1229">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="d7f91-1229">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="d7f91-1230">	智利身份证号</span><span class="sxs-lookup"><span data-stu-id="d7f91-1230">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-1231">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-1231">Format</span></span>

<span data-ttu-id="d7f91-1232">7-8 位数加上分隔符一个校验位或字母</span><span class="sxs-lookup"><span data-stu-id="d7f91-1232">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-1233">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-1233">Pattern</span></span>

<span data-ttu-id="d7f91-1234">7-8 个数字加分隔符：</span><span class="sxs-lookup"><span data-stu-id="d7f91-1234">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="d7f91-1235">1-2 个数字 </span><span class="sxs-lookup"><span data-stu-id="d7f91-1235">1-2 digits</span></span> 
- <span data-ttu-id="d7f91-1236">一个点 </span><span class="sxs-lookup"><span data-stu-id="d7f91-1236">A period</span></span> 
- <span data-ttu-id="d7f91-1237">三个数字 </span><span class="sxs-lookup"><span data-stu-id="d7f91-1237">Three digits</span></span> 
- <span data-ttu-id="d7f91-1238">一个点 </span><span class="sxs-lookup"><span data-stu-id="d7f91-1238">A period</span></span> 
- <span data-ttu-id="d7f91-1239">三个数字 </span><span class="sxs-lookup"><span data-stu-id="d7f91-1239">Three digits</span></span> 
- <span data-ttu-id="d7f91-1240">一个短划线 </span><span class="sxs-lookup"><span data-stu-id="d7f91-1240">A dash</span></span> 
- <span data-ttu-id="d7f91-1241">一个数字或字母（不区分大小写），是校验位</span><span class="sxs-lookup"><span data-stu-id="d7f91-1241">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-1242">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-1242">Checksum</span></span>

<span data-ttu-id="d7f91-1243">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-1243">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-1244">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-1244">Definition</span></span>

<span data-ttu-id="d7f91-1245">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-1245">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-1246">函数 Func_chile_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1246">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-1247">找到 Keyword_chile_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1247">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="d7f91-1248">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1248">The checksum passes.</span></span>

<span data-ttu-id="d7f91-1249">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-1249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-1250">函数 Func_chile_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1250">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-1251">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1251">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-1252">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1252">Keywords</span></span>

#### <a name="keyword_chile_id_card"></a><span data-ttu-id="d7f91-1253">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="d7f91-1253">Keyword_chile_id_card</span></span>

- <span data-ttu-id="d7f91-1254">National Identification Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-1254">National Identification Number</span></span> 
- <span data-ttu-id="d7f91-1255">Identity card</span><span class="sxs-lookup"><span data-stu-id="d7f91-1255">Identity card</span></span> 
- <span data-ttu-id="d7f91-1256">ID</span><span class="sxs-lookup"><span data-stu-id="d7f91-1256">ID</span></span> 
- <span data-ttu-id="d7f91-1257">Id</span><span class="sxs-lookup"><span data-stu-id="d7f91-1257">Identification</span></span> 
- <span data-ttu-id="d7f91-1258">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="d7f91-1258">Rol Único Nacional</span></span> 
- <span data-ttu-id="d7f91-1259">以</span><span class="sxs-lookup"><span data-stu-id="d7f91-1259">RUN</span></span> 
- <span data-ttu-id="d7f91-1260">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="d7f91-1260">Rol Único Tributario</span></span> 
- <span data-ttu-id="d7f91-1261">墨守成规</span><span class="sxs-lookup"><span data-stu-id="d7f91-1261">RUT</span></span> 
- <span data-ttu-id="d7f91-1262">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="d7f91-1262">Cédula de Identidad</span></span> 
- <span data-ttu-id="d7f91-1263">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="d7f91-1263">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="d7f91-1264">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="d7f91-1264">Tarjeta de identificación</span></span> 
- <span data-ttu-id="d7f91-1265">Identificación</span><span class="sxs-lookup"><span data-stu-id="d7f91-1265">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="d7f91-1266">	中国居民身份证号</span><span class="sxs-lookup"><span data-stu-id="d7f91-1266">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-1267">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-1267">Format</span></span>

<span data-ttu-id="d7f91-1268">18 个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1268">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-1269">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-1269">Pattern</span></span>

<span data-ttu-id="d7f91-1270">18 个数字：</span><span class="sxs-lookup"><span data-stu-id="d7f91-1270">18 digits:</span></span>
- <span data-ttu-id="d7f91-1271">其中六个数字是地址代码 </span><span class="sxs-lookup"><span data-stu-id="d7f91-1271">Six digits which are an address code</span></span> 
- <span data-ttu-id="d7f91-1272">八个数字，采用  YYYYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="d7f91-1272">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="d7f91-1273">三个数字，是顺序代码 </span><span class="sxs-lookup"><span data-stu-id="d7f91-1273">Three digits which are an order code</span></span> 
- <span data-ttu-id="d7f91-1274">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="d7f91-1274">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-1275">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-1275">Checksum</span></span>

<span data-ttu-id="d7f91-1276">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-1276">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-1277">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-1277">Definition</span></span>

<span data-ttu-id="d7f91-1278">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-1278">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-1279">函数 Func_china_resident_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1279">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-1280">找到 Keyword_china_resident_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1280">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="d7f91-1281">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1281">The checksum passes.</span></span>

<span data-ttu-id="d7f91-1282">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-1282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-1283">函数 Func_china_resident_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1283">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-1284">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1284">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-1285">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1285">Keywords</span></span>

### <a name="keyword_china_resident_id"></a><span data-ttu-id="d7f91-1286">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="d7f91-1286">Keyword_china_resident_id</span></span>

- <span data-ttu-id="d7f91-1287">Resident Identity Card</span><span class="sxs-lookup"><span data-stu-id="d7f91-1287">Resident Identity Card</span></span> 
- <span data-ttu-id="d7f91-1288">台湾</span><span class="sxs-lookup"><span data-stu-id="d7f91-1288">PRC</span></span> 
- <span data-ttu-id="d7f91-1289">National Identification Card</span><span class="sxs-lookup"><span data-stu-id="d7f91-1289">National Identification Card</span></span> 
- <span data-ttu-id="d7f91-1290">身份证</span><span class="sxs-lookup"><span data-stu-id="d7f91-1290">身份证</span></span> 
- <span data-ttu-id="d7f91-1291">居民 身份证</span><span class="sxs-lookup"><span data-stu-id="d7f91-1291">居民 身份证</span></span> 
- <span data-ttu-id="d7f91-1292">居民身份证</span><span class="sxs-lookup"><span data-stu-id="d7f91-1292">居民身份证</span></span> 
- <span data-ttu-id="d7f91-1293">鉴定</span><span class="sxs-lookup"><span data-stu-id="d7f91-1293">鉴定</span></span> 
- <span data-ttu-id="d7f91-1294">身分證</span><span class="sxs-lookup"><span data-stu-id="d7f91-1294">身分證</span></span> 
- <span data-ttu-id="d7f91-1295">居民身份證</span><span class="sxs-lookup"><span data-stu-id="d7f91-1295">居民 身份證</span></span>
- <span data-ttu-id="d7f91-1296">鑑定</span><span class="sxs-lookup"><span data-stu-id="d7f91-1296">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="d7f91-1297">信用卡号</span><span class="sxs-lookup"><span data-stu-id="d7f91-1297">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-1298">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-1298">Format</span></span>

<span data-ttu-id="d7f91-1299">16个数字, 可以是格式化或无格式 (dddddddddddddddd), 并且必须通过 Luhn 测试。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1299">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-1300">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-1300">Pattern</span></span>

<span data-ttu-id="d7f91-1301">非常复杂且强大的模式，检测到来自世界各地所有重要品牌的卡，包括 Visa、万事达卡、发现卡、JCB卡、美国运通卡、礼品卡以及大莱卡。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1301">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-1302">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-1302">Checksum</span></span>

<span data-ttu-id="d7f91-1303">是，Luhn 校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-1303">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-1304">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-1304">Definition</span></span>

<span data-ttu-id="d7f91-1305">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-1305">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-1306">函数 Func_credit_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1306">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-1307">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="d7f91-1307">One of the following is true:</span></span>
    - <span data-ttu-id="d7f91-1308">找到 Keyword_cc_verification 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1308">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="d7f91-1309">找到 Keyword_cc_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1309">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="d7f91-1310">函数 Func_expiration_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1310">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="d7f91-1311">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1311">The checksum passes.</span></span>

<span data-ttu-id="d7f91-1312">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-1312">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-1313">函数 Func_credit_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1313">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-1314">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1314">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-1315">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1315">Keywords</span></span>

#### <a name="keyword_cc_verification"></a><span data-ttu-id="d7f91-1316">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="d7f91-1316">Keyword_cc_verification</span></span>

- <span data-ttu-id="d7f91-1317">card verification</span><span class="sxs-lookup"><span data-stu-id="d7f91-1317">card verification</span></span>
- <span data-ttu-id="d7f91-1318">card identification number</span><span class="sxs-lookup"><span data-stu-id="d7f91-1318">card identification number</span></span>
- <span data-ttu-id="d7f91-1319">cvn</span><span class="sxs-lookup"><span data-stu-id="d7f91-1319">cvn</span></span>
- <span data-ttu-id="d7f91-1320">cid</span><span class="sxs-lookup"><span data-stu-id="d7f91-1320">cid</span></span>
- <span data-ttu-id="d7f91-1321">cvc2</span><span class="sxs-lookup"><span data-stu-id="d7f91-1321">cvc2</span></span>
- <span data-ttu-id="d7f91-1322">cvv2</span><span class="sxs-lookup"><span data-stu-id="d7f91-1322">cvv2</span></span>
- <span data-ttu-id="d7f91-1323">pin block</span><span class="sxs-lookup"><span data-stu-id="d7f91-1323">pin block</span></span>
- <span data-ttu-id="d7f91-1324">security code</span><span class="sxs-lookup"><span data-stu-id="d7f91-1324">security code</span></span>
- <span data-ttu-id="d7f91-1325">security number</span><span class="sxs-lookup"><span data-stu-id="d7f91-1325">security number</span></span>
- <span data-ttu-id="d7f91-1326">security no</span><span class="sxs-lookup"><span data-stu-id="d7f91-1326">security no</span></span>
- <span data-ttu-id="d7f91-1327">issue number</span><span class="sxs-lookup"><span data-stu-id="d7f91-1327">issue number</span></span>
- <span data-ttu-id="d7f91-1328">issue no</span><span class="sxs-lookup"><span data-stu-id="d7f91-1328">issue no</span></span>
- <span data-ttu-id="d7f91-1329">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="d7f91-1329">cryptogramme</span></span>
- <span data-ttu-id="d7f91-1330">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="d7f91-1330">numéro de sécurité</span></span>
- <span data-ttu-id="d7f91-1331">numero de securite</span><span class="sxs-lookup"><span data-stu-id="d7f91-1331">numero de securite</span></span>
- <span data-ttu-id="d7f91-1332">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="d7f91-1332">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="d7f91-1333">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="d7f91-1333">kreditkartenprufnummer</span></span>
- <span data-ttu-id="d7f91-1334">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="d7f91-1334">prüfziffer</span></span>
- <span data-ttu-id="d7f91-1335">prufziffer</span><span class="sxs-lookup"><span data-stu-id="d7f91-1335">prufziffer</span></span>
- <span data-ttu-id="d7f91-1336">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="d7f91-1336">sicherheits Kode</span></span>
- <span data-ttu-id="d7f91-1337">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="d7f91-1337">sicherheitscode</span></span>
- <span data-ttu-id="d7f91-1338">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="d7f91-1338">sicherheitsnummer</span></span>
- <span data-ttu-id="d7f91-1339">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="d7f91-1339">verfalldatum</span></span>
- <span data-ttu-id="d7f91-1340">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="d7f91-1340">codice di verifica</span></span>
- <span data-ttu-id="d7f91-1341">货.</span><span class="sxs-lookup"><span data-stu-id="d7f91-1341">cod.</span></span> <span data-ttu-id="d7f91-1342">sicurezza</span><span class="sxs-lookup"><span data-stu-id="d7f91-1342">sicurezza</span></span>
- <span data-ttu-id="d7f91-1343">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="d7f91-1343">cod sicurezza</span></span>
- <span data-ttu-id="d7f91-1344">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="d7f91-1344">n autorizzazione</span></span>
- <span data-ttu-id="d7f91-1345">código</span><span class="sxs-lookup"><span data-stu-id="d7f91-1345">código</span></span>
- <span data-ttu-id="d7f91-1346">codigo</span><span class="sxs-lookup"><span data-stu-id="d7f91-1346">codigo</span></span>
- <span data-ttu-id="d7f91-1347">货.</span><span class="sxs-lookup"><span data-stu-id="d7f91-1347">cod.</span></span> <span data-ttu-id="d7f91-1348">seg</span><span class="sxs-lookup"><span data-stu-id="d7f91-1348">seg</span></span>
- <span data-ttu-id="d7f91-1349">cod seg</span><span class="sxs-lookup"><span data-stu-id="d7f91-1349">cod seg</span></span>
- <span data-ttu-id="d7f91-1350">código de segurança</span><span class="sxs-lookup"><span data-stu-id="d7f91-1350">código de segurança</span></span>
- <span data-ttu-id="d7f91-1351">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="d7f91-1351">codigo de seguranca</span></span>
- <span data-ttu-id="d7f91-1352">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="d7f91-1352">codigo de segurança</span></span>
- <span data-ttu-id="d7f91-1353">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="d7f91-1353">código de seguranca</span></span>
- <span data-ttu-id="d7f91-1354">cód.</span><span class="sxs-lookup"><span data-stu-id="d7f91-1354">cód.</span></span> <span data-ttu-id="d7f91-1355">segurança</span><span class="sxs-lookup"><span data-stu-id="d7f91-1355">segurança</span></span>
- <span data-ttu-id="d7f91-1356">货.</span><span class="sxs-lookup"><span data-stu-id="d7f91-1356">cod.</span></span> <span data-ttu-id="d7f91-1357">seguranca 货到付款。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1357">seguranca cod.</span></span> <span data-ttu-id="d7f91-1358">segurança</span><span class="sxs-lookup"><span data-stu-id="d7f91-1358">segurança</span></span>
- <span data-ttu-id="d7f91-1359">cód.</span><span class="sxs-lookup"><span data-stu-id="d7f91-1359">cód.</span></span> <span data-ttu-id="d7f91-1360">seguranca</span><span class="sxs-lookup"><span data-stu-id="d7f91-1360">seguranca</span></span>
- <span data-ttu-id="d7f91-1361">cód segurança</span><span class="sxs-lookup"><span data-stu-id="d7f91-1361">cód segurança</span></span>
- <span data-ttu-id="d7f91-1362">货到付款 seguranca 货到付款 segurança</span><span class="sxs-lookup"><span data-stu-id="d7f91-1362">cod seguranca cod segurança</span></span>
- <span data-ttu-id="d7f91-1363">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="d7f91-1363">cód seguranca</span></span>
- <span data-ttu-id="d7f91-1364">número de verificação</span><span class="sxs-lookup"><span data-stu-id="d7f91-1364">número de verificação</span></span>
- <span data-ttu-id="d7f91-1365">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="d7f91-1365">numero de verificacao</span></span>
- <span data-ttu-id="d7f91-1366">ablauf</span><span class="sxs-lookup"><span data-stu-id="d7f91-1366">ablauf</span></span>
- <span data-ttu-id="d7f91-1367">gültig bis</span><span class="sxs-lookup"><span data-stu-id="d7f91-1367">gültig bis</span></span>
- <span data-ttu-id="d7f91-1368">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="d7f91-1368">gültigkeitsdatum</span></span>
- <span data-ttu-id="d7f91-1369">gultig bis</span><span class="sxs-lookup"><span data-stu-id="d7f91-1369">gultig bis</span></span>
- <span data-ttu-id="d7f91-1370">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="d7f91-1370">gultigkeitsdatum</span></span>
- <span data-ttu-id="d7f91-1371">scadenza</span><span class="sxs-lookup"><span data-stu-id="d7f91-1371">scadenza</span></span>
- <span data-ttu-id="d7f91-1372">data scad</span><span class="sxs-lookup"><span data-stu-id="d7f91-1372">data scad</span></span>
- <span data-ttu-id="d7f91-1373">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="d7f91-1373">fecha de expiracion</span></span>
- <span data-ttu-id="d7f91-1374">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="d7f91-1374">fecha de venc</span></span>
- <span data-ttu-id="d7f91-1375">vencimiento</span><span class="sxs-lookup"><span data-stu-id="d7f91-1375">vencimiento</span></span>
- <span data-ttu-id="d7f91-1376">válido hasta</span><span class="sxs-lookup"><span data-stu-id="d7f91-1376">válido hasta</span></span>
- <span data-ttu-id="d7f91-1377">valido hasta</span><span class="sxs-lookup"><span data-stu-id="d7f91-1377">valido hasta</span></span>
- <span data-ttu-id="d7f91-1378">vto</span><span class="sxs-lookup"><span data-stu-id="d7f91-1378">vto</span></span>
- <span data-ttu-id="d7f91-1379">data de expiração</span><span class="sxs-lookup"><span data-stu-id="d7f91-1379">data de expiração</span></span>
- <span data-ttu-id="d7f91-1380">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="d7f91-1380">data de expiracao</span></span>
- <span data-ttu-id="d7f91-1381">data em que expira</span><span class="sxs-lookup"><span data-stu-id="d7f91-1381">data em que expira</span></span>
- <span data-ttu-id="d7f91-1382">validade</span><span class="sxs-lookup"><span data-stu-id="d7f91-1382">validade</span></span>
- <span data-ttu-id="d7f91-1383">valor</span><span class="sxs-lookup"><span data-stu-id="d7f91-1383">valor</span></span>
- <span data-ttu-id="d7f91-1384">vencimento</span><span class="sxs-lookup"><span data-stu-id="d7f91-1384">vencimento</span></span>
- <span data-ttu-id="d7f91-1385">Venc</span><span class="sxs-lookup"><span data-stu-id="d7f91-1385">Venc</span></span> 

#### <a name="keyword_cc_name"></a><span data-ttu-id="d7f91-1386">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="d7f91-1386">Keyword_cc_name</span></span>

- <span data-ttu-id="d7f91-1387">amex</span><span class="sxs-lookup"><span data-stu-id="d7f91-1387">amex</span></span>
- <span data-ttu-id="d7f91-1388">american express</span><span class="sxs-lookup"><span data-stu-id="d7f91-1388">american express</span></span>
- <span data-ttu-id="d7f91-1389">americanexpress</span><span class="sxs-lookup"><span data-stu-id="d7f91-1389">americanexpress</span></span>
- <span data-ttu-id="d7f91-1390">反之</span><span class="sxs-lookup"><span data-stu-id="d7f91-1390">Visa</span></span>
- <span data-ttu-id="d7f91-1391">mastercard</span><span class="sxs-lookup"><span data-stu-id="d7f91-1391">mastercard</span></span>
- <span data-ttu-id="d7f91-1392">Master Card</span><span class="sxs-lookup"><span data-stu-id="d7f91-1392">master card</span></span>
- <span data-ttu-id="d7f91-1393">emc</span><span class="sxs-lookup"><span data-stu-id="d7f91-1393">mc</span></span> 
- <span data-ttu-id="d7f91-1394">mastercards</span><span class="sxs-lookup"><span data-stu-id="d7f91-1394">mastercards</span></span>
- <span data-ttu-id="d7f91-1395">master cards</span><span class="sxs-lookup"><span data-stu-id="d7f91-1395">master cards</span></span>
- <span data-ttu-id="d7f91-1396">diner's Club</span><span class="sxs-lookup"><span data-stu-id="d7f91-1396">diner's Club</span></span>
- <span data-ttu-id="d7f91-1397">diners club</span><span class="sxs-lookup"><span data-stu-id="d7f91-1397">diners club</span></span>
- <span data-ttu-id="d7f91-1398">dinersclub</span><span class="sxs-lookup"><span data-stu-id="d7f91-1398">dinersclub</span></span>
- <span data-ttu-id="d7f91-1399">discover card</span><span class="sxs-lookup"><span data-stu-id="d7f91-1399">discover card</span></span>
- <span data-ttu-id="d7f91-1400">discovercard</span><span class="sxs-lookup"><span data-stu-id="d7f91-1400">discovercard</span></span>
- <span data-ttu-id="d7f91-1401">discover cards</span><span class="sxs-lookup"><span data-stu-id="d7f91-1401">discover cards</span></span>
- <span data-ttu-id="d7f91-1402">JCB</span><span class="sxs-lookup"><span data-stu-id="d7f91-1402">JCB</span></span>
- <span data-ttu-id="d7f91-1403">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="d7f91-1403">japanese card bureau</span></span>
- <span data-ttu-id="d7f91-1404">carte blanche</span><span class="sxs-lookup"><span data-stu-id="d7f91-1404">carte blanche</span></span>
- <span data-ttu-id="d7f91-1405">carteblanche</span><span class="sxs-lookup"><span data-stu-id="d7f91-1405">carteblanche</span></span>
- <span data-ttu-id="d7f91-1406">credit card</span><span class="sxs-lookup"><span data-stu-id="d7f91-1406">credit card</span></span>
- <span data-ttu-id="d7f91-1407">收件人#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1407">cc#</span></span>
- <span data-ttu-id="d7f91-1408">cc #:</span><span class="sxs-lookup"><span data-stu-id="d7f91-1408">cc#:</span></span>
- <span data-ttu-id="d7f91-1409">expiration date</span><span class="sxs-lookup"><span data-stu-id="d7f91-1409">expiration date</span></span>
- <span data-ttu-id="d7f91-1410">exp date</span><span class="sxs-lookup"><span data-stu-id="d7f91-1410">exp date</span></span>
- <span data-ttu-id="d7f91-1411">expiry date</span><span class="sxs-lookup"><span data-stu-id="d7f91-1411">expiry date</span></span>
- <span data-ttu-id="d7f91-1412">date d’expiration</span><span class="sxs-lookup"><span data-stu-id="d7f91-1412">date d’expiration</span></span>
- <span data-ttu-id="d7f91-1413">date d'exp</span><span class="sxs-lookup"><span data-stu-id="d7f91-1413">date d'exp</span></span>
- <span data-ttu-id="d7f91-1414">date expiration</span><span class="sxs-lookup"><span data-stu-id="d7f91-1414">date expiration</span></span>
- <span data-ttu-id="d7f91-1415">bank card</span><span class="sxs-lookup"><span data-stu-id="d7f91-1415">bank card</span></span>
- <span data-ttu-id="d7f91-1416">bankcard</span><span class="sxs-lookup"><span data-stu-id="d7f91-1416">bankcard</span></span>
- <span data-ttu-id="d7f91-1417">card number</span><span class="sxs-lookup"><span data-stu-id="d7f91-1417">card number</span></span>
- <span data-ttu-id="d7f91-1418">card num</span><span class="sxs-lookup"><span data-stu-id="d7f91-1418">card num</span></span>
- <span data-ttu-id="d7f91-1419">cardnumber</span><span class="sxs-lookup"><span data-stu-id="d7f91-1419">cardnumber</span></span>
- <span data-ttu-id="d7f91-1420">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="d7f91-1420">cardnumbers</span></span>
- <span data-ttu-id="d7f91-1421">card numbers</span><span class="sxs-lookup"><span data-stu-id="d7f91-1421">card numbers</span></span>
- <span data-ttu-id="d7f91-1422">creditcard</span><span class="sxs-lookup"><span data-stu-id="d7f91-1422">creditcard</span></span>
- <span data-ttu-id="d7f91-1423">credit cards</span><span class="sxs-lookup"><span data-stu-id="d7f91-1423">credit cards</span></span>
- <span data-ttu-id="d7f91-1424">creditcards</span><span class="sxs-lookup"><span data-stu-id="d7f91-1424">creditcards</span></span>
- <span data-ttu-id="d7f91-1425">ccn</span><span class="sxs-lookup"><span data-stu-id="d7f91-1425">ccn</span></span>
- <span data-ttu-id="d7f91-1426">card holder</span><span class="sxs-lookup"><span data-stu-id="d7f91-1426">card holder</span></span>
- <span data-ttu-id="d7f91-1427">持卡人</span><span class="sxs-lookup"><span data-stu-id="d7f91-1427">cardholder</span></span>
- <span data-ttu-id="d7f91-1428">card holders</span><span class="sxs-lookup"><span data-stu-id="d7f91-1428">card holders</span></span>
- <span data-ttu-id="d7f91-1429">cardholders</span><span class="sxs-lookup"><span data-stu-id="d7f91-1429">cardholders</span></span>
- <span data-ttu-id="d7f91-1430">check card</span><span class="sxs-lookup"><span data-stu-id="d7f91-1430">check card</span></span>
- <span data-ttu-id="d7f91-1431">checkcard</span><span class="sxs-lookup"><span data-stu-id="d7f91-1431">checkcard</span></span>
- <span data-ttu-id="d7f91-1432">check cards</span><span class="sxs-lookup"><span data-stu-id="d7f91-1432">check cards</span></span>
- <span data-ttu-id="d7f91-1433">checkcards</span><span class="sxs-lookup"><span data-stu-id="d7f91-1433">checkcards</span></span>
- <span data-ttu-id="d7f91-1434">debit card</span><span class="sxs-lookup"><span data-stu-id="d7f91-1434">debit card</span></span>
- <span data-ttu-id="d7f91-1435">debitcard</span><span class="sxs-lookup"><span data-stu-id="d7f91-1435">debitcard</span></span>
- <span data-ttu-id="d7f91-1436">debit cards</span><span class="sxs-lookup"><span data-stu-id="d7f91-1436">debit cards</span></span>
- <span data-ttu-id="d7f91-1437">debitcards</span><span class="sxs-lookup"><span data-stu-id="d7f91-1437">debitcards</span></span>
- <span data-ttu-id="d7f91-1438">atm card</span><span class="sxs-lookup"><span data-stu-id="d7f91-1438">atm card</span></span>
- <span data-ttu-id="d7f91-1439">atmcard</span><span class="sxs-lookup"><span data-stu-id="d7f91-1439">atmcard</span></span>
- <span data-ttu-id="d7f91-1440">atm cards</span><span class="sxs-lookup"><span data-stu-id="d7f91-1440">atm cards</span></span>
- <span data-ttu-id="d7f91-1441">atmcards</span><span class="sxs-lookup"><span data-stu-id="d7f91-1441">atmcards</span></span>
- <span data-ttu-id="d7f91-1442">enroute</span><span class="sxs-lookup"><span data-stu-id="d7f91-1442">enroute</span></span>
- <span data-ttu-id="d7f91-1443">en route</span><span class="sxs-lookup"><span data-stu-id="d7f91-1443">en route</span></span>
- <span data-ttu-id="d7f91-1444">card type</span><span class="sxs-lookup"><span data-stu-id="d7f91-1444">card type</span></span>
- <span data-ttu-id="d7f91-1445">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="d7f91-1445">carte bancaire</span></span>
- <span data-ttu-id="d7f91-1446">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="d7f91-1446">carte de crédit</span></span>
- <span data-ttu-id="d7f91-1447">carte de credit</span><span class="sxs-lookup"><span data-stu-id="d7f91-1447">carte de credit</span></span>
- <span data-ttu-id="d7f91-1448">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="d7f91-1448">numéro de carte</span></span>
- <span data-ttu-id="d7f91-1449">numero de carte</span><span class="sxs-lookup"><span data-stu-id="d7f91-1449">numero de carte</span></span>
- <span data-ttu-id="d7f91-1450">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="d7f91-1450">nº de la carte</span></span>
- <span data-ttu-id="d7f91-1451">nº de carte</span><span class="sxs-lookup"><span data-stu-id="d7f91-1451">nº de carte</span></span>
- <span data-ttu-id="d7f91-1452">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="d7f91-1452">kreditkarte</span></span>
- <span data-ttu-id="d7f91-1453">karte</span><span class="sxs-lookup"><span data-stu-id="d7f91-1453">karte</span></span>
- <span data-ttu-id="d7f91-1454">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="d7f91-1454">karteninhaber</span></span>
- <span data-ttu-id="d7f91-1455">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="d7f91-1455">karteninhabers</span></span>
- <span data-ttu-id="d7f91-1456">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="d7f91-1456">kreditkarteninhaber</span></span>
- <span data-ttu-id="d7f91-1457">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="d7f91-1457">kreditkarteninstitut</span></span>
- <span data-ttu-id="d7f91-1458">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="d7f91-1458">kreditkartentyp</span></span>
- <span data-ttu-id="d7f91-1459">eigentümername</span><span class="sxs-lookup"><span data-stu-id="d7f91-1459">eigentümername</span></span>
- <span data-ttu-id="d7f91-1460">kartennr</span><span class="sxs-lookup"><span data-stu-id="d7f91-1460">kartennr</span></span> 
- <span data-ttu-id="d7f91-1461">kartennummer</span><span class="sxs-lookup"><span data-stu-id="d7f91-1461">kartennummer</span></span>
- <span data-ttu-id="d7f91-1462">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="d7f91-1462">kreditkartennummer</span></span>
- <span data-ttu-id="d7f91-1463">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="d7f91-1463">kreditkarten-nummer</span></span>
- <span data-ttu-id="d7f91-1464">carta di credito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1464">carta di credito</span></span>
- <span data-ttu-id="d7f91-1465">carta credito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1465">carta credito</span></span>
- <span data-ttu-id="d7f91-1466">carta</span><span class="sxs-lookup"><span data-stu-id="d7f91-1466">carta</span></span>
- <span data-ttu-id="d7f91-1467">n carta</span><span class="sxs-lookup"><span data-stu-id="d7f91-1467">n carta</span></span>
- <span data-ttu-id="d7f91-1468">führerschein-nr.</span><span class="sxs-lookup"><span data-stu-id="d7f91-1468">nr.</span></span> <span data-ttu-id="d7f91-1469">carta</span><span class="sxs-lookup"><span data-stu-id="d7f91-1469">carta</span></span>
- <span data-ttu-id="d7f91-1470">nr carta</span><span class="sxs-lookup"><span data-stu-id="d7f91-1470">nr carta</span></span>
- <span data-ttu-id="d7f91-1471">numero carta</span><span class="sxs-lookup"><span data-stu-id="d7f91-1471">numero carta</span></span>
- <span data-ttu-id="d7f91-1472">numero della carta</span><span class="sxs-lookup"><span data-stu-id="d7f91-1472">numero della carta</span></span>
- <span data-ttu-id="d7f91-1473">numero di carta</span><span class="sxs-lookup"><span data-stu-id="d7f91-1473">numero di carta</span></span>
- <span data-ttu-id="d7f91-1474">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1474">tarjeta credito</span></span>
- <span data-ttu-id="d7f91-1475">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1475">tarjeta de credito</span></span>
- <span data-ttu-id="d7f91-1476">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1476">tarjeta crédito</span></span>
- <span data-ttu-id="d7f91-1477">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1477">tarjeta de crédito</span></span>
- <span data-ttu-id="d7f91-1478">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="d7f91-1478">tarjeta de atm</span></span>
- <span data-ttu-id="d7f91-1479">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="d7f91-1479">tarjeta atm</span></span>
- <span data-ttu-id="d7f91-1480">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1480">tarjeta debito</span></span>
- <span data-ttu-id="d7f91-1481">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1481">tarjeta de debito</span></span>
- <span data-ttu-id="d7f91-1482">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1482">tarjeta débito</span></span>
- <span data-ttu-id="d7f91-1483">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1483">tarjeta de débito</span></span>
- <span data-ttu-id="d7f91-1484">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="d7f91-1484">nº de tarjeta</span></span>
- <span data-ttu-id="d7f91-1485">不。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1485">no.</span></span> <span data-ttu-id="d7f91-1486">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="d7f91-1486">de tarjeta</span></span>
- <span data-ttu-id="d7f91-1487">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="d7f91-1487">no de tarjeta</span></span>
- <span data-ttu-id="d7f91-1488">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="d7f91-1488">numero de tarjeta</span></span>
- <span data-ttu-id="d7f91-1489">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="d7f91-1489">número de tarjeta</span></span>
- <span data-ttu-id="d7f91-1490">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="d7f91-1490">tarjeta no</span></span>
- <span data-ttu-id="d7f91-1491">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="d7f91-1491">tarjetahabiente</span></span>
- <span data-ttu-id="d7f91-1492">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1492">cartão de crédito</span></span>
- <span data-ttu-id="d7f91-1493">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1493">cartão de credito</span></span>
- <span data-ttu-id="d7f91-1494">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1494">cartao de crédito</span></span>
- <span data-ttu-id="d7f91-1495">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1495">cartao de credito</span></span>
- <span data-ttu-id="d7f91-1496">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1496">cartão de débito</span></span>
- <span data-ttu-id="d7f91-1497">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1497">cartao de débito</span></span>
- <span data-ttu-id="d7f91-1498">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1498">cartão de debito</span></span>
- <span data-ttu-id="d7f91-1499">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1499">cartao de debito</span></span>
- <span data-ttu-id="d7f91-1500">débito automático</span><span class="sxs-lookup"><span data-stu-id="d7f91-1500">débito automático</span></span>
- <span data-ttu-id="d7f91-1501">debito automatico</span><span class="sxs-lookup"><span data-stu-id="d7f91-1501">debito automatico</span></span>
- <span data-ttu-id="d7f91-1502">número do cartão</span><span class="sxs-lookup"><span data-stu-id="d7f91-1502">número do cartão</span></span>
- <span data-ttu-id="d7f91-1503">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="d7f91-1503">numero do cartão</span></span> 
- <span data-ttu-id="d7f91-1504">número do cartao</span><span class="sxs-lookup"><span data-stu-id="d7f91-1504">número do cartao</span></span>
- <span data-ttu-id="d7f91-1505">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="d7f91-1505">numero do cartao</span></span>
- <span data-ttu-id="d7f91-1506">número de cartão</span><span class="sxs-lookup"><span data-stu-id="d7f91-1506">número de cartão</span></span>
- <span data-ttu-id="d7f91-1507">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="d7f91-1507">numero de cartão</span></span>
- <span data-ttu-id="d7f91-1508">número de cartao</span><span class="sxs-lookup"><span data-stu-id="d7f91-1508">número de cartao</span></span>
- <span data-ttu-id="d7f91-1509">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="d7f91-1509">numero de cartao</span></span>
- <span data-ttu-id="d7f91-1510">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="d7f91-1510">nº do cartão</span></span>
- <span data-ttu-id="d7f91-1511">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="d7f91-1511">nº do cartao</span></span>
- <span data-ttu-id="d7f91-1512">n º。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1512">nº.</span></span> <span data-ttu-id="d7f91-1513">do cartão</span><span class="sxs-lookup"><span data-stu-id="d7f91-1513">do cartão</span></span>
- <span data-ttu-id="d7f91-1514">no do cartão</span><span class="sxs-lookup"><span data-stu-id="d7f91-1514">no do cartão</span></span>
- <span data-ttu-id="d7f91-1515">no do cartao</span><span class="sxs-lookup"><span data-stu-id="d7f91-1515">no do cartao</span></span>
- <span data-ttu-id="d7f91-1516">不。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1516">no.</span></span> <span data-ttu-id="d7f91-1517">do cartão</span><span class="sxs-lookup"><span data-stu-id="d7f91-1517">do cartão</span></span>
- <span data-ttu-id="d7f91-1518">不。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1518">no.</span></span> <span data-ttu-id="d7f91-1519">do cartao</span><span class="sxs-lookup"><span data-stu-id="d7f91-1519">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="d7f91-1520">	克罗地亚身份证号</span><span class="sxs-lookup"><span data-stu-id="d7f91-1520">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-1521">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-1521">Format</span></span>

<span data-ttu-id="d7f91-1522">九个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1522">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-1523">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-1523">Pattern</span></span>

<span data-ttu-id="d7f91-1524">九个连续的数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1524">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-1525">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-1525">Checksum</span></span>

<span data-ttu-id="d7f91-1526">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-1526">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-1527">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-1527">Definition</span></span>

<span data-ttu-id="d7f91-1528">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-1528">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-1529">函数 Func_croatia_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1529">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-1530">找到 Keyword_croatia_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1530">A keyword from Keyword_croatia_id_card is found.</span></span>

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-1531">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1531">Keywords</span></span>

#### <a name="keyword_croatia_id_card"></a><span data-ttu-id="d7f91-1532">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="d7f91-1532">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="d7f91-1533">Croatian identity card</span><span class="sxs-lookup"><span data-stu-id="d7f91-1533">Croatian identity card</span></span>
- <span data-ttu-id="d7f91-1534">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="d7f91-1534">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="d7f91-1535">	Croatia Personal Identification (OIB) Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-1535">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-1536">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-1536">Format</span></span>

<span data-ttu-id="d7f91-1537">11 个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1537">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-1538">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-1538">Pattern</span></span>

<span data-ttu-id="d7f91-1539">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="d7f91-1539">11 digits:</span></span>
- <span data-ttu-id="d7f91-1540">10 个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1540">10 digits</span></span> 
- <span data-ttu-id="d7f91-1541">最后一个数字是用于国际数据交换目的的校验位, 字母 HR 将加上11位数字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1541">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-1542">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-1542">Checksum</span></span>

<span data-ttu-id="d7f91-1543">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-1543">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-1544">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-1544">Definition</span></span>

<span data-ttu-id="d7f91-1545">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-1545">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-1546">函数 Func_croatia_oib_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1546">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-1547">找到 Keyword_croatia_oib_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1547">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="d7f91-1548">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1548">The checksum passes.</span></span>

<span data-ttu-id="d7f91-1549">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-1549">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-1550">函数 Func_croatia_oib_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1550">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-1551">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1551">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-1552">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1552">Keywords</span></span>

#### <a name="keyword_croatia_oib_number"></a><span data-ttu-id="d7f91-1553">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="d7f91-1553">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="d7f91-1554">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-1554">Personal Identification Number</span></span>
- <span data-ttu-id="d7f91-1555">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="d7f91-1555">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="d7f91-1556">OIB</span><span class="sxs-lookup"><span data-stu-id="d7f91-1556">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="d7f91-1557">捷克个人识别码</span><span class="sxs-lookup"><span data-stu-id="d7f91-1557">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-1558">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-1558">Format</span></span>

<span data-ttu-id="d7f91-1559">9个带可选正斜杠 (旧格式) 的数字, 带可选正斜杠的10个数字 (新的格式)</span><span class="sxs-lookup"><span data-stu-id="d7f91-1559">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-1560">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-1560">Pattern</span></span>

<span data-ttu-id="d7f91-1561">9个数字 (旧格式):</span><span class="sxs-lookup"><span data-stu-id="d7f91-1561">Nine digits (old format):</span></span>
- <span data-ttu-id="d7f91-1562">九个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1562">Nine digits</span></span>

<span data-ttu-id="d7f91-1563">OR</span><span class="sxs-lookup"><span data-stu-id="d7f91-1563">OR</span></span>

- <span data-ttu-id="d7f91-1564">代表出生日期的六个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1564">Six digits that represent date of birth</span></span>
- <span data-ttu-id="d7f91-1565">一个正斜杠 </span><span class="sxs-lookup"><span data-stu-id="d7f91-1565">A forward slash</span></span>
- <span data-ttu-id="d7f91-1566">三位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1566">Three digits</span></span>

<span data-ttu-id="d7f91-1567">10个数字 (新格式):</span><span class="sxs-lookup"><span data-stu-id="d7f91-1567">10 digits (new format):</span></span>
- <span data-ttu-id="d7f91-1568">10 个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1568">10 digits</span></span>

<span data-ttu-id="d7f91-1569">OR</span><span class="sxs-lookup"><span data-stu-id="d7f91-1569">OR</span></span>

- <span data-ttu-id="d7f91-1570">代表出生日期的六个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1570">Six digits that represent date of birth</span></span>
- <span data-ttu-id="d7f91-1571">一个正斜杠 </span><span class="sxs-lookup"><span data-stu-id="d7f91-1571">A forward slash</span></span> 
- <span data-ttu-id="d7f91-1572">四个数字, 其中最后一个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="d7f91-1572">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-1573">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-1573">Checksum</span></span>

<span data-ttu-id="d7f91-1574">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-1574">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-1575">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-1575">Definition</span></span>

<span data-ttu-id="d7f91-1576">DLP 策略 85% 确信在300个字符的邻近度内检测到此类型的敏感信息: 函数 Func_czech_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1576">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="d7f91-1577">找到 Keyword_czech_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1577">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="d7f91-1578">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1578">The checksum passes.</span></span>

```xml
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="d7f91-1579">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1579">Keywords</span></span>

- <span data-ttu-id="d7f91-1580">捷克个人识别码</span><span class="sxs-lookup"><span data-stu-id="d7f91-1580">czech personal identity number</span></span>
- <span data-ttu-id="d7f91-1581">Rodné číslo</span><span class="sxs-lookup"><span data-stu-id="d7f91-1581">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="d7f91-1582">	丹麦个人身份号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-1582">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-1583">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-1583">Format</span></span>

<span data-ttu-id="d7f91-1584">10 个数字，包含连字符</span><span class="sxs-lookup"><span data-stu-id="d7f91-1584">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-1585">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-1585">Pattern</span></span>

<span data-ttu-id="d7f91-1586">10 个数字：</span><span class="sxs-lookup"><span data-stu-id="d7f91-1586">10 digits:</span></span>
- <span data-ttu-id="d7f91-1587">六个数字，采用  DDMMYY 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="d7f91-1587">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="d7f91-1588">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="d7f91-1588">A hyphen</span></span> 
- <span data-ttu-id="d7f91-1589">四个数字，最后一位数字是校验位</span><span class="sxs-lookup"><span data-stu-id="d7f91-1589">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-1590">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-1590">Checksum</span></span>

<span data-ttu-id="d7f91-1591">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-1591">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-1592">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-1592">Definition</span></span>

<span data-ttu-id="d7f91-1593">DLP 策略 75% 确信在300个字符的邻近度内检测到此类型的敏感信息: 正则表达式 Regex_denmark_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="d7f91-1594">找到 Keyword_denmark_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1594">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="d7f91-1595">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1595">The checksum passes.</span></span>

```xml
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-1596">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1596">Keywords</span></span>

#### <a name="keyword_denmark_id"></a><span data-ttu-id="d7f91-1597">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="d7f91-1597">Keyword_denmark_id</span></span>

- <span data-ttu-id="d7f91-1598">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-1598">Personal Identification Number</span></span>
- <span data-ttu-id="d7f91-1599">CPR</span><span class="sxs-lookup"><span data-stu-id="d7f91-1599">CPR</span></span>
- <span data-ttu-id="d7f91-1600">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="d7f91-1600">Det Centrale Personregister</span></span>
- <span data-ttu-id="d7f91-1601">Personnummer</span><span class="sxs-lookup"><span data-stu-id="d7f91-1601">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="d7f91-1602">药品管制局 (DEA) 号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-1602">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-1603">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-1603">Format</span></span>

<span data-ttu-id="d7f91-1604">两个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1604">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-1605">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-1605">Pattern</span></span>

<span data-ttu-id="d7f91-1606">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="d7f91-1606">Pattern must include all of the following:</span></span>
- <span data-ttu-id="d7f91-1607">这一组可能的字母（不区分大小写）中的一个字母：abcdefghjklmnprstux，这是注册人代码</span><span class="sxs-lookup"><span data-stu-id="d7f91-1607">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="d7f91-1608">一个字母（不区分大小写），这是注册人姓氏的第一个字母</span><span class="sxs-lookup"><span data-stu-id="d7f91-1608">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="d7f91-1609">七位数字，最后一个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="d7f91-1609">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-1610">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-1610">Checksum</span></span>

<span data-ttu-id="d7f91-1611">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-1611">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-1612">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-1612">Definition</span></span>

<span data-ttu-id="d7f91-1613">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-1613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-1614">函数 Func_dea_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1614">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-1615">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1615">The checksum passes.</span></span>

```xml
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-1616">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1616">Keywords</span></span>

<span data-ttu-id="d7f91-1617">无</span><span class="sxs-lookup"><span data-stu-id="d7f91-1617">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="d7f91-1618">欧盟借记卡号</span><span class="sxs-lookup"><span data-stu-id="d7f91-1618">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-1619">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-1619">Format</span></span>

<span data-ttu-id="d7f91-1620">16 个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1620">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-1621">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-1621">Pattern</span></span>

<span data-ttu-id="d7f91-1622">非常复杂且强大的模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-1622">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-1623">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-1623">Checksum</span></span>

<span data-ttu-id="d7f91-1624">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-1624">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-1625">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-1625">Definition</span></span>

<span data-ttu-id="d7f91-1626">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-1626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-1627">函数 Func_eu_debit_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1627">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-1628">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="d7f91-1628">At least one of the following is true:</span></span>
    - <span data-ttu-id="d7f91-1629">找到 Keyword_eu_debit_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1629">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="d7f91-1630">找到 Keyword_card_terms_dict 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1630">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="d7f91-1631">找到 Keyword_card_security_terms_dict 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1631">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="d7f91-1632">找到 Keyword_card_expiration_terms_dict 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1632">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="d7f91-1633">函数 Func_expiration_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1633">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="d7f91-1634">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1634">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-1635">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1635">Keywords</span></span>

#### <a name="keyword_eu_debit_card"></a><span data-ttu-id="d7f91-1636">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="d7f91-1636">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="d7f91-1637">account number</span><span class="sxs-lookup"><span data-stu-id="d7f91-1637">account number</span></span> 
- <span data-ttu-id="d7f91-1638">card number</span><span class="sxs-lookup"><span data-stu-id="d7f91-1638">card number</span></span> 
- <span data-ttu-id="d7f91-1639">card no.</span><span class="sxs-lookup"><span data-stu-id="d7f91-1639">card no.</span></span> 
- <span data-ttu-id="d7f91-1640">security number</span><span class="sxs-lookup"><span data-stu-id="d7f91-1640">security number</span></span> 
- <span data-ttu-id="d7f91-1641">收件人#</span><span class="sxs-lookup"><span data-stu-id="d7f91-1641">cc#</span></span> 

#### <a name="keyword_card_terms_dict"></a><span data-ttu-id="d7f91-1642">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="d7f91-1642">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="d7f91-1643">acct nbr</span><span class="sxs-lookup"><span data-stu-id="d7f91-1643">acct nbr</span></span> 
- <span data-ttu-id="d7f91-1644">acct num</span><span class="sxs-lookup"><span data-stu-id="d7f91-1644">acct num</span></span> 
- <span data-ttu-id="d7f91-1645">acct no</span><span class="sxs-lookup"><span data-stu-id="d7f91-1645">acct no</span></span> 
- <span data-ttu-id="d7f91-1646">american express</span><span class="sxs-lookup"><span data-stu-id="d7f91-1646">american express</span></span> 
- <span data-ttu-id="d7f91-1647">americanexpress</span><span class="sxs-lookup"><span data-stu-id="d7f91-1647">americanexpress</span></span> 
- <span data-ttu-id="d7f91-1648">americano espresso</span><span class="sxs-lookup"><span data-stu-id="d7f91-1648">americano espresso</span></span> 
- <span data-ttu-id="d7f91-1649">amex</span><span class="sxs-lookup"><span data-stu-id="d7f91-1649">amex</span></span> 
- <span data-ttu-id="d7f91-1650">atm card</span><span class="sxs-lookup"><span data-stu-id="d7f91-1650">atm card</span></span> 
- <span data-ttu-id="d7f91-1651">atm cards</span><span class="sxs-lookup"><span data-stu-id="d7f91-1651">atm cards</span></span> 
- <span data-ttu-id="d7f91-1652">atm kaart</span><span class="sxs-lookup"><span data-stu-id="d7f91-1652">atm kaart</span></span> 
- <span data-ttu-id="d7f91-1653">atmcard</span><span class="sxs-lookup"><span data-stu-id="d7f91-1653">atmcard</span></span> 
- <span data-ttu-id="d7f91-1654">atmcards</span><span class="sxs-lookup"><span data-stu-id="d7f91-1654">atmcards</span></span> 
- <span data-ttu-id="d7f91-1655">atmkaart</span><span class="sxs-lookup"><span data-stu-id="d7f91-1655">atmkaart</span></span> 
- <span data-ttu-id="d7f91-1656">atmkaarten</span><span class="sxs-lookup"><span data-stu-id="d7f91-1656">atmkaarten</span></span> 
- <span data-ttu-id="d7f91-1657">bancontact</span><span class="sxs-lookup"><span data-stu-id="d7f91-1657">bancontact</span></span> 
- <span data-ttu-id="d7f91-1658">bank card</span><span class="sxs-lookup"><span data-stu-id="d7f91-1658">bank card</span></span> 
- <span data-ttu-id="d7f91-1659">bankkaart</span><span class="sxs-lookup"><span data-stu-id="d7f91-1659">bankkaart</span></span> 
- <span data-ttu-id="d7f91-1660">card holder</span><span class="sxs-lookup"><span data-stu-id="d7f91-1660">card holder</span></span> 
- <span data-ttu-id="d7f91-1661">card holders</span><span class="sxs-lookup"><span data-stu-id="d7f91-1661">card holders</span></span> 
- <span data-ttu-id="d7f91-1662">card num</span><span class="sxs-lookup"><span data-stu-id="d7f91-1662">card num</span></span> 
- <span data-ttu-id="d7f91-1663">card number</span><span class="sxs-lookup"><span data-stu-id="d7f91-1663">card number</span></span> 
- <span data-ttu-id="d7f91-1664">card numbers</span><span class="sxs-lookup"><span data-stu-id="d7f91-1664">card numbers</span></span> 
- <span data-ttu-id="d7f91-1665">card type</span><span class="sxs-lookup"><span data-stu-id="d7f91-1665">card type</span></span> 
- <span data-ttu-id="d7f91-1666">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="d7f91-1666">cardano numerico</span></span> 
- <span data-ttu-id="d7f91-1667">持卡人</span><span class="sxs-lookup"><span data-stu-id="d7f91-1667">cardholder</span></span> 
- <span data-ttu-id="d7f91-1668">cardholders</span><span class="sxs-lookup"><span data-stu-id="d7f91-1668">cardholders</span></span> 
- <span data-ttu-id="d7f91-1669">cardnumber</span><span class="sxs-lookup"><span data-stu-id="d7f91-1669">cardnumber</span></span> 
- <span data-ttu-id="d7f91-1670">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="d7f91-1670">cardnumbers</span></span> 
- <span data-ttu-id="d7f91-1671">carta bianca</span><span class="sxs-lookup"><span data-stu-id="d7f91-1671">carta bianca</span></span> 
- <span data-ttu-id="d7f91-1672">carta credito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1672">carta credito</span></span> 
- <span data-ttu-id="d7f91-1673">carta di credito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1673">carta di credito</span></span> 
- <span data-ttu-id="d7f91-1674">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1674">cartao de credito</span></span> 
- <span data-ttu-id="d7f91-1675">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1675">cartao de crédito</span></span> 
- <span data-ttu-id="d7f91-1676">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1676">cartao de debito</span></span> 
- <span data-ttu-id="d7f91-1677">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1677">cartao de débito</span></span> 
- <span data-ttu-id="d7f91-1678">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="d7f91-1678">carte bancaire</span></span> 
- <span data-ttu-id="d7f91-1679">carte blanche</span><span class="sxs-lookup"><span data-stu-id="d7f91-1679">carte blanche</span></span> 
- <span data-ttu-id="d7f91-1680">carte bleue</span><span class="sxs-lookup"><span data-stu-id="d7f91-1680">carte bleue</span></span> 
- <span data-ttu-id="d7f91-1681">carte de credit</span><span class="sxs-lookup"><span data-stu-id="d7f91-1681">carte de credit</span></span> 
- <span data-ttu-id="d7f91-1682">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="d7f91-1682">carte de crédit</span></span> 
- <span data-ttu-id="d7f91-1683">carte di credito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1683">carte di credito</span></span> 
- <span data-ttu-id="d7f91-1684">carteblanche</span><span class="sxs-lookup"><span data-stu-id="d7f91-1684">carteblanche</span></span> 
- <span data-ttu-id="d7f91-1685">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1685">cartão de credito</span></span> 
- <span data-ttu-id="d7f91-1686">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1686">cartão de crédito</span></span> 
- <span data-ttu-id="d7f91-1687">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1687">cartão de debito</span></span> 
- <span data-ttu-id="d7f91-1688">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1688">cartão de débito</span></span> 
- <span data-ttu-id="d7f91-1689">cb</span><span class="sxs-lookup"><span data-stu-id="d7f91-1689">cb</span></span> 
- <span data-ttu-id="d7f91-1690">ccn</span><span class="sxs-lookup"><span data-stu-id="d7f91-1690">ccn</span></span> 
- <span data-ttu-id="d7f91-1691">check card</span><span class="sxs-lookup"><span data-stu-id="d7f91-1691">check card</span></span> 
- <span data-ttu-id="d7f91-1692">check cards</span><span class="sxs-lookup"><span data-stu-id="d7f91-1692">check cards</span></span> 
- <span data-ttu-id="d7f91-1693">checkcard</span><span class="sxs-lookup"><span data-stu-id="d7f91-1693">checkcard</span></span>
- <span data-ttu-id="d7f91-1694">checkcards</span><span class="sxs-lookup"><span data-stu-id="d7f91-1694">checkcards</span></span> 
- <span data-ttu-id="d7f91-1695">chequekaart</span><span class="sxs-lookup"><span data-stu-id="d7f91-1695">chequekaart</span></span> 
- <span data-ttu-id="d7f91-1696">cirrus</span><span class="sxs-lookup"><span data-stu-id="d7f91-1696">cirrus</span></span> 
- <span data-ttu-id="d7f91-1697">cirrus-edc-maestro</span><span class="sxs-lookup"><span data-stu-id="d7f91-1697">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="d7f91-1698">controlekaart</span><span class="sxs-lookup"><span data-stu-id="d7f91-1698">controlekaart</span></span> 
- <span data-ttu-id="d7f91-1699">controlekaarten</span><span class="sxs-lookup"><span data-stu-id="d7f91-1699">controlekaarten</span></span> 
- <span data-ttu-id="d7f91-1700">credit card</span><span class="sxs-lookup"><span data-stu-id="d7f91-1700">credit card</span></span> 
- <span data-ttu-id="d7f91-1701">credit cards</span><span class="sxs-lookup"><span data-stu-id="d7f91-1701">credit cards</span></span> 
- <span data-ttu-id="d7f91-1702">creditcard</span><span class="sxs-lookup"><span data-stu-id="d7f91-1702">creditcard</span></span> 
- <span data-ttu-id="d7f91-1703">creditcards</span><span class="sxs-lookup"><span data-stu-id="d7f91-1703">creditcards</span></span> 
- <span data-ttu-id="d7f91-1704">debetkaart</span><span class="sxs-lookup"><span data-stu-id="d7f91-1704">debetkaart</span></span> 
- <span data-ttu-id="d7f91-1705">debetkaarten</span><span class="sxs-lookup"><span data-stu-id="d7f91-1705">debetkaarten</span></span> 
- <span data-ttu-id="d7f91-1706">debit card</span><span class="sxs-lookup"><span data-stu-id="d7f91-1706">debit card</span></span> 
- <span data-ttu-id="d7f91-1707">debit cards</span><span class="sxs-lookup"><span data-stu-id="d7f91-1707">debit cards</span></span> 
- <span data-ttu-id="d7f91-1708">debitcard</span><span class="sxs-lookup"><span data-stu-id="d7f91-1708">debitcard</span></span> 
- <span data-ttu-id="d7f91-1709">debitcards</span><span class="sxs-lookup"><span data-stu-id="d7f91-1709">debitcards</span></span> 
- <span data-ttu-id="d7f91-1710">debito automatico</span><span class="sxs-lookup"><span data-stu-id="d7f91-1710">debito automatico</span></span> 
- <span data-ttu-id="d7f91-1711">diners club</span><span class="sxs-lookup"><span data-stu-id="d7f91-1711">diners club</span></span> 
- <span data-ttu-id="d7f91-1712">dinersclub</span><span class="sxs-lookup"><span data-stu-id="d7f91-1712">dinersclub</span></span> 
- <span data-ttu-id="d7f91-1713">确定</span><span class="sxs-lookup"><span data-stu-id="d7f91-1713">discover</span></span> 
- <span data-ttu-id="d7f91-1714">discover card</span><span class="sxs-lookup"><span data-stu-id="d7f91-1714">discover card</span></span> 
- <span data-ttu-id="d7f91-1715">discover cards</span><span class="sxs-lookup"><span data-stu-id="d7f91-1715">discover cards</span></span> 
- <span data-ttu-id="d7f91-1716">discovercard</span><span class="sxs-lookup"><span data-stu-id="d7f91-1716">discovercard</span></span> 
- <span data-ttu-id="d7f91-1717">discovercards</span><span class="sxs-lookup"><span data-stu-id="d7f91-1717">discovercards</span></span> 
- <span data-ttu-id="d7f91-1718">débito automático</span><span class="sxs-lookup"><span data-stu-id="d7f91-1718">débito automático</span></span>
- <span data-ttu-id="d7f91-1719">edc</span><span class="sxs-lookup"><span data-stu-id="d7f91-1719">edc</span></span> 
- <span data-ttu-id="d7f91-1720">eigentümername</span><span class="sxs-lookup"><span data-stu-id="d7f91-1720">eigentümername</span></span> 
- <span data-ttu-id="d7f91-1721">european debit card</span><span class="sxs-lookup"><span data-stu-id="d7f91-1721">european debit card</span></span> 
- <span data-ttu-id="d7f91-1722">hoofdkaart</span><span class="sxs-lookup"><span data-stu-id="d7f91-1722">hoofdkaart</span></span> 
- <span data-ttu-id="d7f91-1723">hoofdkaarten</span><span class="sxs-lookup"><span data-stu-id="d7f91-1723">hoofdkaarten</span></span> 
- <span data-ttu-id="d7f91-1724">in viaggio</span><span class="sxs-lookup"><span data-stu-id="d7f91-1724">in viaggio</span></span> 
- <span data-ttu-id="d7f91-1725">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="d7f91-1725">japanese card bureau</span></span> 
- <span data-ttu-id="d7f91-1726">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="d7f91-1726">japanse kaartdienst</span></span> 
- <span data-ttu-id="d7f91-1727">jcb</span><span class="sxs-lookup"><span data-stu-id="d7f91-1727">jcb</span></span> 
- <span data-ttu-id="d7f91-1728">kaart</span><span class="sxs-lookup"><span data-stu-id="d7f91-1728">kaart</span></span> 
- <span data-ttu-id="d7f91-1729">kaart num</span><span class="sxs-lookup"><span data-stu-id="d7f91-1729">kaart num</span></span> 
- <span data-ttu-id="d7f91-1730">kaartaantal</span><span class="sxs-lookup"><span data-stu-id="d7f91-1730">kaartaantal</span></span> 
- <span data-ttu-id="d7f91-1731">kaartaantallen</span><span class="sxs-lookup"><span data-stu-id="d7f91-1731">kaartaantallen</span></span> 
- <span data-ttu-id="d7f91-1732">kaarthouder</span><span class="sxs-lookup"><span data-stu-id="d7f91-1732">kaarthouder</span></span> 
- <span data-ttu-id="d7f91-1733">kaarthouders</span><span class="sxs-lookup"><span data-stu-id="d7f91-1733">kaarthouders</span></span> 
- <span data-ttu-id="d7f91-1734">karte</span><span class="sxs-lookup"><span data-stu-id="d7f91-1734">karte</span></span>  
- <span data-ttu-id="d7f91-1735">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="d7f91-1735">karteninhaber</span></span> 
- <span data-ttu-id="d7f91-1736">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="d7f91-1736">karteninhabers</span></span>
- <span data-ttu-id="d7f91-1737">kartennr</span><span class="sxs-lookup"><span data-stu-id="d7f91-1737">kartennr</span></span> 
- <span data-ttu-id="d7f91-1738">kartennummer</span><span class="sxs-lookup"><span data-stu-id="d7f91-1738">kartennummer</span></span> 
- <span data-ttu-id="d7f91-1739">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="d7f91-1739">kreditkarte</span></span> 
- <span data-ttu-id="d7f91-1740">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="d7f91-1740">kreditkarten-nummer</span></span> 
- <span data-ttu-id="d7f91-1741">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="d7f91-1741">kreditkarteninhaber</span></span> 
- <span data-ttu-id="d7f91-1742">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="d7f91-1742">kreditkarteninstitut</span></span> 
- <span data-ttu-id="d7f91-1743">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="d7f91-1743">kreditkartennummer</span></span> 
- <span data-ttu-id="d7f91-1744">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="d7f91-1744">kreditkartentyp</span></span> 
- <span data-ttu-id="d7f91-1745">maestro</span><span class="sxs-lookup"><span data-stu-id="d7f91-1745">maestro</span></span> 
- <span data-ttu-id="d7f91-1746">Master Card</span><span class="sxs-lookup"><span data-stu-id="d7f91-1746">master card</span></span> 
- <span data-ttu-id="d7f91-1747">master cards</span><span class="sxs-lookup"><span data-stu-id="d7f91-1747">master cards</span></span> 
- <span data-ttu-id="d7f91-1748">mastercard</span><span class="sxs-lookup"><span data-stu-id="d7f91-1748">mastercard</span></span> 
- <span data-ttu-id="d7f91-1749">mastercards</span><span class="sxs-lookup"><span data-stu-id="d7f91-1749">mastercards</span></span> 
- <span data-ttu-id="d7f91-1750">emc</span><span class="sxs-lookup"><span data-stu-id="d7f91-1750">mc</span></span> 
- <span data-ttu-id="d7f91-1751">mister cash</span><span class="sxs-lookup"><span data-stu-id="d7f91-1751">mister cash</span></span> 
- <span data-ttu-id="d7f91-1752">n carta</span><span class="sxs-lookup"><span data-stu-id="d7f91-1752">n carta</span></span> 
- <span data-ttu-id="d7f91-1753">carta</span><span class="sxs-lookup"><span data-stu-id="d7f91-1753">carta</span></span> 
- <span data-ttu-id="d7f91-1754">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="d7f91-1754">no de tarjeta</span></span> 
- <span data-ttu-id="d7f91-1755">no do cartao</span><span class="sxs-lookup"><span data-stu-id="d7f91-1755">no do cartao</span></span> 
- <span data-ttu-id="d7f91-1756">no do cartão</span><span class="sxs-lookup"><span data-stu-id="d7f91-1756">no do cartão</span></span> 
- <span data-ttu-id="d7f91-1757">不。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1757">no.</span></span> <span data-ttu-id="d7f91-1758">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="d7f91-1758">de tarjeta</span></span> 
- <span data-ttu-id="d7f91-1759">不。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1759">no.</span></span> <span data-ttu-id="d7f91-1760">do cartao</span><span class="sxs-lookup"><span data-stu-id="d7f91-1760">do cartao</span></span> 
- <span data-ttu-id="d7f91-1761">不。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1761">no.</span></span> <span data-ttu-id="d7f91-1762">do cartão</span><span class="sxs-lookup"><span data-stu-id="d7f91-1762">do cartão</span></span> 
- <span data-ttu-id="d7f91-1763">nr carta</span><span class="sxs-lookup"><span data-stu-id="d7f91-1763">nr carta</span></span> 
- <span data-ttu-id="d7f91-1764">führerschein-nr.</span><span class="sxs-lookup"><span data-stu-id="d7f91-1764">nr.</span></span> <span data-ttu-id="d7f91-1765">carta</span><span class="sxs-lookup"><span data-stu-id="d7f91-1765">carta</span></span> 
- <span data-ttu-id="d7f91-1766">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="d7f91-1766">numeri di scheda</span></span> 
- <span data-ttu-id="d7f91-1767">numero carta</span><span class="sxs-lookup"><span data-stu-id="d7f91-1767">numero carta</span></span> 
- <span data-ttu-id="d7f91-1768">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="d7f91-1768">numero de cartao</span></span> 
- <span data-ttu-id="d7f91-1769">numero de carte</span><span class="sxs-lookup"><span data-stu-id="d7f91-1769">numero de carte</span></span> 
- <span data-ttu-id="d7f91-1770">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="d7f91-1770">numero de cartão</span></span> 
- <span data-ttu-id="d7f91-1771">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="d7f91-1771">numero de tarjeta</span></span>
- <span data-ttu-id="d7f91-1772">numero della carta</span><span class="sxs-lookup"><span data-stu-id="d7f91-1772">numero della carta</span></span> 
- <span data-ttu-id="d7f91-1773">numero di carta</span><span class="sxs-lookup"><span data-stu-id="d7f91-1773">numero di carta</span></span> 
- <span data-ttu-id="d7f91-1774">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="d7f91-1774">numero di scheda</span></span> 
- <span data-ttu-id="d7f91-1775">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="d7f91-1775">numero do cartao</span></span> 
- <span data-ttu-id="d7f91-1776">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="d7f91-1776">numero do cartão</span></span> 
- <span data-ttu-id="d7f91-1777">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="d7f91-1777">numéro de carte</span></span> 
- <span data-ttu-id="d7f91-1778">nº carta</span><span class="sxs-lookup"><span data-stu-id="d7f91-1778">nº carta</span></span> 
- <span data-ttu-id="d7f91-1779">nº de carte</span><span class="sxs-lookup"><span data-stu-id="d7f91-1779">nº de carte</span></span> 
- <span data-ttu-id="d7f91-1780">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="d7f91-1780">nº de la carte</span></span> 
- <span data-ttu-id="d7f91-1781">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="d7f91-1781">nº de tarjeta</span></span> 
- <span data-ttu-id="d7f91-1782">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="d7f91-1782">nº do cartao</span></span> 
- <span data-ttu-id="d7f91-1783">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="d7f91-1783">nº do cartão</span></span> 
- <span data-ttu-id="d7f91-1784">n º。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1784">nº.</span></span> <span data-ttu-id="d7f91-1785">do cartão</span><span class="sxs-lookup"><span data-stu-id="d7f91-1785">do cartão</span></span> 
- <span data-ttu-id="d7f91-1786">número de cartao</span><span class="sxs-lookup"><span data-stu-id="d7f91-1786">número de cartao</span></span> 
- <span data-ttu-id="d7f91-1787">número de cartão</span><span class="sxs-lookup"><span data-stu-id="d7f91-1787">número de cartão</span></span> 
- <span data-ttu-id="d7f91-1788">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="d7f91-1788">número de tarjeta</span></span> 
- <span data-ttu-id="d7f91-1789">número do cartao</span><span class="sxs-lookup"><span data-stu-id="d7f91-1789">número do cartao</span></span> 
- <span data-ttu-id="d7f91-1790">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="d7f91-1790">scheda dell'assegno</span></span> 
- <span data-ttu-id="d7f91-1791">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="d7f91-1791">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="d7f91-1792">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="d7f91-1792">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="d7f91-1793">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="d7f91-1793">scheda della banca</span></span> 
- <span data-ttu-id="d7f91-1794">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="d7f91-1794">scheda di controllo</span></span> 
- <span data-ttu-id="d7f91-1795">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1795">scheda di debito</span></span> 
- <span data-ttu-id="d7f91-1796">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="d7f91-1796">scheda matrice</span></span> 
- <span data-ttu-id="d7f91-1797">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="d7f91-1797">schede dell'atmosfera</span></span> 
- <span data-ttu-id="d7f91-1798">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="d7f91-1798">schede di controllo</span></span> 
- <span data-ttu-id="d7f91-1799">schede di debito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1799">schede di debito</span></span> 
- <span data-ttu-id="d7f91-1800">schede matrici</span><span class="sxs-lookup"><span data-stu-id="d7f91-1800">schede matrici</span></span> 
- <span data-ttu-id="d7f91-1801">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="d7f91-1801">scoprono la scheda</span></span> 
- <span data-ttu-id="d7f91-1802">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="d7f91-1802">scoprono le schede</span></span> 
- <span data-ttu-id="d7f91-1803">solo</span><span class="sxs-lookup"><span data-stu-id="d7f91-1803">solo</span></span> 
- <span data-ttu-id="d7f91-1804">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="d7f91-1804">supporti di scheda</span></span> 
- <span data-ttu-id="d7f91-1805">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="d7f91-1805">supporto di scheda</span></span> 
- <span data-ttu-id="d7f91-1806">器</span><span class="sxs-lookup"><span data-stu-id="d7f91-1806">switch</span></span> 
- <span data-ttu-id="d7f91-1807">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="d7f91-1807">tarjeta atm</span></span> 
- <span data-ttu-id="d7f91-1808">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1808">tarjeta credito</span></span> 
- <span data-ttu-id="d7f91-1809">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="d7f91-1809">tarjeta de atm</span></span> 
- <span data-ttu-id="d7f91-1810">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1810">tarjeta de credito</span></span> 
- <span data-ttu-id="d7f91-1811">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1811">tarjeta de debito</span></span> 
- <span data-ttu-id="d7f91-1812">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="d7f91-1812">tarjeta debito</span></span> 
- <span data-ttu-id="d7f91-1813">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="d7f91-1813">tarjeta no</span></span>
- <span data-ttu-id="d7f91-1814">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="d7f91-1814">tarjetahabiente</span></span> 
- <span data-ttu-id="d7f91-1815">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="d7f91-1815">tipo della scheda</span></span> 
- <span data-ttu-id="d7f91-1816">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="d7f91-1816">ufficio giapponese della</span></span> 
- <span data-ttu-id="d7f91-1817">scheda</span><span class="sxs-lookup"><span data-stu-id="d7f91-1817">scheda</span></span> 
- <span data-ttu-id="d7f91-1818">v pay</span><span class="sxs-lookup"><span data-stu-id="d7f91-1818">v pay</span></span> 
- <span data-ttu-id="d7f91-1819">v-支付</span><span class="sxs-lookup"><span data-stu-id="d7f91-1819">v-pay</span></span> 
- <span data-ttu-id="d7f91-1820">反之</span><span class="sxs-lookup"><span data-stu-id="d7f91-1820">visa</span></span> 
- <span data-ttu-id="d7f91-1821">visa plus</span><span class="sxs-lookup"><span data-stu-id="d7f91-1821">visa plus</span></span> 
- <span data-ttu-id="d7f91-1822">visa electron</span><span class="sxs-lookup"><span data-stu-id="d7f91-1822">visa electron</span></span> 
- <span data-ttu-id="d7f91-1823">visto</span><span class="sxs-lookup"><span data-stu-id="d7f91-1823">visto</span></span> 
- <span data-ttu-id="d7f91-1824">visum</span><span class="sxs-lookup"><span data-stu-id="d7f91-1824">visum</span></span> 
- <span data-ttu-id="d7f91-1825">vpay</span><span class="sxs-lookup"><span data-stu-id="d7f91-1825">vpay</span></span>   

#### <a name="keyword_card_security_terms_dict"></a><span data-ttu-id="d7f91-1826">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="d7f91-1826">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="d7f91-1827">card identification number</span><span class="sxs-lookup"><span data-stu-id="d7f91-1827">card identification number</span></span>
- <span data-ttu-id="d7f91-1828">card verification</span><span class="sxs-lookup"><span data-stu-id="d7f91-1828">card verification</span></span> 
- <span data-ttu-id="d7f91-1829">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="d7f91-1829">cardi la verifica</span></span> 
- <span data-ttu-id="d7f91-1830">cid</span><span class="sxs-lookup"><span data-stu-id="d7f91-1830">cid</span></span> 
- <span data-ttu-id="d7f91-1831">cod seg</span><span class="sxs-lookup"><span data-stu-id="d7f91-1831">cod seg</span></span> 
- <span data-ttu-id="d7f91-1832">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="d7f91-1832">cod seguranca</span></span> 
- <span data-ttu-id="d7f91-1833">cod segurança</span><span class="sxs-lookup"><span data-stu-id="d7f91-1833">cod segurança</span></span> 
- <span data-ttu-id="d7f91-1834">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="d7f91-1834">cod sicurezza</span></span> 
- <span data-ttu-id="d7f91-1835">货.</span><span class="sxs-lookup"><span data-stu-id="d7f91-1835">cod.</span></span> <span data-ttu-id="d7f91-1836">seg</span><span class="sxs-lookup"><span data-stu-id="d7f91-1836">seg</span></span> 
- <span data-ttu-id="d7f91-1837">货.</span><span class="sxs-lookup"><span data-stu-id="d7f91-1837">cod.</span></span> <span data-ttu-id="d7f91-1838">seguranca</span><span class="sxs-lookup"><span data-stu-id="d7f91-1838">seguranca</span></span> 
- <span data-ttu-id="d7f91-1839">货.</span><span class="sxs-lookup"><span data-stu-id="d7f91-1839">cod.</span></span> <span data-ttu-id="d7f91-1840">segurança</span><span class="sxs-lookup"><span data-stu-id="d7f91-1840">segurança</span></span> 
- <span data-ttu-id="d7f91-1841">货.</span><span class="sxs-lookup"><span data-stu-id="d7f91-1841">cod.</span></span> <span data-ttu-id="d7f91-1842">sicurezza</span><span class="sxs-lookup"><span data-stu-id="d7f91-1842">sicurezza</span></span> 
- <span data-ttu-id="d7f91-1843">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="d7f91-1843">codice di sicurezza</span></span> 
- <span data-ttu-id="d7f91-1844">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="d7f91-1844">codice di verifica</span></span> 
- <span data-ttu-id="d7f91-1845">codigo</span><span class="sxs-lookup"><span data-stu-id="d7f91-1845">codigo</span></span> 
- <span data-ttu-id="d7f91-1846">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="d7f91-1846">codigo de seguranca</span></span> 
- <span data-ttu-id="d7f91-1847">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="d7f91-1847">codigo de segurança</span></span> 
- <span data-ttu-id="d7f91-1848">crittogramma</span><span class="sxs-lookup"><span data-stu-id="d7f91-1848">crittogramma</span></span> 
- <span data-ttu-id="d7f91-1849">cryptogram</span><span class="sxs-lookup"><span data-stu-id="d7f91-1849">cryptogram</span></span> 
- <span data-ttu-id="d7f91-1850">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="d7f91-1850">cryptogramme</span></span> 
- <span data-ttu-id="d7f91-1851">cv2</span><span class="sxs-lookup"><span data-stu-id="d7f91-1851">cv2</span></span> 
- <span data-ttu-id="d7f91-1852">cvc</span><span class="sxs-lookup"><span data-stu-id="d7f91-1852">cvc</span></span> 
- <span data-ttu-id="d7f91-1853">cvc2</span><span class="sxs-lookup"><span data-stu-id="d7f91-1853">cvc2</span></span> 
- <span data-ttu-id="d7f91-1854">cvn</span><span class="sxs-lookup"><span data-stu-id="d7f91-1854">cvn</span></span> 
- <span data-ttu-id="d7f91-1855">cvv</span><span class="sxs-lookup"><span data-stu-id="d7f91-1855">cvv</span></span> 
- <span data-ttu-id="d7f91-1856">cvv2</span><span class="sxs-lookup"><span data-stu-id="d7f91-1856">cvv2</span></span> 
- <span data-ttu-id="d7f91-1857">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="d7f91-1857">cód seguranca</span></span> 
- <span data-ttu-id="d7f91-1858">cód segurança</span><span class="sxs-lookup"><span data-stu-id="d7f91-1858">cód segurança</span></span> 
- <span data-ttu-id="d7f91-1859">cód.</span><span class="sxs-lookup"><span data-stu-id="d7f91-1859">cód.</span></span> <span data-ttu-id="d7f91-1860">seguranca</span><span class="sxs-lookup"><span data-stu-id="d7f91-1860">seguranca</span></span> 
- <span data-ttu-id="d7f91-1861">cód.</span><span class="sxs-lookup"><span data-stu-id="d7f91-1861">cód.</span></span> <span data-ttu-id="d7f91-1862">segurança</span><span class="sxs-lookup"><span data-stu-id="d7f91-1862">segurança</span></span> 
- <span data-ttu-id="d7f91-1863">código</span><span class="sxs-lookup"><span data-stu-id="d7f91-1863">código</span></span> 
- <span data-ttu-id="d7f91-1864">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="d7f91-1864">código de seguranca</span></span> 
- <span data-ttu-id="d7f91-1865">código de segurança</span><span class="sxs-lookup"><span data-stu-id="d7f91-1865">código de segurança</span></span> 
- <span data-ttu-id="d7f91-1866">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="d7f91-1866">de kaart controle</span></span> 
- <span data-ttu-id="d7f91-1867">geeft nr uit</span><span class="sxs-lookup"><span data-stu-id="d7f91-1867">geeft nr uit</span></span> 
- <span data-ttu-id="d7f91-1868">issue no</span><span class="sxs-lookup"><span data-stu-id="d7f91-1868">issue no</span></span> 
- <span data-ttu-id="d7f91-1869">issue number</span><span class="sxs-lookup"><span data-stu-id="d7f91-1869">issue number</span></span> 
- <span data-ttu-id="d7f91-1870">kaartidentificatienummer</span><span class="sxs-lookup"><span data-stu-id="d7f91-1870">kaartidentificatienummer</span></span> 
- <span data-ttu-id="d7f91-1871">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="d7f91-1871">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="d7f91-1872">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="d7f91-1872">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="d7f91-1873">kwestieaantal</span><span class="sxs-lookup"><span data-stu-id="d7f91-1873">kwestieaantal</span></span> 
- <span data-ttu-id="d7f91-1874">不。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1874">no.</span></span> <span data-ttu-id="d7f91-1875">dell'edizione</span><span class="sxs-lookup"><span data-stu-id="d7f91-1875">dell'edizione</span></span> 
- <span data-ttu-id="d7f91-1876">不。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1876">no.</span></span> <span data-ttu-id="d7f91-1877">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="d7f91-1877">di sicurezza</span></span> 
- <span data-ttu-id="d7f91-1878">numero de securite</span><span class="sxs-lookup"><span data-stu-id="d7f91-1878">numero de securite</span></span> 
- <span data-ttu-id="d7f91-1879">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="d7f91-1879">numero de verificacao</span></span> 
- <span data-ttu-id="d7f91-1880">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="d7f91-1880">numero dell'edizione</span></span> 
- <span data-ttu-id="d7f91-1881">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="d7f91-1881">numero di identificazione della</span></span> 
- <span data-ttu-id="d7f91-1882">scheda</span><span class="sxs-lookup"><span data-stu-id="d7f91-1882">scheda</span></span> 
- <span data-ttu-id="d7f91-1883">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="d7f91-1883">numero di sicurezza</span></span> 
- <span data-ttu-id="d7f91-1884">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="d7f91-1884">numero van veiligheid</span></span> 
- <span data-ttu-id="d7f91-1885">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="d7f91-1885">numéro de sécurité</span></span> 
- <span data-ttu-id="d7f91-1886">nº autorizzazione</span><span class="sxs-lookup"><span data-stu-id="d7f91-1886">nº autorizzazione</span></span> 
- <span data-ttu-id="d7f91-1887">número de verificação</span><span class="sxs-lookup"><span data-stu-id="d7f91-1887">número de verificação</span></span> 
- <span data-ttu-id="d7f91-1888">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="d7f91-1888">perno il blocco</span></span> 
- <span data-ttu-id="d7f91-1889">pin block</span><span class="sxs-lookup"><span data-stu-id="d7f91-1889">pin block</span></span> 
- <span data-ttu-id="d7f91-1890">prufziffer</span><span class="sxs-lookup"><span data-stu-id="d7f91-1890">prufziffer</span></span> 
- <span data-ttu-id="d7f91-1891">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="d7f91-1891">prüfziffer</span></span> 
- <span data-ttu-id="d7f91-1892">security code</span><span class="sxs-lookup"><span data-stu-id="d7f91-1892">security code</span></span> 
- <span data-ttu-id="d7f91-1893">security no</span><span class="sxs-lookup"><span data-stu-id="d7f91-1893">security no</span></span> 
- <span data-ttu-id="d7f91-1894">security number</span><span class="sxs-lookup"><span data-stu-id="d7f91-1894">security number</span></span> 
- <span data-ttu-id="d7f91-1895">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="d7f91-1895">sicherheits kode</span></span> 
- <span data-ttu-id="d7f91-1896">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="d7f91-1896">sicherheitscode</span></span> 
- <span data-ttu-id="d7f91-1897">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="d7f91-1897">sicherheitsnummer</span></span> 
- <span data-ttu-id="d7f91-1898">speldblok</span><span class="sxs-lookup"><span data-stu-id="d7f91-1898">speldblok</span></span> 
- <span data-ttu-id="d7f91-1899">veiligheid nr</span><span class="sxs-lookup"><span data-stu-id="d7f91-1899">veiligheid nr</span></span> 
- <span data-ttu-id="d7f91-1900">veiligheidsaantal</span><span class="sxs-lookup"><span data-stu-id="d7f91-1900">veiligheidsaantal</span></span> 
- <span data-ttu-id="d7f91-1901">veiligheidscode</span><span class="sxs-lookup"><span data-stu-id="d7f91-1901">veiligheidscode</span></span> 
- <span data-ttu-id="d7f91-1902">veiligheidsnummer</span><span class="sxs-lookup"><span data-stu-id="d7f91-1902">veiligheidsnummer</span></span> 
- <span data-ttu-id="d7f91-1903">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="d7f91-1903">verfalldatum</span></span> 

#### <a name="keyword_card_expiration_terms_dict"></a><span data-ttu-id="d7f91-1904">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="d7f91-1904">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="d7f91-1905">ablauf</span><span class="sxs-lookup"><span data-stu-id="d7f91-1905">ablauf</span></span> 
- <span data-ttu-id="d7f91-1906">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="d7f91-1906">data de expiracao</span></span> 
- <span data-ttu-id="d7f91-1907">data de expiração</span><span class="sxs-lookup"><span data-stu-id="d7f91-1907">data de expiração</span></span> 
- <span data-ttu-id="d7f91-1908">data del exp</span><span class="sxs-lookup"><span data-stu-id="d7f91-1908">data del exp</span></span> 
- <span data-ttu-id="d7f91-1909">data di exp</span><span class="sxs-lookup"><span data-stu-id="d7f91-1909">data di exp</span></span> 
- <span data-ttu-id="d7f91-1910">data di scadenza</span><span class="sxs-lookup"><span data-stu-id="d7f91-1910">data di scadenza</span></span> 
- <span data-ttu-id="d7f91-1911">data em que expira</span><span class="sxs-lookup"><span data-stu-id="d7f91-1911">data em que expira</span></span> 
- <span data-ttu-id="d7f91-1912">data scad</span><span class="sxs-lookup"><span data-stu-id="d7f91-1912">data scad</span></span> 
- <span data-ttu-id="d7f91-1913">data scadenza</span><span class="sxs-lookup"><span data-stu-id="d7f91-1913">data scadenza</span></span> 
- <span data-ttu-id="d7f91-1914">date de validité</span><span class="sxs-lookup"><span data-stu-id="d7f91-1914">date de validité</span></span> 
- <span data-ttu-id="d7f91-1915">datum afloop</span><span class="sxs-lookup"><span data-stu-id="d7f91-1915">datum afloop</span></span> 
- <span data-ttu-id="d7f91-1916">datum van exp</span><span class="sxs-lookup"><span data-stu-id="d7f91-1916">datum van exp</span></span> 
- <span data-ttu-id="d7f91-1917">de afloop</span><span class="sxs-lookup"><span data-stu-id="d7f91-1917">de afloop</span></span> 
- <span data-ttu-id="d7f91-1918">espira</span><span class="sxs-lookup"><span data-stu-id="d7f91-1918">espira</span></span> 
- <span data-ttu-id="d7f91-1919">espira</span><span class="sxs-lookup"><span data-stu-id="d7f91-1919">espira</span></span> 
- <span data-ttu-id="d7f91-1920">exp date</span><span class="sxs-lookup"><span data-stu-id="d7f91-1920">exp date</span></span> 
- <span data-ttu-id="d7f91-1921">exp datum</span><span class="sxs-lookup"><span data-stu-id="d7f91-1921">exp datum</span></span> 
- <span data-ttu-id="d7f91-1922">时间</span><span class="sxs-lookup"><span data-stu-id="d7f91-1922">expiration</span></span> 
- <span data-ttu-id="d7f91-1923">何时</span><span class="sxs-lookup"><span data-stu-id="d7f91-1923">expire</span></span> 
- <span data-ttu-id="d7f91-1924">不久</span><span class="sxs-lookup"><span data-stu-id="d7f91-1924">expires</span></span> 
- <span data-ttu-id="d7f91-1925">过期</span><span class="sxs-lookup"><span data-stu-id="d7f91-1925">expiry</span></span> 
- <span data-ttu-id="d7f91-1926">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="d7f91-1926">fecha de expiracion</span></span> 
- <span data-ttu-id="d7f91-1927">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="d7f91-1927">fecha de venc</span></span> 
- <span data-ttu-id="d7f91-1928">gultig bis</span><span class="sxs-lookup"><span data-stu-id="d7f91-1928">gultig bis</span></span> 
- <span data-ttu-id="d7f91-1929">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="d7f91-1929">gultigkeitsdatum</span></span> 
- <span data-ttu-id="d7f91-1930">gültig bis</span><span class="sxs-lookup"><span data-stu-id="d7f91-1930">gültig bis</span></span> 
- <span data-ttu-id="d7f91-1931">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="d7f91-1931">gültigkeitsdatum</span></span> 
- <span data-ttu-id="d7f91-1932">la scadenza</span><span class="sxs-lookup"><span data-stu-id="d7f91-1932">la scadenza</span></span> 
- <span data-ttu-id="d7f91-1933">scadenza</span><span class="sxs-lookup"><span data-stu-id="d7f91-1933">scadenza</span></span> 
- <span data-ttu-id="d7f91-1934">valable</span><span class="sxs-lookup"><span data-stu-id="d7f91-1934">valable</span></span> 
- <span data-ttu-id="d7f91-1935">validade</span><span class="sxs-lookup"><span data-stu-id="d7f91-1935">validade</span></span> 
- <span data-ttu-id="d7f91-1936">valido hasta</span><span class="sxs-lookup"><span data-stu-id="d7f91-1936">valido hasta</span></span> 
- <span data-ttu-id="d7f91-1937">valor</span><span class="sxs-lookup"><span data-stu-id="d7f91-1937">valor</span></span> 
- <span data-ttu-id="d7f91-1938">venc</span><span class="sxs-lookup"><span data-stu-id="d7f91-1938">venc</span></span> 
- <span data-ttu-id="d7f91-1939">vencimento</span><span class="sxs-lookup"><span data-stu-id="d7f91-1939">vencimento</span></span> 
- <span data-ttu-id="d7f91-1940">vencimiento</span><span class="sxs-lookup"><span data-stu-id="d7f91-1940">vencimiento</span></span> 
- <span data-ttu-id="d7f91-1941">verloopt</span><span class="sxs-lookup"><span data-stu-id="d7f91-1941">verloopt</span></span> 
- <span data-ttu-id="d7f91-1942">vervaldag</span><span class="sxs-lookup"><span data-stu-id="d7f91-1942">vervaldag</span></span> 
- <span data-ttu-id="d7f91-1943">vervaldatum</span><span class="sxs-lookup"><span data-stu-id="d7f91-1943">vervaldatum</span></span> 
- <span data-ttu-id="d7f91-1944">vto</span><span class="sxs-lookup"><span data-stu-id="d7f91-1944">vto</span></span> 
- <span data-ttu-id="d7f91-1945">válido hasta</span><span class="sxs-lookup"><span data-stu-id="d7f91-1945">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="d7f91-1946">欧盟驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-1946">EU Driver's License Number</span></span>

<span data-ttu-id="d7f91-1947">若要了解详细信息, 请参阅[EU 驱动程序的许可号敏感信息类型](eu-driver-s-license-number.md)。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1947">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="d7f91-1948">欧盟国家身份证号</span><span class="sxs-lookup"><span data-stu-id="d7f91-1948">EU National Identification Number</span></span>

<span data-ttu-id="d7f91-1949">若要了解详细信息, 请参阅[EU 国家身份证号敏感信息类型](eu-national-identification-number.md)。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1949">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="d7f91-1950">EU 护照号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-1950">EU Passport Number</span></span>

<span data-ttu-id="d7f91-1951">若要了解详细信息, 请参阅[EU 护照号敏感信息类型](eu-passport-number.md)。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1951">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="d7f91-1952">欧盟社会安全号码或等效 ID</span><span class="sxs-lookup"><span data-stu-id="d7f91-1952">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="d7f91-1953">若要了解详细信息, 请参阅[EU 社会保险号或等效 ID 敏感信息类型](eu-social-security-number-or-equivalent-id.md)。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1953">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="d7f91-1954">EU 税标识号</span><span class="sxs-lookup"><span data-stu-id="d7f91-1954">EU Tax Identification Number</span></span>

<span data-ttu-id="d7f91-1955">若要了解详细信息, 请参阅[EU 纳税识别号敏感信息类型](eu-tax-identification-number.md)。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1955">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="d7f91-1956">芬兰国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="d7f91-1956">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-1957">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-1957">Format</span></span>

<span data-ttu-id="d7f91-1958">六个数字加一个字符（表示一个世纪），加三个数字再加一个校验位</span><span class="sxs-lookup"><span data-stu-id="d7f91-1958">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-1959">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-1959">Pattern</span></span>

<span data-ttu-id="d7f91-1960">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="d7f91-1960">Pattern must include all of the following:</span></span>
- <span data-ttu-id="d7f91-1961">采用 DDMMYY 格式的六位数字，表示出生日期</span><span class="sxs-lookup"><span data-stu-id="d7f91-1961">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="d7f91-1962">世纪标记（“-”、“+”或“a”）</span><span class="sxs-lookup"><span data-stu-id="d7f91-1962">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="d7f91-1963">三位个人标识号</span><span class="sxs-lookup"><span data-stu-id="d7f91-1963">Three-digit personal identification number</span></span> 
- <span data-ttu-id="d7f91-1964">一个数字或字母（区分大小写），是校验位</span><span class="sxs-lookup"><span data-stu-id="d7f91-1964">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-1965">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-1965">Checksum</span></span>

<span data-ttu-id="d7f91-1966">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-1966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-1967">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-1967">Definition</span></span>

<span data-ttu-id="d7f91-1968">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-1968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-1969">函数 Func_finnish_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1969">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-1970">找到 Keyword_finnish_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1970">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="d7f91-1971">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1971">The checksum passes.</span></span>

```xml
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-1972">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1972">Keywords</span></span>

- <span data-ttu-id="d7f91-1973">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="d7f91-1973">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="d7f91-1974">Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="d7f91-1974">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="d7f91-1975">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="d7f91-1975">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="d7f91-1976">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="d7f91-1976">Personbeteckning</span></span>
- <span data-ttu-id="d7f91-1977">Personnummer</span><span class="sxs-lookup"><span data-stu-id="d7f91-1977">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="d7f91-1978">芬兰护照号</span><span class="sxs-lookup"><span data-stu-id="d7f91-1978">Finland Passport Number</span></span>

<span data-ttu-id="d7f91-1979">设置九个字母和数字的组合的组合九个字母和数字的组合: 两个字母 (不区分大小写) 七个数字校验和无定义 DLP 策略是 75% 确信它检测到这种类型的敏感信息, 如果在300个字符的邻近性: 正则表达式 Regex_finland_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1979">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
<span data-ttu-id="d7f91-1980">找到 Keyword_finland_passport_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1980">A keyword from Keyword_finland_passport_number is found.</span></span>
<!-- Finland Passport Number -->
<span data-ttu-id="d7f91-1981"><Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="d7f91-1981"></span></span>
<span data-ttu-id="d7f91-1982">关键字 Keyword_finland_passport_number Passport Passi</span><span class="sxs-lookup"><span data-stu-id="d7f91-1982">Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="d7f91-1983">法国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-1983">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-1984">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-1984">Format</span></span>

<span data-ttu-id="d7f91-1985">12 个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1985">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-1986">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-1986">Pattern</span></span>

<span data-ttu-id="d7f91-1987">12 个数字，会对类似模式（如法国电话号码）进行验证</span><span class="sxs-lookup"><span data-stu-id="d7f91-1987">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-1988">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-1988">Checksum</span></span>

<span data-ttu-id="d7f91-1989">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-1989">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-1990">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-1990">Definition</span></span>

<span data-ttu-id="d7f91-1991">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-1991">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-1992">函数 Func_french_drivers_license 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1992">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-1993">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="d7f91-1993">At least one of the following is true:</span></span>
- <span data-ttu-id="d7f91-1994">找到 Keyword_french_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1994">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="d7f91-1995">函数 Func_eu_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="d7f91-1995">The function Func_eu_date finds a date in the right date format.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-1996">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-1996">Keywords</span></span>

#### <a name="keyword_french_drivers_license"></a><span data-ttu-id="d7f91-1997">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="d7f91-1997">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="d7f91-1998">drivers licence</span><span class="sxs-lookup"><span data-stu-id="d7f91-1998">drivers licence</span></span>
- <span data-ttu-id="d7f91-1999">drivers license</span><span class="sxs-lookup"><span data-stu-id="d7f91-1999">drivers license</span></span>
- <span data-ttu-id="d7f91-2000">driving licence</span><span class="sxs-lookup"><span data-stu-id="d7f91-2000">driving licence</span></span>
- <span data-ttu-id="d7f91-2001">driving license</span><span class="sxs-lookup"><span data-stu-id="d7f91-2001">driving license</span></span>
- <span data-ttu-id="d7f91-2002">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="d7f91-2002">permis de conduire</span></span>
- <span data-ttu-id="d7f91-2003">licence number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2003">licence number</span></span>
- <span data-ttu-id="d7f91-2004">license number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2004">license number</span></span>
- <span data-ttu-id="d7f91-2005">licence numbers</span><span class="sxs-lookup"><span data-stu-id="d7f91-2005">licence numbers</span></span>
- <span data-ttu-id="d7f91-2006">license numbers</span><span class="sxs-lookup"><span data-stu-id="d7f91-2006">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="d7f91-2007">法国国家/地区 ID 卡 (CNI)</span><span class="sxs-lookup"><span data-stu-id="d7f91-2007">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-2008">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-2008">Format</span></span>

<span data-ttu-id="d7f91-2009">12 个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2009">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-2010">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2010">Pattern</span></span>

<span data-ttu-id="d7f91-2011">12 个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2011">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-2012">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-2012">Checksum</span></span>

<span data-ttu-id="d7f91-2013">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-2013">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-2014">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-2014">Definition</span></span>

<span data-ttu-id="d7f91-2015">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2015">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2016">正则表达式 Regex_france_cni 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2016">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```xml
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-2017">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2017">Keywords</span></span>

<span data-ttu-id="d7f91-2018">无</span><span class="sxs-lookup"><span data-stu-id="d7f91-2018">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="d7f91-2019">法国护照号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-2019">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-2020">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-2020">Format</span></span>

<span data-ttu-id="d7f91-2021">9 个数字和字母</span><span class="sxs-lookup"><span data-stu-id="d7f91-2021">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-2022">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2022">Pattern</span></span>

<span data-ttu-id="d7f91-2023">九位数字和字母：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2023">Nine digits and letters:</span></span>
- <span data-ttu-id="d7f91-2024">两位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2024">Two digits</span></span> 
- <span data-ttu-id="d7f91-2025">两个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="d7f91-2025">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="d7f91-2026">五位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2026">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-2027">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-2027">Checksum</span></span>

<span data-ttu-id="d7f91-2028">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-2028">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-2029">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-2029">Definition</span></span>

<span data-ttu-id="d7f91-2030">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2030">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2031">函数 Func_fr_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2031">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2032">找到 Keyword_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2032">A keyword from Keyword_passport is found.</span></span>

```xml
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-2033">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2033">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="d7f91-2034">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="d7f91-2034">Keyword_passport</span></span>

- <span data-ttu-id="d7f91-2035">Passport Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2035">Passport Number</span></span>
- <span data-ttu-id="d7f91-2036">Passport No</span><span class="sxs-lookup"><span data-stu-id="d7f91-2036">Passport No</span></span>
- <span data-ttu-id="d7f91-2037">Passport #</span><span class="sxs-lookup"><span data-stu-id="d7f91-2037">Passport #</span></span>
- <span data-ttu-id="d7f91-2038">登记卡#</span><span class="sxs-lookup"><span data-stu-id="d7f91-2038">Passport#</span></span>
- <span data-ttu-id="d7f91-2039">PassportID</span><span class="sxs-lookup"><span data-stu-id="d7f91-2039">PassportID</span></span>
- <span data-ttu-id="d7f91-2040">Passportno</span><span class="sxs-lookup"><span data-stu-id="d7f91-2040">Passportno</span></span>
- <span data-ttu-id="d7f91-2041">passportnumber</span><span class="sxs-lookup"><span data-stu-id="d7f91-2041">passportnumber</span></span>
- <span data-ttu-id="d7f91-2042">パスポート</span><span class="sxs-lookup"><span data-stu-id="d7f91-2042">パスポート</span></span>
- <span data-ttu-id="d7f91-2043">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="d7f91-2043">パスポート番号</span></span>
- <span data-ttu-id="d7f91-2044">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="d7f91-2044">パスポートのNum</span></span>
- <span data-ttu-id="d7f91-2045">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="d7f91-2045">パスポート ＃</span></span> 
- <span data-ttu-id="d7f91-2046">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="d7f91-2046">Numéro de passeport</span></span>
- <span data-ttu-id="d7f91-2047">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="d7f91-2047">Passeport n °</span></span>
- <span data-ttu-id="d7f91-2048">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="d7f91-2048">Passeport Non</span></span>
- <span data-ttu-id="d7f91-2049">Passeport #</span><span class="sxs-lookup"><span data-stu-id="d7f91-2049">Passeport #</span></span>
- <span data-ttu-id="d7f91-2050">Passeport#</span><span class="sxs-lookup"><span data-stu-id="d7f91-2050">Passeport#</span></span>
- <span data-ttu-id="d7f91-2051">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="d7f91-2051">PasseportNon</span></span>
- <span data-ttu-id="d7f91-2052">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="d7f91-2052">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="d7f91-2053">法国社会保险号 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="d7f91-2053">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-2054">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-2054">Format</span></span>

<span data-ttu-id="d7f91-2055">15 个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2055">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-2056">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2056">Pattern</span></span>

<span data-ttu-id="d7f91-2057">必须匹配两种模式之一：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2057">Must match one of two patterns:</span></span>
- <span data-ttu-id="d7f91-2058">13位数, 后跟一个空格, 后跟两个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2058">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="d7f91-2059">或</span><span class="sxs-lookup"><span data-stu-id="d7f91-2059">or</span></span>
- <span data-ttu-id="d7f91-2060">15 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2060">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-2061">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-2061">Checksum</span></span>

<span data-ttu-id="d7f91-2062">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-2062">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-2063">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-2063">Definition</span></span>

<span data-ttu-id="d7f91-2064">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2064">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2065">函数 Func_french_insee 或 Func_fr_insee 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2065">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2066">找到 Keyword_fr_insee 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2066">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="d7f91-2067">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2067">The checksum passes.</span></span>

<span data-ttu-id="d7f91-2068">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2068">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2069">函数 Func_french_insee 或 Func_fr_insee 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2069">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2070">未找到 Keyword_fr_insee 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2070">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="d7f91-2071">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2071">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-2072">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2072">Keywords</span></span>

#### <a name="keyword_fr_insee"></a><span data-ttu-id="d7f91-2073">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="d7f91-2073">Keyword_fr_insee</span></span>

- <span data-ttu-id="d7f91-2074">insee</span><span class="sxs-lookup"><span data-stu-id="d7f91-2074">insee</span></span>
- <span data-ttu-id="d7f91-2075">securité sociale</span><span class="sxs-lookup"><span data-stu-id="d7f91-2075">securité sociale</span></span>
- <span data-ttu-id="d7f91-2076">securite sociale</span><span class="sxs-lookup"><span data-stu-id="d7f91-2076">securite sociale</span></span>
- <span data-ttu-id="d7f91-2077">national id</span><span class="sxs-lookup"><span data-stu-id="d7f91-2077">national id</span></span>
- <span data-ttu-id="d7f91-2078">national identification</span><span class="sxs-lookup"><span data-stu-id="d7f91-2078">national identification</span></span>
- <span data-ttu-id="d7f91-2079">numéro d identité</span><span class="sxs-lookup"><span data-stu-id="d7f91-2079">numéro d'identité</span></span>
- <span data-ttu-id="d7f91-2080">no d'identité</span><span class="sxs-lookup"><span data-stu-id="d7f91-2080">no d'identité</span></span>
- <span data-ttu-id="d7f91-2081">不。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2081">no.</span></span> <span data-ttu-id="d7f91-2082">d'identité</span><span class="sxs-lookup"><span data-stu-id="d7f91-2082">d'identité</span></span>
- <span data-ttu-id="d7f91-2083">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="d7f91-2083">numero d'identite</span></span>
- <span data-ttu-id="d7f91-2084">no d'identite</span><span class="sxs-lookup"><span data-stu-id="d7f91-2084">no d'identite</span></span>
- <span data-ttu-id="d7f91-2085">不。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2085">no.</span></span> <span data-ttu-id="d7f91-2086">d'identite</span><span class="sxs-lookup"><span data-stu-id="d7f91-2086">d'identite</span></span>
- <span data-ttu-id="d7f91-2087">social security number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2087">social security number</span></span>
- <span data-ttu-id="d7f91-2088">social security code</span><span class="sxs-lookup"><span data-stu-id="d7f91-2088">social security code</span></span>
- <span data-ttu-id="d7f91-2089">social insurance number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2089">social insurance number</span></span>
- <span data-ttu-id="d7f91-2090">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="d7f91-2090">le numéro d'identification nationale</span></span>
- <span data-ttu-id="d7f91-2091">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="d7f91-2091">d'identité nationale</span></span>
- <span data-ttu-id="d7f91-2092">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="d7f91-2092">numéro de sécurité sociale</span></span>
- <span data-ttu-id="d7f91-2093">le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="d7f91-2093">le code de la sécurité sociale</span></span>
- <span data-ttu-id="d7f91-2094">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="d7f91-2094">numéro d'assurance sociale</span></span>
- <span data-ttu-id="d7f91-2095">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="d7f91-2095">numéro de sécu</span></span>
- <span data-ttu-id="d7f91-2096">code sécu</span><span class="sxs-lookup"><span data-stu-id="d7f91-2096">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="d7f91-2097">德国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-2097">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-2098">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-2098">Format</span></span>

<span data-ttu-id="d7f91-2099">11 个数字和字母组合</span><span class="sxs-lookup"><span data-stu-id="d7f91-2099">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-2100">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2100">Pattern</span></span>

<span data-ttu-id="d7f91-2101">11 位数字和字母（不区分大小写）：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2101">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="d7f91-2102">一个数字或字母</span><span class="sxs-lookup"><span data-stu-id="d7f91-2102">A digit or letter</span></span> 
- <span data-ttu-id="d7f91-2103">两位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2103">Two digits</span></span> 
- <span data-ttu-id="d7f91-2104">六位数字或字母</span><span class="sxs-lookup"><span data-stu-id="d7f91-2104">Six digits or letters</span></span> 
- <span data-ttu-id="d7f91-2105">一位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2105">A digit</span></span> 
- <span data-ttu-id="d7f91-2106">一个数字或字母</span><span class="sxs-lookup"><span data-stu-id="d7f91-2106">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-2107">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-2107">Checksum</span></span>

<span data-ttu-id="d7f91-2108">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-2108">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-2109">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-2109">Definition</span></span>

<span data-ttu-id="d7f91-2110">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2110">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2111">函数 Func_german_drivers_license 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2111">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2112">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2112">At least one of the following is true:</span></span>
    - <span data-ttu-id="d7f91-2113">找到 Keyword_german_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2113">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="d7f91-2114">找到 Keyword_german_drivers_license_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2114">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="d7f91-2115">找到 Keyword_german_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2115">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="d7f91-2116">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2116">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-2117">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2117">Keywords</span></span>

#### <a name="keyword_german_drivers_license_number"></a><span data-ttu-id="d7f91-2118">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2118">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="d7f91-2119">Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="d7f91-2119">Führerschein</span></span>
- <span data-ttu-id="d7f91-2120">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="d7f91-2120">Fuhrerschein</span></span>
- <span data-ttu-id="d7f91-2121">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="d7f91-2121">Fuehrerschein</span></span>
- <span data-ttu-id="d7f91-2122">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="d7f91-2122">Führerscheinnummer</span></span>
- <span data-ttu-id="d7f91-2123">Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="d7f91-2123">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="d7f91-2124">Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="d7f91-2124">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="d7f91-2125">Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="d7f91-2125">Führerschein-</span></span> 
- <span data-ttu-id="d7f91-2126">Fuhrerschein-</span><span class="sxs-lookup"><span data-stu-id="d7f91-2126">Fuhrerschein-</span></span> 
- <span data-ttu-id="d7f91-2127">Fuehrerschein-</span><span class="sxs-lookup"><span data-stu-id="d7f91-2127">Fuehrerschein-</span></span> 
- <span data-ttu-id="d7f91-2128">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="d7f91-2128">FührerscheinnummerNr</span></span>
- <span data-ttu-id="d7f91-2129">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="d7f91-2129">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="d7f91-2130">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="d7f91-2130">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="d7f91-2131">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="d7f91-2131">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="d7f91-2132">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="d7f91-2132">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="d7f91-2133">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="d7f91-2133">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="d7f91-2134">Führerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="d7f91-2134">Führerschein- Nr</span></span>
- <span data-ttu-id="d7f91-2135">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="d7f91-2135">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="d7f91-2136">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="d7f91-2136">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="d7f91-2137">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="d7f91-2137">Führerschein- Klasse</span></span> 
- <span data-ttu-id="d7f91-2138">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="d7f91-2138">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="d7f91-2139">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="d7f91-2139">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="d7f91-2140">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="d7f91-2140">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="d7f91-2141">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="d7f91-2141">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="d7f91-2142">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="d7f91-2142">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="d7f91-2143">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="d7f91-2143">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="d7f91-2144">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="d7f91-2144">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="d7f91-2145">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="d7f91-2145">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="d7f91-2146">Führerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="d7f91-2146">Führerschein- Nr</span></span> 
- <span data-ttu-id="d7f91-2147">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="d7f91-2147">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="d7f91-2148">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="d7f91-2148">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="d7f91-2149">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="d7f91-2149">Führerschein- Klasse</span></span> 
- <span data-ttu-id="d7f91-2150">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="d7f91-2150">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="d7f91-2151">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="d7f91-2151">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="d7f91-2152">通讯</span><span class="sxs-lookup"><span data-stu-id="d7f91-2152">DL</span></span> 
- <span data-ttu-id="d7f91-2153">DLS</span><span class="sxs-lookup"><span data-stu-id="d7f91-2153">DLS</span></span>
- <span data-ttu-id="d7f91-2154">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="d7f91-2154">Driv Lic</span></span> 
- <span data-ttu-id="d7f91-2155">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="d7f91-2155">Driv Licen</span></span> 
- <span data-ttu-id="d7f91-2156">Driv License</span><span class="sxs-lookup"><span data-stu-id="d7f91-2156">Driv License</span></span>
- <span data-ttu-id="d7f91-2157">Driv Licenses</span><span class="sxs-lookup"><span data-stu-id="d7f91-2157">Driv Licenses</span></span> 
- <span data-ttu-id="d7f91-2158">Driv Licence</span><span class="sxs-lookup"><span data-stu-id="d7f91-2158">Driv Licence</span></span> 
- <span data-ttu-id="d7f91-2159">Driv Licences</span><span class="sxs-lookup"><span data-stu-id="d7f91-2159">Driv Licences</span></span> 
- <span data-ttu-id="d7f91-2160">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="d7f91-2160">Driv Lic</span></span> 
- <span data-ttu-id="d7f91-2161">Driver Licen</span><span class="sxs-lookup"><span data-stu-id="d7f91-2161">Driver Licen</span></span> 
- <span data-ttu-id="d7f91-2162">Driver License</span><span class="sxs-lookup"><span data-stu-id="d7f91-2162">Driver License</span></span> 
- <span data-ttu-id="d7f91-2163">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="d7f91-2163">Driver Licenses</span></span> 
- <span data-ttu-id="d7f91-2164">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="d7f91-2164">Driver Licence</span></span> 
- <span data-ttu-id="d7f91-2165">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="d7f91-2165">Driver Licences</span></span> 
- <span data-ttu-id="d7f91-2166">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="d7f91-2166">Drivers Lic</span></span> 
- <span data-ttu-id="d7f91-2167">Drivers Licen</span><span class="sxs-lookup"><span data-stu-id="d7f91-2167">Drivers Licen</span></span> 
- <span data-ttu-id="d7f91-2168">Drivers License</span><span class="sxs-lookup"><span data-stu-id="d7f91-2168">Drivers License</span></span> 
- <span data-ttu-id="d7f91-2169">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="d7f91-2169">Drivers Licenses</span></span> 
- <span data-ttu-id="d7f91-2170">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="d7f91-2170">Drivers Licence</span></span> 
- <span data-ttu-id="d7f91-2171">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="d7f91-2171">Drivers Licences</span></span> 
- <span data-ttu-id="d7f91-2172">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="d7f91-2172">Driver's Lic</span></span> 
- <span data-ttu-id="d7f91-2173">Driver's Licen</span><span class="sxs-lookup"><span data-stu-id="d7f91-2173">Driver's Licen</span></span> 
- <span data-ttu-id="d7f91-2174">Driver's License</span><span class="sxs-lookup"><span data-stu-id="d7f91-2174">Driver's License</span></span> 
- <span data-ttu-id="d7f91-2175">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="d7f91-2175">Driver's Licenses</span></span> 
- <span data-ttu-id="d7f91-2176">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="d7f91-2176">Driver's Licence</span></span> 
- <span data-ttu-id="d7f91-2177">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="d7f91-2177">Driver's Licences</span></span> 
- <span data-ttu-id="d7f91-2178">Driving Lic</span><span class="sxs-lookup"><span data-stu-id="d7f91-2178">Driving Lic</span></span> 
- <span data-ttu-id="d7f91-2179">Driving Licen</span><span class="sxs-lookup"><span data-stu-id="d7f91-2179">Driving Licen</span></span> 
- <span data-ttu-id="d7f91-2180">Driving License</span><span class="sxs-lookup"><span data-stu-id="d7f91-2180">Driving License</span></span> 
- <span data-ttu-id="d7f91-2181">Driving Licenses</span><span class="sxs-lookup"><span data-stu-id="d7f91-2181">Driving Licenses</span></span> 
- <span data-ttu-id="d7f91-2182">Driving Licence</span><span class="sxs-lookup"><span data-stu-id="d7f91-2182">Driving Licence</span></span> 
- <span data-ttu-id="d7f91-2183">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="d7f91-2183">Driving Licences</span></span>

#### <a name="keyword_german_drivers_license_collaborative"></a><span data-ttu-id="d7f91-2184">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="d7f91-2184">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="d7f91-2185">Nr-Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="d7f91-2185">Nr-Führerschein</span></span> 
- <span data-ttu-id="d7f91-2186">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="d7f91-2186">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="d7f91-2187">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="d7f91-2187">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="d7f91-2188">Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="d7f91-2188">No-Führerschein</span></span> 
- <span data-ttu-id="d7f91-2189">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="d7f91-2189">No-Fuhrerschein</span></span> 
- <span data-ttu-id="d7f91-2190">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="d7f91-2190">No-Fuehrerschein</span></span> 
- <span data-ttu-id="d7f91-2191">N-Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="d7f91-2191">N-Führerschein</span></span> 
- <span data-ttu-id="d7f91-2192">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="d7f91-2192">N-Fuhrerschein</span></span> 
- <span data-ttu-id="d7f91-2193">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="d7f91-2193">N-Fuehrerschein</span></span>
- <span data-ttu-id="d7f91-2194">Nr-Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="d7f91-2194">Nr-Führerschein</span></span> 
- <span data-ttu-id="d7f91-2195">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="d7f91-2195">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="d7f91-2196">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="d7f91-2196">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="d7f91-2197">Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="d7f91-2197">No-Führerschein</span></span> 
- <span data-ttu-id="d7f91-2198">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="d7f91-2198">No-Fuhrerschein</span></span> 
- <span data-ttu-id="d7f91-2199">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="d7f91-2199">No-Fuehrerschein</span></span> 
- <span data-ttu-id="d7f91-2200">N-Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="d7f91-2200">N-Führerschein</span></span> 
- <span data-ttu-id="d7f91-2201">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="d7f91-2201">N-Fuhrerschein</span></span> 
- <span data-ttu-id="d7f91-2202">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="d7f91-2202">N-Fuehrerschein</span></span> 

#### <a name="keyword_german_drivers_license"></a><span data-ttu-id="d7f91-2203">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="d7f91-2203">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="d7f91-2204">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="d7f91-2204">ausstellungsdatum</span></span>
- <span data-ttu-id="d7f91-2205">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="d7f91-2205">ausstellungsort</span></span>
- <span data-ttu-id="d7f91-2206">ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="d7f91-2206">ausstellende behöde</span></span>
- <span data-ttu-id="d7f91-2207">ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="d7f91-2207">ausstellende behorde</span></span>
- <span data-ttu-id="d7f91-2208">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="d7f91-2208">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="d7f91-2209">德国护照号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-2209">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-2210">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-2210">Format</span></span>

<span data-ttu-id="d7f91-2211">10 个数字或字母</span><span class="sxs-lookup"><span data-stu-id="d7f91-2211">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-2212">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2212">Pattern</span></span>

<span data-ttu-id="d7f91-2213">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2213">Pattern must include all of the following:</span></span>
- <span data-ttu-id="d7f91-2214">第一个字符是这一组（C、F、G、H、J、K）中的数字或字母</span><span class="sxs-lookup"><span data-stu-id="d7f91-2214">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="d7f91-2215">三位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2215">Three digits</span></span> 
- <span data-ttu-id="d7f91-2216">五位数字或字母都来源于这一组（C、-H、J-N、P、R、T，V-Z）</span><span class="sxs-lookup"><span data-stu-id="d7f91-2216">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="d7f91-2217">一位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2217">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-2218">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-2218">Checksum</span></span>

<span data-ttu-id="d7f91-2219">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-2219">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-2220">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-2220">Definition</span></span>

<span data-ttu-id="d7f91-2221">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2221">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2222">函数 Func_german_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2222">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2223">找到以下任意五个关键字列表中的关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2223">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="d7f91-2224">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2224">The checksum passes.</span></span>

<span data-ttu-id="d7f91-2225">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2226">函数 Func_german_passport_data 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2226">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2227">找到以下任意五个关键字列表中的关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2227">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="d7f91-2228">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2228">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-2229">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2229">Keywords</span></span>

#### <a name="keyword_german_passport"></a><span data-ttu-id="d7f91-2230">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="d7f91-2230">Keyword_german_passport</span></span>

- <span data-ttu-id="d7f91-2231">reisepass</span><span class="sxs-lookup"><span data-stu-id="d7f91-2231">reisepass</span></span>
- <span data-ttu-id="d7f91-2232">reisepasse</span><span class="sxs-lookup"><span data-stu-id="d7f91-2232">reisepasse</span></span>
- <span data-ttu-id="d7f91-2233">reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="d7f91-2233">reisepassnummer</span></span>
- <span data-ttu-id="d7f91-2234">登记卡</span><span class="sxs-lookup"><span data-stu-id="d7f91-2234">passport</span></span>
- <span data-ttu-id="d7f91-2235">passports</span><span class="sxs-lookup"><span data-stu-id="d7f91-2235">passports</span></span>

#### <a name="keyword_german_passport_collaborative"></a><span data-ttu-id="d7f91-2236">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="d7f91-2236">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="d7f91-2237">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="d7f91-2237">geburtsdatum</span></span>
- <span data-ttu-id="d7f91-2238">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="d7f91-2238">ausstellungsdatum</span></span>
- <span data-ttu-id="d7f91-2239">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="d7f91-2239">ausstellungsort</span></span>

#### <a name="keyword_german_passport_number"></a><span data-ttu-id="d7f91-2240">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2240">Keyword_german_passport_number</span></span>

<span data-ttu-id="d7f91-2241">Reisepass Nr-Reisepass</span><span class="sxs-lookup"><span data-stu-id="d7f91-2241">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keyword_german_passport1"></a><span data-ttu-id="d7f91-2242">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="d7f91-2242">Keyword_german_passport1</span></span>

<span data-ttu-id="d7f91-2243">Reisepass-Nr</span><span class="sxs-lookup"><span data-stu-id="d7f91-2243">Reisepass-Nr</span></span>

#### <a name="keyword_german_passport2"></a><span data-ttu-id="d7f91-2244">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="d7f91-2244">Keyword_german_passport2</span></span>

<span data-ttu-id="d7f91-2245">bnationalit</span><span class="sxs-lookup"><span data-stu-id="d7f91-2245">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="d7f91-2246">德国身份证号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-2246">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-2247">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-2247">Format</span></span>

<span data-ttu-id="d7f91-2248">自2010年11月1日起: 九个字母和数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2248">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="d7f91-2249">从1年4月1987至31年10月 2010:10 位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2249">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-2250">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2250">Pattern</span></span>

<span data-ttu-id="d7f91-2251">自 2010 年 11 月 1 日起：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2251">Since 1 November 2010:</span></span>
- <span data-ttu-id="d7f91-2252">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="d7f91-2252">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="d7f91-2253">八个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2253">Eight digits</span></span>

<span data-ttu-id="d7f91-2254">介于1年4月1987至 31 10 月 2010:</span><span class="sxs-lookup"><span data-stu-id="d7f91-2254">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="d7f91-2255">10 个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2255">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-2256">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-2256">Checksum</span></span>

<span data-ttu-id="d7f91-2257">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-2257">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-2258">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-2258">Definition</span></span>

<span data-ttu-id="d7f91-2259">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2259">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2260">正则表达式 Regex_germany_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2260">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2261">找到 Keyword_germany_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2261">A keyword from Keyword_germany_id_card is found.</span></span>

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-2262">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2262">Keywords</span></span>

#### <a name="keyword_germany_id_card"></a><span data-ttu-id="d7f91-2263">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="d7f91-2263">Keyword_germany_id_card</span></span>

- <span data-ttu-id="d7f91-2264">Identity Card</span><span class="sxs-lookup"><span data-stu-id="d7f91-2264">Identity Card</span></span>
- <span data-ttu-id="d7f91-2265">ID</span><span class="sxs-lookup"><span data-stu-id="d7f91-2265">ID</span></span>
- <span data-ttu-id="d7f91-2266">Id</span><span class="sxs-lookup"><span data-stu-id="d7f91-2266">Identification</span></span>
- <span data-ttu-id="d7f91-2267">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="d7f91-2267">Personalausweis</span></span>
- <span data-ttu-id="d7f91-2268">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="d7f91-2268">Identifizierungsnummer</span></span>
- <span data-ttu-id="d7f91-2269">Ausweis</span><span class="sxs-lookup"><span data-stu-id="d7f91-2269">Ausweis</span></span>
- <span data-ttu-id="d7f91-2270">Identifikation</span><span class="sxs-lookup"><span data-stu-id="d7f91-2270">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="d7f91-2271">希腊国家 ID 卡</span><span class="sxs-lookup"><span data-stu-id="d7f91-2271">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-2272">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-2272">Format</span></span>

<span data-ttu-id="d7f91-2273">7-8 个字母和数字组合加一个短划线</span><span class="sxs-lookup"><span data-stu-id="d7f91-2273">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-2274">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2274">Pattern</span></span>

<span data-ttu-id="d7f91-2275">七个字母和数字（旧格式）：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2275">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="d7f91-2276">一个字母（希腊字母表中的任一字母） </span><span class="sxs-lookup"><span data-stu-id="d7f91-2276">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="d7f91-2277">一个短划线 </span><span class="sxs-lookup"><span data-stu-id="d7f91-2277">A dash</span></span> 
- <span data-ttu-id="d7f91-2278">六位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2278">Six digits</span></span>

<span data-ttu-id="d7f91-2279">八个字母和数字（新格式）：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2279">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="d7f91-2280">大写字符同时出现在希腊和拉丁字母表中的两个字母 (ABEZHIKMNOPTYX) </span><span class="sxs-lookup"><span data-stu-id="d7f91-2280">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="d7f91-2281">一个短划线 </span><span class="sxs-lookup"><span data-stu-id="d7f91-2281">A dash</span></span> 
- <span data-ttu-id="d7f91-2282">六位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2282">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-2283">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-2283">Checksum</span></span>

<span data-ttu-id="d7f91-2284">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-2284">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-2285">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-2285">Definition</span></span>

<span data-ttu-id="d7f91-2286">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2286">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2287">正则表达式 Regex_greece_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2287">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2288">找到 Keyword_greece_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2288">A keyword from Keyword_greece_id_card is found.</span></span>

```xml
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-2289">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2289">Keywords</span></span>

#### <a name="keyword_greece_id_card"></a><span data-ttu-id="d7f91-2290">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="d7f91-2290">Keyword_greece_id_card</span></span>

- <span data-ttu-id="d7f91-2291">Greek identity Card</span><span class="sxs-lookup"><span data-stu-id="d7f91-2291">Greek identity Card</span></span>
- <span data-ttu-id="d7f91-2292">Tautotita</span><span class="sxs-lookup"><span data-stu-id="d7f91-2292">Tautotita</span></span>
- <span data-ttu-id="d7f91-2293">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="d7f91-2293">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="d7f91-2294">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="d7f91-2294">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="d7f91-2295">香港身份证 (HKID) 号</span><span class="sxs-lookup"><span data-stu-id="d7f91-2295">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-2296">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-2296">Format</span></span>

<span data-ttu-id="d7f91-2297">8-9 个字母和数字组合，最后一个字符两边可选择加括号</span><span class="sxs-lookup"><span data-stu-id="d7f91-2297">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-2298">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2298">Pattern</span></span>

<span data-ttu-id="d7f91-2299">8-9 个字母组合：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2299">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="d7f91-2300">1-2 个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="d7f91-2300">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="d7f91-2301">六个数字 </span><span class="sxs-lookup"><span data-stu-id="d7f91-2301">Six digits</span></span> 
- <span data-ttu-id="d7f91-2302">最后一个字符（任意数字或字母 A）是校验位，两边可以选择加括号。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2302">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-2303">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-2303">Checksum</span></span>

<span data-ttu-id="d7f91-2304">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-2304">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-2305">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-2305">Definition</span></span>

<span data-ttu-id="d7f91-2306">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2306">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2307">函数 Func_hong_kong_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2307">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2308">找到 Keyword_hong_kong_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2308">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="d7f91-2309">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2309">The checksum passes.</span></span>

<span data-ttu-id="d7f91-2310">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2310">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2311">函数 Func_hong_kong_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2311">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2312">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2312">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-2313">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2313">Keywords</span></span>

#### <a name="keyword_hong_kong_id_card"></a><span data-ttu-id="d7f91-2314">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="d7f91-2314">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="d7f91-2315">中国香港恒等卡片</span><span class="sxs-lookup"><span data-stu-id="d7f91-2315">hong kong identity card</span></span>
- <span data-ttu-id="d7f91-2316">HKIDC</span><span class="sxs-lookup"><span data-stu-id="d7f91-2316">HKIDC</span></span>
- <span data-ttu-id="d7f91-2317">id card</span><span class="sxs-lookup"><span data-stu-id="d7f91-2317">id card</span></span>
- <span data-ttu-id="d7f91-2318">identity card</span><span class="sxs-lookup"><span data-stu-id="d7f91-2318">identity card</span></span>
- <span data-ttu-id="d7f91-2319">hk identity 卡片</span><span class="sxs-lookup"><span data-stu-id="d7f91-2319">hk identity card</span></span>
- <span data-ttu-id="d7f91-2320">香港 id</span><span class="sxs-lookup"><span data-stu-id="d7f91-2320">hong kong id</span></span>
- <span data-ttu-id="d7f91-2321">香港身份證</span><span class="sxs-lookup"><span data-stu-id="d7f91-2321">香港身份證</span></span>
- <span data-ttu-id="d7f91-2322">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="d7f91-2322">香港永久性居民身份證</span></span>
- <span data-ttu-id="d7f91-2323">證</span><span class="sxs-lookup"><span data-stu-id="d7f91-2323">身份證</span></span>
- <span data-ttu-id="d7f91-2324">身份証</span><span class="sxs-lookup"><span data-stu-id="d7f91-2324">身份証</span></span>
- <span data-ttu-id="d7f91-2325">身分證</span><span class="sxs-lookup"><span data-stu-id="d7f91-2325">身分證</span></span>
- <span data-ttu-id="d7f91-2326">身分証</span><span class="sxs-lookup"><span data-stu-id="d7f91-2326">身分証</span></span>
- <span data-ttu-id="d7f91-2327">香港身份証</span><span class="sxs-lookup"><span data-stu-id="d7f91-2327">香港身份証</span></span>
- <span data-ttu-id="d7f91-2328">香港身分證</span><span class="sxs-lookup"><span data-stu-id="d7f91-2328">香港身分證</span></span>
- <span data-ttu-id="d7f91-2329">香港身分証</span><span class="sxs-lookup"><span data-stu-id="d7f91-2329">香港身分証</span></span>
- <span data-ttu-id="d7f91-2330">香港身份證</span><span class="sxs-lookup"><span data-stu-id="d7f91-2330">香港身份證</span></span>
- <span data-ttu-id="d7f91-2331">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="d7f91-2331">香港居民身份證</span></span>
- <span data-ttu-id="d7f91-2332">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="d7f91-2332">香港居民身份証</span></span>
- <span data-ttu-id="d7f91-2333">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="d7f91-2333">香港居民身分證</span></span>
- <span data-ttu-id="d7f91-2334">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="d7f91-2334">香港居民身分証</span></span>
- <span data-ttu-id="d7f91-2335">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="d7f91-2335">香港永久性居民身份証</span></span>
- <span data-ttu-id="d7f91-2336">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="d7f91-2336">香港永久性居民身分證</span></span>
- <span data-ttu-id="d7f91-2337">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="d7f91-2337">香港永久性居民身分証</span></span>
- <span data-ttu-id="d7f91-2338">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="d7f91-2338">香港永久性居民身份證</span></span>
- <span data-ttu-id="d7f91-2339">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="d7f91-2339">香港非永久性居民身份證</span></span>
- <span data-ttu-id="d7f91-2340">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="d7f91-2340">香港非永久性居民身份証</span></span>
- <span data-ttu-id="d7f91-2341">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="d7f91-2341">香港非永久性居民身分證</span></span>
- <span data-ttu-id="d7f91-2342">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="d7f91-2342">香港非永久性居民身分証</span></span>
- <span data-ttu-id="d7f91-2343">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="d7f91-2343">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="d7f91-2344">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="d7f91-2344">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="d7f91-2345">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="d7f91-2345">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="d7f91-2346">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="d7f91-2346">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="d7f91-2347">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="d7f91-2347">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="d7f91-2348">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="d7f91-2348">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="d7f91-2349">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="d7f91-2349">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="d7f91-2350">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="d7f91-2350">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="d7f91-2351">印度永久帐号 (PAN)</span><span class="sxs-lookup"><span data-stu-id="d7f91-2351">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-2352">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-2352">Format</span></span>

<span data-ttu-id="d7f91-2353">10 个字母或数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2353">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-2354">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2354">Pattern</span></span>

<span data-ttu-id="d7f91-2355">10 个字母或数字：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2355">10 letters or digits:</span></span>
- <span data-ttu-id="d7f91-2356">五个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="d7f91-2356">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="d7f91-2357">四位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2357">Four digits</span></span> 
- <span data-ttu-id="d7f91-2358">一个字母，是字母校验位</span><span class="sxs-lookup"><span data-stu-id="d7f91-2358">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-2359">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-2359">Checksum</span></span>

<span data-ttu-id="d7f91-2360">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-2360">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-2361">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-2361">Definition</span></span>

<span data-ttu-id="d7f91-2362">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2362">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2363">正则表达式 Regex_india_permanent_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2363">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2364">找到 Keyword_india_permanent_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2364">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="d7f91-2365">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2365">The checksum passes.</span></span>

```xml
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-2366">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2366">Keywords</span></span>

#### <a name="keyword_india_permanent_account_number"></a><span data-ttu-id="d7f91-2367">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2367">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="d7f91-2368">Permanent Account Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2368">Permanent Account Number</span></span> 
- <span data-ttu-id="d7f91-2369">蛋糕</span><span class="sxs-lookup"><span data-stu-id="d7f91-2369">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="d7f91-2370">India Unique Identification (Aadhaar) Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2370">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-2371">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-2371">Format</span></span>

<span data-ttu-id="d7f91-2372">12 个数字（包含可选空格或短划线）</span><span class="sxs-lookup"><span data-stu-id="d7f91-2372">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-2373">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2373">Pattern</span></span>

<span data-ttu-id="d7f91-2374">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2374">12 digits:</span></span>
- <span data-ttu-id="d7f91-2375">四个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2375">Four digits</span></span> 
- <span data-ttu-id="d7f91-2376">一个可选空格或短划线 </span><span class="sxs-lookup"><span data-stu-id="d7f91-2376">An optional space or dash</span></span> 
- <span data-ttu-id="d7f91-2377">四个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2377">Four digits</span></span> 
- <span data-ttu-id="d7f91-2378">一个可选空格或短划线 </span><span class="sxs-lookup"><span data-stu-id="d7f91-2378">An optional space or dash</span></span> 
- <span data-ttu-id="d7f91-2379">最后一个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="d7f91-2379">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-2380">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-2380">Checksum</span></span>

<span data-ttu-id="d7f91-2381">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-2381">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-2382">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-2382">Definition</span></span>

<span data-ttu-id="d7f91-2383">DLP 策略 85% 确信在300个字符的邻近度内检测到此类型的敏感信息: 函数 Func_india_aadhaar 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2383">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="d7f91-2384">找到 Keyword_india_aadhar 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2384">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="d7f91-2385">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2385">The checksum passes.</span></span>
<span data-ttu-id="d7f91-2386">DLP 策略 75% 确信在300个字符的邻近度内检测到此类型的敏感信息: 函数 Func_india_aadhaar 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2386">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="d7f91-2387">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2387">The checksum passes.</span></span>
```xml
<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_india_aadhaar"/>
     <Match idRef="Keyword_india_aadhar"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_india_aadhaar"/>
  </Pattern>
</Entity>

### Keywords
   
#### Keyword_india_aadhar
- Aadhar
- Aadhaar
- UID
- आधार
   
## Indonesia Identity Card (KTP) Number

### Format

16 digits containing optional periods

### Pattern

16 digits:
- Two-digit province code 
- A period (optional) 
- Two-digit regency or city code 
- Two-digit subdistrict code 
- A period (optional) 
- Six digits in the format DDMMYY which are the date of birth 
- A period (optional) 
- Four digits

### Checksum

No

### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The regular expression Regex_indonesia_id_card finds content that matches the pattern.
- A keyword from Keyword_indonesia_id_card is found.

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The regular expression Regex_indonesia_id_card finds content that matches the pattern.

```
<!-- Indonesia Identity Card (KTP) Number -->
<span data-ttu-id="d7f91-2388"><Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Regex_indonesia_id_card"/> <Match idRef="Keyword_indonesia_id_card"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_indonesia_id_card"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="d7f91-2388"></span></span>
```

### Keywords
   
#### Keyword_indonesia_id_card

- KTP
- Kartu Tanda Penduduk 
- Nomor Induk Kependudukan 
   
## International Banking Account Number (IBAN)

### Format

Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)

### Pattern

Pattern must include all of the following:

- Two-letter country code
- Two check digits (followed by an optional space) 
- 1-7 groups of four letters or digits (can be separated by spaces)
- 1-3 letters or digits

The format for each country is slightly different. The IBAN sensitive information type covers these 60 countries:

ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg

### Checksum

Yes

### Definition

A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_iban finds content that matches the pattern.
- The checksum passes.

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-2389">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2389">Keywords</span></span>

<span data-ttu-id="d7f91-2390">无</span><span class="sxs-lookup"><span data-stu-id="d7f91-2390">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="d7f91-2391">IP 地址</span><span class="sxs-lookup"><span data-stu-id="d7f91-2391">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-2392">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-2392">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="d7f91-2393">IPv4</span><span class="sxs-lookup"><span data-stu-id="d7f91-2393">IPv4:</span></span>
<span data-ttu-id="d7f91-2394">解释 IPv4 地址格式化（点）版本或非格式化（没有点）版本的复杂模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2394">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="d7f91-2395">Ipv4</span><span class="sxs-lookup"><span data-stu-id="d7f91-2395">IPv6:</span></span>
<span data-ttu-id="d7f91-2396"> 解释格式化 IPv6 号码（包含冒号）的复杂模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2396">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-2397">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2397">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-2398">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-2398">Checksum</span></span>

<span data-ttu-id="d7f91-2399">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-2399">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-2400">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-2400">Definition</span></span>

<span data-ttu-id="d7f91-2401">对于 IPv6，在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2401">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2402">正则表达式 Regex_ipv6_address 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2402">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2403">未找到 Keyword_ipaddress 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2403">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="d7f91-2404">对于 IPv4，在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2404">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2405">正则表达式 Regex_ipv4_address 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2405">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2406">找到 Keyword_ipaddress 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2406">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="d7f91-2407">对于 IPv6，在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2407">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2408">正则表达式 Regex_ipv6_address 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2408">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2409">未找到 Keyword_ipaddress 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2409">No keyword from Keyword_ipaddress is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-2410">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2410">Keywords</span></span>

#### <a name="keyword_ipaddress"></a><span data-ttu-id="d7f91-2411">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="d7f91-2411">Keyword_ipaddress</span></span>

- <span data-ttu-id="d7f91-2412">IP（此关键字区分大小写）</span><span class="sxs-lookup"><span data-stu-id="d7f91-2412">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="d7f91-2413">ip address</span><span class="sxs-lookup"><span data-stu-id="d7f91-2413">ip address</span></span> 
- <span data-ttu-id="d7f91-2414">ip addresses</span><span class="sxs-lookup"><span data-stu-id="d7f91-2414">ip addresses</span></span>
- <span data-ttu-id="d7f91-2415">internet protocol</span><span class="sxs-lookup"><span data-stu-id="d7f91-2415">internet protocol</span></span>
- <span data-ttu-id="d7f91-2416">IP-כתובת ה</span><span class="sxs-lookup"><span data-stu-id="d7f91-2416">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="d7f91-2417">国际分类的 Diseases (ICD-10 CM)</span><span class="sxs-lookup"><span data-stu-id="d7f91-2417">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-2418">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-2418">Format</span></span>

<span data-ttu-id="d7f91-2419">Dictionary</span><span class="sxs-lookup"><span data-stu-id="d7f91-2419">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-2420">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2420">Pattern</span></span>

<span data-ttu-id="d7f91-2421">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2421">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-2422">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-2422">Checksum</span></span>

<span data-ttu-id="d7f91-2423">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-2423">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-2424">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-2424">Definition</span></span>

<span data-ttu-id="d7f91-2425">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2425">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2426">找到 Dictionary_icd_10_cm 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2426">A keyword from Dictionary_icd_10_cm is found.</span></span>

```xml
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

<span data-ttu-id="d7f91-2427">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2427">Keywords</span></span>

<span data-ttu-id="d7f91-2428">Dictionary_icd_10_cm 关键字词典中的任何术语, 它基于[Diseases 的国际分类、第十个修订、临床修改 (icd-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604)。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2428">Any term from the Dictionary_icd_10_cm keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="d7f91-2429">此类型仅查找术语, 而不是保险代码。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2429">This type looks only for the term, not the insurance codes.</span></span>

   
## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="d7f91-2430">国际分类的 Diseases (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="d7f91-2430">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-2431">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-2431">Format</span></span>

<span data-ttu-id="d7f91-2432">Dictionary</span><span class="sxs-lookup"><span data-stu-id="d7f91-2432">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-2433">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2433">Pattern</span></span>

<span data-ttu-id="d7f91-2434">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2434">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-2435">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-2435">Checksum</span></span>

<span data-ttu-id="d7f91-2436">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-2436">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-2437">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-2437">Definition</span></span>

<span data-ttu-id="d7f91-2438">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2438">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2439">找到 Dictionary_icd_9_cm 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2439">A keyword from Dictionary_icd_9_cm is found.</span></span>

```xml
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-2440">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2440">Keywords</span></span>

<span data-ttu-id="d7f91-2441">Dictionary_icd_9_cm 关键字词典中的任何术语, 基于[Diseases 的国际分类、第九修订版、临床修改 (icd-9 cm)](https://go.microsoft.com/fwlink/?linkid=852605)。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2441">Any term from the Dictionary_icd_9_cm keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="d7f91-2442">此类型仅查找术语, 而不是保险代码。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2442">This type looks only for the term, not the insurance codes.</span></span>
   
## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="d7f91-2443">爱尔兰个人公共服务 (PPS) 号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-2443">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-2444">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-2444">Format</span></span>

<span data-ttu-id="d7f91-2445">旧格式 (到 31 Dec 2012):</span><span class="sxs-lookup"><span data-stu-id="d7f91-2445">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="d7f91-2446">七位数字后跟 1-2  个字母 </span><span class="sxs-lookup"><span data-stu-id="d7f91-2446">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="d7f91-2447">新格式 (2013 年1月1日和之后):</span><span class="sxs-lookup"><span data-stu-id="d7f91-2447">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="d7f91-2448">七位数字后跟两个字母</span><span class="sxs-lookup"><span data-stu-id="d7f91-2448">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-2449">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2449">Pattern</span></span>

<span data-ttu-id="d7f91-2450">旧格式 (到 31 Dec 2012):</span><span class="sxs-lookup"><span data-stu-id="d7f91-2450">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="d7f91-2451">七个数字 </span><span class="sxs-lookup"><span data-stu-id="d7f91-2451">Seven digits</span></span> 
- <span data-ttu-id="d7f91-2452">1-2 个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="d7f91-2452">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="d7f91-2453">新格式 (2013 年1月1日和之后):</span><span class="sxs-lookup"><span data-stu-id="d7f91-2453">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="d7f91-2454">七个数字 </span><span class="sxs-lookup"><span data-stu-id="d7f91-2454">Seven digits</span></span> 
- <span data-ttu-id="d7f91-2455">一个字母（不区分大小写），是字母校验位 </span><span class="sxs-lookup"><span data-stu-id="d7f91-2455">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="d7f91-2456">字母“A”或“H”（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="d7f91-2456">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-2457">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-2457">Checksum</span></span>

<span data-ttu-id="d7f91-2458">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-2458">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-2459">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-2459">Definition</span></span>

<span data-ttu-id="d7f91-2460">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2460">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2461">函数 Func_ireland_pps 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2461">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2462">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2462">One of the following is true:</span></span>
    - <span data-ttu-id="d7f91-2463">找到 Keyword_ireland_pps 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2463">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="d7f91-2464">函数 Func_eu_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2464">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="d7f91-2465">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2465">The checksum passes.</span></span>

<span data-ttu-id="d7f91-2466">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2466">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2467">函数 Func_ireland_pps 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2467">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2468">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2468">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-2469">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2469">Keywords</span></span>

#### <a name="keyword_ireland_pps"></a><span data-ttu-id="d7f91-2470">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="d7f91-2470">Keyword_ireland_pps</span></span>

- <span data-ttu-id="d7f91-2471">Personal Public Service Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2471">Personal Public Service Number</span></span> 
- <span data-ttu-id="d7f91-2472">PPS Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2472">PPS Number</span></span> 
- <span data-ttu-id="d7f91-2473">PPS Num</span><span class="sxs-lookup"><span data-stu-id="d7f91-2473">PPS Num</span></span> 
- <span data-ttu-id="d7f91-2474">PPS No.</span><span class="sxs-lookup"><span data-stu-id="d7f91-2474">PPS No.</span></span> 
- <span data-ttu-id="d7f91-2475">PPS #</span><span class="sxs-lookup"><span data-stu-id="d7f91-2475">PPS #</span></span> 
- <span data-ttu-id="d7f91-2476">.PPS#</span><span class="sxs-lookup"><span data-stu-id="d7f91-2476">PPS#</span></span> 
- <span data-ttu-id="d7f91-2477">PPSN</span><span class="sxs-lookup"><span data-stu-id="d7f91-2477">PPSN</span></span> 
- <span data-ttu-id="d7f91-2478">Public Services Card</span><span class="sxs-lookup"><span data-stu-id="d7f91-2478">Public Services Card</span></span> 
- <span data-ttu-id="d7f91-2479">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="d7f91-2479">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="d7f91-2480">Uimh.</span><span class="sxs-lookup"><span data-stu-id="d7f91-2480">Uimh.</span></span> <span data-ttu-id="d7f91-2481">PSP</span><span class="sxs-lookup"><span data-stu-id="d7f91-2481">PSP</span></span> 
- <span data-ttu-id="d7f91-2482">PSP</span><span class="sxs-lookup"><span data-stu-id="d7f91-2482">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="d7f91-2483">以色列银行帐号</span><span class="sxs-lookup"><span data-stu-id="d7f91-2483">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-2484">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-2484">Format</span></span>

<span data-ttu-id="d7f91-2485">13 位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2485">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-2486">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2486">Pattern</span></span>

<span data-ttu-id="d7f91-2487">格式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2487">Formatted:</span></span>
- <span data-ttu-id="d7f91-2488">两位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2488">Two digits</span></span> 
- <span data-ttu-id="d7f91-2489">破折号</span><span class="sxs-lookup"><span data-stu-id="d7f91-2489">A dash</span></span> 
- <span data-ttu-id="d7f91-2490">三位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2490">Three digits</span></span> 
- <span data-ttu-id="d7f91-2491">破折号</span><span class="sxs-lookup"><span data-stu-id="d7f91-2491">A dash</span></span> 
- <span data-ttu-id="d7f91-2492">八位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2492">Eight digits</span></span>

<span data-ttu-id="d7f91-2493">纯</span><span class="sxs-lookup"><span data-stu-id="d7f91-2493">Unformatted:</span></span>
- <span data-ttu-id="d7f91-2494">	13 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2494">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-2495">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-2495">Checksum</span></span>

<span data-ttu-id="d7f91-2496">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-2496">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-2497">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-2497">Definition</span></span>

<span data-ttu-id="d7f91-2498">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2499">正则表达式 Regex_israel_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2499">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2500">找到 Keyword_israel_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2500">A keyword from Keyword_israel_bank_account_number is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-2501">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2501">Keywords</span></span>

#### <a name="keyword_israel_bank_account_number"></a><span data-ttu-id="d7f91-2502">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2502">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="d7f91-2503">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2503">Bank Account Number</span></span> 
- <span data-ttu-id="d7f91-2504">Bank Account</span><span class="sxs-lookup"><span data-stu-id="d7f91-2504">Bank Account</span></span> 
- <span data-ttu-id="d7f91-2505">Account Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2505">Account Number</span></span> 
- <span data-ttu-id="d7f91-2506">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="d7f91-2506">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="d7f91-2507">以色列国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="d7f91-2507">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-2508">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-2508">Format</span></span>

<span data-ttu-id="d7f91-2509">九个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2509">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-2510">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2510">Pattern</span></span>

<span data-ttu-id="d7f91-2511">九个连续的数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2511">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-2512">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-2512">Checksum</span></span>

<span data-ttu-id="d7f91-2513">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-2513">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-2514">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-2514">Definition</span></span>

<span data-ttu-id="d7f91-2515">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2515">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2516">函数 Func_israeli_national_id_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2516">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2517">找到 Keyword_Israel_National_ID 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2517">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="d7f91-2518">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2518">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-2519">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2519">Keywords</span></span>

#### <a name="keyword_israel_national_id"></a><span data-ttu-id="d7f91-2520">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="d7f91-2520">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="d7f91-2521">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="d7f91-2521">מספר זהות</span></span> 
- <span data-ttu-id="d7f91-2522">National ID Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2522">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="d7f91-2523">意大利驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-2523">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-2524">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-2524">Format</span></span>

<span data-ttu-id="d7f91-2525">10 个字母和数字的组合</span><span class="sxs-lookup"><span data-stu-id="d7f91-2525">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-2526">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2526">Pattern</span></span>

- <span data-ttu-id="d7f91-2527">10 个字母和数字的组合：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2527">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="d7f91-2528">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="d7f91-2528">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="d7f91-2529">字母“A”或者“V”（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="d7f91-2529">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="d7f91-2530">七个字母（不区分大小写）、数字或下划线字符</span><span class="sxs-lookup"><span data-stu-id="d7f91-2530">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="d7f91-2531">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="d7f91-2531">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-2532">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-2532">Checksum</span></span>

<span data-ttu-id="d7f91-2533">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-2533">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-2534">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-2534">Definition</span></span>

<span data-ttu-id="d7f91-2535">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2536">正则表达式 Regex_italy_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2536">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2537">找到 Keyword_italy_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2537">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-2538">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2538">Keywords</span></span>

#### <a name="keyword_italy_drivers_license_number"></a><span data-ttu-id="d7f91-2539">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2539">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="d7f91-2540">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="d7f91-2540">numero di patente di guida</span></span> 
- <span data-ttu-id="d7f91-2541">patente di guida</span><span class="sxs-lookup"><span data-stu-id="d7f91-2541">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="d7f91-2542">日本银行帐号</span><span class="sxs-lookup"><span data-stu-id="d7f91-2542">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-2543">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-2543">Format</span></span>

<span data-ttu-id="d7f91-2544">七个或八个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2544">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-2545">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2545">Pattern</span></span>

<span data-ttu-id="d7f91-2546">银行帐号：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2546">Bank account number:</span></span>
- <span data-ttu-id="d7f91-2547">七个或八个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2547">Seven or eight digits</span></span>
- <span data-ttu-id="d7f91-2548">银行帐户分支代码：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2548">Bank account branch code:</span></span>
- <span data-ttu-id="d7f91-2549">四位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2549">Four digits</span></span> 
- <span data-ttu-id="d7f91-2550">空格或破折号（可选）</span><span class="sxs-lookup"><span data-stu-id="d7f91-2550">A space or dash (optional)</span></span> 
- <span data-ttu-id="d7f91-2551">三位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2551">Three digits</span></span>

<span data-ttu-id="d7f91-2552">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-2552">Checksum</span></span>

<span data-ttu-id="d7f91-2553">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-2553">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-2554">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-2554">Definition</span></span>

<span data-ttu-id="d7f91-2555">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2555">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2556">函数 Func_jp_bank_account 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2556">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2557">找到 Keyword_jp_bank_account 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2557">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="d7f91-2558">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2558">One of the following is true:</span></span>
- <span data-ttu-id="d7f91-2559">函数 Func_jp_bank_account_branch_code 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2559">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2560">找到 Keyword_jp_bank_branch_code 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2560">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="d7f91-2561">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2561">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2562">函数 Func_jp_bank_account 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2562">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2563">找到 Keyword_jp_bank_account 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2563">A keyword from Keyword_jp_bank_account is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-2564">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2564">Keywords</span></span>

#### <a name="keyword_jp_bank_account"></a><span data-ttu-id="d7f91-2565">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="d7f91-2565">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="d7f91-2566">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2566">Checking Account Number</span></span> 
- <span data-ttu-id="d7f91-2567">Checking Account</span><span class="sxs-lookup"><span data-stu-id="d7f91-2567">Checking Account</span></span> 
- <span data-ttu-id="d7f91-2568">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="d7f91-2568">Checking Account #</span></span> 
- <span data-ttu-id="d7f91-2569">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2569">Checking Acct Number</span></span> 
- <span data-ttu-id="d7f91-2570">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="d7f91-2570">Checking Acct #</span></span> 
- <span data-ttu-id="d7f91-2571">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="d7f91-2571">Checking Acct No.</span></span> 
- <span data-ttu-id="d7f91-2572">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="d7f91-2572">Checking Account No.</span></span> 
- <span data-ttu-id="d7f91-2573">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2573">Bank Account Number</span></span> 
- <span data-ttu-id="d7f91-2574">Bank Account</span><span class="sxs-lookup"><span data-stu-id="d7f91-2574">Bank Account</span></span> 
- <span data-ttu-id="d7f91-2575">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="d7f91-2575">Bank Account #</span></span> 
- <span data-ttu-id="d7f91-2576">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2576">Bank Acct Number</span></span> 
- <span data-ttu-id="d7f91-2577">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="d7f91-2577">Bank Acct #</span></span> 
- <span data-ttu-id="d7f91-2578">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="d7f91-2578">Bank Acct No.</span></span> 
- <span data-ttu-id="d7f91-2579">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="d7f91-2579">Bank Account No.</span></span> 
- <span data-ttu-id="d7f91-2580">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2580">Savings Account Number</span></span> 
- <span data-ttu-id="d7f91-2581">Savings Account</span><span class="sxs-lookup"><span data-stu-id="d7f91-2581">Savings Account</span></span> 
- <span data-ttu-id="d7f91-2582">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="d7f91-2582">Savings Account #</span></span> 
- <span data-ttu-id="d7f91-2583">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2583">Savings Acct Number</span></span> 
- <span data-ttu-id="d7f91-2584">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="d7f91-2584">Savings Acct #</span></span> 
- <span data-ttu-id="d7f91-2585">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="d7f91-2585">Savings Acct No.</span></span> 
- <span data-ttu-id="d7f91-2586">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="d7f91-2586">Savings Account No.</span></span> 
- <span data-ttu-id="d7f91-2587">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2587">Debit Account Number</span></span> 
- <span data-ttu-id="d7f91-2588">Debit Account</span><span class="sxs-lookup"><span data-stu-id="d7f91-2588">Debit Account</span></span> 
- <span data-ttu-id="d7f91-2589">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="d7f91-2589">Debit Account #</span></span> 
- <span data-ttu-id="d7f91-2590">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2590">Debit Acct Number</span></span> 
- <span data-ttu-id="d7f91-2591">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="d7f91-2591">Debit Acct #</span></span> 
- <span data-ttu-id="d7f91-2592">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="d7f91-2592">Debit Acct No.</span></span> 
- <span data-ttu-id="d7f91-2593">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="d7f91-2593">Debit Account No.</span></span> 
- <span data-ttu-id="d7f91-2594">口座番号を当座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="d7f91-2594">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="d7f91-2595">#アカウントの確認、勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="d7f91-2595">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="d7f91-2596">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="d7f91-2596">＃勘定の確認</span></span> 
- <span data-ttu-id="d7f91-2597">勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="d7f91-2597">勘定番号の確認</span></span> 
- <span data-ttu-id="d7f91-2598">口座番号の確認</span><span class="sxs-lookup"><span data-stu-id="d7f91-2598">口座番号の確認</span></span> 
- <span data-ttu-id="d7f91-2599">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="d7f91-2599">銀行口座番号</span></span> 
- <span data-ttu-id="d7f91-2600">銀行口座</span><span class="sxs-lookup"><span data-stu-id="d7f91-2600">銀行口座</span></span> 
- <span data-ttu-id="d7f91-2601">銀行口座＃</span><span class="sxs-lookup"><span data-stu-id="d7f91-2601">銀行口座＃</span></span> 
- <span data-ttu-id="d7f91-2602">銀行の勘定番号</span><span class="sxs-lookup"><span data-stu-id="d7f91-2602">銀行の勘定番号</span></span> 
- <span data-ttu-id="d7f91-2603">銀行のacct＃</span><span class="sxs-lookup"><span data-stu-id="d7f91-2603">銀行のacct＃</span></span> 
- <span data-ttu-id="d7f91-2604">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="d7f91-2604">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="d7f91-2605">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="d7f91-2605">銀行口座番号</span></span>
- <span data-ttu-id="d7f91-2606">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="d7f91-2606">普通預金口座番号</span></span> 
- <span data-ttu-id="d7f91-2607">預金口座</span><span class="sxs-lookup"><span data-stu-id="d7f91-2607">預金口座</span></span> 
- <span data-ttu-id="d7f91-2608">貯蓄口座＃</span><span class="sxs-lookup"><span data-stu-id="d7f91-2608">貯蓄口座＃</span></span> 
- <span data-ttu-id="d7f91-2609">貯蓄勘定の数</span><span class="sxs-lookup"><span data-stu-id="d7f91-2609">貯蓄勘定の数</span></span> 
- <span data-ttu-id="d7f91-2610">貯蓄勘定＃</span><span class="sxs-lookup"><span data-stu-id="d7f91-2610">貯蓄勘定＃</span></span> 
- <span data-ttu-id="d7f91-2611">貯蓄勘定番号</span><span class="sxs-lookup"><span data-stu-id="d7f91-2611">貯蓄勘定番号</span></span> 
- <span data-ttu-id="d7f91-2612">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="d7f91-2612">普通預金口座番号</span></span> 
- <span data-ttu-id="d7f91-2613">引き落とし口座番号</span><span class="sxs-lookup"><span data-stu-id="d7f91-2613">引き落とし口座番号</span></span> 
- <span data-ttu-id="d7f91-2614">口座番号</span><span class="sxs-lookup"><span data-stu-id="d7f91-2614">口座番号</span></span> 
- <span data-ttu-id="d7f91-2615">口座番号＃</span><span class="sxs-lookup"><span data-stu-id="d7f91-2615">口座番号＃</span></span> 
- <span data-ttu-id="d7f91-2616">デビットのacct番号</span><span class="sxs-lookup"><span data-stu-id="d7f91-2616">デビットのacct番号</span></span> 
- <span data-ttu-id="d7f91-2617">デビット勘定＃</span><span class="sxs-lookup"><span data-stu-id="d7f91-2617">デビット勘定＃</span></span> 
- <span data-ttu-id="d7f91-2618">デビットACCTの番号</span><span class="sxs-lookup"><span data-stu-id="d7f91-2618">デビットACCTの番号</span></span> 
- <span data-ttu-id="d7f91-2619">デビット口座番号</span><span class="sxs-lookup"><span data-stu-id="d7f91-2619">デビット口座番号</span></span> 

#### <a name="keyword_jp_bank_branch_code"></a><span data-ttu-id="d7f91-2620">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="d7f91-2620">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="d7f91-2621">Otemachi</span><span class="sxs-lookup"><span data-stu-id="d7f91-2621">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="d7f91-2622">日本驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-2622">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-2623">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-2623">Format</span></span>

<span data-ttu-id="d7f91-2624">12 个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2624">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-2625">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2625">Pattern</span></span>

<span data-ttu-id="d7f91-2626">12 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2626">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-2627">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-2627">Checksum</span></span>

<span data-ttu-id="d7f91-2628">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-2628">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-2629">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-2629">Definition</span></span>

<span data-ttu-id="d7f91-2630">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2630">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2631">函数 Func_jp_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2631">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2632">找到 Keyword_jp_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2632">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-2633">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2633">Keywords</span></span>

#### <a name="keyword_jp_drivers_license_number"></a><span data-ttu-id="d7f91-2634">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2634">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="d7f91-2635">通讯#</span><span class="sxs-lookup"><span data-stu-id="d7f91-2635">dl#</span></span> 
- <span data-ttu-id="d7f91-2636">通讯</span><span class="sxs-lookup"><span data-stu-id="d7f91-2636">DL＃</span></span> 
- <span data-ttu-id="d7f91-2637">dls#</span><span class="sxs-lookup"><span data-stu-id="d7f91-2637">dls#</span></span> 
- <span data-ttu-id="d7f91-2638">DLS</span><span class="sxs-lookup"><span data-stu-id="d7f91-2638">DLS＃</span></span> 
- <span data-ttu-id="d7f91-2639">driver license</span><span class="sxs-lookup"><span data-stu-id="d7f91-2639">driver license</span></span> 
- <span data-ttu-id="d7f91-2640">driver licenses</span><span class="sxs-lookup"><span data-stu-id="d7f91-2640">driver licenses</span></span> 
- <span data-ttu-id="d7f91-2641">drivers license</span><span class="sxs-lookup"><span data-stu-id="d7f91-2641">drivers license</span></span> 
- <span data-ttu-id="d7f91-2642">driver's license</span><span class="sxs-lookup"><span data-stu-id="d7f91-2642">driver's license</span></span> 
- <span data-ttu-id="d7f91-2643">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="d7f91-2643">drivers licenses</span></span> 
- <span data-ttu-id="d7f91-2644">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="d7f91-2644">driver's licenses</span></span> 
- <span data-ttu-id="d7f91-2645">driving licence</span><span class="sxs-lookup"><span data-stu-id="d7f91-2645">driving licence</span></span> 
- <span data-ttu-id="d7f91-2646">.lic#</span><span class="sxs-lookup"><span data-stu-id="d7f91-2646">lic#</span></span> 
- <span data-ttu-id="d7f91-2647">.LIC</span><span class="sxs-lookup"><span data-stu-id="d7f91-2647">LIC＃</span></span> 
- <span data-ttu-id="d7f91-2648">driver'lics#</span><span class="sxs-lookup"><span data-stu-id="d7f91-2648">lics#</span></span> 
- <span data-ttu-id="d7f91-2649">state id</span><span class="sxs-lookup"><span data-stu-id="d7f91-2649">state id</span></span> 
- <span data-ttu-id="d7f91-2650">state identification</span><span class="sxs-lookup"><span data-stu-id="d7f91-2650">state identification</span></span> 
- <span data-ttu-id="d7f91-2651">state identification number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2651">state identification number</span></span> 
- <span data-ttu-id="d7f91-2652">低所得国＃</span><span class="sxs-lookup"><span data-stu-id="d7f91-2652">低所得国＃</span></span> 
- <span data-ttu-id="d7f91-2653">免許証</span><span class="sxs-lookup"><span data-stu-id="d7f91-2653">免許証</span></span> 
- <span data-ttu-id="d7f91-2654">状態ID</span><span class="sxs-lookup"><span data-stu-id="d7f91-2654">状態ID</span></span>
- <span data-ttu-id="d7f91-2655">状態の識別</span><span class="sxs-lookup"><span data-stu-id="d7f91-2655">状態の識別</span></span> 
- <span data-ttu-id="d7f91-2656">状態の識別番号</span><span class="sxs-lookup"><span data-stu-id="d7f91-2656">状態の識別番号</span></span> 
- <span data-ttu-id="d7f91-2657">運転免許</span><span class="sxs-lookup"><span data-stu-id="d7f91-2657">運転免許</span></span> 
- <span data-ttu-id="d7f91-2658">運転免許証</span><span class="sxs-lookup"><span data-stu-id="d7f91-2658">運転免許証</span></span> 
- <span data-ttu-id="d7f91-2659">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="d7f91-2659">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="d7f91-2660">日本护照号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-2660">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-2661">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-2661">Format</span></span>

<span data-ttu-id="d7f91-2662">两个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2662">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-2663">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2663">Pattern</span></span>

<span data-ttu-id="d7f91-2664">两个字母（不区分大小写）后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2664">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-2665">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-2665">Checksum</span></span>

<span data-ttu-id="d7f91-2666">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-2666">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-2667">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-2667">Definition</span></span>

<span data-ttu-id="d7f91-2668">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2668">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2669">函数 Func_jp_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2669">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2670">找到 Keyword_jp_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2670">A keyword from Keyword_jp_passport is found.</span></span>

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-2671">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2671">Keywords</span></span>

#### <a name="keyword_jp_passport"></a><span data-ttu-id="d7f91-2672">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="d7f91-2672">Keyword_jp_passport</span></span>

- <span data-ttu-id="d7f91-2673">パスポート</span><span class="sxs-lookup"><span data-stu-id="d7f91-2673">パスポート</span></span> 
- <span data-ttu-id="d7f91-2674">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="d7f91-2674">パスポート番号</span></span> 
- <span data-ttu-id="d7f91-2675">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="d7f91-2675">パスポートのNum</span></span> 
- <span data-ttu-id="d7f91-2676">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="d7f91-2676">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="d7f91-2677">日本居民登记号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-2677">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-2678">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-2678">Format</span></span>

<span data-ttu-id="d7f91-2679">11 个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2679">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-2680">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2680">Pattern</span></span>

<span data-ttu-id="d7f91-2681">11 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2681">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-2682">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-2682">Checksum</span></span>

<span data-ttu-id="d7f91-2683">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-2683">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-2684">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-2684">Definition</span></span>

<span data-ttu-id="d7f91-2685">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2685">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2686">函数 Func_jp_resident_registration_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2686">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2687">找到 Keyword_jp_resident_registration_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2687">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-2688">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2688">Keywords</span></span>

#### <a name="keyword_jp_resident_registration_number"></a><span data-ttu-id="d7f91-2689">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2689">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="d7f91-2690">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2690">Resident Registration Number</span></span>
- <span data-ttu-id="d7f91-2691">Resident Register Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2691">Resident Register Number</span></span> 
- <span data-ttu-id="d7f91-2692">Residents Basic Registry Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2692">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="d7f91-2693">Resident Registration No.</span><span class="sxs-lookup"><span data-stu-id="d7f91-2693">Resident Registration No.</span></span> 
- <span data-ttu-id="d7f91-2694">Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="d7f91-2694">Resident Register No.</span></span> 
- <span data-ttu-id="d7f91-2695">Residents Basic Registry No.</span><span class="sxs-lookup"><span data-stu-id="d7f91-2695">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="d7f91-2696">Basic Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="d7f91-2696">Basic Resident Register No.</span></span> 
- <span data-ttu-id="d7f91-2697">住民登録番号、登録番号をレジデント</span><span class="sxs-lookup"><span data-stu-id="d7f91-2697">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="d7f91-2698">住民基本登録番号、登録番号</span><span class="sxs-lookup"><span data-stu-id="d7f91-2698">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="d7f91-2699">住民基本レジストリ番号を常駐</span><span class="sxs-lookup"><span data-stu-id="d7f91-2699">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="d7f91-2700">登録番号を常駐住民基本台帳登録番号</span><span class="sxs-lookup"><span data-stu-id="d7f91-2700">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="d7f91-2701">日本社会保险号码 (SIN)</span><span class="sxs-lookup"><span data-stu-id="d7f91-2701">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-2702">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-2702">Format</span></span>

<span data-ttu-id="d7f91-2703">7-12 个数字 </span><span class="sxs-lookup"><span data-stu-id="d7f91-2703">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-2704">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2704">Pattern</span></span>

<span data-ttu-id="d7f91-2705">7-12 位数字：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2705">7-12 digits:</span></span>
- <span data-ttu-id="d7f91-2706">四位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2706">Four digits</span></span> 
- <span data-ttu-id="d7f91-2707">一个连字符（可选）</span><span class="sxs-lookup"><span data-stu-id="d7f91-2707">A hyphen (optional)</span></span> 
- <span data-ttu-id="d7f91-2708">六位数字或</span><span class="sxs-lookup"><span data-stu-id="d7f91-2708">Six digits OR</span></span>
- <span data-ttu-id="d7f91-2709">7-12 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2709">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-2710">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-2710">Checksum</span></span>

<span data-ttu-id="d7f91-2711">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-2711">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-2712">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-2712">Definition</span></span>

<span data-ttu-id="d7f91-2713">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2713">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2714">函数 Func_jp_sin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2714">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2715">找到 Keyword_jp_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2715">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="d7f91-2716">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2716">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2717">函数 Func_jp_sin_pre_1997 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2717">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2718">找到 Keyword_jp_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2718">A keyword from Keyword_jp_sin is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-2719">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2719">Keywords</span></span>

#### <a name="keyword_jp_sin"></a><span data-ttu-id="d7f91-2720">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="d7f91-2720">Keyword_jp_sin</span></span>

- <span data-ttu-id="d7f91-2721">Social Insurance No.</span><span class="sxs-lookup"><span data-stu-id="d7f91-2721">Social Insurance No.</span></span> 
- <span data-ttu-id="d7f91-2722">Social Insurance Num</span><span class="sxs-lookup"><span data-stu-id="d7f91-2722">Social Insurance Num</span></span> 
- <span data-ttu-id="d7f91-2723">Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2723">Social Insurance Number</span></span> 
- <span data-ttu-id="d7f91-2724">社会保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="d7f91-2724">社会保険のテンキー</span></span> 
- <span data-ttu-id="d7f91-2725">社会保険番号</span><span class="sxs-lookup"><span data-stu-id="d7f91-2725">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="d7f91-2726">日本住宅电话卡号</span><span class="sxs-lookup"><span data-stu-id="d7f91-2726">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-2727">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-2727">Format</span></span>

<span data-ttu-id="d7f91-2728">12个字母和数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2728">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-2729">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2729">Pattern</span></span>

<span data-ttu-id="d7f91-2730">12个字母和数字:</span><span class="sxs-lookup"><span data-stu-id="d7f91-2730">12 letters and digits:</span></span>
- <span data-ttu-id="d7f91-2731">两个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="d7f91-2731">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="d7f91-2732">八个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2732">Eight digits</span></span> 
- <span data-ttu-id="d7f91-2733">两个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="d7f91-2733">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-2734">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-2734">Checksum</span></span>

<span data-ttu-id="d7f91-2735">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-2735">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-2736">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-2736">Definition</span></span>

<span data-ttu-id="d7f91-2737">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2737">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2738">正则表达式 Regex_jp_residence_card_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2738">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2739">找到 Keyword_jp_residence_card_number 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2739">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-2740">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2740">Keywords</span></span>

#### <a name="keyword_jp_residence_card_number"></a><span data-ttu-id="d7f91-2741">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2741">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="d7f91-2742">住宅电话卡号</span><span class="sxs-lookup"><span data-stu-id="d7f91-2742">Residence card number</span></span>
- <span data-ttu-id="d7f91-2743">住宅卡编号</span><span class="sxs-lookup"><span data-stu-id="d7f91-2743">Residence card no</span></span>
- <span data-ttu-id="d7f91-2744">住宅卡片#</span><span class="sxs-lookup"><span data-stu-id="d7f91-2744">Residence card #</span></span>
- <span data-ttu-id="d7f91-2745">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="d7f91-2745">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="d7f91-2746">马拉西亚身份证号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-2746">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-2747">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-2747">Format</span></span>

<span data-ttu-id="d7f91-2748">12 个数字（包含可选连字符）</span><span class="sxs-lookup"><span data-stu-id="d7f91-2748">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-2749">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2749">Pattern</span></span>

<span data-ttu-id="d7f91-2750">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2750">12 digits:</span></span>
- <span data-ttu-id="d7f91-2751">六个数字，采用  YYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="d7f91-2751">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="d7f91-2752">一个短划线（可选） </span><span class="sxs-lookup"><span data-stu-id="d7f91-2752">A dash (optional)</span></span> 
- <span data-ttu-id="d7f91-2753">两个字母的出生地代码 </span><span class="sxs-lookup"><span data-stu-id="d7f91-2753">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="d7f91-2754">一个短划线（可选） </span><span class="sxs-lookup"><span data-stu-id="d7f91-2754">A dash (optional)</span></span> 
- <span data-ttu-id="d7f91-2755">三个随机数字 </span><span class="sxs-lookup"><span data-stu-id="d7f91-2755">Three random digits</span></span> 
- <span data-ttu-id="d7f91-2756">一位性别代码</span><span class="sxs-lookup"><span data-stu-id="d7f91-2756">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-2757">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-2757">Checksum</span></span>

<span data-ttu-id="d7f91-2758">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-2758">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-2759">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-2759">Definition</span></span>

<span data-ttu-id="d7f91-2760">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2760">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2761">正则表达式 Regex_malaysia_id_card_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2761">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2762">找到 Keyword_malaysia_id_card_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2762">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

```xml
<!-- Malaysia ID Card Number -->
</Entity>
      <Entity id="7f0e921c-9677-435b-aba2-bb8f1013c749" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_malaysia_id_card_number" />
            <Match idRef="Keyword_malaysia_id_card_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-2763">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2763">Keywords</span></span>
   
#### <a name="keyword_malaysia_id_card_number"></a><span data-ttu-id="d7f91-2764">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2764">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="d7f91-2765">数字应用程序卡</span><span class="sxs-lookup"><span data-stu-id="d7f91-2765">digital application card</span></span>
- <span data-ttu-id="d7f91-2766">i/c</span><span class="sxs-lookup"><span data-stu-id="d7f91-2766">i/c</span></span>
- <span data-ttu-id="d7f91-2767">i/c 否</span><span class="sxs-lookup"><span data-stu-id="d7f91-2767">i/c no</span></span>
- <span data-ttu-id="d7f91-2768">ic</span><span class="sxs-lookup"><span data-stu-id="d7f91-2768">ic</span></span>
- <span data-ttu-id="d7f91-2769">内部公司编号</span><span class="sxs-lookup"><span data-stu-id="d7f91-2769">ic no</span></span>
- <span data-ttu-id="d7f91-2770">id card</span><span class="sxs-lookup"><span data-stu-id="d7f91-2770">id card</span></span>
- <span data-ttu-id="d7f91-2771">标识卡</span><span class="sxs-lookup"><span data-stu-id="d7f91-2771">identification Card</span></span>
- <span data-ttu-id="d7f91-2772">identity card</span><span class="sxs-lookup"><span data-stu-id="d7f91-2772">identity card</span></span>
- <span data-ttu-id="d7f91-2773">k/p</span><span class="sxs-lookup"><span data-stu-id="d7f91-2773">k/p</span></span>
- <span data-ttu-id="d7f91-2774">k/p no</span><span class="sxs-lookup"><span data-stu-id="d7f91-2774">k/p no</span></span>
- <span data-ttu-id="d7f91-2775">kad akuan diri</span><span class="sxs-lookup"><span data-stu-id="d7f91-2775">kad akuan diri</span></span>
- <span data-ttu-id="d7f91-2776">kad aplikasi 数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2776">kad aplikasi digital</span></span>
- <span data-ttu-id="d7f91-2777">kad pengenalan 马来西亚</span><span class="sxs-lookup"><span data-stu-id="d7f91-2777">kad pengenalan malaysia</span></span>
- <span data-ttu-id="d7f91-2778">kp</span><span class="sxs-lookup"><span data-stu-id="d7f91-2778">kp</span></span>
- <span data-ttu-id="d7f91-2779">kp no</span><span class="sxs-lookup"><span data-stu-id="d7f91-2779">kp no</span></span>
- <span data-ttu-id="d7f91-2780">mykad</span><span class="sxs-lookup"><span data-stu-id="d7f91-2780">mykad</span></span>
- <span data-ttu-id="d7f91-2781">mykas</span><span class="sxs-lookup"><span data-stu-id="d7f91-2781">mykas</span></span>
- <span data-ttu-id="d7f91-2782">mykid</span><span class="sxs-lookup"><span data-stu-id="d7f91-2782">mykid</span></span>
- <span data-ttu-id="d7f91-2783">mypr</span><span class="sxs-lookup"><span data-stu-id="d7f91-2783">mypr</span></span>
- <span data-ttu-id="d7f91-2784">mytentera</span><span class="sxs-lookup"><span data-stu-id="d7f91-2784">mytentera</span></span>
- <span data-ttu-id="d7f91-2785">马来西亚身份卡片</span><span class="sxs-lookup"><span data-stu-id="d7f91-2785">malaysia identity card</span></span>
- <span data-ttu-id="d7f91-2786">马来西亚身份卡片</span><span class="sxs-lookup"><span data-stu-id="d7f91-2786">malaysian identity card</span></span>
- <span data-ttu-id="d7f91-2787">nric</span><span class="sxs-lookup"><span data-stu-id="d7f91-2787">nric</span></span>
- <span data-ttu-id="d7f91-2788">个人标识卡</span><span class="sxs-lookup"><span data-stu-id="d7f91-2788">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="d7f91-2789">荷兰公民服务 (BSN) 号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-2789">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-2790">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-2790">Format</span></span>

<span data-ttu-id="d7f91-2791">8-9 个数字（包含可选空格）</span><span class="sxs-lookup"><span data-stu-id="d7f91-2791">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-2792">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2792">Pattern</span></span>

<span data-ttu-id="d7f91-2793">8-9 个数字：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2793">8-9 digits:</span></span>
- <span data-ttu-id="d7f91-2794">三个数字 </span><span class="sxs-lookup"><span data-stu-id="d7f91-2794">Three digits</span></span> 
- <span data-ttu-id="d7f91-2795">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="d7f91-2795">A space (optional)</span></span> 
- <span data-ttu-id="d7f91-2796">三个数字 </span><span class="sxs-lookup"><span data-stu-id="d7f91-2796">Three digits</span></span> 
- <span data-ttu-id="d7f91-2797">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="d7f91-2797">A space (optional)</span></span> 
- <span data-ttu-id="d7f91-2798">2-3 个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2798">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-2799">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-2799">Checksum</span></span>

<span data-ttu-id="d7f91-2800">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-2800">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-2801">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-2801">Definition</span></span>

<span data-ttu-id="d7f91-2802">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2802">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2803">函数 Func_netherlands_bsn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2803">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2804">找到 Keyword_netherlands_bsn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2804">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="d7f91-2805">函数 Func_eu_date2 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2805">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="d7f91-2806">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2806">The checksum passes.</span></span>

```xml
<!-- Netherlands Citizen's Service (BSN) Number -->
<Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="Func_netherlands_bsn" /> 
       <Match idRef="Keyword_netherlands_bsn" /> 
       <Match idRef="Func_eu_date2" /> 
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-2807">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2807">Keywords</span></span>

#### <a name="keyword_netherlands_bsn"></a><span data-ttu-id="d7f91-2808">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="d7f91-2808">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="d7f91-2809">Citizen service number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2809">Citizen service number</span></span> 
- <span data-ttu-id="d7f91-2810">BSN</span><span class="sxs-lookup"><span data-stu-id="d7f91-2810">BSN</span></span> 
- <span data-ttu-id="d7f91-2811">Burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="d7f91-2811">Burgerservicenummer</span></span> 
- <span data-ttu-id="d7f91-2812">Sofinummer</span><span class="sxs-lookup"><span data-stu-id="d7f91-2812">Sofinummer</span></span> 
- <span data-ttu-id="d7f91-2813">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="d7f91-2813">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="d7f91-2814">Persoonsnummer</span><span class="sxs-lookup"><span data-stu-id="d7f91-2814">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="d7f91-2815">新西兰卫生部号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-2815">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-2816">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-2816">Format</span></span>

<span data-ttu-id="d7f91-2817">三个字母、一个空格（可选）以及四个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2817">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-2818">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2818">Pattern</span></span>

<span data-ttu-id="d7f91-2819">三个字母 (不区分大小写) 一个空格 (可选) 四个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2819">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-2820">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-2820">Checksum</span></span>

<span data-ttu-id="d7f91-2821">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-2821">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-2822">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-2822">Definition</span></span>

<span data-ttu-id="d7f91-2823">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2823">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2824">函数 Func_new_zealand_ministry_of_health_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2824">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2825">找到 Keyword_nz_terms 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2825">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="d7f91-2826">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2826">The checksum passes.</span></span>

```xml
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

<span data-ttu-id="d7f91-2827">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2827">Keywords</span></span>

<span data-ttu-id="d7f91-2828">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="d7f91-2828">Keyword_nz_terms</span></span>

- <span data-ttu-id="d7f91-2829">NHI</span><span class="sxs-lookup"><span data-stu-id="d7f91-2829">NHI</span></span> 
- <span data-ttu-id="d7f91-2830">New Zealand</span><span class="sxs-lookup"><span data-stu-id="d7f91-2830">New Zealand</span></span> 
- <span data-ttu-id="d7f91-2831">运行状况</span><span class="sxs-lookup"><span data-stu-id="d7f91-2831">Health</span></span> 
- <span data-ttu-id="d7f91-2832">治疗</span><span class="sxs-lookup"><span data-stu-id="d7f91-2832">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="d7f91-2833">挪威身份证号</span><span class="sxs-lookup"><span data-stu-id="d7f91-2833">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-2834">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-2834">Format</span></span>

<span data-ttu-id="d7f91-2835">11 个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2835">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-2836">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2836">Pattern</span></span>

<span data-ttu-id="d7f91-2837">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2837">11 digits:</span></span>
- <span data-ttu-id="d7f91-2838">六个数字，采用  DDMMYY 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="d7f91-2838">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="d7f91-2839">三位个人号码 </span><span class="sxs-lookup"><span data-stu-id="d7f91-2839">Three-digit individual number</span></span> 
- <span data-ttu-id="d7f91-2840">两个校验位</span><span class="sxs-lookup"><span data-stu-id="d7f91-2840">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-2841">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-2841">Checksum</span></span>

<span data-ttu-id="d7f91-2842">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-2842">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-2843">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-2843">Definition</span></span>

<span data-ttu-id="d7f91-2844">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2844">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2845">函数 Func_norway_id_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2845">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2846">找到 Keyword_norway_id_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2846">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="d7f91-2847">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2847">The checksum passes.</span></span>
- <span data-ttu-id="d7f91-2848">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2848">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2849">函数 Func_norway_id_numbe 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2849">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2850">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2850">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-2851">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2851">Keywords</span></span>

#### <a name="keyword_norway_id_number"></a><span data-ttu-id="d7f91-2852">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2852">Keyword_norway_id_number</span></span>

- <span data-ttu-id="d7f91-2853">Personal identification number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2853">Personal identification number</span></span>
- <span data-ttu-id="d7f91-2854">Norwegian ID Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2854">Norwegian ID Number</span></span>
- <span data-ttu-id="d7f91-2855">ID Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2855">ID Number</span></span>
- <span data-ttu-id="d7f91-2856">Id</span><span class="sxs-lookup"><span data-stu-id="d7f91-2856">Identification</span></span>
- <span data-ttu-id="d7f91-2857">Personnummer</span><span class="sxs-lookup"><span data-stu-id="d7f91-2857">Personnummer</span></span>
- <span data-ttu-id="d7f91-2858">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="d7f91-2858">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="d7f91-2859">菲律宾统一多用途身份证号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-2859">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-2860">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-2860">Format</span></span>

<span data-ttu-id="d7f91-2861">12 个数字，通过连字符分隔 </span><span class="sxs-lookup"><span data-stu-id="d7f91-2861">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-2862">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2862">Pattern</span></span>

<span data-ttu-id="d7f91-2863">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2863">12 digits:</span></span>
- <span data-ttu-id="d7f91-2864">四个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2864">Four digits</span></span> 
- <span data-ttu-id="d7f91-2865">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="d7f91-2865">A hyphen</span></span> 
- <span data-ttu-id="d7f91-2866">七个数字 </span><span class="sxs-lookup"><span data-stu-id="d7f91-2866">Seven digits</span></span> 
- <span data-ttu-id="d7f91-2867">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="d7f91-2867">A hyphen</span></span> 
- <span data-ttu-id="d7f91-2868">一个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2868">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-2869">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-2869">Checksum</span></span>

<span data-ttu-id="d7f91-2870">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-2870">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-2871">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-2871">Definition</span></span>

<span data-ttu-id="d7f91-2872">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2872">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2873">正则表达式 Regex_philippines_unified_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2873">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2874">找到 Keyword_philippines_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2874">A keyword from Keyword_philippines_id is found.</span></span>

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-2875">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2875">Keywords</span></span>
   
#### <a name="keyword_philippines_id"></a><span data-ttu-id="d7f91-2876">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="d7f91-2876">Keyword_philippines_id</span></span>

- <span data-ttu-id="d7f91-2877">Unified Multi-Purpose ID</span><span class="sxs-lookup"><span data-stu-id="d7f91-2877">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="d7f91-2878">UMID</span><span class="sxs-lookup"><span data-stu-id="d7f91-2878">UMID</span></span> 
- <span data-ttu-id="d7f91-2879">Identity Card</span><span class="sxs-lookup"><span data-stu-id="d7f91-2879">Identity Card</span></span> 
- <span data-ttu-id="d7f91-2880">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="d7f91-2880">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="d7f91-2881">波兰身份证</span><span class="sxs-lookup"><span data-stu-id="d7f91-2881">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-2882">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-2882">Format</span></span>

<span data-ttu-id="d7f91-2883">三个字母和六个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2883">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-2884">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2884">Pattern</span></span>

<span data-ttu-id="d7f91-2885">三个字母（不区分大小写）后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2885">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-2886">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-2886">Checksum</span></span>

<span data-ttu-id="d7f91-2887">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-2887">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-2888">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-2888">Definition</span></span>

<span data-ttu-id="d7f91-2889">DLP 策略 75% 确信在300个字符的邻近度内检测到此类型的敏感信息: 函数 Func_polish_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2889">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="d7f91-2890">找到 Keyword_polish_national_id_passport_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2890">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="d7f91-2891">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2891">The checksum passes.</span></span>

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-2892">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2892">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="d7f91-2893">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2893">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="d7f91-2894">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="d7f91-2894">Dowód osobisty</span></span>
- <span data-ttu-id="d7f91-2895">器 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="d7f91-2895">Numer dowodu osobistego</span></span>
- <span data-ttu-id="d7f91-2896">Nazwa i 器 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="d7f91-2896">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="d7f91-2897">Nazwa i nr dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="d7f91-2897">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="d7f91-2898">Nazwa i nr dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="d7f91-2898">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="d7f91-2899">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="d7f91-2899">Dowód Tożsamości</span></span>
- <span data-ttu-id="d7f91-2900">dow.</span><span class="sxs-lookup"><span data-stu-id="d7f91-2900">dow.</span></span> <span data-ttu-id="d7f91-2901">os.</span><span class="sxs-lookup"><span data-stu-id="d7f91-2901">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="d7f91-2902">波兰国家/地区 ID (PESEL)</span><span class="sxs-lookup"><span data-stu-id="d7f91-2902">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-2903">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-2903">Format</span></span>

<span data-ttu-id="d7f91-2904">11 个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2904">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-2905">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2905">Pattern</span></span>

<span data-ttu-id="d7f91-2906">11 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2906">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-2907">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-2907">Checksum</span></span>

<span data-ttu-id="d7f91-2908">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-2908">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-2909">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-2909">Definition</span></span>

<span data-ttu-id="d7f91-2910">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2910">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2911">函数 Func_pesel_identification_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2911">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2912">找到 Keyword_pesel_identification_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2912">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="d7f91-2913">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2913">The checksum passes.</span></span>

```xml
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-2914">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2914">Keywords</span></span>

#### <a name="keyword_pesel_identification_number"></a><span data-ttu-id="d7f91-2915">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2915">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="d7f91-2916">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="d7f91-2916">Nr PESEL</span></span>
- <span data-ttu-id="d7f91-2917">PESEL</span><span class="sxs-lookup"><span data-stu-id="d7f91-2917">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="d7f91-2918">波兰护照</span><span class="sxs-lookup"><span data-stu-id="d7f91-2918">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-2919">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-2919">Format</span></span>

<span data-ttu-id="d7f91-2920">两个字母和七个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2920">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-2921">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2921">Pattern</span></span>

<span data-ttu-id="d7f91-2922">两个字母（不区分大小写）后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2922">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-2923">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-2923">Checksum</span></span>

<span data-ttu-id="d7f91-2924">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-2924">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-2925">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-2925">Definition</span></span>

<span data-ttu-id="d7f91-2926">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2926">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2927">函数 Func_polish_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2927">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2928">找到 Keyword_polish_national_id_passport_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2928">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="d7f91-2929">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2929">The checksum passes.</span></span>

```xml
<!-- Poland Passport Number -->
<Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
</Version>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-2930">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2930">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="d7f91-2931">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2931">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="d7f91-2932">器 paszportu</span><span class="sxs-lookup"><span data-stu-id="d7f91-2932">Numer paszportu</span></span>
- <span data-ttu-id="d7f91-2933">Führerschein-nr.</span><span class="sxs-lookup"><span data-stu-id="d7f91-2933">Nr.</span></span> <span data-ttu-id="d7f91-2934">Paszportu</span><span class="sxs-lookup"><span data-stu-id="d7f91-2934">Paszportu</span></span>
- <span data-ttu-id="d7f91-2935">Paszport</span><span class="sxs-lookup"><span data-stu-id="d7f91-2935">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="d7f91-2936">葡萄牙公民身份证号</span><span class="sxs-lookup"><span data-stu-id="d7f91-2936">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-2937">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-2937">Format</span></span>

<span data-ttu-id="d7f91-2938">八个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2938">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-2939">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2939">Pattern</span></span>

<span data-ttu-id="d7f91-2940">八个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2940">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-2941">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-2941">Checksum</span></span>

<span data-ttu-id="d7f91-2942">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-2942">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-2943">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-2943">Definition</span></span>

<span data-ttu-id="d7f91-2944">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2944">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2945">正则表达式 Regex_portugal_citizen_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2945">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2946">找到 Keyword_portugal_citizen_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2946">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-2947">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2947">Keywords</span></span>

#### <a name="keyword_portugal_citizen_card"></a><span data-ttu-id="d7f91-2948">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="d7f91-2948">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="d7f91-2949">Citizen Card</span><span class="sxs-lookup"><span data-stu-id="d7f91-2949">Citizen Card</span></span>
- <span data-ttu-id="d7f91-2950">National ID Card</span><span class="sxs-lookup"><span data-stu-id="d7f91-2950">National ID Card</span></span>
- <span data-ttu-id="d7f91-2951">CC</span><span class="sxs-lookup"><span data-stu-id="d7f91-2951">CC</span></span>
- <span data-ttu-id="d7f91-2952">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="d7f91-2952">Cartão de Cidadão</span></span>
- <span data-ttu-id="d7f91-2953">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="d7f91-2953">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="d7f91-2954">沙特阿拉伯国家 ID</span><span class="sxs-lookup"><span data-stu-id="d7f91-2954">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-2955">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-2955">Format</span></span>

<span data-ttu-id="d7f91-2956">10 个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2956">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-2957">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2957">Pattern</span></span>

<span data-ttu-id="d7f91-2958">10 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2958">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-2959">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-2959">Checksum</span></span>

<span data-ttu-id="d7f91-2960">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-2960">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-2961">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-2961">Definition</span></span>

<span data-ttu-id="d7f91-2962">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2962">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2963">正则表达式 Regex_saudi_arabia_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2963">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2964">找到 Keyword_saudi_arabia_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2964">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-2965">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2965">Keywords</span></span>

#### <a name="keyword_saudi_arabia_national_id"></a><span data-ttu-id="d7f91-2966">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="d7f91-2966">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="d7f91-2967">Identification Card</span><span class="sxs-lookup"><span data-stu-id="d7f91-2967">Identification Card</span></span> 
- <span data-ttu-id="d7f91-2968">I card number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2968">I card number</span></span> 
- <span data-ttu-id="d7f91-2969">ID number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2969">ID number</span></span> 
- <span data-ttu-id="d7f91-2970">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="d7f91-2970">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="d7f91-2971">新加坡国家登记身份证 (NRIC) 号</span><span class="sxs-lookup"><span data-stu-id="d7f91-2971">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-2972">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-2972">Format</span></span>

<span data-ttu-id="d7f91-2973">九个字母和数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2973">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-2974">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-2974">Pattern</span></span>

- <span data-ttu-id="d7f91-2975">九个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2975">Nine letters and digits:</span></span>
- <span data-ttu-id="d7f91-2976">字母“F”、“G”、“S”或“T”（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="d7f91-2976">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="d7f91-2977">七个数字 </span><span class="sxs-lookup"><span data-stu-id="d7f91-2977">Seven digits</span></span> 
- <span data-ttu-id="d7f91-2978">一个字母校验位</span><span class="sxs-lookup"><span data-stu-id="d7f91-2978">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-2979">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-2979">Checksum</span></span>

<span data-ttu-id="d7f91-2980">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-2980">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-2981">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-2981">Definition</span></span>

<span data-ttu-id="d7f91-2982">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2982">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2983">正则表达式 Regex_singapore_nric 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2983">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2984">找到 Keyword_singapore_nric 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2984">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="d7f91-2985">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2985">The checksum passes.</span></span>

<span data-ttu-id="d7f91-2986">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-2986">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-2987">正则表达式 Regex_singapore_nric 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2987">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-2988">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-2988">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-2989">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-2989">Keywords</span></span>
   
#### <a name="keyword_singapore_nric"></a><span data-ttu-id="d7f91-2990">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="d7f91-2990">Keyword_singapore_nric</span></span>

- <span data-ttu-id="d7f91-2991">National Registration Identity Card</span><span class="sxs-lookup"><span data-stu-id="d7f91-2991">National Registration Identity Card</span></span> 
- <span data-ttu-id="d7f91-2992">Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2992">Identity Card Number</span></span> 
- <span data-ttu-id="d7f91-2993">NRIC</span><span class="sxs-lookup"><span data-stu-id="d7f91-2993">NRIC</span></span> 
- <span data-ttu-id="d7f91-2994">IC</span><span class="sxs-lookup"><span data-stu-id="d7f91-2994">IC</span></span> 
- <span data-ttu-id="d7f91-2995">Foreign Identification Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-2995">Foreign Identification Number</span></span> 
- <span data-ttu-id="d7f91-2996">FIN</span><span class="sxs-lookup"><span data-stu-id="d7f91-2996">FIN</span></span> 
- <span data-ttu-id="d7f91-2997">身份证</span><span class="sxs-lookup"><span data-stu-id="d7f91-2997">身份证</span></span> 
- <span data-ttu-id="d7f91-2998">證</span><span class="sxs-lookup"><span data-stu-id="d7f91-2998">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="d7f91-2999">南非身份证号</span><span class="sxs-lookup"><span data-stu-id="d7f91-2999">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-3000">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-3000">Format</span></span>

<span data-ttu-id="d7f91-3001">13 个数字（可能包含空格）</span><span class="sxs-lookup"><span data-stu-id="d7f91-3001">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-3002">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-3002">Pattern</span></span>

<span data-ttu-id="d7f91-3003">13 个数字：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3003">13 digits:</span></span>
- <span data-ttu-id="d7f91-3004">六个数字，采用  YYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="d7f91-3004">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="d7f91-3005">四个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3005">Four digits</span></span> 
- <span data-ttu-id="d7f91-3006">一位公民指示码 </span><span class="sxs-lookup"><span data-stu-id="d7f91-3006">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="d7f91-3007">数字“8”或“9” </span><span class="sxs-lookup"><span data-stu-id="d7f91-3007">The digit "8" or "9"</span></span> 
- <span data-ttu-id="d7f91-3008">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="d7f91-3008">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-3009">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-3009">Checksum</span></span>

<span data-ttu-id="d7f91-3010">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-3010">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-3011">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-3011">Definition</span></span>

<span data-ttu-id="d7f91-3012">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3012">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-3013">函数 Func_south_africa_identification_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3013">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3014">找到 Keyword_south_africa_identification_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3014">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="d7f91-3015">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3015">The checksum passes.</span></span>

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-3016">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3016">Keywords</span></span>
   
#### <a name="keyword_south_africa_identification_number"></a><span data-ttu-id="d7f91-3017">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="d7f91-3017">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="d7f91-3018">Identity card</span><span class="sxs-lookup"><span data-stu-id="d7f91-3018">Identity card</span></span>
- <span data-ttu-id="d7f91-3019">ID</span><span class="sxs-lookup"><span data-stu-id="d7f91-3019">ID</span></span>
- <span data-ttu-id="d7f91-3020">Id</span><span class="sxs-lookup"><span data-stu-id="d7f91-3020">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="d7f91-3021">韩国居民注册号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-3021">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-3022">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-3022">Format</span></span>

<span data-ttu-id="d7f91-3023">13 个数字（包含连字符）</span><span class="sxs-lookup"><span data-stu-id="d7f91-3023">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-3024">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-3024">Pattern</span></span>

<span data-ttu-id="d7f91-3025">13 个数字：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3025">13 digits:</span></span>
- <span data-ttu-id="d7f91-3026">六个数字，采用  YYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="d7f91-3026">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="d7f91-3027">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="d7f91-3027">A hyphen</span></span> 
- <span data-ttu-id="d7f91-3028">一个数字，由世纪和性别 </span><span class="sxs-lookup"><span data-stu-id="d7f91-3028">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="d7f91-3029">四位数字的出生地区代码 </span><span class="sxs-lookup"><span data-stu-id="d7f91-3029">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="d7f91-3030">一个数字，用于区分前面数字均相同的人 </span><span class="sxs-lookup"><span data-stu-id="d7f91-3030">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="d7f91-3031">一个校验位。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3031">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-3032">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-3032">Checksum</span></span>

<span data-ttu-id="d7f91-3033">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-3033">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-3034">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-3034">Definition</span></span>

<span data-ttu-id="d7f91-3035">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3035">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-3036">函数 Func_south_korea_resident_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3036">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3037">找到 Keyword_south_korea_resident_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3037">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="d7f91-3038">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3038">The checksum passes.</span></span>

<span data-ttu-id="d7f91-3039">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3039">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-3040">函数 Func_south_korea_resident_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3040">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3041">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3041">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-3042">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3042">Keywords</span></span>
   
#### <a name="keyword_south_korea_resident_number"></a><span data-ttu-id="d7f91-3043">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="d7f91-3043">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="d7f91-3044">National ID card</span><span class="sxs-lookup"><span data-stu-id="d7f91-3044">National ID card</span></span> 
- <span data-ttu-id="d7f91-3045">Citizen's Registration Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-3045">Citizen's Registration Number</span></span> 
- <span data-ttu-id="d7f91-3046">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="d7f91-3046">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="d7f91-3047">RRN</span><span class="sxs-lookup"><span data-stu-id="d7f91-3047">RRN</span></span> 
- <span data-ttu-id="d7f91-3048">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="d7f91-3048">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="d7f91-3049">西班牙社会保险号码 (SSN)</span><span class="sxs-lookup"><span data-stu-id="d7f91-3049">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-3050">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-3050">Format</span></span>

<span data-ttu-id="d7f91-3051">11-12 个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3051">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-3052">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-3052">Pattern</span></span>

<span data-ttu-id="d7f91-3053">11-12 位数:</span><span class="sxs-lookup"><span data-stu-id="d7f91-3053">11-12 digits:</span></span>
- <span data-ttu-id="d7f91-3054">两位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3054">Two digits</span></span> 
- <span data-ttu-id="d7f91-3055">正斜杠（可选）</span><span class="sxs-lookup"><span data-stu-id="d7f91-3055">A forward slash (optional)</span></span> 
- <span data-ttu-id="d7f91-3056">7-8 位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3056">7-8 digits</span></span> 
- <span data-ttu-id="d7f91-3057">正斜杠（可选）</span><span class="sxs-lookup"><span data-stu-id="d7f91-3057">A forward slash (optional)</span></span> 
- <span data-ttu-id="d7f91-3058">两位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3058">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-3059">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-3059">Checksum</span></span>

<span data-ttu-id="d7f91-3060">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-3060">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-3061">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-3061">Definition</span></span>

<span data-ttu-id="d7f91-3062">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3062">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-3063">函数 Func_spanish_social_security_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3063">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3064">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3064">The checksum passes.</span></span>

```xml
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-3065">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3065">Keywords</span></span>

<span data-ttu-id="d7f91-3066">无</span><span class="sxs-lookup"><span data-stu-id="d7f91-3066">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="d7f91-3067">SQL Server 连接字符串</span><span class="sxs-lookup"><span data-stu-id="d7f91-3067">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-3068">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-3068">Format</span></span>

<span data-ttu-id="d7f91-3069">字符串 "User Id"、"User ID"、"uid" 或 "UserId", 后跟下面模式中所述的字符和字符串。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3069">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-3070">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-3070">Pattern</span></span>

- <span data-ttu-id="d7f91-3071">字符串 "User Id"、"User ID"、"uid" 或 "UserId"</span><span class="sxs-lookup"><span data-stu-id="d7f91-3071">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="d7f91-3072">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="d7f91-3072">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="d7f91-3073">字符串 "Password" 或 "pwd", 其中 "pwd" 不以小写字母开头</span><span class="sxs-lookup"><span data-stu-id="d7f91-3073">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="d7f91-3074">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="d7f91-3074">An equal sign (=)</span></span>
- <span data-ttu-id="d7f91-3075">任何不是美元符号 ($)、百分比符号 (%)、大于号 (>)、符号 (@)、引号 (")、分号 (;)、左大括号 ([) 或左中括号 ({) 的字符</span><span class="sxs-lookup"><span data-stu-id="d7f91-3075">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="d7f91-3076">7-128 个字符的任意组合, 不是分号 (;)、正斜杠 (/) 或引号 (")</span><span class="sxs-lookup"><span data-stu-id="d7f91-3076">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="d7f91-3077">一个分号 (;)或引号 (")</span><span class="sxs-lookup"><span data-stu-id="d7f91-3077">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-3078">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-3078">Checksum</span></span>

<span data-ttu-id="d7f91-3079">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-3079">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-3080">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-3080">Definition</span></span>

<span data-ttu-id="d7f91-3081">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3081">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-3082">正则表达式 CEP_Regex_SQLServerConnectionString 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3082">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3083">找**不**到 CEP_GlobalFilter 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3083">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="d7f91-3084">正则表达式 CEP_PasswordPlaceHolder**未**找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3084">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3085">正则表达式 CEP_CommonExampleKeywords**未**找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3085">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```sql
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

### <a name="keywords"></a><span data-ttu-id="d7f91-3086">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3086">Keywords</span></span>

#### <a name="cep_globalfilter"></a><span data-ttu-id="d7f91-3087">CEP_GlobalFilter</span><span class="sxs-lookup"><span data-stu-id="d7f91-3087">CEP_GlobalFilter</span></span>

- <span data-ttu-id="d7f91-3088">部分密码</span><span class="sxs-lookup"><span data-stu-id="d7f91-3088">some-password</span></span>
- <span data-ttu-id="d7f91-3089">somepassword</span><span class="sxs-lookup"><span data-stu-id="d7f91-3089">somepassword</span></span>
- <span data-ttu-id="d7f91-3090">secretPassword</span><span class="sxs-lookup"><span data-stu-id="d7f91-3090">secretPassword</span></span>
- <span data-ttu-id="d7f91-3091">采用</span><span class="sxs-lookup"><span data-stu-id="d7f91-3091">sample</span></span>

#### <a name="cep_passwordplaceholder"></a><span data-ttu-id="d7f91-3092">CEP_PasswordPlaceHolder</span><span class="sxs-lookup"><span data-stu-id="d7f91-3092">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="d7f91-3093">(请注意, 从技术上讲, 此敏感信息类型通过使用正则表达式 (而不是关键字列表) 来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3093">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="d7f91-3094">密码或密码后跟0-2 个空格、一个等号 (=)、0-2 个空格和一个星号 (\*)--或--</span><span class="sxs-lookup"><span data-stu-id="d7f91-3094">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="d7f91-3095">密码或密码后跟:</span><span class="sxs-lookup"><span data-stu-id="d7f91-3095">Password or pwd followed by:</span></span>
    - <span data-ttu-id="d7f91-3096">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="d7f91-3096">Equal sign (=)</span></span>
    - <span data-ttu-id="d7f91-3097">小于号 (<)</span><span class="sxs-lookup"><span data-stu-id="d7f91-3097">Less than symbol (<)</span></span>
    - <span data-ttu-id="d7f91-3098">1-200 个字符的任意组合, 这些字符为大写或小写字母、数字、星号 (\*)、连字符 (-)、下划线 (_) 或空白字符</span><span class="sxs-lookup"><span data-stu-id="d7f91-3098">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="d7f91-3099">大于号 (>)</span><span class="sxs-lookup"><span data-stu-id="d7f91-3099">Greater than symbol (>)</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="d7f91-3100">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="d7f91-3100">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="d7f91-3101">(请注意, 从技术上讲, 此敏感信息类型通过使用正则表达式 (而不是关键字列表) 来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3101">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="d7f91-3102">尚未</span><span class="sxs-lookup"><span data-stu-id="d7f91-3102">contoso</span></span>
- <span data-ttu-id="d7f91-3103">送交</span><span class="sxs-lookup"><span data-stu-id="d7f91-3103">fabrikam</span></span>
- <span data-ttu-id="d7f91-3104">罗斯</span><span class="sxs-lookup"><span data-stu-id="d7f91-3104">northwind</span></span>
- <span data-ttu-id="d7f91-3105">沙盒</span><span class="sxs-lookup"><span data-stu-id="d7f91-3105">sandbox</span></span>
- <span data-ttu-id="d7f91-3106">onebox</span><span class="sxs-lookup"><span data-stu-id="d7f91-3106">onebox</span></span>
- <span data-ttu-id="d7f91-3107">localhost</span><span class="sxs-lookup"><span data-stu-id="d7f91-3107">localhost</span></span>
- <span data-ttu-id="d7f91-3108">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="d7f91-3108">127.0.0.1</span></span>
- <span data-ttu-id="d7f91-3109">testacs.</span><span class="sxs-lookup"><span data-stu-id="d7f91-3109">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="d7f91-3110">com</span><span class="sxs-lookup"><span data-stu-id="d7f91-3110">com</span></span>
- <span data-ttu-id="d7f91-3111">s-int。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3111">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="d7f91-3112">netmeeting</span><span class="sxs-lookup"><span data-stu-id="d7f91-3112">net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="d7f91-3113">瑞典国家 ID</span><span class="sxs-lookup"><span data-stu-id="d7f91-3113">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-3114">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-3114">Format</span></span>

<span data-ttu-id="d7f91-3115">10 个或 12 个数字和一个可选分隔符</span><span class="sxs-lookup"><span data-stu-id="d7f91-3115">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-3116">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-3116">Pattern</span></span>

<span data-ttu-id="d7f91-3117">10 或 12 位数字和可选的分隔符：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3117">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="d7f91-3118">2-4 位数字（可选）</span><span class="sxs-lookup"><span data-stu-id="d7f91-3118">2-4 digits (optional)</span></span> 
- <span data-ttu-id="d7f91-3119">采用日期格式 YYMMDD 的六位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3119">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="d7f91-3120">“-”或“+”（可选）的分隔符，加</span><span class="sxs-lookup"><span data-stu-id="d7f91-3120">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="d7f91-3121">四个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3121">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-3122">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-3122">Checksum</span></span>

<span data-ttu-id="d7f91-3123">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-3123">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-3124">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-3124">Definition</span></span>

<span data-ttu-id="d7f91-3125">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3125">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-3126">函数 Func_swedish_national_identifier 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3126">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3127">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3127">The checksum passes.</span></span>

```xml
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-3128">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3128">Keywords</span></span>

<span data-ttu-id="d7f91-3129">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-3129">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="d7f91-3130">瑞典护照号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-3130">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-3131">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-3131">Format</span></span>

<span data-ttu-id="d7f91-3132">八个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3132">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-3133">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-3133">Pattern</span></span>

<span data-ttu-id="d7f91-3134">八个连续的数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3134">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-3135">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-3135">Checksum</span></span>

<span data-ttu-id="d7f91-3136">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-3136">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-3137">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-3137">Definition</span></span>

<span data-ttu-id="d7f91-3138">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3138">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-3139">正则表达式 Regex_sweden_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3139">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3140">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3140">One of the following is true:</span></span>
    - <span data-ttu-id="d7f91-3141">找到 Keyword_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3141">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="d7f91-3142">找到 Keyword_sweden_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3142">A keyword from Keyword_sweden_passport is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-3143">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3143">Keywords</span></span>
   
#### <a name="keyword_sweden_passport"></a><span data-ttu-id="d7f91-3144">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="d7f91-3144">Keyword_sweden_passport</span></span>

- <span data-ttu-id="d7f91-3145">visa requirements</span><span class="sxs-lookup"><span data-stu-id="d7f91-3145">visa requirements</span></span> 
- <span data-ttu-id="d7f91-3146">Alien Registration Card</span><span class="sxs-lookup"><span data-stu-id="d7f91-3146">Alien Registration Card</span></span> 
- <span data-ttu-id="d7f91-3147">Schengen visas</span><span class="sxs-lookup"><span data-stu-id="d7f91-3147">Schengen visas</span></span> 
- <span data-ttu-id="d7f91-3148">Schengen visa</span><span class="sxs-lookup"><span data-stu-id="d7f91-3148">Schengen visa</span></span> 
- <span data-ttu-id="d7f91-3149">Visa Processing</span><span class="sxs-lookup"><span data-stu-id="d7f91-3149">Visa Processing</span></span> 
- <span data-ttu-id="d7f91-3150">Visa Type</span><span class="sxs-lookup"><span data-stu-id="d7f91-3150">Visa Type</span></span> 
- <span data-ttu-id="d7f91-3151">Single Entry</span><span class="sxs-lookup"><span data-stu-id="d7f91-3151">Single Entry</span></span> 
- <span data-ttu-id="d7f91-3152">Multiple Entry</span><span class="sxs-lookup"><span data-stu-id="d7f91-3152">Multiple Entry</span></span> 
- <span data-ttu-id="d7f91-3153">G3 Processing Fees</span><span class="sxs-lookup"><span data-stu-id="d7f91-3153">G3 Processing Fees</span></span> 

#### <a name="keyword_passport"></a><span data-ttu-id="d7f91-3154">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="d7f91-3154">Keyword_passport</span></span>

- <span data-ttu-id="d7f91-3155">Passport Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-3155">Passport Number</span></span> 
- <span data-ttu-id="d7f91-3156">Passport No</span><span class="sxs-lookup"><span data-stu-id="d7f91-3156">Passport No</span></span> 
- <span data-ttu-id="d7f91-3157">Passport #</span><span class="sxs-lookup"><span data-stu-id="d7f91-3157">Passport #</span></span> 
- <span data-ttu-id="d7f91-3158">登记卡#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3158">Passport#</span></span> 
- <span data-ttu-id="d7f91-3159">PassportID</span><span class="sxs-lookup"><span data-stu-id="d7f91-3159">PassportID</span></span> 
- <span data-ttu-id="d7f91-3160">Passportno</span><span class="sxs-lookup"><span data-stu-id="d7f91-3160">Passportno</span></span> 
- <span data-ttu-id="d7f91-3161">passportnumber</span><span class="sxs-lookup"><span data-stu-id="d7f91-3161">passportnumber</span></span> 
- <span data-ttu-id="d7f91-3162">パスポート</span><span class="sxs-lookup"><span data-stu-id="d7f91-3162">パスポート</span></span> 
- <span data-ttu-id="d7f91-3163">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="d7f91-3163">パスポート番号</span></span> 
- <span data-ttu-id="d7f91-3164">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="d7f91-3164">パスポートのNum</span></span> 
- <span data-ttu-id="d7f91-3165">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="d7f91-3165">パスポート＃</span></span> 
- <span data-ttu-id="d7f91-3166">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="d7f91-3166">Numéro de passeport</span></span> 
- <span data-ttu-id="d7f91-3167">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="d7f91-3167">Passeport n °</span></span> 
- <span data-ttu-id="d7f91-3168">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="d7f91-3168">Passeport Non</span></span> 
- <span data-ttu-id="d7f91-3169">Passeport #</span><span class="sxs-lookup"><span data-stu-id="d7f91-3169">Passeport #</span></span> 
- <span data-ttu-id="d7f91-3170">Passeport#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3170">Passeport#</span></span> 
- <span data-ttu-id="d7f91-3171">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="d7f91-3171">PasseportNon</span></span> 
- <span data-ttu-id="d7f91-3172">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="d7f91-3172">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="d7f91-3173">SWIFT 代码</span><span class="sxs-lookup"><span data-stu-id="d7f91-3173">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-3174">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-3174">Format</span></span>

<span data-ttu-id="d7f91-3175">四个字母后跟 5-31 个字母或数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3175">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-3176">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-3176">Pattern</span></span>

<span data-ttu-id="d7f91-3177">四个字母后跟 5-31 个字母或数字：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3177">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="d7f91-3178">四个字母的银行代码（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="d7f91-3178">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="d7f91-3179">可选空格</span><span class="sxs-lookup"><span data-stu-id="d7f91-3179">An optional space</span></span> 
- <span data-ttu-id="d7f91-3180">4-28 个字母或数字（基本银行账号 (BBAN)）</span><span class="sxs-lookup"><span data-stu-id="d7f91-3180">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="d7f91-3181">可选空格</span><span class="sxs-lookup"><span data-stu-id="d7f91-3181">An optional space</span></span> 
- <span data-ttu-id="d7f91-3182">1-3 个字母或数字（BBAN 的剩余内容）</span><span class="sxs-lookup"><span data-stu-id="d7f91-3182">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-3183">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-3183">Checksum</span></span>

<span data-ttu-id="d7f91-3184">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-3184">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-3185">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-3185">Definition</span></span>

<span data-ttu-id="d7f91-3186">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3186">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-3187">正则表达式 Regex_swift 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3187">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3188">找到 Keyword_swift 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3188">A keyword from Keyword_swift is found.</span></span>

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-3189">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3189">Keywords</span></span>
   
#### <a name="keyword_swift"></a><span data-ttu-id="d7f91-3190">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="d7f91-3190">Keyword_swift</span></span>

- <span data-ttu-id="d7f91-3191">international organization for standardization 9362</span><span class="sxs-lookup"><span data-stu-id="d7f91-3191">international organization for standardization 9362</span></span> 
- <span data-ttu-id="d7f91-3192">iso 9362</span><span class="sxs-lookup"><span data-stu-id="d7f91-3192">iso 9362</span></span> 
- <span data-ttu-id="d7f91-3193">iso9362</span><span class="sxs-lookup"><span data-stu-id="d7f91-3193">iso9362</span></span> 
- <span data-ttu-id="d7f91-3194">反应\#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3194">swift\#</span></span> 
- <span data-ttu-id="d7f91-3195">swiftcode</span><span class="sxs-lookup"><span data-stu-id="d7f91-3195">swiftcode</span></span> 
- <span data-ttu-id="d7f91-3196">swiftnumber</span><span class="sxs-lookup"><span data-stu-id="d7f91-3196">swiftnumber</span></span> 
- <span data-ttu-id="d7f91-3197">swiftroutingnumber</span><span class="sxs-lookup"><span data-stu-id="d7f91-3197">swiftroutingnumber</span></span> 
- <span data-ttu-id="d7f91-3198">swift code</span><span class="sxs-lookup"><span data-stu-id="d7f91-3198">swift code</span></span> 
- <span data-ttu-id="d7f91-3199">swift number #</span><span class="sxs-lookup"><span data-stu-id="d7f91-3199">swift number #</span></span> 
- <span data-ttu-id="d7f91-3200">swift routing number</span><span class="sxs-lookup"><span data-stu-id="d7f91-3200">swift routing number</span></span> 
- <span data-ttu-id="d7f91-3201">bic number</span><span class="sxs-lookup"><span data-stu-id="d7f91-3201">bic number</span></span> 
- <span data-ttu-id="d7f91-3202">bic code</span><span class="sxs-lookup"><span data-stu-id="d7f91-3202">bic code</span></span> 
- <span data-ttu-id="d7f91-3203">numéro\#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3203">bic \#</span></span> 
- <span data-ttu-id="d7f91-3204">numéro\#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3204">bic\#</span></span> 
- <span data-ttu-id="d7f91-3205">bank identifier code</span><span class="sxs-lookup"><span data-stu-id="d7f91-3205">bank identifier code</span></span> 
- <span data-ttu-id="d7f91-3206">標準化9362</span><span class="sxs-lookup"><span data-stu-id="d7f91-3206">標準化9362</span></span> 
- <span data-ttu-id="d7f91-3207">迅速＃</span><span class="sxs-lookup"><span data-stu-id="d7f91-3207">迅速＃</span></span> 
- <span data-ttu-id="d7f91-3208">SWIFTコード</span><span class="sxs-lookup"><span data-stu-id="d7f91-3208">SWIFTコード</span></span> 
- <span data-ttu-id="d7f91-3209">SWIFT番号</span><span class="sxs-lookup"><span data-stu-id="d7f91-3209">SWIFT番号</span></span> 
- <span data-ttu-id="d7f91-3210">迅速なルーティング番号</span><span class="sxs-lookup"><span data-stu-id="d7f91-3210">迅速なルーティング番号</span></span> 
- <span data-ttu-id="d7f91-3211">BIC番号</span><span class="sxs-lookup"><span data-stu-id="d7f91-3211">BIC番号</span></span> 
- <span data-ttu-id="d7f91-3212">BICコード</span><span class="sxs-lookup"><span data-stu-id="d7f91-3212">BICコード</span></span> 
- <span data-ttu-id="d7f91-3213">銀行識別コードのための国際組織</span><span class="sxs-lookup"><span data-stu-id="d7f91-3213">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="d7f91-3214">Organisation internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="d7f91-3214">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="d7f91-3215">rapide\#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3215">rapide \#</span></span> 
- <span data-ttu-id="d7f91-3216">code SWIFT</span><span class="sxs-lookup"><span data-stu-id="d7f91-3216">code SWIFT</span></span> 
- <span data-ttu-id="d7f91-3217">le numéro de swift</span><span class="sxs-lookup"><span data-stu-id="d7f91-3217">le numéro de swift</span></span> 
- <span data-ttu-id="d7f91-3218">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="d7f91-3218">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="d7f91-3219">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="d7f91-3219">le numéro BIC</span></span> 
- <span data-ttu-id="d7f91-3220">\#NUMÉRO</span><span class="sxs-lookup"><span data-stu-id="d7f91-3220">\# BIC</span></span> 
- <span data-ttu-id="d7f91-3221">code identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="d7f91-3221">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="d7f91-3222">台湾国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="d7f91-3222">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-3223">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-3223">Format</span></span>

<span data-ttu-id="d7f91-3224">一个字母后跟九个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3224">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-3225">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-3225">Pattern</span></span>

<span data-ttu-id="d7f91-3226">一个字母后跟 9 位数字：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3226">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="d7f91-3227">一个字母（英文，不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="d7f91-3227">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="d7f91-3228">数字“1”或“2”</span><span class="sxs-lookup"><span data-stu-id="d7f91-3228">The digit "1" or "2"</span></span> 
- <span data-ttu-id="d7f91-3229">八位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3229">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-3230">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-3230">Checksum</span></span>

<span data-ttu-id="d7f91-3231">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-3231">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-3232">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-3232">Definition</span></span>

<span data-ttu-id="d7f91-3233">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3233">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-3234">函数 Func_taiwanese_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3234">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3235">找到 Keyword_taiwanese_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3235">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="d7f91-3236">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3236">The checksum passes.</span></span>

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-3237">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3237">Keywords</span></span>

#### <a name="keyword_taiwanese_national_id"></a><span data-ttu-id="d7f91-3238">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="d7f91-3238">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="d7f91-3239">身份證字號</span><span class="sxs-lookup"><span data-stu-id="d7f91-3239">身份證字號</span></span> 
- <span data-ttu-id="d7f91-3240">證</span><span class="sxs-lookup"><span data-stu-id="d7f91-3240">身份證</span></span> 
- <span data-ttu-id="d7f91-3241">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="d7f91-3241">身份證號碼</span></span> 
- <span data-ttu-id="d7f91-3242">身份證號</span><span class="sxs-lookup"><span data-stu-id="d7f91-3242">身份證號</span></span> 
- <span data-ttu-id="d7f91-3243">身分證字號</span><span class="sxs-lookup"><span data-stu-id="d7f91-3243">身分證字號</span></span> 
- <span data-ttu-id="d7f91-3244">身分證</span><span class="sxs-lookup"><span data-stu-id="d7f91-3244">身分證</span></span> 
- <span data-ttu-id="d7f91-3245">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="d7f91-3245">身分證號碼</span></span> 
- <span data-ttu-id="d7f91-3246">身份證號</span><span class="sxs-lookup"><span data-stu-id="d7f91-3246">身份證號</span></span> 
- <span data-ttu-id="d7f91-3247">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="d7f91-3247">身分證統一編號</span></span> 
- <span data-ttu-id="d7f91-3248">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="d7f91-3248">國民身分證統一編號</span></span> 
- <span data-ttu-id="d7f91-3249">簽名</span><span class="sxs-lookup"><span data-stu-id="d7f91-3249">簽名</span></span> 
- <span data-ttu-id="d7f91-3250">蓋章</span><span class="sxs-lookup"><span data-stu-id="d7f91-3250">蓋章</span></span> 
- <span data-ttu-id="d7f91-3251">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="d7f91-3251">簽名或蓋章</span></span> 
- <span data-ttu-id="d7f91-3252">簽章</span><span class="sxs-lookup"><span data-stu-id="d7f91-3252">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="d7f91-3253">	台湾护照号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-3253">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-3254">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-3254">Format</span></span>

- <span data-ttu-id="d7f91-3255">生物识别护照号码: 9 个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3255">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="d7f91-3256">不带生物的护照号码: 9 个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3256">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-3257">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-3257">Pattern</span></span>
<span data-ttu-id="d7f91-3258">生物识别护照号码:</span><span class="sxs-lookup"><span data-stu-id="d7f91-3258">Biometric passport number:</span></span>
- <span data-ttu-id="d7f91-3259">数字“3” </span><span class="sxs-lookup"><span data-stu-id="d7f91-3259">The digit "3"</span></span> 
- <span data-ttu-id="d7f91-3260">八个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3260">Eight digits</span></span>

<span data-ttu-id="d7f91-3261">不带生物的护照号码:</span><span class="sxs-lookup"><span data-stu-id="d7f91-3261">Non-biometric passport number:</span></span>
- <span data-ttu-id="d7f91-3262">九个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3262">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-3263">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-3263">Checksum</span></span>

<span data-ttu-id="d7f91-3264">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-3264">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-3265">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-3265">Definition</span></span>

<span data-ttu-id="d7f91-3266">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3266">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-3267">正则表达式 Regex_taiwan_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3267">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3268">找到 Keyword_taiwan_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3268">A keyword from Keyword_taiwan_passport is found.</span></span>

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-3269">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3269">Keywords</span></span>

#### <a name="keyword_taiwan_passport"></a><span data-ttu-id="d7f91-3270">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="d7f91-3270">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="d7f91-3271">ROC passport number</span><span class="sxs-lookup"><span data-stu-id="d7f91-3271">ROC passport number</span></span> 
- <span data-ttu-id="d7f91-3272">Passport number</span><span class="sxs-lookup"><span data-stu-id="d7f91-3272">Passport number</span></span> 
- <span data-ttu-id="d7f91-3273">Passport no</span><span class="sxs-lookup"><span data-stu-id="d7f91-3273">Passport no</span></span> 
- <span data-ttu-id="d7f91-3274">Passport Num</span><span class="sxs-lookup"><span data-stu-id="d7f91-3274">Passport Num</span></span> 
- <span data-ttu-id="d7f91-3275">Passport #</span><span class="sxs-lookup"><span data-stu-id="d7f91-3275">Passport #</span></span> 
- <span data-ttu-id="d7f91-3276">护照</span><span class="sxs-lookup"><span data-stu-id="d7f91-3276">护照</span></span> 
- <span data-ttu-id="d7f91-3277">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="d7f91-3277">中華民國護照</span></span> 
- <span data-ttu-id="d7f91-3278">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="d7f91-3278">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="d7f91-3279">台湾居民证 (ARC/TARC) 号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-3279">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-3280">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-3280">Format</span></span>

<span data-ttu-id="d7f91-3281">10 letters and digits</span><span class="sxs-lookup"><span data-stu-id="d7f91-3281">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-3282">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-3282">Pattern</span></span>

<span data-ttu-id="d7f91-3283">10 个字母和数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3283">10 letters and digits:</span></span>
- <span data-ttu-id="d7f91-3284">两个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="d7f91-3284">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="d7f91-3285">八个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3285">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-3286">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-3286">Checksum</span></span>

<span data-ttu-id="d7f91-3287">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-3287">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-3288">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-3288">Definition</span></span>

<span data-ttu-id="d7f91-3289">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3289">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-3290">正则表达式 Regex_taiwan_resident_certificate 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3290">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3291">找到 Keyword_taiwan_resident_certificate 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3291">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-3292">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3292">Keywords</span></span>

#### <a name="keyword_taiwan_resident_certificate"></a><span data-ttu-id="d7f91-3293">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="d7f91-3293">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="d7f91-3294">Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="d7f91-3294">Resident Certificate</span></span> 
- <span data-ttu-id="d7f91-3295">Resident Cert</span><span class="sxs-lookup"><span data-stu-id="d7f91-3295">Resident Cert</span></span> 
- <span data-ttu-id="d7f91-3296">Resident Cert.</span><span class="sxs-lookup"><span data-stu-id="d7f91-3296">Resident Cert.</span></span> 
- <span data-ttu-id="d7f91-3297">Identification card</span><span class="sxs-lookup"><span data-stu-id="d7f91-3297">Identification card</span></span> 
- <span data-ttu-id="d7f91-3298">Alien Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="d7f91-3298">Alien Resident Certificate</span></span> 
- <span data-ttu-id="d7f91-3299">ARC</span><span class="sxs-lookup"><span data-stu-id="d7f91-3299">ARC</span></span> 
- <span data-ttu-id="d7f91-3300">Taiwan Area Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="d7f91-3300">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="d7f91-3301">TARC</span><span class="sxs-lookup"><span data-stu-id="d7f91-3301">TARC</span></span> 
- <span data-ttu-id="d7f91-3302">居留證</span><span class="sxs-lookup"><span data-stu-id="d7f91-3302">居留證</span></span> 
- <span data-ttu-id="d7f91-3303">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="d7f91-3303">外僑居留證</span></span> 
- <span data-ttu-id="d7f91-3304">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="d7f91-3304">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="d7f91-3305">泰语填充标识代码</span><span class="sxs-lookup"><span data-stu-id="d7f91-3305">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-3306">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-3306">Format</span></span>

<span data-ttu-id="d7f91-3307">13 位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3307">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-3308">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-3308">Pattern</span></span>

<span data-ttu-id="d7f91-3309">13 个数字：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3309">13 digits:</span></span>
- <span data-ttu-id="d7f91-3310">第一个数字不是0或9</span><span class="sxs-lookup"><span data-stu-id="d7f91-3310">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="d7f91-3311">12 个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3311">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-3312">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-3312">Checksum</span></span>

<span data-ttu-id="d7f91-3313">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-3313">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-3314">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-3314">Definition</span></span>

<span data-ttu-id="d7f91-3315">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3315">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-3316">函数 Func_Thai_Citizen_Id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3316">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3317">找到 Keyword_Thai_Citizen_Id 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3317">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="d7f91-3318">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3318">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-3319">函数 Func_Thai_Citizen_Id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3319">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-3320">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3320">Keywords</span></span>

#### <a name="keyword_thai_citizen_id"></a><span data-ttu-id="d7f91-3321">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="d7f91-3321">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="d7f91-3322">ID Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-3322">ID Number</span></span>
- <span data-ttu-id="d7f91-3323">标识号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-3323">Identification Number</span></span>
- <span data-ttu-id="d7f91-3324">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="d7f91-3324">บัตรประชาชน</span></span>
- <span data-ttu-id="d7f91-3325">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="d7f91-3325">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="d7f91-3326">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="d7f91-3326">บัตรประชาชน</span></span>
- <span data-ttu-id="d7f91-3327">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="d7f91-3327">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="d7f91-3328">土耳其国家标识号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-3328">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-3329">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-3329">Format</span></span>

<span data-ttu-id="d7f91-3330">11 个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3330">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-3331">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-3331">Pattern</span></span>

<span data-ttu-id="d7f91-3332">11 个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3332">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-3333">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-3333">Checksum</span></span>

<span data-ttu-id="d7f91-3334">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-3334">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-3335">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-3335">Definition</span></span>

<span data-ttu-id="d7f91-3336">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3336">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-3337">函数 Func_Turkish_National_Id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3337">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3338">找到 Keyword_Turkish_National_Id 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3338">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="d7f91-3339">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3339">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-3340">函数 Func_Turkish_National_Id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3340">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-3341">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3341">Keywords</span></span>

#### <a name="keyword_turkish_national_id"></a><span data-ttu-id="d7f91-3342">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="d7f91-3342">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="d7f91-3343">TC Kimlik No</span><span class="sxs-lookup"><span data-stu-id="d7f91-3343">TC Kimlik No</span></span>
- <span data-ttu-id="d7f91-3344">TC Kimlik numarası</span><span class="sxs-lookup"><span data-stu-id="d7f91-3344">TC Kimlik numarası</span></span>
- <span data-ttu-id="d7f91-3345">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="d7f91-3345">Vatandaşlık numarası</span></span>
- <span data-ttu-id="d7f91-3346">Vatandaşlık no</span><span class="sxs-lookup"><span data-stu-id="d7f91-3346">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="d7f91-p141">英国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-p141">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-3349">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-3349">Format</span></span>

<span data-ttu-id="d7f91-3350">特定格式的 18 个字母和数字组合</span><span class="sxs-lookup"><span data-stu-id="d7f91-3350">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-3351">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-3351">Pattern</span></span>

<span data-ttu-id="d7f91-3352">18 个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3352">18 letters and digits:</span></span>
- <span data-ttu-id="d7f91-3353">用五个字母（不区分大小写）或数字“9”来代替一个字母</span><span class="sxs-lookup"><span data-stu-id="d7f91-3353">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="d7f91-3354">一位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3354">One digit</span></span> 
- <span data-ttu-id="d7f91-3355">采用日期格式 DDMMY 的五位数字，表示出生日期</span><span class="sxs-lookup"><span data-stu-id="d7f91-3355">Five digits in the date format DDMMY for date of birth</span></span> 
- <span data-ttu-id="d7f91-3356">用两个字母（不区分大小写）或数字“9”来代替一个字母</span><span class="sxs-lookup"><span data-stu-id="d7f91-3356">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="d7f91-3357">五位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3357">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-3358">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-3358">Checksum</span></span>

<span data-ttu-id="d7f91-3359">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-3359">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-3360">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-3360">Definition</span></span>

<span data-ttu-id="d7f91-3361">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3361">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-3362">函数 Func_uk_drivers_license 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3362">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3363">找到 Keyword_uk_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3363">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="d7f91-3364">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3364">The checksum passes.</span></span>

```xml
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-3365">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3365">Keywords</span></span>

#### <a name="keyword_uk_drivers_license"></a><span data-ttu-id="d7f91-3366">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="d7f91-3366">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="d7f91-3367">DVLA</span><span class="sxs-lookup"><span data-stu-id="d7f91-3367">DVLA</span></span> 
- <span data-ttu-id="d7f91-3368">light vans</span><span class="sxs-lookup"><span data-stu-id="d7f91-3368">light vans</span></span> 
- <span data-ttu-id="d7f91-3369">quadbikes</span><span class="sxs-lookup"><span data-stu-id="d7f91-3369">quadbikes</span></span> 
- <span data-ttu-id="d7f91-3370">motor cars</span><span class="sxs-lookup"><span data-stu-id="d7f91-3370">motor cars</span></span> 
- <span data-ttu-id="d7f91-3371">125cc</span><span class="sxs-lookup"><span data-stu-id="d7f91-3371">125cc</span></span> 
- <span data-ttu-id="d7f91-3372">sidecar</span><span class="sxs-lookup"><span data-stu-id="d7f91-3372">sidecar</span></span> 
- <span data-ttu-id="d7f91-3373">tricycles</span><span class="sxs-lookup"><span data-stu-id="d7f91-3373">tricycles</span></span> 
- <span data-ttu-id="d7f91-3374">motorcycles</span><span class="sxs-lookup"><span data-stu-id="d7f91-3374">motorcycles</span></span> 
- <span data-ttu-id="d7f91-3375">photocard licence</span><span class="sxs-lookup"><span data-stu-id="d7f91-3375">photocard licence</span></span> 
- <span data-ttu-id="d7f91-3376">learner drivers</span><span class="sxs-lookup"><span data-stu-id="d7f91-3376">learner drivers</span></span> 
- <span data-ttu-id="d7f91-3377">licence holder</span><span class="sxs-lookup"><span data-stu-id="d7f91-3377">licence holder</span></span> 
- <span data-ttu-id="d7f91-3378">licence holders</span><span class="sxs-lookup"><span data-stu-id="d7f91-3378">licence holders</span></span> 
- <span data-ttu-id="d7f91-3379">driving licences</span><span class="sxs-lookup"><span data-stu-id="d7f91-3379">driving licences</span></span> 
- <span data-ttu-id="d7f91-3380">driving licence</span><span class="sxs-lookup"><span data-stu-id="d7f91-3380">driving licence</span></span> 
- <span data-ttu-id="d7f91-3381">dual control car</span><span class="sxs-lookup"><span data-stu-id="d7f91-3381">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="d7f91-p142">英国选民名册号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-p142">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-3384">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-3384">Format</span></span>

<span data-ttu-id="d7f91-3385">两个字母后跟 1-4 个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3385">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-3386">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-3386">Pattern</span></span>

<span data-ttu-id="d7f91-3387">两个字母（不区分大小写）后跟 1-4 个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3387">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-3388">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-3388">Checksum</span></span>

<span data-ttu-id="d7f91-3389">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-3389">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-3390">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-3390">Definition</span></span>

<span data-ttu-id="d7f91-3391">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3391">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-3392">正则表达式 Regex_uk_electoral 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3392">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3393">找到 Keyword_uk_electoral 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3393">A keyword from Keyword_uk_electoral is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-3394">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3394">Keywords</span></span>

#### <a name="keyword_uk_electoral"></a><span data-ttu-id="d7f91-3395">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="d7f91-3395">Keyword_uk_electoral</span></span>

- <span data-ttu-id="d7f91-3396">council nomination</span><span class="sxs-lookup"><span data-stu-id="d7f91-3396">council nomination</span></span> 
- <span data-ttu-id="d7f91-3397">nomination form</span><span class="sxs-lookup"><span data-stu-id="d7f91-3397">nomination form</span></span> 
- <span data-ttu-id="d7f91-3398">electoral register</span><span class="sxs-lookup"><span data-stu-id="d7f91-3398">electoral register</span></span> 
- <span data-ttu-id="d7f91-3399">electoral roll</span><span class="sxs-lookup"><span data-stu-id="d7f91-3399">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="d7f91-p143">英国国家卫生服务号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-p143">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-3402">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-3402">Format</span></span>

<span data-ttu-id="d7f91-3403">10-17 个数字，通过空格分隔 </span><span class="sxs-lookup"><span data-stu-id="d7f91-3403">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-3404">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-3404">Pattern</span></span>

<span data-ttu-id="d7f91-3405">10-17 位数字：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3405">10-17 digits:</span></span>
- <span data-ttu-id="d7f91-3406">3 或 10 位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3406">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="d7f91-3407">一个空格</span><span class="sxs-lookup"><span data-stu-id="d7f91-3407">A space</span></span> 
- <span data-ttu-id="d7f91-3408">三位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3408">Three digits</span></span> 
- <span data-ttu-id="d7f91-3409">一个空格</span><span class="sxs-lookup"><span data-stu-id="d7f91-3409">A space</span></span> 
- <span data-ttu-id="d7f91-3410">四位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3410">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-3411">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-3411">Checksum</span></span>

<span data-ttu-id="d7f91-3412">是</span><span class="sxs-lookup"><span data-stu-id="d7f91-3412">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-3413">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-3413">Definition</span></span>

<span data-ttu-id="d7f91-3414">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3414">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-3415">函数 Func_uk_nhs_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3415">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3416">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3416">One of the following is true:</span></span>
    - <span data-ttu-id="d7f91-3417">找到 Keyword_uk_nhs_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3417">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="d7f91-3418">找到 Keyword_uk_nhs_number1 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3418">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="d7f91-3419">找到 Keyword_uk_nhs_number_dob 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3419">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="d7f91-3420">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3420">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-3421">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3421">Keywords</span></span>
   
#### <a name="keyword_uk_nhs_number"></a><span data-ttu-id="d7f91-3422">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="d7f91-3422">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="d7f91-3423">national health service</span><span class="sxs-lookup"><span data-stu-id="d7f91-3423">national health service</span></span> 
- <span data-ttu-id="d7f91-3424">nhs</span><span class="sxs-lookup"><span data-stu-id="d7f91-3424">nhs</span></span> 
- <span data-ttu-id="d7f91-3425">health services authority</span><span class="sxs-lookup"><span data-stu-id="d7f91-3425">health services authority</span></span> 
- <span data-ttu-id="d7f91-3426">health authority</span><span class="sxs-lookup"><span data-stu-id="d7f91-3426">health authority</span></span>

#### <a name="keyword_uk_nhs_number1"></a><span data-ttu-id="d7f91-3427">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="d7f91-3427">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="d7f91-3428">patient id</span><span class="sxs-lookup"><span data-stu-id="d7f91-3428">patient id</span></span> 
- <span data-ttu-id="d7f91-3429">patient identification</span><span class="sxs-lookup"><span data-stu-id="d7f91-3429">patient identification</span></span> 
- <span data-ttu-id="d7f91-3430">patient no</span><span class="sxs-lookup"><span data-stu-id="d7f91-3430">patient no</span></span> 
- <span data-ttu-id="d7f91-3431">patient number</span><span class="sxs-lookup"><span data-stu-id="d7f91-3431">patient number</span></span>

#### <a name="keyword_uk_nhs_number_dob"></a><span data-ttu-id="d7f91-3432">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="d7f91-3432">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="d7f91-3433">GP</span><span class="sxs-lookup"><span data-stu-id="d7f91-3433">GP</span></span> 
- <span data-ttu-id="d7f91-3434">DOB</span><span class="sxs-lookup"><span data-stu-id="d7f91-3434">DOB</span></span> 
- <span data-ttu-id="d7f91-3435">D. B。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3435">D.O.B</span></span> 
- <span data-ttu-id="d7f91-3436">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="d7f91-3436">Date of Birth</span></span> 
- <span data-ttu-id="d7f91-3437">Birth Date</span><span class="sxs-lookup"><span data-stu-id="d7f91-3437">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="d7f91-p144">英国国家保险号码 (NINO)</span><span class="sxs-lookup"><span data-stu-id="d7f91-p144">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-3440">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-3440">Format</span></span>

<span data-ttu-id="d7f91-3441">由空格或短划线分隔的7个字符或9个字符</span><span class="sxs-lookup"><span data-stu-id="d7f91-3441">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-3442">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-3442">Pattern</span></span>

<span data-ttu-id="d7f91-3443">两种可能的模式:</span><span class="sxs-lookup"><span data-stu-id="d7f91-3443">Two possible patterns:</span></span>

- <span data-ttu-id="d7f91-3444">两个字母 (有效 NINOs 仅使用此前缀中的特定字符, 此格式将对此进行验证; 不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="d7f91-3444">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="d7f91-3445">六位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3445">Six digits</span></span>
- <span data-ttu-id="d7f91-3446">"A"、"B"、"C" 或 "d" (与前缀一样, 后缀中只允许有某些字符; 不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="d7f91-3446">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="d7f91-3447">OR</span><span class="sxs-lookup"><span data-stu-id="d7f91-3447">OR</span></span>

- <span data-ttu-id="d7f91-3448">两个字母</span><span class="sxs-lookup"><span data-stu-id="d7f91-3448">Two letters</span></span>
- <span data-ttu-id="d7f91-3449">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="d7f91-3449">A space or dash</span></span>
- <span data-ttu-id="d7f91-3450">两位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3450">Two digits</span></span>
- <span data-ttu-id="d7f91-3451">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="d7f91-3451">A space or dash</span></span>
- <span data-ttu-id="d7f91-3452">两位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3452">Two digits</span></span>
- <span data-ttu-id="d7f91-3453">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="d7f91-3453">A space or dash</span></span>
- <span data-ttu-id="d7f91-3454">两位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3454">Two digits</span></span>
- <span data-ttu-id="d7f91-3455">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="d7f91-3455">A space or dash</span></span>
- <span data-ttu-id="d7f91-3456">要么是 "A"、"B"、"C", 要么 ' d '</span><span class="sxs-lookup"><span data-stu-id="d7f91-3456">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-3457">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-3457">Checksum</span></span>

<span data-ttu-id="d7f91-3458">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-3458">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-3459">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-3459">Definition</span></span>

<span data-ttu-id="d7f91-3460">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3460">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-3461">函数 Func_uk_nino 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3461">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3462">找到 Keyword_uk_nino 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3462">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="d7f91-3463">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3463">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-3464">函数 Func_uk_nino 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3464">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3465">未找到 Keyword_uk_nino 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3465">No keyword from Keyword_uk_nino is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-3466">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3466">Keywords</span></span>

#### <a name="keyword_uk_nino"></a><span data-ttu-id="d7f91-3467">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="d7f91-3467">Keyword_uk_nino</span></span>

- <span data-ttu-id="d7f91-3468">national insurance number</span><span class="sxs-lookup"><span data-stu-id="d7f91-3468">national insurance number</span></span> 
- <span data-ttu-id="d7f91-3469">national insurance contributions</span><span class="sxs-lookup"><span data-stu-id="d7f91-3469">national insurance contributions</span></span> 
- <span data-ttu-id="d7f91-3470">protection act</span><span class="sxs-lookup"><span data-stu-id="d7f91-3470">protection act</span></span> 
- <span data-ttu-id="d7f91-3471">方面</span><span class="sxs-lookup"><span data-stu-id="d7f91-3471">insurance</span></span> 
- <span data-ttu-id="d7f91-3472">social security number</span><span class="sxs-lookup"><span data-stu-id="d7f91-3472">social security number</span></span> 
- <span data-ttu-id="d7f91-3473">insurance application</span><span class="sxs-lookup"><span data-stu-id="d7f91-3473">insurance application</span></span> 
- <span data-ttu-id="d7f91-3474">medical application</span><span class="sxs-lookup"><span data-stu-id="d7f91-3474">medical application</span></span> 
- <span data-ttu-id="d7f91-3475">social insurance</span><span class="sxs-lookup"><span data-stu-id="d7f91-3475">social insurance</span></span> 
- <span data-ttu-id="d7f91-3476">medical attention</span><span class="sxs-lookup"><span data-stu-id="d7f91-3476">medical attention</span></span> 
- <span data-ttu-id="d7f91-3477">social security</span><span class="sxs-lookup"><span data-stu-id="d7f91-3477">social security</span></span> 
- <span data-ttu-id="d7f91-3478">great britain</span><span class="sxs-lookup"><span data-stu-id="d7f91-3478">great britain</span></span> 
- <span data-ttu-id="d7f91-3479">方面</span><span class="sxs-lookup"><span data-stu-id="d7f91-3479">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="d7f91-p145">美国/英国护照号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-p145">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-3482">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-3482">Format</span></span>

<span data-ttu-id="d7f91-3483">九个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3483">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-3484">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-3484">Pattern</span></span>

<span data-ttu-id="d7f91-3485">九个连续的数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3485">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-3486">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-3486">Checksum</span></span>

<span data-ttu-id="d7f91-3487">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-3487">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-3488">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-3488">Definition</span></span>

<span data-ttu-id="d7f91-3489">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3489">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-3490">函数 Func_usa_uk_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3490">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3491">找到 Keyword_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3491">A keyword from Keyword_passport is found.</span></span>

```xml
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-3492">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3492">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="d7f91-3493">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="d7f91-3493">Keyword_passport</span></span>

- <span data-ttu-id="d7f91-3494">Passport Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-3494">Passport Number</span></span> 
- <span data-ttu-id="d7f91-3495">Passport No</span><span class="sxs-lookup"><span data-stu-id="d7f91-3495">Passport No</span></span> 
- <span data-ttu-id="d7f91-3496">Passport #</span><span class="sxs-lookup"><span data-stu-id="d7f91-3496">Passport #</span></span> 
- <span data-ttu-id="d7f91-3497">登记卡#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3497">Passport#</span></span> 
- <span data-ttu-id="d7f91-3498">PassportID</span><span class="sxs-lookup"><span data-stu-id="d7f91-3498">PassportID</span></span> 
- <span data-ttu-id="d7f91-3499">Passportno</span><span class="sxs-lookup"><span data-stu-id="d7f91-3499">Passportno</span></span> 
- <span data-ttu-id="d7f91-3500">passportnumber</span><span class="sxs-lookup"><span data-stu-id="d7f91-3500">passportnumber</span></span> 
- <span data-ttu-id="d7f91-3501">パスポート</span><span class="sxs-lookup"><span data-stu-id="d7f91-3501">パスポート</span></span> 
- <span data-ttu-id="d7f91-3502">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="d7f91-3502">パスポート番号</span></span> 
- <span data-ttu-id="d7f91-3503">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="d7f91-3503">パスポートのNum</span></span> 
- <span data-ttu-id="d7f91-3504">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="d7f91-3504">パスポート＃</span></span> 
- <span data-ttu-id="d7f91-3505">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="d7f91-3505">Numéro de passeport</span></span> 
- <span data-ttu-id="d7f91-3506">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="d7f91-3506">Passeport n °</span></span> 
- <span data-ttu-id="d7f91-3507">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="d7f91-3507">Passeport Non</span></span> 
- <span data-ttu-id="d7f91-3508">Passeport #</span><span class="sxs-lookup"><span data-stu-id="d7f91-3508">Passeport #</span></span> 
- <span data-ttu-id="d7f91-3509">Passeport#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3509">Passeport#</span></span> 
- <span data-ttu-id="d7f91-3510">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="d7f91-3510">PasseportNon</span></span> 
- <span data-ttu-id="d7f91-3511">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="d7f91-3511">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="d7f91-3512">美国银行帐号</span><span class="sxs-lookup"><span data-stu-id="d7f91-3512">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-3513">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-3513">Format</span></span>

<span data-ttu-id="d7f91-3514">8-17 个数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3514">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-3515">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-3515">Pattern</span></span>

<span data-ttu-id="d7f91-3516">8-17 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3516">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-3517">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-3517">Checksum</span></span>

<span data-ttu-id="d7f91-3518">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-3518">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-3519">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-3519">Definition</span></span>

<span data-ttu-id="d7f91-3520">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3520">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-3521">正则表达式 Regex_usa_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3521">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3522">找到 Keyword_usa_Bank_Account 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3522">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-3523">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3523">Keywords</span></span>

#### <a name="keyword_usa_bank_account"></a><span data-ttu-id="d7f91-3524">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="d7f91-3524">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="d7f91-3525">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-3525">Checking Account Number</span></span> 
- <span data-ttu-id="d7f91-3526">Checking Account</span><span class="sxs-lookup"><span data-stu-id="d7f91-3526">Checking Account</span></span> 
- <span data-ttu-id="d7f91-3527">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="d7f91-3527">Checking Account #</span></span> 
- <span data-ttu-id="d7f91-3528">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-3528">Checking Acct Number</span></span> 
- <span data-ttu-id="d7f91-3529">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="d7f91-3529">Checking Acct #</span></span> 
- <span data-ttu-id="d7f91-3530">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="d7f91-3530">Checking Acct No.</span></span> 
- <span data-ttu-id="d7f91-3531">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="d7f91-3531">Checking Account No.</span></span> 
- <span data-ttu-id="d7f91-3532">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-3532">Bank Account Number</span></span> 
- <span data-ttu-id="d7f91-3533">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="d7f91-3533">Bank Account #</span></span> 
- <span data-ttu-id="d7f91-3534">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-3534">Bank Acct Number</span></span> 
- <span data-ttu-id="d7f91-3535">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="d7f91-3535">Bank Acct #</span></span> 
- <span data-ttu-id="d7f91-3536">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="d7f91-3536">Bank Acct No.</span></span> 
- <span data-ttu-id="d7f91-3537">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="d7f91-3537">Bank Account No.</span></span> 
- <span data-ttu-id="d7f91-3538">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-3538">Savings Account Number</span></span> 
- <span data-ttu-id="d7f91-3539">Savings Account.</span><span class="sxs-lookup"><span data-stu-id="d7f91-3539">Savings Account.</span></span> 
- <span data-ttu-id="d7f91-3540">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="d7f91-3540">Savings Account #</span></span> 
- <span data-ttu-id="d7f91-3541">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-3541">Savings Acct Number</span></span> 
- <span data-ttu-id="d7f91-3542">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="d7f91-3542">Savings Acct #</span></span> 
- <span data-ttu-id="d7f91-3543">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="d7f91-3543">Savings Acct No.</span></span> 
- <span data-ttu-id="d7f91-3544">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="d7f91-3544">Savings Account No.</span></span> 
- <span data-ttu-id="d7f91-3545">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-3545">Debit Account Number</span></span> 
- <span data-ttu-id="d7f91-3546">Debit Account</span><span class="sxs-lookup"><span data-stu-id="d7f91-3546">Debit Account</span></span> 
- <span data-ttu-id="d7f91-3547">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="d7f91-3547">Debit Account #</span></span> 
- <span data-ttu-id="d7f91-3548">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="d7f91-3548">Debit Acct Number</span></span> 
- <span data-ttu-id="d7f91-3549">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="d7f91-3549">Debit Acct #</span></span> 
- <span data-ttu-id="d7f91-3550">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="d7f91-3550">Debit Acct No.</span></span> 
- <span data-ttu-id="d7f91-3551">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="d7f91-3551">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="d7f91-3552">美国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="d7f91-3552">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-3553">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-3553">Format</span></span>

<span data-ttu-id="d7f91-3554">取决于州</span><span class="sxs-lookup"><span data-stu-id="d7f91-3554">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-3555">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-3555">Pattern</span></span>

<span data-ttu-id="d7f91-3556">取决于州 — 例如，纽约：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3556">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="d7f91-3557">与 ddd ddd ddd 相匹配的9个数字的格式将会匹配。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3557">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="d7f91-3558">诸如 dddddddd 的 9 个数字将不匹配。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3558">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-3559">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-3559">Checksum</span></span>

<span data-ttu-id="d7f91-3560">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-3560">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-3561">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-3561">Definition</span></span>

<span data-ttu-id="d7f91-3562">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3562">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-3563">函数 Func_new_york_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3563">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3564">找到 Keyword_[state_name]_drivers_license_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3564">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="d7f91-3565">找到 Keyword_us_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3565">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="d7f91-3566">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3566">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-3567">函数 Func_new_york_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3567">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3568">找到 Keyword_[state_name]_drivers_license_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3568">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="d7f91-3569">找到 Keyword_us_drivers_license_abbreviations 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3569">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="d7f91-3570">未找到 Keyword_us_drivers_license 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3570">No keyword from Keyword_us_drivers_license is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-3571">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3571">Keywords</span></span>

#### <a name="keyword_us_drivers_license_abbreviations"></a><span data-ttu-id="d7f91-3572">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="d7f91-3572">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="d7f91-3573">通讯</span><span class="sxs-lookup"><span data-stu-id="d7f91-3573">DL</span></span> 
- <span data-ttu-id="d7f91-3574">DLS</span><span class="sxs-lookup"><span data-stu-id="d7f91-3574">DLS</span></span> 
- <span data-ttu-id="d7f91-3575">采用</span><span class="sxs-lookup"><span data-stu-id="d7f91-3575">CDL</span></span> 
- <span data-ttu-id="d7f91-3576">CDLS</span><span class="sxs-lookup"><span data-stu-id="d7f91-3576">CDLS</span></span> 
- <span data-ttu-id="d7f91-3577">ID</span><span class="sxs-lookup"><span data-stu-id="d7f91-3577">ID</span></span> 
- <span data-ttu-id="d7f91-3578">Id</span><span class="sxs-lookup"><span data-stu-id="d7f91-3578">IDs</span></span> 
- <span data-ttu-id="d7f91-3579">通讯#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3579">DL#</span></span> 
- <span data-ttu-id="d7f91-3580">DLS#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3580">DLS#</span></span> 
- <span data-ttu-id="d7f91-3581">采用#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3581">CDL#</span></span> 
- <span data-ttu-id="d7f91-3582">CDLS#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3582">CDLS#</span></span> 
- <span data-ttu-id="d7f91-3583">号#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3583">ID#</span></span>
- <span data-ttu-id="d7f91-3584">Id#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3584">IDs#</span></span> 
- <span data-ttu-id="d7f91-3585">ID number</span><span class="sxs-lookup"><span data-stu-id="d7f91-3585">ID number</span></span> 
- <span data-ttu-id="d7f91-3586">ID numbers</span><span class="sxs-lookup"><span data-stu-id="d7f91-3586">ID numbers</span></span> 
- <span data-ttu-id="d7f91-3587">.LIC</span><span class="sxs-lookup"><span data-stu-id="d7f91-3587">LIC</span></span> 
- <span data-ttu-id="d7f91-3588">.LIC#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3588">LIC#</span></span> 

#### <a name="keyword_us_drivers_license"></a><span data-ttu-id="d7f91-3589">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="d7f91-3589">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="d7f91-3590">DriverLic</span><span class="sxs-lookup"><span data-stu-id="d7f91-3590">DriverLic</span></span> 
- <span data-ttu-id="d7f91-3591">DriverLics</span><span class="sxs-lookup"><span data-stu-id="d7f91-3591">DriverLics</span></span> 
- <span data-ttu-id="d7f91-3592">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="d7f91-3592">DriverLicense</span></span> 
- <span data-ttu-id="d7f91-3593">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="d7f91-3593">DriverLicenses</span></span> 
- <span data-ttu-id="d7f91-3594">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="d7f91-3594">Driver Lic</span></span> 
- <span data-ttu-id="d7f91-3595">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="d7f91-3595">Driver Lics</span></span> 
- <span data-ttu-id="d7f91-3596">Driver License</span><span class="sxs-lookup"><span data-stu-id="d7f91-3596">Driver License</span></span> 
- <span data-ttu-id="d7f91-3597">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="d7f91-3597">Driver Licenses</span></span> 
- <span data-ttu-id="d7f91-3598">DriversLic</span><span class="sxs-lookup"><span data-stu-id="d7f91-3598">DriversLic</span></span> 
- <span data-ttu-id="d7f91-3599">DriversLics</span><span class="sxs-lookup"><span data-stu-id="d7f91-3599">DriversLics</span></span> 
- <span data-ttu-id="d7f91-3600">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="d7f91-3600">DriversLicense</span></span> 
- <span data-ttu-id="d7f91-3601">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="d7f91-3601">DriversLicenses</span></span> 
- <span data-ttu-id="d7f91-3602">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="d7f91-3602">Drivers Lic</span></span> 
- <span data-ttu-id="d7f91-3603">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="d7f91-3603">Drivers Lics</span></span> 
- <span data-ttu-id="d7f91-3604">Drivers License</span><span class="sxs-lookup"><span data-stu-id="d7f91-3604">Drivers License</span></span> 
- <span data-ttu-id="d7f91-3605">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="d7f91-3605">Drivers Licenses</span></span> 
- <span data-ttu-id="d7f91-3606">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="d7f91-3606">Driver'Lic</span></span> 
- <span data-ttu-id="d7f91-3607">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="d7f91-3607">Driver'Lics</span></span> 
- <span data-ttu-id="d7f91-3608">Driver'License</span><span class="sxs-lookup"><span data-stu-id="d7f91-3608">Driver'License</span></span> 
- <span data-ttu-id="d7f91-3609">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="d7f91-3609">Driver'Licenses</span></span> 
- <span data-ttu-id="d7f91-3610">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="d7f91-3610">Driver' Lic</span></span> 
- <span data-ttu-id="d7f91-3611">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="d7f91-3611">Driver' Lics</span></span> 
- <span data-ttu-id="d7f91-3612">Driver' License</span><span class="sxs-lookup"><span data-stu-id="d7f91-3612">Driver' License</span></span> 
- <span data-ttu-id="d7f91-3613">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="d7f91-3613">Driver' Licenses</span></span>
- <span data-ttu-id="d7f91-3614">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="d7f91-3614">Driver'sLic</span></span> 
- <span data-ttu-id="d7f91-3615">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="d7f91-3615">Driver'sLics</span></span> 
- <span data-ttu-id="d7f91-3616">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="d7f91-3616">Driver'sLicense</span></span> 
- <span data-ttu-id="d7f91-3617">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="d7f91-3617">Driver'sLicenses</span></span> 
- <span data-ttu-id="d7f91-3618">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="d7f91-3618">Driver's Lic</span></span> 
- <span data-ttu-id="d7f91-3619">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="d7f91-3619">Driver's Lics</span></span> 
- <span data-ttu-id="d7f91-3620">Driver's License</span><span class="sxs-lookup"><span data-stu-id="d7f91-3620">Driver's License</span></span> 
- <span data-ttu-id="d7f91-3621">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="d7f91-3621">Driver's Licenses</span></span> 
- <span data-ttu-id="d7f91-3622">identification number</span><span class="sxs-lookup"><span data-stu-id="d7f91-3622">identification number</span></span> 
- <span data-ttu-id="d7f91-3623">identification numbers</span><span class="sxs-lookup"><span data-stu-id="d7f91-3623">identification numbers</span></span> 
- <span data-ttu-id="d7f91-3624">identification #</span><span class="sxs-lookup"><span data-stu-id="d7f91-3624">identification #</span></span> 
- <span data-ttu-id="d7f91-3625">id card</span><span class="sxs-lookup"><span data-stu-id="d7f91-3625">id card</span></span> 
- <span data-ttu-id="d7f91-3626">id cards</span><span class="sxs-lookup"><span data-stu-id="d7f91-3626">id cards</span></span> 
- <span data-ttu-id="d7f91-3627">identification card</span><span class="sxs-lookup"><span data-stu-id="d7f91-3627">identification card</span></span> 
- <span data-ttu-id="d7f91-3628">identification cards</span><span class="sxs-lookup"><span data-stu-id="d7f91-3628">identification cards</span></span> 
- <span data-ttu-id="d7f91-3629">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3629">DriverLic#</span></span> 
- <span data-ttu-id="d7f91-3630">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3630">DriverLics#</span></span> 
- <span data-ttu-id="d7f91-3631">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3631">DriverLicense#</span></span> 
- <span data-ttu-id="d7f91-3632">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3632">DriverLicenses#</span></span> 
- <span data-ttu-id="d7f91-3633">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3633">Driver Lic#</span></span> 
- <span data-ttu-id="d7f91-3634">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3634">Driver Lics#</span></span> 
- <span data-ttu-id="d7f91-3635">Driver License#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3635">Driver License#</span></span> 
- <span data-ttu-id="d7f91-3636">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3636">Driver Licenses#</span></span> 
- <span data-ttu-id="d7f91-3637">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3637">DriversLic#</span></span> 
- <span data-ttu-id="d7f91-3638">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3638">DriversLics#</span></span> 
- <span data-ttu-id="d7f91-3639">DriversLicense#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3639">DriversLicense#</span></span> 
- <span data-ttu-id="d7f91-3640">DriversLicenses#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3640">DriversLicenses#</span></span> 
- <span data-ttu-id="d7f91-3641">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3641">Drivers Lic#</span></span> 
- <span data-ttu-id="d7f91-3642">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3642">Drivers Lics#</span></span> 
- <span data-ttu-id="d7f91-3643">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3643">Drivers License#</span></span> 
- <span data-ttu-id="d7f91-3644">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3644">Drivers Licenses#</span></span> 
- <span data-ttu-id="d7f91-3645">Driver'Lic#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3645">Driver'Lic#</span></span> 
- <span data-ttu-id="d7f91-3646">Driver'Lics#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3646">Driver'Lics#</span></span> 
- <span data-ttu-id="d7f91-3647">Driver'License#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3647">Driver'License#</span></span> 
- <span data-ttu-id="d7f91-3648">Driver'Licenses#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3648">Driver'Licenses#</span></span> 
- <span data-ttu-id="d7f91-3649">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3649">Driver' Lic#</span></span> 
- <span data-ttu-id="d7f91-3650">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3650">Driver' Lics#</span></span> 
- <span data-ttu-id="d7f91-3651">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3651">Driver' License#</span></span> 
- <span data-ttu-id="d7f91-3652">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3652">Driver' Licenses#</span></span> 
- <span data-ttu-id="d7f91-3653">Driver'sLic#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3653">Driver'sLic#</span></span> 
- <span data-ttu-id="d7f91-3654">Driver'sLics#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3654">Driver'sLics#</span></span> 
- <span data-ttu-id="d7f91-3655">Driver'sLicense#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3655">Driver'sLicense#</span></span> 
- <span data-ttu-id="d7f91-3656">Driver'sLicenses#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3656">Driver'sLicenses#</span></span> 
- <span data-ttu-id="d7f91-3657">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3657">Driver's Lic#</span></span> 
- <span data-ttu-id="d7f91-3658">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3658">Driver's Lics#</span></span> 
- <span data-ttu-id="d7f91-3659">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3659">Driver's License#</span></span> 
- <span data-ttu-id="d7f91-3660">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3660">Driver's Licenses#</span></span> 
- <span data-ttu-id="d7f91-3661">id card#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3661">id card#</span></span> 
- <span data-ttu-id="d7f91-3662">id cards#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3662">id cards#</span></span> 
- <span data-ttu-id="d7f91-3663">identification card#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3663">identification card#</span></span> 
- <span data-ttu-id="d7f91-3664">identification cards#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3664">identification cards#</span></span> 


#### <a name="keyword_state_name_drivers_license_name"></a><span data-ttu-id="d7f91-3665">Keyword_[state_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="d7f91-3665">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="d7f91-3666">州缩写（例如，“NY”）</span><span class="sxs-lookup"><span data-stu-id="d7f91-3666">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="d7f91-3667">州名称（例如，“New York”）</span><span class="sxs-lookup"><span data-stu-id="d7f91-3667">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="d7f91-3668">美国单独的纳税人标识号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="d7f91-3668">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-3669">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-3669">Format</span></span>

<span data-ttu-id="d7f91-3670">九个数字，以“9”开头，“7”或“8”作为第四个数字，可以采用空格或短划线格式</span><span class="sxs-lookup"><span data-stu-id="d7f91-3670">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-3671">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-3671">Pattern</span></span>

<span data-ttu-id="d7f91-3672">格式</span><span class="sxs-lookup"><span data-stu-id="d7f91-3672">Formatted:</span></span>
- <span data-ttu-id="d7f91-3673">数字“9”</span><span class="sxs-lookup"><span data-stu-id="d7f91-3673">The digit "9"</span></span> 
- <span data-ttu-id="d7f91-3674">两位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3674">Two digits</span></span> 
- <span data-ttu-id="d7f91-3675">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="d7f91-3675">A space or dash</span></span> 
- <span data-ttu-id="d7f91-3676">“7”或“8”</span><span class="sxs-lookup"><span data-stu-id="d7f91-3676">A "7" or "8"</span></span> 
- <span data-ttu-id="d7f91-3677">一位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3677">A digit</span></span> 
- <span data-ttu-id="d7f91-3678">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="d7f91-3678">A space, or dash</span></span> 
- <span data-ttu-id="d7f91-3679">四位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3679">Four digits</span></span>

<span data-ttu-id="d7f91-3680">纯</span><span class="sxs-lookup"><span data-stu-id="d7f91-3680">Unformatted:</span></span>
- <span data-ttu-id="d7f91-3681">数字“9”</span><span class="sxs-lookup"><span data-stu-id="d7f91-3681">The digit "9"</span></span> 
- <span data-ttu-id="d7f91-3682">两位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3682">Two digits</span></span> 
- <span data-ttu-id="d7f91-3683">“7”或“8”</span><span class="sxs-lookup"><span data-stu-id="d7f91-3683">A "7" or "8"</span></span> 
- <span data-ttu-id="d7f91-3684">五位数字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3684">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-3685">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-3685">Checksum</span></span>

<span data-ttu-id="d7f91-3686">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-3686">No</span></span>

### <a name="definition"></a><span data-ttu-id="d7f91-3687">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-3687">Definition</span></span>

<span data-ttu-id="d7f91-3688">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-3689">函数 Func_formatted_itin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3689">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3690">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3690">At least one of the following is true:</span></span>
    - <span data-ttu-id="d7f91-3691">找到 Keyword_itin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3691">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="d7f91-3692">函数 Func_us_address 找到正确日期格式的地址。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3692">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="d7f91-3693">函数 Func_us_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3693">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="d7f91-3694">找到 Keyword_itin_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3694">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="d7f91-3695">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3695">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-3696">函数 Func_unformatted_itin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3696">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3697">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3697">At least one of the following is true:</span></span>
    - <span data-ttu-id="d7f91-3698">找到 Keyword_itin_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3698">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="d7f91-3699">函数 Func_us_address 找到正确日期格式的地址。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3699">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="d7f91-3700">函数 Func_us_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3700">The function Func_us_date finds a date in the right date format.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="d7f91-3701">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3701">Keywords</span></span>

#### <a name="keyword_itin"></a><span data-ttu-id="d7f91-3702">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="d7f91-3702">Keyword_itin</span></span>

- <span data-ttu-id="d7f91-3703">报税</span><span class="sxs-lookup"><span data-stu-id="d7f91-3703">taxpayer</span></span> 
- <span data-ttu-id="d7f91-3704">tax id</span><span class="sxs-lookup"><span data-stu-id="d7f91-3704">tax id</span></span> 
- <span data-ttu-id="d7f91-3705">tax identification</span><span class="sxs-lookup"><span data-stu-id="d7f91-3705">tax identification</span></span> 
- <span data-ttu-id="d7f91-3706">itin</span><span class="sxs-lookup"><span data-stu-id="d7f91-3706">itin</span></span> 
- <span data-ttu-id="d7f91-3707">ssn</span><span class="sxs-lookup"><span data-stu-id="d7f91-3707">ssn</span></span> 
- <span data-ttu-id="d7f91-3708">锡</span><span class="sxs-lookup"><span data-stu-id="d7f91-3708">tin</span></span> 
- <span data-ttu-id="d7f91-3709">social security</span><span class="sxs-lookup"><span data-stu-id="d7f91-3709">social security</span></span> 
- <span data-ttu-id="d7f91-3710">tax payer</span><span class="sxs-lookup"><span data-stu-id="d7f91-3710">tax payer</span></span> 
- <span data-ttu-id="d7f91-3711">itins</span><span class="sxs-lookup"><span data-stu-id="d7f91-3711">itins</span></span> 
- <span data-ttu-id="d7f91-3712">taxid</span><span class="sxs-lookup"><span data-stu-id="d7f91-3712">taxid</span></span> 
- <span data-ttu-id="d7f91-3713">individual taxpayer</span><span class="sxs-lookup"><span data-stu-id="d7f91-3713">individual taxpayer</span></span> 

#### <a name="keyword_itin_collaborative"></a><span data-ttu-id="d7f91-3714">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="d7f91-3714">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="d7f91-3715">许可证</span><span class="sxs-lookup"><span data-stu-id="d7f91-3715">License</span></span> 
- <span data-ttu-id="d7f91-3716">通讯</span><span class="sxs-lookup"><span data-stu-id="d7f91-3716">DL</span></span> 
- <span data-ttu-id="d7f91-3717">DOB</span><span class="sxs-lookup"><span data-stu-id="d7f91-3717">DOB</span></span> 
- <span data-ttu-id="d7f91-3718">出生日期</span><span class="sxs-lookup"><span data-stu-id="d7f91-3718">Birthdate</span></span> 
- <span data-ttu-id="d7f91-3719">生日</span><span class="sxs-lookup"><span data-stu-id="d7f91-3719">Birthday</span></span> 
- <span data-ttu-id="d7f91-3720">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="d7f91-3720">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="d7f91-3721">美国社会保险号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="d7f91-3721">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="d7f91-3722">Format</span><span class="sxs-lookup"><span data-stu-id="d7f91-3722">Format</span></span>

<span data-ttu-id="d7f91-3723">9 个数字，可以是格式化模式，也可以是非格式化模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-3723">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="d7f91-3724">如果在 2011 年中旬前发布，则 SSN 具有强格式，即数字的某部分必须介于某个有效的范围中（但是没有校验和）。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3724">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="d7f91-3725">模式</span><span class="sxs-lookup"><span data-stu-id="d7f91-3725">Pattern</span></span>

<span data-ttu-id="d7f91-3726">四种不同模式中的 SSN 的四种函数外观：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3726">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="d7f91-3727">Func_ssn 查找具有 2011 年以前使用短划线或空格格式化的强格式的 SSN（ddd-dd-dddd 或 ddd dd dddd）</span><span class="sxs-lookup"><span data-stu-id="d7f91-3727">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="d7f91-3728">Func_unformatted_ssn 查找具有 2011 年以前未格式化为 9 个连续数字的强格式的 SSN (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="d7f91-3728">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="d7f91-3729">Func_randomized_formatted_ssn 查找 2011 年后使用短划线或空格（ddd-dd-dddd 或 ddd dd dddd）格式化的 SSN</span><span class="sxs-lookup"><span data-stu-id="d7f91-3729">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="d7f91-3730">Func_randomized_unformatted_ssn 查找 2011 年后未格式化为 9 个连续数字 (ddddddddd) 的 SSN</span><span class="sxs-lookup"><span data-stu-id="d7f91-3730">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="d7f91-3731">校验和</span><span class="sxs-lookup"><span data-stu-id="d7f91-3731">Checksum</span></span>

<span data-ttu-id="d7f91-3732">否</span><span class="sxs-lookup"><span data-stu-id="d7f91-3732">No</span></span>


### <a name="definition"></a><span data-ttu-id="d7f91-3733">定义</span><span class="sxs-lookup"><span data-stu-id="d7f91-3733">Definition</span></span>

<span data-ttu-id="d7f91-3734">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3734">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-3735">函数 Func_ssn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3735">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3736">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3736">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="d7f91-3737">函数 Func_us_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3737">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="d7f91-3738">函数 Func_us_address 找到正确格式的地址。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3738">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="d7f91-3739">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3739">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-3740">函数 Func_unformatted_ssn 查找与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3740">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3741">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3741">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="d7f91-3742">函数 Func_us_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3742">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="d7f91-3743">函数 Func_us_address 找到正确格式的地址。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3743">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="d7f91-3744">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3744">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-3745">函数 Func_randomized_formatted_ssn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3745">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3746">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3746">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="d7f91-3747">函数 Func_us_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3747">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="d7f91-3748">函数 Func_us_address 找到正确格式的地址。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3748">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="d7f91-3749">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 55% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d7f91-3749">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-3750">函数 Func_randomized_unformatted_ssn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3750">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3751">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3751">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="d7f91-3752">函数 Func_us_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3752">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="d7f91-3753">函数 Func_us_address 找到正确格式的地址。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3753">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="d7f91-3754">如果 DLP 策略在300个字符的邻近度内检测到此类型的敏感信息, 则 DLP 策略 40% 确信它检测到这种类型的敏感信息:</span><span class="sxs-lookup"><span data-stu-id="d7f91-3754">A DLP policy is 40% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d7f91-3755">函数 Func_ssn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3755">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3756">函数 Func_unformatted_ssn 未找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3756">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3757">函数 Func_randomized_unformatted_ssn 未找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3757">The function Func_randomized_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3758">找不到 Keyword_ssn 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3758">A keyword from Keyword_ssn is not found.</span></span>
 
<span data-ttu-id="d7f91-3759">或</span><span class="sxs-lookup"><span data-stu-id="d7f91-3759">Or</span></span>

- <span data-ttu-id="d7f91-3760">函数 Func_randomized_formatted_ssn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3760">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3761">函数 Func_unformatted_ssn 未找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3761">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3762">函数 Func_randomized_unformatted_ssn 未找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3762">The function Func_randomized_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="d7f91-3763">找不到 Keyword_ssn 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="d7f91-3763">A keyword from Keyword_ssn is not found.</span></span>

```xml
<!-- U.S. Social Security Number (SSN) -->
  <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Any minMatches="1">
          <Match idRef="Keyword_ssn" />
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
        <Any minMatches="1">
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Any minMatches="1">
          <Match idRef="Keyword_ssn" />
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
        <Any minMatches="1">
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="40">
        <IdMatch idRef="Func_ssn" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Func_unformatted_ssn" />
          <Match idRef="Func_randomized_unformatted_ssn" />
          <Match idRef="Keyword_ssn" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="40">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Func_unformatted_ssn" />
          <Match idRef="Func_randomized_unformatted_ssn" />
          <Match idRef="Keyword_ssn" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="d7f91-3764">关键字</span><span class="sxs-lookup"><span data-stu-id="d7f91-3764">Keywords</span></span>

#### <a name="keyword_ssn"></a><span data-ttu-id="d7f91-3765">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="d7f91-3765">Keyword_ssn</span></span>

- <span data-ttu-id="d7f91-3766">Social Security</span><span class="sxs-lookup"><span data-stu-id="d7f91-3766">Social Security</span></span> 
- <span data-ttu-id="d7f91-3767">Social Security#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3767">Social Security#</span></span> 
- <span data-ttu-id="d7f91-3768">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="d7f91-3768">Soc Sec</span></span> 
- <span data-ttu-id="d7f91-3769">SSN</span><span class="sxs-lookup"><span data-stu-id="d7f91-3769">SSN</span></span> 
- <span data-ttu-id="d7f91-3770">SSN</span><span class="sxs-lookup"><span data-stu-id="d7f91-3770">SSNS</span></span> 
- <span data-ttu-id="d7f91-3771">SSN#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3771">SSN#</span></span> 
- <span data-ttu-id="d7f91-3772">SS#</span><span class="sxs-lookup"><span data-stu-id="d7f91-3772">SS#</span></span> 
- <span data-ttu-id="d7f91-3773">SSID</span><span class="sxs-lookup"><span data-stu-id="d7f91-3773">SSID</span></span> 
   

