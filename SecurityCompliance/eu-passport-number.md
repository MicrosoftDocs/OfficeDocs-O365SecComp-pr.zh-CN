---
title: EU 护照号码
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 8c00df57-9fb3-459c-ba87-40480c87bd55
description: 本主题介绍当数据丢失防护 (DLP) 策略检测到欧盟护照号敏感信息类型时, 应查找什么内容。此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。
ms.openlocfilehash: c46f683bd1baf651bcf13c1766dfff3cb953b341
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218262"
---
# <a name="eu-passport-number"></a><span data-ttu-id="64f83-104">EU 护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-104">EU Passport Number</span></span>

<span data-ttu-id="64f83-p102">本主题介绍当数据丢失防护 (DLP) 策略检测到欧盟护照号敏感信息类型时, 应查找什么内容。此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。</span><span class="sxs-lookup"><span data-stu-id="64f83-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="64f83-107">奥地利</span><span class="sxs-lookup"><span data-stu-id="64f83-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="64f83-108">格式</span><span class="sxs-lookup"><span data-stu-id="64f83-108">Format</span></span>

<span data-ttu-id="64f83-109">一个字母后跟一个可选空格和七个数字</span><span class="sxs-lookup"><span data-stu-id="64f83-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64f83-110">模式</span><span class="sxs-lookup"><span data-stu-id="64f83-110">Pattern</span></span>

<span data-ttu-id="64f83-111">一个字母、七个数字和一个空格的组合:</span><span class="sxs-lookup"><span data-stu-id="64f83-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="64f83-112">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="64f83-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="64f83-113">一个空格 (可选)</span><span class="sxs-lookup"><span data-stu-id="64f83-113">One space (optional)</span></span>
    
- <span data-ttu-id="64f83-114">七个数字</span><span class="sxs-lookup"><span data-stu-id="64f83-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="64f83-115">校验和</span><span class="sxs-lookup"><span data-stu-id="64f83-115">Checksum</span></span>

<span data-ttu-id="64f83-116">不适用</span><span class="sxs-lookup"><span data-stu-id="64f83-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="64f83-117">定义</span><span class="sxs-lookup"><span data-stu-id="64f83-117">Definition</span></span>

<span data-ttu-id="64f83-118">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="64f83-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64f83-119">正则表达式`Regex_austria_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="64f83-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64f83-120">找到了中`Keywords_austria_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="64f83-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64f83-121">关键字</span><span class="sxs-lookup"><span data-stu-id="64f83-121">Keywords</span></span>

<span data-ttu-id="64f83-122">| |</span><span class="sxs-lookup"><span data-stu-id="64f83-122"></span></span>
|<span data-ttu-id="64f83-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64f83-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64f83-124">护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-124">passport number</span></span>  <br/> <span data-ttu-id="64f83-125">奥地利护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-125">austrian passport number</span></span>  <br/> <span data-ttu-id="64f83-126">护照号</span><span class="sxs-lookup"><span data-stu-id="64f83-126">passport no</span></span>  <br/> <span data-ttu-id="64f83-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="64f83-127">reisepass</span></span>  <br/> <span data-ttu-id="64f83-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="64f83-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="64f83-129">比利时</span><span class="sxs-lookup"><span data-stu-id="64f83-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="64f83-130">格式</span><span class="sxs-lookup"><span data-stu-id="64f83-130">Format</span></span>

<span data-ttu-id="64f83-131">两个字母后跟六个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="64f83-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64f83-132">模式</span><span class="sxs-lookup"><span data-stu-id="64f83-132">Pattern</span></span>

<span data-ttu-id="64f83-133">两个字母, 后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="64f83-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="64f83-134">校验和</span><span class="sxs-lookup"><span data-stu-id="64f83-134">Checksum</span></span>

<span data-ttu-id="64f83-135">不适用</span><span class="sxs-lookup"><span data-stu-id="64f83-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="64f83-136">定义</span><span class="sxs-lookup"><span data-stu-id="64f83-136">Definition</span></span>

<span data-ttu-id="64f83-137">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="64f83-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64f83-138">正则表达式`Regex_belgium_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="64f83-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64f83-139">找到了中`Keywords_belgium_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="64f83-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64f83-140">关键字</span><span class="sxs-lookup"><span data-stu-id="64f83-140">Keywords</span></span>

<span data-ttu-id="64f83-141">| |</span><span class="sxs-lookup"><span data-stu-id="64f83-141"></span></span>
|<span data-ttu-id="64f83-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64f83-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64f83-143">护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-143">passport number</span></span>  <br/> <span data-ttu-id="64f83-144">比利时护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-144">belgian passport number</span></span>  <br/> <span data-ttu-id="64f83-145">护照号</span><span class="sxs-lookup"><span data-stu-id="64f83-145">passport no</span></span>  <br/> <span data-ttu-id="64f83-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="64f83-146">paspoort</span></span>  <br/> <span data-ttu-id="64f83-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="64f83-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="64f83-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="64f83-148">reisepass kein</span></span>  <br/> <span data-ttu-id="64f83-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="64f83-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="64f83-150">保加利亚</span><span class="sxs-lookup"><span data-stu-id="64f83-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="64f83-151">格式</span><span class="sxs-lookup"><span data-stu-id="64f83-151">Format</span></span>

<span data-ttu-id="64f83-152">9个数字, 不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="64f83-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64f83-153">模式</span><span class="sxs-lookup"><span data-stu-id="64f83-153">Pattern</span></span>

 <span data-ttu-id="64f83-154">九个数字</span><span class="sxs-lookup"><span data-stu-id="64f83-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="64f83-155">校验和</span><span class="sxs-lookup"><span data-stu-id="64f83-155">Checksum</span></span>

<span data-ttu-id="64f83-156">否</span><span class="sxs-lookup"><span data-stu-id="64f83-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="64f83-157">定义</span><span class="sxs-lookup"><span data-stu-id="64f83-157">Definition</span></span>

<span data-ttu-id="64f83-158">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="64f83-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64f83-159">正则表达式`Regex_bulgaria_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="64f83-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64f83-160">找到了中`Keywords_bulgaria_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="64f83-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64f83-161">关键字</span><span class="sxs-lookup"><span data-stu-id="64f83-161">Keywords</span></span>

<span data-ttu-id="64f83-162">| |</span><span class="sxs-lookup"><span data-stu-id="64f83-162"></span></span>
|<span data-ttu-id="64f83-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64f83-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64f83-164">护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-164">passport number</span></span>  <br/> <span data-ttu-id="64f83-165">保加利亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="64f83-166">护照号</span><span class="sxs-lookup"><span data-stu-id="64f83-166">passport no</span></span>  <br/> <span data-ttu-id="64f83-167">номернапаспорта</span><span class="sxs-lookup"><span data-stu-id="64f83-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="64f83-168">克罗地亚</span><span class="sxs-lookup"><span data-stu-id="64f83-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="64f83-169">格式</span><span class="sxs-lookup"><span data-stu-id="64f83-169">Format</span></span>

<span data-ttu-id="64f83-170">9个数字, 不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="64f83-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64f83-171">模式</span><span class="sxs-lookup"><span data-stu-id="64f83-171">Pattern</span></span>

 <span data-ttu-id="64f83-172">九个数字</span><span class="sxs-lookup"><span data-stu-id="64f83-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="64f83-173">校验和</span><span class="sxs-lookup"><span data-stu-id="64f83-173">Checksum</span></span>

<span data-ttu-id="64f83-174">否</span><span class="sxs-lookup"><span data-stu-id="64f83-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="64f83-175">定义</span><span class="sxs-lookup"><span data-stu-id="64f83-175">Definition</span></span>

<span data-ttu-id="64f83-176">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="64f83-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64f83-177">正则表达式`Regex_croatia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="64f83-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64f83-178">找到了中`Keywords_croatia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="64f83-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64f83-179">关键字</span><span class="sxs-lookup"><span data-stu-id="64f83-179">Keywords</span></span>

<span data-ttu-id="64f83-180">| |</span><span class="sxs-lookup"><span data-stu-id="64f83-180"></span></span>
|<span data-ttu-id="64f83-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64f83-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64f83-182">护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-182">passport number</span></span>  <br/> <span data-ttu-id="64f83-183">克罗地亚护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-183">croatian passport number</span></span>  <br/> <span data-ttu-id="64f83-184">护照号</span><span class="sxs-lookup"><span data-stu-id="64f83-184">passport no</span></span>  <br/> <span data-ttu-id="64f83-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="64f83-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="64f83-186">塞浦路斯</span><span class="sxs-lookup"><span data-stu-id="64f83-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="64f83-187">格式</span><span class="sxs-lookup"><span data-stu-id="64f83-187">Format</span></span>

<span data-ttu-id="64f83-188">一个字母后跟6-8 个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="64f83-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64f83-189">模式</span><span class="sxs-lookup"><span data-stu-id="64f83-189">Pattern</span></span>

<span data-ttu-id="64f83-190">一个字母后跟6到8个数字</span><span class="sxs-lookup"><span data-stu-id="64f83-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="64f83-191">校验和</span><span class="sxs-lookup"><span data-stu-id="64f83-191">Checksum</span></span>

<span data-ttu-id="64f83-192">否</span><span class="sxs-lookup"><span data-stu-id="64f83-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="64f83-193">定义</span><span class="sxs-lookup"><span data-stu-id="64f83-193">Definition</span></span>

<span data-ttu-id="64f83-194">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="64f83-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64f83-195">正则表达式`Regex_cyprus_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="64f83-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64f83-196">找到了中`Keywords_cyprus_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="64f83-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64f83-197">关键字</span><span class="sxs-lookup"><span data-stu-id="64f83-197">Keywords</span></span>

<span data-ttu-id="64f83-198">| |</span><span class="sxs-lookup"><span data-stu-id="64f83-198"></span></span>
|<span data-ttu-id="64f83-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64f83-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64f83-200">护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-200">passport number</span></span>  <br/> <span data-ttu-id="64f83-201">塞浦路斯护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="64f83-202">护照号</span><span class="sxs-lookup"><span data-stu-id="64f83-202">passport no</span></span>  <br/> <span data-ttu-id="64f83-203">αριθμόδιαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="64f83-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="64f83-204">捷克共和国</span><span class="sxs-lookup"><span data-stu-id="64f83-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="64f83-205">格式</span><span class="sxs-lookup"><span data-stu-id="64f83-205">Format</span></span>

<span data-ttu-id="64f83-206">8位数, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="64f83-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64f83-207">模式</span><span class="sxs-lookup"><span data-stu-id="64f83-207">Pattern</span></span>

<span data-ttu-id="64f83-208">8位数, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="64f83-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="64f83-209">校验和</span><span class="sxs-lookup"><span data-stu-id="64f83-209">Checksum</span></span>

<span data-ttu-id="64f83-210">否</span><span class="sxs-lookup"><span data-stu-id="64f83-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="64f83-211">定义</span><span class="sxs-lookup"><span data-stu-id="64f83-211">Definition</span></span>

<span data-ttu-id="64f83-212">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="64f83-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64f83-213">正则表达式`Regex_czech_republic_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="64f83-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64f83-214">找到了中`Keywords_czech_republic_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="64f83-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64f83-215">关键字</span><span class="sxs-lookup"><span data-stu-id="64f83-215">Keywords</span></span>

<span data-ttu-id="64f83-216">| |</span><span class="sxs-lookup"><span data-stu-id="64f83-216"></span></span>
|<span data-ttu-id="64f83-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64f83-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64f83-218">护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-218">passport number</span></span>  <br/> <span data-ttu-id="64f83-219">捷克语护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-219">czech passport number</span></span>  <br/> <span data-ttu-id="64f83-220">护照号</span><span class="sxs-lookup"><span data-stu-id="64f83-220">passport no</span></span>  <br/> <span data-ttu-id="64f83-221">cestovní pas</span><span class="sxs-lookup"><span data-stu-id="64f83-221">cestovní pas</span></span>  <br/> <span data-ttu-id="64f83-222">pas</span><span class="sxs-lookup"><span data-stu-id="64f83-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="64f83-223">丹麦</span><span class="sxs-lookup"><span data-stu-id="64f83-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="64f83-224">格式</span><span class="sxs-lookup"><span data-stu-id="64f83-224">Format</span></span>

<span data-ttu-id="64f83-225">9个数字, 不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="64f83-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64f83-226">模式</span><span class="sxs-lookup"><span data-stu-id="64f83-226">Pattern</span></span>

 <span data-ttu-id="64f83-227">九个数字</span><span class="sxs-lookup"><span data-stu-id="64f83-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="64f83-228">校验和</span><span class="sxs-lookup"><span data-stu-id="64f83-228">Checksum</span></span>

<span data-ttu-id="64f83-229">否</span><span class="sxs-lookup"><span data-stu-id="64f83-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="64f83-230">定义</span><span class="sxs-lookup"><span data-stu-id="64f83-230">Definition</span></span>

<span data-ttu-id="64f83-231">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="64f83-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64f83-232">正则表达式`Regex_denmark_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="64f83-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64f83-233">找到了中`Keywords_denmark_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="64f83-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64f83-234">关键字</span><span class="sxs-lookup"><span data-stu-id="64f83-234">Keywords</span></span>

<span data-ttu-id="64f83-235">| |</span><span class="sxs-lookup"><span data-stu-id="64f83-235"></span></span>
|<span data-ttu-id="64f83-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64f83-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64f83-237">护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-237">passport number</span></span>  <br/> <span data-ttu-id="64f83-238">丹麦护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-238">danish passport number</span></span>  <br/> <span data-ttu-id="64f83-239">护照号</span><span class="sxs-lookup"><span data-stu-id="64f83-239">passport no</span></span>  <br/> <span data-ttu-id="64f83-240">pas</span><span class="sxs-lookup"><span data-stu-id="64f83-240">pas</span></span>  <br/> <span data-ttu-id="64f83-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="64f83-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="64f83-242">爱沙尼亚</span><span class="sxs-lookup"><span data-stu-id="64f83-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="64f83-243">格式</span><span class="sxs-lookup"><span data-stu-id="64f83-243">Format</span></span>

<span data-ttu-id="64f83-244">一个字母后跟七个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="64f83-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64f83-245">模式</span><span class="sxs-lookup"><span data-stu-id="64f83-245">Pattern</span></span>

<span data-ttu-id="64f83-246">一个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="64f83-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="64f83-247">校验和</span><span class="sxs-lookup"><span data-stu-id="64f83-247">Checksum</span></span>

<span data-ttu-id="64f83-248">否</span><span class="sxs-lookup"><span data-stu-id="64f83-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="64f83-249">定义</span><span class="sxs-lookup"><span data-stu-id="64f83-249">Definition</span></span>

<span data-ttu-id="64f83-250">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="64f83-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64f83-251">正则表达式`Regex_estonia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="64f83-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64f83-252">找到了中`Keywords_estonia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="64f83-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64f83-253">关键字</span><span class="sxs-lookup"><span data-stu-id="64f83-253">Keywords</span></span>

<span data-ttu-id="64f83-254">| |</span><span class="sxs-lookup"><span data-stu-id="64f83-254"></span></span>
|<span data-ttu-id="64f83-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64f83-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64f83-256">护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-256">passport number</span></span>  <br/> <span data-ttu-id="64f83-257">爱沙尼亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-257">estonian passport number</span></span>  <br/> <span data-ttu-id="64f83-258">护照号</span><span class="sxs-lookup"><span data-stu-id="64f83-258">passport no</span></span>  <br/> <span data-ttu-id="64f83-259">eesti kodaniku pass</span><span class="sxs-lookup"><span data-stu-id="64f83-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="64f83-260">芬兰</span><span class="sxs-lookup"><span data-stu-id="64f83-260">Finland</span></span>

<span data-ttu-id="64f83-261">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "芬兰护照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="64f83-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="64f83-262">法国</span><span class="sxs-lookup"><span data-stu-id="64f83-262">France</span></span>

<span data-ttu-id="64f83-263">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "法国护照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="64f83-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="64f83-264">德国</span><span class="sxs-lookup"><span data-stu-id="64f83-264">Germany</span></span>

<span data-ttu-id="64f83-265">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "德国护照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="64f83-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="64f83-266">希腊</span><span class="sxs-lookup"><span data-stu-id="64f83-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="64f83-267">格式</span><span class="sxs-lookup"><span data-stu-id="64f83-267">Format</span></span>

<span data-ttu-id="64f83-268">两个字母后跟七个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="64f83-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64f83-269">模式</span><span class="sxs-lookup"><span data-stu-id="64f83-269">Pattern</span></span>

<span data-ttu-id="64f83-270">两个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="64f83-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="64f83-271">校验和</span><span class="sxs-lookup"><span data-stu-id="64f83-271">Checksum</span></span>

<span data-ttu-id="64f83-272">否</span><span class="sxs-lookup"><span data-stu-id="64f83-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="64f83-273">定义</span><span class="sxs-lookup"><span data-stu-id="64f83-273">Definition</span></span>

<span data-ttu-id="64f83-274">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="64f83-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64f83-275">正则表达式`Regex_greece_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="64f83-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64f83-276">找到了中`Keywords_greece_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="64f83-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64f83-277">关键字</span><span class="sxs-lookup"><span data-stu-id="64f83-277">Keywords</span></span>

<span data-ttu-id="64f83-278">| |</span><span class="sxs-lookup"><span data-stu-id="64f83-278"></span></span>
|<span data-ttu-id="64f83-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64f83-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64f83-280">护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-280">passport number</span></span>  <br/> <span data-ttu-id="64f83-281">希腊护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-281">greek passport number</span></span>  <br/> <span data-ttu-id="64f83-282">护照号</span><span class="sxs-lookup"><span data-stu-id="64f83-282">passport no</span></span>  <br/> <span data-ttu-id="64f83-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="64f83-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="64f83-284">匈牙利</span><span class="sxs-lookup"><span data-stu-id="64f83-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="64f83-285">格式</span><span class="sxs-lookup"><span data-stu-id="64f83-285">Format</span></span>

<span data-ttu-id="64f83-286">两个字母后跟6个或7个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="64f83-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64f83-287">模式</span><span class="sxs-lookup"><span data-stu-id="64f83-287">Pattern</span></span>

<span data-ttu-id="64f83-288">两个字母后跟六个或七个数字</span><span class="sxs-lookup"><span data-stu-id="64f83-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="64f83-289">校验和</span><span class="sxs-lookup"><span data-stu-id="64f83-289">Checksum</span></span>

<span data-ttu-id="64f83-290">否</span><span class="sxs-lookup"><span data-stu-id="64f83-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="64f83-291">定义</span><span class="sxs-lookup"><span data-stu-id="64f83-291">Definition</span></span>

<span data-ttu-id="64f83-292">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="64f83-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64f83-293">正则表达式`Regex_hungary_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="64f83-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64f83-294">找到了中`Keywords_hungary_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="64f83-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64f83-295">关键字</span><span class="sxs-lookup"><span data-stu-id="64f83-295">Keywords</span></span>

<span data-ttu-id="64f83-296">| |</span><span class="sxs-lookup"><span data-stu-id="64f83-296"></span></span>
|<span data-ttu-id="64f83-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64f83-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64f83-298">护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-298">passport number</span></span>  <br/> <span data-ttu-id="64f83-299">匈牙利语护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="64f83-300">护照号</span><span class="sxs-lookup"><span data-stu-id="64f83-300">passport no</span></span>  <br/> <span data-ttu-id="64f83-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="64f83-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="64f83-302">Ireland</span><span class="sxs-lookup"><span data-stu-id="64f83-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="64f83-303">格式</span><span class="sxs-lookup"><span data-stu-id="64f83-303">Format</span></span>

<span data-ttu-id="64f83-304">两个字母或数字后跟七个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="64f83-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64f83-305">模式</span><span class="sxs-lookup"><span data-stu-id="64f83-305">Pattern</span></span>

<span data-ttu-id="64f83-306">两个字母或数字, 后跟七个数字:</span><span class="sxs-lookup"><span data-stu-id="64f83-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="64f83-307">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="64f83-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="64f83-308">七个数字</span><span class="sxs-lookup"><span data-stu-id="64f83-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="64f83-309">校验和</span><span class="sxs-lookup"><span data-stu-id="64f83-309">Checksum</span></span>

<span data-ttu-id="64f83-310">否</span><span class="sxs-lookup"><span data-stu-id="64f83-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="64f83-311">定义</span><span class="sxs-lookup"><span data-stu-id="64f83-311">Definition</span></span>

<span data-ttu-id="64f83-312">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="64f83-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64f83-313">正则表达式`Regex_ireland_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="64f83-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64f83-314">找到了中`Keywords_ireland_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="64f83-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64f83-315">关键字</span><span class="sxs-lookup"><span data-stu-id="64f83-315">Keywords</span></span>

<span data-ttu-id="64f83-316">| |</span><span class="sxs-lookup"><span data-stu-id="64f83-316"></span></span>
|<span data-ttu-id="64f83-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64f83-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64f83-318">护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-318">passport number</span></span>  <br/> <span data-ttu-id="64f83-319">爱尔兰护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-319">irish passport number</span></span>  <br/> <span data-ttu-id="64f83-320">护照号</span><span class="sxs-lookup"><span data-stu-id="64f83-320">passport no</span></span>  <br/> <span data-ttu-id="64f83-321">pas</span><span class="sxs-lookup"><span data-stu-id="64f83-321">pas</span></span>  <br/> <span data-ttu-id="64f83-322">passport</span><span class="sxs-lookup"><span data-stu-id="64f83-322">passport</span></span>  <br/> <span data-ttu-id="64f83-323">passeport</span><span class="sxs-lookup"><span data-stu-id="64f83-323">passeport</span></span>  <br/> <span data-ttu-id="64f83-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="64f83-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="64f83-325">意大利</span><span class="sxs-lookup"><span data-stu-id="64f83-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="64f83-326">格式</span><span class="sxs-lookup"><span data-stu-id="64f83-326">Format</span></span>

<span data-ttu-id="64f83-327">两个字母或数字后跟七个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="64f83-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64f83-328">模式</span><span class="sxs-lookup"><span data-stu-id="64f83-328">Pattern</span></span>

<span data-ttu-id="64f83-329">两个字母或数字, 后跟七个数字:</span><span class="sxs-lookup"><span data-stu-id="64f83-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="64f83-330">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="64f83-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="64f83-331">七个数字</span><span class="sxs-lookup"><span data-stu-id="64f83-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="64f83-332">校验和</span><span class="sxs-lookup"><span data-stu-id="64f83-332">Checksum</span></span>

<span data-ttu-id="64f83-333">不适用</span><span class="sxs-lookup"><span data-stu-id="64f83-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="64f83-334">定义</span><span class="sxs-lookup"><span data-stu-id="64f83-334">Definition</span></span>

<span data-ttu-id="64f83-335">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="64f83-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64f83-336">正则表达式`Regex_italy_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="64f83-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64f83-337">找到了中`Keywords_italy_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="64f83-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64f83-338">关键字</span><span class="sxs-lookup"><span data-stu-id="64f83-338">Keywords</span></span>

<span data-ttu-id="64f83-339">| |</span><span class="sxs-lookup"><span data-stu-id="64f83-339"></span></span>
|<span data-ttu-id="64f83-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64f83-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64f83-341">意大利护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-341">italian passport number</span></span>  <br/> <span data-ttu-id="64f83-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="64f83-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="64f83-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="64f83-343">passaporto</span></span>  <br/> <span data-ttu-id="64f83-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="64f83-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="64f83-345">护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-345">passport number</span></span>  <br/> <span data-ttu-id="64f83-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="64f83-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="64f83-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="64f83-347">passaporto numero</span></span>  <br/> <span data-ttu-id="64f83-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="64f83-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="64f83-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="64f83-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="64f83-350">拉脱维亚</span><span class="sxs-lookup"><span data-stu-id="64f83-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="64f83-351">格式</span><span class="sxs-lookup"><span data-stu-id="64f83-351">Format</span></span>

<span data-ttu-id="64f83-352">两个字母或数字后跟七个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="64f83-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64f83-353">模式</span><span class="sxs-lookup"><span data-stu-id="64f83-353">Pattern</span></span>

<span data-ttu-id="64f83-354">两个字母或数字, 后跟七个数字:</span><span class="sxs-lookup"><span data-stu-id="64f83-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="64f83-355">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="64f83-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="64f83-356">七个数字</span><span class="sxs-lookup"><span data-stu-id="64f83-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="64f83-357">校验和</span><span class="sxs-lookup"><span data-stu-id="64f83-357">Checksum</span></span>

<span data-ttu-id="64f83-358">否</span><span class="sxs-lookup"><span data-stu-id="64f83-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="64f83-359">定义</span><span class="sxs-lookup"><span data-stu-id="64f83-359">Definition</span></span>

<span data-ttu-id="64f83-360">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="64f83-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64f83-361">正则表达式`Regex_latvia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="64f83-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64f83-362">找到了中`Keywords_latvia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="64f83-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64f83-363">关键字</span><span class="sxs-lookup"><span data-stu-id="64f83-363">Keywords</span></span>

<span data-ttu-id="64f83-364">| |</span><span class="sxs-lookup"><span data-stu-id="64f83-364"></span></span>
|<span data-ttu-id="64f83-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64f83-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64f83-366">护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-366">passport number</span></span>  <br/> <span data-ttu-id="64f83-367">拉脱维亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-367">latvian passport number</span></span>  <br/> <span data-ttu-id="64f83-368">护照号</span><span class="sxs-lookup"><span data-stu-id="64f83-368">passport no</span></span>  <br/> <span data-ttu-id="64f83-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="64f83-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="64f83-370">立陶宛</span><span class="sxs-lookup"><span data-stu-id="64f83-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="64f83-371">格式</span><span class="sxs-lookup"><span data-stu-id="64f83-371">Format</span></span>

<span data-ttu-id="64f83-372">八个数字或字母不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="64f83-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64f83-373">模式</span><span class="sxs-lookup"><span data-stu-id="64f83-373">Pattern</span></span>

<span data-ttu-id="64f83-374">八个数字或字母 (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="64f83-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="64f83-375">校验和</span><span class="sxs-lookup"><span data-stu-id="64f83-375">Checksum</span></span>

<span data-ttu-id="64f83-376">不适用</span><span class="sxs-lookup"><span data-stu-id="64f83-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="64f83-377">定义</span><span class="sxs-lookup"><span data-stu-id="64f83-377">Definition</span></span>

<span data-ttu-id="64f83-378">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="64f83-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64f83-379">正则表达式`Regex_lithuania_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="64f83-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64f83-380">找到了中`Keywords_lithuania_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="64f83-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64f83-381">关键字</span><span class="sxs-lookup"><span data-stu-id="64f83-381">Keywords</span></span>

<span data-ttu-id="64f83-382">| |</span><span class="sxs-lookup"><span data-stu-id="64f83-382"></span></span>
|<span data-ttu-id="64f83-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64f83-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64f83-384">护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-384">passport number</span></span>  <br/> <span data-ttu-id="64f83-385">lithunian 护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="64f83-386">护照号</span><span class="sxs-lookup"><span data-stu-id="64f83-386">passport no</span></span>  <br/> <span data-ttu-id="64f83-387">paso numeris</span><span class="sxs-lookup"><span data-stu-id="64f83-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="64f83-388">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="64f83-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="64f83-389">格式</span><span class="sxs-lookup"><span data-stu-id="64f83-389">Format</span></span>

<span data-ttu-id="64f83-390">八个数字或字母不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="64f83-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64f83-391">模式</span><span class="sxs-lookup"><span data-stu-id="64f83-391">Pattern</span></span>

<span data-ttu-id="64f83-392">八个数字或字母 (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="64f83-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="64f83-393">校验和</span><span class="sxs-lookup"><span data-stu-id="64f83-393">Checksum</span></span>

<span data-ttu-id="64f83-394">否</span><span class="sxs-lookup"><span data-stu-id="64f83-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="64f83-395">定义</span><span class="sxs-lookup"><span data-stu-id="64f83-395">Definition</span></span>

<span data-ttu-id="64f83-396">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="64f83-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64f83-397">正则表达式`Regex_nation_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="64f83-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64f83-398">找到了中`Keywords_nation_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="64f83-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64f83-399">关键字</span><span class="sxs-lookup"><span data-stu-id="64f83-399">Keywords</span></span>

<span data-ttu-id="64f83-400">| |</span><span class="sxs-lookup"><span data-stu-id="64f83-400"></span></span>
|<span data-ttu-id="64f83-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64f83-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64f83-402">护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-402">passport number</span></span>  <br/> <span data-ttu-id="64f83-403">拉脱维亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-403">latvian passport number</span></span>  <br/> <span data-ttu-id="64f83-404">护照号</span><span class="sxs-lookup"><span data-stu-id="64f83-404">passport no</span></span>  <br/> <span data-ttu-id="64f83-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="64f83-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="64f83-406">马耳他</span><span class="sxs-lookup"><span data-stu-id="64f83-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="64f83-407">格式</span><span class="sxs-lookup"><span data-stu-id="64f83-407">Format</span></span>

<span data-ttu-id="64f83-408">七位数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="64f83-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64f83-409">模式</span><span class="sxs-lookup"><span data-stu-id="64f83-409">Pattern</span></span>

 <span data-ttu-id="64f83-410">七个数字</span><span class="sxs-lookup"><span data-stu-id="64f83-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="64f83-411">校验和</span><span class="sxs-lookup"><span data-stu-id="64f83-411">Checksum</span></span>

<span data-ttu-id="64f83-412">否</span><span class="sxs-lookup"><span data-stu-id="64f83-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="64f83-413">定义</span><span class="sxs-lookup"><span data-stu-id="64f83-413">Definition</span></span>

<span data-ttu-id="64f83-414">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="64f83-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64f83-415">正则表达式`Regex_malta_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="64f83-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64f83-416">找到了中`Keywords_malta_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="64f83-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64f83-417">关键字</span><span class="sxs-lookup"><span data-stu-id="64f83-417">Keywords</span></span>

<span data-ttu-id="64f83-418">| |</span><span class="sxs-lookup"><span data-stu-id="64f83-418"></span></span>
|<span data-ttu-id="64f83-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64f83-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64f83-420">护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-420">passport number</span></span>  <br/> <span data-ttu-id="64f83-421">马耳他护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-421">maltese passport number</span></span>  <br/> <span data-ttu-id="64f83-422">护照号</span><span class="sxs-lookup"><span data-stu-id="64f83-422">passport no</span></span>  <br/> <span data-ttu-id="64f83-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="64f83-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="64f83-424">荷兰</span><span class="sxs-lookup"><span data-stu-id="64f83-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="64f83-425">格式</span><span class="sxs-lookup"><span data-stu-id="64f83-425">Format</span></span>

<span data-ttu-id="64f83-426">九个字母或数字, 不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="64f83-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64f83-427">模式</span><span class="sxs-lookup"><span data-stu-id="64f83-427">Pattern</span></span>

<span data-ttu-id="64f83-428">九个字母或数字</span><span class="sxs-lookup"><span data-stu-id="64f83-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="64f83-429">校验和</span><span class="sxs-lookup"><span data-stu-id="64f83-429">Checksum</span></span>

<span data-ttu-id="64f83-430">不适用</span><span class="sxs-lookup"><span data-stu-id="64f83-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="64f83-431">定义</span><span class="sxs-lookup"><span data-stu-id="64f83-431">Definition</span></span>

<span data-ttu-id="64f83-432">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="64f83-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64f83-433">正则表达式`Regex_netherlands_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="64f83-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64f83-434">找到了中`Keywords_netherlands_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="64f83-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64f83-435">关键字</span><span class="sxs-lookup"><span data-stu-id="64f83-435">Keywords</span></span>

<span data-ttu-id="64f83-436">| |</span><span class="sxs-lookup"><span data-stu-id="64f83-436"></span></span>
|<span data-ttu-id="64f83-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64f83-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64f83-438">荷兰护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-438">dutch passport number</span></span>  <br/> <span data-ttu-id="64f83-439">护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-439">passport number</span></span>  <br/> <span data-ttu-id="64f83-440">荷兰护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="64f83-441">nederlanden paspoort nummer</span><span class="sxs-lookup"><span data-stu-id="64f83-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="64f83-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="64f83-442">paspoort</span></span>  <br/> <span data-ttu-id="64f83-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="64f83-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="64f83-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="64f83-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="64f83-445">波兰</span><span class="sxs-lookup"><span data-stu-id="64f83-445">Poland</span></span>

<span data-ttu-id="64f83-446">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "波兰 Passport 号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="64f83-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="64f83-447">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="64f83-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="64f83-448">格式</span><span class="sxs-lookup"><span data-stu-id="64f83-448">Format</span></span>

<span data-ttu-id="64f83-449">一个字母后跟六个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="64f83-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64f83-450">模式</span><span class="sxs-lookup"><span data-stu-id="64f83-450">Pattern</span></span>

<span data-ttu-id="64f83-451">一个字母后跟六个数字:</span><span class="sxs-lookup"><span data-stu-id="64f83-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="64f83-452">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="64f83-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="64f83-453">六个数字</span><span class="sxs-lookup"><span data-stu-id="64f83-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="64f83-454">校验和</span><span class="sxs-lookup"><span data-stu-id="64f83-454">Checksum</span></span>

<span data-ttu-id="64f83-455">否</span><span class="sxs-lookup"><span data-stu-id="64f83-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="64f83-456">定义</span><span class="sxs-lookup"><span data-stu-id="64f83-456">Definition</span></span>

<span data-ttu-id="64f83-457">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="64f83-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64f83-458">正则表达式`Regex_portugal_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="64f83-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64f83-459">找到了中`Keywords_portugal_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="64f83-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64f83-460">关键字</span><span class="sxs-lookup"><span data-stu-id="64f83-460">Keywords</span></span>

<span data-ttu-id="64f83-461">| |</span><span class="sxs-lookup"><span data-stu-id="64f83-461"></span></span>
|<span data-ttu-id="64f83-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64f83-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64f83-463">护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-463">passport number</span></span>  <br/> <span data-ttu-id="64f83-464">葡萄牙语护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="64f83-465">护照号</span><span class="sxs-lookup"><span data-stu-id="64f83-465">passport no</span></span>  <br/> <span data-ttu-id="64f83-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="64f83-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="64f83-467">罗马尼亚</span><span class="sxs-lookup"><span data-stu-id="64f83-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="64f83-468">格式</span><span class="sxs-lookup"><span data-stu-id="64f83-468">Format</span></span>

<span data-ttu-id="64f83-469">八个或9个数字, 不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="64f83-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64f83-470">模式</span><span class="sxs-lookup"><span data-stu-id="64f83-470">Pattern</span></span>

<span data-ttu-id="64f83-471">8或9个数字</span><span class="sxs-lookup"><span data-stu-id="64f83-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="64f83-472">校验和</span><span class="sxs-lookup"><span data-stu-id="64f83-472">Checksum</span></span>

<span data-ttu-id="64f83-473">否</span><span class="sxs-lookup"><span data-stu-id="64f83-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="64f83-474">定义</span><span class="sxs-lookup"><span data-stu-id="64f83-474">Definition</span></span>

<span data-ttu-id="64f83-475">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="64f83-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64f83-476">正则表达式`Regex_romania_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="64f83-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64f83-477">找到了中`Keywords_romania_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="64f83-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64f83-478">关键字</span><span class="sxs-lookup"><span data-stu-id="64f83-478">Keywords</span></span>

<span data-ttu-id="64f83-479">| |</span><span class="sxs-lookup"><span data-stu-id="64f83-479"></span></span>
|<span data-ttu-id="64f83-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64f83-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64f83-481">护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-481">passport number</span></span>  <br/> <span data-ttu-id="64f83-482">罗马尼亚护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-482">romanian passport number</span></span>  <br/> <span data-ttu-id="64f83-483">护照号</span><span class="sxs-lookup"><span data-stu-id="64f83-483">passport no</span></span>  <br/> <span data-ttu-id="64f83-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="64f83-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="64f83-485">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="64f83-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="64f83-486">格式</span><span class="sxs-lookup"><span data-stu-id="64f83-486">Format</span></span>

<span data-ttu-id="64f83-487">一个数字或字母后跟七个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="64f83-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64f83-488">模式</span><span class="sxs-lookup"><span data-stu-id="64f83-488">Pattern</span></span>

<span data-ttu-id="64f83-489">一个数字或字母 (不区分大小写) 后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="64f83-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="64f83-490">校验和</span><span class="sxs-lookup"><span data-stu-id="64f83-490">Checksum</span></span>

<span data-ttu-id="64f83-491">否</span><span class="sxs-lookup"><span data-stu-id="64f83-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="64f83-492">定义</span><span class="sxs-lookup"><span data-stu-id="64f83-492">Definition</span></span>

<span data-ttu-id="64f83-493">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="64f83-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64f83-494">正则表达式`Regex_slovakia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="64f83-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64f83-495">找到了中`Keywords_slovakia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="64f83-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64f83-496">关键字</span><span class="sxs-lookup"><span data-stu-id="64f83-496">Keywords</span></span>

<span data-ttu-id="64f83-497">| |</span><span class="sxs-lookup"><span data-stu-id="64f83-497"></span></span>
|<span data-ttu-id="64f83-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64f83-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64f83-499">护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-499">passport number</span></span>  <br/> <span data-ttu-id="64f83-500">斯洛伐克护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="64f83-501">护照号</span><span class="sxs-lookup"><span data-stu-id="64f83-501">passport no</span></span>  <br/> <span data-ttu-id="64f83-502">číslo pasu</span><span class="sxs-lookup"><span data-stu-id="64f83-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="64f83-503">斯诺文尼亚</span><span class="sxs-lookup"><span data-stu-id="64f83-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="64f83-504">格式</span><span class="sxs-lookup"><span data-stu-id="64f83-504">Format</span></span>

<span data-ttu-id="64f83-505">两个字母后跟七个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="64f83-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64f83-506">模式</span><span class="sxs-lookup"><span data-stu-id="64f83-506">Pattern</span></span>

<span data-ttu-id="64f83-507">两个字母后跟七个数字:</span><span class="sxs-lookup"><span data-stu-id="64f83-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="64f83-508">字母 "P"</span><span class="sxs-lookup"><span data-stu-id="64f83-508">The letter "P"</span></span>
    
- <span data-ttu-id="64f83-509">一个大写字母</span><span class="sxs-lookup"><span data-stu-id="64f83-509">One uppercase letter</span></span>
    
- <span data-ttu-id="64f83-510">七个数字</span><span class="sxs-lookup"><span data-stu-id="64f83-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="64f83-511">校验和</span><span class="sxs-lookup"><span data-stu-id="64f83-511">Checksum</span></span>

<span data-ttu-id="64f83-512">否</span><span class="sxs-lookup"><span data-stu-id="64f83-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="64f83-513">定义</span><span class="sxs-lookup"><span data-stu-id="64f83-513">Definition</span></span>

<span data-ttu-id="64f83-514">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="64f83-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64f83-515">正则表达式`Regex_slovenia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="64f83-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64f83-516">找到了中`Keywords_slovenia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="64f83-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64f83-517">关键字</span><span class="sxs-lookup"><span data-stu-id="64f83-517">Keywords</span></span>

<span data-ttu-id="64f83-518">| |</span><span class="sxs-lookup"><span data-stu-id="64f83-518"></span></span>
|<span data-ttu-id="64f83-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64f83-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64f83-520">护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-520">passport number</span></span>  <br/> <span data-ttu-id="64f83-521">斯洛文尼亚护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="64f83-522">护照号</span><span class="sxs-lookup"><span data-stu-id="64f83-522">passport no</span></span>  <br/> <span data-ttu-id="64f83-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="64f83-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="64f83-524">西班牙</span><span class="sxs-lookup"><span data-stu-id="64f83-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="64f83-525">格式</span><span class="sxs-lookup"><span data-stu-id="64f83-525">Format</span></span>

<span data-ttu-id="64f83-526">八个或九个字符的字母和数字的组合, 不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="64f83-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64f83-527">模式</span><span class="sxs-lookup"><span data-stu-id="64f83-527">Pattern</span></span>

<span data-ttu-id="64f83-528">字母和数字的八个或九个字符的组合:</span><span class="sxs-lookup"><span data-stu-id="64f83-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="64f83-529">两位数字或字母</span><span class="sxs-lookup"><span data-stu-id="64f83-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="64f83-530">一个数字或字母 (可选)</span><span class="sxs-lookup"><span data-stu-id="64f83-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="64f83-531">六个数字</span><span class="sxs-lookup"><span data-stu-id="64f83-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="64f83-532">校验和</span><span class="sxs-lookup"><span data-stu-id="64f83-532">Checksum</span></span>

<span data-ttu-id="64f83-533">不适用</span><span class="sxs-lookup"><span data-stu-id="64f83-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="64f83-534">定义</span><span class="sxs-lookup"><span data-stu-id="64f83-534">Definition</span></span>

<span data-ttu-id="64f83-535">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="64f83-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64f83-536">正则表达式`Regex_spain_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="64f83-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64f83-537">找到了中`Keywords_spain_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="64f83-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64f83-538">关键字</span><span class="sxs-lookup"><span data-stu-id="64f83-538">Keywords</span></span>

<span data-ttu-id="64f83-539">| |</span><span class="sxs-lookup"><span data-stu-id="64f83-539"></span></span>
|<span data-ttu-id="64f83-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64f83-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64f83-541">passport</span><span class="sxs-lookup"><span data-stu-id="64f83-541">passport</span></span>  <br/> <span data-ttu-id="64f83-542">西班牙护照</span><span class="sxs-lookup"><span data-stu-id="64f83-542">spain passport</span></span>  <br/> <span data-ttu-id="64f83-543">护照书籍</span><span class="sxs-lookup"><span data-stu-id="64f83-543">passport book</span></span>  <br/> <span data-ttu-id="64f83-544">护照号码</span><span class="sxs-lookup"><span data-stu-id="64f83-544">passport number</span></span>  <br/> <span data-ttu-id="64f83-545">护照号</span><span class="sxs-lookup"><span data-stu-id="64f83-545">passport no</span></span>  <br/> <span data-ttu-id="64f83-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="64f83-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="64f83-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="64f83-547">número pasaporte</span></span>  <br/> <span data-ttu-id="64f83-548">西班牙 pasaporte</span><span class="sxs-lookup"><span data-stu-id="64f83-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="64f83-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="64f83-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="64f83-550">瑞典</span><span class="sxs-lookup"><span data-stu-id="64f83-550">Sweden</span></span>

<span data-ttu-id="64f83-551">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "瑞典护照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="64f83-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="64f83-552">英国</span><span class="sxs-lookup"><span data-stu-id="64f83-552">UK</span></span>

<span data-ttu-id="64f83-p103">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)部分中的 "美国/英国护照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="64f83-p103">For details, see the section "U.S. / U.K. Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="64f83-555">另请参阅</span><span class="sxs-lookup"><span data-stu-id="64f83-555">See also</span></span>

[<span data-ttu-id="64f83-556">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="64f83-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

