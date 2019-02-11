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
ms.openlocfilehash: 7a7fc1ff826aab4096c46535686eb0fd68173c6f
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "25840321"
---
# <a name="eu-passport-number"></a><span data-ttu-id="1fa82-104">欧盟护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-104">EU Passport Number</span></span>

<span data-ttu-id="1fa82-p102">本主题演示数据丢失防护 (DLP) 策略检测到的欧盟护照号码敏感信息类型时的寻找。此敏感信息类型定义不同的模式、 关键字和每个国家/地区其他证据。</span><span class="sxs-lookup"><span data-stu-id="1fa82-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="1fa82-107">奥地利</span><span class="sxs-lookup"><span data-stu-id="1fa82-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="1fa82-108">格式</span><span class="sxs-lookup"><span data-stu-id="1fa82-108">Format</span></span>

<span data-ttu-id="1fa82-109">可选的空间和七位数字后跟一个字母</span><span class="sxs-lookup"><span data-stu-id="1fa82-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1fa82-110">模式</span><span class="sxs-lookup"><span data-stu-id="1fa82-110">Pattern</span></span>

<span data-ttu-id="1fa82-111">一个字母、 七个数字和一个空格的组合：</span><span class="sxs-lookup"><span data-stu-id="1fa82-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="1fa82-112">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="1fa82-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="1fa82-113">一个空格 （可选）</span><span class="sxs-lookup"><span data-stu-id="1fa82-113">One space (optional)</span></span>
    
- <span data-ttu-id="1fa82-114">七个数字</span><span class="sxs-lookup"><span data-stu-id="1fa82-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1fa82-115">校验和</span><span class="sxs-lookup"><span data-stu-id="1fa82-115">Checksum</span></span>

<span data-ttu-id="1fa82-116">不适用</span><span class="sxs-lookup"><span data-stu-id="1fa82-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1fa82-117">定义</span><span class="sxs-lookup"><span data-stu-id="1fa82-117">Definition</span></span>

<span data-ttu-id="1fa82-118">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1fa82-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1fa82-119">正则表达式`Regex_austria_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1fa82-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1fa82-120">从关键字`Keywords_austria_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1fa82-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1fa82-121">关键字</span><span class="sxs-lookup"><span data-stu-id="1fa82-121">Keywords</span></span>

<span data-ttu-id="1fa82-122">| |</span><span class="sxs-lookup"><span data-stu-id="1fa82-122"></span></span>
|<span data-ttu-id="1fa82-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1fa82-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1fa82-124">护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-124">passport number</span></span>  <br/> <span data-ttu-id="1fa82-125">奥地利护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-125">austrian passport number</span></span>  <br/> <span data-ttu-id="1fa82-126">passport 没有</span><span class="sxs-lookup"><span data-stu-id="1fa82-126">passport no</span></span>  <br/> <span data-ttu-id="1fa82-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="1fa82-127">reisepass</span></span>  <br/> <span data-ttu-id="1fa82-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="1fa82-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="1fa82-129">比利时</span><span class="sxs-lookup"><span data-stu-id="1fa82-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="1fa82-130">格式</span><span class="sxs-lookup"><span data-stu-id="1fa82-130">Format</span></span>

<span data-ttu-id="1fa82-131">不得含有空格或分隔符六位数字后跟两个字母</span><span class="sxs-lookup"><span data-stu-id="1fa82-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1fa82-132">模式</span><span class="sxs-lookup"><span data-stu-id="1fa82-132">Pattern</span></span>

<span data-ttu-id="1fa82-133">两个字母和包含 6 位数字后跟</span><span class="sxs-lookup"><span data-stu-id="1fa82-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1fa82-134">校验和</span><span class="sxs-lookup"><span data-stu-id="1fa82-134">Checksum</span></span>

<span data-ttu-id="1fa82-135">不适用</span><span class="sxs-lookup"><span data-stu-id="1fa82-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1fa82-136">定义</span><span class="sxs-lookup"><span data-stu-id="1fa82-136">Definition</span></span>

<span data-ttu-id="1fa82-137">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1fa82-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1fa82-138">正则表达式`Regex_belgium_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1fa82-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1fa82-139">从关键字`Keywords_belgium_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1fa82-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1fa82-140">关键字</span><span class="sxs-lookup"><span data-stu-id="1fa82-140">Keywords</span></span>

<span data-ttu-id="1fa82-141">| |</span><span class="sxs-lookup"><span data-stu-id="1fa82-141"></span></span>
|<span data-ttu-id="1fa82-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1fa82-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1fa82-143">护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-143">passport number</span></span>  <br/> <span data-ttu-id="1fa82-144">比利时护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-144">belgian passport number</span></span>  <br/> <span data-ttu-id="1fa82-145">passport 没有</span><span class="sxs-lookup"><span data-stu-id="1fa82-145">passport no</span></span>  <br/> <span data-ttu-id="1fa82-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="1fa82-146">paspoort</span></span>  <br/> <span data-ttu-id="1fa82-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="1fa82-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="1fa82-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="1fa82-148">reisepass kein</span></span>  <br/> <span data-ttu-id="1fa82-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="1fa82-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="1fa82-150">保加利亚</span><span class="sxs-lookup"><span data-stu-id="1fa82-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="1fa82-151">格式</span><span class="sxs-lookup"><span data-stu-id="1fa82-151">Format</span></span>

<span data-ttu-id="1fa82-152">没有空格和分隔符的九个数字</span><span class="sxs-lookup"><span data-stu-id="1fa82-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1fa82-153">模式</span><span class="sxs-lookup"><span data-stu-id="1fa82-153">Pattern</span></span>

 <span data-ttu-id="1fa82-154">九个数字</span><span class="sxs-lookup"><span data-stu-id="1fa82-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="1fa82-155">校验和</span><span class="sxs-lookup"><span data-stu-id="1fa82-155">Checksum</span></span>

<span data-ttu-id="1fa82-156">否</span><span class="sxs-lookup"><span data-stu-id="1fa82-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1fa82-157">定义</span><span class="sxs-lookup"><span data-stu-id="1fa82-157">Definition</span></span>

<span data-ttu-id="1fa82-158">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1fa82-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1fa82-159">正则表达式`Regex_bulgaria_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1fa82-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1fa82-160">从关键字`Keywords_bulgaria_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1fa82-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1fa82-161">关键字</span><span class="sxs-lookup"><span data-stu-id="1fa82-161">Keywords</span></span>

<span data-ttu-id="1fa82-162">| |</span><span class="sxs-lookup"><span data-stu-id="1fa82-162"></span></span>
|<span data-ttu-id="1fa82-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1fa82-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1fa82-164">护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-164">passport number</span></span>  <br/> <span data-ttu-id="1fa82-165">保加利亚护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="1fa82-166">passport 没有</span><span class="sxs-lookup"><span data-stu-id="1fa82-166">passport no</span></span>  <br/> <span data-ttu-id="1fa82-167">НОМЕР НА ПАСПОРТА</span><span class="sxs-lookup"><span data-stu-id="1fa82-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="1fa82-168">克罗地亚</span><span class="sxs-lookup"><span data-stu-id="1fa82-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="1fa82-169">格式</span><span class="sxs-lookup"><span data-stu-id="1fa82-169">Format</span></span>

<span data-ttu-id="1fa82-170">没有空格和分隔符的九个数字</span><span class="sxs-lookup"><span data-stu-id="1fa82-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1fa82-171">模式</span><span class="sxs-lookup"><span data-stu-id="1fa82-171">Pattern</span></span>

 <span data-ttu-id="1fa82-172">九个数字</span><span class="sxs-lookup"><span data-stu-id="1fa82-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="1fa82-173">校验和</span><span class="sxs-lookup"><span data-stu-id="1fa82-173">Checksum</span></span>

<span data-ttu-id="1fa82-174">否</span><span class="sxs-lookup"><span data-stu-id="1fa82-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1fa82-175">定义</span><span class="sxs-lookup"><span data-stu-id="1fa82-175">Definition</span></span>

<span data-ttu-id="1fa82-176">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1fa82-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1fa82-177">正则表达式`Regex_croatia_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1fa82-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1fa82-178">从关键字`Keywords_croatia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1fa82-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1fa82-179">关键字</span><span class="sxs-lookup"><span data-stu-id="1fa82-179">Keywords</span></span>

<span data-ttu-id="1fa82-180">| |</span><span class="sxs-lookup"><span data-stu-id="1fa82-180"></span></span>
|<span data-ttu-id="1fa82-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1fa82-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1fa82-182">护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-182">passport number</span></span>  <br/> <span data-ttu-id="1fa82-183">克罗地亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-183">croatian passport number</span></span>  <br/> <span data-ttu-id="1fa82-184">passport 没有</span><span class="sxs-lookup"><span data-stu-id="1fa82-184">passport no</span></span>  <br/> <span data-ttu-id="1fa82-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="1fa82-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="1fa82-186">塞浦路斯</span><span class="sxs-lookup"><span data-stu-id="1fa82-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="1fa82-187">格式</span><span class="sxs-lookup"><span data-stu-id="1fa82-187">Format</span></span>

<span data-ttu-id="1fa82-188">不得含有空格或分隔符 6-8 位数字后跟一个字母</span><span class="sxs-lookup"><span data-stu-id="1fa82-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1fa82-189">模式</span><span class="sxs-lookup"><span data-stu-id="1fa82-189">Pattern</span></span>

<span data-ttu-id="1fa82-190">6 到 8 位数字后跟一个字母</span><span class="sxs-lookup"><span data-stu-id="1fa82-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1fa82-191">校验和</span><span class="sxs-lookup"><span data-stu-id="1fa82-191">Checksum</span></span>

<span data-ttu-id="1fa82-192">否</span><span class="sxs-lookup"><span data-stu-id="1fa82-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1fa82-193">定义</span><span class="sxs-lookup"><span data-stu-id="1fa82-193">Definition</span></span>

<span data-ttu-id="1fa82-194">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1fa82-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1fa82-195">正则表达式`Regex_cyprus_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1fa82-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1fa82-196">从关键字`Keywords_cyprus_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1fa82-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1fa82-197">关键字</span><span class="sxs-lookup"><span data-stu-id="1fa82-197">Keywords</span></span>

<span data-ttu-id="1fa82-198">| |</span><span class="sxs-lookup"><span data-stu-id="1fa82-198"></span></span>
|<span data-ttu-id="1fa82-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1fa82-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1fa82-200">护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-200">passport number</span></span>  <br/> <span data-ttu-id="1fa82-201">塞浦路斯护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="1fa82-202">passport 没有</span><span class="sxs-lookup"><span data-stu-id="1fa82-202">passport no</span></span>  <br/> <span data-ttu-id="1fa82-203">ΑΡΙΘΜΌ ΔΙΑΒΑΤΗΡΊΟΥ</span><span class="sxs-lookup"><span data-stu-id="1fa82-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="1fa82-204">捷克共和国</span><span class="sxs-lookup"><span data-stu-id="1fa82-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="1fa82-205">格式</span><span class="sxs-lookup"><span data-stu-id="1fa82-205">Format</span></span>

<span data-ttu-id="1fa82-206">八个不含空格或分隔符的数字</span><span class="sxs-lookup"><span data-stu-id="1fa82-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1fa82-207">模式</span><span class="sxs-lookup"><span data-stu-id="1fa82-207">Pattern</span></span>

<span data-ttu-id="1fa82-208">八个不含空格或分隔符的数字</span><span class="sxs-lookup"><span data-stu-id="1fa82-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1fa82-209">校验和</span><span class="sxs-lookup"><span data-stu-id="1fa82-209">Checksum</span></span>

<span data-ttu-id="1fa82-210">否</span><span class="sxs-lookup"><span data-stu-id="1fa82-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1fa82-211">定义</span><span class="sxs-lookup"><span data-stu-id="1fa82-211">Definition</span></span>

<span data-ttu-id="1fa82-212">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1fa82-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1fa82-213">正则表达式`Regex_czech_republic_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1fa82-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1fa82-214">从关键字`Keywords_czech_republic_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1fa82-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1fa82-215">关键字</span><span class="sxs-lookup"><span data-stu-id="1fa82-215">Keywords</span></span>

<span data-ttu-id="1fa82-216">| |</span><span class="sxs-lookup"><span data-stu-id="1fa82-216"></span></span>
|<span data-ttu-id="1fa82-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1fa82-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1fa82-218">护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-218">passport number</span></span>  <br/> <span data-ttu-id="1fa82-219">捷克护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-219">czech passport number</span></span>  <br/> <span data-ttu-id="1fa82-220">passport 没有</span><span class="sxs-lookup"><span data-stu-id="1fa82-220">passport no</span></span>  <br/> <span data-ttu-id="1fa82-221">cestovní pas</span><span class="sxs-lookup"><span data-stu-id="1fa82-221">cestovní pas</span></span>  <br/> <span data-ttu-id="1fa82-222">pas</span><span class="sxs-lookup"><span data-stu-id="1fa82-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="1fa82-223">丹麦</span><span class="sxs-lookup"><span data-stu-id="1fa82-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="1fa82-224">格式</span><span class="sxs-lookup"><span data-stu-id="1fa82-224">Format</span></span>

<span data-ttu-id="1fa82-225">没有空格和分隔符的九个数字</span><span class="sxs-lookup"><span data-stu-id="1fa82-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1fa82-226">模式</span><span class="sxs-lookup"><span data-stu-id="1fa82-226">Pattern</span></span>

 <span data-ttu-id="1fa82-227">九个数字</span><span class="sxs-lookup"><span data-stu-id="1fa82-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="1fa82-228">校验和</span><span class="sxs-lookup"><span data-stu-id="1fa82-228">Checksum</span></span>

<span data-ttu-id="1fa82-229">否</span><span class="sxs-lookup"><span data-stu-id="1fa82-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1fa82-230">定义</span><span class="sxs-lookup"><span data-stu-id="1fa82-230">Definition</span></span>

<span data-ttu-id="1fa82-231">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1fa82-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1fa82-232">正则表达式`Regex_denmark_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1fa82-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1fa82-233">从关键字`Keywords_denmark_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1fa82-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1fa82-234">关键字</span><span class="sxs-lookup"><span data-stu-id="1fa82-234">Keywords</span></span>

<span data-ttu-id="1fa82-235">| |</span><span class="sxs-lookup"><span data-stu-id="1fa82-235"></span></span>
|<span data-ttu-id="1fa82-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1fa82-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1fa82-237">护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-237">passport number</span></span>  <br/> <span data-ttu-id="1fa82-238">丹麦语护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-238">danish passport number</span></span>  <br/> <span data-ttu-id="1fa82-239">passport 没有</span><span class="sxs-lookup"><span data-stu-id="1fa82-239">passport no</span></span>  <br/> <span data-ttu-id="1fa82-240">pas</span><span class="sxs-lookup"><span data-stu-id="1fa82-240">pas</span></span>  <br/> <span data-ttu-id="1fa82-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="1fa82-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="1fa82-242">爱沙尼亚</span><span class="sxs-lookup"><span data-stu-id="1fa82-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="1fa82-243">格式</span><span class="sxs-lookup"><span data-stu-id="1fa82-243">Format</span></span>

<span data-ttu-id="1fa82-244">不得含有空格或分隔符的七位数字后跟一个字母</span><span class="sxs-lookup"><span data-stu-id="1fa82-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1fa82-245">模式</span><span class="sxs-lookup"><span data-stu-id="1fa82-245">Pattern</span></span>

<span data-ttu-id="1fa82-246">七位数字后跟一个字母</span><span class="sxs-lookup"><span data-stu-id="1fa82-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1fa82-247">校验和</span><span class="sxs-lookup"><span data-stu-id="1fa82-247">Checksum</span></span>

<span data-ttu-id="1fa82-248">否</span><span class="sxs-lookup"><span data-stu-id="1fa82-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1fa82-249">定义</span><span class="sxs-lookup"><span data-stu-id="1fa82-249">Definition</span></span>

<span data-ttu-id="1fa82-250">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1fa82-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1fa82-251">正则表达式`Regex_estonia_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1fa82-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1fa82-252">从关键字`Keywords_estonia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1fa82-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1fa82-253">关键字</span><span class="sxs-lookup"><span data-stu-id="1fa82-253">Keywords</span></span>

<span data-ttu-id="1fa82-254">| |</span><span class="sxs-lookup"><span data-stu-id="1fa82-254"></span></span>
|<span data-ttu-id="1fa82-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1fa82-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1fa82-256">护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-256">passport number</span></span>  <br/> <span data-ttu-id="1fa82-257">爱沙尼亚护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-257">estonian passport number</span></span>  <br/> <span data-ttu-id="1fa82-258">passport 没有</span><span class="sxs-lookup"><span data-stu-id="1fa82-258">passport no</span></span>  <br/> <span data-ttu-id="1fa82-259">eesti kodaniku 传递</span><span class="sxs-lookup"><span data-stu-id="1fa82-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="1fa82-260">芬兰</span><span class="sxs-lookup"><span data-stu-id="1fa82-260">Finland</span></span>

<span data-ttu-id="1fa82-261">有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"芬兰护照号码"。</span><span class="sxs-lookup"><span data-stu-id="1fa82-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="1fa82-262">法国</span><span class="sxs-lookup"><span data-stu-id="1fa82-262">France</span></span>

<span data-ttu-id="1fa82-263">有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"法国护照号码"。</span><span class="sxs-lookup"><span data-stu-id="1fa82-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="1fa82-264">德国</span><span class="sxs-lookup"><span data-stu-id="1fa82-264">Germany</span></span>

<span data-ttu-id="1fa82-265">有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"德国护照号码"。</span><span class="sxs-lookup"><span data-stu-id="1fa82-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="1fa82-266">希腊</span><span class="sxs-lookup"><span data-stu-id="1fa82-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="1fa82-267">格式</span><span class="sxs-lookup"><span data-stu-id="1fa82-267">Format</span></span>

<span data-ttu-id="1fa82-268">不得含有空格或分隔符的七位数字后跟两个字母</span><span class="sxs-lookup"><span data-stu-id="1fa82-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1fa82-269">模式</span><span class="sxs-lookup"><span data-stu-id="1fa82-269">Pattern</span></span>

<span data-ttu-id="1fa82-270">两个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="1fa82-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1fa82-271">校验和</span><span class="sxs-lookup"><span data-stu-id="1fa82-271">Checksum</span></span>

<span data-ttu-id="1fa82-272">否</span><span class="sxs-lookup"><span data-stu-id="1fa82-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1fa82-273">定义</span><span class="sxs-lookup"><span data-stu-id="1fa82-273">Definition</span></span>

<span data-ttu-id="1fa82-274">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1fa82-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1fa82-275">正则表达式`Regex_greece_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1fa82-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1fa82-276">从关键字`Keywords_greece_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1fa82-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1fa82-277">关键字</span><span class="sxs-lookup"><span data-stu-id="1fa82-277">Keywords</span></span>

<span data-ttu-id="1fa82-278">| |</span><span class="sxs-lookup"><span data-stu-id="1fa82-278"></span></span>
|<span data-ttu-id="1fa82-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1fa82-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1fa82-280">护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-280">passport number</span></span>  <br/> <span data-ttu-id="1fa82-281">希腊语护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-281">greek passport number</span></span>  <br/> <span data-ttu-id="1fa82-282">passport 没有</span><span class="sxs-lookup"><span data-stu-id="1fa82-282">passport no</span></span>  <br/> <span data-ttu-id="1fa82-283">ΔΙΑΒΑΤΗΡΙΟ</span><span class="sxs-lookup"><span data-stu-id="1fa82-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="1fa82-284">匈牙利</span><span class="sxs-lookup"><span data-stu-id="1fa82-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="1fa82-285">格式</span><span class="sxs-lookup"><span data-stu-id="1fa82-285">Format</span></span>

<span data-ttu-id="1fa82-286">不得含有空格或分隔符的六个或七位数字后跟两个字母</span><span class="sxs-lookup"><span data-stu-id="1fa82-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1fa82-287">模式</span><span class="sxs-lookup"><span data-stu-id="1fa82-287">Pattern</span></span>

<span data-ttu-id="1fa82-288">六个或七位数字后跟两个字母</span><span class="sxs-lookup"><span data-stu-id="1fa82-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1fa82-289">校验和</span><span class="sxs-lookup"><span data-stu-id="1fa82-289">Checksum</span></span>

<span data-ttu-id="1fa82-290">否</span><span class="sxs-lookup"><span data-stu-id="1fa82-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1fa82-291">定义</span><span class="sxs-lookup"><span data-stu-id="1fa82-291">Definition</span></span>

<span data-ttu-id="1fa82-292">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1fa82-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1fa82-293">正则表达式`Regex_hungary_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1fa82-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1fa82-294">从关键字`Keywords_hungary_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1fa82-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1fa82-295">关键字</span><span class="sxs-lookup"><span data-stu-id="1fa82-295">Keywords</span></span>

<span data-ttu-id="1fa82-296">| |</span><span class="sxs-lookup"><span data-stu-id="1fa82-296"></span></span>
|<span data-ttu-id="1fa82-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1fa82-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1fa82-298">护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-298">passport number</span></span>  <br/> <span data-ttu-id="1fa82-299">匈牙利语护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="1fa82-300">passport 没有</span><span class="sxs-lookup"><span data-stu-id="1fa82-300">passport no</span></span>  <br/> <span data-ttu-id="1fa82-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="1fa82-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="1fa82-302">Ireland</span><span class="sxs-lookup"><span data-stu-id="1fa82-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="1fa82-303">格式</span><span class="sxs-lookup"><span data-stu-id="1fa82-303">Format</span></span>

<span data-ttu-id="1fa82-304">两个字母或数字后跟不得含有空格或分隔符的七位数字</span><span class="sxs-lookup"><span data-stu-id="1fa82-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1fa82-305">模式</span><span class="sxs-lookup"><span data-stu-id="1fa82-305">Pattern</span></span>

<span data-ttu-id="1fa82-306">两个字母或数字后跟七位数字：</span><span class="sxs-lookup"><span data-stu-id="1fa82-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="1fa82-307">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="1fa82-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="1fa82-308">七个数字</span><span class="sxs-lookup"><span data-stu-id="1fa82-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1fa82-309">校验和</span><span class="sxs-lookup"><span data-stu-id="1fa82-309">Checksum</span></span>

<span data-ttu-id="1fa82-310">否</span><span class="sxs-lookup"><span data-stu-id="1fa82-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1fa82-311">定义</span><span class="sxs-lookup"><span data-stu-id="1fa82-311">Definition</span></span>

<span data-ttu-id="1fa82-312">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1fa82-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1fa82-313">正则表达式`Regex_ireland_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1fa82-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1fa82-314">从关键字`Keywords_ireland_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1fa82-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1fa82-315">关键字</span><span class="sxs-lookup"><span data-stu-id="1fa82-315">Keywords</span></span>

<span data-ttu-id="1fa82-316">| |</span><span class="sxs-lookup"><span data-stu-id="1fa82-316"></span></span>
|<span data-ttu-id="1fa82-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1fa82-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1fa82-318">护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-318">passport number</span></span>  <br/> <span data-ttu-id="1fa82-319">爱尔兰护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-319">irish passport number</span></span>  <br/> <span data-ttu-id="1fa82-320">passport 没有</span><span class="sxs-lookup"><span data-stu-id="1fa82-320">passport no</span></span>  <br/> <span data-ttu-id="1fa82-321">pas</span><span class="sxs-lookup"><span data-stu-id="1fa82-321">pas</span></span>  <br/> <span data-ttu-id="1fa82-322">passport</span><span class="sxs-lookup"><span data-stu-id="1fa82-322">passport</span></span>  <br/> <span data-ttu-id="1fa82-323">passeport</span><span class="sxs-lookup"><span data-stu-id="1fa82-323">passeport</span></span>  <br/> <span data-ttu-id="1fa82-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="1fa82-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="1fa82-325">意大利</span><span class="sxs-lookup"><span data-stu-id="1fa82-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="1fa82-326">格式</span><span class="sxs-lookup"><span data-stu-id="1fa82-326">Format</span></span>

<span data-ttu-id="1fa82-327">两个字母或数字后跟不得含有空格或分隔符的七位数字</span><span class="sxs-lookup"><span data-stu-id="1fa82-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1fa82-328">模式</span><span class="sxs-lookup"><span data-stu-id="1fa82-328">Pattern</span></span>

<span data-ttu-id="1fa82-329">两个字母或数字后跟七位数字：</span><span class="sxs-lookup"><span data-stu-id="1fa82-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="1fa82-330">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="1fa82-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="1fa82-331">七个数字</span><span class="sxs-lookup"><span data-stu-id="1fa82-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1fa82-332">校验和</span><span class="sxs-lookup"><span data-stu-id="1fa82-332">Checksum</span></span>

<span data-ttu-id="1fa82-333">不适用</span><span class="sxs-lookup"><span data-stu-id="1fa82-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1fa82-334">定义</span><span class="sxs-lookup"><span data-stu-id="1fa82-334">Definition</span></span>

<span data-ttu-id="1fa82-335">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1fa82-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1fa82-336">正则表达式`Regex_italy_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1fa82-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1fa82-337">从关键字`Keywords_italy_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1fa82-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1fa82-338">关键字</span><span class="sxs-lookup"><span data-stu-id="1fa82-338">Keywords</span></span>

<span data-ttu-id="1fa82-339">| |</span><span class="sxs-lookup"><span data-stu-id="1fa82-339"></span></span>
|<span data-ttu-id="1fa82-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1fa82-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1fa82-341">意大利护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-341">italian passport number</span></span>  <br/> <span data-ttu-id="1fa82-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="1fa82-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="1fa82-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="1fa82-343">passaporto</span></span>  <br/> <span data-ttu-id="1fa82-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="1fa82-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="1fa82-345">护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-345">passport number</span></span>  <br/> <span data-ttu-id="1fa82-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="1fa82-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="1fa82-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="1fa82-347">passaporto numero</span></span>  <br/> <span data-ttu-id="1fa82-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="1fa82-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="1fa82-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="1fa82-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="1fa82-350">拉脱维亚</span><span class="sxs-lookup"><span data-stu-id="1fa82-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="1fa82-351">格式</span><span class="sxs-lookup"><span data-stu-id="1fa82-351">Format</span></span>

<span data-ttu-id="1fa82-352">两个字母或数字后跟不得含有空格或分隔符的七位数字</span><span class="sxs-lookup"><span data-stu-id="1fa82-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1fa82-353">模式</span><span class="sxs-lookup"><span data-stu-id="1fa82-353">Pattern</span></span>

<span data-ttu-id="1fa82-354">两个字母或数字后跟七位数字：</span><span class="sxs-lookup"><span data-stu-id="1fa82-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="1fa82-355">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="1fa82-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="1fa82-356">七个数字</span><span class="sxs-lookup"><span data-stu-id="1fa82-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1fa82-357">校验和</span><span class="sxs-lookup"><span data-stu-id="1fa82-357">Checksum</span></span>

<span data-ttu-id="1fa82-358">否</span><span class="sxs-lookup"><span data-stu-id="1fa82-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1fa82-359">定义</span><span class="sxs-lookup"><span data-stu-id="1fa82-359">Definition</span></span>

<span data-ttu-id="1fa82-360">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1fa82-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1fa82-361">正则表达式`Regex_latvia_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1fa82-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1fa82-362">从关键字`Keywords_latvia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1fa82-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1fa82-363">关键字</span><span class="sxs-lookup"><span data-stu-id="1fa82-363">Keywords</span></span>

<span data-ttu-id="1fa82-364">| |</span><span class="sxs-lookup"><span data-stu-id="1fa82-364"></span></span>
|<span data-ttu-id="1fa82-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1fa82-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1fa82-366">护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-366">passport number</span></span>  <br/> <span data-ttu-id="1fa82-367">拉脱维亚护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-367">latvian passport number</span></span>  <br/> <span data-ttu-id="1fa82-368">passport 没有</span><span class="sxs-lookup"><span data-stu-id="1fa82-368">passport no</span></span>  <br/> <span data-ttu-id="1fa82-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="1fa82-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="1fa82-370">立陶宛</span><span class="sxs-lookup"><span data-stu-id="1fa82-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="1fa82-371">格式</span><span class="sxs-lookup"><span data-stu-id="1fa82-371">Format</span></span>

<span data-ttu-id="1fa82-372">八个数字或字母不得含有空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="1fa82-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1fa82-373">模式</span><span class="sxs-lookup"><span data-stu-id="1fa82-373">Pattern</span></span>

<span data-ttu-id="1fa82-374">八个数字或字母 （不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="1fa82-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1fa82-375">校验和</span><span class="sxs-lookup"><span data-stu-id="1fa82-375">Checksum</span></span>

<span data-ttu-id="1fa82-376">不适用</span><span class="sxs-lookup"><span data-stu-id="1fa82-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1fa82-377">定义</span><span class="sxs-lookup"><span data-stu-id="1fa82-377">Definition</span></span>

<span data-ttu-id="1fa82-378">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1fa82-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1fa82-379">正则表达式`Regex_lithuania_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1fa82-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1fa82-380">从关键字`Keywords_lithuania_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1fa82-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1fa82-381">关键字</span><span class="sxs-lookup"><span data-stu-id="1fa82-381">Keywords</span></span>

<span data-ttu-id="1fa82-382">| |</span><span class="sxs-lookup"><span data-stu-id="1fa82-382"></span></span>
|<span data-ttu-id="1fa82-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1fa82-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1fa82-384">护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-384">passport number</span></span>  <br/> <span data-ttu-id="1fa82-385">lithunian 护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="1fa82-386">passport 没有</span><span class="sxs-lookup"><span data-stu-id="1fa82-386">passport no</span></span>  <br/> <span data-ttu-id="1fa82-387">paso numeris</span><span class="sxs-lookup"><span data-stu-id="1fa82-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="1fa82-388">卢森堡</span><span class="sxs-lookup"><span data-stu-id="1fa82-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="1fa82-389">格式</span><span class="sxs-lookup"><span data-stu-id="1fa82-389">Format</span></span>

<span data-ttu-id="1fa82-390">八个数字或字母不得含有空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="1fa82-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1fa82-391">模式</span><span class="sxs-lookup"><span data-stu-id="1fa82-391">Pattern</span></span>

<span data-ttu-id="1fa82-392">八个数字或字母 （不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="1fa82-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1fa82-393">校验和</span><span class="sxs-lookup"><span data-stu-id="1fa82-393">Checksum</span></span>

<span data-ttu-id="1fa82-394">否</span><span class="sxs-lookup"><span data-stu-id="1fa82-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1fa82-395">定义</span><span class="sxs-lookup"><span data-stu-id="1fa82-395">Definition</span></span>

<span data-ttu-id="1fa82-396">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1fa82-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1fa82-397">正则表达式`Regex_nation_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1fa82-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1fa82-398">从关键字`Keywords_nation_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1fa82-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1fa82-399">关键字</span><span class="sxs-lookup"><span data-stu-id="1fa82-399">Keywords</span></span>

<span data-ttu-id="1fa82-400">| |</span><span class="sxs-lookup"><span data-stu-id="1fa82-400"></span></span>
|<span data-ttu-id="1fa82-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1fa82-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1fa82-402">护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-402">passport number</span></span>  <br/> <span data-ttu-id="1fa82-403">拉脱维亚护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-403">latvian passport number</span></span>  <br/> <span data-ttu-id="1fa82-404">passport 没有</span><span class="sxs-lookup"><span data-stu-id="1fa82-404">passport no</span></span>  <br/> <span data-ttu-id="1fa82-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="1fa82-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="1fa82-406">马耳他</span><span class="sxs-lookup"><span data-stu-id="1fa82-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="1fa82-407">格式</span><span class="sxs-lookup"><span data-stu-id="1fa82-407">Format</span></span>

<span data-ttu-id="1fa82-408">不含空格或分隔符的七位数字</span><span class="sxs-lookup"><span data-stu-id="1fa82-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1fa82-409">模式</span><span class="sxs-lookup"><span data-stu-id="1fa82-409">Pattern</span></span>

 <span data-ttu-id="1fa82-410">七个数字</span><span class="sxs-lookup"><span data-stu-id="1fa82-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="1fa82-411">校验和</span><span class="sxs-lookup"><span data-stu-id="1fa82-411">Checksum</span></span>

<span data-ttu-id="1fa82-412">否</span><span class="sxs-lookup"><span data-stu-id="1fa82-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1fa82-413">定义</span><span class="sxs-lookup"><span data-stu-id="1fa82-413">Definition</span></span>

<span data-ttu-id="1fa82-414">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1fa82-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1fa82-415">正则表达式`Regex_malta_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1fa82-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1fa82-416">从关键字`Keywords_malta_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1fa82-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1fa82-417">关键字</span><span class="sxs-lookup"><span data-stu-id="1fa82-417">Keywords</span></span>

<span data-ttu-id="1fa82-418">| |</span><span class="sxs-lookup"><span data-stu-id="1fa82-418"></span></span>
|<span data-ttu-id="1fa82-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1fa82-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1fa82-420">护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-420">passport number</span></span>  <br/> <span data-ttu-id="1fa82-421">马耳他护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-421">maltese passport number</span></span>  <br/> <span data-ttu-id="1fa82-422">passport 没有</span><span class="sxs-lookup"><span data-stu-id="1fa82-422">passport no</span></span>  <br/> <span data-ttu-id="1fa82-423">numru tal passaport</span><span class="sxs-lookup"><span data-stu-id="1fa82-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="1fa82-424">荷兰</span><span class="sxs-lookup"><span data-stu-id="1fa82-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="1fa82-425">格式</span><span class="sxs-lookup"><span data-stu-id="1fa82-425">Format</span></span>

<span data-ttu-id="1fa82-426">九个字母或数字不得含有空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="1fa82-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1fa82-427">模式</span><span class="sxs-lookup"><span data-stu-id="1fa82-427">Pattern</span></span>

<span data-ttu-id="1fa82-428">九个字母或数字</span><span class="sxs-lookup"><span data-stu-id="1fa82-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1fa82-429">校验和</span><span class="sxs-lookup"><span data-stu-id="1fa82-429">Checksum</span></span>

<span data-ttu-id="1fa82-430">不适用</span><span class="sxs-lookup"><span data-stu-id="1fa82-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1fa82-431">定义</span><span class="sxs-lookup"><span data-stu-id="1fa82-431">Definition</span></span>

<span data-ttu-id="1fa82-432">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1fa82-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1fa82-433">正则表达式`Regex_netherlands_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1fa82-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1fa82-434">从关键字`Keywords_netherlands_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1fa82-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1fa82-435">关键字</span><span class="sxs-lookup"><span data-stu-id="1fa82-435">Keywords</span></span>

<span data-ttu-id="1fa82-436">| |</span><span class="sxs-lookup"><span data-stu-id="1fa82-436"></span></span>
|<span data-ttu-id="1fa82-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1fa82-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1fa82-438">荷兰语护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-438">dutch passport number</span></span>  <br/> <span data-ttu-id="1fa82-439">护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-439">passport number</span></span>  <br/> <span data-ttu-id="1fa82-440">荷兰护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="1fa82-441">nederlanden paspoort nummer</span><span class="sxs-lookup"><span data-stu-id="1fa82-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="1fa82-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="1fa82-442">paspoort</span></span>  <br/> <span data-ttu-id="1fa82-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="1fa82-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="1fa82-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="1fa82-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="1fa82-445">波兰</span><span class="sxs-lookup"><span data-stu-id="1fa82-445">Poland</span></span>

<span data-ttu-id="1fa82-446">有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"波兰护照号码"。</span><span class="sxs-lookup"><span data-stu-id="1fa82-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="1fa82-447">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="1fa82-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="1fa82-448">格式</span><span class="sxs-lookup"><span data-stu-id="1fa82-448">Format</span></span>

<span data-ttu-id="1fa82-449">不得含有空格或分隔符六位数字后跟一个字母</span><span class="sxs-lookup"><span data-stu-id="1fa82-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1fa82-450">模式</span><span class="sxs-lookup"><span data-stu-id="1fa82-450">Pattern</span></span>

<span data-ttu-id="1fa82-451">包含 6 位数字后跟一个字母：</span><span class="sxs-lookup"><span data-stu-id="1fa82-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="1fa82-452">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="1fa82-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="1fa82-453">六个数字</span><span class="sxs-lookup"><span data-stu-id="1fa82-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1fa82-454">校验和</span><span class="sxs-lookup"><span data-stu-id="1fa82-454">Checksum</span></span>

<span data-ttu-id="1fa82-455">否</span><span class="sxs-lookup"><span data-stu-id="1fa82-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1fa82-456">定义</span><span class="sxs-lookup"><span data-stu-id="1fa82-456">Definition</span></span>

<span data-ttu-id="1fa82-457">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1fa82-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1fa82-458">正则表达式`Regex_portugal_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1fa82-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1fa82-459">从关键字`Keywords_portugal_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1fa82-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1fa82-460">关键字</span><span class="sxs-lookup"><span data-stu-id="1fa82-460">Keywords</span></span>

<span data-ttu-id="1fa82-461">| |</span><span class="sxs-lookup"><span data-stu-id="1fa82-461"></span></span>
|<span data-ttu-id="1fa82-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1fa82-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1fa82-463">护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-463">passport number</span></span>  <br/> <span data-ttu-id="1fa82-464">葡萄牙语护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="1fa82-465">passport 没有</span><span class="sxs-lookup"><span data-stu-id="1fa82-465">passport no</span></span>  <br/> <span data-ttu-id="1fa82-466">número 执行 passaporte</span><span class="sxs-lookup"><span data-stu-id="1fa82-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="1fa82-467">罗马尼亚</span><span class="sxs-lookup"><span data-stu-id="1fa82-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="1fa82-468">格式</span><span class="sxs-lookup"><span data-stu-id="1fa82-468">Format</span></span>

<span data-ttu-id="1fa82-469">八个或九个没有空格和分隔符的数字</span><span class="sxs-lookup"><span data-stu-id="1fa82-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1fa82-470">模式</span><span class="sxs-lookup"><span data-stu-id="1fa82-470">Pattern</span></span>

<span data-ttu-id="1fa82-471">八个或九个数字</span><span class="sxs-lookup"><span data-stu-id="1fa82-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1fa82-472">校验和</span><span class="sxs-lookup"><span data-stu-id="1fa82-472">Checksum</span></span>

<span data-ttu-id="1fa82-473">否</span><span class="sxs-lookup"><span data-stu-id="1fa82-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1fa82-474">定义</span><span class="sxs-lookup"><span data-stu-id="1fa82-474">Definition</span></span>

<span data-ttu-id="1fa82-475">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1fa82-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1fa82-476">正则表达式`Regex_romania_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1fa82-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1fa82-477">从关键字`Keywords_romania_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1fa82-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1fa82-478">关键字</span><span class="sxs-lookup"><span data-stu-id="1fa82-478">Keywords</span></span>

<span data-ttu-id="1fa82-479">| |</span><span class="sxs-lookup"><span data-stu-id="1fa82-479"></span></span>
|<span data-ttu-id="1fa82-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1fa82-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1fa82-481">护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-481">passport number</span></span>  <br/> <span data-ttu-id="1fa82-482">罗马尼亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-482">romanian passport number</span></span>  <br/> <span data-ttu-id="1fa82-483">passport 没有</span><span class="sxs-lookup"><span data-stu-id="1fa82-483">passport no</span></span>  <br/> <span data-ttu-id="1fa82-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="1fa82-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="1fa82-485">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="1fa82-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="1fa82-486">格式</span><span class="sxs-lookup"><span data-stu-id="1fa82-486">Format</span></span>

<span data-ttu-id="1fa82-487">一个数字或字母不得含有空格或分隔符的七位数字后跟</span><span class="sxs-lookup"><span data-stu-id="1fa82-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1fa82-488">模式</span><span class="sxs-lookup"><span data-stu-id="1fa82-488">Pattern</span></span>

<span data-ttu-id="1fa82-489">一个数字或字母 （不区分大小写） 七位数字后跟</span><span class="sxs-lookup"><span data-stu-id="1fa82-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1fa82-490">校验和</span><span class="sxs-lookup"><span data-stu-id="1fa82-490">Checksum</span></span>

<span data-ttu-id="1fa82-491">否</span><span class="sxs-lookup"><span data-stu-id="1fa82-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1fa82-492">定义</span><span class="sxs-lookup"><span data-stu-id="1fa82-492">Definition</span></span>

<span data-ttu-id="1fa82-493">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1fa82-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1fa82-494">正则表达式`Regex_slovakia_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1fa82-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1fa82-495">从关键字`Keywords_slovakia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1fa82-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1fa82-496">关键字</span><span class="sxs-lookup"><span data-stu-id="1fa82-496">Keywords</span></span>

<span data-ttu-id="1fa82-497">| |</span><span class="sxs-lookup"><span data-stu-id="1fa82-497"></span></span>
|<span data-ttu-id="1fa82-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1fa82-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1fa82-499">护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-499">passport number</span></span>  <br/> <span data-ttu-id="1fa82-500">斯洛伐克语护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="1fa82-501">passport 没有</span><span class="sxs-lookup"><span data-stu-id="1fa82-501">passport no</span></span>  <br/> <span data-ttu-id="1fa82-502">Číslo pasu</span><span class="sxs-lookup"><span data-stu-id="1fa82-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="1fa82-503">斯诺文尼亚</span><span class="sxs-lookup"><span data-stu-id="1fa82-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="1fa82-504">格式</span><span class="sxs-lookup"><span data-stu-id="1fa82-504">Format</span></span>

<span data-ttu-id="1fa82-505">不得含有空格或分隔符的七位数字后跟两个字母</span><span class="sxs-lookup"><span data-stu-id="1fa82-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1fa82-506">模式</span><span class="sxs-lookup"><span data-stu-id="1fa82-506">Pattern</span></span>

<span data-ttu-id="1fa82-507">七位数字后跟两个字母：</span><span class="sxs-lookup"><span data-stu-id="1fa82-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="1fa82-508">字母"P"</span><span class="sxs-lookup"><span data-stu-id="1fa82-508">The letter "P"</span></span>
    
- <span data-ttu-id="1fa82-509">一个大写字母</span><span class="sxs-lookup"><span data-stu-id="1fa82-509">One uppercase letter</span></span>
    
- <span data-ttu-id="1fa82-510">七个数字</span><span class="sxs-lookup"><span data-stu-id="1fa82-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1fa82-511">校验和</span><span class="sxs-lookup"><span data-stu-id="1fa82-511">Checksum</span></span>

<span data-ttu-id="1fa82-512">否</span><span class="sxs-lookup"><span data-stu-id="1fa82-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1fa82-513">定义</span><span class="sxs-lookup"><span data-stu-id="1fa82-513">Definition</span></span>

<span data-ttu-id="1fa82-514">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1fa82-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1fa82-515">正则表达式`Regex_slovenia_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1fa82-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1fa82-516">从关键字`Keywords_slovenia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1fa82-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1fa82-517">关键字</span><span class="sxs-lookup"><span data-stu-id="1fa82-517">Keywords</span></span>

<span data-ttu-id="1fa82-518">| |</span><span class="sxs-lookup"><span data-stu-id="1fa82-518"></span></span>
|<span data-ttu-id="1fa82-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1fa82-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1fa82-520">护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-520">passport number</span></span>  <br/> <span data-ttu-id="1fa82-521">斯洛文尼亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="1fa82-522">passport 没有</span><span class="sxs-lookup"><span data-stu-id="1fa82-522">passport no</span></span>  <br/> <span data-ttu-id="1fa82-523">Številka potnega 可变</span><span class="sxs-lookup"><span data-stu-id="1fa82-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="1fa82-524">西班牙</span><span class="sxs-lookup"><span data-stu-id="1fa82-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="1fa82-525">格式</span><span class="sxs-lookup"><span data-stu-id="1fa82-525">Format</span></span>

<span data-ttu-id="1fa82-526">字母或数字，没有空格或分隔符的八个字符或九个字符组合</span><span class="sxs-lookup"><span data-stu-id="1fa82-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1fa82-527">模式</span><span class="sxs-lookup"><span data-stu-id="1fa82-527">Pattern</span></span>

<span data-ttu-id="1fa82-528">字母和数字的八个字符或九个字符组合：</span><span class="sxs-lookup"><span data-stu-id="1fa82-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="1fa82-529">两个数字或字母</span><span class="sxs-lookup"><span data-stu-id="1fa82-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="1fa82-530">一个数字或字母 （可选）</span><span class="sxs-lookup"><span data-stu-id="1fa82-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="1fa82-531">六个数字</span><span class="sxs-lookup"><span data-stu-id="1fa82-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1fa82-532">校验和</span><span class="sxs-lookup"><span data-stu-id="1fa82-532">Checksum</span></span>

<span data-ttu-id="1fa82-533">不适用</span><span class="sxs-lookup"><span data-stu-id="1fa82-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1fa82-534">定义</span><span class="sxs-lookup"><span data-stu-id="1fa82-534">Definition</span></span>

<span data-ttu-id="1fa82-535">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1fa82-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1fa82-536">正则表达式`Regex_spain_eu_passport_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1fa82-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1fa82-537">从关键字`Keywords_spain_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1fa82-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1fa82-538">关键字</span><span class="sxs-lookup"><span data-stu-id="1fa82-538">Keywords</span></span>

<span data-ttu-id="1fa82-539">| |</span><span class="sxs-lookup"><span data-stu-id="1fa82-539"></span></span>
|<span data-ttu-id="1fa82-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1fa82-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1fa82-541">passport</span><span class="sxs-lookup"><span data-stu-id="1fa82-541">passport</span></span>  <br/> <span data-ttu-id="1fa82-542">西班牙 passport</span><span class="sxs-lookup"><span data-stu-id="1fa82-542">spain passport</span></span>  <br/> <span data-ttu-id="1fa82-543">passport 书籍</span><span class="sxs-lookup"><span data-stu-id="1fa82-543">passport book</span></span>  <br/> <span data-ttu-id="1fa82-544">护照号码</span><span class="sxs-lookup"><span data-stu-id="1fa82-544">passport number</span></span>  <br/> <span data-ttu-id="1fa82-545">passport 没有</span><span class="sxs-lookup"><span data-stu-id="1fa82-545">passport no</span></span>  <br/> <span data-ttu-id="1fa82-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="1fa82-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="1fa82-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="1fa82-547">número pasaporte</span></span>  <br/> <span data-ttu-id="1fa82-548">españa pasaporte</span><span class="sxs-lookup"><span data-stu-id="1fa82-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="1fa82-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="1fa82-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="1fa82-550">瑞典</span><span class="sxs-lookup"><span data-stu-id="1fa82-550">Sweden</span></span>

<span data-ttu-id="1fa82-551">有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"瑞典护照号码"。</span><span class="sxs-lookup"><span data-stu-id="1fa82-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="1fa82-552">英国</span><span class="sxs-lookup"><span data-stu-id="1fa82-552">UK</span></span>

<span data-ttu-id="1fa82-p103">有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"美国/英国护照号码"。</span><span class="sxs-lookup"><span data-stu-id="1fa82-p103">For details, see the section "U.S. / U.K. Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1fa82-555">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1fa82-555">See also</span></span>

[<span data-ttu-id="1fa82-556">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="1fa82-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

