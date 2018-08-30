---
title: 欧盟护照号码
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 8c00df57-9fb3-459c-ba87-40480c87bd55
description: 本主题演示数据丢失防护 (DLP) 策略检测到的欧盟护照号码敏感信息类型时的寻找。此敏感信息类型定义不同的模式、 关键字和每个国家/地区其他证据。
ms.openlocfilehash: 71acc39b885c057e1771ec13b2f3c25017ac1bb6
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525488"
---
# <a name="eu-passport-number"></a><span data-ttu-id="3afab-104">欧盟护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-104">EU Passport Number</span></span>

<span data-ttu-id="3afab-p102">本主题演示数据丢失防护 (DLP) 策略检测到的欧盟护照号码敏感信息类型时的寻找。此敏感信息类型定义不同的模式、 关键字和每个国家/地区其他证据。</span><span class="sxs-lookup"><span data-stu-id="3afab-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="3afab-107">奥地利</span><span class="sxs-lookup"><span data-stu-id="3afab-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="3afab-108">格式</span><span class="sxs-lookup"><span data-stu-id="3afab-108">Format</span></span>

<span data-ttu-id="3afab-109">可选的空间和七位数字后跟一个字母</span><span class="sxs-lookup"><span data-stu-id="3afab-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3afab-110">模式</span><span class="sxs-lookup"><span data-stu-id="3afab-110">Pattern</span></span>

<span data-ttu-id="3afab-111">一个字母、 七个数字和一个空格的组合：</span><span class="sxs-lookup"><span data-stu-id="3afab-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="3afab-112">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="3afab-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="3afab-113">一个空格 （可选）</span><span class="sxs-lookup"><span data-stu-id="3afab-113">One space (optional)</span></span>
    
- <span data-ttu-id="3afab-114">七个数字</span><span class="sxs-lookup"><span data-stu-id="3afab-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3afab-115">校验和</span><span class="sxs-lookup"><span data-stu-id="3afab-115">Checksum</span></span>

<span data-ttu-id="3afab-116">不适用</span><span class="sxs-lookup"><span data-stu-id="3afab-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3afab-117">定义</span><span class="sxs-lookup"><span data-stu-id="3afab-117">Definition</span></span>

<span data-ttu-id="3afab-118">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3afab-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3afab-119">正则表达式`Regex_austria_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3afab-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3afab-120">从关键字`Keywords_austria_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="3afab-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3afab-121">Keywords</span><span class="sxs-lookup"><span data-stu-id="3afab-121">Keywords</span></span>

<span data-ttu-id="3afab-122">| |</span><span class="sxs-lookup"><span data-stu-id="3afab-122"></span></span>
|<span data-ttu-id="3afab-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3afab-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3afab-124">护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-124">passport number</span></span>  <br/> <span data-ttu-id="3afab-125">奥地利护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-125">austrian passport number</span></span>  <br/> <span data-ttu-id="3afab-126">passport 没有</span><span class="sxs-lookup"><span data-stu-id="3afab-126">passport no</span></span>  <br/> <span data-ttu-id="3afab-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="3afab-127">reisepass</span></span>  <br/> <span data-ttu-id="3afab-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="3afab-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="3afab-129">比利时</span><span class="sxs-lookup"><span data-stu-id="3afab-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="3afab-130">格式</span><span class="sxs-lookup"><span data-stu-id="3afab-130">Format</span></span>

<span data-ttu-id="3afab-131">不得含有空格或分隔符六位数字后跟两个字母</span><span class="sxs-lookup"><span data-stu-id="3afab-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3afab-132">模式</span><span class="sxs-lookup"><span data-stu-id="3afab-132">Pattern</span></span>

<span data-ttu-id="3afab-133">两个字母和包含 6 位数字后跟</span><span class="sxs-lookup"><span data-stu-id="3afab-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3afab-134">校验和</span><span class="sxs-lookup"><span data-stu-id="3afab-134">Checksum</span></span>

<span data-ttu-id="3afab-135">不适用</span><span class="sxs-lookup"><span data-stu-id="3afab-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3afab-136">定义</span><span class="sxs-lookup"><span data-stu-id="3afab-136">Definition</span></span>

<span data-ttu-id="3afab-137">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3afab-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3afab-138">正则表达式`Regex_belgium_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3afab-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3afab-139">从关键字`Keywords_belgium_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="3afab-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3afab-140">Keywords</span><span class="sxs-lookup"><span data-stu-id="3afab-140">Keywords</span></span>

<span data-ttu-id="3afab-141">| |</span><span class="sxs-lookup"><span data-stu-id="3afab-141"></span></span>
|<span data-ttu-id="3afab-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3afab-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3afab-143">护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-143">passport number</span></span>  <br/> <span data-ttu-id="3afab-144">比利时护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-144">belgian passport number</span></span>  <br/> <span data-ttu-id="3afab-145">passport 没有</span><span class="sxs-lookup"><span data-stu-id="3afab-145">passport no</span></span>  <br/> <span data-ttu-id="3afab-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="3afab-146">paspoort</span></span>  <br/> <span data-ttu-id="3afab-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="3afab-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="3afab-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="3afab-148">reisepass kein</span></span>  <br/> <span data-ttu-id="3afab-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="3afab-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="3afab-150">保加利亚</span><span class="sxs-lookup"><span data-stu-id="3afab-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="3afab-151">格式</span><span class="sxs-lookup"><span data-stu-id="3afab-151">Format</span></span>

<span data-ttu-id="3afab-152">没有空格和分隔符的九个数字</span><span class="sxs-lookup"><span data-stu-id="3afab-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3afab-153">模式</span><span class="sxs-lookup"><span data-stu-id="3afab-153">Pattern</span></span>

 <span data-ttu-id="3afab-154">九个数字</span><span class="sxs-lookup"><span data-stu-id="3afab-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="3afab-155">校验和</span><span class="sxs-lookup"><span data-stu-id="3afab-155">Checksum</span></span>

<span data-ttu-id="3afab-156">否</span><span class="sxs-lookup"><span data-stu-id="3afab-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3afab-157">定义</span><span class="sxs-lookup"><span data-stu-id="3afab-157">Definition</span></span>

<span data-ttu-id="3afab-158">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3afab-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3afab-159">正则表达式`Regex_bulgaria_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3afab-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3afab-160">从关键字`Keywords_bulgaria_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="3afab-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3afab-161">Keywords</span><span class="sxs-lookup"><span data-stu-id="3afab-161">Keywords</span></span>

<span data-ttu-id="3afab-162">| |</span><span class="sxs-lookup"><span data-stu-id="3afab-162"></span></span>
|<span data-ttu-id="3afab-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3afab-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3afab-164">护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-164">passport number</span></span>  <br/> <span data-ttu-id="3afab-165">保加利亚护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="3afab-166">passport 没有</span><span class="sxs-lookup"><span data-stu-id="3afab-166">passport no</span></span>  <br/> <span data-ttu-id="3afab-167">НОМЕР НА ПАСПОРТА</span><span class="sxs-lookup"><span data-stu-id="3afab-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="3afab-168">克罗地亚</span><span class="sxs-lookup"><span data-stu-id="3afab-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="3afab-169">格式</span><span class="sxs-lookup"><span data-stu-id="3afab-169">Format</span></span>

<span data-ttu-id="3afab-170">没有空格和分隔符的九个数字</span><span class="sxs-lookup"><span data-stu-id="3afab-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3afab-171">模式</span><span class="sxs-lookup"><span data-stu-id="3afab-171">Pattern</span></span>

 <span data-ttu-id="3afab-172">九个数字</span><span class="sxs-lookup"><span data-stu-id="3afab-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="3afab-173">校验和</span><span class="sxs-lookup"><span data-stu-id="3afab-173">Checksum</span></span>

<span data-ttu-id="3afab-174">否</span><span class="sxs-lookup"><span data-stu-id="3afab-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3afab-175">定义</span><span class="sxs-lookup"><span data-stu-id="3afab-175">Definition</span></span>

<span data-ttu-id="3afab-176">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3afab-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3afab-177">正则表达式`Regex_croatia_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3afab-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3afab-178">从关键字`Keywords_croatia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="3afab-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3afab-179">Keywords</span><span class="sxs-lookup"><span data-stu-id="3afab-179">Keywords</span></span>

<span data-ttu-id="3afab-180">| |</span><span class="sxs-lookup"><span data-stu-id="3afab-180"></span></span>
|<span data-ttu-id="3afab-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3afab-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3afab-182">护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-182">passport number</span></span>  <br/> <span data-ttu-id="3afab-183">克罗地亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-183">croatian passport number</span></span>  <br/> <span data-ttu-id="3afab-184">passport 没有</span><span class="sxs-lookup"><span data-stu-id="3afab-184">passport no</span></span>  <br/> <span data-ttu-id="3afab-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="3afab-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="3afab-186">塞浦路斯</span><span class="sxs-lookup"><span data-stu-id="3afab-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="3afab-187">格式</span><span class="sxs-lookup"><span data-stu-id="3afab-187">Format</span></span>

<span data-ttu-id="3afab-188">不得含有空格或分隔符 6-8 位数字后跟一个字母</span><span class="sxs-lookup"><span data-stu-id="3afab-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3afab-189">模式</span><span class="sxs-lookup"><span data-stu-id="3afab-189">Pattern</span></span>

<span data-ttu-id="3afab-190">6 到 8 位数字后跟一个字母</span><span class="sxs-lookup"><span data-stu-id="3afab-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3afab-191">校验和</span><span class="sxs-lookup"><span data-stu-id="3afab-191">Checksum</span></span>

<span data-ttu-id="3afab-192">否</span><span class="sxs-lookup"><span data-stu-id="3afab-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3afab-193">定义</span><span class="sxs-lookup"><span data-stu-id="3afab-193">Definition</span></span>

<span data-ttu-id="3afab-194">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3afab-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3afab-195">正则表达式`Regex_cyprus_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3afab-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3afab-196">从关键字`Keywords_cyprus_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="3afab-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3afab-197">Keywords</span><span class="sxs-lookup"><span data-stu-id="3afab-197">Keywords</span></span>

<span data-ttu-id="3afab-198">| |</span><span class="sxs-lookup"><span data-stu-id="3afab-198"></span></span>
|<span data-ttu-id="3afab-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3afab-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3afab-200">护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-200">passport number</span></span>  <br/> <span data-ttu-id="3afab-201">塞浦路斯护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="3afab-202">passport 没有</span><span class="sxs-lookup"><span data-stu-id="3afab-202">passport no</span></span>  <br/> <span data-ttu-id="3afab-203">ΑΡΙΘΜΌ ΔΙΑΒΑΤΗΡΊΟΥ</span><span class="sxs-lookup"><span data-stu-id="3afab-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="3afab-204">捷克共和国</span><span class="sxs-lookup"><span data-stu-id="3afab-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="3afab-205">格式</span><span class="sxs-lookup"><span data-stu-id="3afab-205">Format</span></span>

<span data-ttu-id="3afab-206">八个不含空格或分隔符的数字</span><span class="sxs-lookup"><span data-stu-id="3afab-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3afab-207">模式</span><span class="sxs-lookup"><span data-stu-id="3afab-207">Pattern</span></span>

<span data-ttu-id="3afab-208">八个不含空格或分隔符的数字</span><span class="sxs-lookup"><span data-stu-id="3afab-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3afab-209">校验和</span><span class="sxs-lookup"><span data-stu-id="3afab-209">Checksum</span></span>

<span data-ttu-id="3afab-210">否</span><span class="sxs-lookup"><span data-stu-id="3afab-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3afab-211">定义</span><span class="sxs-lookup"><span data-stu-id="3afab-211">Definition</span></span>

<span data-ttu-id="3afab-212">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3afab-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3afab-213">正则表达式`Regex_czech_republic_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3afab-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3afab-214">从关键字`Keywords_czech_republic_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="3afab-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3afab-215">Keywords</span><span class="sxs-lookup"><span data-stu-id="3afab-215">Keywords</span></span>

<span data-ttu-id="3afab-216">| |</span><span class="sxs-lookup"><span data-stu-id="3afab-216"></span></span>
|<span data-ttu-id="3afab-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3afab-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3afab-218">护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-218">passport number</span></span>  <br/> <span data-ttu-id="3afab-219">捷克护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-219">czech passport number</span></span>  <br/> <span data-ttu-id="3afab-220">passport 没有</span><span class="sxs-lookup"><span data-stu-id="3afab-220">passport no</span></span>  <br/> <span data-ttu-id="3afab-221">cestovní pas</span><span class="sxs-lookup"><span data-stu-id="3afab-221">cestovní pas</span></span>  <br/> <span data-ttu-id="3afab-222">pas</span><span class="sxs-lookup"><span data-stu-id="3afab-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="3afab-223">丹麦</span><span class="sxs-lookup"><span data-stu-id="3afab-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="3afab-224">格式</span><span class="sxs-lookup"><span data-stu-id="3afab-224">Format</span></span>

<span data-ttu-id="3afab-225">没有空格和分隔符的九个数字</span><span class="sxs-lookup"><span data-stu-id="3afab-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3afab-226">模式</span><span class="sxs-lookup"><span data-stu-id="3afab-226">Pattern</span></span>

 <span data-ttu-id="3afab-227">九个数字</span><span class="sxs-lookup"><span data-stu-id="3afab-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="3afab-228">校验和</span><span class="sxs-lookup"><span data-stu-id="3afab-228">Checksum</span></span>

<span data-ttu-id="3afab-229">否</span><span class="sxs-lookup"><span data-stu-id="3afab-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3afab-230">定义</span><span class="sxs-lookup"><span data-stu-id="3afab-230">Definition</span></span>

<span data-ttu-id="3afab-231">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3afab-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3afab-232">正则表达式`Regex_denmark_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3afab-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3afab-233">从关键字`Keywords_denmark_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="3afab-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3afab-234">Keywords</span><span class="sxs-lookup"><span data-stu-id="3afab-234">Keywords</span></span>

<span data-ttu-id="3afab-235">| |</span><span class="sxs-lookup"><span data-stu-id="3afab-235"></span></span>
|<span data-ttu-id="3afab-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3afab-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3afab-237">护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-237">passport number</span></span>  <br/> <span data-ttu-id="3afab-238">丹麦语护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-238">danish passport number</span></span>  <br/> <span data-ttu-id="3afab-239">passport 没有</span><span class="sxs-lookup"><span data-stu-id="3afab-239">passport no</span></span>  <br/> <span data-ttu-id="3afab-240">pas</span><span class="sxs-lookup"><span data-stu-id="3afab-240">pas</span></span>  <br/> <span data-ttu-id="3afab-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="3afab-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="3afab-242">爱沙尼亚</span><span class="sxs-lookup"><span data-stu-id="3afab-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="3afab-243">格式</span><span class="sxs-lookup"><span data-stu-id="3afab-243">Format</span></span>

<span data-ttu-id="3afab-244">不得含有空格或分隔符的七位数字后跟一个字母</span><span class="sxs-lookup"><span data-stu-id="3afab-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3afab-245">模式</span><span class="sxs-lookup"><span data-stu-id="3afab-245">Pattern</span></span>

<span data-ttu-id="3afab-246">七位数字后跟一个字母</span><span class="sxs-lookup"><span data-stu-id="3afab-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3afab-247">校验和</span><span class="sxs-lookup"><span data-stu-id="3afab-247">Checksum</span></span>

<span data-ttu-id="3afab-248">否</span><span class="sxs-lookup"><span data-stu-id="3afab-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3afab-249">定义</span><span class="sxs-lookup"><span data-stu-id="3afab-249">Definition</span></span>

<span data-ttu-id="3afab-250">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3afab-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3afab-251">正则表达式`Regex_estonia_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3afab-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3afab-252">从关键字`Keywords_estonia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="3afab-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3afab-253">Keywords</span><span class="sxs-lookup"><span data-stu-id="3afab-253">Keywords</span></span>

<span data-ttu-id="3afab-254">| |</span><span class="sxs-lookup"><span data-stu-id="3afab-254"></span></span>
|<span data-ttu-id="3afab-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3afab-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3afab-256">护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-256">passport number</span></span>  <br/> <span data-ttu-id="3afab-257">爱沙尼亚护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-257">estonian passport number</span></span>  <br/> <span data-ttu-id="3afab-258">passport 没有</span><span class="sxs-lookup"><span data-stu-id="3afab-258">passport no</span></span>  <br/> <span data-ttu-id="3afab-259">eesti kodaniku 传递</span><span class="sxs-lookup"><span data-stu-id="3afab-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="3afab-260">芬兰</span><span class="sxs-lookup"><span data-stu-id="3afab-260">Finland</span></span>

<span data-ttu-id="3afab-261">有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"芬兰护照号码"。</span><span class="sxs-lookup"><span data-stu-id="3afab-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="3afab-262">法国</span><span class="sxs-lookup"><span data-stu-id="3afab-262">France</span></span>

<span data-ttu-id="3afab-263">有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"法国护照号码"。</span><span class="sxs-lookup"><span data-stu-id="3afab-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="3afab-264">德国</span><span class="sxs-lookup"><span data-stu-id="3afab-264">Germany</span></span>

<span data-ttu-id="3afab-265">有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"德国护照号码"。</span><span class="sxs-lookup"><span data-stu-id="3afab-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="3afab-266">希腊</span><span class="sxs-lookup"><span data-stu-id="3afab-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="3afab-267">格式</span><span class="sxs-lookup"><span data-stu-id="3afab-267">Format</span></span>

<span data-ttu-id="3afab-268">不得含有空格或分隔符的七位数字后跟两个字母</span><span class="sxs-lookup"><span data-stu-id="3afab-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3afab-269">模式</span><span class="sxs-lookup"><span data-stu-id="3afab-269">Pattern</span></span>

<span data-ttu-id="3afab-270">两个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="3afab-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3afab-271">校验和</span><span class="sxs-lookup"><span data-stu-id="3afab-271">Checksum</span></span>

<span data-ttu-id="3afab-272">否</span><span class="sxs-lookup"><span data-stu-id="3afab-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3afab-273">定义</span><span class="sxs-lookup"><span data-stu-id="3afab-273">Definition</span></span>

<span data-ttu-id="3afab-274">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3afab-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3afab-275">正则表达式`Regex_greece_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3afab-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3afab-276">从关键字`Keywords_greece_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="3afab-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3afab-277">Keywords</span><span class="sxs-lookup"><span data-stu-id="3afab-277">Keywords</span></span>

<span data-ttu-id="3afab-278">| |</span><span class="sxs-lookup"><span data-stu-id="3afab-278"></span></span>
|<span data-ttu-id="3afab-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3afab-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3afab-280">护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-280">passport number</span></span>  <br/> <span data-ttu-id="3afab-281">希腊语护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-281">greek passport number</span></span>  <br/> <span data-ttu-id="3afab-282">passport 没有</span><span class="sxs-lookup"><span data-stu-id="3afab-282">passport no</span></span>  <br/> <span data-ttu-id="3afab-283">ΔΙΑΒΑΤΗΡΙΟ</span><span class="sxs-lookup"><span data-stu-id="3afab-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="3afab-284">匈牙利</span><span class="sxs-lookup"><span data-stu-id="3afab-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="3afab-285">格式</span><span class="sxs-lookup"><span data-stu-id="3afab-285">Format</span></span>

<span data-ttu-id="3afab-286">不得含有空格或分隔符的六个或七位数字后跟两个字母</span><span class="sxs-lookup"><span data-stu-id="3afab-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3afab-287">模式</span><span class="sxs-lookup"><span data-stu-id="3afab-287">Pattern</span></span>

<span data-ttu-id="3afab-288">六个或七位数字后跟两个字母</span><span class="sxs-lookup"><span data-stu-id="3afab-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3afab-289">校验和</span><span class="sxs-lookup"><span data-stu-id="3afab-289">Checksum</span></span>

<span data-ttu-id="3afab-290">否</span><span class="sxs-lookup"><span data-stu-id="3afab-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3afab-291">定义</span><span class="sxs-lookup"><span data-stu-id="3afab-291">Definition</span></span>

<span data-ttu-id="3afab-292">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3afab-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3afab-293">正则表达式`Regex_hungary_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3afab-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3afab-294">从关键字`Keywords_hungary_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="3afab-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3afab-295">Keywords</span><span class="sxs-lookup"><span data-stu-id="3afab-295">Keywords</span></span>

<span data-ttu-id="3afab-296">| |</span><span class="sxs-lookup"><span data-stu-id="3afab-296"></span></span>
|<span data-ttu-id="3afab-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3afab-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3afab-298">护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-298">passport number</span></span>  <br/> <span data-ttu-id="3afab-299">匈牙利语护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="3afab-300">passport 没有</span><span class="sxs-lookup"><span data-stu-id="3afab-300">passport no</span></span>  <br/> <span data-ttu-id="3afab-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="3afab-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="3afab-302">Ireland</span><span class="sxs-lookup"><span data-stu-id="3afab-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="3afab-303">格式</span><span class="sxs-lookup"><span data-stu-id="3afab-303">Format</span></span>

<span data-ttu-id="3afab-304">两个字母或数字后跟不得含有空格或分隔符的七位数字</span><span class="sxs-lookup"><span data-stu-id="3afab-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3afab-305">模式</span><span class="sxs-lookup"><span data-stu-id="3afab-305">Pattern</span></span>

<span data-ttu-id="3afab-306">两个字母或数字后跟七位数字：</span><span class="sxs-lookup"><span data-stu-id="3afab-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="3afab-307">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="3afab-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="3afab-308">七个数字</span><span class="sxs-lookup"><span data-stu-id="3afab-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3afab-309">校验和</span><span class="sxs-lookup"><span data-stu-id="3afab-309">Checksum</span></span>

<span data-ttu-id="3afab-310">否</span><span class="sxs-lookup"><span data-stu-id="3afab-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3afab-311">定义</span><span class="sxs-lookup"><span data-stu-id="3afab-311">Definition</span></span>

<span data-ttu-id="3afab-312">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3afab-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3afab-313">正则表达式`Regex_ireland_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3afab-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3afab-314">从关键字`Keywords_ireland_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="3afab-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3afab-315">Keywords</span><span class="sxs-lookup"><span data-stu-id="3afab-315">Keywords</span></span>

<span data-ttu-id="3afab-316">| |</span><span class="sxs-lookup"><span data-stu-id="3afab-316"></span></span>
|<span data-ttu-id="3afab-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3afab-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3afab-318">护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-318">passport number</span></span>  <br/> <span data-ttu-id="3afab-319">爱尔兰护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-319">irish passport number</span></span>  <br/> <span data-ttu-id="3afab-320">passport 没有</span><span class="sxs-lookup"><span data-stu-id="3afab-320">passport no</span></span>  <br/> <span data-ttu-id="3afab-321">pas</span><span class="sxs-lookup"><span data-stu-id="3afab-321">pas</span></span>  <br/> <span data-ttu-id="3afab-322">passport</span><span class="sxs-lookup"><span data-stu-id="3afab-322">passport</span></span>  <br/> <span data-ttu-id="3afab-323">passeport</span><span class="sxs-lookup"><span data-stu-id="3afab-323">passeport</span></span>  <br/> <span data-ttu-id="3afab-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="3afab-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="3afab-325">意大利</span><span class="sxs-lookup"><span data-stu-id="3afab-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="3afab-326">格式</span><span class="sxs-lookup"><span data-stu-id="3afab-326">Format</span></span>

<span data-ttu-id="3afab-327">两个字母或数字后跟不得含有空格或分隔符的七位数字</span><span class="sxs-lookup"><span data-stu-id="3afab-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3afab-328">模式</span><span class="sxs-lookup"><span data-stu-id="3afab-328">Pattern</span></span>

<span data-ttu-id="3afab-329">两个字母或数字后跟七位数字：</span><span class="sxs-lookup"><span data-stu-id="3afab-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="3afab-330">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="3afab-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="3afab-331">七个数字</span><span class="sxs-lookup"><span data-stu-id="3afab-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3afab-332">校验和</span><span class="sxs-lookup"><span data-stu-id="3afab-332">Checksum</span></span>

<span data-ttu-id="3afab-333">不适用</span><span class="sxs-lookup"><span data-stu-id="3afab-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3afab-334">定义</span><span class="sxs-lookup"><span data-stu-id="3afab-334">Definition</span></span>

<span data-ttu-id="3afab-335">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3afab-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3afab-336">正则表达式`Regex_italy_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3afab-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3afab-337">从关键字`Keywords_italy_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="3afab-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3afab-338">Keywords</span><span class="sxs-lookup"><span data-stu-id="3afab-338">Keywords</span></span>

<span data-ttu-id="3afab-339">| |</span><span class="sxs-lookup"><span data-stu-id="3afab-339"></span></span>
|<span data-ttu-id="3afab-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3afab-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3afab-341">意大利护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-341">italian passport number</span></span>  <br/> <span data-ttu-id="3afab-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="3afab-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="3afab-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="3afab-343">passaporto</span></span>  <br/> <span data-ttu-id="3afab-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="3afab-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="3afab-345">护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-345">passport number</span></span>  <br/> <span data-ttu-id="3afab-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="3afab-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="3afab-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="3afab-347">passaporto numero</span></span>  <br/> <span data-ttu-id="3afab-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="3afab-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="3afab-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="3afab-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="3afab-350">拉脱维亚</span><span class="sxs-lookup"><span data-stu-id="3afab-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="3afab-351">格式</span><span class="sxs-lookup"><span data-stu-id="3afab-351">Format</span></span>

<span data-ttu-id="3afab-352">两个字母或数字后跟不得含有空格或分隔符的七位数字</span><span class="sxs-lookup"><span data-stu-id="3afab-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3afab-353">模式</span><span class="sxs-lookup"><span data-stu-id="3afab-353">Pattern</span></span>

<span data-ttu-id="3afab-354">两个字母或数字后跟七位数字：</span><span class="sxs-lookup"><span data-stu-id="3afab-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="3afab-355">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="3afab-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="3afab-356">七个数字</span><span class="sxs-lookup"><span data-stu-id="3afab-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3afab-357">校验和</span><span class="sxs-lookup"><span data-stu-id="3afab-357">Checksum</span></span>

<span data-ttu-id="3afab-358">否</span><span class="sxs-lookup"><span data-stu-id="3afab-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3afab-359">定义</span><span class="sxs-lookup"><span data-stu-id="3afab-359">Definition</span></span>

<span data-ttu-id="3afab-360">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3afab-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3afab-361">正则表达式`Regex_latvia_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3afab-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3afab-362">从关键字`Keywords_latvia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="3afab-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3afab-363">Keywords</span><span class="sxs-lookup"><span data-stu-id="3afab-363">Keywords</span></span>

<span data-ttu-id="3afab-364">| |</span><span class="sxs-lookup"><span data-stu-id="3afab-364"></span></span>
|<span data-ttu-id="3afab-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3afab-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3afab-366">护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-366">passport number</span></span>  <br/> <span data-ttu-id="3afab-367">拉脱维亚护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-367">latvian passport number</span></span>  <br/> <span data-ttu-id="3afab-368">passport 没有</span><span class="sxs-lookup"><span data-stu-id="3afab-368">passport no</span></span>  <br/> <span data-ttu-id="3afab-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="3afab-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="3afab-370">立陶宛</span><span class="sxs-lookup"><span data-stu-id="3afab-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="3afab-371">格式</span><span class="sxs-lookup"><span data-stu-id="3afab-371">Format</span></span>

<span data-ttu-id="3afab-372">八个数字或字母不得含有空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3afab-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3afab-373">模式</span><span class="sxs-lookup"><span data-stu-id="3afab-373">Pattern</span></span>

<span data-ttu-id="3afab-374">八个数字或字母 （不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="3afab-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3afab-375">校验和</span><span class="sxs-lookup"><span data-stu-id="3afab-375">Checksum</span></span>

<span data-ttu-id="3afab-376">不适用</span><span class="sxs-lookup"><span data-stu-id="3afab-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3afab-377">定义</span><span class="sxs-lookup"><span data-stu-id="3afab-377">Definition</span></span>

<span data-ttu-id="3afab-378">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3afab-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3afab-379">正则表达式`Regex_lithuania_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3afab-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3afab-380">从关键字`Keywords_lithuania_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="3afab-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3afab-381">Keywords</span><span class="sxs-lookup"><span data-stu-id="3afab-381">Keywords</span></span>

<span data-ttu-id="3afab-382">| |</span><span class="sxs-lookup"><span data-stu-id="3afab-382"></span></span>
|<span data-ttu-id="3afab-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3afab-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3afab-384">护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-384">passport number</span></span>  <br/> <span data-ttu-id="3afab-385">lithunian 护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="3afab-386">passport 没有</span><span class="sxs-lookup"><span data-stu-id="3afab-386">passport no</span></span>  <br/> <span data-ttu-id="3afab-387">paso numeris</span><span class="sxs-lookup"><span data-stu-id="3afab-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="3afab-388">卢森堡</span><span class="sxs-lookup"><span data-stu-id="3afab-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="3afab-389">格式</span><span class="sxs-lookup"><span data-stu-id="3afab-389">Format</span></span>

<span data-ttu-id="3afab-390">八个数字或字母不得含有空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3afab-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3afab-391">模式</span><span class="sxs-lookup"><span data-stu-id="3afab-391">Pattern</span></span>

<span data-ttu-id="3afab-392">八个数字或字母 （不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="3afab-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3afab-393">校验和</span><span class="sxs-lookup"><span data-stu-id="3afab-393">Checksum</span></span>

<span data-ttu-id="3afab-394">否</span><span class="sxs-lookup"><span data-stu-id="3afab-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3afab-395">定义</span><span class="sxs-lookup"><span data-stu-id="3afab-395">Definition</span></span>

<span data-ttu-id="3afab-396">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3afab-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3afab-397">正则表达式`Regex_nation_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3afab-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3afab-398">从关键字`Keywords_nation_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="3afab-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3afab-399">Keywords</span><span class="sxs-lookup"><span data-stu-id="3afab-399">Keywords</span></span>

<span data-ttu-id="3afab-400">| |</span><span class="sxs-lookup"><span data-stu-id="3afab-400"></span></span>
|<span data-ttu-id="3afab-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3afab-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3afab-402">护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-402">passport number</span></span>  <br/> <span data-ttu-id="3afab-403">拉脱维亚护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-403">latvian passport number</span></span>  <br/> <span data-ttu-id="3afab-404">passport 没有</span><span class="sxs-lookup"><span data-stu-id="3afab-404">passport no</span></span>  <br/> <span data-ttu-id="3afab-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="3afab-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="3afab-406">马耳他</span><span class="sxs-lookup"><span data-stu-id="3afab-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="3afab-407">格式</span><span class="sxs-lookup"><span data-stu-id="3afab-407">Format</span></span>

<span data-ttu-id="3afab-408">不含空格或分隔符的七位数字</span><span class="sxs-lookup"><span data-stu-id="3afab-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3afab-409">模式</span><span class="sxs-lookup"><span data-stu-id="3afab-409">Pattern</span></span>

 <span data-ttu-id="3afab-410">七个数字</span><span class="sxs-lookup"><span data-stu-id="3afab-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="3afab-411">校验和</span><span class="sxs-lookup"><span data-stu-id="3afab-411">Checksum</span></span>

<span data-ttu-id="3afab-412">否</span><span class="sxs-lookup"><span data-stu-id="3afab-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3afab-413">定义</span><span class="sxs-lookup"><span data-stu-id="3afab-413">Definition</span></span>

<span data-ttu-id="3afab-414">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3afab-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3afab-415">正则表达式`Regex_malta_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3afab-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3afab-416">从关键字`Keywords_malta_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="3afab-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3afab-417">Keywords</span><span class="sxs-lookup"><span data-stu-id="3afab-417">Keywords</span></span>

<span data-ttu-id="3afab-418">| |</span><span class="sxs-lookup"><span data-stu-id="3afab-418"></span></span>
|<span data-ttu-id="3afab-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3afab-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3afab-420">护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-420">passport number</span></span>  <br/> <span data-ttu-id="3afab-421">马耳他护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-421">maltese passport number</span></span>  <br/> <span data-ttu-id="3afab-422">passport 没有</span><span class="sxs-lookup"><span data-stu-id="3afab-422">passport no</span></span>  <br/> <span data-ttu-id="3afab-423">numru tal passaport</span><span class="sxs-lookup"><span data-stu-id="3afab-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="3afab-424">荷兰</span><span class="sxs-lookup"><span data-stu-id="3afab-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="3afab-425">格式</span><span class="sxs-lookup"><span data-stu-id="3afab-425">Format</span></span>

<span data-ttu-id="3afab-426">九个字母或数字不得含有空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3afab-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3afab-427">模式</span><span class="sxs-lookup"><span data-stu-id="3afab-427">Pattern</span></span>

<span data-ttu-id="3afab-428">九个字母或数字</span><span class="sxs-lookup"><span data-stu-id="3afab-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3afab-429">校验和</span><span class="sxs-lookup"><span data-stu-id="3afab-429">Checksum</span></span>

<span data-ttu-id="3afab-430">不适用</span><span class="sxs-lookup"><span data-stu-id="3afab-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3afab-431">定义</span><span class="sxs-lookup"><span data-stu-id="3afab-431">Definition</span></span>

<span data-ttu-id="3afab-432">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3afab-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3afab-433">正则表达式`Regex_netherlands_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3afab-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3afab-434">从关键字`Keywords_netherlands_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="3afab-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3afab-435">Keywords</span><span class="sxs-lookup"><span data-stu-id="3afab-435">Keywords</span></span>

<span data-ttu-id="3afab-436">| |</span><span class="sxs-lookup"><span data-stu-id="3afab-436"></span></span>
|<span data-ttu-id="3afab-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3afab-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3afab-438">荷兰语护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-438">dutch passport number</span></span>  <br/> <span data-ttu-id="3afab-439">护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-439">passport number</span></span>  <br/> <span data-ttu-id="3afab-440">荷兰护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="3afab-441">nederlanden paspoort nummer</span><span class="sxs-lookup"><span data-stu-id="3afab-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="3afab-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="3afab-442">paspoort</span></span>  <br/> <span data-ttu-id="3afab-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="3afab-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="3afab-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="3afab-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="3afab-445">波兰</span><span class="sxs-lookup"><span data-stu-id="3afab-445">Poland</span></span>

<span data-ttu-id="3afab-446">有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"波兰护照号码"。</span><span class="sxs-lookup"><span data-stu-id="3afab-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="3afab-447">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="3afab-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="3afab-448">格式</span><span class="sxs-lookup"><span data-stu-id="3afab-448">Format</span></span>

<span data-ttu-id="3afab-449">不得含有空格或分隔符六位数字后跟一个字母</span><span class="sxs-lookup"><span data-stu-id="3afab-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3afab-450">模式</span><span class="sxs-lookup"><span data-stu-id="3afab-450">Pattern</span></span>

<span data-ttu-id="3afab-451">包含 6 位数字后跟一个字母：</span><span class="sxs-lookup"><span data-stu-id="3afab-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="3afab-452">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="3afab-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="3afab-453">六个数字</span><span class="sxs-lookup"><span data-stu-id="3afab-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3afab-454">校验和</span><span class="sxs-lookup"><span data-stu-id="3afab-454">Checksum</span></span>

<span data-ttu-id="3afab-455">否</span><span class="sxs-lookup"><span data-stu-id="3afab-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3afab-456">定义</span><span class="sxs-lookup"><span data-stu-id="3afab-456">Definition</span></span>

<span data-ttu-id="3afab-457">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3afab-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3afab-458">正则表达式`Regex_portugal_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3afab-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3afab-459">从关键字`Keywords_portugal_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="3afab-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3afab-460">Keywords</span><span class="sxs-lookup"><span data-stu-id="3afab-460">Keywords</span></span>

<span data-ttu-id="3afab-461">| |</span><span class="sxs-lookup"><span data-stu-id="3afab-461"></span></span>
|<span data-ttu-id="3afab-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3afab-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3afab-463">护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-463">passport number</span></span>  <br/> <span data-ttu-id="3afab-464">葡萄牙语护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-464">portugese passport number</span></span>  <br/> <span data-ttu-id="3afab-465">passport 没有</span><span class="sxs-lookup"><span data-stu-id="3afab-465">passport no</span></span>  <br/> <span data-ttu-id="3afab-466">número 执行 passaporte</span><span class="sxs-lookup"><span data-stu-id="3afab-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="3afab-467">罗马尼亚</span><span class="sxs-lookup"><span data-stu-id="3afab-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="3afab-468">格式</span><span class="sxs-lookup"><span data-stu-id="3afab-468">Format</span></span>

<span data-ttu-id="3afab-469">八个或九个没有空格和分隔符的数字</span><span class="sxs-lookup"><span data-stu-id="3afab-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3afab-470">模式</span><span class="sxs-lookup"><span data-stu-id="3afab-470">Pattern</span></span>

<span data-ttu-id="3afab-471">八个或九个数字</span><span class="sxs-lookup"><span data-stu-id="3afab-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3afab-472">校验和</span><span class="sxs-lookup"><span data-stu-id="3afab-472">Checksum</span></span>

<span data-ttu-id="3afab-473">否</span><span class="sxs-lookup"><span data-stu-id="3afab-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3afab-474">定义</span><span class="sxs-lookup"><span data-stu-id="3afab-474">Definition</span></span>

<span data-ttu-id="3afab-475">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3afab-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3afab-476">正则表达式`Regex_romania_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3afab-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3afab-477">从关键字`Keywords_romania_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="3afab-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3afab-478">Keywords</span><span class="sxs-lookup"><span data-stu-id="3afab-478">Keywords</span></span>

<span data-ttu-id="3afab-479">| |</span><span class="sxs-lookup"><span data-stu-id="3afab-479"></span></span>
|<span data-ttu-id="3afab-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3afab-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3afab-481">护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-481">passport number</span></span>  <br/> <span data-ttu-id="3afab-482">罗马尼亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-482">romanian passport number</span></span>  <br/> <span data-ttu-id="3afab-483">passport 没有</span><span class="sxs-lookup"><span data-stu-id="3afab-483">passport no</span></span>  <br/> <span data-ttu-id="3afab-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="3afab-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="3afab-485">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="3afab-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="3afab-486">格式</span><span class="sxs-lookup"><span data-stu-id="3afab-486">Format</span></span>

<span data-ttu-id="3afab-487">一个数字或字母不得含有空格或分隔符的七位数字后跟</span><span class="sxs-lookup"><span data-stu-id="3afab-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3afab-488">模式</span><span class="sxs-lookup"><span data-stu-id="3afab-488">Pattern</span></span>

<span data-ttu-id="3afab-489">一个数字或字母 （不区分大小写） 七位数字后跟</span><span class="sxs-lookup"><span data-stu-id="3afab-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3afab-490">校验和</span><span class="sxs-lookup"><span data-stu-id="3afab-490">Checksum</span></span>

<span data-ttu-id="3afab-491">否</span><span class="sxs-lookup"><span data-stu-id="3afab-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3afab-492">定义</span><span class="sxs-lookup"><span data-stu-id="3afab-492">Definition</span></span>

<span data-ttu-id="3afab-493">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3afab-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3afab-494">正则表达式`Regex_slovakia_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3afab-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3afab-495">从关键字`Keywords_slovakia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="3afab-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3afab-496">Keywords</span><span class="sxs-lookup"><span data-stu-id="3afab-496">Keywords</span></span>

<span data-ttu-id="3afab-497">| |</span><span class="sxs-lookup"><span data-stu-id="3afab-497"></span></span>
|<span data-ttu-id="3afab-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3afab-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3afab-499">护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-499">passport number</span></span>  <br/> <span data-ttu-id="3afab-500">斯洛伐克语护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="3afab-501">passport 没有</span><span class="sxs-lookup"><span data-stu-id="3afab-501">passport no</span></span>  <br/> <span data-ttu-id="3afab-502">Číslo pasu</span><span class="sxs-lookup"><span data-stu-id="3afab-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="3afab-503">斯诺文尼亚</span><span class="sxs-lookup"><span data-stu-id="3afab-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="3afab-504">格式</span><span class="sxs-lookup"><span data-stu-id="3afab-504">Format</span></span>

<span data-ttu-id="3afab-505">不得含有空格或分隔符的七位数字后跟两个字母</span><span class="sxs-lookup"><span data-stu-id="3afab-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3afab-506">模式</span><span class="sxs-lookup"><span data-stu-id="3afab-506">Pattern</span></span>

<span data-ttu-id="3afab-507">七位数字后跟两个字母：</span><span class="sxs-lookup"><span data-stu-id="3afab-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="3afab-508">字母"P"</span><span class="sxs-lookup"><span data-stu-id="3afab-508">The letter "P"</span></span>
    
- <span data-ttu-id="3afab-509">一个大写字母</span><span class="sxs-lookup"><span data-stu-id="3afab-509">One uppercase letter</span></span>
    
- <span data-ttu-id="3afab-510">七个数字</span><span class="sxs-lookup"><span data-stu-id="3afab-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3afab-511">校验和</span><span class="sxs-lookup"><span data-stu-id="3afab-511">Checksum</span></span>

<span data-ttu-id="3afab-512">否</span><span class="sxs-lookup"><span data-stu-id="3afab-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3afab-513">定义</span><span class="sxs-lookup"><span data-stu-id="3afab-513">Definition</span></span>

<span data-ttu-id="3afab-514">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3afab-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3afab-515">正则表达式`Regex_slovenia_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3afab-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3afab-516">从关键字`Keywords_slovenia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="3afab-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3afab-517">Keywords</span><span class="sxs-lookup"><span data-stu-id="3afab-517">Keywords</span></span>

<span data-ttu-id="3afab-518">| |</span><span class="sxs-lookup"><span data-stu-id="3afab-518"></span></span>
|<span data-ttu-id="3afab-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3afab-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3afab-520">护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-520">passport number</span></span>  <br/> <span data-ttu-id="3afab-521">斯洛文尼亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="3afab-522">passport 没有</span><span class="sxs-lookup"><span data-stu-id="3afab-522">passport no</span></span>  <br/> <span data-ttu-id="3afab-523">Številka potnega 可变</span><span class="sxs-lookup"><span data-stu-id="3afab-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="3afab-524">西班牙</span><span class="sxs-lookup"><span data-stu-id="3afab-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="3afab-525">格式</span><span class="sxs-lookup"><span data-stu-id="3afab-525">Format</span></span>

<span data-ttu-id="3afab-526">字母或数字，没有空格或分隔符的八个字符或九个字符组合</span><span class="sxs-lookup"><span data-stu-id="3afab-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3afab-527">模式</span><span class="sxs-lookup"><span data-stu-id="3afab-527">Pattern</span></span>

<span data-ttu-id="3afab-528">字母和数字的八个字符或九个字符组合：</span><span class="sxs-lookup"><span data-stu-id="3afab-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="3afab-529">两个数字或字母</span><span class="sxs-lookup"><span data-stu-id="3afab-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="3afab-530">一个数字或字母 （可选）</span><span class="sxs-lookup"><span data-stu-id="3afab-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="3afab-531">六个数字</span><span class="sxs-lookup"><span data-stu-id="3afab-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3afab-532">校验和</span><span class="sxs-lookup"><span data-stu-id="3afab-532">Checksum</span></span>

<span data-ttu-id="3afab-533">不适用</span><span class="sxs-lookup"><span data-stu-id="3afab-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3afab-534">定义</span><span class="sxs-lookup"><span data-stu-id="3afab-534">Definition</span></span>

<span data-ttu-id="3afab-535">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3afab-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3afab-536">正则表达式`Regex_spain_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3afab-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3afab-537">从关键字`Keywords_spain_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="3afab-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3afab-538">Keywords</span><span class="sxs-lookup"><span data-stu-id="3afab-538">Keywords</span></span>

<span data-ttu-id="3afab-539">| |</span><span class="sxs-lookup"><span data-stu-id="3afab-539"></span></span>
|<span data-ttu-id="3afab-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3afab-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3afab-541">passport</span><span class="sxs-lookup"><span data-stu-id="3afab-541">passport</span></span>  <br/> <span data-ttu-id="3afab-542">西班牙 passport</span><span class="sxs-lookup"><span data-stu-id="3afab-542">spain passport</span></span>  <br/> <span data-ttu-id="3afab-543">passport 书籍</span><span class="sxs-lookup"><span data-stu-id="3afab-543">passport book</span></span>  <br/> <span data-ttu-id="3afab-544">护照号码</span><span class="sxs-lookup"><span data-stu-id="3afab-544">passport number</span></span>  <br/> <span data-ttu-id="3afab-545">passport 没有</span><span class="sxs-lookup"><span data-stu-id="3afab-545">passport no</span></span>  <br/> <span data-ttu-id="3afab-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="3afab-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="3afab-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="3afab-547">número pasaporte</span></span>  <br/> <span data-ttu-id="3afab-548">españa pasaporte</span><span class="sxs-lookup"><span data-stu-id="3afab-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="3afab-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="3afab-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="3afab-550">瑞典</span><span class="sxs-lookup"><span data-stu-id="3afab-550">Sweden</span></span>

<span data-ttu-id="3afab-551">有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"瑞典护照号码"。</span><span class="sxs-lookup"><span data-stu-id="3afab-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="3afab-552">英国</span><span class="sxs-lookup"><span data-stu-id="3afab-552">UK</span></span>

<span data-ttu-id="3afab-p103">有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"美国/英国护照号码"。</span><span class="sxs-lookup"><span data-stu-id="3afab-p103">For details, see the section "U.S. / U.K. Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3afab-555">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3afab-555">See also</span></span>

[<span data-ttu-id="3afab-556">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="3afab-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

