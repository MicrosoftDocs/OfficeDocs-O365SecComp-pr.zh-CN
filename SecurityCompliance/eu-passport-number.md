---
title: EU 护照号码
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主题介绍当数据丢失防护 (DLP) 策略检测到欧盟护照号敏感信息类型时, 应查找什么内容。 此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。
ms.openlocfilehash: fa3be04dec0f71a2568e046abd6b0af3e20181c5
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152964"
---
# <a name="eu-passport-number"></a><span data-ttu-id="a849b-104">EU 护照号码</span><span class="sxs-lookup"><span data-stu-id="a849b-104">EU Passport Number</span></span>

<span data-ttu-id="a849b-105">本主题介绍当数据丢失防护 (DLP) 策略检测到欧盟护照号敏感信息类型时, 应查找什么内容。</span><span class="sxs-lookup"><span data-stu-id="a849b-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="a849b-106">此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。</span><span class="sxs-lookup"><span data-stu-id="a849b-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="a849b-107">奥地利</span><span class="sxs-lookup"><span data-stu-id="a849b-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="a849b-108">Format</span><span class="sxs-lookup"><span data-stu-id="a849b-108">Format</span></span>

<span data-ttu-id="a849b-109">一个字母后跟一个可选空格和七个数字</span><span class="sxs-lookup"><span data-stu-id="a849b-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a849b-110">模式</span><span class="sxs-lookup"><span data-stu-id="a849b-110">Pattern</span></span>

<span data-ttu-id="a849b-111">一个字母、七个数字和一个空格的组合:</span><span class="sxs-lookup"><span data-stu-id="a849b-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="a849b-112">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="a849b-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="a849b-113">一个空格 (可选)</span><span class="sxs-lookup"><span data-stu-id="a849b-113">One space (optional)</span></span>
    
- <span data-ttu-id="a849b-114">七个数字</span><span class="sxs-lookup"><span data-stu-id="a849b-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a849b-115">校验和</span><span class="sxs-lookup"><span data-stu-id="a849b-115">Checksum</span></span>

<span data-ttu-id="a849b-116">不适用</span><span class="sxs-lookup"><span data-stu-id="a849b-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a849b-117">定义</span><span class="sxs-lookup"><span data-stu-id="a849b-117">Definition</span></span>

<span data-ttu-id="a849b-118">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a849b-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a849b-119">正则表达式`Regex_austria_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a849b-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a849b-120">找到了中`Keywords_austria_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="a849b-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a849b-121">关键字</span><span class="sxs-lookup"><span data-stu-id="a849b-121">Keywords</span></span>

<span data-ttu-id="a849b-122">| |</span><span class="sxs-lookup"><span data-stu-id="a849b-122"></span></span>
|<span data-ttu-id="a849b-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a849b-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a849b-124">passport number</span><span class="sxs-lookup"><span data-stu-id="a849b-124">passport number</span></span>  <br/> <span data-ttu-id="a849b-125">奥地利护照号码</span><span class="sxs-lookup"><span data-stu-id="a849b-125">austrian passport number</span></span>  <br/> <span data-ttu-id="a849b-126">护照号</span><span class="sxs-lookup"><span data-stu-id="a849b-126">passport no</span></span>  <br/> <span data-ttu-id="a849b-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="a849b-127">reisepass</span></span>  <br/> <span data-ttu-id="a849b-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="a849b-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="a849b-129">比利时</span><span class="sxs-lookup"><span data-stu-id="a849b-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="a849b-130">Format</span><span class="sxs-lookup"><span data-stu-id="a849b-130">Format</span></span>

<span data-ttu-id="a849b-131">两个字母后跟六个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="a849b-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a849b-132">模式</span><span class="sxs-lookup"><span data-stu-id="a849b-132">Pattern</span></span>

<span data-ttu-id="a849b-133">两个字母, 后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="a849b-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a849b-134">校验和</span><span class="sxs-lookup"><span data-stu-id="a849b-134">Checksum</span></span>

<span data-ttu-id="a849b-135">不适用</span><span class="sxs-lookup"><span data-stu-id="a849b-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a849b-136">定义</span><span class="sxs-lookup"><span data-stu-id="a849b-136">Definition</span></span>

<span data-ttu-id="a849b-137">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a849b-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a849b-138">正则表达式`Regex_belgium_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a849b-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a849b-139">找到了中`Keywords_belgium_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="a849b-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a849b-140">关键字</span><span class="sxs-lookup"><span data-stu-id="a849b-140">Keywords</span></span>

<span data-ttu-id="a849b-141">| |</span><span class="sxs-lookup"><span data-stu-id="a849b-141"></span></span>
|<span data-ttu-id="a849b-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a849b-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a849b-143">passport number</span><span class="sxs-lookup"><span data-stu-id="a849b-143">passport number</span></span>  <br/> <span data-ttu-id="a849b-144">比利时护照号码</span><span class="sxs-lookup"><span data-stu-id="a849b-144">belgian passport number</span></span>  <br/> <span data-ttu-id="a849b-145">护照号</span><span class="sxs-lookup"><span data-stu-id="a849b-145">passport no</span></span>  <br/> <span data-ttu-id="a849b-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="a849b-146">paspoort</span></span>  <br/> <span data-ttu-id="a849b-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a849b-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="a849b-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="a849b-148">reisepass kein</span></span>  <br/> <span data-ttu-id="a849b-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="a849b-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="a849b-150">保加利亚语</span><span class="sxs-lookup"><span data-stu-id="a849b-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="a849b-151">Format</span><span class="sxs-lookup"><span data-stu-id="a849b-151">Format</span></span>

<span data-ttu-id="a849b-152">9个数字, 不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="a849b-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a849b-153">模式</span><span class="sxs-lookup"><span data-stu-id="a849b-153">Pattern</span></span>

 <span data-ttu-id="a849b-154">九个数字</span><span class="sxs-lookup"><span data-stu-id="a849b-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="a849b-155">校验和</span><span class="sxs-lookup"><span data-stu-id="a849b-155">Checksum</span></span>

<span data-ttu-id="a849b-156">否</span><span class="sxs-lookup"><span data-stu-id="a849b-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a849b-157">定义</span><span class="sxs-lookup"><span data-stu-id="a849b-157">Definition</span></span>

<span data-ttu-id="a849b-158">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a849b-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a849b-159">正则表达式`Regex_bulgaria_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a849b-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a849b-160">找到了中`Keywords_bulgaria_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="a849b-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a849b-161">关键字</span><span class="sxs-lookup"><span data-stu-id="a849b-161">Keywords</span></span>

<span data-ttu-id="a849b-162">| |</span><span class="sxs-lookup"><span data-stu-id="a849b-162"></span></span>
|<span data-ttu-id="a849b-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a849b-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a849b-164">passport number</span><span class="sxs-lookup"><span data-stu-id="a849b-164">passport number</span></span>  <br/> <span data-ttu-id="a849b-165">保加利亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="a849b-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="a849b-166">护照号</span><span class="sxs-lookup"><span data-stu-id="a849b-166">passport no</span></span>  <br/> <span data-ttu-id="a849b-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="a849b-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="a849b-168">克罗地亚</span><span class="sxs-lookup"><span data-stu-id="a849b-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="a849b-169">Format</span><span class="sxs-lookup"><span data-stu-id="a849b-169">Format</span></span>

<span data-ttu-id="a849b-170">9个数字, 不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="a849b-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a849b-171">模式</span><span class="sxs-lookup"><span data-stu-id="a849b-171">Pattern</span></span>

 <span data-ttu-id="a849b-172">九个数字</span><span class="sxs-lookup"><span data-stu-id="a849b-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="a849b-173">校验和</span><span class="sxs-lookup"><span data-stu-id="a849b-173">Checksum</span></span>

<span data-ttu-id="a849b-174">否</span><span class="sxs-lookup"><span data-stu-id="a849b-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a849b-175">定义</span><span class="sxs-lookup"><span data-stu-id="a849b-175">Definition</span></span>

<span data-ttu-id="a849b-176">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a849b-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a849b-177">正则表达式`Regex_croatia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a849b-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a849b-178">找到了中`Keywords_croatia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="a849b-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a849b-179">关键字</span><span class="sxs-lookup"><span data-stu-id="a849b-179">Keywords</span></span>

<span data-ttu-id="a849b-180">| |</span><span class="sxs-lookup"><span data-stu-id="a849b-180"></span></span>
|<span data-ttu-id="a849b-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a849b-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a849b-182">passport number</span><span class="sxs-lookup"><span data-stu-id="a849b-182">passport number</span></span>  <br/> <span data-ttu-id="a849b-183">克罗地亚护照号码</span><span class="sxs-lookup"><span data-stu-id="a849b-183">croatian passport number</span></span>  <br/> <span data-ttu-id="a849b-184">护照号</span><span class="sxs-lookup"><span data-stu-id="a849b-184">passport no</span></span>  <br/> <span data-ttu-id="a849b-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="a849b-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="a849b-186">塞浦路斯</span><span class="sxs-lookup"><span data-stu-id="a849b-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="a849b-187">Format</span><span class="sxs-lookup"><span data-stu-id="a849b-187">Format</span></span>

<span data-ttu-id="a849b-188">一个字母后跟6-8 个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="a849b-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a849b-189">模式</span><span class="sxs-lookup"><span data-stu-id="a849b-189">Pattern</span></span>

<span data-ttu-id="a849b-190">一个字母后跟6到8个数字</span><span class="sxs-lookup"><span data-stu-id="a849b-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a849b-191">校验和</span><span class="sxs-lookup"><span data-stu-id="a849b-191">Checksum</span></span>

<span data-ttu-id="a849b-192">否</span><span class="sxs-lookup"><span data-stu-id="a849b-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a849b-193">定义</span><span class="sxs-lookup"><span data-stu-id="a849b-193">Definition</span></span>

<span data-ttu-id="a849b-194">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a849b-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a849b-195">正则表达式`Regex_cyprus_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a849b-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a849b-196">找到了中`Keywords_cyprus_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="a849b-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a849b-197">关键字</span><span class="sxs-lookup"><span data-stu-id="a849b-197">Keywords</span></span>

<span data-ttu-id="a849b-198">| |</span><span class="sxs-lookup"><span data-stu-id="a849b-198"></span></span>
|<span data-ttu-id="a849b-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a849b-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a849b-200">passport number</span><span class="sxs-lookup"><span data-stu-id="a849b-200">passport number</span></span>  <br/> <span data-ttu-id="a849b-201">塞浦路斯护照号码</span><span class="sxs-lookup"><span data-stu-id="a849b-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="a849b-202">护照号</span><span class="sxs-lookup"><span data-stu-id="a849b-202">passport no</span></span>  <br/> <span data-ttu-id="a849b-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="a849b-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="a849b-204">捷克共和国</span><span class="sxs-lookup"><span data-stu-id="a849b-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="a849b-205">Format</span><span class="sxs-lookup"><span data-stu-id="a849b-205">Format</span></span>

<span data-ttu-id="a849b-206">8位数, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="a849b-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a849b-207">模式</span><span class="sxs-lookup"><span data-stu-id="a849b-207">Pattern</span></span>

<span data-ttu-id="a849b-208">8位数, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="a849b-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a849b-209">校验和</span><span class="sxs-lookup"><span data-stu-id="a849b-209">Checksum</span></span>

<span data-ttu-id="a849b-210">否</span><span class="sxs-lookup"><span data-stu-id="a849b-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a849b-211">定义</span><span class="sxs-lookup"><span data-stu-id="a849b-211">Definition</span></span>

<span data-ttu-id="a849b-212">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a849b-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a849b-213">正则表达式`Regex_czech_republic_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a849b-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a849b-214">找到了中`Keywords_czech_republic_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="a849b-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a849b-215">关键字</span><span class="sxs-lookup"><span data-stu-id="a849b-215">Keywords</span></span>

<span data-ttu-id="a849b-216">| |</span><span class="sxs-lookup"><span data-stu-id="a849b-216"></span></span>
|<span data-ttu-id="a849b-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a849b-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a849b-218">passport number</span><span class="sxs-lookup"><span data-stu-id="a849b-218">passport number</span></span>  <br/> <span data-ttu-id="a849b-219">捷克语护照号码</span><span class="sxs-lookup"><span data-stu-id="a849b-219">czech passport number</span></span>  <br/> <span data-ttu-id="a849b-220">护照号</span><span class="sxs-lookup"><span data-stu-id="a849b-220">passport no</span></span>  <br/> <span data-ttu-id="a849b-221">cestovní pas</span><span class="sxs-lookup"><span data-stu-id="a849b-221">cestovní pas</span></span>  <br/> <span data-ttu-id="a849b-222">pas</span><span class="sxs-lookup"><span data-stu-id="a849b-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="a849b-223">丹麦</span><span class="sxs-lookup"><span data-stu-id="a849b-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="a849b-224">Format</span><span class="sxs-lookup"><span data-stu-id="a849b-224">Format</span></span>

<span data-ttu-id="a849b-225">9个数字, 不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="a849b-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a849b-226">模式</span><span class="sxs-lookup"><span data-stu-id="a849b-226">Pattern</span></span>

 <span data-ttu-id="a849b-227">九个数字</span><span class="sxs-lookup"><span data-stu-id="a849b-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="a849b-228">校验和</span><span class="sxs-lookup"><span data-stu-id="a849b-228">Checksum</span></span>

<span data-ttu-id="a849b-229">否</span><span class="sxs-lookup"><span data-stu-id="a849b-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a849b-230">定义</span><span class="sxs-lookup"><span data-stu-id="a849b-230">Definition</span></span>

<span data-ttu-id="a849b-231">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a849b-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a849b-232">正则表达式`Regex_denmark_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a849b-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a849b-233">找到了中`Keywords_denmark_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="a849b-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a849b-234">关键字</span><span class="sxs-lookup"><span data-stu-id="a849b-234">Keywords</span></span>

<span data-ttu-id="a849b-235">| |</span><span class="sxs-lookup"><span data-stu-id="a849b-235"></span></span>
|<span data-ttu-id="a849b-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a849b-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a849b-237">passport number</span><span class="sxs-lookup"><span data-stu-id="a849b-237">passport number</span></span>  <br/> <span data-ttu-id="a849b-238">丹麦护照号码</span><span class="sxs-lookup"><span data-stu-id="a849b-238">danish passport number</span></span>  <br/> <span data-ttu-id="a849b-239">护照号</span><span class="sxs-lookup"><span data-stu-id="a849b-239">passport no</span></span>  <br/> <span data-ttu-id="a849b-240">pas</span><span class="sxs-lookup"><span data-stu-id="a849b-240">pas</span></span>  <br/> <span data-ttu-id="a849b-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="a849b-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="a849b-242">爱沙尼亚</span><span class="sxs-lookup"><span data-stu-id="a849b-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="a849b-243">Format</span><span class="sxs-lookup"><span data-stu-id="a849b-243">Format</span></span>

<span data-ttu-id="a849b-244">一个字母后跟七个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="a849b-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a849b-245">模式</span><span class="sxs-lookup"><span data-stu-id="a849b-245">Pattern</span></span>

<span data-ttu-id="a849b-246">一个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="a849b-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a849b-247">校验和</span><span class="sxs-lookup"><span data-stu-id="a849b-247">Checksum</span></span>

<span data-ttu-id="a849b-248">否</span><span class="sxs-lookup"><span data-stu-id="a849b-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a849b-249">定义</span><span class="sxs-lookup"><span data-stu-id="a849b-249">Definition</span></span>

<span data-ttu-id="a849b-250">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a849b-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a849b-251">正则表达式`Regex_estonia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a849b-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a849b-252">找到了中`Keywords_estonia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="a849b-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a849b-253">关键字</span><span class="sxs-lookup"><span data-stu-id="a849b-253">Keywords</span></span>

<span data-ttu-id="a849b-254">| |</span><span class="sxs-lookup"><span data-stu-id="a849b-254"></span></span>
|<span data-ttu-id="a849b-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a849b-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a849b-256">passport number</span><span class="sxs-lookup"><span data-stu-id="a849b-256">passport number</span></span>  <br/> <span data-ttu-id="a849b-257">爱沙尼亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="a849b-257">estonian passport number</span></span>  <br/> <span data-ttu-id="a849b-258">护照号</span><span class="sxs-lookup"><span data-stu-id="a849b-258">passport no</span></span>  <br/> <span data-ttu-id="a849b-259">eesti kodaniku pass</span><span class="sxs-lookup"><span data-stu-id="a849b-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="a849b-260">芬兰</span><span class="sxs-lookup"><span data-stu-id="a849b-260">Finland</span></span>

<span data-ttu-id="a849b-261">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "芬兰护照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="a849b-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="a849b-262">法国</span><span class="sxs-lookup"><span data-stu-id="a849b-262">France</span></span>

<span data-ttu-id="a849b-263">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "法国护照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="a849b-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="a849b-264">德国</span><span class="sxs-lookup"><span data-stu-id="a849b-264">Germany</span></span>

<span data-ttu-id="a849b-265">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "德国护照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="a849b-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="a849b-266">希腊</span><span class="sxs-lookup"><span data-stu-id="a849b-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="a849b-267">Format</span><span class="sxs-lookup"><span data-stu-id="a849b-267">Format</span></span>

<span data-ttu-id="a849b-268">两个字母后跟七个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="a849b-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a849b-269">模式</span><span class="sxs-lookup"><span data-stu-id="a849b-269">Pattern</span></span>

<span data-ttu-id="a849b-270">两个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="a849b-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a849b-271">校验和</span><span class="sxs-lookup"><span data-stu-id="a849b-271">Checksum</span></span>

<span data-ttu-id="a849b-272">否</span><span class="sxs-lookup"><span data-stu-id="a849b-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a849b-273">定义</span><span class="sxs-lookup"><span data-stu-id="a849b-273">Definition</span></span>

<span data-ttu-id="a849b-274">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a849b-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a849b-275">正则表达式`Regex_greece_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a849b-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a849b-276">找到了中`Keywords_greece_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="a849b-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a849b-277">关键字</span><span class="sxs-lookup"><span data-stu-id="a849b-277">Keywords</span></span>

<span data-ttu-id="a849b-278">| |</span><span class="sxs-lookup"><span data-stu-id="a849b-278"></span></span>
|<span data-ttu-id="a849b-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a849b-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a849b-280">passport number</span><span class="sxs-lookup"><span data-stu-id="a849b-280">passport number</span></span>  <br/> <span data-ttu-id="a849b-281">希腊护照号码</span><span class="sxs-lookup"><span data-stu-id="a849b-281">greek passport number</span></span>  <br/> <span data-ttu-id="a849b-282">护照号</span><span class="sxs-lookup"><span data-stu-id="a849b-282">passport no</span></span>  <br/> <span data-ttu-id="a849b-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="a849b-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="a849b-284">匈牙利</span><span class="sxs-lookup"><span data-stu-id="a849b-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="a849b-285">Format</span><span class="sxs-lookup"><span data-stu-id="a849b-285">Format</span></span>

<span data-ttu-id="a849b-286">两个字母后跟6个或7个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="a849b-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a849b-287">模式</span><span class="sxs-lookup"><span data-stu-id="a849b-287">Pattern</span></span>

<span data-ttu-id="a849b-288">两个字母后跟六个或七个数字</span><span class="sxs-lookup"><span data-stu-id="a849b-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a849b-289">校验和</span><span class="sxs-lookup"><span data-stu-id="a849b-289">Checksum</span></span>

<span data-ttu-id="a849b-290">否</span><span class="sxs-lookup"><span data-stu-id="a849b-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a849b-291">定义</span><span class="sxs-lookup"><span data-stu-id="a849b-291">Definition</span></span>

<span data-ttu-id="a849b-292">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a849b-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a849b-293">正则表达式`Regex_hungary_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a849b-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a849b-294">找到了中`Keywords_hungary_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="a849b-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a849b-295">关键字</span><span class="sxs-lookup"><span data-stu-id="a849b-295">Keywords</span></span>

<span data-ttu-id="a849b-296">| |</span><span class="sxs-lookup"><span data-stu-id="a849b-296"></span></span>
|<span data-ttu-id="a849b-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a849b-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a849b-298">passport number</span><span class="sxs-lookup"><span data-stu-id="a849b-298">passport number</span></span>  <br/> <span data-ttu-id="a849b-299">匈牙利语护照号码</span><span class="sxs-lookup"><span data-stu-id="a849b-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="a849b-300">护照号</span><span class="sxs-lookup"><span data-stu-id="a849b-300">passport no</span></span>  <br/> <span data-ttu-id="a849b-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="a849b-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="a849b-302">爱尔兰</span><span class="sxs-lookup"><span data-stu-id="a849b-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="a849b-303">Format</span><span class="sxs-lookup"><span data-stu-id="a849b-303">Format</span></span>

<span data-ttu-id="a849b-304">两个字母或数字后跟七个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="a849b-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a849b-305">模式</span><span class="sxs-lookup"><span data-stu-id="a849b-305">Pattern</span></span>

<span data-ttu-id="a849b-306">两个字母或数字, 后跟七个数字:</span><span class="sxs-lookup"><span data-stu-id="a849b-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="a849b-307">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="a849b-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="a849b-308">七个数字</span><span class="sxs-lookup"><span data-stu-id="a849b-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a849b-309">校验和</span><span class="sxs-lookup"><span data-stu-id="a849b-309">Checksum</span></span>

<span data-ttu-id="a849b-310">否</span><span class="sxs-lookup"><span data-stu-id="a849b-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a849b-311">定义</span><span class="sxs-lookup"><span data-stu-id="a849b-311">Definition</span></span>

<span data-ttu-id="a849b-312">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a849b-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a849b-313">正则表达式`Regex_ireland_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a849b-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a849b-314">找到了中`Keywords_ireland_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="a849b-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a849b-315">关键字</span><span class="sxs-lookup"><span data-stu-id="a849b-315">Keywords</span></span>

<span data-ttu-id="a849b-316">| |</span><span class="sxs-lookup"><span data-stu-id="a849b-316"></span></span>
|<span data-ttu-id="a849b-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a849b-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a849b-318">passport number</span><span class="sxs-lookup"><span data-stu-id="a849b-318">passport number</span></span>  <br/> <span data-ttu-id="a849b-319">爱尔兰护照号码</span><span class="sxs-lookup"><span data-stu-id="a849b-319">irish passport number</span></span>  <br/> <span data-ttu-id="a849b-320">护照号</span><span class="sxs-lookup"><span data-stu-id="a849b-320">passport no</span></span>  <br/> <span data-ttu-id="a849b-321">pas</span><span class="sxs-lookup"><span data-stu-id="a849b-321">pas</span></span>  <br/> <span data-ttu-id="a849b-322">登记卡</span><span class="sxs-lookup"><span data-stu-id="a849b-322">passport</span></span>  <br/> <span data-ttu-id="a849b-323">passeport</span><span class="sxs-lookup"><span data-stu-id="a849b-323">passeport</span></span>  <br/> <span data-ttu-id="a849b-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="a849b-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="a849b-325">意大利</span><span class="sxs-lookup"><span data-stu-id="a849b-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="a849b-326">Format</span><span class="sxs-lookup"><span data-stu-id="a849b-326">Format</span></span>

<span data-ttu-id="a849b-327">两个字母或数字后跟七个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="a849b-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a849b-328">模式</span><span class="sxs-lookup"><span data-stu-id="a849b-328">Pattern</span></span>

<span data-ttu-id="a849b-329">两个字母或数字, 后跟七个数字:</span><span class="sxs-lookup"><span data-stu-id="a849b-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="a849b-330">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="a849b-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="a849b-331">七个数字</span><span class="sxs-lookup"><span data-stu-id="a849b-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a849b-332">校验和</span><span class="sxs-lookup"><span data-stu-id="a849b-332">Checksum</span></span>

<span data-ttu-id="a849b-333">不适用</span><span class="sxs-lookup"><span data-stu-id="a849b-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a849b-334">定义</span><span class="sxs-lookup"><span data-stu-id="a849b-334">Definition</span></span>

<span data-ttu-id="a849b-335">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a849b-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a849b-336">正则表达式`Regex_italy_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a849b-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a849b-337">找到了中`Keywords_italy_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="a849b-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a849b-338">关键字</span><span class="sxs-lookup"><span data-stu-id="a849b-338">Keywords</span></span>

<span data-ttu-id="a849b-339">| |</span><span class="sxs-lookup"><span data-stu-id="a849b-339"></span></span>
|<span data-ttu-id="a849b-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a849b-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a849b-341">意大利护照号码</span><span class="sxs-lookup"><span data-stu-id="a849b-341">italian passport number</span></span>  <br/> <span data-ttu-id="a849b-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="a849b-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="a849b-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="a849b-343">passaporto</span></span>  <br/> <span data-ttu-id="a849b-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="a849b-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="a849b-345">passport number</span><span class="sxs-lookup"><span data-stu-id="a849b-345">passport number</span></span>  <br/> <span data-ttu-id="a849b-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="a849b-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="a849b-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="a849b-347">passaporto numero</span></span>  <br/> <span data-ttu-id="a849b-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="a849b-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="a849b-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="a849b-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="a849b-350">拉脱维亚</span><span class="sxs-lookup"><span data-stu-id="a849b-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="a849b-351">Format</span><span class="sxs-lookup"><span data-stu-id="a849b-351">Format</span></span>

<span data-ttu-id="a849b-352">两个字母或数字后跟七个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="a849b-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a849b-353">模式</span><span class="sxs-lookup"><span data-stu-id="a849b-353">Pattern</span></span>

<span data-ttu-id="a849b-354">两个字母或数字, 后跟七个数字:</span><span class="sxs-lookup"><span data-stu-id="a849b-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="a849b-355">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="a849b-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="a849b-356">七个数字</span><span class="sxs-lookup"><span data-stu-id="a849b-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a849b-357">校验和</span><span class="sxs-lookup"><span data-stu-id="a849b-357">Checksum</span></span>

<span data-ttu-id="a849b-358">否</span><span class="sxs-lookup"><span data-stu-id="a849b-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a849b-359">定义</span><span class="sxs-lookup"><span data-stu-id="a849b-359">Definition</span></span>

<span data-ttu-id="a849b-360">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a849b-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a849b-361">正则表达式`Regex_latvia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a849b-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a849b-362">找到了中`Keywords_latvia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="a849b-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a849b-363">关键字</span><span class="sxs-lookup"><span data-stu-id="a849b-363">Keywords</span></span>

<span data-ttu-id="a849b-364">| |</span><span class="sxs-lookup"><span data-stu-id="a849b-364"></span></span>
|<span data-ttu-id="a849b-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a849b-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a849b-366">passport number</span><span class="sxs-lookup"><span data-stu-id="a849b-366">passport number</span></span>  <br/> <span data-ttu-id="a849b-367">拉脱维亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="a849b-367">latvian passport number</span></span>  <br/> <span data-ttu-id="a849b-368">护照号</span><span class="sxs-lookup"><span data-stu-id="a849b-368">passport no</span></span>  <br/> <span data-ttu-id="a849b-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="a849b-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="a849b-370">立陶宛</span><span class="sxs-lookup"><span data-stu-id="a849b-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="a849b-371">Format</span><span class="sxs-lookup"><span data-stu-id="a849b-371">Format</span></span>

<span data-ttu-id="a849b-372">八个数字或字母不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="a849b-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a849b-373">模式</span><span class="sxs-lookup"><span data-stu-id="a849b-373">Pattern</span></span>

<span data-ttu-id="a849b-374">八个数字或字母 (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="a849b-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a849b-375">校验和</span><span class="sxs-lookup"><span data-stu-id="a849b-375">Checksum</span></span>

<span data-ttu-id="a849b-376">不适用</span><span class="sxs-lookup"><span data-stu-id="a849b-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a849b-377">定义</span><span class="sxs-lookup"><span data-stu-id="a849b-377">Definition</span></span>

<span data-ttu-id="a849b-378">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a849b-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a849b-379">正则表达式`Regex_lithuania_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a849b-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a849b-380">找到了中`Keywords_lithuania_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="a849b-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a849b-381">关键字</span><span class="sxs-lookup"><span data-stu-id="a849b-381">Keywords</span></span>

<span data-ttu-id="a849b-382">| |</span><span class="sxs-lookup"><span data-stu-id="a849b-382"></span></span>
|<span data-ttu-id="a849b-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a849b-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a849b-384">passport number</span><span class="sxs-lookup"><span data-stu-id="a849b-384">passport number</span></span>  <br/> <span data-ttu-id="a849b-385">lithunian 护照号码</span><span class="sxs-lookup"><span data-stu-id="a849b-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="a849b-386">护照号</span><span class="sxs-lookup"><span data-stu-id="a849b-386">passport no</span></span>  <br/> <span data-ttu-id="a849b-387">paso numeris</span><span class="sxs-lookup"><span data-stu-id="a849b-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="a849b-388">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="a849b-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="a849b-389">Format</span><span class="sxs-lookup"><span data-stu-id="a849b-389">Format</span></span>

<span data-ttu-id="a849b-390">八个数字或字母不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="a849b-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a849b-391">模式</span><span class="sxs-lookup"><span data-stu-id="a849b-391">Pattern</span></span>

<span data-ttu-id="a849b-392">八个数字或字母 (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="a849b-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a849b-393">校验和</span><span class="sxs-lookup"><span data-stu-id="a849b-393">Checksum</span></span>

<span data-ttu-id="a849b-394">否</span><span class="sxs-lookup"><span data-stu-id="a849b-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a849b-395">定义</span><span class="sxs-lookup"><span data-stu-id="a849b-395">Definition</span></span>

<span data-ttu-id="a849b-396">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a849b-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a849b-397">正则表达式`Regex_nation_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a849b-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a849b-398">找到了中`Keywords_nation_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="a849b-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a849b-399">关键字</span><span class="sxs-lookup"><span data-stu-id="a849b-399">Keywords</span></span>

<span data-ttu-id="a849b-400">| |</span><span class="sxs-lookup"><span data-stu-id="a849b-400"></span></span>
|<span data-ttu-id="a849b-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a849b-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a849b-402">passport number</span><span class="sxs-lookup"><span data-stu-id="a849b-402">passport number</span></span>  <br/> <span data-ttu-id="a849b-403">拉脱维亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="a849b-403">latvian passport number</span></span>  <br/> <span data-ttu-id="a849b-404">护照号</span><span class="sxs-lookup"><span data-stu-id="a849b-404">passport no</span></span>  <br/> <span data-ttu-id="a849b-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="a849b-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="a849b-406">马耳他</span><span class="sxs-lookup"><span data-stu-id="a849b-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="a849b-407">Format</span><span class="sxs-lookup"><span data-stu-id="a849b-407">Format</span></span>

<span data-ttu-id="a849b-408">七位数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="a849b-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a849b-409">模式</span><span class="sxs-lookup"><span data-stu-id="a849b-409">Pattern</span></span>

 <span data-ttu-id="a849b-410">七个数字</span><span class="sxs-lookup"><span data-stu-id="a849b-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="a849b-411">校验和</span><span class="sxs-lookup"><span data-stu-id="a849b-411">Checksum</span></span>

<span data-ttu-id="a849b-412">否</span><span class="sxs-lookup"><span data-stu-id="a849b-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a849b-413">定义</span><span class="sxs-lookup"><span data-stu-id="a849b-413">Definition</span></span>

<span data-ttu-id="a849b-414">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a849b-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a849b-415">正则表达式`Regex_malta_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a849b-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a849b-416">找到了中`Keywords_malta_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="a849b-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a849b-417">关键字</span><span class="sxs-lookup"><span data-stu-id="a849b-417">Keywords</span></span>

<span data-ttu-id="a849b-418">| |</span><span class="sxs-lookup"><span data-stu-id="a849b-418"></span></span>
|<span data-ttu-id="a849b-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a849b-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a849b-420">passport number</span><span class="sxs-lookup"><span data-stu-id="a849b-420">passport number</span></span>  <br/> <span data-ttu-id="a849b-421">马耳他护照号码</span><span class="sxs-lookup"><span data-stu-id="a849b-421">maltese passport number</span></span>  <br/> <span data-ttu-id="a849b-422">护照号</span><span class="sxs-lookup"><span data-stu-id="a849b-422">passport no</span></span>  <br/> <span data-ttu-id="a849b-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="a849b-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="a849b-424">荷兰</span><span class="sxs-lookup"><span data-stu-id="a849b-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="a849b-425">Format</span><span class="sxs-lookup"><span data-stu-id="a849b-425">Format</span></span>

<span data-ttu-id="a849b-426">九个字母或数字, 不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="a849b-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a849b-427">模式</span><span class="sxs-lookup"><span data-stu-id="a849b-427">Pattern</span></span>

<span data-ttu-id="a849b-428">九个字母或数字</span><span class="sxs-lookup"><span data-stu-id="a849b-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a849b-429">校验和</span><span class="sxs-lookup"><span data-stu-id="a849b-429">Checksum</span></span>

<span data-ttu-id="a849b-430">不适用</span><span class="sxs-lookup"><span data-stu-id="a849b-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a849b-431">定义</span><span class="sxs-lookup"><span data-stu-id="a849b-431">Definition</span></span>

<span data-ttu-id="a849b-432">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a849b-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a849b-433">正则表达式`Regex_netherlands_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a849b-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a849b-434">找到了中`Keywords_netherlands_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="a849b-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a849b-435">关键字</span><span class="sxs-lookup"><span data-stu-id="a849b-435">Keywords</span></span>

<span data-ttu-id="a849b-436">| |</span><span class="sxs-lookup"><span data-stu-id="a849b-436"></span></span>
|<span data-ttu-id="a849b-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a849b-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a849b-438">荷兰护照号码</span><span class="sxs-lookup"><span data-stu-id="a849b-438">dutch passport number</span></span>  <br/> <span data-ttu-id="a849b-439">passport number</span><span class="sxs-lookup"><span data-stu-id="a849b-439">passport number</span></span>  <br/> <span data-ttu-id="a849b-440">荷兰护照号码</span><span class="sxs-lookup"><span data-stu-id="a849b-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="a849b-441">nederlanden paspoort nummer</span><span class="sxs-lookup"><span data-stu-id="a849b-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="a849b-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="a849b-442">paspoort</span></span>  <br/> <span data-ttu-id="a849b-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a849b-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="a849b-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a849b-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="a849b-445">波兰</span><span class="sxs-lookup"><span data-stu-id="a849b-445">Poland</span></span>

<span data-ttu-id="a849b-446">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "波兰 Passport 号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="a849b-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="a849b-447">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="a849b-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="a849b-448">Format</span><span class="sxs-lookup"><span data-stu-id="a849b-448">Format</span></span>

<span data-ttu-id="a849b-449">一个字母后跟六个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="a849b-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a849b-450">模式</span><span class="sxs-lookup"><span data-stu-id="a849b-450">Pattern</span></span>

<span data-ttu-id="a849b-451">一个字母后跟六个数字:</span><span class="sxs-lookup"><span data-stu-id="a849b-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="a849b-452">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="a849b-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="a849b-453">六个数字</span><span class="sxs-lookup"><span data-stu-id="a849b-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a849b-454">校验和</span><span class="sxs-lookup"><span data-stu-id="a849b-454">Checksum</span></span>

<span data-ttu-id="a849b-455">否</span><span class="sxs-lookup"><span data-stu-id="a849b-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a849b-456">定义</span><span class="sxs-lookup"><span data-stu-id="a849b-456">Definition</span></span>

<span data-ttu-id="a849b-457">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a849b-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a849b-458">正则表达式`Regex_portugal_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a849b-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a849b-459">找到了中`Keywords_portugal_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="a849b-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a849b-460">关键字</span><span class="sxs-lookup"><span data-stu-id="a849b-460">Keywords</span></span>

<span data-ttu-id="a849b-461">| |</span><span class="sxs-lookup"><span data-stu-id="a849b-461"></span></span>
|<span data-ttu-id="a849b-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a849b-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a849b-463">passport number</span><span class="sxs-lookup"><span data-stu-id="a849b-463">passport number</span></span>  <br/> <span data-ttu-id="a849b-464">葡萄牙语护照号码</span><span class="sxs-lookup"><span data-stu-id="a849b-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="a849b-465">护照号</span><span class="sxs-lookup"><span data-stu-id="a849b-465">passport no</span></span>  <br/> <span data-ttu-id="a849b-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="a849b-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="a849b-467">罗马尼亚</span><span class="sxs-lookup"><span data-stu-id="a849b-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="a849b-468">Format</span><span class="sxs-lookup"><span data-stu-id="a849b-468">Format</span></span>

<span data-ttu-id="a849b-469">八个或9个数字, 不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="a849b-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a849b-470">模式</span><span class="sxs-lookup"><span data-stu-id="a849b-470">Pattern</span></span>

<span data-ttu-id="a849b-471">8或9个数字</span><span class="sxs-lookup"><span data-stu-id="a849b-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a849b-472">校验和</span><span class="sxs-lookup"><span data-stu-id="a849b-472">Checksum</span></span>

<span data-ttu-id="a849b-473">否</span><span class="sxs-lookup"><span data-stu-id="a849b-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a849b-474">定义</span><span class="sxs-lookup"><span data-stu-id="a849b-474">Definition</span></span>

<span data-ttu-id="a849b-475">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a849b-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a849b-476">正则表达式`Regex_romania_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a849b-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a849b-477">找到了中`Keywords_romania_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="a849b-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a849b-478">关键字</span><span class="sxs-lookup"><span data-stu-id="a849b-478">Keywords</span></span>

<span data-ttu-id="a849b-479">| |</span><span class="sxs-lookup"><span data-stu-id="a849b-479"></span></span>
|<span data-ttu-id="a849b-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a849b-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a849b-481">passport number</span><span class="sxs-lookup"><span data-stu-id="a849b-481">passport number</span></span>  <br/> <span data-ttu-id="a849b-482">罗马尼亚护照号码</span><span class="sxs-lookup"><span data-stu-id="a849b-482">romanian passport number</span></span>  <br/> <span data-ttu-id="a849b-483">护照号</span><span class="sxs-lookup"><span data-stu-id="a849b-483">passport no</span></span>  <br/> <span data-ttu-id="a849b-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="a849b-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="a849b-485">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="a849b-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="a849b-486">Format</span><span class="sxs-lookup"><span data-stu-id="a849b-486">Format</span></span>

<span data-ttu-id="a849b-487">一个数字或字母后跟七个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="a849b-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a849b-488">模式</span><span class="sxs-lookup"><span data-stu-id="a849b-488">Pattern</span></span>

<span data-ttu-id="a849b-489">一个数字或字母 (不区分大小写) 后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="a849b-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a849b-490">校验和</span><span class="sxs-lookup"><span data-stu-id="a849b-490">Checksum</span></span>

<span data-ttu-id="a849b-491">否</span><span class="sxs-lookup"><span data-stu-id="a849b-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a849b-492">定义</span><span class="sxs-lookup"><span data-stu-id="a849b-492">Definition</span></span>

<span data-ttu-id="a849b-493">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a849b-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a849b-494">正则表达式`Regex_slovakia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a849b-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a849b-495">找到了中`Keywords_slovakia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="a849b-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a849b-496">关键字</span><span class="sxs-lookup"><span data-stu-id="a849b-496">Keywords</span></span>

<span data-ttu-id="a849b-497">| |</span><span class="sxs-lookup"><span data-stu-id="a849b-497"></span></span>
|<span data-ttu-id="a849b-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a849b-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a849b-499">passport number</span><span class="sxs-lookup"><span data-stu-id="a849b-499">passport number</span></span>  <br/> <span data-ttu-id="a849b-500">斯洛伐克护照号码</span><span class="sxs-lookup"><span data-stu-id="a849b-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="a849b-501">护照号</span><span class="sxs-lookup"><span data-stu-id="a849b-501">passport no</span></span>  <br/> <span data-ttu-id="a849b-502">číslo pasu</span><span class="sxs-lookup"><span data-stu-id="a849b-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="a849b-503">斯洛文尼亚</span><span class="sxs-lookup"><span data-stu-id="a849b-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="a849b-504">Format</span><span class="sxs-lookup"><span data-stu-id="a849b-504">Format</span></span>

<span data-ttu-id="a849b-505">两个字母后跟七个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="a849b-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a849b-506">模式</span><span class="sxs-lookup"><span data-stu-id="a849b-506">Pattern</span></span>

<span data-ttu-id="a849b-507">两个字母后跟七个数字:</span><span class="sxs-lookup"><span data-stu-id="a849b-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="a849b-508">字母 "P"</span><span class="sxs-lookup"><span data-stu-id="a849b-508">The letter "P"</span></span>
    
- <span data-ttu-id="a849b-509">一个大写字母</span><span class="sxs-lookup"><span data-stu-id="a849b-509">One uppercase letter</span></span>
    
- <span data-ttu-id="a849b-510">七个数字</span><span class="sxs-lookup"><span data-stu-id="a849b-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a849b-511">校验和</span><span class="sxs-lookup"><span data-stu-id="a849b-511">Checksum</span></span>

<span data-ttu-id="a849b-512">否</span><span class="sxs-lookup"><span data-stu-id="a849b-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a849b-513">定义</span><span class="sxs-lookup"><span data-stu-id="a849b-513">Definition</span></span>

<span data-ttu-id="a849b-514">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a849b-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a849b-515">正则表达式`Regex_slovenia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a849b-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a849b-516">找到了中`Keywords_slovenia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="a849b-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a849b-517">关键字</span><span class="sxs-lookup"><span data-stu-id="a849b-517">Keywords</span></span>

<span data-ttu-id="a849b-518">| |</span><span class="sxs-lookup"><span data-stu-id="a849b-518"></span></span>
|<span data-ttu-id="a849b-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a849b-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a849b-520">passport number</span><span class="sxs-lookup"><span data-stu-id="a849b-520">passport number</span></span>  <br/> <span data-ttu-id="a849b-521">斯洛文尼亚护照号码</span><span class="sxs-lookup"><span data-stu-id="a849b-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="a849b-522">护照号</span><span class="sxs-lookup"><span data-stu-id="a849b-522">passport no</span></span>  <br/> <span data-ttu-id="a849b-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="a849b-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="a849b-524">西班牙</span><span class="sxs-lookup"><span data-stu-id="a849b-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="a849b-525">Format</span><span class="sxs-lookup"><span data-stu-id="a849b-525">Format</span></span>

<span data-ttu-id="a849b-526">八个或九个字符的字母和数字的组合, 不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="a849b-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a849b-527">模式</span><span class="sxs-lookup"><span data-stu-id="a849b-527">Pattern</span></span>

<span data-ttu-id="a849b-528">字母和数字的八个或九个字符的组合:</span><span class="sxs-lookup"><span data-stu-id="a849b-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="a849b-529">两位数字或字母</span><span class="sxs-lookup"><span data-stu-id="a849b-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="a849b-530">一个数字或字母 (可选)</span><span class="sxs-lookup"><span data-stu-id="a849b-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="a849b-531">六个数字</span><span class="sxs-lookup"><span data-stu-id="a849b-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a849b-532">校验和</span><span class="sxs-lookup"><span data-stu-id="a849b-532">Checksum</span></span>

<span data-ttu-id="a849b-533">不适用</span><span class="sxs-lookup"><span data-stu-id="a849b-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a849b-534">定义</span><span class="sxs-lookup"><span data-stu-id="a849b-534">Definition</span></span>

<span data-ttu-id="a849b-535">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a849b-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a849b-536">正则表达式`Regex_spain_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a849b-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a849b-537">找到了中`Keywords_spain_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="a849b-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a849b-538">关键字</span><span class="sxs-lookup"><span data-stu-id="a849b-538">Keywords</span></span>

<span data-ttu-id="a849b-539">| |</span><span class="sxs-lookup"><span data-stu-id="a849b-539"></span></span>
|<span data-ttu-id="a849b-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a849b-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a849b-541">登记卡</span><span class="sxs-lookup"><span data-stu-id="a849b-541">passport</span></span>  <br/> <span data-ttu-id="a849b-542">西班牙护照</span><span class="sxs-lookup"><span data-stu-id="a849b-542">spain passport</span></span>  <br/> <span data-ttu-id="a849b-543">护照书籍</span><span class="sxs-lookup"><span data-stu-id="a849b-543">passport book</span></span>  <br/> <span data-ttu-id="a849b-544">passport number</span><span class="sxs-lookup"><span data-stu-id="a849b-544">passport number</span></span>  <br/> <span data-ttu-id="a849b-545">护照号</span><span class="sxs-lookup"><span data-stu-id="a849b-545">passport no</span></span>  <br/> <span data-ttu-id="a849b-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="a849b-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="a849b-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="a849b-547">número pasaporte</span></span>  <br/> <span data-ttu-id="a849b-548">西班牙 pasaporte</span><span class="sxs-lookup"><span data-stu-id="a849b-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="a849b-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="a849b-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="a849b-550">瑞典</span><span class="sxs-lookup"><span data-stu-id="a849b-550">Sweden</span></span>

<span data-ttu-id="a849b-551">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "瑞典护照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="a849b-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="a849b-552">英国</span><span class="sxs-lookup"><span data-stu-id="a849b-552">UK</span></span>

<span data-ttu-id="a849b-553">有关详细信息, 请参阅 "美国/英国" 一节。</span><span class="sxs-lookup"><span data-stu-id="a849b-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="a849b-554">"Passport 号码", 在[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中。</span><span class="sxs-lookup"><span data-stu-id="a849b-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a849b-555">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a849b-555">See also</span></span>

[<span data-ttu-id="a849b-556">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="a849b-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

