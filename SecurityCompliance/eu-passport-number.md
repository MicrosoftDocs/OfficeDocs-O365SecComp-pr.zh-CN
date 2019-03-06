---
title: EU 护照号码
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主题介绍当数据丢失防护 (DLP) 策略检测到欧盟护照号敏感信息类型时, 应查找什么内容。 此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。
ms.openlocfilehash: 3ab92e87607f41cffa8c15f1179a4eef5369cb29
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410927"
---
# <a name="eu-passport-number"></a><span data-ttu-id="8e6d4-104">EU 护照号码</span><span class="sxs-lookup"><span data-stu-id="8e6d4-104">EU Passport Number</span></span>

<span data-ttu-id="8e6d4-105">本主题介绍当数据丢失防护 (DLP) 策略检测到欧盟护照号敏感信息类型时, 应查找什么内容。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="8e6d4-106">此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="8e6d4-107">奥地利</span><span class="sxs-lookup"><span data-stu-id="8e6d4-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="8e6d4-108">格式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-108">Format</span></span>

<span data-ttu-id="8e6d4-109">一个字母后跟一个可选空格和七个数字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8e6d4-110">模式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-110">Pattern</span></span>

<span data-ttu-id="8e6d4-111">一个字母、七个数字和一个空格的组合:</span><span class="sxs-lookup"><span data-stu-id="8e6d4-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="8e6d4-112">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="8e6d4-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="8e6d4-113">一个空格 (可选)</span><span class="sxs-lookup"><span data-stu-id="8e6d4-113">One space (optional)</span></span>
    
- <span data-ttu-id="8e6d4-114">七个数字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8e6d4-115">校验和</span><span class="sxs-lookup"><span data-stu-id="8e6d4-115">Checksum</span></span>

<span data-ttu-id="8e6d4-116">不适用</span><span class="sxs-lookup"><span data-stu-id="8e6d4-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8e6d4-117">定义</span><span class="sxs-lookup"><span data-stu-id="8e6d4-117">Definition</span></span>

<span data-ttu-id="8e6d4-118">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8e6d4-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8e6d4-119">正则表达式`Regex_austria_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8e6d4-120">找到了中`Keywords_austria_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8e6d4-121">关键字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-121">Keywords</span></span>

<span data-ttu-id="8e6d4-122">| |</span><span class="sxs-lookup"><span data-stu-id="8e6d4-122"></span></span>
|<span data-ttu-id="8e6d4-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8e6d4-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8e6d4-124">passport number</span><span class="sxs-lookup"><span data-stu-id="8e6d4-124">passport number</span></span>  <br/> <span data-ttu-id="8e6d4-125">奥地利护照号码</span><span class="sxs-lookup"><span data-stu-id="8e6d4-125">austrian passport number</span></span>  <br/> <span data-ttu-id="8e6d4-126">护照号</span><span class="sxs-lookup"><span data-stu-id="8e6d4-126">passport no</span></span>  <br/> <span data-ttu-id="8e6d4-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="8e6d4-127">reisepass</span></span>  <br/> <span data-ttu-id="8e6d4-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="8e6d4-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="8e6d4-129">比利时</span><span class="sxs-lookup"><span data-stu-id="8e6d4-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="8e6d4-130">格式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-130">Format</span></span>

<span data-ttu-id="8e6d4-131">两个字母后跟六个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8e6d4-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8e6d4-132">模式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-132">Pattern</span></span>

<span data-ttu-id="8e6d4-133">两个字母, 后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8e6d4-134">校验和</span><span class="sxs-lookup"><span data-stu-id="8e6d4-134">Checksum</span></span>

<span data-ttu-id="8e6d4-135">不适用</span><span class="sxs-lookup"><span data-stu-id="8e6d4-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8e6d4-136">定义</span><span class="sxs-lookup"><span data-stu-id="8e6d4-136">Definition</span></span>

<span data-ttu-id="8e6d4-137">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8e6d4-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8e6d4-138">正则表达式`Regex_belgium_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8e6d4-139">找到了中`Keywords_belgium_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8e6d4-140">关键字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-140">Keywords</span></span>

<span data-ttu-id="8e6d4-141">| |</span><span class="sxs-lookup"><span data-stu-id="8e6d4-141"></span></span>
|<span data-ttu-id="8e6d4-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8e6d4-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8e6d4-143">passport number</span><span class="sxs-lookup"><span data-stu-id="8e6d4-143">passport number</span></span>  <br/> <span data-ttu-id="8e6d4-144">比利时护照号码</span><span class="sxs-lookup"><span data-stu-id="8e6d4-144">belgian passport number</span></span>  <br/> <span data-ttu-id="8e6d4-145">护照号</span><span class="sxs-lookup"><span data-stu-id="8e6d4-145">passport no</span></span>  <br/> <span data-ttu-id="8e6d4-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="8e6d4-146">paspoort</span></span>  <br/> <span data-ttu-id="8e6d4-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="8e6d4-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="8e6d4-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="8e6d4-148">reisepass kein</span></span>  <br/> <span data-ttu-id="8e6d4-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="8e6d4-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="8e6d4-150">保加利亚语</span><span class="sxs-lookup"><span data-stu-id="8e6d4-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="8e6d4-151">格式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-151">Format</span></span>

<span data-ttu-id="8e6d4-152">9个数字, 不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="8e6d4-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8e6d4-153">模式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-153">Pattern</span></span>

 <span data-ttu-id="8e6d4-154">九个数字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="8e6d4-155">校验和</span><span class="sxs-lookup"><span data-stu-id="8e6d4-155">Checksum</span></span>

<span data-ttu-id="8e6d4-156">否</span><span class="sxs-lookup"><span data-stu-id="8e6d4-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8e6d4-157">定义</span><span class="sxs-lookup"><span data-stu-id="8e6d4-157">Definition</span></span>

<span data-ttu-id="8e6d4-158">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8e6d4-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8e6d4-159">正则表达式`Regex_bulgaria_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8e6d4-160">找到了中`Keywords_bulgaria_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8e6d4-161">关键字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-161">Keywords</span></span>

<span data-ttu-id="8e6d4-162">| |</span><span class="sxs-lookup"><span data-stu-id="8e6d4-162"></span></span>
|<span data-ttu-id="8e6d4-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8e6d4-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8e6d4-164">passport number</span><span class="sxs-lookup"><span data-stu-id="8e6d4-164">passport number</span></span>  <br/> <span data-ttu-id="8e6d4-165">保加利亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="8e6d4-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="8e6d4-166">护照号</span><span class="sxs-lookup"><span data-stu-id="8e6d4-166">passport no</span></span>  <br/> <span data-ttu-id="8e6d4-167">номернапаспорта</span><span class="sxs-lookup"><span data-stu-id="8e6d4-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="8e6d4-168">克罗地亚</span><span class="sxs-lookup"><span data-stu-id="8e6d4-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="8e6d4-169">格式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-169">Format</span></span>

<span data-ttu-id="8e6d4-170">9个数字, 不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="8e6d4-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8e6d4-171">模式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-171">Pattern</span></span>

 <span data-ttu-id="8e6d4-172">九个数字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="8e6d4-173">校验和</span><span class="sxs-lookup"><span data-stu-id="8e6d4-173">Checksum</span></span>

<span data-ttu-id="8e6d4-174">否</span><span class="sxs-lookup"><span data-stu-id="8e6d4-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8e6d4-175">定义</span><span class="sxs-lookup"><span data-stu-id="8e6d4-175">Definition</span></span>

<span data-ttu-id="8e6d4-176">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8e6d4-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8e6d4-177">正则表达式`Regex_croatia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8e6d4-178">找到了中`Keywords_croatia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8e6d4-179">关键字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-179">Keywords</span></span>

<span data-ttu-id="8e6d4-180">| |</span><span class="sxs-lookup"><span data-stu-id="8e6d4-180"></span></span>
|<span data-ttu-id="8e6d4-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8e6d4-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8e6d4-182">passport number</span><span class="sxs-lookup"><span data-stu-id="8e6d4-182">passport number</span></span>  <br/> <span data-ttu-id="8e6d4-183">克罗地亚护照号码</span><span class="sxs-lookup"><span data-stu-id="8e6d4-183">croatian passport number</span></span>  <br/> <span data-ttu-id="8e6d4-184">护照号</span><span class="sxs-lookup"><span data-stu-id="8e6d4-184">passport no</span></span>  <br/> <span data-ttu-id="8e6d4-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="8e6d4-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="8e6d4-186">塞浦路斯</span><span class="sxs-lookup"><span data-stu-id="8e6d4-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="8e6d4-187">格式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-187">Format</span></span>

<span data-ttu-id="8e6d4-188">一个字母后跟6-8 个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8e6d4-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8e6d4-189">模式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-189">Pattern</span></span>

<span data-ttu-id="8e6d4-190">一个字母后跟6到8个数字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8e6d4-191">校验和</span><span class="sxs-lookup"><span data-stu-id="8e6d4-191">Checksum</span></span>

<span data-ttu-id="8e6d4-192">否</span><span class="sxs-lookup"><span data-stu-id="8e6d4-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8e6d4-193">定义</span><span class="sxs-lookup"><span data-stu-id="8e6d4-193">Definition</span></span>

<span data-ttu-id="8e6d4-194">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8e6d4-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8e6d4-195">正则表达式`Regex_cyprus_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8e6d4-196">找到了中`Keywords_cyprus_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8e6d4-197">关键字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-197">Keywords</span></span>

<span data-ttu-id="8e6d4-198">| |</span><span class="sxs-lookup"><span data-stu-id="8e6d4-198"></span></span>
|<span data-ttu-id="8e6d4-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8e6d4-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8e6d4-200">passport number</span><span class="sxs-lookup"><span data-stu-id="8e6d4-200">passport number</span></span>  <br/> <span data-ttu-id="8e6d4-201">塞浦路斯护照号码</span><span class="sxs-lookup"><span data-stu-id="8e6d4-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="8e6d4-202">护照号</span><span class="sxs-lookup"><span data-stu-id="8e6d4-202">passport no</span></span>  <br/> <span data-ttu-id="8e6d4-203">αριθμόδιαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="8e6d4-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="8e6d4-204">捷克共和国</span><span class="sxs-lookup"><span data-stu-id="8e6d4-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="8e6d4-205">格式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-205">Format</span></span>

<span data-ttu-id="8e6d4-206">8位数, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8e6d4-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8e6d4-207">模式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-207">Pattern</span></span>

<span data-ttu-id="8e6d4-208">8位数, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8e6d4-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8e6d4-209">校验和</span><span class="sxs-lookup"><span data-stu-id="8e6d4-209">Checksum</span></span>

<span data-ttu-id="8e6d4-210">否</span><span class="sxs-lookup"><span data-stu-id="8e6d4-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8e6d4-211">定义</span><span class="sxs-lookup"><span data-stu-id="8e6d4-211">Definition</span></span>

<span data-ttu-id="8e6d4-212">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8e6d4-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8e6d4-213">正则表达式`Regex_czech_republic_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8e6d4-214">找到了中`Keywords_czech_republic_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8e6d4-215">关键字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-215">Keywords</span></span>

<span data-ttu-id="8e6d4-216">| |</span><span class="sxs-lookup"><span data-stu-id="8e6d4-216"></span></span>
|<span data-ttu-id="8e6d4-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8e6d4-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8e6d4-218">passport number</span><span class="sxs-lookup"><span data-stu-id="8e6d4-218">passport number</span></span>  <br/> <span data-ttu-id="8e6d4-219">捷克语护照号码</span><span class="sxs-lookup"><span data-stu-id="8e6d4-219">czech passport number</span></span>  <br/> <span data-ttu-id="8e6d4-220">护照号</span><span class="sxs-lookup"><span data-stu-id="8e6d4-220">passport no</span></span>  <br/> <span data-ttu-id="8e6d4-221">cestovní pas</span><span class="sxs-lookup"><span data-stu-id="8e6d4-221">cestovní pas</span></span>  <br/> <span data-ttu-id="8e6d4-222">pas</span><span class="sxs-lookup"><span data-stu-id="8e6d4-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="8e6d4-223">丹麦</span><span class="sxs-lookup"><span data-stu-id="8e6d4-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="8e6d4-224">格式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-224">Format</span></span>

<span data-ttu-id="8e6d4-225">9个数字, 不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="8e6d4-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8e6d4-226">模式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-226">Pattern</span></span>

 <span data-ttu-id="8e6d4-227">九个数字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="8e6d4-228">校验和</span><span class="sxs-lookup"><span data-stu-id="8e6d4-228">Checksum</span></span>

<span data-ttu-id="8e6d4-229">否</span><span class="sxs-lookup"><span data-stu-id="8e6d4-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8e6d4-230">定义</span><span class="sxs-lookup"><span data-stu-id="8e6d4-230">Definition</span></span>

<span data-ttu-id="8e6d4-231">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8e6d4-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8e6d4-232">正则表达式`Regex_denmark_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8e6d4-233">找到了中`Keywords_denmark_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8e6d4-234">关键字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-234">Keywords</span></span>

<span data-ttu-id="8e6d4-235">| |</span><span class="sxs-lookup"><span data-stu-id="8e6d4-235"></span></span>
|<span data-ttu-id="8e6d4-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8e6d4-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8e6d4-237">passport number</span><span class="sxs-lookup"><span data-stu-id="8e6d4-237">passport number</span></span>  <br/> <span data-ttu-id="8e6d4-238">丹麦护照号码</span><span class="sxs-lookup"><span data-stu-id="8e6d4-238">danish passport number</span></span>  <br/> <span data-ttu-id="8e6d4-239">护照号</span><span class="sxs-lookup"><span data-stu-id="8e6d4-239">passport no</span></span>  <br/> <span data-ttu-id="8e6d4-240">pas</span><span class="sxs-lookup"><span data-stu-id="8e6d4-240">pas</span></span>  <br/> <span data-ttu-id="8e6d4-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="8e6d4-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="8e6d4-242">爱沙尼亚</span><span class="sxs-lookup"><span data-stu-id="8e6d4-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="8e6d4-243">格式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-243">Format</span></span>

<span data-ttu-id="8e6d4-244">一个字母后跟七个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8e6d4-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8e6d4-245">模式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-245">Pattern</span></span>

<span data-ttu-id="8e6d4-246">一个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8e6d4-247">校验和</span><span class="sxs-lookup"><span data-stu-id="8e6d4-247">Checksum</span></span>

<span data-ttu-id="8e6d4-248">否</span><span class="sxs-lookup"><span data-stu-id="8e6d4-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8e6d4-249">定义</span><span class="sxs-lookup"><span data-stu-id="8e6d4-249">Definition</span></span>

<span data-ttu-id="8e6d4-250">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8e6d4-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8e6d4-251">正则表达式`Regex_estonia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8e6d4-252">找到了中`Keywords_estonia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8e6d4-253">关键字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-253">Keywords</span></span>

<span data-ttu-id="8e6d4-254">| |</span><span class="sxs-lookup"><span data-stu-id="8e6d4-254"></span></span>
|<span data-ttu-id="8e6d4-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8e6d4-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8e6d4-256">passport number</span><span class="sxs-lookup"><span data-stu-id="8e6d4-256">passport number</span></span>  <br/> <span data-ttu-id="8e6d4-257">爱沙尼亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="8e6d4-257">estonian passport number</span></span>  <br/> <span data-ttu-id="8e6d4-258">护照号</span><span class="sxs-lookup"><span data-stu-id="8e6d4-258">passport no</span></span>  <br/> <span data-ttu-id="8e6d4-259">eesti kodaniku pass</span><span class="sxs-lookup"><span data-stu-id="8e6d4-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="8e6d4-260">芬兰</span><span class="sxs-lookup"><span data-stu-id="8e6d4-260">Finland</span></span>

<span data-ttu-id="8e6d4-261">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "芬兰护照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="8e6d4-262">法国</span><span class="sxs-lookup"><span data-stu-id="8e6d4-262">France</span></span>

<span data-ttu-id="8e6d4-263">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "法国护照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="8e6d4-264">德国</span><span class="sxs-lookup"><span data-stu-id="8e6d4-264">Germany</span></span>

<span data-ttu-id="8e6d4-265">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "德国护照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="8e6d4-266">希腊</span><span class="sxs-lookup"><span data-stu-id="8e6d4-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="8e6d4-267">格式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-267">Format</span></span>

<span data-ttu-id="8e6d4-268">两个字母后跟七个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8e6d4-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8e6d4-269">模式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-269">Pattern</span></span>

<span data-ttu-id="8e6d4-270">两个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8e6d4-271">校验和</span><span class="sxs-lookup"><span data-stu-id="8e6d4-271">Checksum</span></span>

<span data-ttu-id="8e6d4-272">否</span><span class="sxs-lookup"><span data-stu-id="8e6d4-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8e6d4-273">定义</span><span class="sxs-lookup"><span data-stu-id="8e6d4-273">Definition</span></span>

<span data-ttu-id="8e6d4-274">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8e6d4-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8e6d4-275">正则表达式`Regex_greece_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8e6d4-276">找到了中`Keywords_greece_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8e6d4-277">关键字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-277">Keywords</span></span>

<span data-ttu-id="8e6d4-278">| |</span><span class="sxs-lookup"><span data-stu-id="8e6d4-278"></span></span>
|<span data-ttu-id="8e6d4-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8e6d4-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8e6d4-280">passport number</span><span class="sxs-lookup"><span data-stu-id="8e6d4-280">passport number</span></span>  <br/> <span data-ttu-id="8e6d4-281">希腊护照号码</span><span class="sxs-lookup"><span data-stu-id="8e6d4-281">greek passport number</span></span>  <br/> <span data-ttu-id="8e6d4-282">护照号</span><span class="sxs-lookup"><span data-stu-id="8e6d4-282">passport no</span></span>  <br/> <span data-ttu-id="8e6d4-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="8e6d4-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="8e6d4-284">匈牙利</span><span class="sxs-lookup"><span data-stu-id="8e6d4-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="8e6d4-285">格式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-285">Format</span></span>

<span data-ttu-id="8e6d4-286">两个字母后跟6个或7个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8e6d4-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8e6d4-287">模式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-287">Pattern</span></span>

<span data-ttu-id="8e6d4-288">两个字母后跟六个或七个数字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8e6d4-289">校验和</span><span class="sxs-lookup"><span data-stu-id="8e6d4-289">Checksum</span></span>

<span data-ttu-id="8e6d4-290">否</span><span class="sxs-lookup"><span data-stu-id="8e6d4-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8e6d4-291">定义</span><span class="sxs-lookup"><span data-stu-id="8e6d4-291">Definition</span></span>

<span data-ttu-id="8e6d4-292">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8e6d4-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8e6d4-293">正则表达式`Regex_hungary_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8e6d4-294">找到了中`Keywords_hungary_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8e6d4-295">关键字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-295">Keywords</span></span>

<span data-ttu-id="8e6d4-296">| |</span><span class="sxs-lookup"><span data-stu-id="8e6d4-296"></span></span>
|<span data-ttu-id="8e6d4-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8e6d4-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8e6d4-298">passport number</span><span class="sxs-lookup"><span data-stu-id="8e6d4-298">passport number</span></span>  <br/> <span data-ttu-id="8e6d4-299">匈牙利语护照号码</span><span class="sxs-lookup"><span data-stu-id="8e6d4-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="8e6d4-300">护照号</span><span class="sxs-lookup"><span data-stu-id="8e6d4-300">passport no</span></span>  <br/> <span data-ttu-id="8e6d4-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="8e6d4-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="8e6d4-302">Ireland</span><span class="sxs-lookup"><span data-stu-id="8e6d4-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="8e6d4-303">格式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-303">Format</span></span>

<span data-ttu-id="8e6d4-304">两个字母或数字后跟七个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8e6d4-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8e6d4-305">模式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-305">Pattern</span></span>

<span data-ttu-id="8e6d4-306">两个字母或数字, 后跟七个数字:</span><span class="sxs-lookup"><span data-stu-id="8e6d4-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="8e6d4-307">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="8e6d4-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="8e6d4-308">七个数字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8e6d4-309">校验和</span><span class="sxs-lookup"><span data-stu-id="8e6d4-309">Checksum</span></span>

<span data-ttu-id="8e6d4-310">否</span><span class="sxs-lookup"><span data-stu-id="8e6d4-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8e6d4-311">定义</span><span class="sxs-lookup"><span data-stu-id="8e6d4-311">Definition</span></span>

<span data-ttu-id="8e6d4-312">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8e6d4-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8e6d4-313">正则表达式`Regex_ireland_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8e6d4-314">找到了中`Keywords_ireland_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8e6d4-315">关键字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-315">Keywords</span></span>

<span data-ttu-id="8e6d4-316">| |</span><span class="sxs-lookup"><span data-stu-id="8e6d4-316"></span></span>
|<span data-ttu-id="8e6d4-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8e6d4-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8e6d4-318">passport number</span><span class="sxs-lookup"><span data-stu-id="8e6d4-318">passport number</span></span>  <br/> <span data-ttu-id="8e6d4-319">爱尔兰护照号码</span><span class="sxs-lookup"><span data-stu-id="8e6d4-319">irish passport number</span></span>  <br/> <span data-ttu-id="8e6d4-320">护照号</span><span class="sxs-lookup"><span data-stu-id="8e6d4-320">passport no</span></span>  <br/> <span data-ttu-id="8e6d4-321">pas</span><span class="sxs-lookup"><span data-stu-id="8e6d4-321">pas</span></span>  <br/> <span data-ttu-id="8e6d4-322">登记卡</span><span class="sxs-lookup"><span data-stu-id="8e6d4-322">passport</span></span>  <br/> <span data-ttu-id="8e6d4-323">passeport</span><span class="sxs-lookup"><span data-stu-id="8e6d4-323">passeport</span></span>  <br/> <span data-ttu-id="8e6d4-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="8e6d4-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="8e6d4-325">意大利</span><span class="sxs-lookup"><span data-stu-id="8e6d4-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="8e6d4-326">格式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-326">Format</span></span>

<span data-ttu-id="8e6d4-327">两个字母或数字后跟七个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8e6d4-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8e6d4-328">模式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-328">Pattern</span></span>

<span data-ttu-id="8e6d4-329">两个字母或数字, 后跟七个数字:</span><span class="sxs-lookup"><span data-stu-id="8e6d4-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="8e6d4-330">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="8e6d4-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="8e6d4-331">七个数字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8e6d4-332">校验和</span><span class="sxs-lookup"><span data-stu-id="8e6d4-332">Checksum</span></span>

<span data-ttu-id="8e6d4-333">不适用</span><span class="sxs-lookup"><span data-stu-id="8e6d4-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8e6d4-334">定义</span><span class="sxs-lookup"><span data-stu-id="8e6d4-334">Definition</span></span>

<span data-ttu-id="8e6d4-335">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8e6d4-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8e6d4-336">正则表达式`Regex_italy_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8e6d4-337">找到了中`Keywords_italy_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8e6d4-338">关键字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-338">Keywords</span></span>

<span data-ttu-id="8e6d4-339">| |</span><span class="sxs-lookup"><span data-stu-id="8e6d4-339"></span></span>
|<span data-ttu-id="8e6d4-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8e6d4-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8e6d4-341">意大利护照号码</span><span class="sxs-lookup"><span data-stu-id="8e6d4-341">italian passport number</span></span>  <br/> <span data-ttu-id="8e6d4-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="8e6d4-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="8e6d4-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="8e6d4-343">passaporto</span></span>  <br/> <span data-ttu-id="8e6d4-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="8e6d4-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="8e6d4-345">passport number</span><span class="sxs-lookup"><span data-stu-id="8e6d4-345">passport number</span></span>  <br/> <span data-ttu-id="8e6d4-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="8e6d4-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="8e6d4-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="8e6d4-347">passaporto numero</span></span>  <br/> <span data-ttu-id="8e6d4-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="8e6d4-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="8e6d4-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="8e6d4-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="8e6d4-350">拉脱维亚</span><span class="sxs-lookup"><span data-stu-id="8e6d4-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="8e6d4-351">格式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-351">Format</span></span>

<span data-ttu-id="8e6d4-352">两个字母或数字后跟七个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8e6d4-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8e6d4-353">模式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-353">Pattern</span></span>

<span data-ttu-id="8e6d4-354">两个字母或数字, 后跟七个数字:</span><span class="sxs-lookup"><span data-stu-id="8e6d4-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="8e6d4-355">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="8e6d4-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="8e6d4-356">七个数字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8e6d4-357">校验和</span><span class="sxs-lookup"><span data-stu-id="8e6d4-357">Checksum</span></span>

<span data-ttu-id="8e6d4-358">否</span><span class="sxs-lookup"><span data-stu-id="8e6d4-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8e6d4-359">定义</span><span class="sxs-lookup"><span data-stu-id="8e6d4-359">Definition</span></span>

<span data-ttu-id="8e6d4-360">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8e6d4-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8e6d4-361">正则表达式`Regex_latvia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8e6d4-362">找到了中`Keywords_latvia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8e6d4-363">关键字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-363">Keywords</span></span>

<span data-ttu-id="8e6d4-364">| |</span><span class="sxs-lookup"><span data-stu-id="8e6d4-364"></span></span>
|<span data-ttu-id="8e6d4-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8e6d4-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8e6d4-366">passport number</span><span class="sxs-lookup"><span data-stu-id="8e6d4-366">passport number</span></span>  <br/> <span data-ttu-id="8e6d4-367">拉脱维亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="8e6d4-367">latvian passport number</span></span>  <br/> <span data-ttu-id="8e6d4-368">护照号</span><span class="sxs-lookup"><span data-stu-id="8e6d4-368">passport no</span></span>  <br/> <span data-ttu-id="8e6d4-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="8e6d4-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="8e6d4-370">立陶宛</span><span class="sxs-lookup"><span data-stu-id="8e6d4-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="8e6d4-371">格式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-371">Format</span></span>

<span data-ttu-id="8e6d4-372">八个数字或字母不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8e6d4-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8e6d4-373">模式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-373">Pattern</span></span>

<span data-ttu-id="8e6d4-374">八个数字或字母 (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="8e6d4-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8e6d4-375">校验和</span><span class="sxs-lookup"><span data-stu-id="8e6d4-375">Checksum</span></span>

<span data-ttu-id="8e6d4-376">不适用</span><span class="sxs-lookup"><span data-stu-id="8e6d4-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8e6d4-377">定义</span><span class="sxs-lookup"><span data-stu-id="8e6d4-377">Definition</span></span>

<span data-ttu-id="8e6d4-378">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8e6d4-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8e6d4-379">正则表达式`Regex_lithuania_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8e6d4-380">找到了中`Keywords_lithuania_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8e6d4-381">关键字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-381">Keywords</span></span>

<span data-ttu-id="8e6d4-382">| |</span><span class="sxs-lookup"><span data-stu-id="8e6d4-382"></span></span>
|<span data-ttu-id="8e6d4-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8e6d4-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8e6d4-384">passport number</span><span class="sxs-lookup"><span data-stu-id="8e6d4-384">passport number</span></span>  <br/> <span data-ttu-id="8e6d4-385">lithunian 护照号码</span><span class="sxs-lookup"><span data-stu-id="8e6d4-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="8e6d4-386">护照号</span><span class="sxs-lookup"><span data-stu-id="8e6d4-386">passport no</span></span>  <br/> <span data-ttu-id="8e6d4-387">paso numeris</span><span class="sxs-lookup"><span data-stu-id="8e6d4-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="8e6d4-388">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="8e6d4-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="8e6d4-389">格式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-389">Format</span></span>

<span data-ttu-id="8e6d4-390">八个数字或字母不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8e6d4-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8e6d4-391">模式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-391">Pattern</span></span>

<span data-ttu-id="8e6d4-392">八个数字或字母 (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="8e6d4-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8e6d4-393">校验和</span><span class="sxs-lookup"><span data-stu-id="8e6d4-393">Checksum</span></span>

<span data-ttu-id="8e6d4-394">否</span><span class="sxs-lookup"><span data-stu-id="8e6d4-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8e6d4-395">定义</span><span class="sxs-lookup"><span data-stu-id="8e6d4-395">Definition</span></span>

<span data-ttu-id="8e6d4-396">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8e6d4-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8e6d4-397">正则表达式`Regex_nation_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8e6d4-398">找到了中`Keywords_nation_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8e6d4-399">关键字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-399">Keywords</span></span>

<span data-ttu-id="8e6d4-400">| |</span><span class="sxs-lookup"><span data-stu-id="8e6d4-400"></span></span>
|<span data-ttu-id="8e6d4-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8e6d4-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8e6d4-402">passport number</span><span class="sxs-lookup"><span data-stu-id="8e6d4-402">passport number</span></span>  <br/> <span data-ttu-id="8e6d4-403">拉脱维亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="8e6d4-403">latvian passport number</span></span>  <br/> <span data-ttu-id="8e6d4-404">护照号</span><span class="sxs-lookup"><span data-stu-id="8e6d4-404">passport no</span></span>  <br/> <span data-ttu-id="8e6d4-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="8e6d4-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="8e6d4-406">Malta（马耳他）</span><span class="sxs-lookup"><span data-stu-id="8e6d4-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="8e6d4-407">格式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-407">Format</span></span>

<span data-ttu-id="8e6d4-408">七位数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8e6d4-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8e6d4-409">模式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-409">Pattern</span></span>

 <span data-ttu-id="8e6d4-410">七个数字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="8e6d4-411">校验和</span><span class="sxs-lookup"><span data-stu-id="8e6d4-411">Checksum</span></span>

<span data-ttu-id="8e6d4-412">否</span><span class="sxs-lookup"><span data-stu-id="8e6d4-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8e6d4-413">定义</span><span class="sxs-lookup"><span data-stu-id="8e6d4-413">Definition</span></span>

<span data-ttu-id="8e6d4-414">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8e6d4-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8e6d4-415">正则表达式`Regex_malta_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8e6d4-416">找到了中`Keywords_malta_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8e6d4-417">关键字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-417">Keywords</span></span>

<span data-ttu-id="8e6d4-418">| |</span><span class="sxs-lookup"><span data-stu-id="8e6d4-418"></span></span>
|<span data-ttu-id="8e6d4-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8e6d4-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8e6d4-420">passport number</span><span class="sxs-lookup"><span data-stu-id="8e6d4-420">passport number</span></span>  <br/> <span data-ttu-id="8e6d4-421">马耳他护照号码</span><span class="sxs-lookup"><span data-stu-id="8e6d4-421">maltese passport number</span></span>  <br/> <span data-ttu-id="8e6d4-422">护照号</span><span class="sxs-lookup"><span data-stu-id="8e6d4-422">passport no</span></span>  <br/> <span data-ttu-id="8e6d4-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="8e6d4-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="8e6d4-424">荷兰</span><span class="sxs-lookup"><span data-stu-id="8e6d4-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="8e6d4-425">格式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-425">Format</span></span>

<span data-ttu-id="8e6d4-426">九个字母或数字, 不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8e6d4-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8e6d4-427">模式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-427">Pattern</span></span>

<span data-ttu-id="8e6d4-428">九个字母或数字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8e6d4-429">校验和</span><span class="sxs-lookup"><span data-stu-id="8e6d4-429">Checksum</span></span>

<span data-ttu-id="8e6d4-430">不适用</span><span class="sxs-lookup"><span data-stu-id="8e6d4-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8e6d4-431">定义</span><span class="sxs-lookup"><span data-stu-id="8e6d4-431">Definition</span></span>

<span data-ttu-id="8e6d4-432">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8e6d4-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8e6d4-433">正则表达式`Regex_netherlands_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8e6d4-434">找到了中`Keywords_netherlands_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8e6d4-435">关键字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-435">Keywords</span></span>

<span data-ttu-id="8e6d4-436">| |</span><span class="sxs-lookup"><span data-stu-id="8e6d4-436"></span></span>
|<span data-ttu-id="8e6d4-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8e6d4-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8e6d4-438">荷兰护照号码</span><span class="sxs-lookup"><span data-stu-id="8e6d4-438">dutch passport number</span></span>  <br/> <span data-ttu-id="8e6d4-439">passport number</span><span class="sxs-lookup"><span data-stu-id="8e6d4-439">passport number</span></span>  <br/> <span data-ttu-id="8e6d4-440">荷兰护照号码</span><span class="sxs-lookup"><span data-stu-id="8e6d4-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="8e6d4-441">nederlanden paspoort nummer</span><span class="sxs-lookup"><span data-stu-id="8e6d4-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="8e6d4-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="8e6d4-442">paspoort</span></span>  <br/> <span data-ttu-id="8e6d4-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="8e6d4-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="8e6d4-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="8e6d4-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="8e6d4-445">波兰</span><span class="sxs-lookup"><span data-stu-id="8e6d4-445">Poland</span></span>

<span data-ttu-id="8e6d4-446">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "波兰 Passport 号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="8e6d4-447">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="8e6d4-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="8e6d4-448">格式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-448">Format</span></span>

<span data-ttu-id="8e6d4-449">一个字母后跟六个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8e6d4-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8e6d4-450">模式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-450">Pattern</span></span>

<span data-ttu-id="8e6d4-451">一个字母后跟六个数字:</span><span class="sxs-lookup"><span data-stu-id="8e6d4-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="8e6d4-452">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="8e6d4-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="8e6d4-453">六个数字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8e6d4-454">校验和</span><span class="sxs-lookup"><span data-stu-id="8e6d4-454">Checksum</span></span>

<span data-ttu-id="8e6d4-455">否</span><span class="sxs-lookup"><span data-stu-id="8e6d4-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8e6d4-456">定义</span><span class="sxs-lookup"><span data-stu-id="8e6d4-456">Definition</span></span>

<span data-ttu-id="8e6d4-457">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8e6d4-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8e6d4-458">正则表达式`Regex_portugal_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8e6d4-459">找到了中`Keywords_portugal_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8e6d4-460">关键字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-460">Keywords</span></span>

<span data-ttu-id="8e6d4-461">| |</span><span class="sxs-lookup"><span data-stu-id="8e6d4-461"></span></span>
|<span data-ttu-id="8e6d4-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8e6d4-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8e6d4-463">passport number</span><span class="sxs-lookup"><span data-stu-id="8e6d4-463">passport number</span></span>  <br/> <span data-ttu-id="8e6d4-464">葡萄牙语护照号码</span><span class="sxs-lookup"><span data-stu-id="8e6d4-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="8e6d4-465">护照号</span><span class="sxs-lookup"><span data-stu-id="8e6d4-465">passport no</span></span>  <br/> <span data-ttu-id="8e6d4-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="8e6d4-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="8e6d4-467">罗马尼亚</span><span class="sxs-lookup"><span data-stu-id="8e6d4-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="8e6d4-468">格式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-468">Format</span></span>

<span data-ttu-id="8e6d4-469">八个或9个数字, 不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="8e6d4-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8e6d4-470">模式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-470">Pattern</span></span>

<span data-ttu-id="8e6d4-471">8或9个数字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8e6d4-472">校验和</span><span class="sxs-lookup"><span data-stu-id="8e6d4-472">Checksum</span></span>

<span data-ttu-id="8e6d4-473">否</span><span class="sxs-lookup"><span data-stu-id="8e6d4-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8e6d4-474">定义</span><span class="sxs-lookup"><span data-stu-id="8e6d4-474">Definition</span></span>

<span data-ttu-id="8e6d4-475">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8e6d4-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8e6d4-476">正则表达式`Regex_romania_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8e6d4-477">找到了中`Keywords_romania_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8e6d4-478">关键字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-478">Keywords</span></span>

<span data-ttu-id="8e6d4-479">| |</span><span class="sxs-lookup"><span data-stu-id="8e6d4-479"></span></span>
|<span data-ttu-id="8e6d4-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8e6d4-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8e6d4-481">passport number</span><span class="sxs-lookup"><span data-stu-id="8e6d4-481">passport number</span></span>  <br/> <span data-ttu-id="8e6d4-482">罗马尼亚护照号码</span><span class="sxs-lookup"><span data-stu-id="8e6d4-482">romanian passport number</span></span>  <br/> <span data-ttu-id="8e6d4-483">护照号</span><span class="sxs-lookup"><span data-stu-id="8e6d4-483">passport no</span></span>  <br/> <span data-ttu-id="8e6d4-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="8e6d4-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="8e6d4-485">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="8e6d4-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="8e6d4-486">格式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-486">Format</span></span>

<span data-ttu-id="8e6d4-487">一个数字或字母后跟七个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8e6d4-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8e6d4-488">模式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-488">Pattern</span></span>

<span data-ttu-id="8e6d4-489">一个数字或字母 (不区分大小写) 后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8e6d4-490">校验和</span><span class="sxs-lookup"><span data-stu-id="8e6d4-490">Checksum</span></span>

<span data-ttu-id="8e6d4-491">否</span><span class="sxs-lookup"><span data-stu-id="8e6d4-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8e6d4-492">定义</span><span class="sxs-lookup"><span data-stu-id="8e6d4-492">Definition</span></span>

<span data-ttu-id="8e6d4-493">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8e6d4-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8e6d4-494">正则表达式`Regex_slovakia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8e6d4-495">找到了中`Keywords_slovakia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8e6d4-496">关键字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-496">Keywords</span></span>

<span data-ttu-id="8e6d4-497">| |</span><span class="sxs-lookup"><span data-stu-id="8e6d4-497"></span></span>
|<span data-ttu-id="8e6d4-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8e6d4-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8e6d4-499">passport number</span><span class="sxs-lookup"><span data-stu-id="8e6d4-499">passport number</span></span>  <br/> <span data-ttu-id="8e6d4-500">斯洛伐克护照号码</span><span class="sxs-lookup"><span data-stu-id="8e6d4-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="8e6d4-501">护照号</span><span class="sxs-lookup"><span data-stu-id="8e6d4-501">passport no</span></span>  <br/> <span data-ttu-id="8e6d4-502">číslo pasu</span><span class="sxs-lookup"><span data-stu-id="8e6d4-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="8e6d4-503">斯洛文尼亚</span><span class="sxs-lookup"><span data-stu-id="8e6d4-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="8e6d4-504">格式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-504">Format</span></span>

<span data-ttu-id="8e6d4-505">两个字母后跟七个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8e6d4-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8e6d4-506">模式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-506">Pattern</span></span>

<span data-ttu-id="8e6d4-507">两个字母后跟七个数字:</span><span class="sxs-lookup"><span data-stu-id="8e6d4-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="8e6d4-508">字母 "P"</span><span class="sxs-lookup"><span data-stu-id="8e6d4-508">The letter "P"</span></span>
    
- <span data-ttu-id="8e6d4-509">一个大写字母</span><span class="sxs-lookup"><span data-stu-id="8e6d4-509">One uppercase letter</span></span>
    
- <span data-ttu-id="8e6d4-510">七个数字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8e6d4-511">校验和</span><span class="sxs-lookup"><span data-stu-id="8e6d4-511">Checksum</span></span>

<span data-ttu-id="8e6d4-512">否</span><span class="sxs-lookup"><span data-stu-id="8e6d4-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8e6d4-513">定义</span><span class="sxs-lookup"><span data-stu-id="8e6d4-513">Definition</span></span>

<span data-ttu-id="8e6d4-514">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8e6d4-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8e6d4-515">正则表达式`Regex_slovenia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8e6d4-516">找到了中`Keywords_slovenia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8e6d4-517">关键字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-517">Keywords</span></span>

<span data-ttu-id="8e6d4-518">| |</span><span class="sxs-lookup"><span data-stu-id="8e6d4-518"></span></span>
|<span data-ttu-id="8e6d4-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8e6d4-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8e6d4-520">passport number</span><span class="sxs-lookup"><span data-stu-id="8e6d4-520">passport number</span></span>  <br/> <span data-ttu-id="8e6d4-521">斯洛文尼亚护照号码</span><span class="sxs-lookup"><span data-stu-id="8e6d4-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="8e6d4-522">护照号</span><span class="sxs-lookup"><span data-stu-id="8e6d4-522">passport no</span></span>  <br/> <span data-ttu-id="8e6d4-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="8e6d4-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="8e6d4-524">西班牙</span><span class="sxs-lookup"><span data-stu-id="8e6d4-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="8e6d4-525">格式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-525">Format</span></span>

<span data-ttu-id="8e6d4-526">八个或九个字符的字母和数字的组合, 不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8e6d4-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8e6d4-527">模式</span><span class="sxs-lookup"><span data-stu-id="8e6d4-527">Pattern</span></span>

<span data-ttu-id="8e6d4-528">字母和数字的八个或九个字符的组合:</span><span class="sxs-lookup"><span data-stu-id="8e6d4-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="8e6d4-529">两位数字或字母</span><span class="sxs-lookup"><span data-stu-id="8e6d4-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="8e6d4-530">一个数字或字母 (可选)</span><span class="sxs-lookup"><span data-stu-id="8e6d4-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="8e6d4-531">六个数字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8e6d4-532">校验和</span><span class="sxs-lookup"><span data-stu-id="8e6d4-532">Checksum</span></span>

<span data-ttu-id="8e6d4-533">不适用</span><span class="sxs-lookup"><span data-stu-id="8e6d4-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8e6d4-534">定义</span><span class="sxs-lookup"><span data-stu-id="8e6d4-534">Definition</span></span>

<span data-ttu-id="8e6d4-535">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8e6d4-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8e6d4-536">正则表达式`Regex_spain_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8e6d4-537">找到了中`Keywords_spain_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8e6d4-538">关键字</span><span class="sxs-lookup"><span data-stu-id="8e6d4-538">Keywords</span></span>

<span data-ttu-id="8e6d4-539">| |</span><span class="sxs-lookup"><span data-stu-id="8e6d4-539"></span></span>
|<span data-ttu-id="8e6d4-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8e6d4-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8e6d4-541">登记卡</span><span class="sxs-lookup"><span data-stu-id="8e6d4-541">passport</span></span>  <br/> <span data-ttu-id="8e6d4-542">西班牙护照</span><span class="sxs-lookup"><span data-stu-id="8e6d4-542">spain passport</span></span>  <br/> <span data-ttu-id="8e6d4-543">护照书籍</span><span class="sxs-lookup"><span data-stu-id="8e6d4-543">passport book</span></span>  <br/> <span data-ttu-id="8e6d4-544">passport number</span><span class="sxs-lookup"><span data-stu-id="8e6d4-544">passport number</span></span>  <br/> <span data-ttu-id="8e6d4-545">护照号</span><span class="sxs-lookup"><span data-stu-id="8e6d4-545">passport no</span></span>  <br/> <span data-ttu-id="8e6d4-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="8e6d4-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="8e6d4-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="8e6d4-547">número pasaporte</span></span>  <br/> <span data-ttu-id="8e6d4-548">西班牙 pasaporte</span><span class="sxs-lookup"><span data-stu-id="8e6d4-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="8e6d4-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="8e6d4-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="8e6d4-550">瑞典</span><span class="sxs-lookup"><span data-stu-id="8e6d4-550">Sweden</span></span>

<span data-ttu-id="8e6d4-551">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "瑞典护照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="8e6d4-552">英国</span><span class="sxs-lookup"><span data-stu-id="8e6d4-552">UK</span></span>

<span data-ttu-id="8e6d4-553">有关详细信息, 请参阅 "美国/英国" 一节。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="8e6d4-554">"Passport 号码", 在[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中。</span><span class="sxs-lookup"><span data-stu-id="8e6d4-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8e6d4-555">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e6d4-555">See also</span></span>

[<span data-ttu-id="8e6d4-556">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="8e6d4-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

