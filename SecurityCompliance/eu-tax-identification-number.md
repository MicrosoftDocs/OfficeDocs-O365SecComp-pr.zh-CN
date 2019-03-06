---
title: EU 税标识号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主题介绍当数据丢失防护 (DLP) 策略检测到欧盟税务识别号敏感信息类型时, 应查找什么。 此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。
ms.openlocfilehash: 4914ff078695519c2a298190d82c86a6abebceb9
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410907"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="eef02-104">EU 税标识号</span><span class="sxs-lookup"><span data-stu-id="eef02-104">EU Tax Identification Number</span></span>

<span data-ttu-id="eef02-105">本主题介绍了数据丢失防护 (DLP) 策略在检测到欧盟纳税标识号 (TIN) 敏感信息类型时的查找内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type.</span></span> <span data-ttu-id="eef02-106">此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。</span><span class="sxs-lookup"><span data-stu-id="eef02-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="eef02-107">奥地利</span><span class="sxs-lookup"><span data-stu-id="eef02-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="eef02-108">格式</span><span class="sxs-lookup"><span data-stu-id="eef02-108">Format</span></span>

<span data-ttu-id="eef02-109">9个数字, 带可选连字符和正斜线</span><span class="sxs-lookup"><span data-stu-id="eef02-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eef02-110">模式</span><span class="sxs-lookup"><span data-stu-id="eef02-110">Pattern</span></span>

<span data-ttu-id="eef02-111">9个带可选连字符和正斜线的数字:</span><span class="sxs-lookup"><span data-stu-id="eef02-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="eef02-112">两位数字</span><span class="sxs-lookup"><span data-stu-id="eef02-112">Two digits</span></span> 
    
- <span data-ttu-id="eef02-113">一个连字符（可选）</span><span class="sxs-lookup"><span data-stu-id="eef02-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="eef02-114">三位数字</span><span class="sxs-lookup"><span data-stu-id="eef02-114">Three digits</span></span>
    
- <span data-ttu-id="eef02-115">正斜杠（可选）</span><span class="sxs-lookup"><span data-stu-id="eef02-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="eef02-116">四位数字</span><span class="sxs-lookup"><span data-stu-id="eef02-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="eef02-117">校验和</span><span class="sxs-lookup"><span data-stu-id="eef02-117">Checksum</span></span>

<span data-ttu-id="eef02-118">是</span><span class="sxs-lookup"><span data-stu-id="eef02-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="eef02-119">定义</span><span class="sxs-lookup"><span data-stu-id="eef02-119">Definition</span></span>

<span data-ttu-id="eef02-120">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-121">函数`Func_austria_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eef02-122">找到了中`Keywords_austria_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="eef02-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="eef02-123">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-124">函数`Func_austria_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eef02-125">关键字</span><span class="sxs-lookup"><span data-stu-id="eef02-125">Keywords</span></span>

#### <a name="keywordsaustriaeutaxfilenumber"></a><span data-ttu-id="eef02-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="eef02-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="eef02-127">税号</span><span class="sxs-lookup"><span data-stu-id="eef02-127">tax number</span></span>
  
<span data-ttu-id="eef02-128">number</span><span class="sxs-lookup"><span data-stu-id="eef02-128">number</span></span>
  
<span data-ttu-id="eef02-129">税务登记编号</span><span class="sxs-lookup"><span data-stu-id="eef02-129">tax registration number</span></span>
  
<span data-ttu-id="eef02-130">tax id</span><span class="sxs-lookup"><span data-stu-id="eef02-130">tax id</span></span>
  
<span data-ttu-id="eef02-131">st.nr。</span><span class="sxs-lookup"><span data-stu-id="eef02-131">st.nr.</span></span>
  
<span data-ttu-id="eef02-132">steuernummer</span><span class="sxs-lookup"><span data-stu-id="eef02-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="eef02-133">比利时</span><span class="sxs-lookup"><span data-stu-id="eef02-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="eef02-134">格式</span><span class="sxs-lookup"><span data-stu-id="eef02-134">Format</span></span>

<span data-ttu-id="eef02-135">11个数字, 无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="eef02-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eef02-136">模式</span><span class="sxs-lookup"><span data-stu-id="eef02-136">Pattern</span></span>

<span data-ttu-id="eef02-137">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="eef02-137">11 digits:</span></span>
  
- <span data-ttu-id="eef02-138">两位数字</span><span class="sxs-lookup"><span data-stu-id="eef02-138">Two digits</span></span>
    
- <span data-ttu-id="eef02-139">"0" 或 "1"</span><span class="sxs-lookup"><span data-stu-id="eef02-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="eef02-140">一位数字</span><span class="sxs-lookup"><span data-stu-id="eef02-140">One digit</span></span>
    
- <span data-ttu-id="eef02-141">"0" 或 "1" 或 "2" 或 "3"</span><span class="sxs-lookup"><span data-stu-id="eef02-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="eef02-142">六个数字</span><span class="sxs-lookup"><span data-stu-id="eef02-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="eef02-143">校验和</span><span class="sxs-lookup"><span data-stu-id="eef02-143">Checksum</span></span>

<span data-ttu-id="eef02-144">不适用</span><span class="sxs-lookup"><span data-stu-id="eef02-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="eef02-145">定义</span><span class="sxs-lookup"><span data-stu-id="eef02-145">Definition</span></span>

<span data-ttu-id="eef02-146">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-147">正则表达式`Regex_belgium_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eef02-148">找到了中`Keywords_belgium_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="eef02-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eef02-149">关键字</span><span class="sxs-lookup"><span data-stu-id="eef02-149">Keywords</span></span>

#### <a name="keywordsbelgiumeutaxfilenumber"></a><span data-ttu-id="eef02-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="eef02-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="eef02-151">税号</span><span class="sxs-lookup"><span data-stu-id="eef02-151">tax number</span></span>
  
<span data-ttu-id="eef02-152">国家注册号码</span><span class="sxs-lookup"><span data-stu-id="eef02-152">national registration number</span></span>
  
<span data-ttu-id="eef02-153">税务登记编号</span><span class="sxs-lookup"><span data-stu-id="eef02-153">tax registration number</span></span>
  
<span data-ttu-id="eef02-154">tax id</span><span class="sxs-lookup"><span data-stu-id="eef02-154">tax id</span></span>
  
<span data-ttu-id="eef02-155">\n\n</span><span class="sxs-lookup"><span data-stu-id="eef02-155">nif</span></span>
  
<span data-ttu-id="eef02-156">\n\n</span><span class="sxs-lookup"><span data-stu-id="eef02-156">nif#</span></span>
  
<span data-ttu-id="eef02-157">numéro de registre 国</span><span class="sxs-lookup"><span data-stu-id="eef02-157">numéro de registre national</span></span>
  
<span data-ttu-id="eef02-158">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="eef02-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="eef02-159">保加利亚语</span><span class="sxs-lookup"><span data-stu-id="eef02-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="eef02-160">格式</span><span class="sxs-lookup"><span data-stu-id="eef02-160">Format</span></span>

<span data-ttu-id="eef02-161">10个数字, 无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="eef02-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eef02-162">模式</span><span class="sxs-lookup"><span data-stu-id="eef02-162">Pattern</span></span>

<span data-ttu-id="eef02-163">10 个数字</span><span class="sxs-lookup"><span data-stu-id="eef02-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="eef02-164">校验和</span><span class="sxs-lookup"><span data-stu-id="eef02-164">Checksum</span></span>

<span data-ttu-id="eef02-165">是</span><span class="sxs-lookup"><span data-stu-id="eef02-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="eef02-166">定义</span><span class="sxs-lookup"><span data-stu-id="eef02-166">Definition</span></span>

<span data-ttu-id="eef02-167">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-168">函数`Func_bulgaria_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eef02-169">找到了中`Keywords_bulgaria_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="eef02-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="eef02-170">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-171">函数`Func_bulgaria_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
          <Match idRef="Keywords_bulgaria_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eef02-172">关键字</span><span class="sxs-lookup"><span data-stu-id="eef02-172">Keywords</span></span>

#### <a name="keywordsbulgariaeutaxfilenumber"></a><span data-ttu-id="eef02-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="eef02-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="eef02-174">bucn</span><span class="sxs-lookup"><span data-stu-id="eef02-174">bucn</span></span>
  
<span data-ttu-id="eef02-175">统一的民事号码</span><span class="sxs-lookup"><span data-stu-id="eef02-175">uniform civil number</span></span>
  
<span data-ttu-id="eef02-176">bucn #</span><span class="sxs-lookup"><span data-stu-id="eef02-176">bucn#</span></span>
  
<span data-ttu-id="eef02-177">uniformcivilnumber #</span><span class="sxs-lookup"><span data-stu-id="eef02-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="eef02-178">统一的民事 id</span><span class="sxs-lookup"><span data-stu-id="eef02-178">uniform civil id</span></span>
  
<span data-ttu-id="eef02-179">统一的民事无</span><span class="sxs-lookup"><span data-stu-id="eef02-179">uniform civil no</span></span>
  
<span data-ttu-id="eef02-180">egn</span><span class="sxs-lookup"><span data-stu-id="eef02-180">egn</span></span>
  
<span data-ttu-id="eef02-181">保加利亚语统一民事号码</span><span class="sxs-lookup"><span data-stu-id="eef02-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="eef02-182">uniformcivilno #</span><span class="sxs-lookup"><span data-stu-id="eef02-182">uniformcivilno#</span></span>
  
<span data-ttu-id="eef02-183">egn #</span><span class="sxs-lookup"><span data-stu-id="eef02-183">egn#</span></span>
  
<span data-ttu-id="eef02-184">униформгражданскиномер</span><span class="sxs-lookup"><span data-stu-id="eef02-184">униформ граждански номер</span></span>
  
<span data-ttu-id="eef02-185">униформ id</span><span class="sxs-lookup"><span data-stu-id="eef02-185">униформ id</span></span>
  
<span data-ttu-id="eef02-186">униформграждански id</span><span class="sxs-lookup"><span data-stu-id="eef02-186">униформ граждански id</span></span>
  
<span data-ttu-id="eef02-187">униформгражданскине</span><span class="sxs-lookup"><span data-stu-id="eef02-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="eef02-188">克罗地亚</span><span class="sxs-lookup"><span data-stu-id="eef02-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="eef02-189">格式</span><span class="sxs-lookup"><span data-stu-id="eef02-189">Format</span></span>

<span data-ttu-id="eef02-190">11个不带空格或分隔符的数字</span><span class="sxs-lookup"><span data-stu-id="eef02-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eef02-191">模式</span><span class="sxs-lookup"><span data-stu-id="eef02-191">Pattern</span></span>

<span data-ttu-id="eef02-192">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="eef02-192">11 digits:</span></span>
  
- <span data-ttu-id="eef02-193">10个数字, 随机选择</span><span class="sxs-lookup"><span data-stu-id="eef02-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="eef02-194">一个校验位</span><span class="sxs-lookup"><span data-stu-id="eef02-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="eef02-195">校验和</span><span class="sxs-lookup"><span data-stu-id="eef02-195">Checksum</span></span>

<span data-ttu-id="eef02-196">是</span><span class="sxs-lookup"><span data-stu-id="eef02-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="eef02-197">定义</span><span class="sxs-lookup"><span data-stu-id="eef02-197">Definition</span></span>

<span data-ttu-id="eef02-198">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-199">函数`Func_croatia_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eef02-200">找到了中`Keywords_croatia_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="eef02-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="eef02-201">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-202">函数`Func_croatia_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eef02-203">关键字</span><span class="sxs-lookup"><span data-stu-id="eef02-203">Keywords</span></span>

#### <a name="keywordscroatiaeutaxfilenumber"></a><span data-ttu-id="eef02-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="eef02-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="eef02-205">税号</span><span class="sxs-lookup"><span data-stu-id="eef02-205">tax number</span></span>
  
<span data-ttu-id="eef02-206">税种</span><span class="sxs-lookup"><span data-stu-id="eef02-206">tax</span></span>
  
<span data-ttu-id="eef02-207">tax id</span><span class="sxs-lookup"><span data-stu-id="eef02-207">tax id</span></span>
  
<span data-ttu-id="eef02-208">oid</span><span class="sxs-lookup"><span data-stu-id="eef02-208">oid</span></span>
  
<span data-ttu-id="eef02-209">排列</span><span class="sxs-lookup"><span data-stu-id="eef02-209">oid#</span></span>
  
<span data-ttu-id="eef02-210">porezni broj</span><span class="sxs-lookup"><span data-stu-id="eef02-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="eef02-211">塞浦路斯</span><span class="sxs-lookup"><span data-stu-id="eef02-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="eef02-212">格式</span><span class="sxs-lookup"><span data-stu-id="eef02-212">Format</span></span>

<span data-ttu-id="eef02-213">指定模式中的八个数字和一个字母</span><span class="sxs-lookup"><span data-stu-id="eef02-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eef02-214">模式</span><span class="sxs-lookup"><span data-stu-id="eef02-214">Pattern</span></span>

<span data-ttu-id="eef02-215">八个数字和一个字母:</span><span class="sxs-lookup"><span data-stu-id="eef02-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="eef02-216">一个 "0"</span><span class="sxs-lookup"><span data-stu-id="eef02-216">A "0"</span></span> 
    
- <span data-ttu-id="eef02-217">七个数字 </span><span class="sxs-lookup"><span data-stu-id="eef02-217">Seven digits</span></span>
    
- <span data-ttu-id="eef02-218">一个字母 (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="eef02-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="eef02-219">校验和</span><span class="sxs-lookup"><span data-stu-id="eef02-219">Checksum</span></span>

<span data-ttu-id="eef02-220">不适用</span><span class="sxs-lookup"><span data-stu-id="eef02-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="eef02-221">定义</span><span class="sxs-lookup"><span data-stu-id="eef02-221">Definition</span></span>

<span data-ttu-id="eef02-222">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-223">函数`Func_cyprus_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eef02-224">找到了中`Keywords_cyprus_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="eef02-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="eef02-225">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-226">函数`Func_cyprus_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eef02-227">关键字</span><span class="sxs-lookup"><span data-stu-id="eef02-227">Keywords</span></span>

#### <a name="keywordscypruseutaxfilenumber"></a><span data-ttu-id="eef02-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="eef02-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="eef02-229">税号</span><span class="sxs-lookup"><span data-stu-id="eef02-229">tax number</span></span>
  
<span data-ttu-id="eef02-230">税种</span><span class="sxs-lookup"><span data-stu-id="eef02-230">tax</span></span>
  
<span data-ttu-id="eef02-231">tax id</span><span class="sxs-lookup"><span data-stu-id="eef02-231">tax id</span></span>
  
<span data-ttu-id="eef02-232">税标识代码</span><span class="sxs-lookup"><span data-stu-id="eef02-232">tax identification code</span></span>
  
<span data-ttu-id="eef02-233">和</span><span class="sxs-lookup"><span data-stu-id="eef02-233">tic</span></span>
  
<span data-ttu-id="eef02-234">和</span><span class="sxs-lookup"><span data-stu-id="eef02-234">tic#</span></span>
  
<span data-ttu-id="eef02-235">αριθμόςφορολογικούμητρώου</span><span class="sxs-lookup"><span data-stu-id="eef02-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="eef02-236">φορολογικήταυτότητα</span><span class="sxs-lookup"><span data-stu-id="eef02-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="eef02-237">κωδικόςφορολογικούμητρώου</span><span class="sxs-lookup"><span data-stu-id="eef02-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="eef02-238">捷克共和国</span><span class="sxs-lookup"><span data-stu-id="eef02-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="eef02-239">格式</span><span class="sxs-lookup"><span data-stu-id="eef02-239">Format</span></span>

<span data-ttu-id="eef02-240">9个或10个数字, 带可选反斜杠</span><span class="sxs-lookup"><span data-stu-id="eef02-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eef02-241">模式</span><span class="sxs-lookup"><span data-stu-id="eef02-241">Pattern</span></span>

<span data-ttu-id="eef02-242">9个或10个数字, 可选 backslashl:</span><span class="sxs-lookup"><span data-stu-id="eef02-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="eef02-243">六位数字</span><span class="sxs-lookup"><span data-stu-id="eef02-243">Six digits</span></span> 
    
- <span data-ttu-id="eef02-244">反斜杠 (可选)</span><span class="sxs-lookup"><span data-stu-id="eef02-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="eef02-245">三个或四个数字</span><span class="sxs-lookup"><span data-stu-id="eef02-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="eef02-246">校验和</span><span class="sxs-lookup"><span data-stu-id="eef02-246">Checksum</span></span>

<span data-ttu-id="eef02-247">不适用</span><span class="sxs-lookup"><span data-stu-id="eef02-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="eef02-248">定义</span><span class="sxs-lookup"><span data-stu-id="eef02-248">Definition</span></span>

<span data-ttu-id="eef02-249">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-250">正则表达式`Regex_czech_republic_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eef02-251">找到了中`Keywords_czech_republic_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="eef02-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eef02-252">关键字</span><span class="sxs-lookup"><span data-stu-id="eef02-252">Keywords</span></span>

#### <a name="keywordsczechrepubliceutaxfilenumber"></a><span data-ttu-id="eef02-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="eef02-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="eef02-254">税号</span><span class="sxs-lookup"><span data-stu-id="eef02-254">tax number</span></span>
  
<span data-ttu-id="eef02-255">税种</span><span class="sxs-lookup"><span data-stu-id="eef02-255">tax</span></span>
  
<span data-ttu-id="eef02-256">tax id</span><span class="sxs-lookup"><span data-stu-id="eef02-256">tax id</span></span>
  
<span data-ttu-id="eef02-257">个人号码</span><span class="sxs-lookup"><span data-stu-id="eef02-257">personal number</span></span>
  
<span data-ttu-id="eef02-258">daňovéčíslo</span><span class="sxs-lookup"><span data-stu-id="eef02-258">daňové číslo</span></span>
  
<span data-ttu-id="eef02-259">osobníčíslo</span><span class="sxs-lookup"><span data-stu-id="eef02-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="eef02-260">丹麦</span><span class="sxs-lookup"><span data-stu-id="eef02-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="eef02-261">格式</span><span class="sxs-lookup"><span data-stu-id="eef02-261">Format</span></span>

<span data-ttu-id="eef02-262">10个数字, 包含连字符</span><span class="sxs-lookup"><span data-stu-id="eef02-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eef02-263">模式</span><span class="sxs-lookup"><span data-stu-id="eef02-263">Pattern</span></span>

<span data-ttu-id="eef02-264">包含 hyphenl 的10个数字:</span><span class="sxs-lookup"><span data-stu-id="eef02-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="eef02-265">与出生日期对应的6个数字 (DDMMYY)</span><span class="sxs-lookup"><span data-stu-id="eef02-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="eef02-266">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="eef02-266">A hyphen</span></span>
    
- <span data-ttu-id="eef02-267">与序列号对应的四个数字, 其中第一个数字对应于出生世纪, 最后一个数字对应于个人的性别 (对于男为奇数, 甚至对于母版)</span><span class="sxs-lookup"><span data-stu-id="eef02-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="eef02-268">校验和</span><span class="sxs-lookup"><span data-stu-id="eef02-268">Checksum</span></span>

<span data-ttu-id="eef02-269">是</span><span class="sxs-lookup"><span data-stu-id="eef02-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="eef02-270">定义</span><span class="sxs-lookup"><span data-stu-id="eef02-270">Definition</span></span>

<span data-ttu-id="eef02-271">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-272">函数`Func_denmark_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eef02-273">找到了中`Keywords_denmark_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="eef02-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="eef02-274">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-275">函数`Func_denmark_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keywords_denmark_eu_tax_file_number" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eef02-276">关键字</span><span class="sxs-lookup"><span data-stu-id="eef02-276">Keywords</span></span>

#### <a name="keywordsdenmarkeutaxfilenumber"></a><span data-ttu-id="eef02-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="eef02-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="eef02-278">税号</span><span class="sxs-lookup"><span data-stu-id="eef02-278">tax number</span></span>
  
<span data-ttu-id="eef02-279">税种</span><span class="sxs-lookup"><span data-stu-id="eef02-279">tax</span></span>
  
<span data-ttu-id="eef02-280">tax id</span><span class="sxs-lookup"><span data-stu-id="eef02-280">tax id</span></span>
  
<span data-ttu-id="eef02-281">cpr 编号</span><span class="sxs-lookup"><span data-stu-id="eef02-281">cpr number</span></span>
  
<span data-ttu-id="eef02-282">cpr #</span><span class="sxs-lookup"><span data-stu-id="eef02-282">cpr#</span></span>
  
<span data-ttu-id="eef02-283">skat nummer</span><span class="sxs-lookup"><span data-stu-id="eef02-283">skat nummer</span></span>
  
<span data-ttu-id="eef02-284">skat id</span><span class="sxs-lookup"><span data-stu-id="eef02-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="eef02-285">爱沙尼亚</span><span class="sxs-lookup"><span data-stu-id="eef02-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="eef02-286">格式</span><span class="sxs-lookup"><span data-stu-id="eef02-286">Format</span></span>

<span data-ttu-id="eef02-287">11个不带空格或分隔符的数字</span><span class="sxs-lookup"><span data-stu-id="eef02-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eef02-288">模式</span><span class="sxs-lookup"><span data-stu-id="eef02-288">Pattern</span></span>

<span data-ttu-id="eef02-289">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="eef02-289">11 digits:</span></span>
  
-  <span data-ttu-id="eef02-290">一种与性别和世纪相对应的数字, 其中奇数表示男, 偶数表示女, 如下所示: 1, 2 代表19世纪;3, 4 表示20世纪;对于21世纪, 为 5, 6</span><span class="sxs-lookup"><span data-stu-id="eef02-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="eef02-291">与出生日期对应的6个数字 (YYMMDD)</span><span class="sxs-lookup"><span data-stu-id="eef02-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="eef02-292">三个数字, 对应于将出生在同一日期的人员组成的序列号</span><span class="sxs-lookup"><span data-stu-id="eef02-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="eef02-293">一个校验位</span><span class="sxs-lookup"><span data-stu-id="eef02-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="eef02-294">校验和</span><span class="sxs-lookup"><span data-stu-id="eef02-294">Checksum</span></span>

<span data-ttu-id="eef02-295">是</span><span class="sxs-lookup"><span data-stu-id="eef02-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="eef02-296">定义</span><span class="sxs-lookup"><span data-stu-id="eef02-296">Definition</span></span>

<span data-ttu-id="eef02-297">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-298">函数`Func_estonia_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eef02-299">找到了中`Keywords_estonia_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="eef02-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="eef02-300">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-301">函数`Func_estonia_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
          <Match idRef="Keywords_estonia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eef02-302">关键字</span><span class="sxs-lookup"><span data-stu-id="eef02-302">Keywords</span></span>

#### <a name="keywordsestoniaeutaxfilenumber"></a><span data-ttu-id="eef02-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="eef02-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="eef02-304">税号</span><span class="sxs-lookup"><span data-stu-id="eef02-304">tax number</span></span>
  
<span data-ttu-id="eef02-305">税种</span><span class="sxs-lookup"><span data-stu-id="eef02-305">tax</span></span>
  
<span data-ttu-id="eef02-306">tax id</span><span class="sxs-lookup"><span data-stu-id="eef02-306">tax id</span></span>
  
<span data-ttu-id="eef02-307">个人代码</span><span class="sxs-lookup"><span data-stu-id="eef02-307">personal code</span></span>
  
<span data-ttu-id="eef02-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="eef02-308">maksunumber</span></span>
  
<span data-ttu-id="eef02-309">maksu id</span><span class="sxs-lookup"><span data-stu-id="eef02-309">maksu id</span></span>
  
<span data-ttu-id="eef02-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="eef02-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="eef02-311">芬兰</span><span class="sxs-lookup"><span data-stu-id="eef02-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="eef02-312">格式</span><span class="sxs-lookup"><span data-stu-id="eef02-312">Format</span></span>

<span data-ttu-id="eef02-313">一个11字符组合的数字、字母、加号和减号</span><span class="sxs-lookup"><span data-stu-id="eef02-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eef02-314">模式</span><span class="sxs-lookup"><span data-stu-id="eef02-314">Pattern</span></span>

<span data-ttu-id="eef02-315">一个11个字符的数字、字母和加号和减号的组合:</span><span class="sxs-lookup"><span data-stu-id="eef02-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="eef02-316">六位数字</span><span class="sxs-lookup"><span data-stu-id="eef02-316">Six digits</span></span>
    
- <span data-ttu-id="eef02-317">以下之一: 加号、减号或字母 "a" (不区分大小写), 其中加号表示介于1800-1899 之间, 负号表示在1900-1999 之间, 而 "a" 表示出生2000和之后</span><span class="sxs-lookup"><span data-stu-id="eef02-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="eef02-318">三位数字</span><span class="sxs-lookup"><span data-stu-id="eef02-318">Three digits</span></span>
    
- <span data-ttu-id="eef02-319">一个字母或一个数字</span><span class="sxs-lookup"><span data-stu-id="eef02-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="eef02-320">校验和</span><span class="sxs-lookup"><span data-stu-id="eef02-320">Checksum</span></span>

<span data-ttu-id="eef02-321">是</span><span class="sxs-lookup"><span data-stu-id="eef02-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="eef02-322">定义</span><span class="sxs-lookup"><span data-stu-id="eef02-322">Definition</span></span>

<span data-ttu-id="eef02-323">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-324">函数`Func_finland_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eef02-325">找到了中`Keywords_finland_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="eef02-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="eef02-326">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-327">函数`Func_finland_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
          <Match idRef="Keywords_finland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eef02-328">关键字</span><span class="sxs-lookup"><span data-stu-id="eef02-328">Keywords</span></span>

#### <a name="keywordsfinlandeutaxfilenumber"></a><span data-ttu-id="eef02-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="eef02-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="eef02-330">identification number</span><span class="sxs-lookup"><span data-stu-id="eef02-330">identification number</span></span>
  
<span data-ttu-id="eef02-331">个人 id</span><span class="sxs-lookup"><span data-stu-id="eef02-331">personal id</span></span>
  
<span data-ttu-id="eef02-332">标识号码</span><span class="sxs-lookup"><span data-stu-id="eef02-332">identity number</span></span>
  
<span data-ttu-id="eef02-333">芬兰国家/地区 id 号</span><span class="sxs-lookup"><span data-stu-id="eef02-333">finnish national id number</span></span>
  
<span data-ttu-id="eef02-334">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="eef02-334">personalidnumber#</span></span>
  
<span data-ttu-id="eef02-335">national identification number</span><span class="sxs-lookup"><span data-stu-id="eef02-335">national identification number</span></span>
  
<span data-ttu-id="eef02-336">id 号</span><span class="sxs-lookup"><span data-stu-id="eef02-336">id number</span></span>
  
<span data-ttu-id="eef02-337">国家/地区 id 编号。</span><span class="sxs-lookup"><span data-stu-id="eef02-337">national id no.</span></span>
  
<span data-ttu-id="eef02-338">国家/地区 id 号</span><span class="sxs-lookup"><span data-stu-id="eef02-338">national id number</span></span>
  
<span data-ttu-id="eef02-339">id 号</span><span class="sxs-lookup"><span data-stu-id="eef02-339">id no</span></span>
  
<span data-ttu-id="eef02-340">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="eef02-340">tunnistenumero</span></span>
  
<span data-ttu-id="eef02-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="eef02-341">henkilötunnus</span></span>
  
<span data-ttu-id="eef02-342">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="eef02-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="eef02-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="eef02-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="eef02-344">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="eef02-344">identiteetti numero</span></span>
  
<span data-ttu-id="eef02-345">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="eef02-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="eef02-346">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="eef02-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="eef02-347">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="eef02-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="eef02-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="eef02-348">tunnusnumero</span></span>
  
<span data-ttu-id="eef02-349">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="eef02-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="eef02-350">法国</span><span class="sxs-lookup"><span data-stu-id="eef02-350">France</span></span>

### <a name="format"></a><span data-ttu-id="eef02-351">格式</span><span class="sxs-lookup"><span data-stu-id="eef02-351">Format</span></span>

<span data-ttu-id="eef02-352">13位数的个人和九个数字的实体</span><span class="sxs-lookup"><span data-stu-id="eef02-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eef02-353">模式</span><span class="sxs-lookup"><span data-stu-id="eef02-353">Pattern</span></span>

<span data-ttu-id="eef02-354">适用于个人的13个数字:</span><span class="sxs-lookup"><span data-stu-id="eef02-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="eef02-355">一个数字, 必须为0、1、2或3</span><span class="sxs-lookup"><span data-stu-id="eef02-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="eef02-356">12 个数字</span><span class="sxs-lookup"><span data-stu-id="eef02-356">12 digits</span></span>
    
<span data-ttu-id="eef02-357">9个图元数字</span><span class="sxs-lookup"><span data-stu-id="eef02-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="eef02-358">校验和</span><span class="sxs-lookup"><span data-stu-id="eef02-358">Checksum</span></span>

<span data-ttu-id="eef02-359">不适用</span><span class="sxs-lookup"><span data-stu-id="eef02-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="eef02-360">定义</span><span class="sxs-lookup"><span data-stu-id="eef02-360">Definition</span></span>

<span data-ttu-id="eef02-361">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-362">函数`Func_france_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eef02-363">找到了中`Keywords_france_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="eef02-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="eef02-364">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-365">函数`Func_france_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eef02-366">关键字</span><span class="sxs-lookup"><span data-stu-id="eef02-366">Keywords</span></span>

#### <a name="keywordsfranceeutaxfilenumber"></a><span data-ttu-id="eef02-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="eef02-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="eef02-368">税标识号</span><span class="sxs-lookup"><span data-stu-id="eef02-368">tax identification number</span></span>
  
<span data-ttu-id="eef02-369">税号</span><span class="sxs-lookup"><span data-stu-id="eef02-369">tax number</span></span>
  
<span data-ttu-id="eef02-370">tax id</span><span class="sxs-lookup"><span data-stu-id="eef02-370">tax id</span></span>
  
<span data-ttu-id="eef02-371">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="eef02-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="eef02-372">德国</span><span class="sxs-lookup"><span data-stu-id="eef02-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="eef02-373">格式</span><span class="sxs-lookup"><span data-stu-id="eef02-373">Format</span></span>

<span data-ttu-id="eef02-374">11个数字, 无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="eef02-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eef02-375">模式</span><span class="sxs-lookup"><span data-stu-id="eef02-375">Pattern</span></span>

<span data-ttu-id="eef02-376">11位数字:</span><span class="sxs-lookup"><span data-stu-id="eef02-376">11 digits :</span></span>
  
-  <span data-ttu-id="eef02-377">10位数字</span><span class="sxs-lookup"><span data-stu-id="eef02-377">Ten digits</span></span> 
    
- <span data-ttu-id="eef02-378">一个校验位</span><span class="sxs-lookup"><span data-stu-id="eef02-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="eef02-379">校验和</span><span class="sxs-lookup"><span data-stu-id="eef02-379">Checksum</span></span>

<span data-ttu-id="eef02-380">是</span><span class="sxs-lookup"><span data-stu-id="eef02-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="eef02-381">定义</span><span class="sxs-lookup"><span data-stu-id="eef02-381">Definition</span></span>

<span data-ttu-id="eef02-382">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-383">函数`Func_germany_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eef02-384">找到了中`Keywords_germany_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="eef02-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="eef02-385">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-386">函数`Func_germany_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eef02-387">关键字</span><span class="sxs-lookup"><span data-stu-id="eef02-387">Keywords</span></span>

#### <a name="keywordsgermanyeutaxfilenumber"></a><span data-ttu-id="eef02-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="eef02-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="eef02-389">税号</span><span class="sxs-lookup"><span data-stu-id="eef02-389">tax number</span></span>
  
<span data-ttu-id="eef02-390">纳税编号</span><span class="sxs-lookup"><span data-stu-id="eef02-390">tax no.</span></span>
  
<span data-ttu-id="eef02-391">taxno #</span><span class="sxs-lookup"><span data-stu-id="eef02-391">taxno#</span></span>
  
<span data-ttu-id="eef02-392">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="eef02-392">taxnumber#</span></span>
  
<span data-ttu-id="eef02-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="eef02-393">taxnumber</span></span>
  
<span data-ttu-id="eef02-394">tax id</span><span class="sxs-lookup"><span data-stu-id="eef02-394">tax id</span></span>
  
<span data-ttu-id="eef02-395">taxid #</span><span class="sxs-lookup"><span data-stu-id="eef02-395">taxid#</span></span>
  
<span data-ttu-id="eef02-396">税标识号</span><span class="sxs-lookup"><span data-stu-id="eef02-396">tax identification number</span></span>
  
<span data-ttu-id="eef02-397">税号标识号。</span><span class="sxs-lookup"><span data-stu-id="eef02-397">tax identification no.</span></span>
  
<span data-ttu-id="eef02-398">steuernummer</span><span class="sxs-lookup"><span data-stu-id="eef02-398">steuernummer</span></span>
  
<span data-ttu-id="eef02-399">steuer id</span><span class="sxs-lookup"><span data-stu-id="eef02-399">steuer id</span></span>
  
<span data-ttu-id="eef02-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="eef02-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="eef02-401">希腊</span><span class="sxs-lookup"><span data-stu-id="eef02-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="eef02-402">格式</span><span class="sxs-lookup"><span data-stu-id="eef02-402">Format</span></span>

<span data-ttu-id="eef02-403">9个数字, 不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="eef02-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eef02-404">模式</span><span class="sxs-lookup"><span data-stu-id="eef02-404">Pattern</span></span>

<span data-ttu-id="eef02-405">九个数字</span><span class="sxs-lookup"><span data-stu-id="eef02-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="eef02-406">校验和</span><span class="sxs-lookup"><span data-stu-id="eef02-406">Checksum</span></span>

<span data-ttu-id="eef02-407">不适用</span><span class="sxs-lookup"><span data-stu-id="eef02-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="eef02-408">定义</span><span class="sxs-lookup"><span data-stu-id="eef02-408">Definition</span></span>

<span data-ttu-id="eef02-409">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-410">正则表达式`Regex_greece_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eef02-411">找到了中`Keywords_greece_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="eef02-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eef02-412">关键字</span><span class="sxs-lookup"><span data-stu-id="eef02-412">Keywords</span></span>

#### <a name="keywordsgreeceeutaxfilenumber"></a><span data-ttu-id="eef02-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="eef02-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="eef02-414">afm</span><span class="sxs-lookup"><span data-stu-id="eef02-414">afm</span></span>
  
<span data-ttu-id="eef02-415">锡</span><span class="sxs-lookup"><span data-stu-id="eef02-415">tin</span></span>
  
<span data-ttu-id="eef02-416">税号编号</span><span class="sxs-lookup"><span data-stu-id="eef02-416">tax id no.</span></span>
  
<span data-ttu-id="eef02-417">税号编号</span><span class="sxs-lookup"><span data-stu-id="eef02-417">tax id no</span></span>
  
<span data-ttu-id="eef02-418">税标识号</span><span class="sxs-lookup"><span data-stu-id="eef02-418">tax identification number</span></span>
  
<span data-ttu-id="eef02-419">税务注册表号</span><span class="sxs-lookup"><span data-stu-id="eef02-419">tax registry number</span></span>
  
<span data-ttu-id="eef02-420">税务注册表号</span><span class="sxs-lookup"><span data-stu-id="eef02-420">tax registry no.</span></span>
  
<span data-ttu-id="eef02-421">afm</span><span class="sxs-lookup"><span data-stu-id="eef02-421">afm#</span></span>
  
<span data-ttu-id="eef02-422">锡</span><span class="sxs-lookup"><span data-stu-id="eef02-422">tin#</span></span>
  
<span data-ttu-id="eef02-423">taxidno #</span><span class="sxs-lookup"><span data-stu-id="eef02-423">taxidno#</span></span>
  
<span data-ttu-id="eef02-424">taxregistryno #</span><span class="sxs-lookup"><span data-stu-id="eef02-424">taxregistryno#</span></span>
  
<span data-ttu-id="eef02-425">αριθμόςφορολογικούμητρώου</span><span class="sxs-lookup"><span data-stu-id="eef02-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="eef02-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="eef02-426">aφμ</span></span>
  
<span data-ttu-id="eef02-427">aφμαριθμός</span><span class="sxs-lookup"><span data-stu-id="eef02-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="eef02-428">φορολογικούμητρώουνο。</span><span class="sxs-lookup"><span data-stu-id="eef02-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="eef02-429">τοναριθμόφορολογικούμητρώου</span><span class="sxs-lookup"><span data-stu-id="eef02-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="eef02-430">匈牙利</span><span class="sxs-lookup"><span data-stu-id="eef02-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="eef02-431">格式</span><span class="sxs-lookup"><span data-stu-id="eef02-431">Format</span></span>

<span data-ttu-id="eef02-432">10个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="eef02-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eef02-433">模式</span><span class="sxs-lookup"><span data-stu-id="eef02-433">Pattern</span></span>

<span data-ttu-id="eef02-434">10位数字:</span><span class="sxs-lookup"><span data-stu-id="eef02-434">Ten digits:</span></span>
  
-  <span data-ttu-id="eef02-435">一个必须为 "8" 的数字</span><span class="sxs-lookup"><span data-stu-id="eef02-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="eef02-436">与日期01/01/1867 之间的天数对应的五个数字和个人的出生日期</span><span class="sxs-lookup"><span data-stu-id="eef02-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="eef02-437">三个数字, 对应于通过机会区分在同一天的人所生成的数字</span><span class="sxs-lookup"><span data-stu-id="eef02-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="eef02-438">一个校验位</span><span class="sxs-lookup"><span data-stu-id="eef02-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="eef02-439">校验和</span><span class="sxs-lookup"><span data-stu-id="eef02-439">Checksum</span></span>

<span data-ttu-id="eef02-440">是</span><span class="sxs-lookup"><span data-stu-id="eef02-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="eef02-441">定义</span><span class="sxs-lookup"><span data-stu-id="eef02-441">Definition</span></span>

<span data-ttu-id="eef02-442">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-443">函数`Func_hungary_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eef02-444">找到了中`Keywords_hungary_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="eef02-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="eef02-445">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-446">函数`Func_hungary_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eef02-447">关键字</span><span class="sxs-lookup"><span data-stu-id="eef02-447">Keywords</span></span>

#### <a name="keywordshungaryeutaxfilenumber"></a><span data-ttu-id="eef02-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="eef02-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="eef02-449">匈牙利语税号标识号</span><span class="sxs-lookup"><span data-stu-id="eef02-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="eef02-450">匈牙利纳税人标识号</span><span class="sxs-lookup"><span data-stu-id="eef02-450">hungarian tin</span></span>
  
<span data-ttu-id="eef02-451">税务 id 号</span><span class="sxs-lookup"><span data-stu-id="eef02-451">tax id number</span></span>
  
<span data-ttu-id="eef02-452">vat 号码</span><span class="sxs-lookup"><span data-stu-id="eef02-452">vat number</span></span>
  
<span data-ttu-id="eef02-453">税务主管机构编号</span><span class="sxs-lookup"><span data-stu-id="eef02-453">tax authority no</span></span>
  
<span data-ttu-id="eef02-454">税号纳税标识号</span><span class="sxs-lookup"><span data-stu-id="eef02-454">tax id tax identity number</span></span>
  
<span data-ttu-id="eef02-455">taxidnumber #</span><span class="sxs-lookup"><span data-stu-id="eef02-455">taxidnumber#</span></span>
  
<span data-ttu-id="eef02-456">锡</span><span class="sxs-lookup"><span data-stu-id="eef02-456">tin#</span></span>
  
<span data-ttu-id="eef02-457">hungatiantin #</span><span class="sxs-lookup"><span data-stu-id="eef02-457">hungatiantin#</span></span>
  
<span data-ttu-id="eef02-458">税号标识编号</span><span class="sxs-lookup"><span data-stu-id="eef02-458">tax identification no</span></span>
  
<span data-ttu-id="eef02-459">taxidno #</span><span class="sxs-lookup"><span data-stu-id="eef02-459">taxidno#</span></span>
  
<span data-ttu-id="eef02-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="eef02-460">adóazonosító szám</span></span>
  
<span data-ttu-id="eef02-461">adószám</span><span class="sxs-lookup"><span data-stu-id="eef02-461">adószám</span></span>
  
<span data-ttu-id="eef02-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="eef02-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="eef02-463">Ireland</span><span class="sxs-lookup"><span data-stu-id="eef02-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="eef02-464">格式</span><span class="sxs-lookup"><span data-stu-id="eef02-464">Format</span></span>

<span data-ttu-id="eef02-465">七位数字后跟一个不带空格或分隔符的字母</span><span class="sxs-lookup"><span data-stu-id="eef02-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eef02-466">模式</span><span class="sxs-lookup"><span data-stu-id="eef02-466">Pattern</span></span>

<span data-ttu-id="eef02-467">七位数字后跟一个字母:</span><span class="sxs-lookup"><span data-stu-id="eef02-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="eef02-468">七个数字 </span><span class="sxs-lookup"><span data-stu-id="eef02-468">Seven digits</span></span> 
    
- <span data-ttu-id="eef02-469">一个字母 (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="eef02-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="eef02-470">校验和</span><span class="sxs-lookup"><span data-stu-id="eef02-470">Checksum</span></span>

<span data-ttu-id="eef02-471">不适用</span><span class="sxs-lookup"><span data-stu-id="eef02-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="eef02-472">定义</span><span class="sxs-lookup"><span data-stu-id="eef02-472">Definition</span></span>

<span data-ttu-id="eef02-473">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-474">函数`Func_ireland_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eef02-475">找到了中`Keywords_ireland_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="eef02-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="eef02-476">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-477">函数`Func_ireland_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
          <Match idRef="Keywords_ireland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eef02-478">关键字</span><span class="sxs-lookup"><span data-stu-id="eef02-478">Keywords</span></span>

#### <a name="keywordsirelandeutaxfilenumber"></a><span data-ttu-id="eef02-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="eef02-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="eef02-480">公共服务编号</span><span class="sxs-lookup"><span data-stu-id="eef02-480">public service no</span></span>
  
<span data-ttu-id="eef02-481">个人公开服务编号</span><span class="sxs-lookup"><span data-stu-id="eef02-481">personal public service no</span></span>
  
<span data-ttu-id="eef02-482">pps no</span><span class="sxs-lookup"><span data-stu-id="eef02-482">pps no</span></span>
  
<span data-ttu-id="eef02-483">个人服务编号</span><span class="sxs-lookup"><span data-stu-id="eef02-483">personal service no</span></span>
  
<span data-ttu-id="eef02-484">pps 服务否</span><span class="sxs-lookup"><span data-stu-id="eef02-484">pps service no</span></span>
  
<span data-ttu-id="eef02-485">ppsno #</span><span class="sxs-lookup"><span data-stu-id="eef02-485">ppsno#</span></span>
  
<span data-ttu-id="eef02-486">爱尔兰 pps 否</span><span class="sxs-lookup"><span data-stu-id="eef02-486">irish pps no</span></span>
  
<span data-ttu-id="eef02-487">publicserviceno #</span><span class="sxs-lookup"><span data-stu-id="eef02-487">publicserviceno#</span></span>
  
<span data-ttu-id="eef02-488">个人公开服务号码</span><span class="sxs-lookup"><span data-stu-id="eef02-488">personal public service number</span></span>
  
<span data-ttu-id="eef02-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="eef02-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="eef02-490">pps uimh</span><span class="sxs-lookup"><span data-stu-id="eef02-490">pps uimh</span></span>
  
<span data-ttu-id="eef02-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="eef02-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="eef02-492">意大利</span><span class="sxs-lookup"><span data-stu-id="eef02-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="eef02-493">格式</span><span class="sxs-lookup"><span data-stu-id="eef02-493">Format</span></span>

<span data-ttu-id="eef02-494">指定模式中的16个字母和数字</span><span class="sxs-lookup"><span data-stu-id="eef02-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eef02-495">模式</span><span class="sxs-lookup"><span data-stu-id="eef02-495">Pattern</span></span>

<span data-ttu-id="eef02-496">16个字母和数字:</span><span class="sxs-lookup"><span data-stu-id="eef02-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="eef02-497">与系列名称中的前三个辅音对应的三个字母</span><span class="sxs-lookup"><span data-stu-id="eef02-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="eef02-498">与名字中的第一个、第三个和第四个辅音对应的三个字母</span><span class="sxs-lookup"><span data-stu-id="eef02-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="eef02-499">与出生年份的最后一个数字对应的两个数字</span><span class="sxs-lookup"><span data-stu-id="eef02-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="eef02-500">一个与出生月份相对应的数字 (字母按字母顺序使用), 但仅使用字母 A 到 E、H、L、M、P、R 和 T (因此, 一月为 a, 10 月为 r)</span><span class="sxs-lookup"><span data-stu-id="eef02-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="eef02-501">两个数字, 对应于出生月份中的某一天, 其中40将添加到偶数的出生日, 以区别于奇数</span><span class="sxs-lookup"><span data-stu-id="eef02-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="eef02-502">与某人出生的 municipality 特定的区号相对应的四个数字 (国家/地区代码用于外国国家/地区)</span><span class="sxs-lookup"><span data-stu-id="eef02-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="eef02-503">一个校验位</span><span class="sxs-lookup"><span data-stu-id="eef02-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="eef02-504">校验和</span><span class="sxs-lookup"><span data-stu-id="eef02-504">Checksum</span></span>

<span data-ttu-id="eef02-505">是</span><span class="sxs-lookup"><span data-stu-id="eef02-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="eef02-506">定义</span><span class="sxs-lookup"><span data-stu-id="eef02-506">Definition</span></span>

<span data-ttu-id="eef02-507">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-508">函数`Func_italy_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eef02-509">找到了中`Keywords_italy_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="eef02-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="eef02-510">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-511">函数`Func_italy_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
          <Match idRef="Keywords_italy_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eef02-512">关键字</span><span class="sxs-lookup"><span data-stu-id="eef02-512">Keywords</span></span>

#### <a name="keywordsitalyeutaxfilenumber"></a><span data-ttu-id="eef02-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="eef02-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="eef02-514">税号</span><span class="sxs-lookup"><span data-stu-id="eef02-514">tax number</span></span>
  
<span data-ttu-id="eef02-515">纳税编号</span><span class="sxs-lookup"><span data-stu-id="eef02-515">tax no.</span></span>
  
<span data-ttu-id="eef02-516">taxno #</span><span class="sxs-lookup"><span data-stu-id="eef02-516">taxno#</span></span>
  
<span data-ttu-id="eef02-517">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="eef02-517">taxnumber#</span></span>
  
<span data-ttu-id="eef02-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="eef02-518">taxnumber</span></span>
  
<span data-ttu-id="eef02-519">tax id</span><span class="sxs-lookup"><span data-stu-id="eef02-519">tax id</span></span>
  
<span data-ttu-id="eef02-520">taxid #</span><span class="sxs-lookup"><span data-stu-id="eef02-520">taxid#</span></span>
  
<span data-ttu-id="eef02-521">会计代码</span><span class="sxs-lookup"><span data-stu-id="eef02-521">fiscal code</span></span>
  
<span data-ttu-id="eef02-522">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="eef02-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="eef02-523">拉脱维亚</span><span class="sxs-lookup"><span data-stu-id="eef02-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="eef02-524">格式</span><span class="sxs-lookup"><span data-stu-id="eef02-524">Format</span></span>

<span data-ttu-id="eef02-525">11个不带空格或分隔符的数字</span><span class="sxs-lookup"><span data-stu-id="eef02-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eef02-526">模式</span><span class="sxs-lookup"><span data-stu-id="eef02-526">Pattern</span></span>

<span data-ttu-id="eef02-527">指定模式中的11位数</span><span class="sxs-lookup"><span data-stu-id="eef02-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="eef02-528">六个数字, 对应于出生日期 (DDMMYY)</span><span class="sxs-lookup"><span data-stu-id="eef02-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="eef02-529">一个与 "出生世纪" 相对应的数字, 其中 "0" 对应于19世纪, "1" 对应于20世纪, "2" 对应于21世纪。</span><span class="sxs-lookup"><span data-stu-id="eef02-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="eef02-530">四位数字</span><span class="sxs-lookup"><span data-stu-id="eef02-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="eef02-531">校验和</span><span class="sxs-lookup"><span data-stu-id="eef02-531">Checksum</span></span>

<span data-ttu-id="eef02-532">是</span><span class="sxs-lookup"><span data-stu-id="eef02-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="eef02-533">定义</span><span class="sxs-lookup"><span data-stu-id="eef02-533">Definition</span></span>

<span data-ttu-id="eef02-534">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-535">函数`Func_latvia_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eef02-536">找到了中`Keywords_latvia_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="eef02-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="eef02-537">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-538">函数`Func_latvia_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
          <Match idRef="Keywords_latvia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eef02-539">关键字</span><span class="sxs-lookup"><span data-stu-id="eef02-539">Keywords</span></span>

#### <a name="keywordslatviaeutaxfilenumber"></a><span data-ttu-id="eef02-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="eef02-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="eef02-541">税号</span><span class="sxs-lookup"><span data-stu-id="eef02-541">tax number</span></span>
  
<span data-ttu-id="eef02-542">纳税编号</span><span class="sxs-lookup"><span data-stu-id="eef02-542">tax no.</span></span>
  
<span data-ttu-id="eef02-543">taxno #</span><span class="sxs-lookup"><span data-stu-id="eef02-543">taxno#</span></span>
  
<span data-ttu-id="eef02-544">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="eef02-544">taxnumber#</span></span>
  
<span data-ttu-id="eef02-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="eef02-545">taxnumber</span></span>
  
<span data-ttu-id="eef02-546">tax id</span><span class="sxs-lookup"><span data-stu-id="eef02-546">tax id</span></span>
  
<span data-ttu-id="eef02-547">taxid #</span><span class="sxs-lookup"><span data-stu-id="eef02-547">taxid#</span></span>
  
<span data-ttu-id="eef02-548">税标识号</span><span class="sxs-lookup"><span data-stu-id="eef02-548">tax identification number</span></span>
  
<span data-ttu-id="eef02-549">税号标识号。</span><span class="sxs-lookup"><span data-stu-id="eef02-549">tax identification no.</span></span>
  
<span data-ttu-id="eef02-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="eef02-550">nodokļa numurs</span></span>
  
<span data-ttu-id="eef02-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="eef02-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="eef02-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="eef02-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="eef02-553">立陶宛</span><span class="sxs-lookup"><span data-stu-id="eef02-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="eef02-554">格式</span><span class="sxs-lookup"><span data-stu-id="eef02-554">Format</span></span>

<span data-ttu-id="eef02-555">11位数, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="eef02-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eef02-556">模式</span><span class="sxs-lookup"><span data-stu-id="eef02-556">Pattern</span></span>

<span data-ttu-id="eef02-557">11 个数字</span><span class="sxs-lookup"><span data-stu-id="eef02-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="eef02-558">校验和</span><span class="sxs-lookup"><span data-stu-id="eef02-558">Checksum</span></span>

<span data-ttu-id="eef02-559">不适用</span><span class="sxs-lookup"><span data-stu-id="eef02-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="eef02-560">定义</span><span class="sxs-lookup"><span data-stu-id="eef02-560">Definition</span></span>

<span data-ttu-id="eef02-561">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-562">函数`Func_lithuania_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eef02-563">找到了中`Keywords_lithuania_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="eef02-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="eef02-564">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-565">函数`Func_lithuania_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eef02-566">关键字</span><span class="sxs-lookup"><span data-stu-id="eef02-566">Keywords</span></span>

#### <a name="keywordslithuaniaeutaxfilenumber"></a><span data-ttu-id="eef02-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="eef02-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="eef02-568">税号</span><span class="sxs-lookup"><span data-stu-id="eef02-568">tax number</span></span>
  
<span data-ttu-id="eef02-569">纳税编号</span><span class="sxs-lookup"><span data-stu-id="eef02-569">tax no.</span></span>
  
<span data-ttu-id="eef02-570">税号 (无 #)</span><span class="sxs-lookup"><span data-stu-id="eef02-570">tax no#</span></span>
  
<span data-ttu-id="eef02-571">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="eef02-571">taxnumber#</span></span>
  
<span data-ttu-id="eef02-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="eef02-572">taxnumber</span></span>
  
<span data-ttu-id="eef02-573">tax id</span><span class="sxs-lookup"><span data-stu-id="eef02-573">tax id</span></span>
  
<span data-ttu-id="eef02-574">taxid #</span><span class="sxs-lookup"><span data-stu-id="eef02-574">taxid#</span></span>
  
<span data-ttu-id="eef02-575">税标识号</span><span class="sxs-lookup"><span data-stu-id="eef02-575">tax identification number</span></span>
  
<span data-ttu-id="eef02-576">税号标识号。</span><span class="sxs-lookup"><span data-stu-id="eef02-576">tax identification no.</span></span>
  
<span data-ttu-id="eef02-577">mokesčių id</span><span class="sxs-lookup"><span data-stu-id="eef02-577">mokesčių id</span></span>
  
<span data-ttu-id="eef02-578">mokesčių numeris</span><span class="sxs-lookup"><span data-stu-id="eef02-578">mokesčių numeris</span></span>
  
<span data-ttu-id="eef02-579">mokesčių identifikavimas numeris</span><span class="sxs-lookup"><span data-stu-id="eef02-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="eef02-580">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="eef02-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="eef02-581">格式</span><span class="sxs-lookup"><span data-stu-id="eef02-581">Format</span></span>

<span data-ttu-id="eef02-582">13个不带空格或分隔符的数字</span><span class="sxs-lookup"><span data-stu-id="eef02-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eef02-583">模式</span><span class="sxs-lookup"><span data-stu-id="eef02-583">Pattern</span></span>

<span data-ttu-id="eef02-584">13 个数字：</span><span class="sxs-lookup"><span data-stu-id="eef02-584">13 digits:</span></span>
  
-  <span data-ttu-id="eef02-585">11 个数字</span><span class="sxs-lookup"><span data-stu-id="eef02-585">11 digits</span></span> 
    
- <span data-ttu-id="eef02-586">两个校验位</span><span class="sxs-lookup"><span data-stu-id="eef02-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="eef02-587">校验和</span><span class="sxs-lookup"><span data-stu-id="eef02-587">Checksum</span></span>

<span data-ttu-id="eef02-588">是</span><span class="sxs-lookup"><span data-stu-id="eef02-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="eef02-589">定义</span><span class="sxs-lookup"><span data-stu-id="eef02-589">Definition</span></span>

<span data-ttu-id="eef02-590">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-591">函数`Func_luxemburg_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eef02-592">找到了中`Keywords_luxemburg_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="eef02-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="eef02-593">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-594">函数`Func_luxemburg_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eef02-595">关键字</span><span class="sxs-lookup"><span data-stu-id="eef02-595">Keywords</span></span>

#### <a name="keywordsluxemburgeutaxfilenumber"></a><span data-ttu-id="eef02-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="eef02-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="eef02-597">税号</span><span class="sxs-lookup"><span data-stu-id="eef02-597">tax number</span></span>
  
<span data-ttu-id="eef02-598">纳税编号</span><span class="sxs-lookup"><span data-stu-id="eef02-598">tax no.</span></span>
  
<span data-ttu-id="eef02-599">taxno #</span><span class="sxs-lookup"><span data-stu-id="eef02-599">taxno#</span></span>
  
<span data-ttu-id="eef02-600">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="eef02-600">taxnumber#</span></span>
  
<span data-ttu-id="eef02-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="eef02-601">taxnumber</span></span>
  
<span data-ttu-id="eef02-602">tax id</span><span class="sxs-lookup"><span data-stu-id="eef02-602">tax id</span></span>
  
<span data-ttu-id="eef02-603">taxid #</span><span class="sxs-lookup"><span data-stu-id="eef02-603">taxid#</span></span>
  
<span data-ttu-id="eef02-604">税标识号</span><span class="sxs-lookup"><span data-stu-id="eef02-604">tax identification number</span></span>
  
<span data-ttu-id="eef02-605">税号标识号。</span><span class="sxs-lookup"><span data-stu-id="eef02-605">tax identification no.</span></span>
  
<span data-ttu-id="eef02-606">steuernummer</span><span class="sxs-lookup"><span data-stu-id="eef02-606">steuernummer</span></span>
  
<span data-ttu-id="eef02-607">steuer id</span><span class="sxs-lookup"><span data-stu-id="eef02-607">steuer id</span></span>
  
<span data-ttu-id="eef02-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="eef02-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="eef02-609">Malta（马耳他）</span><span class="sxs-lookup"><span data-stu-id="eef02-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="eef02-610">格式</span><span class="sxs-lookup"><span data-stu-id="eef02-610">Format</span></span>

<span data-ttu-id="eef02-611">对于马耳他 nationals: 7 位数和指定模式中的一个字母</span><span class="sxs-lookup"><span data-stu-id="eef02-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="eef02-612">非马耳他语 nationals 和马耳他语实体: 9 个数字</span><span class="sxs-lookup"><span data-stu-id="eef02-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eef02-613">模式</span><span class="sxs-lookup"><span data-stu-id="eef02-613">Pattern</span></span>

<span data-ttu-id="eef02-614">马耳他 nationals: 7 个数字和一个字母</span><span class="sxs-lookup"><span data-stu-id="eef02-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="eef02-615">七个数字 </span><span class="sxs-lookup"><span data-stu-id="eef02-615">Seven digits</span></span> 
    
- <span data-ttu-id="eef02-616">一个字母 (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="eef02-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="eef02-617">非马耳他语 nationals 和马耳他语实体: 9 个数字</span><span class="sxs-lookup"><span data-stu-id="eef02-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="eef02-618">九个数字</span><span class="sxs-lookup"><span data-stu-id="eef02-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="eef02-619">校验和</span><span class="sxs-lookup"><span data-stu-id="eef02-619">Checksum</span></span>

<span data-ttu-id="eef02-620">不适用</span><span class="sxs-lookup"><span data-stu-id="eef02-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="eef02-621">定义</span><span class="sxs-lookup"><span data-stu-id="eef02-621">Definition</span></span>

<span data-ttu-id="eef02-622">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-623">函数`Func_malta_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eef02-624">找到了中`Keywords_malta_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="eef02-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="eef02-625">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-626">函数`Func_malta_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eef02-627">关键字</span><span class="sxs-lookup"><span data-stu-id="eef02-627">Keywords</span></span>

#### <a name="keywordsmaltaeutaxfilenumber"></a><span data-ttu-id="eef02-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="eef02-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="eef02-629">税号</span><span class="sxs-lookup"><span data-stu-id="eef02-629">tax number</span></span>
  
<span data-ttu-id="eef02-630">纳税编号</span><span class="sxs-lookup"><span data-stu-id="eef02-630">tax no.</span></span>
  
<span data-ttu-id="eef02-631">taxno #</span><span class="sxs-lookup"><span data-stu-id="eef02-631">taxno#</span></span>
  
<span data-ttu-id="eef02-632">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="eef02-632">taxnumber#</span></span>
  
<span data-ttu-id="eef02-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="eef02-633">taxnumber</span></span>
  
<span data-ttu-id="eef02-634">tax id</span><span class="sxs-lookup"><span data-stu-id="eef02-634">tax id</span></span>
  
<span data-ttu-id="eef02-635">taxid #</span><span class="sxs-lookup"><span data-stu-id="eef02-635">taxid#</span></span>
  
<span data-ttu-id="eef02-636">税标识号</span><span class="sxs-lookup"><span data-stu-id="eef02-636">tax identification number</span></span>
  
<span data-ttu-id="eef02-637">税号标识号。</span><span class="sxs-lookup"><span data-stu-id="eef02-637">tax identification no.</span></span>
  
<span data-ttu-id="eef02-638">numru tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="eef02-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="eef02-639">id tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="eef02-639">id tat-taxxa</span></span>
  
<span data-ttu-id="eef02-640">numru ta "identifikazzjoni tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="eef02-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="eef02-641">荷兰</span><span class="sxs-lookup"><span data-stu-id="eef02-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="eef02-642">格式</span><span class="sxs-lookup"><span data-stu-id="eef02-642">Format</span></span>

<span data-ttu-id="eef02-643">9个数字, 不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="eef02-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eef02-644">模式</span><span class="sxs-lookup"><span data-stu-id="eef02-644">Pattern</span></span>

<span data-ttu-id="eef02-645">九个数字</span><span class="sxs-lookup"><span data-stu-id="eef02-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="eef02-646">校验和</span><span class="sxs-lookup"><span data-stu-id="eef02-646">Checksum</span></span>

<span data-ttu-id="eef02-647">是</span><span class="sxs-lookup"><span data-stu-id="eef02-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="eef02-648">定义</span><span class="sxs-lookup"><span data-stu-id="eef02-648">Definition</span></span>

<span data-ttu-id="eef02-649">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-650">函数`Func_netherlands_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eef02-651">找到了中`Keywords_netherlands_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="eef02-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="eef02-652">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-653">函数`Func_netherlands_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eef02-654">关键字</span><span class="sxs-lookup"><span data-stu-id="eef02-654">Keywords</span></span>

#### <a name="keywordsnetherlandseutaxfilenumber"></a><span data-ttu-id="eef02-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="eef02-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="eef02-656">荷兰税标识号</span><span class="sxs-lookup"><span data-stu-id="eef02-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="eef02-657">荷兰税务标识</span><span class="sxs-lookup"><span data-stu-id="eef02-657">netherlands tax identification</span></span>
  
<span data-ttu-id="eef02-658">netherland 的税标识号</span><span class="sxs-lookup"><span data-stu-id="eef02-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="eef02-659">netherland 的税标识</span><span class="sxs-lookup"><span data-stu-id="eef02-659">netherland's tax identification</span></span>
  
<span data-ttu-id="eef02-660">税标识号</span><span class="sxs-lookup"><span data-stu-id="eef02-660">tax identification number</span></span>
  
<span data-ttu-id="eef02-661">荷兰税号</span><span class="sxs-lookup"><span data-stu-id="eef02-661">dutch tax id</span></span>
  
<span data-ttu-id="eef02-662">荷兰纳税标识号</span><span class="sxs-lookup"><span data-stu-id="eef02-662">dutch tax identification number</span></span>
  
<span data-ttu-id="eef02-663">tax id</span><span class="sxs-lookup"><span data-stu-id="eef02-663">tax id</span></span>
  
<span data-ttu-id="eef02-664">税号 #</span><span class="sxs-lookup"><span data-stu-id="eef02-664">tax id#</span></span>
  
<span data-ttu-id="eef02-665">税号</span><span class="sxs-lookup"><span data-stu-id="eef02-665">tax number</span></span>
  
<span data-ttu-id="eef02-666">税号 (无 #)</span><span class="sxs-lookup"><span data-stu-id="eef02-666">tax no#</span></span>
  
<span data-ttu-id="eef02-667">税种</span><span class="sxs-lookup"><span data-stu-id="eef02-667">tax#</span></span>
  
<span data-ttu-id="eef02-668">锡</span><span class="sxs-lookup"><span data-stu-id="eef02-668">tin</span></span>
  
<span data-ttu-id="eef02-669">锡</span><span class="sxs-lookup"><span data-stu-id="eef02-669">tin#</span></span>
  
<span data-ttu-id="eef02-670">荷属安的纳税人标识号</span><span class="sxs-lookup"><span data-stu-id="eef02-670">netherlands tin</span></span>
  
<span data-ttu-id="eef02-671">netherland 的纳税人标识号</span><span class="sxs-lookup"><span data-stu-id="eef02-671">netherland's tin</span></span>
  
<span data-ttu-id="eef02-672">荷兰语 belasting identificatienummer</span><span class="sxs-lookup"><span data-stu-id="eef02-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="eef02-673">identificatienummer van belasting</span><span class="sxs-lookup"><span data-stu-id="eef02-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="eef02-674">identificatienummer belasting</span><span class="sxs-lookup"><span data-stu-id="eef02-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="eef02-675">荷兰语 belasting identificatie</span><span class="sxs-lookup"><span data-stu-id="eef02-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="eef02-676">荷兰语 belasting id nummer</span><span class="sxs-lookup"><span data-stu-id="eef02-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="eef02-677">荷兰语 belastingnummer</span><span class="sxs-lookup"><span data-stu-id="eef02-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="eef02-678">btw nummer</span><span class="sxs-lookup"><span data-stu-id="eef02-678">btw nummer</span></span>
  
<span data-ttu-id="eef02-679">nederlandse belasting identificatie</span><span class="sxs-lookup"><span data-stu-id="eef02-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="eef02-680">波兰</span><span class="sxs-lookup"><span data-stu-id="eef02-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="eef02-681">格式</span><span class="sxs-lookup"><span data-stu-id="eef02-681">Format</span></span>

<span data-ttu-id="eef02-682">不带空格或分隔符的11个数字</span><span class="sxs-lookup"><span data-stu-id="eef02-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eef02-683">模式</span><span class="sxs-lookup"><span data-stu-id="eef02-683">Pattern</span></span>

<span data-ttu-id="eef02-684">11位数字</span><span class="sxs-lookup"><span data-stu-id="eef02-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="eef02-685">校验和</span><span class="sxs-lookup"><span data-stu-id="eef02-685">Checksum</span></span>

<span data-ttu-id="eef02-686">是</span><span class="sxs-lookup"><span data-stu-id="eef02-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="eef02-687">定义</span><span class="sxs-lookup"><span data-stu-id="eef02-687">Definition</span></span>

<span data-ttu-id="eef02-688">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-689">函数`Func_poland_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eef02-690">找到了中`Keywords_poland_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="eef02-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="eef02-691">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-692">函数`Func_poland_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eef02-693">关键字</span><span class="sxs-lookup"><span data-stu-id="eef02-693">Keywords</span></span>

#### <a name="keywordspolandeutaxfilenumber"></a><span data-ttu-id="eef02-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="eef02-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="eef02-695">税号</span><span class="sxs-lookup"><span data-stu-id="eef02-695">tax number</span></span>
  
<span data-ttu-id="eef02-696">纳税编号</span><span class="sxs-lookup"><span data-stu-id="eef02-696">tax no.</span></span>
  
<span data-ttu-id="eef02-697">taxno #</span><span class="sxs-lookup"><span data-stu-id="eef02-697">taxno#</span></span>
  
<span data-ttu-id="eef02-698">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="eef02-698">taxnumber#</span></span>
  
<span data-ttu-id="eef02-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="eef02-699">taxnumber</span></span>
  
<span data-ttu-id="eef02-700">nip</span><span class="sxs-lookup"><span data-stu-id="eef02-700">nip</span></span>
  
<span data-ttu-id="eef02-701">nip #</span><span class="sxs-lookup"><span data-stu-id="eef02-701">nip#</span></span>
  
<span data-ttu-id="eef02-702">tax id</span><span class="sxs-lookup"><span data-stu-id="eef02-702">tax id</span></span>
  
<span data-ttu-id="eef02-703">税号 #</span><span class="sxs-lookup"><span data-stu-id="eef02-703">tax id#</span></span>
  
<span data-ttu-id="eef02-704">nip id</span><span class="sxs-lookup"><span data-stu-id="eef02-704">nip id</span></span>
  
<span data-ttu-id="eef02-705">nip id #</span><span class="sxs-lookup"><span data-stu-id="eef02-705">nip id#</span></span>
  
<span data-ttu-id="eef02-706">税标识号</span><span class="sxs-lookup"><span data-stu-id="eef02-706">tax identification number</span></span>
  
<span data-ttu-id="eef02-707">税号标识号。</span><span class="sxs-lookup"><span data-stu-id="eef02-707">tax identification no.</span></span>
  
<span data-ttu-id="eef02-708">vat 号码</span><span class="sxs-lookup"><span data-stu-id="eef02-708">vat number</span></span>
  
<span data-ttu-id="eef02-709">vat 编号</span><span class="sxs-lookup"><span data-stu-id="eef02-709">vat no.</span></span>
  
<span data-ttu-id="eef02-710">vatno #</span><span class="sxs-lookup"><span data-stu-id="eef02-710">vatno#</span></span>
  
<span data-ttu-id="eef02-711">vat id</span><span class="sxs-lookup"><span data-stu-id="eef02-711">vat id</span></span>
  
<span data-ttu-id="eef02-712">vat id #</span><span class="sxs-lookup"><span data-stu-id="eef02-712">vat id#</span></span>
  
<span data-ttu-id="eef02-713">器 identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="eef02-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="eef02-714">polski 器 identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="eef02-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="eef02-715">numeridentyfikacjipodatkowej #</span><span class="sxs-lookup"><span data-stu-id="eef02-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="eef02-716">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="eef02-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="eef02-717">格式</span><span class="sxs-lookup"><span data-stu-id="eef02-717">Format</span></span>

<span data-ttu-id="eef02-718">9个不带空格或分隔符的数字</span><span class="sxs-lookup"><span data-stu-id="eef02-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eef02-719">模式</span><span class="sxs-lookup"><span data-stu-id="eef02-719">Pattern</span></span>

<span data-ttu-id="eef02-720">九个数字</span><span class="sxs-lookup"><span data-stu-id="eef02-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="eef02-721">校验和</span><span class="sxs-lookup"><span data-stu-id="eef02-721">Checksum</span></span>

<span data-ttu-id="eef02-722">是</span><span class="sxs-lookup"><span data-stu-id="eef02-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="eef02-723">定义</span><span class="sxs-lookup"><span data-stu-id="eef02-723">Definition</span></span>

<span data-ttu-id="eef02-724">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-725">函数`Func_portugal_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eef02-726">找到了中`Keywords_portugal_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="eef02-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="eef02-727">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-728">函数`Func_portugal_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eef02-729">关键字</span><span class="sxs-lookup"><span data-stu-id="eef02-729">Keywords</span></span>

#### <a name="keywordsportugaleutaxfilenumber"></a><span data-ttu-id="eef02-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="eef02-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="eef02-731">税号</span><span class="sxs-lookup"><span data-stu-id="eef02-731">tax number</span></span>
  
<span data-ttu-id="eef02-732">纳税编号</span><span class="sxs-lookup"><span data-stu-id="eef02-732">tax no.</span></span>
  
<span data-ttu-id="eef02-733">taxno #</span><span class="sxs-lookup"><span data-stu-id="eef02-733">taxno#</span></span>
  
<span data-ttu-id="eef02-734">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="eef02-734">taxnumber#</span></span>
  
<span data-ttu-id="eef02-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="eef02-735">taxnumber</span></span>
  
<span data-ttu-id="eef02-736">\n\n</span><span class="sxs-lookup"><span data-stu-id="eef02-736">nif</span></span>
  
<span data-ttu-id="eef02-737">\n\n</span><span class="sxs-lookup"><span data-stu-id="eef02-737">nif#</span></span>
  
<span data-ttu-id="eef02-738">numero 会计</span><span class="sxs-lookup"><span data-stu-id="eef02-738">numero fiscal</span></span>
  
<span data-ttu-id="eef02-739">número de identificação 会计</span><span class="sxs-lookup"><span data-stu-id="eef02-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="eef02-740">罗马尼亚</span><span class="sxs-lookup"><span data-stu-id="eef02-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="eef02-741">格式</span><span class="sxs-lookup"><span data-stu-id="eef02-741">Format</span></span>

<span data-ttu-id="eef02-742">13个不带空格或分隔符的数字</span><span class="sxs-lookup"><span data-stu-id="eef02-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eef02-743">模式</span><span class="sxs-lookup"><span data-stu-id="eef02-743">Pattern</span></span>

<span data-ttu-id="eef02-744">13 位数字</span><span class="sxs-lookup"><span data-stu-id="eef02-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="eef02-745">校验和</span><span class="sxs-lookup"><span data-stu-id="eef02-745">Checksum</span></span>

<span data-ttu-id="eef02-746">不适用</span><span class="sxs-lookup"><span data-stu-id="eef02-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="eef02-747">定义</span><span class="sxs-lookup"><span data-stu-id="eef02-747">Definition</span></span>

<span data-ttu-id="eef02-748">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-749">正则表达式`Regex_romania_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eef02-750">找到了中`Keywords_romania_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="eef02-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eef02-751">关键字</span><span class="sxs-lookup"><span data-stu-id="eef02-751">Keywords</span></span>

#### <a name="keywordsromaniaeutaxfilenumber"></a><span data-ttu-id="eef02-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="eef02-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="eef02-753">tax id</span><span class="sxs-lookup"><span data-stu-id="eef02-753">tax id</span></span>
  
<span data-ttu-id="eef02-754">税务 id 号</span><span class="sxs-lookup"><span data-stu-id="eef02-754">tax id number</span></span>
  
<span data-ttu-id="eef02-755">税文件编号</span><span class="sxs-lookup"><span data-stu-id="eef02-755">tax file no</span></span>
  
<span data-ttu-id="eef02-756">tax file number</span><span class="sxs-lookup"><span data-stu-id="eef02-756">tax file number</span></span>
  
<span data-ttu-id="eef02-757">免税</span><span class="sxs-lookup"><span data-stu-id="eef02-757">tax no</span></span>
  
<span data-ttu-id="eef02-758">税号</span><span class="sxs-lookup"><span data-stu-id="eef02-758">tax number</span></span>
  
<span data-ttu-id="eef02-759">taxid #</span><span class="sxs-lookup"><span data-stu-id="eef02-759">taxid#</span></span>
  
<span data-ttu-id="eef02-760">taxno #</span><span class="sxs-lookup"><span data-stu-id="eef02-760">taxno#</span></span>
  
<span data-ttu-id="eef02-761">id-ul taxei</span><span class="sxs-lookup"><span data-stu-id="eef02-761">id-ul taxei</span></span>
  
<span data-ttu-id="eef02-762">numărul de identificare fiscală</span><span class="sxs-lookup"><span data-stu-id="eef02-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="eef02-763">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="eef02-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="eef02-764">格式</span><span class="sxs-lookup"><span data-stu-id="eef02-764">Format</span></span>

<span data-ttu-id="eef02-765">10个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="eef02-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eef02-766">模式</span><span class="sxs-lookup"><span data-stu-id="eef02-766">Pattern</span></span>

<span data-ttu-id="eef02-767">10 个数字</span><span class="sxs-lookup"><span data-stu-id="eef02-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="eef02-768">校验和</span><span class="sxs-lookup"><span data-stu-id="eef02-768">Checksum</span></span>

<span data-ttu-id="eef02-769">不适用</span><span class="sxs-lookup"><span data-stu-id="eef02-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="eef02-770">定义</span><span class="sxs-lookup"><span data-stu-id="eef02-770">Definition</span></span>

<span data-ttu-id="eef02-771">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-772">正则表达式`Regex_slovakia_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eef02-773">找到了中`Keywords_slovakia_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="eef02-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eef02-774">关键字</span><span class="sxs-lookup"><span data-stu-id="eef02-774">Keywords</span></span>

#### <a name="keywordsslovakiaeutaxfilenumber"></a><span data-ttu-id="eef02-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="eef02-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="eef02-776">tax id</span><span class="sxs-lookup"><span data-stu-id="eef02-776">tax id</span></span>
  
<span data-ttu-id="eef02-777">税务 id 号</span><span class="sxs-lookup"><span data-stu-id="eef02-777">tax id number</span></span>
  
<span data-ttu-id="eef02-778">纳税人 id</span><span class="sxs-lookup"><span data-stu-id="eef02-778">tin id</span></span>
  
<span data-ttu-id="eef02-779">tin 编号</span><span class="sxs-lookup"><span data-stu-id="eef02-779">tin no</span></span>
  
<span data-ttu-id="eef02-780">斯洛伐克纳税人标识号 id</span><span class="sxs-lookup"><span data-stu-id="eef02-780">slovakian tin id</span></span>
  
<span data-ttu-id="eef02-781">锡</span><span class="sxs-lookup"><span data-stu-id="eef02-781">tin</span></span>
  
<span data-ttu-id="eef02-782">税文件编号</span><span class="sxs-lookup"><span data-stu-id="eef02-782">tax file no</span></span>
  
<span data-ttu-id="eef02-783">tax file number</span><span class="sxs-lookup"><span data-stu-id="eef02-783">tax file number</span></span>
  
<span data-ttu-id="eef02-784">免税</span><span class="sxs-lookup"><span data-stu-id="eef02-784">tax no</span></span>
  
<span data-ttu-id="eef02-785">税号</span><span class="sxs-lookup"><span data-stu-id="eef02-785">tax number</span></span>
  
<span data-ttu-id="eef02-786">taxid #</span><span class="sxs-lookup"><span data-stu-id="eef02-786">taxid#</span></span>
  
<span data-ttu-id="eef02-787">taxno #</span><span class="sxs-lookup"><span data-stu-id="eef02-787">taxno#</span></span>
  
<span data-ttu-id="eef02-788">daňové identifikačnéčíslo</span><span class="sxs-lookup"><span data-stu-id="eef02-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="eef02-789">daňovéčíslo</span><span class="sxs-lookup"><span data-stu-id="eef02-789">daňové číslo</span></span>
  
<span data-ttu-id="eef02-790">daňovéčíslo súboru</span><span class="sxs-lookup"><span data-stu-id="eef02-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="eef02-791">斯洛文尼亚</span><span class="sxs-lookup"><span data-stu-id="eef02-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="eef02-792">格式</span><span class="sxs-lookup"><span data-stu-id="eef02-792">Format</span></span>

<span data-ttu-id="eef02-793">8位数, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="eef02-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eef02-794">模式</span><span class="sxs-lookup"><span data-stu-id="eef02-794">Pattern</span></span>

<span data-ttu-id="eef02-795">八个数字</span><span class="sxs-lookup"><span data-stu-id="eef02-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="eef02-796">校验和</span><span class="sxs-lookup"><span data-stu-id="eef02-796">Checksum</span></span>

<span data-ttu-id="eef02-797">是</span><span class="sxs-lookup"><span data-stu-id="eef02-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="eef02-798">定义</span><span class="sxs-lookup"><span data-stu-id="eef02-798">Definition</span></span>

<span data-ttu-id="eef02-799">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-800">函数`Func_slovenia_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eef02-801">找到了中`Keywords_slovenia_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="eef02-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="eef02-802">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-803">函数`Func_slovenia_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_nation_eu_tax_file_number" />
          <Match idRef="Keywords_nation_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eef02-804">关键字</span><span class="sxs-lookup"><span data-stu-id="eef02-804">Keywords</span></span>

#### <a name="keywordssloveniaeutaxfilenumber"></a><span data-ttu-id="eef02-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="eef02-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="eef02-806">tax id</span><span class="sxs-lookup"><span data-stu-id="eef02-806">tax id</span></span>
  
<span data-ttu-id="eef02-807">税务 id 号</span><span class="sxs-lookup"><span data-stu-id="eef02-807">tax id number</span></span>
  
<span data-ttu-id="eef02-808">纳税人 id</span><span class="sxs-lookup"><span data-stu-id="eef02-808">tin id</span></span>
  
<span data-ttu-id="eef02-809">tin 编号</span><span class="sxs-lookup"><span data-stu-id="eef02-809">tin no</span></span>
  
<span data-ttu-id="eef02-810">斯洛文尼亚纳税人标识号 id</span><span class="sxs-lookup"><span data-stu-id="eef02-810">slovenian tin id</span></span>
  
<span data-ttu-id="eef02-811">锡</span><span class="sxs-lookup"><span data-stu-id="eef02-811">tin</span></span>
  
<span data-ttu-id="eef02-812">税文件编号</span><span class="sxs-lookup"><span data-stu-id="eef02-812">tax file no</span></span>
  
<span data-ttu-id="eef02-813">tax file number</span><span class="sxs-lookup"><span data-stu-id="eef02-813">tax file number</span></span>
  
<span data-ttu-id="eef02-814">免税</span><span class="sxs-lookup"><span data-stu-id="eef02-814">tax no</span></span>
  
<span data-ttu-id="eef02-815">税号</span><span class="sxs-lookup"><span data-stu-id="eef02-815">tax number</span></span>
  
<span data-ttu-id="eef02-816">taxid #</span><span class="sxs-lookup"><span data-stu-id="eef02-816">taxid#</span></span>
  
<span data-ttu-id="eef02-817">taxno #</span><span class="sxs-lookup"><span data-stu-id="eef02-817">taxno#</span></span>
  
<span data-ttu-id="eef02-818">identifikacijska številka davka</span><span class="sxs-lookup"><span data-stu-id="eef02-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="eef02-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="eef02-819">davčna številka</span></span>
  
<span data-ttu-id="eef02-820">številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="eef02-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="eef02-821">西班牙</span><span class="sxs-lookup"><span data-stu-id="eef02-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="eef02-822">格式</span><span class="sxs-lookup"><span data-stu-id="eef02-822">Format</span></span>

<span data-ttu-id="eef02-823">七个或8个数字以及指定模式中的一个或两个字母</span><span class="sxs-lookup"><span data-stu-id="eef02-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eef02-824">模式</span><span class="sxs-lookup"><span data-stu-id="eef02-824">Pattern</span></span>

<span data-ttu-id="eef02-825">具有西班牙国家标识卡片的西班牙语自然人:</span><span class="sxs-lookup"><span data-stu-id="eef02-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="eef02-826">八个数字</span><span class="sxs-lookup"><span data-stu-id="eef02-826">Eight digits</span></span> 
    
- <span data-ttu-id="eef02-827">一个大写字母 (区分大小写)</span><span class="sxs-lookup"><span data-stu-id="eef02-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="eef02-828">不包含西班牙国家的非居民 Spaniards 国家标识卡片</span><span class="sxs-lookup"><span data-stu-id="eef02-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="eef02-829">一个大写字母 "L" (区分大小写)</span><span class="sxs-lookup"><span data-stu-id="eef02-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="eef02-830">七个数字 </span><span class="sxs-lookup"><span data-stu-id="eef02-830">Seven digits</span></span>
    
- <span data-ttu-id="eef02-831">一个大写字母 (区分大小写)</span><span class="sxs-lookup"><span data-stu-id="eef02-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="eef02-832">在没有西班牙国内身份证的14年年龄下的居民 Spaniards:</span><span class="sxs-lookup"><span data-stu-id="eef02-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="eef02-833">一个大写字母 "K" (区分大小写)</span><span class="sxs-lookup"><span data-stu-id="eef02-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="eef02-834">七个数字 </span><span class="sxs-lookup"><span data-stu-id="eef02-834">Seven digits</span></span> 
    
- <span data-ttu-id="eef02-835">一个大写字母 (区分大小写)</span><span class="sxs-lookup"><span data-stu-id="eef02-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="eef02-836">带有 Foreigner 标识号的 Foreigners</span><span class="sxs-lookup"><span data-stu-id="eef02-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="eef02-837">一个大写的字母, 为 "X"、"Y" 或 "Z" (区分大小写)</span><span class="sxs-lookup"><span data-stu-id="eef02-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="eef02-838">七个数字 </span><span class="sxs-lookup"><span data-stu-id="eef02-838">Seven digits</span></span>
    
- <span data-ttu-id="eef02-839">一个大写字母 (区分大小写)</span><span class="sxs-lookup"><span data-stu-id="eef02-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="eef02-840">没有 Foreigner 标识号的 Foreigners</span><span class="sxs-lookup"><span data-stu-id="eef02-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="eef02-841">一个大写的字母 "M" (区分大小写)</span><span class="sxs-lookup"><span data-stu-id="eef02-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="eef02-842">七个数字 </span><span class="sxs-lookup"><span data-stu-id="eef02-842">Seven digits</span></span>
    
- <span data-ttu-id="eef02-843">一个大写字母 (区分大小写)</span><span class="sxs-lookup"><span data-stu-id="eef02-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="eef02-844">校验和</span><span class="sxs-lookup"><span data-stu-id="eef02-844">Checksum</span></span>

<span data-ttu-id="eef02-845">是</span><span class="sxs-lookup"><span data-stu-id="eef02-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="eef02-846">定义</span><span class="sxs-lookup"><span data-stu-id="eef02-846">Definition</span></span>

<span data-ttu-id="eef02-847">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-848">函数`Func_spain_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eef02-849">找到了中`Keywords_spain_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="eef02-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="eef02-850">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-851">函数`Func_spain_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eef02-852">关键字</span><span class="sxs-lookup"><span data-stu-id="eef02-852">Keywords</span></span>

#### <a name="keywordsspaineutaxfilenumber"></a><span data-ttu-id="eef02-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="eef02-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="eef02-854">tax id</span><span class="sxs-lookup"><span data-stu-id="eef02-854">tax id</span></span>
  
<span data-ttu-id="eef02-855">税务 id 号</span><span class="sxs-lookup"><span data-stu-id="eef02-855">tax id number</span></span>
  
<span data-ttu-id="eef02-856">cif id</span><span class="sxs-lookup"><span data-stu-id="eef02-856">cif id</span></span>
  
<span data-ttu-id="eef02-857">cif no</span><span class="sxs-lookup"><span data-stu-id="eef02-857">cif no</span></span>
  
<span data-ttu-id="eef02-858">西班牙语 cif id</span><span class="sxs-lookup"><span data-stu-id="eef02-858">spanish cif id</span></span>
  
<span data-ttu-id="eef02-859">cif</span><span class="sxs-lookup"><span data-stu-id="eef02-859">cif</span></span>
  
<span data-ttu-id="eef02-860">税文件编号</span><span class="sxs-lookup"><span data-stu-id="eef02-860">tax file no</span></span>
  
<span data-ttu-id="eef02-861">西班牙语 cif 号码</span><span class="sxs-lookup"><span data-stu-id="eef02-861">spanish cif number</span></span>
  
<span data-ttu-id="eef02-862">tax file number</span><span class="sxs-lookup"><span data-stu-id="eef02-862">tax file number</span></span>
  
<span data-ttu-id="eef02-863">西班牙语 cif no</span><span class="sxs-lookup"><span data-stu-id="eef02-863">spanish cif no</span></span>
  
<span data-ttu-id="eef02-864">免税</span><span class="sxs-lookup"><span data-stu-id="eef02-864">tax no</span></span>
  
<span data-ttu-id="eef02-865">税号</span><span class="sxs-lookup"><span data-stu-id="eef02-865">tax number</span></span>
  
<span data-ttu-id="eef02-866">taxid #</span><span class="sxs-lookup"><span data-stu-id="eef02-866">taxid#</span></span>
  
<span data-ttu-id="eef02-867">taxno #</span><span class="sxs-lookup"><span data-stu-id="eef02-867">taxno#</span></span>
  
<span data-ttu-id="eef02-868">cifid #</span><span class="sxs-lookup"><span data-stu-id="eef02-868">cifid#</span></span>
  
<span data-ttu-id="eef02-869">spanishcifid #</span><span class="sxs-lookup"><span data-stu-id="eef02-869">spanishcifid#</span></span>
  
<span data-ttu-id="eef02-870">spanishcifno #</span><span class="sxs-lookup"><span data-stu-id="eef02-870">spanishcifno#</span></span>
  
<span data-ttu-id="eef02-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="eef02-871">número de contribuyente</span></span>
  
<span data-ttu-id="eef02-872">número de impuesto corporativo</span><span class="sxs-lookup"><span data-stu-id="eef02-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="eef02-873">número de identificación 会计</span><span class="sxs-lookup"><span data-stu-id="eef02-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="eef02-874">cif número</span><span class="sxs-lookup"><span data-stu-id="eef02-874">cif número</span></span>
  
<span data-ttu-id="eef02-875">cifnúmero #</span><span class="sxs-lookup"><span data-stu-id="eef02-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="eef02-876">瑞典</span><span class="sxs-lookup"><span data-stu-id="eef02-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="eef02-877">格式</span><span class="sxs-lookup"><span data-stu-id="eef02-877">Format</span></span>

<span data-ttu-id="eef02-878">10个数字和指定模式中的符号</span><span class="sxs-lookup"><span data-stu-id="eef02-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eef02-879">模式</span><span class="sxs-lookup"><span data-stu-id="eef02-879">Pattern</span></span>

<span data-ttu-id="eef02-880">10个数字和一个符号:</span><span class="sxs-lookup"><span data-stu-id="eef02-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="eef02-881">与出生日期对应的6个数字 (YYMMDD)</span><span class="sxs-lookup"><span data-stu-id="eef02-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="eef02-882">加号、减号或反斜杠</span><span class="sxs-lookup"><span data-stu-id="eef02-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="eef02-883">在以下位置使标识号唯一的三个数字:</span><span class="sxs-lookup"><span data-stu-id="eef02-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="eef02-884">对于在1990之前发出的号码, 第七和第八位数字标识出生的县或外部人</span><span class="sxs-lookup"><span data-stu-id="eef02-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="eef02-885">第九个位置中的数字表示为奇数或甚至是女的性别</span><span class="sxs-lookup"><span data-stu-id="eef02-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="eef02-886">一个校验位</span><span class="sxs-lookup"><span data-stu-id="eef02-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="eef02-887">校验和</span><span class="sxs-lookup"><span data-stu-id="eef02-887">Checksum</span></span>

<span data-ttu-id="eef02-888">是</span><span class="sxs-lookup"><span data-stu-id="eef02-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="eef02-889">定义</span><span class="sxs-lookup"><span data-stu-id="eef02-889">Definition</span></span>

<span data-ttu-id="eef02-890">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-891">函数`Func_sweden_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eef02-892">找到了中`Keywords_sweden_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="eef02-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="eef02-893">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-894">函数`Func_sweden_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eef02-895">关键字</span><span class="sxs-lookup"><span data-stu-id="eef02-895">Keywords</span></span>

#### <a name="keywordsswedeneutaxfilenumber"></a><span data-ttu-id="eef02-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="eef02-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="eef02-897">tax id</span><span class="sxs-lookup"><span data-stu-id="eef02-897">tax id</span></span>
  
<span data-ttu-id="eef02-898">税号编号</span><span class="sxs-lookup"><span data-stu-id="eef02-898">tax id no.</span></span>
  
<span data-ttu-id="eef02-899">税务 id 号</span><span class="sxs-lookup"><span data-stu-id="eef02-899">tax id number</span></span>
  
<span data-ttu-id="eef02-900">tax identification</span><span class="sxs-lookup"><span data-stu-id="eef02-900">tax identification</span></span>
  
<span data-ttu-id="eef02-901">纳税标识号</span><span class="sxs-lookup"><span data-stu-id="eef02-901">tax identification#</span></span>
  
<span data-ttu-id="eef02-902">纳税编号</span><span class="sxs-lookup"><span data-stu-id="eef02-902">tax no.</span></span>
  
<span data-ttu-id="eef02-903">税种</span><span class="sxs-lookup"><span data-stu-id="eef02-903">tax#</span></span>
  
<span data-ttu-id="eef02-904">taxid #</span><span class="sxs-lookup"><span data-stu-id="eef02-904">taxid#</span></span>
  
<span data-ttu-id="eef02-905">税文件</span><span class="sxs-lookup"><span data-stu-id="eef02-905">tax file</span></span>
  
<span data-ttu-id="eef02-906">税文件编号</span><span class="sxs-lookup"><span data-stu-id="eef02-906">tax file no.</span></span>
  
<span data-ttu-id="eef02-907">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="eef02-907">personal id number</span></span>
  
<span data-ttu-id="eef02-908">skatt id nummer</span><span class="sxs-lookup"><span data-stu-id="eef02-908">skatt id nummer</span></span>
  
<span data-ttu-id="eef02-909">skatt identifikation</span><span class="sxs-lookup"><span data-stu-id="eef02-909">skatt identifikation</span></span>
  
<span data-ttu-id="eef02-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="eef02-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="eef02-911">英国</span><span class="sxs-lookup"><span data-stu-id="eef02-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="eef02-912">格式</span><span class="sxs-lookup"><span data-stu-id="eef02-912">Format</span></span>

<span data-ttu-id="eef02-913">唯一的纳税人参考 (UTR):10 个数字, 无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="eef02-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="eef02-914">国家保险业号码 (NINO): 有关详细信息, 请参阅 "英国</span><span class="sxs-lookup"><span data-stu-id="eef02-914">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="eef02-915">[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的国家保险业号码 (NINO)。</span><span class="sxs-lookup"><span data-stu-id="eef02-915">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eef02-916">模式</span><span class="sxs-lookup"><span data-stu-id="eef02-916">Pattern</span></span>

<span data-ttu-id="eef02-917">唯一的纳税人引用 (UTR):10 个数字</span><span class="sxs-lookup"><span data-stu-id="eef02-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="eef02-918">国家保险业号码 (NINO): 有关详细信息, 请参阅 "英国</span><span class="sxs-lookup"><span data-stu-id="eef02-918">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="eef02-919">[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的国家保险业号码 (NINO)。</span><span class="sxs-lookup"><span data-stu-id="eef02-919">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="eef02-920">校验和</span><span class="sxs-lookup"><span data-stu-id="eef02-920">Checksum</span></span>

<span data-ttu-id="eef02-921">是</span><span class="sxs-lookup"><span data-stu-id="eef02-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="eef02-922">定义</span><span class="sxs-lookup"><span data-stu-id="eef02-922">Definition</span></span>

<span data-ttu-id="eef02-923">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="eef02-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eef02-924">函数`Func_uk_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="eef02-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eef02-925">找到了中`Keywords_uk_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="eef02-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eef02-926">关键字</span><span class="sxs-lookup"><span data-stu-id="eef02-926">Keywords</span></span>

#### <a name="keywordsukeutaxfilenumber"></a><span data-ttu-id="eef02-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="eef02-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="eef02-928">tax id</span><span class="sxs-lookup"><span data-stu-id="eef02-928">tax id</span></span>
  
<span data-ttu-id="eef02-929">税号编号</span><span class="sxs-lookup"><span data-stu-id="eef02-929">tax id no.</span></span>
  
<span data-ttu-id="eef02-930">税务 id 号</span><span class="sxs-lookup"><span data-stu-id="eef02-930">tax id number</span></span>
  
<span data-ttu-id="eef02-931">tax identification</span><span class="sxs-lookup"><span data-stu-id="eef02-931">tax identification</span></span>
  
<span data-ttu-id="eef02-932">纳税标识号</span><span class="sxs-lookup"><span data-stu-id="eef02-932">tax identification#</span></span>
  
<span data-ttu-id="eef02-933">纳税编号</span><span class="sxs-lookup"><span data-stu-id="eef02-933">tax no.</span></span>
  
<span data-ttu-id="eef02-934">税种</span><span class="sxs-lookup"><span data-stu-id="eef02-934">tax#</span></span>
  
<span data-ttu-id="eef02-935">taxid #</span><span class="sxs-lookup"><span data-stu-id="eef02-935">taxid#</span></span>
  
<span data-ttu-id="eef02-936">税文件</span><span class="sxs-lookup"><span data-stu-id="eef02-936">tax file</span></span>
  
<span data-ttu-id="eef02-937">税文件编号</span><span class="sxs-lookup"><span data-stu-id="eef02-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="eef02-938">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eef02-938">See also</span></span>

[<span data-ttu-id="eef02-939">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="eef02-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

