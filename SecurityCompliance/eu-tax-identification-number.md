---
title: 欧盟纳税标识号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: f04919c8-2356-4de2-bb2a-b9f67f339726
description: 本主题演示数据丢失防护 (DLP) 策略检测到的欧盟纳税标识号敏感信息类型时的寻找。此敏感信息类型定义不同的模式、 关键字和每个国家/地区其他证据。
ms.openlocfilehash: 5192496b393d15fd6d063e09c9bfe1cb3dd7e2dd
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525378"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="a99f5-104">欧盟纳税标识号</span><span class="sxs-lookup"><span data-stu-id="a99f5-104">EU Tax Identification Number</span></span>

<span data-ttu-id="a99f5-p102">本主题演示数据丢失防护 (DLP) 策略检测到的欧盟税费识别号码 （会议） 敏感信息类型时的寻找。此敏感信息类型定义不同的模式、 关键字和每个国家/地区其他证据。</span><span class="sxs-lookup"><span data-stu-id="a99f5-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="a99f5-107">奥地利</span><span class="sxs-lookup"><span data-stu-id="a99f5-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="a99f5-108">格式</span><span class="sxs-lookup"><span data-stu-id="a99f5-108">Format</span></span>

<span data-ttu-id="a99f5-109">可选连字符与正斜杠九个数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a99f5-110">模式</span><span class="sxs-lookup"><span data-stu-id="a99f5-110">Pattern</span></span>

<span data-ttu-id="a99f5-111">可选连字符与正斜杠的九个数字：</span><span class="sxs-lookup"><span data-stu-id="a99f5-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="a99f5-112">两位数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-112">Two digits</span></span> 
    
- <span data-ttu-id="a99f5-113">一个连字符（可选）</span><span class="sxs-lookup"><span data-stu-id="a99f5-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="a99f5-114">三位数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-114">Three digits</span></span>
    
- <span data-ttu-id="a99f5-115">正斜杠（可选）</span><span class="sxs-lookup"><span data-stu-id="a99f5-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="a99f5-116">四位数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a99f5-117">校验和</span><span class="sxs-lookup"><span data-stu-id="a99f5-117">Checksum</span></span>

<span data-ttu-id="a99f5-118">是</span><span class="sxs-lookup"><span data-stu-id="a99f5-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a99f5-119">定义</span><span class="sxs-lookup"><span data-stu-id="a99f5-119">Definition</span></span>

<span data-ttu-id="a99f5-120">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-121">该函数`Func_austria_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a99f5-122">从关键字`Keywords_austria_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="a99f5-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a99f5-123">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-124">该函数`Func_austria_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="a99f5-125">Keywords</span><span class="sxs-lookup"><span data-stu-id="a99f5-125">Keywords</span></span>

#### <a name="keywordsaustriaeutaxfilenumber"></a><span data-ttu-id="a99f5-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a99f5-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="a99f5-127">税号</span><span class="sxs-lookup"><span data-stu-id="a99f5-127">tax number</span></span>
  
<span data-ttu-id="a99f5-128">号码</span><span class="sxs-lookup"><span data-stu-id="a99f5-128">number</span></span>
  
<span data-ttu-id="a99f5-129">税费登记号码</span><span class="sxs-lookup"><span data-stu-id="a99f5-129">tax registration number</span></span>
  
<span data-ttu-id="a99f5-130">tax id
</span><span class="sxs-lookup"><span data-stu-id="a99f5-130">tax id</span></span>
  
<span data-ttu-id="a99f5-131">st.nr。</span><span class="sxs-lookup"><span data-stu-id="a99f5-131">st.nr.</span></span>
  
<span data-ttu-id="a99f5-132">steuernummer</span><span class="sxs-lookup"><span data-stu-id="a99f5-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="a99f5-133">比利时</span><span class="sxs-lookup"><span data-stu-id="a99f5-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="a99f5-134">格式</span><span class="sxs-lookup"><span data-stu-id="a99f5-134">Format</span></span>

<span data-ttu-id="a99f5-135">没有空格和分隔符 11 位数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a99f5-136">模式</span><span class="sxs-lookup"><span data-stu-id="a99f5-136">Pattern</span></span>

<span data-ttu-id="a99f5-137">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="a99f5-137">11 digits:</span></span>
  
- <span data-ttu-id="a99f5-138">两位数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-138">Two digits</span></span>
    
- <span data-ttu-id="a99f5-139">"0"或者"1"</span><span class="sxs-lookup"><span data-stu-id="a99f5-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="a99f5-140">一位数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-140">One digit</span></span>
    
- <span data-ttu-id="a99f5-141">"0"或"1"或"2"或者"3"</span><span class="sxs-lookup"><span data-stu-id="a99f5-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="a99f5-142">六个数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a99f5-143">校验和</span><span class="sxs-lookup"><span data-stu-id="a99f5-143">Checksum</span></span>

<span data-ttu-id="a99f5-144">不适用</span><span class="sxs-lookup"><span data-stu-id="a99f5-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a99f5-145">定义</span><span class="sxs-lookup"><span data-stu-id="a99f5-145">Definition</span></span>

<span data-ttu-id="a99f5-146">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-147">正则表达式`Regex_belgium_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a99f5-148">从关键字`Keywords_belgium_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="a99f5-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a99f5-149">Keywords</span><span class="sxs-lookup"><span data-stu-id="a99f5-149">Keywords</span></span>

#### <a name="keywordsbelgiumeutaxfilenumber"></a><span data-ttu-id="a99f5-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a99f5-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="a99f5-151">税号</span><span class="sxs-lookup"><span data-stu-id="a99f5-151">tax number</span></span>
  
<span data-ttu-id="a99f5-152">国家/地区的注册号码</span><span class="sxs-lookup"><span data-stu-id="a99f5-152">national registration number</span></span>
  
<span data-ttu-id="a99f5-153">税费登记号码</span><span class="sxs-lookup"><span data-stu-id="a99f5-153">tax registration number</span></span>
  
<span data-ttu-id="a99f5-154">tax id
</span><span class="sxs-lookup"><span data-stu-id="a99f5-154">tax id</span></span>
  
<span data-ttu-id="a99f5-155">n 如果</span><span class="sxs-lookup"><span data-stu-id="a99f5-155">nif</span></span>
  
<span data-ttu-id="a99f5-156">n 如果 #</span><span class="sxs-lookup"><span data-stu-id="a99f5-156">nif#</span></span>
  
<span data-ttu-id="a99f5-157">numéro de registre 国家/地区</span><span class="sxs-lookup"><span data-stu-id="a99f5-157">numéro de registre national</span></span>
  
<span data-ttu-id="a99f5-158">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="a99f5-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="a99f5-159">保加利亚</span><span class="sxs-lookup"><span data-stu-id="a99f5-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="a99f5-160">格式</span><span class="sxs-lookup"><span data-stu-id="a99f5-160">Format</span></span>

<span data-ttu-id="a99f5-161">没有空格和分隔符的 10 位数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a99f5-162">模式</span><span class="sxs-lookup"><span data-stu-id="a99f5-162">Pattern</span></span>

<span data-ttu-id="a99f5-163">10 个数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a99f5-164">校验和</span><span class="sxs-lookup"><span data-stu-id="a99f5-164">Checksum</span></span>

<span data-ttu-id="a99f5-165">是</span><span class="sxs-lookup"><span data-stu-id="a99f5-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a99f5-166">定义</span><span class="sxs-lookup"><span data-stu-id="a99f5-166">Definition</span></span>

<span data-ttu-id="a99f5-167">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-168">该函数`Func_bulgaria_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a99f5-169">从关键字`Keywords_bulgaria_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="a99f5-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a99f5-170">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-171">该函数`Func_bulgaria_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="a99f5-172">Keywords</span><span class="sxs-lookup"><span data-stu-id="a99f5-172">Keywords</span></span>

#### <a name="keywordsbulgariaeutaxfilenumber"></a><span data-ttu-id="a99f5-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a99f5-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="a99f5-174">bucn</span><span class="sxs-lookup"><span data-stu-id="a99f5-174">bucn</span></span>
  
<span data-ttu-id="a99f5-175">统一民事号码</span><span class="sxs-lookup"><span data-stu-id="a99f5-175">uniform civil number</span></span>
  
<span data-ttu-id="a99f5-176">bucn #</span><span class="sxs-lookup"><span data-stu-id="a99f5-176">bucn#</span></span>
  
<span data-ttu-id="a99f5-177">uniformcivilnumber #</span><span class="sxs-lookup"><span data-stu-id="a99f5-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="a99f5-178">统一民事 id</span><span class="sxs-lookup"><span data-stu-id="a99f5-178">uniform civil id</span></span>
  
<span data-ttu-id="a99f5-179">统一民事否</span><span class="sxs-lookup"><span data-stu-id="a99f5-179">uniform civil no</span></span>
  
<span data-ttu-id="a99f5-180">egn</span><span class="sxs-lookup"><span data-stu-id="a99f5-180">egn</span></span>
  
<span data-ttu-id="a99f5-181">保加利亚语统一民事号码</span><span class="sxs-lookup"><span data-stu-id="a99f5-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="a99f5-182">uniformcivilno #</span><span class="sxs-lookup"><span data-stu-id="a99f5-182">uniformcivilno#</span></span>
  
<span data-ttu-id="a99f5-183">egn #</span><span class="sxs-lookup"><span data-stu-id="a99f5-183">egn#</span></span>
  
<span data-ttu-id="a99f5-184">УНИФОРМ ГРАЖДАНСКИ НОМЕР</span><span class="sxs-lookup"><span data-stu-id="a99f5-184">униформ граждански номер</span></span>
  
<span data-ttu-id="a99f5-185">Униформ id</span><span class="sxs-lookup"><span data-stu-id="a99f5-185">униформ id</span></span>
  
<span data-ttu-id="a99f5-186">Униформ граждански id</span><span class="sxs-lookup"><span data-stu-id="a99f5-186">униформ граждански id</span></span>
  
<span data-ttu-id="a99f5-187">УНИФОРМ ГРАЖДАНСКИ НЕ</span><span class="sxs-lookup"><span data-stu-id="a99f5-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="a99f5-188">克罗地亚</span><span class="sxs-lookup"><span data-stu-id="a99f5-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="a99f5-189">格式</span><span class="sxs-lookup"><span data-stu-id="a99f5-189">Format</span></span>

<span data-ttu-id="a99f5-190">不得含有空格或分隔符 11 位数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a99f5-191">模式</span><span class="sxs-lookup"><span data-stu-id="a99f5-191">Pattern</span></span>

<span data-ttu-id="a99f5-192">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="a99f5-192">11 digits:</span></span>
  
- <span data-ttu-id="a99f5-193">10 位数字，随机选择</span><span class="sxs-lookup"><span data-stu-id="a99f5-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="a99f5-194">一个检查数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a99f5-195">校验和</span><span class="sxs-lookup"><span data-stu-id="a99f5-195">Checksum</span></span>

<span data-ttu-id="a99f5-196">是</span><span class="sxs-lookup"><span data-stu-id="a99f5-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a99f5-197">定义</span><span class="sxs-lookup"><span data-stu-id="a99f5-197">Definition</span></span>

<span data-ttu-id="a99f5-198">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-199">该函数`Func_croatia_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a99f5-200">从关键字`Keywords_croatia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="a99f5-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a99f5-201">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-202">该函数`Func_croatia_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="a99f5-203">Keywords</span><span class="sxs-lookup"><span data-stu-id="a99f5-203">Keywords</span></span>

#### <a name="keywordscroatiaeutaxfilenumber"></a><span data-ttu-id="a99f5-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a99f5-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="a99f5-205">税号</span><span class="sxs-lookup"><span data-stu-id="a99f5-205">tax number</span></span>
  
<span data-ttu-id="a99f5-206">税费</span><span class="sxs-lookup"><span data-stu-id="a99f5-206">tax</span></span>
  
<span data-ttu-id="a99f5-207">tax id
</span><span class="sxs-lookup"><span data-stu-id="a99f5-207">tax id</span></span>
  
<span data-ttu-id="a99f5-208">oid</span><span class="sxs-lookup"><span data-stu-id="a99f5-208">oid</span></span>
  
<span data-ttu-id="a99f5-209">oid #</span><span class="sxs-lookup"><span data-stu-id="a99f5-209">oid#</span></span>
  
<span data-ttu-id="a99f5-210">porezni broj</span><span class="sxs-lookup"><span data-stu-id="a99f5-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="a99f5-211">塞浦路斯</span><span class="sxs-lookup"><span data-stu-id="a99f5-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="a99f5-212">格式</span><span class="sxs-lookup"><span data-stu-id="a99f5-212">Format</span></span>

<span data-ttu-id="a99f5-213">八个数字和指定的模式中的一个字母</span><span class="sxs-lookup"><span data-stu-id="a99f5-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a99f5-214">模式</span><span class="sxs-lookup"><span data-stu-id="a99f5-214">Pattern</span></span>

<span data-ttu-id="a99f5-215">八个数字和一个字母：</span><span class="sxs-lookup"><span data-stu-id="a99f5-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="a99f5-216">"0"</span><span class="sxs-lookup"><span data-stu-id="a99f5-216">A "0"</span></span> 
    
- <span data-ttu-id="a99f5-217">七个数字 </span><span class="sxs-lookup"><span data-stu-id="a99f5-217">Seven digits</span></span>
    
- <span data-ttu-id="a99f5-218">一个字母 （不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="a99f5-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a99f5-219">校验和</span><span class="sxs-lookup"><span data-stu-id="a99f5-219">Checksum</span></span>

<span data-ttu-id="a99f5-220">不适用</span><span class="sxs-lookup"><span data-stu-id="a99f5-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a99f5-221">定义</span><span class="sxs-lookup"><span data-stu-id="a99f5-221">Definition</span></span>

<span data-ttu-id="a99f5-222">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-223">该函数`Func_cyprus_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a99f5-224">从关键字`Keywords_cyprus_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="a99f5-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a99f5-225">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-226">该函数`Func_cyprus_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="a99f5-227">Keywords</span><span class="sxs-lookup"><span data-stu-id="a99f5-227">Keywords</span></span>

#### <a name="keywordscypruseutaxfilenumber"></a><span data-ttu-id="a99f5-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a99f5-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="a99f5-229">税号</span><span class="sxs-lookup"><span data-stu-id="a99f5-229">tax number</span></span>
  
<span data-ttu-id="a99f5-230">税费</span><span class="sxs-lookup"><span data-stu-id="a99f5-230">tax</span></span>
  
<span data-ttu-id="a99f5-231">tax id
</span><span class="sxs-lookup"><span data-stu-id="a99f5-231">tax id</span></span>
  
<span data-ttu-id="a99f5-232">税费标识代码</span><span class="sxs-lookup"><span data-stu-id="a99f5-232">tax identification code</span></span>
  
<span data-ttu-id="a99f5-233">tic</span><span class="sxs-lookup"><span data-stu-id="a99f5-233">tic</span></span>
  
<span data-ttu-id="a99f5-234">tic #</span><span class="sxs-lookup"><span data-stu-id="a99f5-234">tic#</span></span>
  
<span data-ttu-id="a99f5-235">ΑΡΙΘΜΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="a99f5-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="a99f5-236">ΦΟΡΟΛΟΓΙΚΉ ΤΑΥΤΌΤΗΤΑ</span><span class="sxs-lookup"><span data-stu-id="a99f5-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="a99f5-237">ΚΩΔΙΚΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="a99f5-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="a99f5-238">捷克共和国</span><span class="sxs-lookup"><span data-stu-id="a99f5-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="a99f5-239">格式</span><span class="sxs-lookup"><span data-stu-id="a99f5-239">Format</span></span>

<span data-ttu-id="a99f5-240">使用可选的反斜杠 9 或 10 个数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a99f5-241">模式</span><span class="sxs-lookup"><span data-stu-id="a99f5-241">Pattern</span></span>

<span data-ttu-id="a99f5-242">使用可选 backslashl 9 或 10 位数字：</span><span class="sxs-lookup"><span data-stu-id="a99f5-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="a99f5-243">六位数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-243">Six digits</span></span> 
    
- <span data-ttu-id="a99f5-244">反斜杠 （可选）</span><span class="sxs-lookup"><span data-stu-id="a99f5-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="a99f5-245">三个或四个数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a99f5-246">校验和</span><span class="sxs-lookup"><span data-stu-id="a99f5-246">Checksum</span></span>

<span data-ttu-id="a99f5-247">不适用</span><span class="sxs-lookup"><span data-stu-id="a99f5-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a99f5-248">定义</span><span class="sxs-lookup"><span data-stu-id="a99f5-248">Definition</span></span>

<span data-ttu-id="a99f5-249">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-250">正则表达式`Regex_czech_republic_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a99f5-251">从关键字`Keywords_czech_republic_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="a99f5-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a99f5-252">Keywords</span><span class="sxs-lookup"><span data-stu-id="a99f5-252">Keywords</span></span>

#### <a name="keywordsczechrepubliceutaxfilenumber"></a><span data-ttu-id="a99f5-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a99f5-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="a99f5-254">税号</span><span class="sxs-lookup"><span data-stu-id="a99f5-254">tax number</span></span>
  
<span data-ttu-id="a99f5-255">税费</span><span class="sxs-lookup"><span data-stu-id="a99f5-255">tax</span></span>
  
<span data-ttu-id="a99f5-256">tax id
</span><span class="sxs-lookup"><span data-stu-id="a99f5-256">tax id</span></span>
  
<span data-ttu-id="a99f5-257">个人号码</span><span class="sxs-lookup"><span data-stu-id="a99f5-257">personal number</span></span>
  
<span data-ttu-id="a99f5-258">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="a99f5-258">daňové číslo</span></span>
  
<span data-ttu-id="a99f5-259">osobní číslo</span><span class="sxs-lookup"><span data-stu-id="a99f5-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="a99f5-260">丹麦</span><span class="sxs-lookup"><span data-stu-id="a99f5-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="a99f5-261">格式</span><span class="sxs-lookup"><span data-stu-id="a99f5-261">Format</span></span>

<span data-ttu-id="a99f5-262">包含连字符的 10 位数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a99f5-263">模式</span><span class="sxs-lookup"><span data-stu-id="a99f5-263">Pattern</span></span>

<span data-ttu-id="a99f5-264">包含 hyphenl 10 位数字：</span><span class="sxs-lookup"><span data-stu-id="a99f5-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="a99f5-265">对应于出生日期月日的 6 个数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="a99f5-266">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="a99f5-266">A hyphen</span></span>
    
- <span data-ttu-id="a99f5-267">对应的第一个数字对应的出生 century 的顺序号的四位数字的最后一位对应的个人性别 （男性和甚至女性奇数页）</span><span class="sxs-lookup"><span data-stu-id="a99f5-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a99f5-268">校验和</span><span class="sxs-lookup"><span data-stu-id="a99f5-268">Checksum</span></span>

<span data-ttu-id="a99f5-269">是</span><span class="sxs-lookup"><span data-stu-id="a99f5-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a99f5-270">定义</span><span class="sxs-lookup"><span data-stu-id="a99f5-270">Definition</span></span>

<span data-ttu-id="a99f5-271">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-272">该函数`Func_denmark_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a99f5-273">从关键字`Keywords_denmark_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="a99f5-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a99f5-274">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-275">该函数`Func_denmark_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="a99f5-276">Keywords</span><span class="sxs-lookup"><span data-stu-id="a99f5-276">Keywords</span></span>

#### <a name="keywordsdenmarkeutaxfilenumber"></a><span data-ttu-id="a99f5-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a99f5-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="a99f5-278">税号</span><span class="sxs-lookup"><span data-stu-id="a99f5-278">tax number</span></span>
  
<span data-ttu-id="a99f5-279">税费</span><span class="sxs-lookup"><span data-stu-id="a99f5-279">tax</span></span>
  
<span data-ttu-id="a99f5-280">tax id
</span><span class="sxs-lookup"><span data-stu-id="a99f5-280">tax id</span></span>
  
<span data-ttu-id="a99f5-281">cpr 号码</span><span class="sxs-lookup"><span data-stu-id="a99f5-281">cpr number</span></span>
  
<span data-ttu-id="a99f5-282">cpr #</span><span class="sxs-lookup"><span data-stu-id="a99f5-282">cpr#</span></span>
  
<span data-ttu-id="a99f5-283">skat nummer</span><span class="sxs-lookup"><span data-stu-id="a99f5-283">skat nummer</span></span>
  
<span data-ttu-id="a99f5-284">skat id</span><span class="sxs-lookup"><span data-stu-id="a99f5-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="a99f5-285">爱沙尼亚</span><span class="sxs-lookup"><span data-stu-id="a99f5-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="a99f5-286">格式</span><span class="sxs-lookup"><span data-stu-id="a99f5-286">Format</span></span>

<span data-ttu-id="a99f5-287">不得含有空格或分隔符 11 位数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a99f5-288">模式</span><span class="sxs-lookup"><span data-stu-id="a99f5-288">Pattern</span></span>

<span data-ttu-id="a99f5-289">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="a99f5-289">11 digits:</span></span>
  
-  <span data-ttu-id="a99f5-290">有一个对应于性别和出生其中奇数指示男性和偶数指示女性，如下所示的 century 的数字： 1，2 代表 19 世纪;3、 4 20 世纪;5、 6 21 世纪和</span><span class="sxs-lookup"><span data-stu-id="a99f5-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="a99f5-291">对应于出生日期 (YYMMDD) 的 6 个数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="a99f5-292">对应于分隔人员在相同日期出生日期序列号的三个数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="a99f5-293">一个检查数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a99f5-294">校验和</span><span class="sxs-lookup"><span data-stu-id="a99f5-294">Checksum</span></span>

<span data-ttu-id="a99f5-295">是</span><span class="sxs-lookup"><span data-stu-id="a99f5-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a99f5-296">定义</span><span class="sxs-lookup"><span data-stu-id="a99f5-296">Definition</span></span>

<span data-ttu-id="a99f5-297">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-298">该函数`Func_estonia_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a99f5-299">从关键字`Keywords_estonia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="a99f5-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a99f5-300">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-301">该函数`Func_estonia_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="a99f5-302">Keywords</span><span class="sxs-lookup"><span data-stu-id="a99f5-302">Keywords</span></span>

#### <a name="keywordsestoniaeutaxfilenumber"></a><span data-ttu-id="a99f5-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a99f5-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="a99f5-304">税号</span><span class="sxs-lookup"><span data-stu-id="a99f5-304">tax number</span></span>
  
<span data-ttu-id="a99f5-305">税费</span><span class="sxs-lookup"><span data-stu-id="a99f5-305">tax</span></span>
  
<span data-ttu-id="a99f5-306">tax id
</span><span class="sxs-lookup"><span data-stu-id="a99f5-306">tax id</span></span>
  
<span data-ttu-id="a99f5-307">个人代码</span><span class="sxs-lookup"><span data-stu-id="a99f5-307">personal code</span></span>
  
<span data-ttu-id="a99f5-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="a99f5-308">maksunumber</span></span>
  
<span data-ttu-id="a99f5-309">maksu id</span><span class="sxs-lookup"><span data-stu-id="a99f5-309">maksu id</span></span>
  
<span data-ttu-id="a99f5-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="a99f5-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="a99f5-311">芬兰</span><span class="sxs-lookup"><span data-stu-id="a99f5-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="a99f5-312">格式</span><span class="sxs-lookup"><span data-stu-id="a99f5-312">Format</span></span>

<span data-ttu-id="a99f5-313">字母数字 11 个字符组成，和加号和减号</span><span class="sxs-lookup"><span data-stu-id="a99f5-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a99f5-314">模式</span><span class="sxs-lookup"><span data-stu-id="a99f5-314">Pattern</span></span>

<span data-ttu-id="a99f5-315">字母数字 11 个字符组成，和加号和减号：</span><span class="sxs-lookup"><span data-stu-id="a99f5-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="a99f5-316">六位数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-316">Six digits</span></span>
    
- <span data-ttu-id="a99f5-317">以下项之一： 加号、 减号或其中加号表示的字母"A"（不区分大小写） 之间 1800年 1899年出生减号登录出生日期之间的表示 1900年-1999年和"A"表示出生 2000年和之后</span><span class="sxs-lookup"><span data-stu-id="a99f5-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="a99f5-318">三位数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-318">Three digits</span></span>
    
- <span data-ttu-id="a99f5-319">一个字母或一个号码</span><span class="sxs-lookup"><span data-stu-id="a99f5-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a99f5-320">校验和</span><span class="sxs-lookup"><span data-stu-id="a99f5-320">Checksum</span></span>

<span data-ttu-id="a99f5-321">是</span><span class="sxs-lookup"><span data-stu-id="a99f5-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a99f5-322">定义</span><span class="sxs-lookup"><span data-stu-id="a99f5-322">Definition</span></span>

<span data-ttu-id="a99f5-323">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-324">该函数`Func_finland_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a99f5-325">从关键字`Keywords_finland_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="a99f5-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a99f5-326">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-327">该函数`Func_finland_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="a99f5-328">Keywords</span><span class="sxs-lookup"><span data-stu-id="a99f5-328">Keywords</span></span>

#### <a name="keywordsfinlandeutaxfilenumber"></a><span data-ttu-id="a99f5-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a99f5-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="a99f5-330">identification number
</span><span class="sxs-lookup"><span data-stu-id="a99f5-330">identification number</span></span>
  
<span data-ttu-id="a99f5-331">个人 id</span><span class="sxs-lookup"><span data-stu-id="a99f5-331">personal id</span></span>
  
<span data-ttu-id="a99f5-332">标识号</span><span class="sxs-lookup"><span data-stu-id="a99f5-332">identity number</span></span>
  
<span data-ttu-id="a99f5-333">芬兰国家/地区 id 号</span><span class="sxs-lookup"><span data-stu-id="a99f5-333">finnish national id number</span></span>
  
<span data-ttu-id="a99f5-334">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="a99f5-334">personalidnumber#</span></span>
  
<span data-ttu-id="a99f5-335">国家/地区标识号</span><span class="sxs-lookup"><span data-stu-id="a99f5-335">national identification number</span></span>
  
<span data-ttu-id="a99f5-336">id 号</span><span class="sxs-lookup"><span data-stu-id="a99f5-336">id number</span></span>
  
<span data-ttu-id="a99f5-337">国家/地区 id 没有。</span><span class="sxs-lookup"><span data-stu-id="a99f5-337">national id no.</span></span>
  
<span data-ttu-id="a99f5-338">国家/地区 id 号</span><span class="sxs-lookup"><span data-stu-id="a99f5-338">national id number</span></span>
  
<span data-ttu-id="a99f5-339">id 没有</span><span class="sxs-lookup"><span data-stu-id="a99f5-339">id no</span></span>
  
<span data-ttu-id="a99f5-340">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="a99f5-340">tunnistenumero</span></span>
  
<span data-ttu-id="a99f5-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="a99f5-341">henkilötunnus</span></span>
  
<span data-ttu-id="a99f5-342">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="a99f5-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="a99f5-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="a99f5-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="a99f5-344">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="a99f5-344">identiteetti numero</span></span>
  
<span data-ttu-id="a99f5-345">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="a99f5-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="a99f5-346">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="a99f5-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="a99f5-347">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="a99f5-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="a99f5-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="a99f5-348">tunnusnumero</span></span>
  
<span data-ttu-id="a99f5-349">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="a99f5-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="a99f5-350">法国</span><span class="sxs-lookup"><span data-stu-id="a99f5-350">France</span></span>

### <a name="format"></a><span data-ttu-id="a99f5-351">格式</span><span class="sxs-lookup"><span data-stu-id="a99f5-351">Format</span></span>

<span data-ttu-id="a99f5-352">为个人和实体的九个数字 13 数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a99f5-353">模式</span><span class="sxs-lookup"><span data-stu-id="a99f5-353">Pattern</span></span>

<span data-ttu-id="a99f5-354">对于个人的 13 数字：</span><span class="sxs-lookup"><span data-stu-id="a99f5-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="a99f5-355">必须是 0、 1、 2 或 3 的一位数</span><span class="sxs-lookup"><span data-stu-id="a99f5-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="a99f5-356">12 个数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-356">12 digits</span></span>
    
<span data-ttu-id="a99f5-357">实体的九个数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a99f5-358">校验和</span><span class="sxs-lookup"><span data-stu-id="a99f5-358">Checksum</span></span>

<span data-ttu-id="a99f5-359">不适用</span><span class="sxs-lookup"><span data-stu-id="a99f5-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a99f5-360">定义</span><span class="sxs-lookup"><span data-stu-id="a99f5-360">Definition</span></span>

<span data-ttu-id="a99f5-361">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-362">该函数`Func_france_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a99f5-363">从关键字`Keywords_france_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="a99f5-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a99f5-364">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-365">该函数`Func_france_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="a99f5-366">Keywords</span><span class="sxs-lookup"><span data-stu-id="a99f5-366">Keywords</span></span>

#### <a name="keywordsfranceeutaxfilenumber"></a><span data-ttu-id="a99f5-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a99f5-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="a99f5-368">纳税标识号</span><span class="sxs-lookup"><span data-stu-id="a99f5-368">tax identification number</span></span>
  
<span data-ttu-id="a99f5-369">税号</span><span class="sxs-lookup"><span data-stu-id="a99f5-369">tax number</span></span>
  
<span data-ttu-id="a99f5-370">tax id
</span><span class="sxs-lookup"><span data-stu-id="a99f5-370">tax id</span></span>
  
<span data-ttu-id="a99f5-371">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="a99f5-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="a99f5-372">德国</span><span class="sxs-lookup"><span data-stu-id="a99f5-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="a99f5-373">格式</span><span class="sxs-lookup"><span data-stu-id="a99f5-373">Format</span></span>

<span data-ttu-id="a99f5-374">没有空格和分隔符 11 位数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a99f5-375">模式</span><span class="sxs-lookup"><span data-stu-id="a99f5-375">Pattern</span></span>

<span data-ttu-id="a99f5-376">11 位数字：</span><span class="sxs-lookup"><span data-stu-id="a99f5-376">11 digits :</span></span>
  
-  <span data-ttu-id="a99f5-377">10 位数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-377">Ten digits</span></span> 
    
- <span data-ttu-id="a99f5-378">一个检查数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a99f5-379">校验和</span><span class="sxs-lookup"><span data-stu-id="a99f5-379">Checksum</span></span>

<span data-ttu-id="a99f5-380">是</span><span class="sxs-lookup"><span data-stu-id="a99f5-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a99f5-381">定义</span><span class="sxs-lookup"><span data-stu-id="a99f5-381">Definition</span></span>

<span data-ttu-id="a99f5-382">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-383">该函数`Func_germany_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a99f5-384">从关键字`Keywords_germany_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="a99f5-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a99f5-385">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-386">该函数`Func_germany_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="a99f5-387">Keywords</span><span class="sxs-lookup"><span data-stu-id="a99f5-387">Keywords</span></span>

#### <a name="keywordsgermanyeutaxfilenumber"></a><span data-ttu-id="a99f5-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a99f5-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="a99f5-389">税号</span><span class="sxs-lookup"><span data-stu-id="a99f5-389">tax number</span></span>
  
<span data-ttu-id="a99f5-390">税费否。</span><span class="sxs-lookup"><span data-stu-id="a99f5-390">tax no.</span></span>
  
<span data-ttu-id="a99f5-391">taxno #</span><span class="sxs-lookup"><span data-stu-id="a99f5-391">taxno#</span></span>
  
<span data-ttu-id="a99f5-392">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="a99f5-392">taxnumber#</span></span>
  
<span data-ttu-id="a99f5-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="a99f5-393">taxnumber</span></span>
  
<span data-ttu-id="a99f5-394">tax id
</span><span class="sxs-lookup"><span data-stu-id="a99f5-394">tax id</span></span>
  
<span data-ttu-id="a99f5-395">taxid #</span><span class="sxs-lookup"><span data-stu-id="a99f5-395">taxid#</span></span>
  
<span data-ttu-id="a99f5-396">纳税标识号</span><span class="sxs-lookup"><span data-stu-id="a99f5-396">tax identification number</span></span>
  
<span data-ttu-id="a99f5-397">不纳税标识。</span><span class="sxs-lookup"><span data-stu-id="a99f5-397">tax identification no.</span></span>
  
<span data-ttu-id="a99f5-398">steuernummer</span><span class="sxs-lookup"><span data-stu-id="a99f5-398">steuernummer</span></span>
  
<span data-ttu-id="a99f5-399">steuer id</span><span class="sxs-lookup"><span data-stu-id="a99f5-399">steuer id</span></span>
  
<span data-ttu-id="a99f5-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="a99f5-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="a99f5-401">希腊</span><span class="sxs-lookup"><span data-stu-id="a99f5-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="a99f5-402">格式</span><span class="sxs-lookup"><span data-stu-id="a99f5-402">Format</span></span>

<span data-ttu-id="a99f5-403">没有空格和分隔符的九个数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a99f5-404">模式</span><span class="sxs-lookup"><span data-stu-id="a99f5-404">Pattern</span></span>

<span data-ttu-id="a99f5-405">九个数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a99f5-406">校验和</span><span class="sxs-lookup"><span data-stu-id="a99f5-406">Checksum</span></span>

<span data-ttu-id="a99f5-407">不适用</span><span class="sxs-lookup"><span data-stu-id="a99f5-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a99f5-408">定义</span><span class="sxs-lookup"><span data-stu-id="a99f5-408">Definition</span></span>

<span data-ttu-id="a99f5-409">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-410">正则表达式`Regex_greece_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a99f5-411">从关键字`Keywords_greece_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="a99f5-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a99f5-412">Keywords</span><span class="sxs-lookup"><span data-stu-id="a99f5-412">Keywords</span></span>

#### <a name="keywordsgreeceeutaxfilenumber"></a><span data-ttu-id="a99f5-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a99f5-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="a99f5-414">afm</span><span class="sxs-lookup"><span data-stu-id="a99f5-414">afm</span></span>
  
<span data-ttu-id="a99f5-415">tin
</span><span class="sxs-lookup"><span data-stu-id="a99f5-415">tin</span></span>
  
<span data-ttu-id="a99f5-416">不税费 id。</span><span class="sxs-lookup"><span data-stu-id="a99f5-416">tax id no.</span></span>
  
<span data-ttu-id="a99f5-417">不税费 id</span><span class="sxs-lookup"><span data-stu-id="a99f5-417">tax id no</span></span>
  
<span data-ttu-id="a99f5-418">纳税标识号</span><span class="sxs-lookup"><span data-stu-id="a99f5-418">tax identification number</span></span>
  
<span data-ttu-id="a99f5-419">税务注册表编号</span><span class="sxs-lookup"><span data-stu-id="a99f5-419">tax registry number</span></span>
  
<span data-ttu-id="a99f5-420">不税费注册表。</span><span class="sxs-lookup"><span data-stu-id="a99f5-420">tax registry no.</span></span>
  
<span data-ttu-id="a99f5-421">afm #</span><span class="sxs-lookup"><span data-stu-id="a99f5-421">afm#</span></span>
  
<span data-ttu-id="a99f5-422">会议 #</span><span class="sxs-lookup"><span data-stu-id="a99f5-422">tin#</span></span>
  
<span data-ttu-id="a99f5-423">taxidno #</span><span class="sxs-lookup"><span data-stu-id="a99f5-423">taxidno#</span></span>
  
<span data-ttu-id="a99f5-424">taxregistryno #</span><span class="sxs-lookup"><span data-stu-id="a99f5-424">taxregistryno#</span></span>
  
<span data-ttu-id="a99f5-425">ΑΡΙΘΜΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="a99f5-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="a99f5-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="a99f5-426">aφμ</span></span>
  
<span data-ttu-id="a99f5-427">aφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="a99f5-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="a99f5-428">ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ ΝΟ。</span><span class="sxs-lookup"><span data-stu-id="a99f5-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="a99f5-429">ΤΟΝ ΑΡΙΘΜΌ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="a99f5-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="a99f5-430">匈牙利</span><span class="sxs-lookup"><span data-stu-id="a99f5-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="a99f5-431">格式</span><span class="sxs-lookup"><span data-stu-id="a99f5-431">Format</span></span>

<span data-ttu-id="a99f5-432">不得含有空格或分隔符的 10 位数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a99f5-433">模式</span><span class="sxs-lookup"><span data-stu-id="a99f5-433">Pattern</span></span>

<span data-ttu-id="a99f5-434">10 位数字：</span><span class="sxs-lookup"><span data-stu-id="a99f5-434">Ten digits:</span></span>
  
-  <span data-ttu-id="a99f5-435">必须是"8"的一位数</span><span class="sxs-lookup"><span data-stu-id="a99f5-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="a99f5-436">对应于日期之间的天数的五个数字 01/01/1867年和各出生日期</span><span class="sxs-lookup"><span data-stu-id="a99f5-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="a99f5-437">生成的可能性区分出生在同一天的个人号码所对应的三个数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="a99f5-438">一个检查数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a99f5-439">校验和</span><span class="sxs-lookup"><span data-stu-id="a99f5-439">Checksum</span></span>

<span data-ttu-id="a99f5-440">是</span><span class="sxs-lookup"><span data-stu-id="a99f5-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a99f5-441">定义</span><span class="sxs-lookup"><span data-stu-id="a99f5-441">Definition</span></span>

<span data-ttu-id="a99f5-442">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-443">该函数`Func_hungary_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a99f5-444">从关键字`Keywords_hungary_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="a99f5-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a99f5-445">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-446">该函数`Func_hungary_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="a99f5-447">Keywords</span><span class="sxs-lookup"><span data-stu-id="a99f5-447">Keywords</span></span>

#### <a name="keywordshungaryeutaxfilenumber"></a><span data-ttu-id="a99f5-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a99f5-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="a99f5-449">匈牙利语纳税标识号</span><span class="sxs-lookup"><span data-stu-id="a99f5-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="a99f5-450">匈牙利语会议</span><span class="sxs-lookup"><span data-stu-id="a99f5-450">hungarian tin</span></span>
  
<span data-ttu-id="a99f5-451">税号</span><span class="sxs-lookup"><span data-stu-id="a99f5-451">tax id number</span></span>
  
<span data-ttu-id="a99f5-452">增值税编号</span><span class="sxs-lookup"><span data-stu-id="a99f5-452">vat number</span></span>
  
<span data-ttu-id="a99f5-453">不税费证书颁发机构</span><span class="sxs-lookup"><span data-stu-id="a99f5-453">tax authority no</span></span>
  
<span data-ttu-id="a99f5-454">税号税费标识</span><span class="sxs-lookup"><span data-stu-id="a99f5-454">tax id tax identity number</span></span>
  
<span data-ttu-id="a99f5-455">taxidnumber #</span><span class="sxs-lookup"><span data-stu-id="a99f5-455">taxidnumber#</span></span>
  
<span data-ttu-id="a99f5-456">会议 #</span><span class="sxs-lookup"><span data-stu-id="a99f5-456">tin#</span></span>
  
<span data-ttu-id="a99f5-457">hungatiantin #</span><span class="sxs-lookup"><span data-stu-id="a99f5-457">hungatiantin#</span></span>
  
<span data-ttu-id="a99f5-458">不税费标识</span><span class="sxs-lookup"><span data-stu-id="a99f5-458">tax identification no</span></span>
  
<span data-ttu-id="a99f5-459">taxidno #</span><span class="sxs-lookup"><span data-stu-id="a99f5-459">taxidno#</span></span>
  
<span data-ttu-id="a99f5-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="a99f5-460">adóazonosító szám</span></span>
  
<span data-ttu-id="a99f5-461">adószám</span><span class="sxs-lookup"><span data-stu-id="a99f5-461">adószám</span></span>
  
<span data-ttu-id="a99f5-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="a99f5-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="a99f5-463">Ireland</span><span class="sxs-lookup"><span data-stu-id="a99f5-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="a99f5-464">格式</span><span class="sxs-lookup"><span data-stu-id="a99f5-464">Format</span></span>

<span data-ttu-id="a99f5-465">七位数字后跟不得含有空格或分隔符号</span><span class="sxs-lookup"><span data-stu-id="a99f5-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a99f5-466">模式</span><span class="sxs-lookup"><span data-stu-id="a99f5-466">Pattern</span></span>

<span data-ttu-id="a99f5-467">接一个字母的七个数字：</span><span class="sxs-lookup"><span data-stu-id="a99f5-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="a99f5-468">七个数字 </span><span class="sxs-lookup"><span data-stu-id="a99f5-468">Seven digits</span></span> 
    
- <span data-ttu-id="a99f5-469">一个字母 （不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="a99f5-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a99f5-470">校验和</span><span class="sxs-lookup"><span data-stu-id="a99f5-470">Checksum</span></span>

<span data-ttu-id="a99f5-471">不适用</span><span class="sxs-lookup"><span data-stu-id="a99f5-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a99f5-472">定义</span><span class="sxs-lookup"><span data-stu-id="a99f5-472">Definition</span></span>

<span data-ttu-id="a99f5-473">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-474">该函数`Func_ireland_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a99f5-475">从关键字`Keywords_ireland_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="a99f5-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a99f5-476">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-477">该函数`Func_ireland_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="a99f5-478">Keywords</span><span class="sxs-lookup"><span data-stu-id="a99f5-478">Keywords</span></span>

#### <a name="keywordsirelandeutaxfilenumber"></a><span data-ttu-id="a99f5-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a99f5-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="a99f5-480">公共服务没有</span><span class="sxs-lookup"><span data-stu-id="a99f5-480">public service no</span></span>
  
<span data-ttu-id="a99f5-481">个人公共服务没有</span><span class="sxs-lookup"><span data-stu-id="a99f5-481">personal public service no</span></span>
  
<span data-ttu-id="a99f5-482">pps 没有</span><span class="sxs-lookup"><span data-stu-id="a99f5-482">pps no</span></span>
  
<span data-ttu-id="a99f5-483">个人服务否</span><span class="sxs-lookup"><span data-stu-id="a99f5-483">personal service no</span></span>
  
<span data-ttu-id="a99f5-484">pps service 否</span><span class="sxs-lookup"><span data-stu-id="a99f5-484">pps service no</span></span>
  
<span data-ttu-id="a99f5-485">ppsno #</span><span class="sxs-lookup"><span data-stu-id="a99f5-485">ppsno#</span></span>
  
<span data-ttu-id="a99f5-486">爱尔兰 pps 没有</span><span class="sxs-lookup"><span data-stu-id="a99f5-486">irish pps no</span></span>
  
<span data-ttu-id="a99f5-487">publicserviceno #</span><span class="sxs-lookup"><span data-stu-id="a99f5-487">publicserviceno#</span></span>
  
<span data-ttu-id="a99f5-488">个人公共服务号码</span><span class="sxs-lookup"><span data-stu-id="a99f5-488">personal public service number</span></span>
  
<span data-ttu-id="a99f5-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="a99f5-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="a99f5-490">pps uimh</span><span class="sxs-lookup"><span data-stu-id="a99f5-490">pps uimh</span></span>
  
<span data-ttu-id="a99f5-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="a99f5-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="a99f5-492">意大利</span><span class="sxs-lookup"><span data-stu-id="a99f5-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="a99f5-493">格式</span><span class="sxs-lookup"><span data-stu-id="a99f5-493">Format</span></span>

<span data-ttu-id="a99f5-494">16 字母和指定的模式中的数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a99f5-495">模式</span><span class="sxs-lookup"><span data-stu-id="a99f5-495">Pattern</span></span>

<span data-ttu-id="a99f5-496">16 字母和数字：</span><span class="sxs-lookup"><span data-stu-id="a99f5-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="a99f5-497">对应于系列名称中的前三个辅音的三个字母</span><span class="sxs-lookup"><span data-stu-id="a99f5-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="a99f5-498">对应于第一、 第三个和第四个的三个字母辅音中第一个名称</span><span class="sxs-lookup"><span data-stu-id="a99f5-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="a99f5-499">两位数的最后一个对应出生年份的数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="a99f5-500">对应于出生月份的一位数 — 字母使用以字母顺序列出，但仅字母 A 到 E、 H、 L、 M、 P、 R T 到使用 （即年 1 月是 A 和年 10 月为 R）</span><span class="sxs-lookup"><span data-stu-id="a99f5-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="a99f5-501">对应于出生 40 其中添加到的女生从男生区分出生日期的月的天的两位数</span><span class="sxs-lookup"><span data-stu-id="a99f5-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="a99f5-502">对应于特定于此人出生上级主管机构区号的四位数字 — 外的国家/地区使用范围内的国家/地区代码</span><span class="sxs-lookup"><span data-stu-id="a99f5-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="a99f5-503">一个检查数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a99f5-504">校验和</span><span class="sxs-lookup"><span data-stu-id="a99f5-504">Checksum</span></span>

<span data-ttu-id="a99f5-505">是</span><span class="sxs-lookup"><span data-stu-id="a99f5-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a99f5-506">定义</span><span class="sxs-lookup"><span data-stu-id="a99f5-506">Definition</span></span>

<span data-ttu-id="a99f5-507">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-508">该函数`Func_italy_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a99f5-509">从关键字`Keywords_italy_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="a99f5-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a99f5-510">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-511">该函数`Func_italy_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="a99f5-512">Keywords</span><span class="sxs-lookup"><span data-stu-id="a99f5-512">Keywords</span></span>

#### <a name="keywordsitalyeutaxfilenumber"></a><span data-ttu-id="a99f5-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a99f5-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="a99f5-514">税号</span><span class="sxs-lookup"><span data-stu-id="a99f5-514">tax number</span></span>
  
<span data-ttu-id="a99f5-515">税费否。</span><span class="sxs-lookup"><span data-stu-id="a99f5-515">tax no.</span></span>
  
<span data-ttu-id="a99f5-516">taxno #</span><span class="sxs-lookup"><span data-stu-id="a99f5-516">taxno#</span></span>
  
<span data-ttu-id="a99f5-517">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="a99f5-517">taxnumber#</span></span>
  
<span data-ttu-id="a99f5-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="a99f5-518">taxnumber</span></span>
  
<span data-ttu-id="a99f5-519">tax id
</span><span class="sxs-lookup"><span data-stu-id="a99f5-519">tax id</span></span>
  
<span data-ttu-id="a99f5-520">taxid #</span><span class="sxs-lookup"><span data-stu-id="a99f5-520">taxid#</span></span>
  
<span data-ttu-id="a99f5-521">会计代码</span><span class="sxs-lookup"><span data-stu-id="a99f5-521">fiscal code</span></span>
  
<span data-ttu-id="a99f5-522">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="a99f5-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="a99f5-523">拉脱维亚</span><span class="sxs-lookup"><span data-stu-id="a99f5-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="a99f5-524">格式</span><span class="sxs-lookup"><span data-stu-id="a99f5-524">Format</span></span>

<span data-ttu-id="a99f5-525">不得含有空格或分隔符 11 位数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a99f5-526">模式</span><span class="sxs-lookup"><span data-stu-id="a99f5-526">Pattern</span></span>

<span data-ttu-id="a99f5-527">11 位数字中指定的模式</span><span class="sxs-lookup"><span data-stu-id="a99f5-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="a99f5-528">对应于月日出生日期的 6 个数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="a99f5-529">对应于出生其中"0"对应于 19 century、"1"对应于 20 世纪和"2"对应于 21 世纪 century 的一位数</span><span class="sxs-lookup"><span data-stu-id="a99f5-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="a99f5-530">四位数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a99f5-531">校验和</span><span class="sxs-lookup"><span data-stu-id="a99f5-531">Checksum</span></span>

<span data-ttu-id="a99f5-532">是</span><span class="sxs-lookup"><span data-stu-id="a99f5-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a99f5-533">定义</span><span class="sxs-lookup"><span data-stu-id="a99f5-533">Definition</span></span>

<span data-ttu-id="a99f5-534">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-535">该函数`Func_latvia_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a99f5-536">从关键字`Keywords_latvia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="a99f5-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a99f5-537">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-538">该函数`Func_latvia_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="a99f5-539">Keywords</span><span class="sxs-lookup"><span data-stu-id="a99f5-539">Keywords</span></span>

#### <a name="keywordslatviaeutaxfilenumber"></a><span data-ttu-id="a99f5-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a99f5-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="a99f5-541">税号</span><span class="sxs-lookup"><span data-stu-id="a99f5-541">tax number</span></span>
  
<span data-ttu-id="a99f5-542">税费否。</span><span class="sxs-lookup"><span data-stu-id="a99f5-542">tax no.</span></span>
  
<span data-ttu-id="a99f5-543">taxno #</span><span class="sxs-lookup"><span data-stu-id="a99f5-543">taxno#</span></span>
  
<span data-ttu-id="a99f5-544">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="a99f5-544">taxnumber#</span></span>
  
<span data-ttu-id="a99f5-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="a99f5-545">taxnumber</span></span>
  
<span data-ttu-id="a99f5-546">tax id
</span><span class="sxs-lookup"><span data-stu-id="a99f5-546">tax id</span></span>
  
<span data-ttu-id="a99f5-547">taxid #</span><span class="sxs-lookup"><span data-stu-id="a99f5-547">taxid#</span></span>
  
<span data-ttu-id="a99f5-548">纳税标识号</span><span class="sxs-lookup"><span data-stu-id="a99f5-548">tax identification number</span></span>
  
<span data-ttu-id="a99f5-549">不纳税标识。</span><span class="sxs-lookup"><span data-stu-id="a99f5-549">tax identification no.</span></span>
  
<span data-ttu-id="a99f5-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="a99f5-550">nodokļa numurs</span></span>
  
<span data-ttu-id="a99f5-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="a99f5-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="a99f5-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="a99f5-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="a99f5-553">立陶宛</span><span class="sxs-lookup"><span data-stu-id="a99f5-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="a99f5-554">格式</span><span class="sxs-lookup"><span data-stu-id="a99f5-554">Format</span></span>

<span data-ttu-id="a99f5-555">不含空格或分隔符 11 位数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a99f5-556">模式</span><span class="sxs-lookup"><span data-stu-id="a99f5-556">Pattern</span></span>

<span data-ttu-id="a99f5-557">11 个数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a99f5-558">校验和</span><span class="sxs-lookup"><span data-stu-id="a99f5-558">Checksum</span></span>

<span data-ttu-id="a99f5-559">不适用</span><span class="sxs-lookup"><span data-stu-id="a99f5-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a99f5-560">定义</span><span class="sxs-lookup"><span data-stu-id="a99f5-560">Definition</span></span>

<span data-ttu-id="a99f5-561">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-562">该函数`Func_lithuania_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a99f5-563">从关键字`Keywords_lithuania_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="a99f5-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a99f5-564">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-565">该函数`Func_lithuania_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="a99f5-566">Keywords</span><span class="sxs-lookup"><span data-stu-id="a99f5-566">Keywords</span></span>

#### <a name="keywordslithuaniaeutaxfilenumber"></a><span data-ttu-id="a99f5-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a99f5-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="a99f5-568">税号</span><span class="sxs-lookup"><span data-stu-id="a99f5-568">tax number</span></span>
  
<span data-ttu-id="a99f5-569">税费否。</span><span class="sxs-lookup"><span data-stu-id="a99f5-569">tax no.</span></span>
  
<span data-ttu-id="a99f5-570">税费无 #</span><span class="sxs-lookup"><span data-stu-id="a99f5-570">tax no#</span></span>
  
<span data-ttu-id="a99f5-571">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="a99f5-571">taxnumber#</span></span>
  
<span data-ttu-id="a99f5-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="a99f5-572">taxnumber</span></span>
  
<span data-ttu-id="a99f5-573">tax id
</span><span class="sxs-lookup"><span data-stu-id="a99f5-573">tax id</span></span>
  
<span data-ttu-id="a99f5-574">taxid #</span><span class="sxs-lookup"><span data-stu-id="a99f5-574">taxid#</span></span>
  
<span data-ttu-id="a99f5-575">纳税标识号</span><span class="sxs-lookup"><span data-stu-id="a99f5-575">tax identification number</span></span>
  
<span data-ttu-id="a99f5-576">不纳税标识。</span><span class="sxs-lookup"><span data-stu-id="a99f5-576">tax identification no.</span></span>
  
<span data-ttu-id="a99f5-577">mokesčių id</span><span class="sxs-lookup"><span data-stu-id="a99f5-577">mokesčių id</span></span>
  
<span data-ttu-id="a99f5-578">mokesčių numeris</span><span class="sxs-lookup"><span data-stu-id="a99f5-578">mokesčių numeris</span></span>
  
<span data-ttu-id="a99f5-579">mokesčių identifikavimas numeris</span><span class="sxs-lookup"><span data-stu-id="a99f5-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="a99f5-580">卢森堡</span><span class="sxs-lookup"><span data-stu-id="a99f5-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="a99f5-581">格式</span><span class="sxs-lookup"><span data-stu-id="a99f5-581">Format</span></span>

<span data-ttu-id="a99f5-582">13 不得含有空格或分隔符的数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a99f5-583">模式</span><span class="sxs-lookup"><span data-stu-id="a99f5-583">Pattern</span></span>

<span data-ttu-id="a99f5-584">13 个数字：</span><span class="sxs-lookup"><span data-stu-id="a99f5-584">13 digits:</span></span>
  
-  <span data-ttu-id="a99f5-585">11 个数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-585">11 digits</span></span> 
    
- <span data-ttu-id="a99f5-586">两个校验位</span><span class="sxs-lookup"><span data-stu-id="a99f5-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a99f5-587">校验和</span><span class="sxs-lookup"><span data-stu-id="a99f5-587">Checksum</span></span>

<span data-ttu-id="a99f5-588">是</span><span class="sxs-lookup"><span data-stu-id="a99f5-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a99f5-589">定义</span><span class="sxs-lookup"><span data-stu-id="a99f5-589">Definition</span></span>

<span data-ttu-id="a99f5-590">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-591">该函数`Func_luxemburg_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a99f5-592">从关键字`Keywords_luxemburg_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="a99f5-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a99f5-593">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-594">该函数`Func_luxemburg_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="a99f5-595">Keywords</span><span class="sxs-lookup"><span data-stu-id="a99f5-595">Keywords</span></span>

#### <a name="keywordsluxemburgeutaxfilenumber"></a><span data-ttu-id="a99f5-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a99f5-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="a99f5-597">税号</span><span class="sxs-lookup"><span data-stu-id="a99f5-597">tax number</span></span>
  
<span data-ttu-id="a99f5-598">税费否。</span><span class="sxs-lookup"><span data-stu-id="a99f5-598">tax no.</span></span>
  
<span data-ttu-id="a99f5-599">taxno #</span><span class="sxs-lookup"><span data-stu-id="a99f5-599">taxno#</span></span>
  
<span data-ttu-id="a99f5-600">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="a99f5-600">taxnumber#</span></span>
  
<span data-ttu-id="a99f5-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="a99f5-601">taxnumber</span></span>
  
<span data-ttu-id="a99f5-602">tax id
</span><span class="sxs-lookup"><span data-stu-id="a99f5-602">tax id</span></span>
  
<span data-ttu-id="a99f5-603">taxid #</span><span class="sxs-lookup"><span data-stu-id="a99f5-603">taxid#</span></span>
  
<span data-ttu-id="a99f5-604">纳税标识号</span><span class="sxs-lookup"><span data-stu-id="a99f5-604">tax identification number</span></span>
  
<span data-ttu-id="a99f5-605">不纳税标识。</span><span class="sxs-lookup"><span data-stu-id="a99f5-605">tax identification no.</span></span>
  
<span data-ttu-id="a99f5-606">steuernummer</span><span class="sxs-lookup"><span data-stu-id="a99f5-606">steuernummer</span></span>
  
<span data-ttu-id="a99f5-607">steuer id</span><span class="sxs-lookup"><span data-stu-id="a99f5-607">steuer id</span></span>
  
<span data-ttu-id="a99f5-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="a99f5-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="a99f5-609">马耳他</span><span class="sxs-lookup"><span data-stu-id="a99f5-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="a99f5-610">格式</span><span class="sxs-lookup"><span data-stu-id="a99f5-610">Format</span></span>

<span data-ttu-id="a99f5-611">为马耳他公民： 7 位数字和指定的模式中的一个字母</span><span class="sxs-lookup"><span data-stu-id="a99f5-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="a99f5-612">非马耳他公民和马耳他实体： 9 位</span><span class="sxs-lookup"><span data-stu-id="a99f5-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a99f5-613">模式</span><span class="sxs-lookup"><span data-stu-id="a99f5-613">Pattern</span></span>

<span data-ttu-id="a99f5-614">马耳他公民： 7 位数字和一个字母</span><span class="sxs-lookup"><span data-stu-id="a99f5-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="a99f5-615">七个数字 </span><span class="sxs-lookup"><span data-stu-id="a99f5-615">Seven digits</span></span> 
    
- <span data-ttu-id="a99f5-616">一个字母 （不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="a99f5-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="a99f5-617">非马耳他公民和马耳他实体： 9 位</span><span class="sxs-lookup"><span data-stu-id="a99f5-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="a99f5-618">九个数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="a99f5-619">校验和</span><span class="sxs-lookup"><span data-stu-id="a99f5-619">Checksum</span></span>

<span data-ttu-id="a99f5-620">不适用</span><span class="sxs-lookup"><span data-stu-id="a99f5-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a99f5-621">定义</span><span class="sxs-lookup"><span data-stu-id="a99f5-621">Definition</span></span>

<span data-ttu-id="a99f5-622">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-623">该函数`Func_malta_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a99f5-624">从关键字`Keywords_malta_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="a99f5-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a99f5-625">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-626">该函数`Func_malta_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="a99f5-627">Keywords</span><span class="sxs-lookup"><span data-stu-id="a99f5-627">Keywords</span></span>

#### <a name="keywordsmaltaeutaxfilenumber"></a><span data-ttu-id="a99f5-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a99f5-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="a99f5-629">税号</span><span class="sxs-lookup"><span data-stu-id="a99f5-629">tax number</span></span>
  
<span data-ttu-id="a99f5-630">税费否。</span><span class="sxs-lookup"><span data-stu-id="a99f5-630">tax no.</span></span>
  
<span data-ttu-id="a99f5-631">taxno #</span><span class="sxs-lookup"><span data-stu-id="a99f5-631">taxno#</span></span>
  
<span data-ttu-id="a99f5-632">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="a99f5-632">taxnumber#</span></span>
  
<span data-ttu-id="a99f5-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="a99f5-633">taxnumber</span></span>
  
<span data-ttu-id="a99f5-634">tax id
</span><span class="sxs-lookup"><span data-stu-id="a99f5-634">tax id</span></span>
  
<span data-ttu-id="a99f5-635">taxid #</span><span class="sxs-lookup"><span data-stu-id="a99f5-635">taxid#</span></span>
  
<span data-ttu-id="a99f5-636">纳税标识号</span><span class="sxs-lookup"><span data-stu-id="a99f5-636">tax identification number</span></span>
  
<span data-ttu-id="a99f5-637">不纳税标识。</span><span class="sxs-lookup"><span data-stu-id="a99f5-637">tax identification no.</span></span>
  
<span data-ttu-id="a99f5-638">numru tat taxxa</span><span class="sxs-lookup"><span data-stu-id="a99f5-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="a99f5-639">id tat taxxa</span><span class="sxs-lookup"><span data-stu-id="a99f5-639">id tat-taxxa</span></span>
  
<span data-ttu-id="a99f5-640">numru 选项卡 identifikazzjoni tat taxxa</span><span class="sxs-lookup"><span data-stu-id="a99f5-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="a99f5-641">荷兰</span><span class="sxs-lookup"><span data-stu-id="a99f5-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="a99f5-642">格式</span><span class="sxs-lookup"><span data-stu-id="a99f5-642">Format</span></span>

<span data-ttu-id="a99f5-643">不含空格或分隔符的九个数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a99f5-644">模式</span><span class="sxs-lookup"><span data-stu-id="a99f5-644">Pattern</span></span>

<span data-ttu-id="a99f5-645">九个数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="a99f5-646">校验和</span><span class="sxs-lookup"><span data-stu-id="a99f5-646">Checksum</span></span>

<span data-ttu-id="a99f5-647">是</span><span class="sxs-lookup"><span data-stu-id="a99f5-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a99f5-648">定义</span><span class="sxs-lookup"><span data-stu-id="a99f5-648">Definition</span></span>

<span data-ttu-id="a99f5-649">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-650">该函数`Func_netherlands_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a99f5-651">从关键字`Keywords_netherlands_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="a99f5-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a99f5-652">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-653">该函数`Func_netherlands_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="a99f5-654">Keywords</span><span class="sxs-lookup"><span data-stu-id="a99f5-654">Keywords</span></span>

#### <a name="keywordsnetherlandseutaxfilenumber"></a><span data-ttu-id="a99f5-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a99f5-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="a99f5-656">荷兰纳税标识号</span><span class="sxs-lookup"><span data-stu-id="a99f5-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="a99f5-657">荷兰税标识</span><span class="sxs-lookup"><span data-stu-id="a99f5-657">netherlands tax identification</span></span>
  
<span data-ttu-id="a99f5-658">荷属安的纳税标识号</span><span class="sxs-lookup"><span data-stu-id="a99f5-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="a99f5-659">荷属安的税费标识</span><span class="sxs-lookup"><span data-stu-id="a99f5-659">netherland's tax identification</span></span>
  
<span data-ttu-id="a99f5-660">纳税标识号</span><span class="sxs-lookup"><span data-stu-id="a99f5-660">tax identification number</span></span>
  
<span data-ttu-id="a99f5-661">荷兰税务 id</span><span class="sxs-lookup"><span data-stu-id="a99f5-661">dutch tax id</span></span>
  
<span data-ttu-id="a99f5-662">荷兰税务标识号</span><span class="sxs-lookup"><span data-stu-id="a99f5-662">dutch tax identification number</span></span>
  
<span data-ttu-id="a99f5-663">tax id
</span><span class="sxs-lookup"><span data-stu-id="a99f5-663">tax id</span></span>
  
<span data-ttu-id="a99f5-664">税费 id #</span><span class="sxs-lookup"><span data-stu-id="a99f5-664">tax id#</span></span>
  
<span data-ttu-id="a99f5-665">税号</span><span class="sxs-lookup"><span data-stu-id="a99f5-665">tax number</span></span>
  
<span data-ttu-id="a99f5-666">税费无 #</span><span class="sxs-lookup"><span data-stu-id="a99f5-666">tax no#</span></span>
  
<span data-ttu-id="a99f5-667">税费 #</span><span class="sxs-lookup"><span data-stu-id="a99f5-667">tax#</span></span>
  
<span data-ttu-id="a99f5-668">tin
</span><span class="sxs-lookup"><span data-stu-id="a99f5-668">tin</span></span>
  
<span data-ttu-id="a99f5-669">会议 #</span><span class="sxs-lookup"><span data-stu-id="a99f5-669">tin#</span></span>
  
<span data-ttu-id="a99f5-670">荷兰会议</span><span class="sxs-lookup"><span data-stu-id="a99f5-670">netherlands tin</span></span>
  
<span data-ttu-id="a99f5-671">荷属安的会议</span><span class="sxs-lookup"><span data-stu-id="a99f5-671">netherland's tin</span></span>
  
<span data-ttu-id="a99f5-672">nederlands belasting identificatienummer</span><span class="sxs-lookup"><span data-stu-id="a99f5-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="a99f5-673">identificatienummer van belasting</span><span class="sxs-lookup"><span data-stu-id="a99f5-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="a99f5-674">identificatienummer belasting</span><span class="sxs-lookup"><span data-stu-id="a99f5-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="a99f5-675">nederlands belasting identificatie</span><span class="sxs-lookup"><span data-stu-id="a99f5-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="a99f5-676">nederlands belasting id nummer</span><span class="sxs-lookup"><span data-stu-id="a99f5-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="a99f5-677">nederlands belastingnummer</span><span class="sxs-lookup"><span data-stu-id="a99f5-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="a99f5-678">顺便说一下 nummer</span><span class="sxs-lookup"><span data-stu-id="a99f5-678">btw nummer</span></span>
  
<span data-ttu-id="a99f5-679">nederlandse belasting identificatie</span><span class="sxs-lookup"><span data-stu-id="a99f5-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="a99f5-680">波兰</span><span class="sxs-lookup"><span data-stu-id="a99f5-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="a99f5-681">格式</span><span class="sxs-lookup"><span data-stu-id="a99f5-681">Format</span></span>

<span data-ttu-id="a99f5-682">不得含有空格或分隔符 11 个数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a99f5-683">模式</span><span class="sxs-lookup"><span data-stu-id="a99f5-683">Pattern</span></span>

<span data-ttu-id="a99f5-684">11 个数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a99f5-685">校验和</span><span class="sxs-lookup"><span data-stu-id="a99f5-685">Checksum</span></span>

<span data-ttu-id="a99f5-686">是</span><span class="sxs-lookup"><span data-stu-id="a99f5-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a99f5-687">定义</span><span class="sxs-lookup"><span data-stu-id="a99f5-687">Definition</span></span>

<span data-ttu-id="a99f5-688">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-689">该函数`Func_poland_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a99f5-690">从关键字`Keywords_poland_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="a99f5-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a99f5-691">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-692">该函数`Func_poland_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="a99f5-693">Keywords</span><span class="sxs-lookup"><span data-stu-id="a99f5-693">Keywords</span></span>

#### <a name="keywordspolandeutaxfilenumber"></a><span data-ttu-id="a99f5-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a99f5-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="a99f5-695">税号</span><span class="sxs-lookup"><span data-stu-id="a99f5-695">tax number</span></span>
  
<span data-ttu-id="a99f5-696">税费否。</span><span class="sxs-lookup"><span data-stu-id="a99f5-696">tax no.</span></span>
  
<span data-ttu-id="a99f5-697">taxno #</span><span class="sxs-lookup"><span data-stu-id="a99f5-697">taxno#</span></span>
  
<span data-ttu-id="a99f5-698">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="a99f5-698">taxnumber#</span></span>
  
<span data-ttu-id="a99f5-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="a99f5-699">taxnumber</span></span>
  
<span data-ttu-id="a99f5-700">nip</span><span class="sxs-lookup"><span data-stu-id="a99f5-700">nip</span></span>
  
<span data-ttu-id="a99f5-701">nip #</span><span class="sxs-lookup"><span data-stu-id="a99f5-701">nip#</span></span>
  
<span data-ttu-id="a99f5-702">tax id
</span><span class="sxs-lookup"><span data-stu-id="a99f5-702">tax id</span></span>
  
<span data-ttu-id="a99f5-703">税费 id #</span><span class="sxs-lookup"><span data-stu-id="a99f5-703">tax id#</span></span>
  
<span data-ttu-id="a99f5-704">nip id</span><span class="sxs-lookup"><span data-stu-id="a99f5-704">nip id</span></span>
  
<span data-ttu-id="a99f5-705">nip id #</span><span class="sxs-lookup"><span data-stu-id="a99f5-705">nip id#</span></span>
  
<span data-ttu-id="a99f5-706">纳税标识号</span><span class="sxs-lookup"><span data-stu-id="a99f5-706">tax identification number</span></span>
  
<span data-ttu-id="a99f5-707">不纳税标识。</span><span class="sxs-lookup"><span data-stu-id="a99f5-707">tax identification no.</span></span>
  
<span data-ttu-id="a99f5-708">增值税编号</span><span class="sxs-lookup"><span data-stu-id="a99f5-708">vat number</span></span>
  
<span data-ttu-id="a99f5-709">增值税否。</span><span class="sxs-lookup"><span data-stu-id="a99f5-709">vat no.</span></span>
  
<span data-ttu-id="a99f5-710">vatno #</span><span class="sxs-lookup"><span data-stu-id="a99f5-710">vatno#</span></span>
  
<span data-ttu-id="a99f5-711">增值税 id</span><span class="sxs-lookup"><span data-stu-id="a99f5-711">vat id</span></span>
  
<span data-ttu-id="a99f5-712">增值税 id #</span><span class="sxs-lookup"><span data-stu-id="a99f5-712">vat id#</span></span>
  
<span data-ttu-id="a99f5-713">个数 identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="a99f5-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="a99f5-714">polski 个数 identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="a99f5-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="a99f5-715">numeridentyfikacjipodatkowej #</span><span class="sxs-lookup"><span data-stu-id="a99f5-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="a99f5-716">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="a99f5-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="a99f5-717">格式</span><span class="sxs-lookup"><span data-stu-id="a99f5-717">Format</span></span>

<span data-ttu-id="a99f5-718">不得含有空格或分隔符的九个数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a99f5-719">模式</span><span class="sxs-lookup"><span data-stu-id="a99f5-719">Pattern</span></span>

<span data-ttu-id="a99f5-720">九个数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a99f5-721">校验和</span><span class="sxs-lookup"><span data-stu-id="a99f5-721">Checksum</span></span>

<span data-ttu-id="a99f5-722">是</span><span class="sxs-lookup"><span data-stu-id="a99f5-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a99f5-723">定义</span><span class="sxs-lookup"><span data-stu-id="a99f5-723">Definition</span></span>

<span data-ttu-id="a99f5-724">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-725">该函数`Func_portugal_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a99f5-726">从关键字`Keywords_portugal_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="a99f5-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a99f5-727">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-728">该函数`Func_portugal_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="a99f5-729">Keywords</span><span class="sxs-lookup"><span data-stu-id="a99f5-729">Keywords</span></span>

#### <a name="keywordsportugaleutaxfilenumber"></a><span data-ttu-id="a99f5-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a99f5-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="a99f5-731">税号</span><span class="sxs-lookup"><span data-stu-id="a99f5-731">tax number</span></span>
  
<span data-ttu-id="a99f5-732">税费否。</span><span class="sxs-lookup"><span data-stu-id="a99f5-732">tax no.</span></span>
  
<span data-ttu-id="a99f5-733">taxno #</span><span class="sxs-lookup"><span data-stu-id="a99f5-733">taxno#</span></span>
  
<span data-ttu-id="a99f5-734">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="a99f5-734">taxnumber#</span></span>
  
<span data-ttu-id="a99f5-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="a99f5-735">taxnumber</span></span>
  
<span data-ttu-id="a99f5-736">n 如果</span><span class="sxs-lookup"><span data-stu-id="a99f5-736">nif</span></span>
  
<span data-ttu-id="a99f5-737">n 如果 #</span><span class="sxs-lookup"><span data-stu-id="a99f5-737">nif#</span></span>
  
<span data-ttu-id="a99f5-738">会计 numero</span><span class="sxs-lookup"><span data-stu-id="a99f5-738">numero fiscal</span></span>
  
<span data-ttu-id="a99f5-739">número de identificação 会计</span><span class="sxs-lookup"><span data-stu-id="a99f5-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="a99f5-740">罗马尼亚</span><span class="sxs-lookup"><span data-stu-id="a99f5-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="a99f5-741">格式</span><span class="sxs-lookup"><span data-stu-id="a99f5-741">Format</span></span>

<span data-ttu-id="a99f5-742">13 不得含有空格或分隔符的数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a99f5-743">模式</span><span class="sxs-lookup"><span data-stu-id="a99f5-743">Pattern</span></span>

<span data-ttu-id="a99f5-744">13 位数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a99f5-745">校验和</span><span class="sxs-lookup"><span data-stu-id="a99f5-745">Checksum</span></span>

<span data-ttu-id="a99f5-746">不适用</span><span class="sxs-lookup"><span data-stu-id="a99f5-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a99f5-747">定义</span><span class="sxs-lookup"><span data-stu-id="a99f5-747">Definition</span></span>

<span data-ttu-id="a99f5-748">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-749">正则表达式`Regex_romania_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a99f5-750">从关键字`Keywords_romania_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="a99f5-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a99f5-751">Keywords</span><span class="sxs-lookup"><span data-stu-id="a99f5-751">Keywords</span></span>

#### <a name="keywordsromaniaeutaxfilenumber"></a><span data-ttu-id="a99f5-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a99f5-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="a99f5-753">tax id
</span><span class="sxs-lookup"><span data-stu-id="a99f5-753">tax id</span></span>
  
<span data-ttu-id="a99f5-754">税号</span><span class="sxs-lookup"><span data-stu-id="a99f5-754">tax id number</span></span>
  
<span data-ttu-id="a99f5-755">不税费文件</span><span class="sxs-lookup"><span data-stu-id="a99f5-755">tax file no</span></span>
  
<span data-ttu-id="a99f5-756">

tax file number</span><span class="sxs-lookup"><span data-stu-id="a99f5-756">tax file number</span></span>
  
<span data-ttu-id="a99f5-757">税费否</span><span class="sxs-lookup"><span data-stu-id="a99f5-757">tax no</span></span>
  
<span data-ttu-id="a99f5-758">税号</span><span class="sxs-lookup"><span data-stu-id="a99f5-758">tax number</span></span>
  
<span data-ttu-id="a99f5-759">taxid #</span><span class="sxs-lookup"><span data-stu-id="a99f5-759">taxid#</span></span>
  
<span data-ttu-id="a99f5-760">taxno #</span><span class="sxs-lookup"><span data-stu-id="a99f5-760">taxno#</span></span>
  
<span data-ttu-id="a99f5-761">id ul taxei</span><span class="sxs-lookup"><span data-stu-id="a99f5-761">id-ul taxei</span></span>
  
<span data-ttu-id="a99f5-762">numărul de identificare fiscală</span><span class="sxs-lookup"><span data-stu-id="a99f5-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="a99f5-763">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="a99f5-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="a99f5-764">格式</span><span class="sxs-lookup"><span data-stu-id="a99f5-764">Format</span></span>

<span data-ttu-id="a99f5-765">不得含有空格或分隔符的 10 位数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a99f5-766">模式</span><span class="sxs-lookup"><span data-stu-id="a99f5-766">Pattern</span></span>

<span data-ttu-id="a99f5-767">10 个数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a99f5-768">校验和</span><span class="sxs-lookup"><span data-stu-id="a99f5-768">Checksum</span></span>

<span data-ttu-id="a99f5-769">不适用</span><span class="sxs-lookup"><span data-stu-id="a99f5-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a99f5-770">定义</span><span class="sxs-lookup"><span data-stu-id="a99f5-770">Definition</span></span>

<span data-ttu-id="a99f5-771">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-772">正则表达式`Regex_slovakia_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a99f5-773">从关键字`Keywords_slovakia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="a99f5-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a99f5-774">Keywords</span><span class="sxs-lookup"><span data-stu-id="a99f5-774">Keywords</span></span>

#### <a name="keywordsslovakiaeutaxfilenumber"></a><span data-ttu-id="a99f5-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a99f5-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="a99f5-776">tax id
</span><span class="sxs-lookup"><span data-stu-id="a99f5-776">tax id</span></span>
  
<span data-ttu-id="a99f5-777">税号</span><span class="sxs-lookup"><span data-stu-id="a99f5-777">tax id number</span></span>
  
<span data-ttu-id="a99f5-778">锡 id</span><span class="sxs-lookup"><span data-stu-id="a99f5-778">tin id</span></span>
  
<span data-ttu-id="a99f5-779">锡否</span><span class="sxs-lookup"><span data-stu-id="a99f5-779">tin no</span></span>
  
<span data-ttu-id="a99f5-780">斯洛伐克语锡 id</span><span class="sxs-lookup"><span data-stu-id="a99f5-780">slovakian tin id</span></span>
  
<span data-ttu-id="a99f5-781">tin
</span><span class="sxs-lookup"><span data-stu-id="a99f5-781">tin</span></span>
  
<span data-ttu-id="a99f5-782">不税费文件</span><span class="sxs-lookup"><span data-stu-id="a99f5-782">tax file no</span></span>
  
<span data-ttu-id="a99f5-783">

tax file number</span><span class="sxs-lookup"><span data-stu-id="a99f5-783">tax file number</span></span>
  
<span data-ttu-id="a99f5-784">税费否</span><span class="sxs-lookup"><span data-stu-id="a99f5-784">tax no</span></span>
  
<span data-ttu-id="a99f5-785">税号</span><span class="sxs-lookup"><span data-stu-id="a99f5-785">tax number</span></span>
  
<span data-ttu-id="a99f5-786">taxid #</span><span class="sxs-lookup"><span data-stu-id="a99f5-786">taxid#</span></span>
  
<span data-ttu-id="a99f5-787">taxno #</span><span class="sxs-lookup"><span data-stu-id="a99f5-787">taxno#</span></span>
  
<span data-ttu-id="a99f5-788">daňové identifikačné číslo</span><span class="sxs-lookup"><span data-stu-id="a99f5-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="a99f5-789">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="a99f5-789">daňové číslo</span></span>
  
<span data-ttu-id="a99f5-790">daňové číslo súboru</span><span class="sxs-lookup"><span data-stu-id="a99f5-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="a99f5-791">斯诺文尼亚</span><span class="sxs-lookup"><span data-stu-id="a99f5-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="a99f5-792">格式</span><span class="sxs-lookup"><span data-stu-id="a99f5-792">Format</span></span>

<span data-ttu-id="a99f5-793">不得含有空格或分隔符的八个数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a99f5-794">模式</span><span class="sxs-lookup"><span data-stu-id="a99f5-794">Pattern</span></span>

<span data-ttu-id="a99f5-795">八个数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a99f5-796">校验和</span><span class="sxs-lookup"><span data-stu-id="a99f5-796">Checksum</span></span>

<span data-ttu-id="a99f5-797">是</span><span class="sxs-lookup"><span data-stu-id="a99f5-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a99f5-798">定义</span><span class="sxs-lookup"><span data-stu-id="a99f5-798">Definition</span></span>

<span data-ttu-id="a99f5-799">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-800">该函数`Func_slovenia_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a99f5-801">从关键字`Keywords_slovenia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="a99f5-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a99f5-802">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-803">该函数`Func_slovenia_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="a99f5-804">Keywords</span><span class="sxs-lookup"><span data-stu-id="a99f5-804">Keywords</span></span>

#### <a name="keywordssloveniaeutaxfilenumber"></a><span data-ttu-id="a99f5-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a99f5-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="a99f5-806">tax id
</span><span class="sxs-lookup"><span data-stu-id="a99f5-806">tax id</span></span>
  
<span data-ttu-id="a99f5-807">税号</span><span class="sxs-lookup"><span data-stu-id="a99f5-807">tax id number</span></span>
  
<span data-ttu-id="a99f5-808">锡 id</span><span class="sxs-lookup"><span data-stu-id="a99f5-808">tin id</span></span>
  
<span data-ttu-id="a99f5-809">锡否</span><span class="sxs-lookup"><span data-stu-id="a99f5-809">tin no</span></span>
  
<span data-ttu-id="a99f5-810">斯洛文尼亚语锡 id</span><span class="sxs-lookup"><span data-stu-id="a99f5-810">slovenian tin id</span></span>
  
<span data-ttu-id="a99f5-811">tin
</span><span class="sxs-lookup"><span data-stu-id="a99f5-811">tin</span></span>
  
<span data-ttu-id="a99f5-812">不税费文件</span><span class="sxs-lookup"><span data-stu-id="a99f5-812">tax file no</span></span>
  
<span data-ttu-id="a99f5-813">

tax file number</span><span class="sxs-lookup"><span data-stu-id="a99f5-813">tax file number</span></span>
  
<span data-ttu-id="a99f5-814">税费否</span><span class="sxs-lookup"><span data-stu-id="a99f5-814">tax no</span></span>
  
<span data-ttu-id="a99f5-815">税号</span><span class="sxs-lookup"><span data-stu-id="a99f5-815">tax number</span></span>
  
<span data-ttu-id="a99f5-816">taxid #</span><span class="sxs-lookup"><span data-stu-id="a99f5-816">taxid#</span></span>
  
<span data-ttu-id="a99f5-817">taxno #</span><span class="sxs-lookup"><span data-stu-id="a99f5-817">taxno#</span></span>
  
<span data-ttu-id="a99f5-818">identifikacijska številka davka</span><span class="sxs-lookup"><span data-stu-id="a99f5-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="a99f5-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="a99f5-819">davčna številka</span></span>
  
<span data-ttu-id="a99f5-820">Številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="a99f5-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="a99f5-821">西班牙</span><span class="sxs-lookup"><span data-stu-id="a99f5-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="a99f5-822">格式</span><span class="sxs-lookup"><span data-stu-id="a99f5-822">Format</span></span>

<span data-ttu-id="a99f5-823">七个或八个数字和指定的模式中的一个或两个字母</span><span class="sxs-lookup"><span data-stu-id="a99f5-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a99f5-824">模式</span><span class="sxs-lookup"><span data-stu-id="a99f5-824">Pattern</span></span>

<span data-ttu-id="a99f5-825">西班牙国家/地区身份证与西班牙语自然人员：</span><span class="sxs-lookup"><span data-stu-id="a99f5-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="a99f5-826">八个数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-826">Eight digits</span></span> 
    
- <span data-ttu-id="a99f5-827">一个大写字母 （区分大小写）</span><span class="sxs-lookup"><span data-stu-id="a99f5-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="a99f5-828">西班牙国家/地区身份证不非居民 Spaniards</span><span class="sxs-lookup"><span data-stu-id="a99f5-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="a99f5-829">一个大写字母"L"（区分大小写）</span><span class="sxs-lookup"><span data-stu-id="a99f5-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="a99f5-830">七个数字 </span><span class="sxs-lookup"><span data-stu-id="a99f5-830">Seven digits</span></span>
    
- <span data-ttu-id="a99f5-831">一个大写字母 （区分大小写）</span><span class="sxs-lookup"><span data-stu-id="a99f5-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="a99f5-832">14 年不西班牙国家/地区身份证岁驻留 Spaniards:</span><span class="sxs-lookup"><span data-stu-id="a99f5-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="a99f5-833">一个大写字母"K"（区分大小写）</span><span class="sxs-lookup"><span data-stu-id="a99f5-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="a99f5-834">七个数字 </span><span class="sxs-lookup"><span data-stu-id="a99f5-834">Seven digits</span></span> 
    
- <span data-ttu-id="a99f5-835">一个大写字母 （区分大小写）</span><span class="sxs-lookup"><span data-stu-id="a99f5-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="a99f5-836">与 Foreigner 标识号外国人</span><span class="sxs-lookup"><span data-stu-id="a99f5-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="a99f5-837">一个大写字母的字母"X"、"Y"或"Z"（区分大小写）</span><span class="sxs-lookup"><span data-stu-id="a99f5-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="a99f5-838">七个数字 </span><span class="sxs-lookup"><span data-stu-id="a99f5-838">Seven digits</span></span>
    
- <span data-ttu-id="a99f5-839">一个大写字母 （区分大小写）</span><span class="sxs-lookup"><span data-stu-id="a99f5-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="a99f5-840">外国人不 Foreigner 标识号</span><span class="sxs-lookup"><span data-stu-id="a99f5-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="a99f5-841">一个大写字母的"M"（区分大小写）</span><span class="sxs-lookup"><span data-stu-id="a99f5-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="a99f5-842">七个数字 </span><span class="sxs-lookup"><span data-stu-id="a99f5-842">Seven digits</span></span>
    
- <span data-ttu-id="a99f5-843">一个大写字母 （区分大小写）</span><span class="sxs-lookup"><span data-stu-id="a99f5-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="a99f5-844">校验和</span><span class="sxs-lookup"><span data-stu-id="a99f5-844">Checksum</span></span>

<span data-ttu-id="a99f5-845">是</span><span class="sxs-lookup"><span data-stu-id="a99f5-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a99f5-846">定义</span><span class="sxs-lookup"><span data-stu-id="a99f5-846">Definition</span></span>

<span data-ttu-id="a99f5-847">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-848">该函数`Func_spain_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a99f5-849">从关键字`Keywords_spain_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="a99f5-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a99f5-850">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-851">该函数`Func_spain_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="a99f5-852">Keywords</span><span class="sxs-lookup"><span data-stu-id="a99f5-852">Keywords</span></span>

#### <a name="keywordsspaineutaxfilenumber"></a><span data-ttu-id="a99f5-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a99f5-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="a99f5-854">tax id
</span><span class="sxs-lookup"><span data-stu-id="a99f5-854">tax id</span></span>
  
<span data-ttu-id="a99f5-855">税号</span><span class="sxs-lookup"><span data-stu-id="a99f5-855">tax id number</span></span>
  
<span data-ttu-id="a99f5-856">cif id</span><span class="sxs-lookup"><span data-stu-id="a99f5-856">cif id</span></span>
  
<span data-ttu-id="a99f5-857">cif 没有</span><span class="sxs-lookup"><span data-stu-id="a99f5-857">cif no</span></span>
  
<span data-ttu-id="a99f5-858">西班牙语 cif id</span><span class="sxs-lookup"><span data-stu-id="a99f5-858">spanish cif id</span></span>
  
<span data-ttu-id="a99f5-859">cif</span><span class="sxs-lookup"><span data-stu-id="a99f5-859">cif</span></span>
  
<span data-ttu-id="a99f5-860">不税费文件</span><span class="sxs-lookup"><span data-stu-id="a99f5-860">tax file no</span></span>
  
<span data-ttu-id="a99f5-861">西班牙语 cif 号码</span><span class="sxs-lookup"><span data-stu-id="a99f5-861">spanish cif number</span></span>
  
<span data-ttu-id="a99f5-862">

tax file number</span><span class="sxs-lookup"><span data-stu-id="a99f5-862">tax file number</span></span>
  
<span data-ttu-id="a99f5-863">西班牙语 cif 没有</span><span class="sxs-lookup"><span data-stu-id="a99f5-863">spanish cif no</span></span>
  
<span data-ttu-id="a99f5-864">税费否</span><span class="sxs-lookup"><span data-stu-id="a99f5-864">tax no</span></span>
  
<span data-ttu-id="a99f5-865">税号</span><span class="sxs-lookup"><span data-stu-id="a99f5-865">tax number</span></span>
  
<span data-ttu-id="a99f5-866">taxid #</span><span class="sxs-lookup"><span data-stu-id="a99f5-866">taxid#</span></span>
  
<span data-ttu-id="a99f5-867">taxno #</span><span class="sxs-lookup"><span data-stu-id="a99f5-867">taxno#</span></span>
  
<span data-ttu-id="a99f5-868">cifid #</span><span class="sxs-lookup"><span data-stu-id="a99f5-868">cifid#</span></span>
  
<span data-ttu-id="a99f5-869">spanishcifid #</span><span class="sxs-lookup"><span data-stu-id="a99f5-869">spanishcifid#</span></span>
  
<span data-ttu-id="a99f5-870">spanishcifno #</span><span class="sxs-lookup"><span data-stu-id="a99f5-870">spanishcifno#</span></span>
  
<span data-ttu-id="a99f5-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="a99f5-871">número de contribuyente</span></span>
  
<span data-ttu-id="a99f5-872">número de impuesto corporativo</span><span class="sxs-lookup"><span data-stu-id="a99f5-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="a99f5-873">número de identificación 会计</span><span class="sxs-lookup"><span data-stu-id="a99f5-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="a99f5-874">cif número</span><span class="sxs-lookup"><span data-stu-id="a99f5-874">cif número</span></span>
  
<span data-ttu-id="a99f5-875">cifnúmero #</span><span class="sxs-lookup"><span data-stu-id="a99f5-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="a99f5-876">瑞典</span><span class="sxs-lookup"><span data-stu-id="a99f5-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="a99f5-877">格式</span><span class="sxs-lookup"><span data-stu-id="a99f5-877">Format</span></span>

<span data-ttu-id="a99f5-878">10 位数字和中指定的模式的符号</span><span class="sxs-lookup"><span data-stu-id="a99f5-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a99f5-879">模式</span><span class="sxs-lookup"><span data-stu-id="a99f5-879">Pattern</span></span>

<span data-ttu-id="a99f5-880">10 位数字和一个符号：</span><span class="sxs-lookup"><span data-stu-id="a99f5-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="a99f5-881">对应于出生日期 (YYMMDD) 的 6 个数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="a99f5-882">加号、 减号或反斜杠</span><span class="sxs-lookup"><span data-stu-id="a99f5-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="a99f5-883">进行标识的三个数字数字唯一位置：</span><span class="sxs-lookup"><span data-stu-id="a99f5-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="a99f5-884">对于之前 1990年颁发的数字，第七个和第八个数字标识出生或 foreign-born 人员的县</span><span class="sxs-lookup"><span data-stu-id="a99f5-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="a99f5-885">第九个位置中的数字的任一奇数男性或甚至女性指示性别</span><span class="sxs-lookup"><span data-stu-id="a99f5-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="a99f5-886">一个检查数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a99f5-887">校验和</span><span class="sxs-lookup"><span data-stu-id="a99f5-887">Checksum</span></span>

<span data-ttu-id="a99f5-888">是</span><span class="sxs-lookup"><span data-stu-id="a99f5-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a99f5-889">定义</span><span class="sxs-lookup"><span data-stu-id="a99f5-889">Definition</span></span>

<span data-ttu-id="a99f5-890">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-891">该函数`Func_sweden_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a99f5-892">从关键字`Keywords_sweden_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="a99f5-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a99f5-893">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-894">该函数`Func_sweden_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="a99f5-895">Keywords</span><span class="sxs-lookup"><span data-stu-id="a99f5-895">Keywords</span></span>

#### <a name="keywordsswedeneutaxfilenumber"></a><span data-ttu-id="a99f5-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a99f5-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="a99f5-897">tax id
</span><span class="sxs-lookup"><span data-stu-id="a99f5-897">tax id</span></span>
  
<span data-ttu-id="a99f5-898">不税费 id。</span><span class="sxs-lookup"><span data-stu-id="a99f5-898">tax id no.</span></span>
  
<span data-ttu-id="a99f5-899">税号</span><span class="sxs-lookup"><span data-stu-id="a99f5-899">tax id number</span></span>
  
<span data-ttu-id="a99f5-900">tax identification
</span><span class="sxs-lookup"><span data-stu-id="a99f5-900">tax identification</span></span>
  
<span data-ttu-id="a99f5-901">税费标识 #</span><span class="sxs-lookup"><span data-stu-id="a99f5-901">tax identification#</span></span>
  
<span data-ttu-id="a99f5-902">税费否。</span><span class="sxs-lookup"><span data-stu-id="a99f5-902">tax no.</span></span>
  
<span data-ttu-id="a99f5-903">税费 #</span><span class="sxs-lookup"><span data-stu-id="a99f5-903">tax#</span></span>
  
<span data-ttu-id="a99f5-904">taxid #</span><span class="sxs-lookup"><span data-stu-id="a99f5-904">taxid#</span></span>
  
<span data-ttu-id="a99f5-905">税费文件</span><span class="sxs-lookup"><span data-stu-id="a99f5-905">tax file</span></span>
  
<span data-ttu-id="a99f5-906">不税费文件。</span><span class="sxs-lookup"><span data-stu-id="a99f5-906">tax file no.</span></span>
  
<span data-ttu-id="a99f5-907">个人标识号</span><span class="sxs-lookup"><span data-stu-id="a99f5-907">personal id number</span></span>
  
<span data-ttu-id="a99f5-908">skatt id nummer</span><span class="sxs-lookup"><span data-stu-id="a99f5-908">skatt id nummer</span></span>
  
<span data-ttu-id="a99f5-909">skatt identifikation</span><span class="sxs-lookup"><span data-stu-id="a99f5-909">skatt identifikation</span></span>
  
<span data-ttu-id="a99f5-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="a99f5-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="a99f5-911">英国</span><span class="sxs-lookup"><span data-stu-id="a99f5-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="a99f5-912">格式</span><span class="sxs-lookup"><span data-stu-id="a99f5-912">Format</span></span>

<span data-ttu-id="a99f5-913">没有空格和分隔符的唯一纳税人引用 (UTR): 10 位数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="a99f5-p103">国家保险号码 (NINO): 有关详细信息，请参阅"英国 National 保险号码 (NINO)"部分中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="a99f5-p103">National Insurance Number (NINO): For details, see the section "U.K. National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a99f5-916">模式</span><span class="sxs-lookup"><span data-stu-id="a99f5-916">Pattern</span></span>

<span data-ttu-id="a99f5-917">唯一纳税人引用 (UTR): 10 位数字</span><span class="sxs-lookup"><span data-stu-id="a99f5-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="a99f5-p104">国家保险号码 (NINO): 有关详细信息，请参阅"英国 National 保险号码 (NINO)"部分中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="a99f5-p104">National Insurance Number (NINO): For details, see the section "U.K. National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a99f5-920">校验和</span><span class="sxs-lookup"><span data-stu-id="a99f5-920">Checksum</span></span>

<span data-ttu-id="a99f5-921">是</span><span class="sxs-lookup"><span data-stu-id="a99f5-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a99f5-922">定义</span><span class="sxs-lookup"><span data-stu-id="a99f5-922">Definition</span></span>

<span data-ttu-id="a99f5-923">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a99f5-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a99f5-924">该函数`Func_uk_eu_tax_file_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a99f5-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a99f5-925">从关键字`Keywords_uk_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="a99f5-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a99f5-926">Keywords</span><span class="sxs-lookup"><span data-stu-id="a99f5-926">Keywords</span></span>

#### <a name="keywordsukeutaxfilenumber"></a><span data-ttu-id="a99f5-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a99f5-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="a99f5-928">tax id
</span><span class="sxs-lookup"><span data-stu-id="a99f5-928">tax id</span></span>
  
<span data-ttu-id="a99f5-929">不税费 id。</span><span class="sxs-lookup"><span data-stu-id="a99f5-929">tax id no.</span></span>
  
<span data-ttu-id="a99f5-930">税号</span><span class="sxs-lookup"><span data-stu-id="a99f5-930">tax id number</span></span>
  
<span data-ttu-id="a99f5-931">tax identification
</span><span class="sxs-lookup"><span data-stu-id="a99f5-931">tax identification</span></span>
  
<span data-ttu-id="a99f5-932">税费标识 #</span><span class="sxs-lookup"><span data-stu-id="a99f5-932">tax identification#</span></span>
  
<span data-ttu-id="a99f5-933">税费否。</span><span class="sxs-lookup"><span data-stu-id="a99f5-933">tax no.</span></span>
  
<span data-ttu-id="a99f5-934">税费 #</span><span class="sxs-lookup"><span data-stu-id="a99f5-934">tax#</span></span>
  
<span data-ttu-id="a99f5-935">taxid #</span><span class="sxs-lookup"><span data-stu-id="a99f5-935">taxid#</span></span>
  
<span data-ttu-id="a99f5-936">税费文件</span><span class="sxs-lookup"><span data-stu-id="a99f5-936">tax file</span></span>
  
<span data-ttu-id="a99f5-937">不税费文件。</span><span class="sxs-lookup"><span data-stu-id="a99f5-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a99f5-938">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a99f5-938">See also</span></span>

[<span data-ttu-id="a99f5-939">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="a99f5-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

