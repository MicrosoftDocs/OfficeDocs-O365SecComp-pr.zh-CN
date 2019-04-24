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
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32256820"
---
# <a name="eu-passport-number"></a><span data-ttu-id="3c569-104">EU 护照号码</span><span class="sxs-lookup"><span data-stu-id="3c569-104">EU Passport Number</span></span>

<span data-ttu-id="3c569-105">本主题介绍当数据丢失防护 (DLP) 策略检测到欧盟护照号敏感信息类型时, 应查找什么内容。</span><span class="sxs-lookup"><span data-stu-id="3c569-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="3c569-106">此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。</span><span class="sxs-lookup"><span data-stu-id="3c569-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="3c569-107">奥地利</span><span class="sxs-lookup"><span data-stu-id="3c569-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="3c569-108">Format</span><span class="sxs-lookup"><span data-stu-id="3c569-108">Format</span></span>

<span data-ttu-id="3c569-109">一个字母后跟一个可选空格和七个数字</span><span class="sxs-lookup"><span data-stu-id="3c569-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c569-110">模式</span><span class="sxs-lookup"><span data-stu-id="3c569-110">Pattern</span></span>

<span data-ttu-id="3c569-111">一个字母、七个数字和一个空格的组合:</span><span class="sxs-lookup"><span data-stu-id="3c569-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="3c569-112">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="3c569-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="3c569-113">一个空格 (可选)</span><span class="sxs-lookup"><span data-stu-id="3c569-113">One space (optional)</span></span>
    
- <span data-ttu-id="3c569-114">七个数字</span><span class="sxs-lookup"><span data-stu-id="3c569-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3c569-115">校验和</span><span class="sxs-lookup"><span data-stu-id="3c569-115">Checksum</span></span>

<span data-ttu-id="3c569-116">不适用</span><span class="sxs-lookup"><span data-stu-id="3c569-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c569-117">定义</span><span class="sxs-lookup"><span data-stu-id="3c569-117">Definition</span></span>

<span data-ttu-id="3c569-118">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c569-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c569-119">正则表达式`Regex_austria_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c569-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c569-120">找到了中`Keywords_austria_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c569-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c569-121">关键字</span><span class="sxs-lookup"><span data-stu-id="3c569-121">Keywords</span></span>

<span data-ttu-id="3c569-122">| |</span><span class="sxs-lookup"><span data-stu-id="3c569-122"></span></span>
|<span data-ttu-id="3c569-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3c569-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3c569-124">passport number</span><span class="sxs-lookup"><span data-stu-id="3c569-124">passport number</span></span>  <br/> <span data-ttu-id="3c569-125">奥地利护照号码</span><span class="sxs-lookup"><span data-stu-id="3c569-125">austrian passport number</span></span>  <br/> <span data-ttu-id="3c569-126">护照号</span><span class="sxs-lookup"><span data-stu-id="3c569-126">passport no</span></span>  <br/> <span data-ttu-id="3c569-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="3c569-127">reisepass</span></span>  <br/> <span data-ttu-id="3c569-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="3c569-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="3c569-129">比利时</span><span class="sxs-lookup"><span data-stu-id="3c569-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="3c569-130">Format</span><span class="sxs-lookup"><span data-stu-id="3c569-130">Format</span></span>

<span data-ttu-id="3c569-131">两个字母后跟六个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3c569-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c569-132">模式</span><span class="sxs-lookup"><span data-stu-id="3c569-132">Pattern</span></span>

<span data-ttu-id="3c569-133">两个字母, 后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="3c569-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3c569-134">校验和</span><span class="sxs-lookup"><span data-stu-id="3c569-134">Checksum</span></span>

<span data-ttu-id="3c569-135">不适用</span><span class="sxs-lookup"><span data-stu-id="3c569-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c569-136">定义</span><span class="sxs-lookup"><span data-stu-id="3c569-136">Definition</span></span>

<span data-ttu-id="3c569-137">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c569-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c569-138">正则表达式`Regex_belgium_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c569-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c569-139">找到了中`Keywords_belgium_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c569-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c569-140">关键字</span><span class="sxs-lookup"><span data-stu-id="3c569-140">Keywords</span></span>

<span data-ttu-id="3c569-141">| |</span><span class="sxs-lookup"><span data-stu-id="3c569-141"></span></span>
|<span data-ttu-id="3c569-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3c569-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3c569-143">passport number</span><span class="sxs-lookup"><span data-stu-id="3c569-143">passport number</span></span>  <br/> <span data-ttu-id="3c569-144">比利时护照号码</span><span class="sxs-lookup"><span data-stu-id="3c569-144">belgian passport number</span></span>  <br/> <span data-ttu-id="3c569-145">护照号</span><span class="sxs-lookup"><span data-stu-id="3c569-145">passport no</span></span>  <br/> <span data-ttu-id="3c569-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="3c569-146">paspoort</span></span>  <br/> <span data-ttu-id="3c569-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="3c569-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="3c569-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="3c569-148">reisepass kein</span></span>  <br/> <span data-ttu-id="3c569-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="3c569-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="3c569-150">保加利亚语</span><span class="sxs-lookup"><span data-stu-id="3c569-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="3c569-151">Format</span><span class="sxs-lookup"><span data-stu-id="3c569-151">Format</span></span>

<span data-ttu-id="3c569-152">9个数字, 不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="3c569-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c569-153">模式</span><span class="sxs-lookup"><span data-stu-id="3c569-153">Pattern</span></span>

 <span data-ttu-id="3c569-154">九个数字</span><span class="sxs-lookup"><span data-stu-id="3c569-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="3c569-155">校验和</span><span class="sxs-lookup"><span data-stu-id="3c569-155">Checksum</span></span>

<span data-ttu-id="3c569-156">否</span><span class="sxs-lookup"><span data-stu-id="3c569-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c569-157">定义</span><span class="sxs-lookup"><span data-stu-id="3c569-157">Definition</span></span>

<span data-ttu-id="3c569-158">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c569-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c569-159">正则表达式`Regex_bulgaria_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c569-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c569-160">找到了中`Keywords_bulgaria_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c569-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c569-161">关键字</span><span class="sxs-lookup"><span data-stu-id="3c569-161">Keywords</span></span>

<span data-ttu-id="3c569-162">| |</span><span class="sxs-lookup"><span data-stu-id="3c569-162"></span></span>
|<span data-ttu-id="3c569-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3c569-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3c569-164">passport number</span><span class="sxs-lookup"><span data-stu-id="3c569-164">passport number</span></span>  <br/> <span data-ttu-id="3c569-165">保加利亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="3c569-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="3c569-166">护照号</span><span class="sxs-lookup"><span data-stu-id="3c569-166">passport no</span></span>  <br/> <span data-ttu-id="3c569-167">номернапаспорта</span><span class="sxs-lookup"><span data-stu-id="3c569-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="3c569-168">克罗地亚</span><span class="sxs-lookup"><span data-stu-id="3c569-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="3c569-169">Format</span><span class="sxs-lookup"><span data-stu-id="3c569-169">Format</span></span>

<span data-ttu-id="3c569-170">9个数字, 不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="3c569-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c569-171">模式</span><span class="sxs-lookup"><span data-stu-id="3c569-171">Pattern</span></span>

 <span data-ttu-id="3c569-172">九个数字</span><span class="sxs-lookup"><span data-stu-id="3c569-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="3c569-173">校验和</span><span class="sxs-lookup"><span data-stu-id="3c569-173">Checksum</span></span>

<span data-ttu-id="3c569-174">否</span><span class="sxs-lookup"><span data-stu-id="3c569-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c569-175">定义</span><span class="sxs-lookup"><span data-stu-id="3c569-175">Definition</span></span>

<span data-ttu-id="3c569-176">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c569-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c569-177">正则表达式`Regex_croatia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c569-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c569-178">找到了中`Keywords_croatia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c569-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c569-179">关键字</span><span class="sxs-lookup"><span data-stu-id="3c569-179">Keywords</span></span>

<span data-ttu-id="3c569-180">| |</span><span class="sxs-lookup"><span data-stu-id="3c569-180"></span></span>
|<span data-ttu-id="3c569-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3c569-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3c569-182">passport number</span><span class="sxs-lookup"><span data-stu-id="3c569-182">passport number</span></span>  <br/> <span data-ttu-id="3c569-183">克罗地亚护照号码</span><span class="sxs-lookup"><span data-stu-id="3c569-183">croatian passport number</span></span>  <br/> <span data-ttu-id="3c569-184">护照号</span><span class="sxs-lookup"><span data-stu-id="3c569-184">passport no</span></span>  <br/> <span data-ttu-id="3c569-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="3c569-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="3c569-186">塞浦路斯</span><span class="sxs-lookup"><span data-stu-id="3c569-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="3c569-187">Format</span><span class="sxs-lookup"><span data-stu-id="3c569-187">Format</span></span>

<span data-ttu-id="3c569-188">一个字母后跟6-8 个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3c569-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c569-189">模式</span><span class="sxs-lookup"><span data-stu-id="3c569-189">Pattern</span></span>

<span data-ttu-id="3c569-190">一个字母后跟6到8个数字</span><span class="sxs-lookup"><span data-stu-id="3c569-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3c569-191">校验和</span><span class="sxs-lookup"><span data-stu-id="3c569-191">Checksum</span></span>

<span data-ttu-id="3c569-192">否</span><span class="sxs-lookup"><span data-stu-id="3c569-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c569-193">定义</span><span class="sxs-lookup"><span data-stu-id="3c569-193">Definition</span></span>

<span data-ttu-id="3c569-194">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c569-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c569-195">正则表达式`Regex_cyprus_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c569-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c569-196">找到了中`Keywords_cyprus_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c569-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c569-197">关键字</span><span class="sxs-lookup"><span data-stu-id="3c569-197">Keywords</span></span>

<span data-ttu-id="3c569-198">| |</span><span class="sxs-lookup"><span data-stu-id="3c569-198"></span></span>
|<span data-ttu-id="3c569-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3c569-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3c569-200">passport number</span><span class="sxs-lookup"><span data-stu-id="3c569-200">passport number</span></span>  <br/> <span data-ttu-id="3c569-201">塞浦路斯护照号码</span><span class="sxs-lookup"><span data-stu-id="3c569-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="3c569-202">护照号</span><span class="sxs-lookup"><span data-stu-id="3c569-202">passport no</span></span>  <br/> <span data-ttu-id="3c569-203">αριθμόδιαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="3c569-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="3c569-204">捷克共和国</span><span class="sxs-lookup"><span data-stu-id="3c569-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="3c569-205">Format</span><span class="sxs-lookup"><span data-stu-id="3c569-205">Format</span></span>

<span data-ttu-id="3c569-206">8位数, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3c569-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c569-207">模式</span><span class="sxs-lookup"><span data-stu-id="3c569-207">Pattern</span></span>

<span data-ttu-id="3c569-208">8位数, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3c569-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3c569-209">校验和</span><span class="sxs-lookup"><span data-stu-id="3c569-209">Checksum</span></span>

<span data-ttu-id="3c569-210">否</span><span class="sxs-lookup"><span data-stu-id="3c569-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c569-211">定义</span><span class="sxs-lookup"><span data-stu-id="3c569-211">Definition</span></span>

<span data-ttu-id="3c569-212">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c569-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c569-213">正则表达式`Regex_czech_republic_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c569-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c569-214">找到了中`Keywords_czech_republic_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c569-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c569-215">关键字</span><span class="sxs-lookup"><span data-stu-id="3c569-215">Keywords</span></span>

<span data-ttu-id="3c569-216">| |</span><span class="sxs-lookup"><span data-stu-id="3c569-216"></span></span>
|<span data-ttu-id="3c569-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3c569-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3c569-218">passport number</span><span class="sxs-lookup"><span data-stu-id="3c569-218">passport number</span></span>  <br/> <span data-ttu-id="3c569-219">捷克语护照号码</span><span class="sxs-lookup"><span data-stu-id="3c569-219">czech passport number</span></span>  <br/> <span data-ttu-id="3c569-220">护照号</span><span class="sxs-lookup"><span data-stu-id="3c569-220">passport no</span></span>  <br/> <span data-ttu-id="3c569-221">cestovní pas</span><span class="sxs-lookup"><span data-stu-id="3c569-221">cestovní pas</span></span>  <br/> <span data-ttu-id="3c569-222">pas</span><span class="sxs-lookup"><span data-stu-id="3c569-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="3c569-223">丹麦</span><span class="sxs-lookup"><span data-stu-id="3c569-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="3c569-224">Format</span><span class="sxs-lookup"><span data-stu-id="3c569-224">Format</span></span>

<span data-ttu-id="3c569-225">9个数字, 不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="3c569-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c569-226">模式</span><span class="sxs-lookup"><span data-stu-id="3c569-226">Pattern</span></span>

 <span data-ttu-id="3c569-227">九个数字</span><span class="sxs-lookup"><span data-stu-id="3c569-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="3c569-228">校验和</span><span class="sxs-lookup"><span data-stu-id="3c569-228">Checksum</span></span>

<span data-ttu-id="3c569-229">否</span><span class="sxs-lookup"><span data-stu-id="3c569-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c569-230">定义</span><span class="sxs-lookup"><span data-stu-id="3c569-230">Definition</span></span>

<span data-ttu-id="3c569-231">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c569-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c569-232">正则表达式`Regex_denmark_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c569-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c569-233">找到了中`Keywords_denmark_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c569-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c569-234">关键字</span><span class="sxs-lookup"><span data-stu-id="3c569-234">Keywords</span></span>

<span data-ttu-id="3c569-235">| |</span><span class="sxs-lookup"><span data-stu-id="3c569-235"></span></span>
|<span data-ttu-id="3c569-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3c569-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3c569-237">passport number</span><span class="sxs-lookup"><span data-stu-id="3c569-237">passport number</span></span>  <br/> <span data-ttu-id="3c569-238">丹麦护照号码</span><span class="sxs-lookup"><span data-stu-id="3c569-238">danish passport number</span></span>  <br/> <span data-ttu-id="3c569-239">护照号</span><span class="sxs-lookup"><span data-stu-id="3c569-239">passport no</span></span>  <br/> <span data-ttu-id="3c569-240">pas</span><span class="sxs-lookup"><span data-stu-id="3c569-240">pas</span></span>  <br/> <span data-ttu-id="3c569-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="3c569-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="3c569-242">爱沙尼亚</span><span class="sxs-lookup"><span data-stu-id="3c569-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="3c569-243">Format</span><span class="sxs-lookup"><span data-stu-id="3c569-243">Format</span></span>

<span data-ttu-id="3c569-244">一个字母后跟七个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3c569-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c569-245">模式</span><span class="sxs-lookup"><span data-stu-id="3c569-245">Pattern</span></span>

<span data-ttu-id="3c569-246">一个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="3c569-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3c569-247">校验和</span><span class="sxs-lookup"><span data-stu-id="3c569-247">Checksum</span></span>

<span data-ttu-id="3c569-248">否</span><span class="sxs-lookup"><span data-stu-id="3c569-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c569-249">定义</span><span class="sxs-lookup"><span data-stu-id="3c569-249">Definition</span></span>

<span data-ttu-id="3c569-250">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c569-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c569-251">正则表达式`Regex_estonia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c569-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c569-252">找到了中`Keywords_estonia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c569-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c569-253">关键字</span><span class="sxs-lookup"><span data-stu-id="3c569-253">Keywords</span></span>

<span data-ttu-id="3c569-254">| |</span><span class="sxs-lookup"><span data-stu-id="3c569-254"></span></span>
|<span data-ttu-id="3c569-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3c569-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3c569-256">passport number</span><span class="sxs-lookup"><span data-stu-id="3c569-256">passport number</span></span>  <br/> <span data-ttu-id="3c569-257">爱沙尼亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="3c569-257">estonian passport number</span></span>  <br/> <span data-ttu-id="3c569-258">护照号</span><span class="sxs-lookup"><span data-stu-id="3c569-258">passport no</span></span>  <br/> <span data-ttu-id="3c569-259">eesti kodaniku pass</span><span class="sxs-lookup"><span data-stu-id="3c569-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="3c569-260">芬兰</span><span class="sxs-lookup"><span data-stu-id="3c569-260">Finland</span></span>

<span data-ttu-id="3c569-261">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "芬兰护照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="3c569-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="3c569-262">法国</span><span class="sxs-lookup"><span data-stu-id="3c569-262">France</span></span>

<span data-ttu-id="3c569-263">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "法国护照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="3c569-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="3c569-264">德国</span><span class="sxs-lookup"><span data-stu-id="3c569-264">Germany</span></span>

<span data-ttu-id="3c569-265">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "德国护照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="3c569-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="3c569-266">希腊</span><span class="sxs-lookup"><span data-stu-id="3c569-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="3c569-267">Format</span><span class="sxs-lookup"><span data-stu-id="3c569-267">Format</span></span>

<span data-ttu-id="3c569-268">两个字母后跟七个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3c569-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c569-269">模式</span><span class="sxs-lookup"><span data-stu-id="3c569-269">Pattern</span></span>

<span data-ttu-id="3c569-270">两个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="3c569-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3c569-271">校验和</span><span class="sxs-lookup"><span data-stu-id="3c569-271">Checksum</span></span>

<span data-ttu-id="3c569-272">否</span><span class="sxs-lookup"><span data-stu-id="3c569-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c569-273">定义</span><span class="sxs-lookup"><span data-stu-id="3c569-273">Definition</span></span>

<span data-ttu-id="3c569-274">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c569-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c569-275">正则表达式`Regex_greece_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c569-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c569-276">找到了中`Keywords_greece_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c569-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c569-277">关键字</span><span class="sxs-lookup"><span data-stu-id="3c569-277">Keywords</span></span>

<span data-ttu-id="3c569-278">| |</span><span class="sxs-lookup"><span data-stu-id="3c569-278"></span></span>
|<span data-ttu-id="3c569-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3c569-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3c569-280">passport number</span><span class="sxs-lookup"><span data-stu-id="3c569-280">passport number</span></span>  <br/> <span data-ttu-id="3c569-281">希腊护照号码</span><span class="sxs-lookup"><span data-stu-id="3c569-281">greek passport number</span></span>  <br/> <span data-ttu-id="3c569-282">护照号</span><span class="sxs-lookup"><span data-stu-id="3c569-282">passport no</span></span>  <br/> <span data-ttu-id="3c569-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="3c569-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="3c569-284">匈牙利</span><span class="sxs-lookup"><span data-stu-id="3c569-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="3c569-285">Format</span><span class="sxs-lookup"><span data-stu-id="3c569-285">Format</span></span>

<span data-ttu-id="3c569-286">两个字母后跟6个或7个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3c569-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c569-287">模式</span><span class="sxs-lookup"><span data-stu-id="3c569-287">Pattern</span></span>

<span data-ttu-id="3c569-288">两个字母后跟六个或七个数字</span><span class="sxs-lookup"><span data-stu-id="3c569-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3c569-289">校验和</span><span class="sxs-lookup"><span data-stu-id="3c569-289">Checksum</span></span>

<span data-ttu-id="3c569-290">否</span><span class="sxs-lookup"><span data-stu-id="3c569-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c569-291">定义</span><span class="sxs-lookup"><span data-stu-id="3c569-291">Definition</span></span>

<span data-ttu-id="3c569-292">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c569-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c569-293">正则表达式`Regex_hungary_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c569-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c569-294">找到了中`Keywords_hungary_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c569-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c569-295">关键字</span><span class="sxs-lookup"><span data-stu-id="3c569-295">Keywords</span></span>

<span data-ttu-id="3c569-296">| |</span><span class="sxs-lookup"><span data-stu-id="3c569-296"></span></span>
|<span data-ttu-id="3c569-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3c569-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3c569-298">passport number</span><span class="sxs-lookup"><span data-stu-id="3c569-298">passport number</span></span>  <br/> <span data-ttu-id="3c569-299">匈牙利语护照号码</span><span class="sxs-lookup"><span data-stu-id="3c569-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="3c569-300">护照号</span><span class="sxs-lookup"><span data-stu-id="3c569-300">passport no</span></span>  <br/> <span data-ttu-id="3c569-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="3c569-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="3c569-302">爱尔兰</span><span class="sxs-lookup"><span data-stu-id="3c569-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="3c569-303">Format</span><span class="sxs-lookup"><span data-stu-id="3c569-303">Format</span></span>

<span data-ttu-id="3c569-304">两个字母或数字后跟七个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3c569-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c569-305">模式</span><span class="sxs-lookup"><span data-stu-id="3c569-305">Pattern</span></span>

<span data-ttu-id="3c569-306">两个字母或数字, 后跟七个数字:</span><span class="sxs-lookup"><span data-stu-id="3c569-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="3c569-307">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="3c569-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="3c569-308">七个数字</span><span class="sxs-lookup"><span data-stu-id="3c569-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3c569-309">校验和</span><span class="sxs-lookup"><span data-stu-id="3c569-309">Checksum</span></span>

<span data-ttu-id="3c569-310">否</span><span class="sxs-lookup"><span data-stu-id="3c569-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c569-311">定义</span><span class="sxs-lookup"><span data-stu-id="3c569-311">Definition</span></span>

<span data-ttu-id="3c569-312">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c569-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c569-313">正则表达式`Regex_ireland_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c569-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c569-314">找到了中`Keywords_ireland_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c569-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c569-315">关键字</span><span class="sxs-lookup"><span data-stu-id="3c569-315">Keywords</span></span>

<span data-ttu-id="3c569-316">| |</span><span class="sxs-lookup"><span data-stu-id="3c569-316"></span></span>
|<span data-ttu-id="3c569-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3c569-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3c569-318">passport number</span><span class="sxs-lookup"><span data-stu-id="3c569-318">passport number</span></span>  <br/> <span data-ttu-id="3c569-319">爱尔兰护照号码</span><span class="sxs-lookup"><span data-stu-id="3c569-319">irish passport number</span></span>  <br/> <span data-ttu-id="3c569-320">护照号</span><span class="sxs-lookup"><span data-stu-id="3c569-320">passport no</span></span>  <br/> <span data-ttu-id="3c569-321">pas</span><span class="sxs-lookup"><span data-stu-id="3c569-321">pas</span></span>  <br/> <span data-ttu-id="3c569-322">登记卡</span><span class="sxs-lookup"><span data-stu-id="3c569-322">passport</span></span>  <br/> <span data-ttu-id="3c569-323">passeport</span><span class="sxs-lookup"><span data-stu-id="3c569-323">passeport</span></span>  <br/> <span data-ttu-id="3c569-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="3c569-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="3c569-325">意大利</span><span class="sxs-lookup"><span data-stu-id="3c569-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="3c569-326">Format</span><span class="sxs-lookup"><span data-stu-id="3c569-326">Format</span></span>

<span data-ttu-id="3c569-327">两个字母或数字后跟七个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3c569-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c569-328">模式</span><span class="sxs-lookup"><span data-stu-id="3c569-328">Pattern</span></span>

<span data-ttu-id="3c569-329">两个字母或数字, 后跟七个数字:</span><span class="sxs-lookup"><span data-stu-id="3c569-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="3c569-330">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="3c569-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="3c569-331">七个数字</span><span class="sxs-lookup"><span data-stu-id="3c569-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3c569-332">校验和</span><span class="sxs-lookup"><span data-stu-id="3c569-332">Checksum</span></span>

<span data-ttu-id="3c569-333">不适用</span><span class="sxs-lookup"><span data-stu-id="3c569-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c569-334">定义</span><span class="sxs-lookup"><span data-stu-id="3c569-334">Definition</span></span>

<span data-ttu-id="3c569-335">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c569-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c569-336">正则表达式`Regex_italy_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c569-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c569-337">找到了中`Keywords_italy_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c569-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c569-338">关键字</span><span class="sxs-lookup"><span data-stu-id="3c569-338">Keywords</span></span>

<span data-ttu-id="3c569-339">| |</span><span class="sxs-lookup"><span data-stu-id="3c569-339"></span></span>
|<span data-ttu-id="3c569-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3c569-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3c569-341">意大利护照号码</span><span class="sxs-lookup"><span data-stu-id="3c569-341">italian passport number</span></span>  <br/> <span data-ttu-id="3c569-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="3c569-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="3c569-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="3c569-343">passaporto</span></span>  <br/> <span data-ttu-id="3c569-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="3c569-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="3c569-345">passport number</span><span class="sxs-lookup"><span data-stu-id="3c569-345">passport number</span></span>  <br/> <span data-ttu-id="3c569-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="3c569-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="3c569-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="3c569-347">passaporto numero</span></span>  <br/> <span data-ttu-id="3c569-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="3c569-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="3c569-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="3c569-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="3c569-350">拉脱维亚</span><span class="sxs-lookup"><span data-stu-id="3c569-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="3c569-351">Format</span><span class="sxs-lookup"><span data-stu-id="3c569-351">Format</span></span>

<span data-ttu-id="3c569-352">两个字母或数字后跟七个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3c569-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c569-353">模式</span><span class="sxs-lookup"><span data-stu-id="3c569-353">Pattern</span></span>

<span data-ttu-id="3c569-354">两个字母或数字, 后跟七个数字:</span><span class="sxs-lookup"><span data-stu-id="3c569-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="3c569-355">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="3c569-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="3c569-356">七个数字</span><span class="sxs-lookup"><span data-stu-id="3c569-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3c569-357">校验和</span><span class="sxs-lookup"><span data-stu-id="3c569-357">Checksum</span></span>

<span data-ttu-id="3c569-358">否</span><span class="sxs-lookup"><span data-stu-id="3c569-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c569-359">定义</span><span class="sxs-lookup"><span data-stu-id="3c569-359">Definition</span></span>

<span data-ttu-id="3c569-360">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c569-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c569-361">正则表达式`Regex_latvia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c569-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c569-362">找到了中`Keywords_latvia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c569-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c569-363">关键字</span><span class="sxs-lookup"><span data-stu-id="3c569-363">Keywords</span></span>

<span data-ttu-id="3c569-364">| |</span><span class="sxs-lookup"><span data-stu-id="3c569-364"></span></span>
|<span data-ttu-id="3c569-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3c569-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3c569-366">passport number</span><span class="sxs-lookup"><span data-stu-id="3c569-366">passport number</span></span>  <br/> <span data-ttu-id="3c569-367">拉脱维亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="3c569-367">latvian passport number</span></span>  <br/> <span data-ttu-id="3c569-368">护照号</span><span class="sxs-lookup"><span data-stu-id="3c569-368">passport no</span></span>  <br/> <span data-ttu-id="3c569-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="3c569-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="3c569-370">立陶宛</span><span class="sxs-lookup"><span data-stu-id="3c569-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="3c569-371">Format</span><span class="sxs-lookup"><span data-stu-id="3c569-371">Format</span></span>

<span data-ttu-id="3c569-372">八个数字或字母不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3c569-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c569-373">模式</span><span class="sxs-lookup"><span data-stu-id="3c569-373">Pattern</span></span>

<span data-ttu-id="3c569-374">八个数字或字母 (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="3c569-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3c569-375">校验和</span><span class="sxs-lookup"><span data-stu-id="3c569-375">Checksum</span></span>

<span data-ttu-id="3c569-376">不适用</span><span class="sxs-lookup"><span data-stu-id="3c569-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c569-377">定义</span><span class="sxs-lookup"><span data-stu-id="3c569-377">Definition</span></span>

<span data-ttu-id="3c569-378">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c569-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c569-379">正则表达式`Regex_lithuania_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c569-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c569-380">找到了中`Keywords_lithuania_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c569-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c569-381">关键字</span><span class="sxs-lookup"><span data-stu-id="3c569-381">Keywords</span></span>

<span data-ttu-id="3c569-382">| |</span><span class="sxs-lookup"><span data-stu-id="3c569-382"></span></span>
|<span data-ttu-id="3c569-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3c569-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3c569-384">passport number</span><span class="sxs-lookup"><span data-stu-id="3c569-384">passport number</span></span>  <br/> <span data-ttu-id="3c569-385">lithunian 护照号码</span><span class="sxs-lookup"><span data-stu-id="3c569-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="3c569-386">护照号</span><span class="sxs-lookup"><span data-stu-id="3c569-386">passport no</span></span>  <br/> <span data-ttu-id="3c569-387">paso numeris</span><span class="sxs-lookup"><span data-stu-id="3c569-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="3c569-388">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="3c569-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="3c569-389">Format</span><span class="sxs-lookup"><span data-stu-id="3c569-389">Format</span></span>

<span data-ttu-id="3c569-390">八个数字或字母不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3c569-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c569-391">模式</span><span class="sxs-lookup"><span data-stu-id="3c569-391">Pattern</span></span>

<span data-ttu-id="3c569-392">八个数字或字母 (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="3c569-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3c569-393">校验和</span><span class="sxs-lookup"><span data-stu-id="3c569-393">Checksum</span></span>

<span data-ttu-id="3c569-394">否</span><span class="sxs-lookup"><span data-stu-id="3c569-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c569-395">定义</span><span class="sxs-lookup"><span data-stu-id="3c569-395">Definition</span></span>

<span data-ttu-id="3c569-396">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c569-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c569-397">正则表达式`Regex_nation_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c569-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c569-398">找到了中`Keywords_nation_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c569-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c569-399">关键字</span><span class="sxs-lookup"><span data-stu-id="3c569-399">Keywords</span></span>

<span data-ttu-id="3c569-400">| |</span><span class="sxs-lookup"><span data-stu-id="3c569-400"></span></span>
|<span data-ttu-id="3c569-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3c569-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3c569-402">passport number</span><span class="sxs-lookup"><span data-stu-id="3c569-402">passport number</span></span>  <br/> <span data-ttu-id="3c569-403">拉脱维亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="3c569-403">latvian passport number</span></span>  <br/> <span data-ttu-id="3c569-404">护照号</span><span class="sxs-lookup"><span data-stu-id="3c569-404">passport no</span></span>  <br/> <span data-ttu-id="3c569-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="3c569-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="3c569-406">马耳他</span><span class="sxs-lookup"><span data-stu-id="3c569-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="3c569-407">Format</span><span class="sxs-lookup"><span data-stu-id="3c569-407">Format</span></span>

<span data-ttu-id="3c569-408">七位数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3c569-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c569-409">模式</span><span class="sxs-lookup"><span data-stu-id="3c569-409">Pattern</span></span>

 <span data-ttu-id="3c569-410">七个数字</span><span class="sxs-lookup"><span data-stu-id="3c569-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="3c569-411">校验和</span><span class="sxs-lookup"><span data-stu-id="3c569-411">Checksum</span></span>

<span data-ttu-id="3c569-412">否</span><span class="sxs-lookup"><span data-stu-id="3c569-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c569-413">定义</span><span class="sxs-lookup"><span data-stu-id="3c569-413">Definition</span></span>

<span data-ttu-id="3c569-414">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c569-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c569-415">正则表达式`Regex_malta_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c569-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c569-416">找到了中`Keywords_malta_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c569-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c569-417">关键字</span><span class="sxs-lookup"><span data-stu-id="3c569-417">Keywords</span></span>

<span data-ttu-id="3c569-418">| |</span><span class="sxs-lookup"><span data-stu-id="3c569-418"></span></span>
|<span data-ttu-id="3c569-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3c569-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3c569-420">passport number</span><span class="sxs-lookup"><span data-stu-id="3c569-420">passport number</span></span>  <br/> <span data-ttu-id="3c569-421">马耳他护照号码</span><span class="sxs-lookup"><span data-stu-id="3c569-421">maltese passport number</span></span>  <br/> <span data-ttu-id="3c569-422">护照号</span><span class="sxs-lookup"><span data-stu-id="3c569-422">passport no</span></span>  <br/> <span data-ttu-id="3c569-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="3c569-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="3c569-424">荷兰</span><span class="sxs-lookup"><span data-stu-id="3c569-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="3c569-425">Format</span><span class="sxs-lookup"><span data-stu-id="3c569-425">Format</span></span>

<span data-ttu-id="3c569-426">九个字母或数字, 不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3c569-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c569-427">模式</span><span class="sxs-lookup"><span data-stu-id="3c569-427">Pattern</span></span>

<span data-ttu-id="3c569-428">九个字母或数字</span><span class="sxs-lookup"><span data-stu-id="3c569-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3c569-429">校验和</span><span class="sxs-lookup"><span data-stu-id="3c569-429">Checksum</span></span>

<span data-ttu-id="3c569-430">不适用</span><span class="sxs-lookup"><span data-stu-id="3c569-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c569-431">定义</span><span class="sxs-lookup"><span data-stu-id="3c569-431">Definition</span></span>

<span data-ttu-id="3c569-432">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c569-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c569-433">正则表达式`Regex_netherlands_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c569-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c569-434">找到了中`Keywords_netherlands_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c569-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c569-435">关键字</span><span class="sxs-lookup"><span data-stu-id="3c569-435">Keywords</span></span>

<span data-ttu-id="3c569-436">| |</span><span class="sxs-lookup"><span data-stu-id="3c569-436"></span></span>
|<span data-ttu-id="3c569-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3c569-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3c569-438">荷兰护照号码</span><span class="sxs-lookup"><span data-stu-id="3c569-438">dutch passport number</span></span>  <br/> <span data-ttu-id="3c569-439">passport number</span><span class="sxs-lookup"><span data-stu-id="3c569-439">passport number</span></span>  <br/> <span data-ttu-id="3c569-440">荷兰护照号码</span><span class="sxs-lookup"><span data-stu-id="3c569-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="3c569-441">nederlanden paspoort nummer</span><span class="sxs-lookup"><span data-stu-id="3c569-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="3c569-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="3c569-442">paspoort</span></span>  <br/> <span data-ttu-id="3c569-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="3c569-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="3c569-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="3c569-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="3c569-445">波兰</span><span class="sxs-lookup"><span data-stu-id="3c569-445">Poland</span></span>

<span data-ttu-id="3c569-446">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "波兰 Passport 号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="3c569-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="3c569-447">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="3c569-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="3c569-448">Format</span><span class="sxs-lookup"><span data-stu-id="3c569-448">Format</span></span>

<span data-ttu-id="3c569-449">一个字母后跟六个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3c569-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c569-450">模式</span><span class="sxs-lookup"><span data-stu-id="3c569-450">Pattern</span></span>

<span data-ttu-id="3c569-451">一个字母后跟六个数字:</span><span class="sxs-lookup"><span data-stu-id="3c569-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="3c569-452">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="3c569-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="3c569-453">六个数字</span><span class="sxs-lookup"><span data-stu-id="3c569-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3c569-454">校验和</span><span class="sxs-lookup"><span data-stu-id="3c569-454">Checksum</span></span>

<span data-ttu-id="3c569-455">否</span><span class="sxs-lookup"><span data-stu-id="3c569-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c569-456">定义</span><span class="sxs-lookup"><span data-stu-id="3c569-456">Definition</span></span>

<span data-ttu-id="3c569-457">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c569-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c569-458">正则表达式`Regex_portugal_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c569-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c569-459">找到了中`Keywords_portugal_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c569-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c569-460">关键字</span><span class="sxs-lookup"><span data-stu-id="3c569-460">Keywords</span></span>

<span data-ttu-id="3c569-461">| |</span><span class="sxs-lookup"><span data-stu-id="3c569-461"></span></span>
|<span data-ttu-id="3c569-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3c569-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3c569-463">passport number</span><span class="sxs-lookup"><span data-stu-id="3c569-463">passport number</span></span>  <br/> <span data-ttu-id="3c569-464">葡萄牙语护照号码</span><span class="sxs-lookup"><span data-stu-id="3c569-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="3c569-465">护照号</span><span class="sxs-lookup"><span data-stu-id="3c569-465">passport no</span></span>  <br/> <span data-ttu-id="3c569-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="3c569-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="3c569-467">罗马尼亚</span><span class="sxs-lookup"><span data-stu-id="3c569-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="3c569-468">Format</span><span class="sxs-lookup"><span data-stu-id="3c569-468">Format</span></span>

<span data-ttu-id="3c569-469">八个或9个数字, 不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="3c569-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c569-470">模式</span><span class="sxs-lookup"><span data-stu-id="3c569-470">Pattern</span></span>

<span data-ttu-id="3c569-471">8或9个数字</span><span class="sxs-lookup"><span data-stu-id="3c569-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3c569-472">校验和</span><span class="sxs-lookup"><span data-stu-id="3c569-472">Checksum</span></span>

<span data-ttu-id="3c569-473">否</span><span class="sxs-lookup"><span data-stu-id="3c569-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c569-474">定义</span><span class="sxs-lookup"><span data-stu-id="3c569-474">Definition</span></span>

<span data-ttu-id="3c569-475">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c569-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c569-476">正则表达式`Regex_romania_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c569-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c569-477">找到了中`Keywords_romania_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c569-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c569-478">关键字</span><span class="sxs-lookup"><span data-stu-id="3c569-478">Keywords</span></span>

<span data-ttu-id="3c569-479">| |</span><span class="sxs-lookup"><span data-stu-id="3c569-479"></span></span>
|<span data-ttu-id="3c569-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3c569-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3c569-481">passport number</span><span class="sxs-lookup"><span data-stu-id="3c569-481">passport number</span></span>  <br/> <span data-ttu-id="3c569-482">罗马尼亚护照号码</span><span class="sxs-lookup"><span data-stu-id="3c569-482">romanian passport number</span></span>  <br/> <span data-ttu-id="3c569-483">护照号</span><span class="sxs-lookup"><span data-stu-id="3c569-483">passport no</span></span>  <br/> <span data-ttu-id="3c569-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="3c569-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="3c569-485">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="3c569-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="3c569-486">Format</span><span class="sxs-lookup"><span data-stu-id="3c569-486">Format</span></span>

<span data-ttu-id="3c569-487">一个数字或字母后跟七个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3c569-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c569-488">模式</span><span class="sxs-lookup"><span data-stu-id="3c569-488">Pattern</span></span>

<span data-ttu-id="3c569-489">一个数字或字母 (不区分大小写) 后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="3c569-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3c569-490">校验和</span><span class="sxs-lookup"><span data-stu-id="3c569-490">Checksum</span></span>

<span data-ttu-id="3c569-491">否</span><span class="sxs-lookup"><span data-stu-id="3c569-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c569-492">定义</span><span class="sxs-lookup"><span data-stu-id="3c569-492">Definition</span></span>

<span data-ttu-id="3c569-493">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c569-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c569-494">正则表达式`Regex_slovakia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c569-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c569-495">找到了中`Keywords_slovakia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c569-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c569-496">关键字</span><span class="sxs-lookup"><span data-stu-id="3c569-496">Keywords</span></span>

<span data-ttu-id="3c569-497">| |</span><span class="sxs-lookup"><span data-stu-id="3c569-497"></span></span>
|<span data-ttu-id="3c569-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3c569-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3c569-499">passport number</span><span class="sxs-lookup"><span data-stu-id="3c569-499">passport number</span></span>  <br/> <span data-ttu-id="3c569-500">斯洛伐克护照号码</span><span class="sxs-lookup"><span data-stu-id="3c569-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="3c569-501">护照号</span><span class="sxs-lookup"><span data-stu-id="3c569-501">passport no</span></span>  <br/> <span data-ttu-id="3c569-502">číslo pasu</span><span class="sxs-lookup"><span data-stu-id="3c569-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="3c569-503">斯洛文尼亚</span><span class="sxs-lookup"><span data-stu-id="3c569-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="3c569-504">Format</span><span class="sxs-lookup"><span data-stu-id="3c569-504">Format</span></span>

<span data-ttu-id="3c569-505">两个字母后跟七个数字, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3c569-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c569-506">模式</span><span class="sxs-lookup"><span data-stu-id="3c569-506">Pattern</span></span>

<span data-ttu-id="3c569-507">两个字母后跟七个数字:</span><span class="sxs-lookup"><span data-stu-id="3c569-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="3c569-508">字母 "P"</span><span class="sxs-lookup"><span data-stu-id="3c569-508">The letter "P"</span></span>
    
- <span data-ttu-id="3c569-509">一个大写字母</span><span class="sxs-lookup"><span data-stu-id="3c569-509">One uppercase letter</span></span>
    
- <span data-ttu-id="3c569-510">七个数字</span><span class="sxs-lookup"><span data-stu-id="3c569-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3c569-511">校验和</span><span class="sxs-lookup"><span data-stu-id="3c569-511">Checksum</span></span>

<span data-ttu-id="3c569-512">否</span><span class="sxs-lookup"><span data-stu-id="3c569-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c569-513">定义</span><span class="sxs-lookup"><span data-stu-id="3c569-513">Definition</span></span>

<span data-ttu-id="3c569-514">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c569-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c569-515">正则表达式`Regex_slovenia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c569-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c569-516">找到了中`Keywords_slovenia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c569-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c569-517">关键字</span><span class="sxs-lookup"><span data-stu-id="3c569-517">Keywords</span></span>

<span data-ttu-id="3c569-518">| |</span><span class="sxs-lookup"><span data-stu-id="3c569-518"></span></span>
|<span data-ttu-id="3c569-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3c569-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3c569-520">passport number</span><span class="sxs-lookup"><span data-stu-id="3c569-520">passport number</span></span>  <br/> <span data-ttu-id="3c569-521">斯洛文尼亚护照号码</span><span class="sxs-lookup"><span data-stu-id="3c569-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="3c569-522">护照号</span><span class="sxs-lookup"><span data-stu-id="3c569-522">passport no</span></span>  <br/> <span data-ttu-id="3c569-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="3c569-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="3c569-524">西班牙</span><span class="sxs-lookup"><span data-stu-id="3c569-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="3c569-525">Format</span><span class="sxs-lookup"><span data-stu-id="3c569-525">Format</span></span>

<span data-ttu-id="3c569-526">八个或九个字符的字母和数字的组合, 不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3c569-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c569-527">模式</span><span class="sxs-lookup"><span data-stu-id="3c569-527">Pattern</span></span>

<span data-ttu-id="3c569-528">字母和数字的八个或九个字符的组合:</span><span class="sxs-lookup"><span data-stu-id="3c569-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="3c569-529">两位数字或字母</span><span class="sxs-lookup"><span data-stu-id="3c569-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="3c569-530">一个数字或字母 (可选)</span><span class="sxs-lookup"><span data-stu-id="3c569-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="3c569-531">六个数字</span><span class="sxs-lookup"><span data-stu-id="3c569-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3c569-532">校验和</span><span class="sxs-lookup"><span data-stu-id="3c569-532">Checksum</span></span>

<span data-ttu-id="3c569-533">不适用</span><span class="sxs-lookup"><span data-stu-id="3c569-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c569-534">定义</span><span class="sxs-lookup"><span data-stu-id="3c569-534">Definition</span></span>

<span data-ttu-id="3c569-535">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c569-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c569-536">正则表达式`Regex_spain_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c569-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c569-537">找到了中`Keywords_spain_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c569-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c569-538">关键字</span><span class="sxs-lookup"><span data-stu-id="3c569-538">Keywords</span></span>

<span data-ttu-id="3c569-539">| |</span><span class="sxs-lookup"><span data-stu-id="3c569-539"></span></span>
|<span data-ttu-id="3c569-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3c569-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3c569-541">登记卡</span><span class="sxs-lookup"><span data-stu-id="3c569-541">passport</span></span>  <br/> <span data-ttu-id="3c569-542">西班牙护照</span><span class="sxs-lookup"><span data-stu-id="3c569-542">spain passport</span></span>  <br/> <span data-ttu-id="3c569-543">护照书籍</span><span class="sxs-lookup"><span data-stu-id="3c569-543">passport book</span></span>  <br/> <span data-ttu-id="3c569-544">passport number</span><span class="sxs-lookup"><span data-stu-id="3c569-544">passport number</span></span>  <br/> <span data-ttu-id="3c569-545">护照号</span><span class="sxs-lookup"><span data-stu-id="3c569-545">passport no</span></span>  <br/> <span data-ttu-id="3c569-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="3c569-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="3c569-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="3c569-547">número pasaporte</span></span>  <br/> <span data-ttu-id="3c569-548">西班牙 pasaporte</span><span class="sxs-lookup"><span data-stu-id="3c569-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="3c569-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="3c569-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="3c569-550">瑞典</span><span class="sxs-lookup"><span data-stu-id="3c569-550">Sweden</span></span>

<span data-ttu-id="3c569-551">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "瑞典护照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="3c569-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="3c569-552">英国</span><span class="sxs-lookup"><span data-stu-id="3c569-552">UK</span></span>

<span data-ttu-id="3c569-553">有关详细信息, 请参阅 "美国/英国" 一节。</span><span class="sxs-lookup"><span data-stu-id="3c569-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="3c569-554">"Passport 号码", 在[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中。</span><span class="sxs-lookup"><span data-stu-id="3c569-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3c569-555">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3c569-555">See also</span></span>

[<span data-ttu-id="3c569-556">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="3c569-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

