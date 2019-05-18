---
title: EU 税标识号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主题介绍当数据丢失防护 (DLP) 策略检测到欧盟税务识别号敏感信息类型时, 应查找什么。 此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。
ms.openlocfilehash: adcd9be9b5f8775ad39010d771ff2ac214df1e17
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152954"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="e850d-104">EU 税标识号</span><span class="sxs-lookup"><span data-stu-id="e850d-104">EU Tax Identification Number</span></span>

<span data-ttu-id="e850d-105">本主题介绍了数据丢失防护 (DLP) 策略在检测到欧盟纳税标识号 (TIN) 敏感信息类型时的查找内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type.</span></span> <span data-ttu-id="e850d-106">此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。</span><span class="sxs-lookup"><span data-stu-id="e850d-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="e850d-107">奥地利</span><span class="sxs-lookup"><span data-stu-id="e850d-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="e850d-108">Format</span><span class="sxs-lookup"><span data-stu-id="e850d-108">Format</span></span>

<span data-ttu-id="e850d-109">9个数字, 带可选连字符和正斜线</span><span class="sxs-lookup"><span data-stu-id="e850d-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e850d-110">模式</span><span class="sxs-lookup"><span data-stu-id="e850d-110">Pattern</span></span>

<span data-ttu-id="e850d-111">9个带可选连字符和正斜线的数字:</span><span class="sxs-lookup"><span data-stu-id="e850d-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="e850d-112">两位数字</span><span class="sxs-lookup"><span data-stu-id="e850d-112">Two digits</span></span> 
    
- <span data-ttu-id="e850d-113">一个连字符（可选）</span><span class="sxs-lookup"><span data-stu-id="e850d-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="e850d-114">三位数字</span><span class="sxs-lookup"><span data-stu-id="e850d-114">Three digits</span></span>
    
- <span data-ttu-id="e850d-115">正斜杠（可选）</span><span class="sxs-lookup"><span data-stu-id="e850d-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="e850d-116">四位数字</span><span class="sxs-lookup"><span data-stu-id="e850d-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e850d-117">校验和</span><span class="sxs-lookup"><span data-stu-id="e850d-117">Checksum</span></span>

<span data-ttu-id="e850d-118">是</span><span class="sxs-lookup"><span data-stu-id="e850d-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e850d-119">定义</span><span class="sxs-lookup"><span data-stu-id="e850d-119">Definition</span></span>

<span data-ttu-id="e850d-120">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-121">函数`Func_austria_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e850d-122">找到了中`Keywords_austria_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="e850d-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e850d-123">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-124">函数`Func_austria_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e850d-125">关键字</span><span class="sxs-lookup"><span data-stu-id="e850d-125">Keywords</span></span>

#### <a name="keywordsaustriaeutaxfilenumber"></a><span data-ttu-id="e850d-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e850d-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="e850d-127">税号</span><span class="sxs-lookup"><span data-stu-id="e850d-127">tax number</span></span>
  
<span data-ttu-id="e850d-128">number</span><span class="sxs-lookup"><span data-stu-id="e850d-128">number</span></span>
  
<span data-ttu-id="e850d-129">税务登记编号</span><span class="sxs-lookup"><span data-stu-id="e850d-129">tax registration number</span></span>
  
<span data-ttu-id="e850d-130">tax id</span><span class="sxs-lookup"><span data-stu-id="e850d-130">tax id</span></span>
  
<span data-ttu-id="e850d-131">st.nr。</span><span class="sxs-lookup"><span data-stu-id="e850d-131">st.nr.</span></span>
  
<span data-ttu-id="e850d-132">steuernummer</span><span class="sxs-lookup"><span data-stu-id="e850d-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="e850d-133">比利时</span><span class="sxs-lookup"><span data-stu-id="e850d-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="e850d-134">Format</span><span class="sxs-lookup"><span data-stu-id="e850d-134">Format</span></span>

<span data-ttu-id="e850d-135">11个数字, 无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="e850d-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e850d-136">模式</span><span class="sxs-lookup"><span data-stu-id="e850d-136">Pattern</span></span>

<span data-ttu-id="e850d-137">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="e850d-137">11 digits:</span></span>
  
- <span data-ttu-id="e850d-138">两位数字</span><span class="sxs-lookup"><span data-stu-id="e850d-138">Two digits</span></span>
    
- <span data-ttu-id="e850d-139">"0" 或 "1"</span><span class="sxs-lookup"><span data-stu-id="e850d-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="e850d-140">一位数字</span><span class="sxs-lookup"><span data-stu-id="e850d-140">One digit</span></span>
    
- <span data-ttu-id="e850d-141">"0" 或 "1" 或 "2" 或 "3"</span><span class="sxs-lookup"><span data-stu-id="e850d-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="e850d-142">六个数字</span><span class="sxs-lookup"><span data-stu-id="e850d-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e850d-143">校验和</span><span class="sxs-lookup"><span data-stu-id="e850d-143">Checksum</span></span>

<span data-ttu-id="e850d-144">不适用</span><span class="sxs-lookup"><span data-stu-id="e850d-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e850d-145">定义</span><span class="sxs-lookup"><span data-stu-id="e850d-145">Definition</span></span>

<span data-ttu-id="e850d-146">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-147">正则表达式`Regex_belgium_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e850d-148">找到了中`Keywords_belgium_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="e850d-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e850d-149">关键字</span><span class="sxs-lookup"><span data-stu-id="e850d-149">Keywords</span></span>

#### <a name="keywordsbelgiumeutaxfilenumber"></a><span data-ttu-id="e850d-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e850d-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="e850d-151">税号</span><span class="sxs-lookup"><span data-stu-id="e850d-151">tax number</span></span>
  
<span data-ttu-id="e850d-152">国家注册号码</span><span class="sxs-lookup"><span data-stu-id="e850d-152">national registration number</span></span>
  
<span data-ttu-id="e850d-153">税务登记编号</span><span class="sxs-lookup"><span data-stu-id="e850d-153">tax registration number</span></span>
  
<span data-ttu-id="e850d-154">tax id</span><span class="sxs-lookup"><span data-stu-id="e850d-154">tax id</span></span>
  
<span data-ttu-id="e850d-155">\n\n</span><span class="sxs-lookup"><span data-stu-id="e850d-155">nif</span></span>
  
<span data-ttu-id="e850d-156">\n\n</span><span class="sxs-lookup"><span data-stu-id="e850d-156">nif#</span></span>
  
<span data-ttu-id="e850d-157">numéro de registre 国</span><span class="sxs-lookup"><span data-stu-id="e850d-157">numéro de registre national</span></span>
  
<span data-ttu-id="e850d-158">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="e850d-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="e850d-159">保加利亚语</span><span class="sxs-lookup"><span data-stu-id="e850d-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="e850d-160">Format</span><span class="sxs-lookup"><span data-stu-id="e850d-160">Format</span></span>

<span data-ttu-id="e850d-161">10个数字, 无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="e850d-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e850d-162">模式</span><span class="sxs-lookup"><span data-stu-id="e850d-162">Pattern</span></span>

<span data-ttu-id="e850d-163">10 个数字</span><span class="sxs-lookup"><span data-stu-id="e850d-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e850d-164">校验和</span><span class="sxs-lookup"><span data-stu-id="e850d-164">Checksum</span></span>

<span data-ttu-id="e850d-165">是</span><span class="sxs-lookup"><span data-stu-id="e850d-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e850d-166">定义</span><span class="sxs-lookup"><span data-stu-id="e850d-166">Definition</span></span>

<span data-ttu-id="e850d-167">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-168">函数`Func_bulgaria_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e850d-169">找到了中`Keywords_bulgaria_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="e850d-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e850d-170">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-171">函数`Func_bulgaria_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e850d-172">关键字</span><span class="sxs-lookup"><span data-stu-id="e850d-172">Keywords</span></span>

#### <a name="keywordsbulgariaeutaxfilenumber"></a><span data-ttu-id="e850d-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e850d-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="e850d-174">bucn</span><span class="sxs-lookup"><span data-stu-id="e850d-174">bucn</span></span>
  
<span data-ttu-id="e850d-175">统一的民事号码</span><span class="sxs-lookup"><span data-stu-id="e850d-175">uniform civil number</span></span>
  
<span data-ttu-id="e850d-176">bucn#</span><span class="sxs-lookup"><span data-stu-id="e850d-176">bucn#</span></span>
  
<span data-ttu-id="e850d-177">uniformcivilnumber#</span><span class="sxs-lookup"><span data-stu-id="e850d-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="e850d-178">统一的民事 id</span><span class="sxs-lookup"><span data-stu-id="e850d-178">uniform civil id</span></span>
  
<span data-ttu-id="e850d-179">统一的民事无</span><span class="sxs-lookup"><span data-stu-id="e850d-179">uniform civil no</span></span>
  
<span data-ttu-id="e850d-180">egn</span><span class="sxs-lookup"><span data-stu-id="e850d-180">egn</span></span>
  
<span data-ttu-id="e850d-181">保加利亚语统一民事号码</span><span class="sxs-lookup"><span data-stu-id="e850d-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="e850d-182">uniformcivilno#</span><span class="sxs-lookup"><span data-stu-id="e850d-182">uniformcivilno#</span></span>
  
<span data-ttu-id="e850d-183">egn#</span><span class="sxs-lookup"><span data-stu-id="e850d-183">egn#</span></span>
  
<span data-ttu-id="e850d-184">униформ граждански номер</span><span class="sxs-lookup"><span data-stu-id="e850d-184">униформ граждански номер</span></span>
  
<span data-ttu-id="e850d-185">униформ id</span><span class="sxs-lookup"><span data-stu-id="e850d-185">униформ id</span></span>
  
<span data-ttu-id="e850d-186">униформграждански id</span><span class="sxs-lookup"><span data-stu-id="e850d-186">униформ граждански id</span></span>
  
<span data-ttu-id="e850d-187">униформ граждански не</span><span class="sxs-lookup"><span data-stu-id="e850d-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="e850d-188">克罗地亚</span><span class="sxs-lookup"><span data-stu-id="e850d-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="e850d-189">Format</span><span class="sxs-lookup"><span data-stu-id="e850d-189">Format</span></span>

<span data-ttu-id="e850d-190">11个不带空格或分隔符的数字</span><span class="sxs-lookup"><span data-stu-id="e850d-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e850d-191">模式</span><span class="sxs-lookup"><span data-stu-id="e850d-191">Pattern</span></span>

<span data-ttu-id="e850d-192">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="e850d-192">11 digits:</span></span>
  
- <span data-ttu-id="e850d-193">10个数字, 随机选择</span><span class="sxs-lookup"><span data-stu-id="e850d-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="e850d-194">一个校验位</span><span class="sxs-lookup"><span data-stu-id="e850d-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e850d-195">校验和</span><span class="sxs-lookup"><span data-stu-id="e850d-195">Checksum</span></span>

<span data-ttu-id="e850d-196">是</span><span class="sxs-lookup"><span data-stu-id="e850d-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e850d-197">定义</span><span class="sxs-lookup"><span data-stu-id="e850d-197">Definition</span></span>

<span data-ttu-id="e850d-198">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-199">函数`Func_croatia_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e850d-200">找到了中`Keywords_croatia_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="e850d-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e850d-201">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-202">函数`Func_croatia_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e850d-203">关键字</span><span class="sxs-lookup"><span data-stu-id="e850d-203">Keywords</span></span>

#### <a name="keywordscroatiaeutaxfilenumber"></a><span data-ttu-id="e850d-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e850d-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="e850d-205">税号</span><span class="sxs-lookup"><span data-stu-id="e850d-205">tax number</span></span>
  
<span data-ttu-id="e850d-206">税种</span><span class="sxs-lookup"><span data-stu-id="e850d-206">tax</span></span>
  
<span data-ttu-id="e850d-207">tax id</span><span class="sxs-lookup"><span data-stu-id="e850d-207">tax id</span></span>
  
<span data-ttu-id="e850d-208">oid</span><span class="sxs-lookup"><span data-stu-id="e850d-208">oid</span></span>
  
<span data-ttu-id="e850d-209">排列</span><span class="sxs-lookup"><span data-stu-id="e850d-209">oid#</span></span>
  
<span data-ttu-id="e850d-210">porezni broj</span><span class="sxs-lookup"><span data-stu-id="e850d-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="e850d-211">塞浦路斯</span><span class="sxs-lookup"><span data-stu-id="e850d-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="e850d-212">Format</span><span class="sxs-lookup"><span data-stu-id="e850d-212">Format</span></span>

<span data-ttu-id="e850d-213">指定模式中的八个数字和一个字母</span><span class="sxs-lookup"><span data-stu-id="e850d-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e850d-214">模式</span><span class="sxs-lookup"><span data-stu-id="e850d-214">Pattern</span></span>

<span data-ttu-id="e850d-215">八个数字和一个字母:</span><span class="sxs-lookup"><span data-stu-id="e850d-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="e850d-216">一个 "0"</span><span class="sxs-lookup"><span data-stu-id="e850d-216">A "0"</span></span> 
    
- <span data-ttu-id="e850d-217">七个数字 </span><span class="sxs-lookup"><span data-stu-id="e850d-217">Seven digits</span></span>
    
- <span data-ttu-id="e850d-218">一个字母 (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="e850d-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e850d-219">校验和</span><span class="sxs-lookup"><span data-stu-id="e850d-219">Checksum</span></span>

<span data-ttu-id="e850d-220">不适用</span><span class="sxs-lookup"><span data-stu-id="e850d-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e850d-221">定义</span><span class="sxs-lookup"><span data-stu-id="e850d-221">Definition</span></span>

<span data-ttu-id="e850d-222">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-223">函数`Func_cyprus_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e850d-224">找到了中`Keywords_cyprus_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="e850d-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e850d-225">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-226">函数`Func_cyprus_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e850d-227">关键字</span><span class="sxs-lookup"><span data-stu-id="e850d-227">Keywords</span></span>

#### <a name="keywordscypruseutaxfilenumber"></a><span data-ttu-id="e850d-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e850d-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="e850d-229">税号</span><span class="sxs-lookup"><span data-stu-id="e850d-229">tax number</span></span>
  
<span data-ttu-id="e850d-230">税种</span><span class="sxs-lookup"><span data-stu-id="e850d-230">tax</span></span>
  
<span data-ttu-id="e850d-231">tax id</span><span class="sxs-lookup"><span data-stu-id="e850d-231">tax id</span></span>
  
<span data-ttu-id="e850d-232">税标识代码</span><span class="sxs-lookup"><span data-stu-id="e850d-232">tax identification code</span></span>
  
<span data-ttu-id="e850d-233">和</span><span class="sxs-lookup"><span data-stu-id="e850d-233">tic</span></span>
  
<span data-ttu-id="e850d-234">和</span><span class="sxs-lookup"><span data-stu-id="e850d-234">tic#</span></span>
  
<span data-ttu-id="e850d-235">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="e850d-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="e850d-236">φορολογική ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="e850d-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="e850d-237">κωδικός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="e850d-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="e850d-238">捷克共和国</span><span class="sxs-lookup"><span data-stu-id="e850d-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="e850d-239">Format</span><span class="sxs-lookup"><span data-stu-id="e850d-239">Format</span></span>

<span data-ttu-id="e850d-240">9个或10个数字, 带可选反斜杠</span><span class="sxs-lookup"><span data-stu-id="e850d-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e850d-241">模式</span><span class="sxs-lookup"><span data-stu-id="e850d-241">Pattern</span></span>

<span data-ttu-id="e850d-242">9个或10个数字, 可选 backslashl:</span><span class="sxs-lookup"><span data-stu-id="e850d-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="e850d-243">六位数字</span><span class="sxs-lookup"><span data-stu-id="e850d-243">Six digits</span></span> 
    
- <span data-ttu-id="e850d-244">反斜杠 (可选)</span><span class="sxs-lookup"><span data-stu-id="e850d-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="e850d-245">三个或四个数字</span><span class="sxs-lookup"><span data-stu-id="e850d-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e850d-246">校验和</span><span class="sxs-lookup"><span data-stu-id="e850d-246">Checksum</span></span>

<span data-ttu-id="e850d-247">不适用</span><span class="sxs-lookup"><span data-stu-id="e850d-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e850d-248">定义</span><span class="sxs-lookup"><span data-stu-id="e850d-248">Definition</span></span>

<span data-ttu-id="e850d-249">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-250">正则表达式`Regex_czech_republic_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e850d-251">找到了中`Keywords_czech_republic_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="e850d-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e850d-252">关键字</span><span class="sxs-lookup"><span data-stu-id="e850d-252">Keywords</span></span>

#### <a name="keywordsczechrepubliceutaxfilenumber"></a><span data-ttu-id="e850d-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e850d-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="e850d-254">税号</span><span class="sxs-lookup"><span data-stu-id="e850d-254">tax number</span></span>
  
<span data-ttu-id="e850d-255">税种</span><span class="sxs-lookup"><span data-stu-id="e850d-255">tax</span></span>
  
<span data-ttu-id="e850d-256">tax id</span><span class="sxs-lookup"><span data-stu-id="e850d-256">tax id</span></span>
  
<span data-ttu-id="e850d-257">个人号码</span><span class="sxs-lookup"><span data-stu-id="e850d-257">personal number</span></span>
  
<span data-ttu-id="e850d-258">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="e850d-258">daňové číslo</span></span>
  
<span data-ttu-id="e850d-259">osobní číslo</span><span class="sxs-lookup"><span data-stu-id="e850d-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="e850d-260">丹麦</span><span class="sxs-lookup"><span data-stu-id="e850d-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="e850d-261">Format</span><span class="sxs-lookup"><span data-stu-id="e850d-261">Format</span></span>

<span data-ttu-id="e850d-262">10个数字, 包含连字符</span><span class="sxs-lookup"><span data-stu-id="e850d-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e850d-263">模式</span><span class="sxs-lookup"><span data-stu-id="e850d-263">Pattern</span></span>

<span data-ttu-id="e850d-264">包含 hyphenl 的10个数字:</span><span class="sxs-lookup"><span data-stu-id="e850d-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="e850d-265">与出生日期对应的6个数字 (DDMMYY)</span><span class="sxs-lookup"><span data-stu-id="e850d-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="e850d-266">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="e850d-266">A hyphen</span></span>
    
- <span data-ttu-id="e850d-267">与序列号对应的四个数字, 其中第一个数字对应于出生世纪, 最后一个数字对应于个人的性别 (对于男为奇数, 甚至对于母版)</span><span class="sxs-lookup"><span data-stu-id="e850d-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e850d-268">校验和</span><span class="sxs-lookup"><span data-stu-id="e850d-268">Checksum</span></span>

<span data-ttu-id="e850d-269">是</span><span class="sxs-lookup"><span data-stu-id="e850d-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e850d-270">定义</span><span class="sxs-lookup"><span data-stu-id="e850d-270">Definition</span></span>

<span data-ttu-id="e850d-271">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-272">函数`Func_denmark_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e850d-273">找到了中`Keywords_denmark_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="e850d-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e850d-274">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-275">函数`Func_denmark_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e850d-276">关键字</span><span class="sxs-lookup"><span data-stu-id="e850d-276">Keywords</span></span>

#### <a name="keywordsdenmarkeutaxfilenumber"></a><span data-ttu-id="e850d-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e850d-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="e850d-278">税号</span><span class="sxs-lookup"><span data-stu-id="e850d-278">tax number</span></span>
  
<span data-ttu-id="e850d-279">税种</span><span class="sxs-lookup"><span data-stu-id="e850d-279">tax</span></span>
  
<span data-ttu-id="e850d-280">tax id</span><span class="sxs-lookup"><span data-stu-id="e850d-280">tax id</span></span>
  
<span data-ttu-id="e850d-281">cpr 编号</span><span class="sxs-lookup"><span data-stu-id="e850d-281">cpr number</span></span>
  
<span data-ttu-id="e850d-282">cpr#</span><span class="sxs-lookup"><span data-stu-id="e850d-282">cpr#</span></span>
  
<span data-ttu-id="e850d-283">skat nummer</span><span class="sxs-lookup"><span data-stu-id="e850d-283">skat nummer</span></span>
  
<span data-ttu-id="e850d-284">skat id</span><span class="sxs-lookup"><span data-stu-id="e850d-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="e850d-285">爱沙尼亚</span><span class="sxs-lookup"><span data-stu-id="e850d-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="e850d-286">Format</span><span class="sxs-lookup"><span data-stu-id="e850d-286">Format</span></span>

<span data-ttu-id="e850d-287">11个不带空格或分隔符的数字</span><span class="sxs-lookup"><span data-stu-id="e850d-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e850d-288">模式</span><span class="sxs-lookup"><span data-stu-id="e850d-288">Pattern</span></span>

<span data-ttu-id="e850d-289">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="e850d-289">11 digits:</span></span>
  
-  <span data-ttu-id="e850d-290">一种与性别和世纪相对应的数字, 其中奇数表示男, 偶数表示女, 如下所示: 1, 2 代表19世纪;3, 4 表示20世纪;对于21世纪, 为 5, 6</span><span class="sxs-lookup"><span data-stu-id="e850d-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="e850d-291">与出生日期对应的6个数字 (YYMMDD)</span><span class="sxs-lookup"><span data-stu-id="e850d-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="e850d-292">三个数字, 对应于将出生在同一日期的人员组成的序列号</span><span class="sxs-lookup"><span data-stu-id="e850d-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="e850d-293">一个校验位</span><span class="sxs-lookup"><span data-stu-id="e850d-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e850d-294">校验和</span><span class="sxs-lookup"><span data-stu-id="e850d-294">Checksum</span></span>

<span data-ttu-id="e850d-295">是</span><span class="sxs-lookup"><span data-stu-id="e850d-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e850d-296">定义</span><span class="sxs-lookup"><span data-stu-id="e850d-296">Definition</span></span>

<span data-ttu-id="e850d-297">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-298">函数`Func_estonia_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e850d-299">找到了中`Keywords_estonia_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="e850d-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e850d-300">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-301">函数`Func_estonia_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e850d-302">关键字</span><span class="sxs-lookup"><span data-stu-id="e850d-302">Keywords</span></span>

#### <a name="keywordsestoniaeutaxfilenumber"></a><span data-ttu-id="e850d-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e850d-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="e850d-304">税号</span><span class="sxs-lookup"><span data-stu-id="e850d-304">tax number</span></span>
  
<span data-ttu-id="e850d-305">税种</span><span class="sxs-lookup"><span data-stu-id="e850d-305">tax</span></span>
  
<span data-ttu-id="e850d-306">tax id</span><span class="sxs-lookup"><span data-stu-id="e850d-306">tax id</span></span>
  
<span data-ttu-id="e850d-307">个人代码</span><span class="sxs-lookup"><span data-stu-id="e850d-307">personal code</span></span>
  
<span data-ttu-id="e850d-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="e850d-308">maksunumber</span></span>
  
<span data-ttu-id="e850d-309">maksu id</span><span class="sxs-lookup"><span data-stu-id="e850d-309">maksu id</span></span>
  
<span data-ttu-id="e850d-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="e850d-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="e850d-311">芬兰</span><span class="sxs-lookup"><span data-stu-id="e850d-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="e850d-312">Format</span><span class="sxs-lookup"><span data-stu-id="e850d-312">Format</span></span>

<span data-ttu-id="e850d-313">一个11字符组合的数字、字母、加号和减号</span><span class="sxs-lookup"><span data-stu-id="e850d-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e850d-314">模式</span><span class="sxs-lookup"><span data-stu-id="e850d-314">Pattern</span></span>

<span data-ttu-id="e850d-315">一个11个字符的数字、字母和加号和减号的组合:</span><span class="sxs-lookup"><span data-stu-id="e850d-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="e850d-316">六位数字</span><span class="sxs-lookup"><span data-stu-id="e850d-316">Six digits</span></span>
    
- <span data-ttu-id="e850d-317">以下之一: 加号、减号或字母 "A" (不区分大小写), 其中加号表示介于1800-1899 之间, 负号表示在1900-1999 之间, 而 "A" 表示出生2000和之后</span><span class="sxs-lookup"><span data-stu-id="e850d-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="e850d-318">三位数字</span><span class="sxs-lookup"><span data-stu-id="e850d-318">Three digits</span></span>
    
- <span data-ttu-id="e850d-319">一个字母或一个数字</span><span class="sxs-lookup"><span data-stu-id="e850d-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e850d-320">校验和</span><span class="sxs-lookup"><span data-stu-id="e850d-320">Checksum</span></span>

<span data-ttu-id="e850d-321">是</span><span class="sxs-lookup"><span data-stu-id="e850d-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e850d-322">定义</span><span class="sxs-lookup"><span data-stu-id="e850d-322">Definition</span></span>

<span data-ttu-id="e850d-323">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-324">函数`Func_finland_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e850d-325">找到了中`Keywords_finland_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="e850d-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e850d-326">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-327">函数`Func_finland_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e850d-328">关键字</span><span class="sxs-lookup"><span data-stu-id="e850d-328">Keywords</span></span>

#### <a name="keywordsfinlandeutaxfilenumber"></a><span data-ttu-id="e850d-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e850d-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="e850d-330">identification number</span><span class="sxs-lookup"><span data-stu-id="e850d-330">identification number</span></span>
  
<span data-ttu-id="e850d-331">个人 id</span><span class="sxs-lookup"><span data-stu-id="e850d-331">personal id</span></span>
  
<span data-ttu-id="e850d-332">标识号码</span><span class="sxs-lookup"><span data-stu-id="e850d-332">identity number</span></span>
  
<span data-ttu-id="e850d-333">芬兰国家/地区 id 号</span><span class="sxs-lookup"><span data-stu-id="e850d-333">finnish national id number</span></span>
  
<span data-ttu-id="e850d-334">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="e850d-334">personalidnumber#</span></span>
  
<span data-ttu-id="e850d-335">national identification number</span><span class="sxs-lookup"><span data-stu-id="e850d-335">national identification number</span></span>
  
<span data-ttu-id="e850d-336">id 号</span><span class="sxs-lookup"><span data-stu-id="e850d-336">id number</span></span>
  
<span data-ttu-id="e850d-337">国家/地区 id 编号。</span><span class="sxs-lookup"><span data-stu-id="e850d-337">national id no.</span></span>
  
<span data-ttu-id="e850d-338">国家/地区 id 号</span><span class="sxs-lookup"><span data-stu-id="e850d-338">national id number</span></span>
  
<span data-ttu-id="e850d-339">id 号</span><span class="sxs-lookup"><span data-stu-id="e850d-339">id no</span></span>
  
<span data-ttu-id="e850d-340">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="e850d-340">tunnistenumero</span></span>
  
<span data-ttu-id="e850d-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="e850d-341">henkilötunnus</span></span>
  
<span data-ttu-id="e850d-342">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="e850d-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="e850d-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="e850d-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="e850d-344">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="e850d-344">identiteetti numero</span></span>
  
<span data-ttu-id="e850d-345">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="e850d-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="e850d-346">henkilötunnusnumero#</span><span class="sxs-lookup"><span data-stu-id="e850d-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="e850d-347">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="e850d-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="e850d-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="e850d-348">tunnusnumero</span></span>
  
<span data-ttu-id="e850d-349">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="e850d-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="e850d-350">法国</span><span class="sxs-lookup"><span data-stu-id="e850d-350">France</span></span>

### <a name="format"></a><span data-ttu-id="e850d-351">Format</span><span class="sxs-lookup"><span data-stu-id="e850d-351">Format</span></span>

<span data-ttu-id="e850d-352">13位数的个人和九个数字的实体</span><span class="sxs-lookup"><span data-stu-id="e850d-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e850d-353">模式</span><span class="sxs-lookup"><span data-stu-id="e850d-353">Pattern</span></span>

<span data-ttu-id="e850d-354">适用于个人的13个数字:</span><span class="sxs-lookup"><span data-stu-id="e850d-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="e850d-355">一个数字, 必须为0、1、2或3</span><span class="sxs-lookup"><span data-stu-id="e850d-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="e850d-356">12 个数字</span><span class="sxs-lookup"><span data-stu-id="e850d-356">12 digits</span></span>
    
<span data-ttu-id="e850d-357">9个图元数字</span><span class="sxs-lookup"><span data-stu-id="e850d-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e850d-358">校验和</span><span class="sxs-lookup"><span data-stu-id="e850d-358">Checksum</span></span>

<span data-ttu-id="e850d-359">不适用</span><span class="sxs-lookup"><span data-stu-id="e850d-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e850d-360">定义</span><span class="sxs-lookup"><span data-stu-id="e850d-360">Definition</span></span>

<span data-ttu-id="e850d-361">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-362">函数`Func_france_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e850d-363">找到了中`Keywords_france_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="e850d-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e850d-364">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-365">函数`Func_france_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e850d-366">关键字</span><span class="sxs-lookup"><span data-stu-id="e850d-366">Keywords</span></span>

#### <a name="keywordsfranceeutaxfilenumber"></a><span data-ttu-id="e850d-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e850d-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="e850d-368">税标识号</span><span class="sxs-lookup"><span data-stu-id="e850d-368">tax identification number</span></span>
  
<span data-ttu-id="e850d-369">税号</span><span class="sxs-lookup"><span data-stu-id="e850d-369">tax number</span></span>
  
<span data-ttu-id="e850d-370">tax id</span><span class="sxs-lookup"><span data-stu-id="e850d-370">tax id</span></span>
  
<span data-ttu-id="e850d-371">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="e850d-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="e850d-372">德国</span><span class="sxs-lookup"><span data-stu-id="e850d-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="e850d-373">Format</span><span class="sxs-lookup"><span data-stu-id="e850d-373">Format</span></span>

<span data-ttu-id="e850d-374">11个数字, 无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="e850d-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e850d-375">模式</span><span class="sxs-lookup"><span data-stu-id="e850d-375">Pattern</span></span>

<span data-ttu-id="e850d-376">11位数字:</span><span class="sxs-lookup"><span data-stu-id="e850d-376">11 digits :</span></span>
  
-  <span data-ttu-id="e850d-377">10位数字</span><span class="sxs-lookup"><span data-stu-id="e850d-377">Ten digits</span></span> 
    
- <span data-ttu-id="e850d-378">一个校验位</span><span class="sxs-lookup"><span data-stu-id="e850d-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e850d-379">校验和</span><span class="sxs-lookup"><span data-stu-id="e850d-379">Checksum</span></span>

<span data-ttu-id="e850d-380">是</span><span class="sxs-lookup"><span data-stu-id="e850d-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e850d-381">定义</span><span class="sxs-lookup"><span data-stu-id="e850d-381">Definition</span></span>

<span data-ttu-id="e850d-382">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-383">函数`Func_germany_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e850d-384">找到了中`Keywords_germany_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="e850d-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e850d-385">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-386">函数`Func_germany_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e850d-387">关键字</span><span class="sxs-lookup"><span data-stu-id="e850d-387">Keywords</span></span>

#### <a name="keywordsgermanyeutaxfilenumber"></a><span data-ttu-id="e850d-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e850d-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="e850d-389">税号</span><span class="sxs-lookup"><span data-stu-id="e850d-389">tax number</span></span>
  
<span data-ttu-id="e850d-390">纳税编号</span><span class="sxs-lookup"><span data-stu-id="e850d-390">tax no.</span></span>
  
<span data-ttu-id="e850d-391">taxno#</span><span class="sxs-lookup"><span data-stu-id="e850d-391">taxno#</span></span>
  
<span data-ttu-id="e850d-392">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="e850d-392">taxnumber#</span></span>
  
<span data-ttu-id="e850d-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="e850d-393">taxnumber</span></span>
  
<span data-ttu-id="e850d-394">tax id</span><span class="sxs-lookup"><span data-stu-id="e850d-394">tax id</span></span>
  
<span data-ttu-id="e850d-395">taxid#</span><span class="sxs-lookup"><span data-stu-id="e850d-395">taxid#</span></span>
  
<span data-ttu-id="e850d-396">税标识号</span><span class="sxs-lookup"><span data-stu-id="e850d-396">tax identification number</span></span>
  
<span data-ttu-id="e850d-397">税号标识号。</span><span class="sxs-lookup"><span data-stu-id="e850d-397">tax identification no.</span></span>
  
<span data-ttu-id="e850d-398">steuernummer</span><span class="sxs-lookup"><span data-stu-id="e850d-398">steuernummer</span></span>
  
<span data-ttu-id="e850d-399">steuer id</span><span class="sxs-lookup"><span data-stu-id="e850d-399">steuer id</span></span>
  
<span data-ttu-id="e850d-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="e850d-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="e850d-401">希腊</span><span class="sxs-lookup"><span data-stu-id="e850d-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="e850d-402">Format</span><span class="sxs-lookup"><span data-stu-id="e850d-402">Format</span></span>

<span data-ttu-id="e850d-403">9个数字, 不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="e850d-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e850d-404">模式</span><span class="sxs-lookup"><span data-stu-id="e850d-404">Pattern</span></span>

<span data-ttu-id="e850d-405">九个数字</span><span class="sxs-lookup"><span data-stu-id="e850d-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e850d-406">校验和</span><span class="sxs-lookup"><span data-stu-id="e850d-406">Checksum</span></span>

<span data-ttu-id="e850d-407">不适用</span><span class="sxs-lookup"><span data-stu-id="e850d-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e850d-408">定义</span><span class="sxs-lookup"><span data-stu-id="e850d-408">Definition</span></span>

<span data-ttu-id="e850d-409">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-410">正则表达式`Regex_greece_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e850d-411">找到了中`Keywords_greece_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="e850d-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e850d-412">关键字</span><span class="sxs-lookup"><span data-stu-id="e850d-412">Keywords</span></span>

#### <a name="keywordsgreeceeutaxfilenumber"></a><span data-ttu-id="e850d-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e850d-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="e850d-414">afm</span><span class="sxs-lookup"><span data-stu-id="e850d-414">afm</span></span>
  
<span data-ttu-id="e850d-415">锡</span><span class="sxs-lookup"><span data-stu-id="e850d-415">tin</span></span>
  
<span data-ttu-id="e850d-416">税号编号</span><span class="sxs-lookup"><span data-stu-id="e850d-416">tax id no.</span></span>
  
<span data-ttu-id="e850d-417">税号编号</span><span class="sxs-lookup"><span data-stu-id="e850d-417">tax id no</span></span>
  
<span data-ttu-id="e850d-418">税标识号</span><span class="sxs-lookup"><span data-stu-id="e850d-418">tax identification number</span></span>
  
<span data-ttu-id="e850d-419">税务注册表号</span><span class="sxs-lookup"><span data-stu-id="e850d-419">tax registry number</span></span>
  
<span data-ttu-id="e850d-420">税务注册表号</span><span class="sxs-lookup"><span data-stu-id="e850d-420">tax registry no.</span></span>
  
<span data-ttu-id="e850d-421">afm</span><span class="sxs-lookup"><span data-stu-id="e850d-421">afm#</span></span>
  
<span data-ttu-id="e850d-422">锡</span><span class="sxs-lookup"><span data-stu-id="e850d-422">tin#</span></span>
  
<span data-ttu-id="e850d-423">taxidno#</span><span class="sxs-lookup"><span data-stu-id="e850d-423">taxidno#</span></span>
  
<span data-ttu-id="e850d-424">taxregistryno#</span><span class="sxs-lookup"><span data-stu-id="e850d-424">taxregistryno#</span></span>
  
<span data-ttu-id="e850d-425">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="e850d-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="e850d-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="e850d-426">aφμ</span></span>
  
<span data-ttu-id="e850d-427">aφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="e850d-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="e850d-428">φορολογικού μητρώου νο.</span><span class="sxs-lookup"><span data-stu-id="e850d-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="e850d-429">τον αριθμό φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="e850d-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="e850d-430">匈牙利</span><span class="sxs-lookup"><span data-stu-id="e850d-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="e850d-431">Format</span><span class="sxs-lookup"><span data-stu-id="e850d-431">Format</span></span>

<span data-ttu-id="e850d-432">10个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="e850d-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e850d-433">模式</span><span class="sxs-lookup"><span data-stu-id="e850d-433">Pattern</span></span>

<span data-ttu-id="e850d-434">10位数字:</span><span class="sxs-lookup"><span data-stu-id="e850d-434">Ten digits:</span></span>
  
-  <span data-ttu-id="e850d-435">一个必须为 "8" 的数字</span><span class="sxs-lookup"><span data-stu-id="e850d-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="e850d-436">与日期01/01/1867 之间的天数对应的五个数字和个人的出生日期</span><span class="sxs-lookup"><span data-stu-id="e850d-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="e850d-437">三个数字, 对应于通过机会区分在同一天的人所生成的数字</span><span class="sxs-lookup"><span data-stu-id="e850d-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="e850d-438">一个校验位</span><span class="sxs-lookup"><span data-stu-id="e850d-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e850d-439">校验和</span><span class="sxs-lookup"><span data-stu-id="e850d-439">Checksum</span></span>

<span data-ttu-id="e850d-440">是</span><span class="sxs-lookup"><span data-stu-id="e850d-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e850d-441">定义</span><span class="sxs-lookup"><span data-stu-id="e850d-441">Definition</span></span>

<span data-ttu-id="e850d-442">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-443">函数`Func_hungary_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e850d-444">找到了中`Keywords_hungary_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="e850d-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e850d-445">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-446">函数`Func_hungary_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e850d-447">关键字</span><span class="sxs-lookup"><span data-stu-id="e850d-447">Keywords</span></span>

#### <a name="keywordshungaryeutaxfilenumber"></a><span data-ttu-id="e850d-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e850d-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="e850d-449">匈牙利语税号标识号</span><span class="sxs-lookup"><span data-stu-id="e850d-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="e850d-450">匈牙利纳税人标识号</span><span class="sxs-lookup"><span data-stu-id="e850d-450">hungarian tin</span></span>
  
<span data-ttu-id="e850d-451">税务 id 号</span><span class="sxs-lookup"><span data-stu-id="e850d-451">tax id number</span></span>
  
<span data-ttu-id="e850d-452">vat 号码</span><span class="sxs-lookup"><span data-stu-id="e850d-452">vat number</span></span>
  
<span data-ttu-id="e850d-453">税务主管机构编号</span><span class="sxs-lookup"><span data-stu-id="e850d-453">tax authority no</span></span>
  
<span data-ttu-id="e850d-454">税号纳税标识号</span><span class="sxs-lookup"><span data-stu-id="e850d-454">tax id tax identity number</span></span>
  
<span data-ttu-id="e850d-455">taxidnumber#</span><span class="sxs-lookup"><span data-stu-id="e850d-455">taxidnumber#</span></span>
  
<span data-ttu-id="e850d-456">锡</span><span class="sxs-lookup"><span data-stu-id="e850d-456">tin#</span></span>
  
<span data-ttu-id="e850d-457">hungatiantin#</span><span class="sxs-lookup"><span data-stu-id="e850d-457">hungatiantin#</span></span>
  
<span data-ttu-id="e850d-458">税号标识编号</span><span class="sxs-lookup"><span data-stu-id="e850d-458">tax identification no</span></span>
  
<span data-ttu-id="e850d-459">taxidno#</span><span class="sxs-lookup"><span data-stu-id="e850d-459">taxidno#</span></span>
  
<span data-ttu-id="e850d-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="e850d-460">adóazonosító szám</span></span>
  
<span data-ttu-id="e850d-461">adószám</span><span class="sxs-lookup"><span data-stu-id="e850d-461">adószám</span></span>
  
<span data-ttu-id="e850d-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="e850d-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="e850d-463">爱尔兰</span><span class="sxs-lookup"><span data-stu-id="e850d-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="e850d-464">Format</span><span class="sxs-lookup"><span data-stu-id="e850d-464">Format</span></span>

<span data-ttu-id="e850d-465">七位数字后跟一个不带空格或分隔符的字母</span><span class="sxs-lookup"><span data-stu-id="e850d-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e850d-466">模式</span><span class="sxs-lookup"><span data-stu-id="e850d-466">Pattern</span></span>

<span data-ttu-id="e850d-467">七位数字后跟一个字母:</span><span class="sxs-lookup"><span data-stu-id="e850d-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="e850d-468">七个数字 </span><span class="sxs-lookup"><span data-stu-id="e850d-468">Seven digits</span></span> 
    
- <span data-ttu-id="e850d-469">一个字母 (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="e850d-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e850d-470">校验和</span><span class="sxs-lookup"><span data-stu-id="e850d-470">Checksum</span></span>

<span data-ttu-id="e850d-471">不适用</span><span class="sxs-lookup"><span data-stu-id="e850d-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e850d-472">定义</span><span class="sxs-lookup"><span data-stu-id="e850d-472">Definition</span></span>

<span data-ttu-id="e850d-473">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-474">函数`Func_ireland_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e850d-475">找到了中`Keywords_ireland_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="e850d-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e850d-476">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-477">函数`Func_ireland_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e850d-478">关键字</span><span class="sxs-lookup"><span data-stu-id="e850d-478">Keywords</span></span>

#### <a name="keywordsirelandeutaxfilenumber"></a><span data-ttu-id="e850d-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e850d-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="e850d-480">公共服务编号</span><span class="sxs-lookup"><span data-stu-id="e850d-480">public service no</span></span>
  
<span data-ttu-id="e850d-481">个人公开服务编号</span><span class="sxs-lookup"><span data-stu-id="e850d-481">personal public service no</span></span>
  
<span data-ttu-id="e850d-482">pps no</span><span class="sxs-lookup"><span data-stu-id="e850d-482">pps no</span></span>
  
<span data-ttu-id="e850d-483">个人服务编号</span><span class="sxs-lookup"><span data-stu-id="e850d-483">personal service no</span></span>
  
<span data-ttu-id="e850d-484">pps 服务否</span><span class="sxs-lookup"><span data-stu-id="e850d-484">pps service no</span></span>
  
<span data-ttu-id="e850d-485">ppsno#</span><span class="sxs-lookup"><span data-stu-id="e850d-485">ppsno#</span></span>
  
<span data-ttu-id="e850d-486">爱尔兰 pps 否</span><span class="sxs-lookup"><span data-stu-id="e850d-486">irish pps no</span></span>
  
<span data-ttu-id="e850d-487">publicserviceno#</span><span class="sxs-lookup"><span data-stu-id="e850d-487">publicserviceno#</span></span>
  
<span data-ttu-id="e850d-488">个人公开服务号码</span><span class="sxs-lookup"><span data-stu-id="e850d-488">personal public service number</span></span>
  
<span data-ttu-id="e850d-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="e850d-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="e850d-490">pps uimh</span><span class="sxs-lookup"><span data-stu-id="e850d-490">pps uimh</span></span>
  
<span data-ttu-id="e850d-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="e850d-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="e850d-492">意大利</span><span class="sxs-lookup"><span data-stu-id="e850d-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="e850d-493">Format</span><span class="sxs-lookup"><span data-stu-id="e850d-493">Format</span></span>

<span data-ttu-id="e850d-494">指定模式中的16个字母和数字</span><span class="sxs-lookup"><span data-stu-id="e850d-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e850d-495">模式</span><span class="sxs-lookup"><span data-stu-id="e850d-495">Pattern</span></span>

<span data-ttu-id="e850d-496">16个字母和数字:</span><span class="sxs-lookup"><span data-stu-id="e850d-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="e850d-497">与系列名称中的前三个辅音对应的三个字母</span><span class="sxs-lookup"><span data-stu-id="e850d-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="e850d-498">与名字中的第一个、第三个和第四个辅音对应的三个字母</span><span class="sxs-lookup"><span data-stu-id="e850d-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="e850d-499">与出生年份的最后一个数字对应的两个数字</span><span class="sxs-lookup"><span data-stu-id="e850d-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="e850d-500">一个与出生月份相对应的数字 (字母按字母顺序使用), 但仅使用字母 A 到 E、H、L、M、P、R 和 T (因此, 一月为 A, 10 月为 R)</span><span class="sxs-lookup"><span data-stu-id="e850d-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="e850d-501">两个数字, 对应于出生月份中的某一天, 其中40将添加到偶数的出生日, 以区别于奇数</span><span class="sxs-lookup"><span data-stu-id="e850d-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="e850d-502">与某人出生的 municipality 特定的区号相对应的四个数字 (国家/地区代码用于外国国家/地区)</span><span class="sxs-lookup"><span data-stu-id="e850d-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="e850d-503">一个校验位</span><span class="sxs-lookup"><span data-stu-id="e850d-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e850d-504">校验和</span><span class="sxs-lookup"><span data-stu-id="e850d-504">Checksum</span></span>

<span data-ttu-id="e850d-505">是</span><span class="sxs-lookup"><span data-stu-id="e850d-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e850d-506">定义</span><span class="sxs-lookup"><span data-stu-id="e850d-506">Definition</span></span>

<span data-ttu-id="e850d-507">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-508">函数`Func_italy_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e850d-509">找到了中`Keywords_italy_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="e850d-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e850d-510">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-511">函数`Func_italy_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e850d-512">关键字</span><span class="sxs-lookup"><span data-stu-id="e850d-512">Keywords</span></span>

#### <a name="keywordsitalyeutaxfilenumber"></a><span data-ttu-id="e850d-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e850d-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="e850d-514">税号</span><span class="sxs-lookup"><span data-stu-id="e850d-514">tax number</span></span>
  
<span data-ttu-id="e850d-515">纳税编号</span><span class="sxs-lookup"><span data-stu-id="e850d-515">tax no.</span></span>
  
<span data-ttu-id="e850d-516">taxno#</span><span class="sxs-lookup"><span data-stu-id="e850d-516">taxno#</span></span>
  
<span data-ttu-id="e850d-517">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="e850d-517">taxnumber#</span></span>
  
<span data-ttu-id="e850d-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="e850d-518">taxnumber</span></span>
  
<span data-ttu-id="e850d-519">tax id</span><span class="sxs-lookup"><span data-stu-id="e850d-519">tax id</span></span>
  
<span data-ttu-id="e850d-520">taxid#</span><span class="sxs-lookup"><span data-stu-id="e850d-520">taxid#</span></span>
  
<span data-ttu-id="e850d-521">会计代码</span><span class="sxs-lookup"><span data-stu-id="e850d-521">fiscal code</span></span>
  
<span data-ttu-id="e850d-522">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="e850d-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="e850d-523">拉脱维亚</span><span class="sxs-lookup"><span data-stu-id="e850d-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="e850d-524">Format</span><span class="sxs-lookup"><span data-stu-id="e850d-524">Format</span></span>

<span data-ttu-id="e850d-525">11个不带空格或分隔符的数字</span><span class="sxs-lookup"><span data-stu-id="e850d-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e850d-526">模式</span><span class="sxs-lookup"><span data-stu-id="e850d-526">Pattern</span></span>

<span data-ttu-id="e850d-527">指定模式中的11位数</span><span class="sxs-lookup"><span data-stu-id="e850d-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="e850d-528">六个数字, 对应于出生日期 (DDMMYY)</span><span class="sxs-lookup"><span data-stu-id="e850d-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="e850d-529">一个与 "出生世纪" 相对应的数字, 其中 "0" 对应于19世纪, "1" 对应于20世纪, "2" 对应于21世纪。</span><span class="sxs-lookup"><span data-stu-id="e850d-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="e850d-530">四位数字</span><span class="sxs-lookup"><span data-stu-id="e850d-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e850d-531">校验和</span><span class="sxs-lookup"><span data-stu-id="e850d-531">Checksum</span></span>

<span data-ttu-id="e850d-532">是</span><span class="sxs-lookup"><span data-stu-id="e850d-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e850d-533">定义</span><span class="sxs-lookup"><span data-stu-id="e850d-533">Definition</span></span>

<span data-ttu-id="e850d-534">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-535">函数`Func_latvia_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e850d-536">找到了中`Keywords_latvia_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="e850d-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e850d-537">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-538">函数`Func_latvia_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e850d-539">关键字</span><span class="sxs-lookup"><span data-stu-id="e850d-539">Keywords</span></span>

#### <a name="keywordslatviaeutaxfilenumber"></a><span data-ttu-id="e850d-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e850d-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="e850d-541">税号</span><span class="sxs-lookup"><span data-stu-id="e850d-541">tax number</span></span>
  
<span data-ttu-id="e850d-542">纳税编号</span><span class="sxs-lookup"><span data-stu-id="e850d-542">tax no.</span></span>
  
<span data-ttu-id="e850d-543">taxno#</span><span class="sxs-lookup"><span data-stu-id="e850d-543">taxno#</span></span>
  
<span data-ttu-id="e850d-544">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="e850d-544">taxnumber#</span></span>
  
<span data-ttu-id="e850d-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="e850d-545">taxnumber</span></span>
  
<span data-ttu-id="e850d-546">tax id</span><span class="sxs-lookup"><span data-stu-id="e850d-546">tax id</span></span>
  
<span data-ttu-id="e850d-547">taxid#</span><span class="sxs-lookup"><span data-stu-id="e850d-547">taxid#</span></span>
  
<span data-ttu-id="e850d-548">税标识号</span><span class="sxs-lookup"><span data-stu-id="e850d-548">tax identification number</span></span>
  
<span data-ttu-id="e850d-549">税号标识号。</span><span class="sxs-lookup"><span data-stu-id="e850d-549">tax identification no.</span></span>
  
<span data-ttu-id="e850d-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="e850d-550">nodokļa numurs</span></span>
  
<span data-ttu-id="e850d-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="e850d-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="e850d-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="e850d-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="e850d-553">立陶宛</span><span class="sxs-lookup"><span data-stu-id="e850d-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="e850d-554">Format</span><span class="sxs-lookup"><span data-stu-id="e850d-554">Format</span></span>

<span data-ttu-id="e850d-555">11位数, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="e850d-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e850d-556">模式</span><span class="sxs-lookup"><span data-stu-id="e850d-556">Pattern</span></span>

<span data-ttu-id="e850d-557">11 个数字</span><span class="sxs-lookup"><span data-stu-id="e850d-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e850d-558">校验和</span><span class="sxs-lookup"><span data-stu-id="e850d-558">Checksum</span></span>

<span data-ttu-id="e850d-559">不适用</span><span class="sxs-lookup"><span data-stu-id="e850d-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e850d-560">定义</span><span class="sxs-lookup"><span data-stu-id="e850d-560">Definition</span></span>

<span data-ttu-id="e850d-561">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-562">函数`Func_lithuania_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e850d-563">找到了中`Keywords_lithuania_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="e850d-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e850d-564">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-565">函数`Func_lithuania_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e850d-566">关键字</span><span class="sxs-lookup"><span data-stu-id="e850d-566">Keywords</span></span>

#### <a name="keywordslithuaniaeutaxfilenumber"></a><span data-ttu-id="e850d-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e850d-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="e850d-568">税号</span><span class="sxs-lookup"><span data-stu-id="e850d-568">tax number</span></span>
  
<span data-ttu-id="e850d-569">纳税编号</span><span class="sxs-lookup"><span data-stu-id="e850d-569">tax no.</span></span>
  
<span data-ttu-id="e850d-570">税号 (无 #)</span><span class="sxs-lookup"><span data-stu-id="e850d-570">tax no#</span></span>
  
<span data-ttu-id="e850d-571">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="e850d-571">taxnumber#</span></span>
  
<span data-ttu-id="e850d-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="e850d-572">taxnumber</span></span>
  
<span data-ttu-id="e850d-573">tax id</span><span class="sxs-lookup"><span data-stu-id="e850d-573">tax id</span></span>
  
<span data-ttu-id="e850d-574">taxid#</span><span class="sxs-lookup"><span data-stu-id="e850d-574">taxid#</span></span>
  
<span data-ttu-id="e850d-575">税标识号</span><span class="sxs-lookup"><span data-stu-id="e850d-575">tax identification number</span></span>
  
<span data-ttu-id="e850d-576">税号标识号。</span><span class="sxs-lookup"><span data-stu-id="e850d-576">tax identification no.</span></span>
  
<span data-ttu-id="e850d-577">mokesčių id</span><span class="sxs-lookup"><span data-stu-id="e850d-577">mokesčių id</span></span>
  
<span data-ttu-id="e850d-578">mokesčių numeris</span><span class="sxs-lookup"><span data-stu-id="e850d-578">mokesčių numeris</span></span>
  
<span data-ttu-id="e850d-579">mokesčių identifikavimas numeris</span><span class="sxs-lookup"><span data-stu-id="e850d-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="e850d-580">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="e850d-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="e850d-581">Format</span><span class="sxs-lookup"><span data-stu-id="e850d-581">Format</span></span>

<span data-ttu-id="e850d-582">13个不带空格或分隔符的数字</span><span class="sxs-lookup"><span data-stu-id="e850d-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e850d-583">模式</span><span class="sxs-lookup"><span data-stu-id="e850d-583">Pattern</span></span>

<span data-ttu-id="e850d-584">13 个数字：</span><span class="sxs-lookup"><span data-stu-id="e850d-584">13 digits:</span></span>
  
-  <span data-ttu-id="e850d-585">11 个数字</span><span class="sxs-lookup"><span data-stu-id="e850d-585">11 digits</span></span> 
    
- <span data-ttu-id="e850d-586">两个校验位</span><span class="sxs-lookup"><span data-stu-id="e850d-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e850d-587">校验和</span><span class="sxs-lookup"><span data-stu-id="e850d-587">Checksum</span></span>

<span data-ttu-id="e850d-588">是</span><span class="sxs-lookup"><span data-stu-id="e850d-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e850d-589">定义</span><span class="sxs-lookup"><span data-stu-id="e850d-589">Definition</span></span>

<span data-ttu-id="e850d-590">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-591">函数`Func_luxemburg_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e850d-592">找到了中`Keywords_luxemburg_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="e850d-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e850d-593">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-594">函数`Func_luxemburg_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e850d-595">关键字</span><span class="sxs-lookup"><span data-stu-id="e850d-595">Keywords</span></span>

#### <a name="keywordsluxemburgeutaxfilenumber"></a><span data-ttu-id="e850d-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e850d-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="e850d-597">税号</span><span class="sxs-lookup"><span data-stu-id="e850d-597">tax number</span></span>
  
<span data-ttu-id="e850d-598">纳税编号</span><span class="sxs-lookup"><span data-stu-id="e850d-598">tax no.</span></span>
  
<span data-ttu-id="e850d-599">taxno#</span><span class="sxs-lookup"><span data-stu-id="e850d-599">taxno#</span></span>
  
<span data-ttu-id="e850d-600">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="e850d-600">taxnumber#</span></span>
  
<span data-ttu-id="e850d-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="e850d-601">taxnumber</span></span>
  
<span data-ttu-id="e850d-602">tax id</span><span class="sxs-lookup"><span data-stu-id="e850d-602">tax id</span></span>
  
<span data-ttu-id="e850d-603">taxid#</span><span class="sxs-lookup"><span data-stu-id="e850d-603">taxid#</span></span>
  
<span data-ttu-id="e850d-604">税标识号</span><span class="sxs-lookup"><span data-stu-id="e850d-604">tax identification number</span></span>
  
<span data-ttu-id="e850d-605">税号标识号。</span><span class="sxs-lookup"><span data-stu-id="e850d-605">tax identification no.</span></span>
  
<span data-ttu-id="e850d-606">steuernummer</span><span class="sxs-lookup"><span data-stu-id="e850d-606">steuernummer</span></span>
  
<span data-ttu-id="e850d-607">steuer id</span><span class="sxs-lookup"><span data-stu-id="e850d-607">steuer id</span></span>
  
<span data-ttu-id="e850d-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="e850d-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="e850d-609">马耳他</span><span class="sxs-lookup"><span data-stu-id="e850d-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="e850d-610">Format</span><span class="sxs-lookup"><span data-stu-id="e850d-610">Format</span></span>

<span data-ttu-id="e850d-611">对于马耳他 nationals: 7 位数和指定模式中的一个字母</span><span class="sxs-lookup"><span data-stu-id="e850d-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="e850d-612">非马耳他语 nationals 和马耳他语实体: 9 个数字</span><span class="sxs-lookup"><span data-stu-id="e850d-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e850d-613">模式</span><span class="sxs-lookup"><span data-stu-id="e850d-613">Pattern</span></span>

<span data-ttu-id="e850d-614">马耳他 nationals: 7 个数字和一个字母</span><span class="sxs-lookup"><span data-stu-id="e850d-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="e850d-615">七个数字 </span><span class="sxs-lookup"><span data-stu-id="e850d-615">Seven digits</span></span> 
    
- <span data-ttu-id="e850d-616">一个字母 (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="e850d-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="e850d-617">非马耳他语 nationals 和马耳他语实体: 9 个数字</span><span class="sxs-lookup"><span data-stu-id="e850d-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="e850d-618">九个数字</span><span class="sxs-lookup"><span data-stu-id="e850d-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e850d-619">校验和</span><span class="sxs-lookup"><span data-stu-id="e850d-619">Checksum</span></span>

<span data-ttu-id="e850d-620">不适用</span><span class="sxs-lookup"><span data-stu-id="e850d-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e850d-621">定义</span><span class="sxs-lookup"><span data-stu-id="e850d-621">Definition</span></span>

<span data-ttu-id="e850d-622">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-623">函数`Func_malta_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e850d-624">找到了中`Keywords_malta_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="e850d-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e850d-625">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-626">函数`Func_malta_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e850d-627">关键字</span><span class="sxs-lookup"><span data-stu-id="e850d-627">Keywords</span></span>

#### <a name="keywordsmaltaeutaxfilenumber"></a><span data-ttu-id="e850d-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e850d-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="e850d-629">税号</span><span class="sxs-lookup"><span data-stu-id="e850d-629">tax number</span></span>
  
<span data-ttu-id="e850d-630">纳税编号</span><span class="sxs-lookup"><span data-stu-id="e850d-630">tax no.</span></span>
  
<span data-ttu-id="e850d-631">taxno#</span><span class="sxs-lookup"><span data-stu-id="e850d-631">taxno#</span></span>
  
<span data-ttu-id="e850d-632">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="e850d-632">taxnumber#</span></span>
  
<span data-ttu-id="e850d-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="e850d-633">taxnumber</span></span>
  
<span data-ttu-id="e850d-634">tax id</span><span class="sxs-lookup"><span data-stu-id="e850d-634">tax id</span></span>
  
<span data-ttu-id="e850d-635">taxid#</span><span class="sxs-lookup"><span data-stu-id="e850d-635">taxid#</span></span>
  
<span data-ttu-id="e850d-636">税标识号</span><span class="sxs-lookup"><span data-stu-id="e850d-636">tax identification number</span></span>
  
<span data-ttu-id="e850d-637">税号标识号。</span><span class="sxs-lookup"><span data-stu-id="e850d-637">tax identification no.</span></span>
  
<span data-ttu-id="e850d-638">numru tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="e850d-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="e850d-639">id tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="e850d-639">id tat-taxxa</span></span>
  
<span data-ttu-id="e850d-640">numru ta "identifikazzjoni tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="e850d-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="e850d-641">荷兰</span><span class="sxs-lookup"><span data-stu-id="e850d-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="e850d-642">Format</span><span class="sxs-lookup"><span data-stu-id="e850d-642">Format</span></span>

<span data-ttu-id="e850d-643">9个数字, 不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="e850d-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e850d-644">模式</span><span class="sxs-lookup"><span data-stu-id="e850d-644">Pattern</span></span>

<span data-ttu-id="e850d-645">九个数字</span><span class="sxs-lookup"><span data-stu-id="e850d-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="e850d-646">校验和</span><span class="sxs-lookup"><span data-stu-id="e850d-646">Checksum</span></span>

<span data-ttu-id="e850d-647">是</span><span class="sxs-lookup"><span data-stu-id="e850d-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e850d-648">定义</span><span class="sxs-lookup"><span data-stu-id="e850d-648">Definition</span></span>

<span data-ttu-id="e850d-649">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-650">函数`Func_netherlands_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e850d-651">找到了中`Keywords_netherlands_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="e850d-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e850d-652">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-653">函数`Func_netherlands_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e850d-654">关键字</span><span class="sxs-lookup"><span data-stu-id="e850d-654">Keywords</span></span>

#### <a name="keywordsnetherlandseutaxfilenumber"></a><span data-ttu-id="e850d-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e850d-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="e850d-656">荷兰税标识号</span><span class="sxs-lookup"><span data-stu-id="e850d-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="e850d-657">荷兰税务标识</span><span class="sxs-lookup"><span data-stu-id="e850d-657">netherlands tax identification</span></span>
  
<span data-ttu-id="e850d-658">netherland 的税标识号</span><span class="sxs-lookup"><span data-stu-id="e850d-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="e850d-659">netherland 的税标识</span><span class="sxs-lookup"><span data-stu-id="e850d-659">netherland's tax identification</span></span>
  
<span data-ttu-id="e850d-660">税标识号</span><span class="sxs-lookup"><span data-stu-id="e850d-660">tax identification number</span></span>
  
<span data-ttu-id="e850d-661">荷兰税号</span><span class="sxs-lookup"><span data-stu-id="e850d-661">dutch tax id</span></span>
  
<span data-ttu-id="e850d-662">荷兰纳税标识号</span><span class="sxs-lookup"><span data-stu-id="e850d-662">dutch tax identification number</span></span>
  
<span data-ttu-id="e850d-663">tax id</span><span class="sxs-lookup"><span data-stu-id="e850d-663">tax id</span></span>
  
<span data-ttu-id="e850d-664">税号 #</span><span class="sxs-lookup"><span data-stu-id="e850d-664">tax id#</span></span>
  
<span data-ttu-id="e850d-665">税号</span><span class="sxs-lookup"><span data-stu-id="e850d-665">tax number</span></span>
  
<span data-ttu-id="e850d-666">税号 (无 #)</span><span class="sxs-lookup"><span data-stu-id="e850d-666">tax no#</span></span>
  
<span data-ttu-id="e850d-667">税种</span><span class="sxs-lookup"><span data-stu-id="e850d-667">tax#</span></span>
  
<span data-ttu-id="e850d-668">锡</span><span class="sxs-lookup"><span data-stu-id="e850d-668">tin</span></span>
  
<span data-ttu-id="e850d-669">锡</span><span class="sxs-lookup"><span data-stu-id="e850d-669">tin#</span></span>
  
<span data-ttu-id="e850d-670">荷属安的纳税人标识号</span><span class="sxs-lookup"><span data-stu-id="e850d-670">netherlands tin</span></span>
  
<span data-ttu-id="e850d-671">netherland 的纳税人标识号</span><span class="sxs-lookup"><span data-stu-id="e850d-671">netherland's tin</span></span>
  
<span data-ttu-id="e850d-672">荷兰语 belasting identificatienummer</span><span class="sxs-lookup"><span data-stu-id="e850d-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="e850d-673">identificatienummer van belasting</span><span class="sxs-lookup"><span data-stu-id="e850d-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="e850d-674">identificatienummer belasting</span><span class="sxs-lookup"><span data-stu-id="e850d-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="e850d-675">荷兰语 belasting identificatie</span><span class="sxs-lookup"><span data-stu-id="e850d-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="e850d-676">荷兰语 belasting id nummer</span><span class="sxs-lookup"><span data-stu-id="e850d-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="e850d-677">荷兰语 belastingnummer</span><span class="sxs-lookup"><span data-stu-id="e850d-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="e850d-678">btw nummer</span><span class="sxs-lookup"><span data-stu-id="e850d-678">btw nummer</span></span>
  
<span data-ttu-id="e850d-679">nederlandse belasting identificatie</span><span class="sxs-lookup"><span data-stu-id="e850d-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="e850d-680">波兰</span><span class="sxs-lookup"><span data-stu-id="e850d-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="e850d-681">Format</span><span class="sxs-lookup"><span data-stu-id="e850d-681">Format</span></span>

<span data-ttu-id="e850d-682">不带空格或分隔符的11个数字</span><span class="sxs-lookup"><span data-stu-id="e850d-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e850d-683">模式</span><span class="sxs-lookup"><span data-stu-id="e850d-683">Pattern</span></span>

<span data-ttu-id="e850d-684">11位数字</span><span class="sxs-lookup"><span data-stu-id="e850d-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e850d-685">校验和</span><span class="sxs-lookup"><span data-stu-id="e850d-685">Checksum</span></span>

<span data-ttu-id="e850d-686">是</span><span class="sxs-lookup"><span data-stu-id="e850d-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e850d-687">定义</span><span class="sxs-lookup"><span data-stu-id="e850d-687">Definition</span></span>

<span data-ttu-id="e850d-688">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-689">函数`Func_poland_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e850d-690">找到了中`Keywords_poland_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="e850d-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e850d-691">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-692">函数`Func_poland_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e850d-693">关键字</span><span class="sxs-lookup"><span data-stu-id="e850d-693">Keywords</span></span>

#### <a name="keywordspolandeutaxfilenumber"></a><span data-ttu-id="e850d-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e850d-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="e850d-695">税号</span><span class="sxs-lookup"><span data-stu-id="e850d-695">tax number</span></span>
  
<span data-ttu-id="e850d-696">纳税编号</span><span class="sxs-lookup"><span data-stu-id="e850d-696">tax no.</span></span>
  
<span data-ttu-id="e850d-697">taxno#</span><span class="sxs-lookup"><span data-stu-id="e850d-697">taxno#</span></span>
  
<span data-ttu-id="e850d-698">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="e850d-698">taxnumber#</span></span>
  
<span data-ttu-id="e850d-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="e850d-699">taxnumber</span></span>
  
<span data-ttu-id="e850d-700">nip</span><span class="sxs-lookup"><span data-stu-id="e850d-700">nip</span></span>
  
<span data-ttu-id="e850d-701">nip#</span><span class="sxs-lookup"><span data-stu-id="e850d-701">nip#</span></span>
  
<span data-ttu-id="e850d-702">tax id</span><span class="sxs-lookup"><span data-stu-id="e850d-702">tax id</span></span>
  
<span data-ttu-id="e850d-703">税号 #</span><span class="sxs-lookup"><span data-stu-id="e850d-703">tax id#</span></span>
  
<span data-ttu-id="e850d-704">nip id</span><span class="sxs-lookup"><span data-stu-id="e850d-704">nip id</span></span>
  
<span data-ttu-id="e850d-705">nip id #</span><span class="sxs-lookup"><span data-stu-id="e850d-705">nip id#</span></span>
  
<span data-ttu-id="e850d-706">税标识号</span><span class="sxs-lookup"><span data-stu-id="e850d-706">tax identification number</span></span>
  
<span data-ttu-id="e850d-707">税号标识号。</span><span class="sxs-lookup"><span data-stu-id="e850d-707">tax identification no.</span></span>
  
<span data-ttu-id="e850d-708">vat 号码</span><span class="sxs-lookup"><span data-stu-id="e850d-708">vat number</span></span>
  
<span data-ttu-id="e850d-709">vat 编号</span><span class="sxs-lookup"><span data-stu-id="e850d-709">vat no.</span></span>
  
<span data-ttu-id="e850d-710">vatno#</span><span class="sxs-lookup"><span data-stu-id="e850d-710">vatno#</span></span>
  
<span data-ttu-id="e850d-711">vat id</span><span class="sxs-lookup"><span data-stu-id="e850d-711">vat id</span></span>
  
<span data-ttu-id="e850d-712">vat id #</span><span class="sxs-lookup"><span data-stu-id="e850d-712">vat id#</span></span>
  
<span data-ttu-id="e850d-713">器 identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="e850d-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="e850d-714">polski 器 identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="e850d-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="e850d-715">numeridentyfikacjipodatkowej#</span><span class="sxs-lookup"><span data-stu-id="e850d-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="e850d-716">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="e850d-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="e850d-717">Format</span><span class="sxs-lookup"><span data-stu-id="e850d-717">Format</span></span>

<span data-ttu-id="e850d-718">9个不带空格或分隔符的数字</span><span class="sxs-lookup"><span data-stu-id="e850d-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e850d-719">模式</span><span class="sxs-lookup"><span data-stu-id="e850d-719">Pattern</span></span>

<span data-ttu-id="e850d-720">九个数字</span><span class="sxs-lookup"><span data-stu-id="e850d-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e850d-721">校验和</span><span class="sxs-lookup"><span data-stu-id="e850d-721">Checksum</span></span>

<span data-ttu-id="e850d-722">是</span><span class="sxs-lookup"><span data-stu-id="e850d-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e850d-723">定义</span><span class="sxs-lookup"><span data-stu-id="e850d-723">Definition</span></span>

<span data-ttu-id="e850d-724">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-725">函数`Func_portugal_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e850d-726">找到了中`Keywords_portugal_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="e850d-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e850d-727">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-728">函数`Func_portugal_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e850d-729">关键字</span><span class="sxs-lookup"><span data-stu-id="e850d-729">Keywords</span></span>

#### <a name="keywordsportugaleutaxfilenumber"></a><span data-ttu-id="e850d-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e850d-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="e850d-731">税号</span><span class="sxs-lookup"><span data-stu-id="e850d-731">tax number</span></span>
  
<span data-ttu-id="e850d-732">纳税编号</span><span class="sxs-lookup"><span data-stu-id="e850d-732">tax no.</span></span>
  
<span data-ttu-id="e850d-733">taxno#</span><span class="sxs-lookup"><span data-stu-id="e850d-733">taxno#</span></span>
  
<span data-ttu-id="e850d-734">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="e850d-734">taxnumber#</span></span>
  
<span data-ttu-id="e850d-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="e850d-735">taxnumber</span></span>
  
<span data-ttu-id="e850d-736">\n\n</span><span class="sxs-lookup"><span data-stu-id="e850d-736">nif</span></span>
  
<span data-ttu-id="e850d-737">\n\n</span><span class="sxs-lookup"><span data-stu-id="e850d-737">nif#</span></span>
  
<span data-ttu-id="e850d-738">numero 会计</span><span class="sxs-lookup"><span data-stu-id="e850d-738">numero fiscal</span></span>
  
<span data-ttu-id="e850d-739">número de identificação 会计</span><span class="sxs-lookup"><span data-stu-id="e850d-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="e850d-740">罗马尼亚</span><span class="sxs-lookup"><span data-stu-id="e850d-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="e850d-741">Format</span><span class="sxs-lookup"><span data-stu-id="e850d-741">Format</span></span>

<span data-ttu-id="e850d-742">13个不带空格或分隔符的数字</span><span class="sxs-lookup"><span data-stu-id="e850d-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e850d-743">模式</span><span class="sxs-lookup"><span data-stu-id="e850d-743">Pattern</span></span>

<span data-ttu-id="e850d-744">13 位数字</span><span class="sxs-lookup"><span data-stu-id="e850d-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e850d-745">校验和</span><span class="sxs-lookup"><span data-stu-id="e850d-745">Checksum</span></span>

<span data-ttu-id="e850d-746">不适用</span><span class="sxs-lookup"><span data-stu-id="e850d-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e850d-747">定义</span><span class="sxs-lookup"><span data-stu-id="e850d-747">Definition</span></span>

<span data-ttu-id="e850d-748">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-749">正则表达式`Regex_romania_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e850d-750">找到了中`Keywords_romania_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="e850d-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e850d-751">关键字</span><span class="sxs-lookup"><span data-stu-id="e850d-751">Keywords</span></span>

#### <a name="keywordsromaniaeutaxfilenumber"></a><span data-ttu-id="e850d-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e850d-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="e850d-753">tax id</span><span class="sxs-lookup"><span data-stu-id="e850d-753">tax id</span></span>
  
<span data-ttu-id="e850d-754">税务 id 号</span><span class="sxs-lookup"><span data-stu-id="e850d-754">tax id number</span></span>
  
<span data-ttu-id="e850d-755">税文件编号</span><span class="sxs-lookup"><span data-stu-id="e850d-755">tax file no</span></span>
  
<span data-ttu-id="e850d-756">tax file number</span><span class="sxs-lookup"><span data-stu-id="e850d-756">tax file number</span></span>
  
<span data-ttu-id="e850d-757">免税</span><span class="sxs-lookup"><span data-stu-id="e850d-757">tax no</span></span>
  
<span data-ttu-id="e850d-758">税号</span><span class="sxs-lookup"><span data-stu-id="e850d-758">tax number</span></span>
  
<span data-ttu-id="e850d-759">taxid#</span><span class="sxs-lookup"><span data-stu-id="e850d-759">taxid#</span></span>
  
<span data-ttu-id="e850d-760">taxno#</span><span class="sxs-lookup"><span data-stu-id="e850d-760">taxno#</span></span>
  
<span data-ttu-id="e850d-761">id-ul taxei</span><span class="sxs-lookup"><span data-stu-id="e850d-761">id-ul taxei</span></span>
  
<span data-ttu-id="e850d-762">numărul de identificare fiscală</span><span class="sxs-lookup"><span data-stu-id="e850d-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="e850d-763">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="e850d-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="e850d-764">Format</span><span class="sxs-lookup"><span data-stu-id="e850d-764">Format</span></span>

<span data-ttu-id="e850d-765">10个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="e850d-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e850d-766">模式</span><span class="sxs-lookup"><span data-stu-id="e850d-766">Pattern</span></span>

<span data-ttu-id="e850d-767">10 个数字</span><span class="sxs-lookup"><span data-stu-id="e850d-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e850d-768">校验和</span><span class="sxs-lookup"><span data-stu-id="e850d-768">Checksum</span></span>

<span data-ttu-id="e850d-769">不适用</span><span class="sxs-lookup"><span data-stu-id="e850d-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e850d-770">定义</span><span class="sxs-lookup"><span data-stu-id="e850d-770">Definition</span></span>

<span data-ttu-id="e850d-771">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-772">正则表达式`Regex_slovakia_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e850d-773">找到了中`Keywords_slovakia_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="e850d-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e850d-774">关键字</span><span class="sxs-lookup"><span data-stu-id="e850d-774">Keywords</span></span>

#### <a name="keywordsslovakiaeutaxfilenumber"></a><span data-ttu-id="e850d-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e850d-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="e850d-776">tax id</span><span class="sxs-lookup"><span data-stu-id="e850d-776">tax id</span></span>
  
<span data-ttu-id="e850d-777">税务 id 号</span><span class="sxs-lookup"><span data-stu-id="e850d-777">tax id number</span></span>
  
<span data-ttu-id="e850d-778">纳税人 id</span><span class="sxs-lookup"><span data-stu-id="e850d-778">tin id</span></span>
  
<span data-ttu-id="e850d-779">tin 编号</span><span class="sxs-lookup"><span data-stu-id="e850d-779">tin no</span></span>
  
<span data-ttu-id="e850d-780">斯洛伐克纳税人标识号 id</span><span class="sxs-lookup"><span data-stu-id="e850d-780">slovakian tin id</span></span>
  
<span data-ttu-id="e850d-781">锡</span><span class="sxs-lookup"><span data-stu-id="e850d-781">tin</span></span>
  
<span data-ttu-id="e850d-782">税文件编号</span><span class="sxs-lookup"><span data-stu-id="e850d-782">tax file no</span></span>
  
<span data-ttu-id="e850d-783">tax file number</span><span class="sxs-lookup"><span data-stu-id="e850d-783">tax file number</span></span>
  
<span data-ttu-id="e850d-784">免税</span><span class="sxs-lookup"><span data-stu-id="e850d-784">tax no</span></span>
  
<span data-ttu-id="e850d-785">税号</span><span class="sxs-lookup"><span data-stu-id="e850d-785">tax number</span></span>
  
<span data-ttu-id="e850d-786">taxid#</span><span class="sxs-lookup"><span data-stu-id="e850d-786">taxid#</span></span>
  
<span data-ttu-id="e850d-787">taxno#</span><span class="sxs-lookup"><span data-stu-id="e850d-787">taxno#</span></span>
  
<span data-ttu-id="e850d-788">daňové identifikačné číslo</span><span class="sxs-lookup"><span data-stu-id="e850d-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="e850d-789">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="e850d-789">daňové číslo</span></span>
  
<span data-ttu-id="e850d-790">daňové číslo súboru</span><span class="sxs-lookup"><span data-stu-id="e850d-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="e850d-791">斯洛文尼亚</span><span class="sxs-lookup"><span data-stu-id="e850d-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="e850d-792">Format</span><span class="sxs-lookup"><span data-stu-id="e850d-792">Format</span></span>

<span data-ttu-id="e850d-793">8位数, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="e850d-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e850d-794">模式</span><span class="sxs-lookup"><span data-stu-id="e850d-794">Pattern</span></span>

<span data-ttu-id="e850d-795">八个数字</span><span class="sxs-lookup"><span data-stu-id="e850d-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e850d-796">校验和</span><span class="sxs-lookup"><span data-stu-id="e850d-796">Checksum</span></span>

<span data-ttu-id="e850d-797">是</span><span class="sxs-lookup"><span data-stu-id="e850d-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e850d-798">定义</span><span class="sxs-lookup"><span data-stu-id="e850d-798">Definition</span></span>

<span data-ttu-id="e850d-799">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-800">函数`Func_slovenia_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e850d-801">找到了中`Keywords_slovenia_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="e850d-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e850d-802">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-803">函数`Func_slovenia_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e850d-804">关键字</span><span class="sxs-lookup"><span data-stu-id="e850d-804">Keywords</span></span>

#### <a name="keywordssloveniaeutaxfilenumber"></a><span data-ttu-id="e850d-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e850d-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="e850d-806">tax id</span><span class="sxs-lookup"><span data-stu-id="e850d-806">tax id</span></span>
  
<span data-ttu-id="e850d-807">税务 id 号</span><span class="sxs-lookup"><span data-stu-id="e850d-807">tax id number</span></span>
  
<span data-ttu-id="e850d-808">纳税人 id</span><span class="sxs-lookup"><span data-stu-id="e850d-808">tin id</span></span>
  
<span data-ttu-id="e850d-809">tin 编号</span><span class="sxs-lookup"><span data-stu-id="e850d-809">tin no</span></span>
  
<span data-ttu-id="e850d-810">斯洛文尼亚纳税人标识号 id</span><span class="sxs-lookup"><span data-stu-id="e850d-810">slovenian tin id</span></span>
  
<span data-ttu-id="e850d-811">锡</span><span class="sxs-lookup"><span data-stu-id="e850d-811">tin</span></span>
  
<span data-ttu-id="e850d-812">税文件编号</span><span class="sxs-lookup"><span data-stu-id="e850d-812">tax file no</span></span>
  
<span data-ttu-id="e850d-813">tax file number</span><span class="sxs-lookup"><span data-stu-id="e850d-813">tax file number</span></span>
  
<span data-ttu-id="e850d-814">免税</span><span class="sxs-lookup"><span data-stu-id="e850d-814">tax no</span></span>
  
<span data-ttu-id="e850d-815">税号</span><span class="sxs-lookup"><span data-stu-id="e850d-815">tax number</span></span>
  
<span data-ttu-id="e850d-816">taxid#</span><span class="sxs-lookup"><span data-stu-id="e850d-816">taxid#</span></span>
  
<span data-ttu-id="e850d-817">taxno#</span><span class="sxs-lookup"><span data-stu-id="e850d-817">taxno#</span></span>
  
<span data-ttu-id="e850d-818">identifikacijska številka davka</span><span class="sxs-lookup"><span data-stu-id="e850d-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="e850d-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="e850d-819">davčna številka</span></span>
  
<span data-ttu-id="e850d-820">številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="e850d-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="e850d-821">西班牙</span><span class="sxs-lookup"><span data-stu-id="e850d-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="e850d-822">Format</span><span class="sxs-lookup"><span data-stu-id="e850d-822">Format</span></span>

<span data-ttu-id="e850d-823">七个或8个数字以及指定模式中的一个或两个字母</span><span class="sxs-lookup"><span data-stu-id="e850d-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e850d-824">模式</span><span class="sxs-lookup"><span data-stu-id="e850d-824">Pattern</span></span>

<span data-ttu-id="e850d-825">具有西班牙国家标识卡片的西班牙语自然人:</span><span class="sxs-lookup"><span data-stu-id="e850d-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="e850d-826">八个数字</span><span class="sxs-lookup"><span data-stu-id="e850d-826">Eight digits</span></span> 
    
- <span data-ttu-id="e850d-827">一个大写字母 (区分大小写)</span><span class="sxs-lookup"><span data-stu-id="e850d-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="e850d-828">不包含西班牙国家的非居民 Spaniards 国家标识卡片</span><span class="sxs-lookup"><span data-stu-id="e850d-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="e850d-829">一个大写字母 "L" (区分大小写)</span><span class="sxs-lookup"><span data-stu-id="e850d-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="e850d-830">七个数字 </span><span class="sxs-lookup"><span data-stu-id="e850d-830">Seven digits</span></span>
    
- <span data-ttu-id="e850d-831">一个大写字母 (区分大小写)</span><span class="sxs-lookup"><span data-stu-id="e850d-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="e850d-832">在没有西班牙国内身份证的14年年龄下的居民 Spaniards:</span><span class="sxs-lookup"><span data-stu-id="e850d-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="e850d-833">一个大写字母 "K" (区分大小写)</span><span class="sxs-lookup"><span data-stu-id="e850d-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="e850d-834">七个数字 </span><span class="sxs-lookup"><span data-stu-id="e850d-834">Seven digits</span></span> 
    
- <span data-ttu-id="e850d-835">一个大写字母 (区分大小写)</span><span class="sxs-lookup"><span data-stu-id="e850d-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="e850d-836">带有 Foreigner 标识号的 Foreigners</span><span class="sxs-lookup"><span data-stu-id="e850d-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="e850d-837">一个大写的字母, 为 "X"、"Y" 或 "Z" (区分大小写)</span><span class="sxs-lookup"><span data-stu-id="e850d-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="e850d-838">七个数字 </span><span class="sxs-lookup"><span data-stu-id="e850d-838">Seven digits</span></span>
    
- <span data-ttu-id="e850d-839">一个大写字母 (区分大小写)</span><span class="sxs-lookup"><span data-stu-id="e850d-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="e850d-840">没有 Foreigner 标识号的 Foreigners</span><span class="sxs-lookup"><span data-stu-id="e850d-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="e850d-841">一个大写的字母 "M" (区分大小写)</span><span class="sxs-lookup"><span data-stu-id="e850d-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="e850d-842">七个数字 </span><span class="sxs-lookup"><span data-stu-id="e850d-842">Seven digits</span></span>
    
- <span data-ttu-id="e850d-843">一个大写字母 (区分大小写)</span><span class="sxs-lookup"><span data-stu-id="e850d-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e850d-844">校验和</span><span class="sxs-lookup"><span data-stu-id="e850d-844">Checksum</span></span>

<span data-ttu-id="e850d-845">是</span><span class="sxs-lookup"><span data-stu-id="e850d-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e850d-846">定义</span><span class="sxs-lookup"><span data-stu-id="e850d-846">Definition</span></span>

<span data-ttu-id="e850d-847">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-848">函数`Func_spain_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e850d-849">找到了中`Keywords_spain_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="e850d-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e850d-850">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-851">函数`Func_spain_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e850d-852">关键字</span><span class="sxs-lookup"><span data-stu-id="e850d-852">Keywords</span></span>

#### <a name="keywordsspaineutaxfilenumber"></a><span data-ttu-id="e850d-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e850d-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="e850d-854">tax id</span><span class="sxs-lookup"><span data-stu-id="e850d-854">tax id</span></span>
  
<span data-ttu-id="e850d-855">税务 id 号</span><span class="sxs-lookup"><span data-stu-id="e850d-855">tax id number</span></span>
  
<span data-ttu-id="e850d-856">cif id</span><span class="sxs-lookup"><span data-stu-id="e850d-856">cif id</span></span>
  
<span data-ttu-id="e850d-857">cif no</span><span class="sxs-lookup"><span data-stu-id="e850d-857">cif no</span></span>
  
<span data-ttu-id="e850d-858">西班牙语 cif id</span><span class="sxs-lookup"><span data-stu-id="e850d-858">spanish cif id</span></span>
  
<span data-ttu-id="e850d-859">cif</span><span class="sxs-lookup"><span data-stu-id="e850d-859">cif</span></span>
  
<span data-ttu-id="e850d-860">税文件编号</span><span class="sxs-lookup"><span data-stu-id="e850d-860">tax file no</span></span>
  
<span data-ttu-id="e850d-861">西班牙语 cif 号码</span><span class="sxs-lookup"><span data-stu-id="e850d-861">spanish cif number</span></span>
  
<span data-ttu-id="e850d-862">tax file number</span><span class="sxs-lookup"><span data-stu-id="e850d-862">tax file number</span></span>
  
<span data-ttu-id="e850d-863">西班牙语 cif no</span><span class="sxs-lookup"><span data-stu-id="e850d-863">spanish cif no</span></span>
  
<span data-ttu-id="e850d-864">免税</span><span class="sxs-lookup"><span data-stu-id="e850d-864">tax no</span></span>
  
<span data-ttu-id="e850d-865">税号</span><span class="sxs-lookup"><span data-stu-id="e850d-865">tax number</span></span>
  
<span data-ttu-id="e850d-866">taxid#</span><span class="sxs-lookup"><span data-stu-id="e850d-866">taxid#</span></span>
  
<span data-ttu-id="e850d-867">taxno#</span><span class="sxs-lookup"><span data-stu-id="e850d-867">taxno#</span></span>
  
<span data-ttu-id="e850d-868">cifid#</span><span class="sxs-lookup"><span data-stu-id="e850d-868">cifid#</span></span>
  
<span data-ttu-id="e850d-869">spanishcifid#</span><span class="sxs-lookup"><span data-stu-id="e850d-869">spanishcifid#</span></span>
  
<span data-ttu-id="e850d-870">spanishcifno#</span><span class="sxs-lookup"><span data-stu-id="e850d-870">spanishcifno#</span></span>
  
<span data-ttu-id="e850d-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="e850d-871">número de contribuyente</span></span>
  
<span data-ttu-id="e850d-872">número de impuesto corporativo</span><span class="sxs-lookup"><span data-stu-id="e850d-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="e850d-873">número de identificación 会计</span><span class="sxs-lookup"><span data-stu-id="e850d-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="e850d-874">cif número</span><span class="sxs-lookup"><span data-stu-id="e850d-874">cif número</span></span>
  
<span data-ttu-id="e850d-875">cifnúmero#</span><span class="sxs-lookup"><span data-stu-id="e850d-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="e850d-876">瑞典</span><span class="sxs-lookup"><span data-stu-id="e850d-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="e850d-877">Format</span><span class="sxs-lookup"><span data-stu-id="e850d-877">Format</span></span>

<span data-ttu-id="e850d-878">10个数字和指定模式中的符号</span><span class="sxs-lookup"><span data-stu-id="e850d-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e850d-879">模式</span><span class="sxs-lookup"><span data-stu-id="e850d-879">Pattern</span></span>

<span data-ttu-id="e850d-880">10个数字和一个符号:</span><span class="sxs-lookup"><span data-stu-id="e850d-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="e850d-881">与出生日期对应的6个数字 (YYMMDD)</span><span class="sxs-lookup"><span data-stu-id="e850d-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="e850d-882">加号、减号或反斜杠</span><span class="sxs-lookup"><span data-stu-id="e850d-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="e850d-883">在以下位置使标识号唯一的三个数字:</span><span class="sxs-lookup"><span data-stu-id="e850d-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="e850d-884">对于在1990之前发出的号码, 第七和第八位数字标识出生的县或外部人</span><span class="sxs-lookup"><span data-stu-id="e850d-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="e850d-885">第九个位置中的数字表示为奇数或甚至是女的性别</span><span class="sxs-lookup"><span data-stu-id="e850d-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="e850d-886">一个校验位</span><span class="sxs-lookup"><span data-stu-id="e850d-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e850d-887">校验和</span><span class="sxs-lookup"><span data-stu-id="e850d-887">Checksum</span></span>

<span data-ttu-id="e850d-888">是</span><span class="sxs-lookup"><span data-stu-id="e850d-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e850d-889">定义</span><span class="sxs-lookup"><span data-stu-id="e850d-889">Definition</span></span>

<span data-ttu-id="e850d-890">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-891">函数`Func_sweden_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e850d-892">找到了中`Keywords_sweden_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="e850d-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e850d-893">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-894">函数`Func_sweden_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e850d-895">关键字</span><span class="sxs-lookup"><span data-stu-id="e850d-895">Keywords</span></span>

#### <a name="keywordsswedeneutaxfilenumber"></a><span data-ttu-id="e850d-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e850d-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="e850d-897">tax id</span><span class="sxs-lookup"><span data-stu-id="e850d-897">tax id</span></span>
  
<span data-ttu-id="e850d-898">税号编号</span><span class="sxs-lookup"><span data-stu-id="e850d-898">tax id no.</span></span>
  
<span data-ttu-id="e850d-899">税务 id 号</span><span class="sxs-lookup"><span data-stu-id="e850d-899">tax id number</span></span>
  
<span data-ttu-id="e850d-900">tax identification</span><span class="sxs-lookup"><span data-stu-id="e850d-900">tax identification</span></span>
  
<span data-ttu-id="e850d-901">纳税标识号</span><span class="sxs-lookup"><span data-stu-id="e850d-901">tax identification#</span></span>
  
<span data-ttu-id="e850d-902">纳税编号</span><span class="sxs-lookup"><span data-stu-id="e850d-902">tax no.</span></span>
  
<span data-ttu-id="e850d-903">税种</span><span class="sxs-lookup"><span data-stu-id="e850d-903">tax#</span></span>
  
<span data-ttu-id="e850d-904">taxid#</span><span class="sxs-lookup"><span data-stu-id="e850d-904">taxid#</span></span>
  
<span data-ttu-id="e850d-905">税文件</span><span class="sxs-lookup"><span data-stu-id="e850d-905">tax file</span></span>
  
<span data-ttu-id="e850d-906">税文件编号</span><span class="sxs-lookup"><span data-stu-id="e850d-906">tax file no.</span></span>
  
<span data-ttu-id="e850d-907">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="e850d-907">personal id number</span></span>
  
<span data-ttu-id="e850d-908">skatt id nummer</span><span class="sxs-lookup"><span data-stu-id="e850d-908">skatt id nummer</span></span>
  
<span data-ttu-id="e850d-909">skatt identifikation</span><span class="sxs-lookup"><span data-stu-id="e850d-909">skatt identifikation</span></span>
  
<span data-ttu-id="e850d-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="e850d-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="e850d-911">英国</span><span class="sxs-lookup"><span data-stu-id="e850d-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="e850d-912">Format</span><span class="sxs-lookup"><span data-stu-id="e850d-912">Format</span></span>

<span data-ttu-id="e850d-913">唯一的纳税人参考 (UTR):10 个数字, 无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="e850d-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="e850d-914">国家保险业号码 (NINO): 有关详细信息, 请参阅 "英国</span><span class="sxs-lookup"><span data-stu-id="e850d-914">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="e850d-915">[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的国家保险业号码 (NINO)。</span><span class="sxs-lookup"><span data-stu-id="e850d-915">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e850d-916">模式</span><span class="sxs-lookup"><span data-stu-id="e850d-916">Pattern</span></span>

<span data-ttu-id="e850d-917">唯一的纳税人引用 (UTR):10 个数字</span><span class="sxs-lookup"><span data-stu-id="e850d-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="e850d-918">国家保险业号码 (NINO): 有关详细信息, 请参阅 "英国</span><span class="sxs-lookup"><span data-stu-id="e850d-918">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="e850d-919">[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的国家保险业号码 (NINO)。</span><span class="sxs-lookup"><span data-stu-id="e850d-919">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e850d-920">校验和</span><span class="sxs-lookup"><span data-stu-id="e850d-920">Checksum</span></span>

<span data-ttu-id="e850d-921">是</span><span class="sxs-lookup"><span data-stu-id="e850d-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e850d-922">定义</span><span class="sxs-lookup"><span data-stu-id="e850d-922">Definition</span></span>

<span data-ttu-id="e850d-923">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="e850d-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e850d-924">函数`Func_uk_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e850d-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e850d-925">找到了中`Keywords_uk_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="e850d-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e850d-926">关键字</span><span class="sxs-lookup"><span data-stu-id="e850d-926">Keywords</span></span>

#### <a name="keywordsukeutaxfilenumber"></a><span data-ttu-id="e850d-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e850d-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="e850d-928">tax id</span><span class="sxs-lookup"><span data-stu-id="e850d-928">tax id</span></span>
  
<span data-ttu-id="e850d-929">税号编号</span><span class="sxs-lookup"><span data-stu-id="e850d-929">tax id no.</span></span>
  
<span data-ttu-id="e850d-930">税务 id 号</span><span class="sxs-lookup"><span data-stu-id="e850d-930">tax id number</span></span>
  
<span data-ttu-id="e850d-931">tax identification</span><span class="sxs-lookup"><span data-stu-id="e850d-931">tax identification</span></span>
  
<span data-ttu-id="e850d-932">纳税标识号</span><span class="sxs-lookup"><span data-stu-id="e850d-932">tax identification#</span></span>
  
<span data-ttu-id="e850d-933">纳税编号</span><span class="sxs-lookup"><span data-stu-id="e850d-933">tax no.</span></span>
  
<span data-ttu-id="e850d-934">税种</span><span class="sxs-lookup"><span data-stu-id="e850d-934">tax#</span></span>
  
<span data-ttu-id="e850d-935">taxid#</span><span class="sxs-lookup"><span data-stu-id="e850d-935">taxid#</span></span>
  
<span data-ttu-id="e850d-936">税文件</span><span class="sxs-lookup"><span data-stu-id="e850d-936">tax file</span></span>
  
<span data-ttu-id="e850d-937">税文件编号</span><span class="sxs-lookup"><span data-stu-id="e850d-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e850d-938">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e850d-938">See also</span></span>

[<span data-ttu-id="e850d-939">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="e850d-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

