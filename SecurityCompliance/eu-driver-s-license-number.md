---
title: 欧盟驾驶证号码
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: c3923cd3-ec84-435f-bf41-cadc37996a4b
description: 本主题演示数据丢失防护 (DLP) 策略检测到欧盟驱动程序的许可证数量敏感信息类型时的寻找。此敏感信息类型定义不同的模式、 关键字和每个国家/地区其他证据。
ms.openlocfilehash: 065684249f9766d567c63e6b8170d36f56692e45
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525367"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="9fb1e-104">欧盟驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-104">EU Driver's License Number</span></span>

<span data-ttu-id="9fb1e-p102">本主题演示数据丢失防护 (DLP) 策略检测到欧盟驱动程序的许可证数量敏感信息类型时的寻找。此敏感信息类型定义不同的模式、 关键字和每个国家/地区其他证据。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="9fb1e-107">奥地利</span><span class="sxs-lookup"><span data-stu-id="9fb1e-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="9fb1e-108">格式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-108">Format</span></span>

<span data-ttu-id="9fb1e-109">没有空格和分隔符的八个数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9fb1e-110">模式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-110">Pattern</span></span>

<span data-ttu-id="9fb1e-111">八个数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9fb1e-112">校验和</span><span class="sxs-lookup"><span data-stu-id="9fb1e-112">Checksum</span></span>

<span data-ttu-id="9fb1e-113">否</span><span class="sxs-lookup"><span data-stu-id="9fb1e-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9fb1e-114">定义</span><span class="sxs-lookup"><span data-stu-id="9fb1e-114">Definition</span></span>

<span data-ttu-id="9fb1e-115">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9fb1e-116">正则表达式`Regex_austria_eu_driver's_license_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9fb1e-117">从关键字`Keywords_austria_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="9fb1e-118">Keywords</span><span class="sxs-lookup"><span data-stu-id="9fb1e-118">Keywords</span></span>

<span data-ttu-id="9fb1e-119">| |</span><span class="sxs-lookup"><span data-stu-id="9fb1e-119"></span></span>
|<span data-ttu-id="9fb1e-120">**Keywords_austria_eu_driver s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9fb1e-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9fb1e-121">dl#</span><span class="sxs-lookup"><span data-stu-id="9fb1e-121">dl#</span></span>  <br/> <span data-ttu-id="9fb1e-122">driver license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-122">driver license</span></span>  <br/> <span data-ttu-id="9fb1e-123">驱动程序驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-123">driver license number</span></span>  <br/> <span data-ttu-id="9fb1e-124">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="9fb1e-124">driver licence</span></span>  <br/> <span data-ttu-id="9fb1e-125">驱动因素 lic。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-125">drivers lic.</span></span>  <br/> <span data-ttu-id="9fb1e-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-126">drivers license</span></span>  <br/> <span data-ttu-id="9fb1e-127">驱动程序的许可</span><span class="sxs-lookup"><span data-stu-id="9fb1e-127">driver's licence</span></span>  <br/> <span data-ttu-id="9fb1e-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-128">driver's license</span></span>  <br/> <span data-ttu-id="9fb1e-129">驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-129">driver's license number</span></span>  <br/> <span data-ttu-id="9fb1e-130">驱动程序的许可证数</span><span class="sxs-lookup"><span data-stu-id="9fb1e-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="9fb1e-131">驱动驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-131">driving license number</span></span>  <br/> <span data-ttu-id="9fb1e-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="9fb1e-132">dlno#</span></span>  <br/> <span data-ttu-id="9fb1e-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="9fb1e-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="9fb1e-134">fuhrerschein republik osterreich</span><span class="sxs-lookup"><span data-stu-id="9fb1e-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="9fb1e-135">比利时</span><span class="sxs-lookup"><span data-stu-id="9fb1e-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="9fb1e-136">格式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-136">Format</span></span>

<span data-ttu-id="9fb1e-137">没有空格和分隔符的 10 位数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9fb1e-138">模式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-138">Pattern</span></span>

<span data-ttu-id="9fb1e-139">10 个数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9fb1e-140">校验和</span><span class="sxs-lookup"><span data-stu-id="9fb1e-140">Checksum</span></span>

<span data-ttu-id="9fb1e-141">否</span><span class="sxs-lookup"><span data-stu-id="9fb1e-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9fb1e-142">定义</span><span class="sxs-lookup"><span data-stu-id="9fb1e-142">Definition</span></span>

<span data-ttu-id="9fb1e-143">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9fb1e-144">正则表达式`Regex_belgium_eu_driver's_license_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9fb1e-145">从关键字`Keywords_belgium_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="9fb1e-146">Keywords</span><span class="sxs-lookup"><span data-stu-id="9fb1e-146">Keywords</span></span>

<span data-ttu-id="9fb1e-147">| |</span><span class="sxs-lookup"><span data-stu-id="9fb1e-147"></span></span>
|<span data-ttu-id="9fb1e-148">**Keywords__belgium_eu_driver s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9fb1e-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9fb1e-149">dl#</span><span class="sxs-lookup"><span data-stu-id="9fb1e-149">dl#</span></span>  <br/> <span data-ttu-id="9fb1e-150">driver license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-150">driver license</span></span>  <br/> <span data-ttu-id="9fb1e-151">驱动程序驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-151">driver license number</span></span>  <br/> <span data-ttu-id="9fb1e-152">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="9fb1e-152">driver licence</span></span>  <br/> <span data-ttu-id="9fb1e-153">驱动因素 lic。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-153">drivers lic.</span></span>  <br/> <span data-ttu-id="9fb1e-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-154">drivers license</span></span>  <br/> <span data-ttu-id="9fb1e-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9fb1e-155">drivers licence</span></span>  <br/> <span data-ttu-id="9fb1e-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-156">driver's license</span></span>  <br/> <span data-ttu-id="9fb1e-157">驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-157">driver's license number</span></span>  <br/> <span data-ttu-id="9fb1e-158">驱动程序的许可证数</span><span class="sxs-lookup"><span data-stu-id="9fb1e-158">driver's licence number</span></span>  <br/> <span data-ttu-id="9fb1e-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="9fb1e-159">dlno#</span></span>  <br/> <span data-ttu-id="9fb1e-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="9fb1e-160">rijbewijs</span></span>  <br/> <span data-ttu-id="9fb1e-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="9fb1e-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="9fb1e-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="9fb1e-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="9fb1e-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="9fb1e-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="9fb1e-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="9fb1e-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="9fb1e-165">führerschein nr</span><span class="sxs-lookup"><span data-stu-id="9fb1e-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="9fb1e-166">fuehrerschein Nr</span><span class="sxs-lookup"><span data-stu-id="9fb1e-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="9fb1e-167">fuehrerschein nr</span><span class="sxs-lookup"><span data-stu-id="9fb1e-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="9fb1e-168">保加利亚</span><span class="sxs-lookup"><span data-stu-id="9fb1e-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="9fb1e-169">格式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-169">Format</span></span>

<span data-ttu-id="9fb1e-170">没有空格和分隔符的九个数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9fb1e-171">模式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-171">Pattern</span></span>

<span data-ttu-id="9fb1e-172">九个数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9fb1e-173">校验和</span><span class="sxs-lookup"><span data-stu-id="9fb1e-173">Checksum</span></span>

<span data-ttu-id="9fb1e-174">否</span><span class="sxs-lookup"><span data-stu-id="9fb1e-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9fb1e-175">定义</span><span class="sxs-lookup"><span data-stu-id="9fb1e-175">Definition</span></span>

<span data-ttu-id="9fb1e-176">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9fb1e-177">正则表达式`Regex_bulgaria_eu_driver's_license_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9fb1e-178">从关键字`Keywords_bulgaria_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="9fb1e-179">Keywords</span><span class="sxs-lookup"><span data-stu-id="9fb1e-179">Keywords</span></span>

<span data-ttu-id="9fb1e-180">| |</span><span class="sxs-lookup"><span data-stu-id="9fb1e-180"></span></span>
|<span data-ttu-id="9fb1e-181">**Keywords_bulgaria_eu_driver s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9fb1e-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9fb1e-182">dl#</span><span class="sxs-lookup"><span data-stu-id="9fb1e-182">dl#</span></span>  <br/> <span data-ttu-id="9fb1e-183">driver license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-183">driver license</span></span>  <br/> <span data-ttu-id="9fb1e-184">驱动程序驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-184">driver license number</span></span>  <br/> <span data-ttu-id="9fb1e-185">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="9fb1e-185">driver licence</span></span>  <br/> <span data-ttu-id="9fb1e-186">驱动因素 lic。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-186">drivers lic.</span></span>  <br/> <span data-ttu-id="9fb1e-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-187">drivers license</span></span>  <br/> <span data-ttu-id="9fb1e-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9fb1e-188">drivers licence</span></span>  <br/> <span data-ttu-id="9fb1e-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-189">driver's license</span></span>  <br/> <span data-ttu-id="9fb1e-190">驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-190">driver's license number</span></span>  <br/> <span data-ttu-id="9fb1e-191">驱动程序的许可证数</span><span class="sxs-lookup"><span data-stu-id="9fb1e-191">driver's licence number</span></span>  <br/> <span data-ttu-id="9fb1e-192">驱动驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-192">driving license number</span></span>  <br/> <span data-ttu-id="9fb1e-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="9fb1e-193">dlno#</span></span>  <br/> <span data-ttu-id="9fb1e-194">СВИДЕТЕЛСТВО ЗА УПРАВЛЕНИЕ НА МПС</span><span class="sxs-lookup"><span data-stu-id="9fb1e-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="9fb1e-195">СВИДЕТЕЛСТВО ЗА УПРАВЛЕНИЕ НА МОТОРНО ПРЕВОЗНО СРЕДСТВО</span><span class="sxs-lookup"><span data-stu-id="9fb1e-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="9fb1e-196">СУМПС</span><span class="sxs-lookup"><span data-stu-id="9fb1e-196">сумпс</span></span>  <br/> <span data-ttu-id="9fb1e-197">ШОФЬОРСКА КНИЖКА</span><span class="sxs-lookup"><span data-stu-id="9fb1e-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="9fb1e-198">克罗地亚</span><span class="sxs-lookup"><span data-stu-id="9fb1e-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="9fb1e-199">格式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-199">Format</span></span>

<span data-ttu-id="9fb1e-200">没有空格和分隔符的八个数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9fb1e-201">模式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-201">Pattern</span></span>

<span data-ttu-id="9fb1e-202">八个数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9fb1e-203">校验和</span><span class="sxs-lookup"><span data-stu-id="9fb1e-203">Checksum</span></span>

<span data-ttu-id="9fb1e-204">否</span><span class="sxs-lookup"><span data-stu-id="9fb1e-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9fb1e-205">定义</span><span class="sxs-lookup"><span data-stu-id="9fb1e-205">Definition</span></span>

<span data-ttu-id="9fb1e-206">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9fb1e-207">正则表达式`Regex_croatia_eu_driver's_license_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9fb1e-208">从关键字`Keywords_croatia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="9fb1e-209">Keywords</span><span class="sxs-lookup"><span data-stu-id="9fb1e-209">Keywords</span></span>

<span data-ttu-id="9fb1e-210">| |</span><span class="sxs-lookup"><span data-stu-id="9fb1e-210"></span></span>
|<span data-ttu-id="9fb1e-211">**Keywords_croatia_eu_driver s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9fb1e-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9fb1e-212">dl#</span><span class="sxs-lookup"><span data-stu-id="9fb1e-212">dl#</span></span>  <br/> <span data-ttu-id="9fb1e-213">driver license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-213">driver license</span></span>  <br/> <span data-ttu-id="9fb1e-214">驱动程序驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-214">driver license number</span></span>  <br/> <span data-ttu-id="9fb1e-215">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="9fb1e-215">driver licence</span></span>  <br/> <span data-ttu-id="9fb1e-216">驱动因素 lic。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-216">drivers lic.</span></span>  <br/> <span data-ttu-id="9fb1e-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-217">drivers license</span></span>  <br/> <span data-ttu-id="9fb1e-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9fb1e-218">drivers licence</span></span>  <br/> <span data-ttu-id="9fb1e-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-219">driver's license</span></span>  <br/> <span data-ttu-id="9fb1e-220">驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-220">driver's license number</span></span>  <br/> <span data-ttu-id="9fb1e-221">驱动程序的许可证数</span><span class="sxs-lookup"><span data-stu-id="9fb1e-221">driver's licence number</span></span>  <br/> <span data-ttu-id="9fb1e-222">驱动驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-222">driving license number</span></span>  <br/> <span data-ttu-id="9fb1e-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="9fb1e-223">dlno#</span></span>  <br/> <span data-ttu-id="9fb1e-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="9fb1e-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="9fb1e-225">塞浦路斯</span><span class="sxs-lookup"><span data-stu-id="9fb1e-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="9fb1e-226">格式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-226">Format</span></span>

<span data-ttu-id="9fb1e-227">没有空格和分隔符的 12 个数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9fb1e-228">模式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-228">Pattern</span></span>

<span data-ttu-id="9fb1e-229">12 个数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9fb1e-230">校验和</span><span class="sxs-lookup"><span data-stu-id="9fb1e-230">Checksum</span></span>

<span data-ttu-id="9fb1e-231">否</span><span class="sxs-lookup"><span data-stu-id="9fb1e-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9fb1e-232">定义</span><span class="sxs-lookup"><span data-stu-id="9fb1e-232">Definition</span></span>

<span data-ttu-id="9fb1e-233">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9fb1e-234">正则表达式`Regex_cyprus_eu_driver's_license_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9fb1e-235">从关键字`Keywords_cyprus_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9fb1e-236">Keywords</span><span class="sxs-lookup"><span data-stu-id="9fb1e-236">Keywords</span></span>

<span data-ttu-id="9fb1e-237">| |</span><span class="sxs-lookup"><span data-stu-id="9fb1e-237"></span></span>
|<span data-ttu-id="9fb1e-238">**Keywords_cyprus_eu_driver s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9fb1e-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9fb1e-239">dl#</span><span class="sxs-lookup"><span data-stu-id="9fb1e-239">dl#</span></span>  <br/> <span data-ttu-id="9fb1e-240">driver license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-240">driver license</span></span>  <br/> <span data-ttu-id="9fb1e-241">驱动程序驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-241">driver license number</span></span>  <br/> <span data-ttu-id="9fb1e-242">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="9fb1e-242">driver licence</span></span>  <br/> <span data-ttu-id="9fb1e-243">驱动因素 lic。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-243">drivers lic.</span></span>  <br/> <span data-ttu-id="9fb1e-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-244">drivers license</span></span>  <br/> <span data-ttu-id="9fb1e-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9fb1e-245">drivers licence</span></span>  <br/> <span data-ttu-id="9fb1e-246">驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-246">driver's license number</span></span>  <br/> <span data-ttu-id="9fb1e-247">驱动程序的许可证数</span><span class="sxs-lookup"><span data-stu-id="9fb1e-247">driver's licence number</span></span>  <br/> <span data-ttu-id="9fb1e-248">驱动驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-248">driving license number</span></span>  <br/> <span data-ttu-id="9fb1e-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="9fb1e-249">dlno#</span></span>  <br/> <span data-ttu-id="9fb1e-250">ΆΔΕΙΑ ΟΔΉΓΗΣΗΣ</span><span class="sxs-lookup"><span data-stu-id="9fb1e-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="9fb1e-251">捷克共和国</span><span class="sxs-lookup"><span data-stu-id="9fb1e-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="9fb1e-252">格式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-252">Format</span></span>

<span data-ttu-id="9fb1e-253">包含 6 位数字后跟两个字母</span><span class="sxs-lookup"><span data-stu-id="9fb1e-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9fb1e-254">模式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-254">Pattern</span></span>

<span data-ttu-id="9fb1e-255">八个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="9fb1e-256">两个字母 （不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="9fb1e-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="9fb1e-257">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="9fb1e-257">A space (optional)</span></span>
    
- <span data-ttu-id="9fb1e-258">六个数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9fb1e-259">校验和</span><span class="sxs-lookup"><span data-stu-id="9fb1e-259">Checksum</span></span>

<span data-ttu-id="9fb1e-260">否</span><span class="sxs-lookup"><span data-stu-id="9fb1e-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9fb1e-261">定义</span><span class="sxs-lookup"><span data-stu-id="9fb1e-261">Definition</span></span>

<span data-ttu-id="9fb1e-262">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9fb1e-263">正则表达式`Regex_czech_republic_eu_driver's_license_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9fb1e-264">从关键字`Keywords_czech_republic_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="9fb1e-265">Keywords</span><span class="sxs-lookup"><span data-stu-id="9fb1e-265">Keywords</span></span>

<span data-ttu-id="9fb1e-266">| |</span><span class="sxs-lookup"><span data-stu-id="9fb1e-266"></span></span>
|<span data-ttu-id="9fb1e-267">**Keywords_czech_republic_eu_driver s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9fb1e-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9fb1e-268">dl#</span><span class="sxs-lookup"><span data-stu-id="9fb1e-268">dl#</span></span>  <br/> <span data-ttu-id="9fb1e-269">driver license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-269">driver license</span></span>  <br/> <span data-ttu-id="9fb1e-270">驱动程序驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-270">driver license number</span></span>  <br/> <span data-ttu-id="9fb1e-271">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="9fb1e-271">driver licence</span></span>  <br/> <span data-ttu-id="9fb1e-272">驱动因素 lic。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-272">drivers lic.</span></span>  <br/> <span data-ttu-id="9fb1e-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-273">drivers license</span></span>  <br/> <span data-ttu-id="9fb1e-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9fb1e-274">drivers licence</span></span>  <br/> <span data-ttu-id="9fb1e-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-275">driver's license</span></span>  <br/> <span data-ttu-id="9fb1e-276">驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-276">driver's license number</span></span>  <br/> <span data-ttu-id="9fb1e-277">驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-277">driver's license number</span></span>  <br/> <span data-ttu-id="9fb1e-278">驱动程序的许可证数</span><span class="sxs-lookup"><span data-stu-id="9fb1e-278">driver's licence number</span></span>  <br/> <span data-ttu-id="9fb1e-279">驱动驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-279">driving license number</span></span>  <br/> <span data-ttu-id="9fb1e-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="9fb1e-280">dlno#</span></span>  <br/> <span data-ttu-id="9fb1e-281">Řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="9fb1e-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="9fb1e-282">丹麦</span><span class="sxs-lookup"><span data-stu-id="9fb1e-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="9fb1e-283">格式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-283">Format</span></span>

<span data-ttu-id="9fb1e-284">没有空格和分隔符的八个数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9fb1e-285">模式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-285">Pattern</span></span>

<span data-ttu-id="9fb1e-286">八个数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9fb1e-287">校验和</span><span class="sxs-lookup"><span data-stu-id="9fb1e-287">Checksum</span></span>

<span data-ttu-id="9fb1e-288">是</span><span class="sxs-lookup"><span data-stu-id="9fb1e-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9fb1e-289">定义</span><span class="sxs-lookup"><span data-stu-id="9fb1e-289">Definition</span></span>

<span data-ttu-id="9fb1e-290">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9fb1e-291">正则表达式`Regex_denmark_eu_driver's_license_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9fb1e-292">从关键字`Keywords_denmark_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="9fb1e-293">Keywords</span><span class="sxs-lookup"><span data-stu-id="9fb1e-293">Keywords</span></span>

<span data-ttu-id="9fb1e-294">| |</span><span class="sxs-lookup"><span data-stu-id="9fb1e-294"></span></span>
|<span data-ttu-id="9fb1e-295">**Keywords_denmark_eu_driver s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9fb1e-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9fb1e-296">dl#</span><span class="sxs-lookup"><span data-stu-id="9fb1e-296">dl#</span></span>  <br/> <span data-ttu-id="9fb1e-297">driver license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-297">driver license</span></span>  <br/> <span data-ttu-id="9fb1e-298">驱动程序驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-298">driver license number</span></span>  <br/> <span data-ttu-id="9fb1e-299">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="9fb1e-299">driver licence</span></span>  <br/> <span data-ttu-id="9fb1e-300">驱动因素 lic。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-300">drivers lic.</span></span>  <br/> <span data-ttu-id="9fb1e-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-301">drivers license</span></span>  <br/> <span data-ttu-id="9fb1e-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9fb1e-302">drivers licence</span></span>  <br/> <span data-ttu-id="9fb1e-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-303">driver's license</span></span>  <br/> <span data-ttu-id="9fb1e-304">驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-304">driver's license number</span></span>  <br/> <span data-ttu-id="9fb1e-305">驱动程序的许可证数</span><span class="sxs-lookup"><span data-stu-id="9fb1e-305">driver's licence number</span></span>  <br/> <span data-ttu-id="9fb1e-306">驱动驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-306">driving license number</span></span>  <br/> <span data-ttu-id="9fb1e-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="9fb1e-307">dlno#</span></span>  <br/> <span data-ttu-id="9fb1e-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="9fb1e-308">kørekort</span></span>  <br/> <span data-ttu-id="9fb1e-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="9fb1e-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="9fb1e-310">爱沙尼亚</span><span class="sxs-lookup"><span data-stu-id="9fb1e-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="9fb1e-311">格式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-311">Format</span></span>

<span data-ttu-id="9fb1e-312">包含 6 位数字后跟两个字母</span><span class="sxs-lookup"><span data-stu-id="9fb1e-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9fb1e-313">模式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-313">Pattern</span></span>

<span data-ttu-id="9fb1e-314">两个字母和 6 个数字：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="9fb1e-315">字母"ET"（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="9fb1e-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="9fb1e-316">六个数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9fb1e-317">校验和</span><span class="sxs-lookup"><span data-stu-id="9fb1e-317">Checksum</span></span>

<span data-ttu-id="9fb1e-318">否</span><span class="sxs-lookup"><span data-stu-id="9fb1e-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9fb1e-319">定义</span><span class="sxs-lookup"><span data-stu-id="9fb1e-319">Definition</span></span>

<span data-ttu-id="9fb1e-320">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9fb1e-321">正则表达式`Regex_estonia_eu_driver's_license_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9fb1e-322">从关键字`Keywords_estonia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9fb1e-323">Keywords</span><span class="sxs-lookup"><span data-stu-id="9fb1e-323">Keywords</span></span>

<span data-ttu-id="9fb1e-324">| |</span><span class="sxs-lookup"><span data-stu-id="9fb1e-324"></span></span>
|<span data-ttu-id="9fb1e-325">**Keywords_estonia_eu_driver s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9fb1e-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9fb1e-326">dl#</span><span class="sxs-lookup"><span data-stu-id="9fb1e-326">dl#</span></span>  <br/> <span data-ttu-id="9fb1e-327">driver license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-327">driver license</span></span>  <br/> <span data-ttu-id="9fb1e-328">驱动程序驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-328">driver license number</span></span>  <br/> <span data-ttu-id="9fb1e-329">驱动程序驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-329">driver license number</span></span>  <br/> <span data-ttu-id="9fb1e-330">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="9fb1e-330">driver licence</span></span>  <br/> <span data-ttu-id="9fb1e-331">驱动因素 lic。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-331">drivers lic.</span></span>  <br/> <span data-ttu-id="9fb1e-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-332">drivers license</span></span>  <br/> <span data-ttu-id="9fb1e-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9fb1e-333">drivers licence</span></span>  <br/> <span data-ttu-id="9fb1e-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-334">driver's license</span></span>  <br/> <span data-ttu-id="9fb1e-335">驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-335">driver's license number</span></span>  <br/> <span data-ttu-id="9fb1e-336">驱动驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-336">driving license number</span></span>  <br/> <span data-ttu-id="9fb1e-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="9fb1e-337">dlno#</span></span>  <br/> <span data-ttu-id="9fb1e-338">
permis de conduire</span><span class="sxs-lookup"><span data-stu-id="9fb1e-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="9fb1e-339">芬兰</span><span class="sxs-lookup"><span data-stu-id="9fb1e-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="9fb1e-340">格式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-340">Format</span></span>

<span data-ttu-id="9fb1e-341">10 个数字，包含连字符</span><span class="sxs-lookup"><span data-stu-id="9fb1e-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9fb1e-342">模式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-342">Pattern</span></span>

<span data-ttu-id="9fb1e-343">包含连字符的 10 位数字：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="9fb1e-344">六位数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-344">Six digits</span></span> 
    
- <span data-ttu-id="9fb1e-345">连字符</span><span class="sxs-lookup"><span data-stu-id="9fb1e-345">A hyphen</span></span>
    
-  <span data-ttu-id="9fb1e-346">四位数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="9fb1e-347">校验和</span><span class="sxs-lookup"><span data-stu-id="9fb1e-347">Checksum</span></span>

<span data-ttu-id="9fb1e-348">否</span><span class="sxs-lookup"><span data-stu-id="9fb1e-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9fb1e-349">定义</span><span class="sxs-lookup"><span data-stu-id="9fb1e-349">Definition</span></span>

<span data-ttu-id="9fb1e-350">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9fb1e-351">正则表达式`Regex_finland_eu_driver's_license_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9fb1e-352">从关键字`Keywords_finland_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9fb1e-353">Keywords</span><span class="sxs-lookup"><span data-stu-id="9fb1e-353">Keywords</span></span>

<span data-ttu-id="9fb1e-354">| |</span><span class="sxs-lookup"><span data-stu-id="9fb1e-354"></span></span>
|<span data-ttu-id="9fb1e-355">**Keywords_finland_eu_driver s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9fb1e-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9fb1e-356">dl#</span><span class="sxs-lookup"><span data-stu-id="9fb1e-356">dl#</span></span>  <br/> <span data-ttu-id="9fb1e-357">driver license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-357">driver license</span></span>  <br/> <span data-ttu-id="9fb1e-358">驱动程序驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-358">driver license number</span></span>  <br/> <span data-ttu-id="9fb1e-359">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="9fb1e-359">driver licence</span></span>  <br/> <span data-ttu-id="9fb1e-360">驱动因素 lic。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-360">drivers lic.</span></span>  <br/> <span data-ttu-id="9fb1e-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-361">drivers license</span></span>  <br/> <span data-ttu-id="9fb1e-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9fb1e-362">drivers licence</span></span>  <br/> <span data-ttu-id="9fb1e-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-363">driver's license</span></span>  <br/> <span data-ttu-id="9fb1e-364">驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-364">driver's license number</span></span>  <br/> <span data-ttu-id="9fb1e-365">驱动程序的许可证数</span><span class="sxs-lookup"><span data-stu-id="9fb1e-365">driver's licence number</span></span>  <br/> <span data-ttu-id="9fb1e-366">驱动驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-366">driving license number</span></span>  <br/> <span data-ttu-id="9fb1e-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="9fb1e-367">dlno#</span></span>  <br/> <span data-ttu-id="9fb1e-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="9fb1e-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="9fb1e-369">法国</span><span class="sxs-lookup"><span data-stu-id="9fb1e-369">France</span></span>

<span data-ttu-id="9fb1e-370">有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"法国驾驶证号码"。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="9fb1e-371">德国</span><span class="sxs-lookup"><span data-stu-id="9fb1e-371">Germany</span></span>

<span data-ttu-id="9fb1e-372">有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"德国驾驶证号码"。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="9fb1e-373">希腊</span><span class="sxs-lookup"><span data-stu-id="9fb1e-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="9fb1e-374">格式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-374">Format</span></span>

<span data-ttu-id="9fb1e-375">没有空格和分隔符的九个数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9fb1e-376">模式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-376">Pattern</span></span>

 <span data-ttu-id="9fb1e-377">九个数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="9fb1e-378">校验和</span><span class="sxs-lookup"><span data-stu-id="9fb1e-378">Checksum</span></span>

<span data-ttu-id="9fb1e-379">否</span><span class="sxs-lookup"><span data-stu-id="9fb1e-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9fb1e-380">定义</span><span class="sxs-lookup"><span data-stu-id="9fb1e-380">Definition</span></span>

<span data-ttu-id="9fb1e-381">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9fb1e-382">正则表达式`Regex_greece_eu_driver's_license_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9fb1e-383">从关键字`Keywords_greece_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9fb1e-384">Keywords</span><span class="sxs-lookup"><span data-stu-id="9fb1e-384">Keywords</span></span>

<span data-ttu-id="9fb1e-385">| |</span><span class="sxs-lookup"><span data-stu-id="9fb1e-385"></span></span>
|<span data-ttu-id="9fb1e-386">**Keywords_greece_eu_driver s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9fb1e-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9fb1e-387">dlL #</span><span class="sxs-lookup"><span data-stu-id="9fb1e-387">dlL#</span></span>  <br/> <span data-ttu-id="9fb1e-388">driver license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-388">driver license</span></span>  <br/> <span data-ttu-id="9fb1e-389">驱动程序驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-389">driver license number</span></span>  <br/> <span data-ttu-id="9fb1e-390">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="9fb1e-390">driver licence</span></span>  <br/> <span data-ttu-id="9fb1e-391">驱动因素 lic。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-391">drivers lic.</span></span>  <br/> <span data-ttu-id="9fb1e-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-392">drivers license</span></span>  <br/> <span data-ttu-id="9fb1e-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9fb1e-393">drivers licence</span></span>  <br/> <span data-ttu-id="9fb1e-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-394">driver's license</span></span>  <br/> <span data-ttu-id="9fb1e-395">驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-395">driver's license number</span></span>  <br/> <span data-ttu-id="9fb1e-396">驱动程序的许可证数</span><span class="sxs-lookup"><span data-stu-id="9fb1e-396">driver's licence number</span></span>  <br/> <span data-ttu-id="9fb1e-397">驱动驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-397">driving license number</span></span>  <br/> <span data-ttu-id="9fb1e-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="9fb1e-398">dlno#</span></span>  <br/> <span data-ttu-id="9fb1e-399">ΔΕΙΑ ΟΔΉΓΗΣΗΣ</span><span class="sxs-lookup"><span data-stu-id="9fb1e-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="9fb1e-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="9fb1e-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="9fb1e-401">匈牙利</span><span class="sxs-lookup"><span data-stu-id="9fb1e-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="9fb1e-402">格式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-402">Format</span></span>

<span data-ttu-id="9fb1e-403">包含 6 位数字后跟两个字母</span><span class="sxs-lookup"><span data-stu-id="9fb1e-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9fb1e-404">模式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-404">Pattern</span></span>

<span data-ttu-id="9fb1e-405">两个字母和 6 个数字：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="9fb1e-406">两个字母 （不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="9fb1e-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="9fb1e-407">六个数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9fb1e-408">校验和</span><span class="sxs-lookup"><span data-stu-id="9fb1e-408">Checksum</span></span>

<span data-ttu-id="9fb1e-409">否</span><span class="sxs-lookup"><span data-stu-id="9fb1e-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9fb1e-410">定义</span><span class="sxs-lookup"><span data-stu-id="9fb1e-410">Definition</span></span>

<span data-ttu-id="9fb1e-411">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9fb1e-412">正则表达式`Regex_hungary_eu_driver's_license_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9fb1e-413">从关键字`Keywords_hungary_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9fb1e-414">Keywords</span><span class="sxs-lookup"><span data-stu-id="9fb1e-414">Keywords</span></span>

<span data-ttu-id="9fb1e-415">| |</span><span class="sxs-lookup"><span data-stu-id="9fb1e-415"></span></span>
|<span data-ttu-id="9fb1e-416">**Keywords_hungary_eu_driver s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9fb1e-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9fb1e-417">dl#</span><span class="sxs-lookup"><span data-stu-id="9fb1e-417">dl#</span></span>  <br/> <span data-ttu-id="9fb1e-418">driver license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-418">driver license</span></span>  <br/> <span data-ttu-id="9fb1e-419">驱动程序驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-419">driver license number</span></span>  <br/> <span data-ttu-id="9fb1e-420">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="9fb1e-420">driver licence</span></span>  <br/> <span data-ttu-id="9fb1e-421">驱动因素 lic。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-421">drivers lic.</span></span>  <br/> <span data-ttu-id="9fb1e-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-422">drivers license</span></span>  <br/> <span data-ttu-id="9fb1e-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9fb1e-423">drivers licence</span></span>  <br/> <span data-ttu-id="9fb1e-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-424">driver's license</span></span>  <br/> <span data-ttu-id="9fb1e-425">驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-425">driver's license number</span></span>  <br/> <span data-ttu-id="9fb1e-426">驱动程序的许可证数</span><span class="sxs-lookup"><span data-stu-id="9fb1e-426">driver's licence number</span></span>  <br/> <span data-ttu-id="9fb1e-427">驱动驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-427">driving license number</span></span>  <br/> <span data-ttu-id="9fb1e-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="9fb1e-428">dlno#</span></span>  <br/> <span data-ttu-id="9fb1e-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="9fb1e-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="9fb1e-430">Ireland</span><span class="sxs-lookup"><span data-stu-id="9fb1e-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="9fb1e-431">格式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-431">Format</span></span>

<span data-ttu-id="9fb1e-432">跟四个字母的 6 个数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9fb1e-433">模式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-433">Pattern</span></span>

<span data-ttu-id="9fb1e-434">6 个数字和四个字母：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="9fb1e-435">六位数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-435">Six digits</span></span>
    
- <span data-ttu-id="9fb1e-436">四个字母 （不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="9fb1e-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9fb1e-437">校验和</span><span class="sxs-lookup"><span data-stu-id="9fb1e-437">Checksum</span></span>

<span data-ttu-id="9fb1e-438">否</span><span class="sxs-lookup"><span data-stu-id="9fb1e-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9fb1e-439">定义</span><span class="sxs-lookup"><span data-stu-id="9fb1e-439">Definition</span></span>

<span data-ttu-id="9fb1e-440">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9fb1e-441">正则表达式`Regex_ireland_eu_driver's_license_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9fb1e-442">从关键字`Keywords_ireland_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9fb1e-443">Keywords</span><span class="sxs-lookup"><span data-stu-id="9fb1e-443">Keywords</span></span>

<span data-ttu-id="9fb1e-444">| |</span><span class="sxs-lookup"><span data-stu-id="9fb1e-444"></span></span>
|<span data-ttu-id="9fb1e-445">**Keywords_ireland_eu_driver s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9fb1e-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9fb1e-446">dl#</span><span class="sxs-lookup"><span data-stu-id="9fb1e-446">dl#</span></span>  <br/> <span data-ttu-id="9fb1e-447">driver license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-447">driver license</span></span>  <br/> <span data-ttu-id="9fb1e-448">驱动程序驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-448">driver license number</span></span>  <br/> <span data-ttu-id="9fb1e-449">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="9fb1e-449">driver licence</span></span>  <br/> <span data-ttu-id="9fb1e-450">驱动因素 lic。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-450">drivers lic.</span></span>  <br/> <span data-ttu-id="9fb1e-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-451">drivers license</span></span>  <br/> <span data-ttu-id="9fb1e-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9fb1e-452">drivers licence</span></span>  <br/> <span data-ttu-id="9fb1e-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-453">driver's license</span></span>  <br/> <span data-ttu-id="9fb1e-454">驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-454">driver's license number</span></span>  <br/> <span data-ttu-id="9fb1e-455">驱动程序的许可证数</span><span class="sxs-lookup"><span data-stu-id="9fb1e-455">driver's licence number</span></span>  <br/> <span data-ttu-id="9fb1e-456">驱动驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-456">driving license number</span></span>  <br/> <span data-ttu-id="9fb1e-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="9fb1e-457">dlno#</span></span>  <br/> <span data-ttu-id="9fb1e-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="9fb1e-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="9fb1e-459">意大利</span><span class="sxs-lookup"><span data-stu-id="9fb1e-459">Italy</span></span>

<span data-ttu-id="9fb1e-460">有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"意大利驾驶证号码"。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="9fb1e-461">拉脱维亚</span><span class="sxs-lookup"><span data-stu-id="9fb1e-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="9fb1e-462">格式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-462">Format</span></span>

<span data-ttu-id="9fb1e-463">包含 6 位数字后跟的三个字母</span><span class="sxs-lookup"><span data-stu-id="9fb1e-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9fb1e-464">模式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-464">Pattern</span></span>

<span data-ttu-id="9fb1e-465">三个字母和 6 个数字：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="9fb1e-466">三个字母 （不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="9fb1e-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="9fb1e-467">六个数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9fb1e-468">校验和</span><span class="sxs-lookup"><span data-stu-id="9fb1e-468">Checksum</span></span>

<span data-ttu-id="9fb1e-469">否</span><span class="sxs-lookup"><span data-stu-id="9fb1e-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9fb1e-470">定义</span><span class="sxs-lookup"><span data-stu-id="9fb1e-470">Definition</span></span>

<span data-ttu-id="9fb1e-471">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9fb1e-472">正则表达式`Regex_latvia_eu_driver's_license_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9fb1e-473">从关键字`Keywords_latvia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9fb1e-474">Keywords</span><span class="sxs-lookup"><span data-stu-id="9fb1e-474">Keywords</span></span>

<span data-ttu-id="9fb1e-475">| |</span><span class="sxs-lookup"><span data-stu-id="9fb1e-475"></span></span>
|<span data-ttu-id="9fb1e-476">**Keywords_latvia_eu_driver s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9fb1e-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9fb1e-477">dl#</span><span class="sxs-lookup"><span data-stu-id="9fb1e-477">dl#</span></span>  <br/> <span data-ttu-id="9fb1e-478">driver license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-478">driver license</span></span>  <br/> <span data-ttu-id="9fb1e-479">驱动程序驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-479">driver license number</span></span>  <br/> <span data-ttu-id="9fb1e-480">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="9fb1e-480">driver licence</span></span>  <br/> <span data-ttu-id="9fb1e-481">驱动因素 lic。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-481">drivers lic.</span></span>  <br/> <span data-ttu-id="9fb1e-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-482">drivers license</span></span>  <br/> <span data-ttu-id="9fb1e-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9fb1e-483">drivers licence</span></span>  <br/> <span data-ttu-id="9fb1e-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-484">driver's license</span></span>  <br/> <span data-ttu-id="9fb1e-485">驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-485">driver's license number</span></span>  <br/> <span data-ttu-id="9fb1e-486">驱动程序的许可证数</span><span class="sxs-lookup"><span data-stu-id="9fb1e-486">driver's licence number</span></span>  <br/> <span data-ttu-id="9fb1e-487">驱动驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-487">driving license number</span></span>  <br/> <span data-ttu-id="9fb1e-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="9fb1e-488">dlno#</span></span>  <br/> <span data-ttu-id="9fb1e-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="9fb1e-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="9fb1e-490">立陶宛</span><span class="sxs-lookup"><span data-stu-id="9fb1e-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="9fb1e-491">格式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-491">Format</span></span>

<span data-ttu-id="9fb1e-492">没有空格和分隔符的八个数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9fb1e-493">模式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-493">Pattern</span></span>

 <span data-ttu-id="9fb1e-494">八个数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="9fb1e-495">校验和</span><span class="sxs-lookup"><span data-stu-id="9fb1e-495">Checksum</span></span>

<span data-ttu-id="9fb1e-496">否</span><span class="sxs-lookup"><span data-stu-id="9fb1e-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9fb1e-497">定义</span><span class="sxs-lookup"><span data-stu-id="9fb1e-497">Definition</span></span>

<span data-ttu-id="9fb1e-498">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9fb1e-499">正则表达式`Regex_lithuania_eu_driver's_license_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9fb1e-500">从关键字`Keywords_lithuania_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9fb1e-501">Keywords</span><span class="sxs-lookup"><span data-stu-id="9fb1e-501">Keywords</span></span>

<span data-ttu-id="9fb1e-502">| |</span><span class="sxs-lookup"><span data-stu-id="9fb1e-502"></span></span>
|<span data-ttu-id="9fb1e-503">**Keywords_lithuania_eu_driver s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9fb1e-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9fb1e-504">dl#</span><span class="sxs-lookup"><span data-stu-id="9fb1e-504">dl#</span></span>  <br/> <span data-ttu-id="9fb1e-505">driver license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-505">driver license</span></span>  <br/> <span data-ttu-id="9fb1e-506">驱动程序驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-506">driver license number</span></span>  <br/> <span data-ttu-id="9fb1e-507">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="9fb1e-507">driver licence</span></span>  <br/> <span data-ttu-id="9fb1e-508">驱动因素 lic。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-508">drivers lic.</span></span>  <br/> <span data-ttu-id="9fb1e-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-509">drivers license</span></span>  <br/> <span data-ttu-id="9fb1e-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9fb1e-510">drivers licence</span></span>  <br/> <span data-ttu-id="9fb1e-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-511">driver's license</span></span>  <br/> <span data-ttu-id="9fb1e-512">驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-512">driver's license number</span></span>  <br/> <span data-ttu-id="9fb1e-513">驱动程序的许可证数</span><span class="sxs-lookup"><span data-stu-id="9fb1e-513">driver's licence number</span></span>  <br/> <span data-ttu-id="9fb1e-514">驱动驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-514">driving license number</span></span>  <br/> <span data-ttu-id="9fb1e-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="9fb1e-515">dlno#</span></span>  <br/> <span data-ttu-id="9fb1e-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="9fb1e-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="9fb1e-517">卢森堡</span><span class="sxs-lookup"><span data-stu-id="9fb1e-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="9fb1e-518">格式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-518">Format</span></span>

<span data-ttu-id="9fb1e-519">没有空格和分隔符的 6 个数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9fb1e-520">模式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-520">Pattern</span></span>

 <span data-ttu-id="9fb1e-521">六个数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="9fb1e-522">校验和</span><span class="sxs-lookup"><span data-stu-id="9fb1e-522">Checksum</span></span>

<span data-ttu-id="9fb1e-523">否</span><span class="sxs-lookup"><span data-stu-id="9fb1e-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9fb1e-524">定义</span><span class="sxs-lookup"><span data-stu-id="9fb1e-524">Definition</span></span>

<span data-ttu-id="9fb1e-525">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9fb1e-526">正则表达式`Regex_luxemburg_eu_driver's_license_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9fb1e-527">从关键字`Keywords_luxemburg_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9fb1e-528">Keywords</span><span class="sxs-lookup"><span data-stu-id="9fb1e-528">Keywords</span></span>

<span data-ttu-id="9fb1e-529">| |</span><span class="sxs-lookup"><span data-stu-id="9fb1e-529"></span></span>
|<span data-ttu-id="9fb1e-530">**Keywords_luxemburg_eu_driver s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9fb1e-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9fb1e-531">dl#</span><span class="sxs-lookup"><span data-stu-id="9fb1e-531">dl#</span></span>  <br/> <span data-ttu-id="9fb1e-532">driver license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-532">driver license</span></span>  <br/> <span data-ttu-id="9fb1e-533">驱动程序驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-533">driver license number</span></span>  <br/> <span data-ttu-id="9fb1e-534">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="9fb1e-534">driver licence</span></span>  <br/> <span data-ttu-id="9fb1e-535">驱动因素 lic。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-535">drivers lic.</span></span>  <br/> <span data-ttu-id="9fb1e-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-536">drivers license</span></span>  <br/> <span data-ttu-id="9fb1e-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9fb1e-537">drivers licence</span></span>  <br/> <span data-ttu-id="9fb1e-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-538">driver's license</span></span>  <br/> <span data-ttu-id="9fb1e-539">驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-539">driver's license number</span></span>  <br/> <span data-ttu-id="9fb1e-540">驱动程序的许可证数</span><span class="sxs-lookup"><span data-stu-id="9fb1e-540">driver's licence number</span></span>  <br/> <span data-ttu-id="9fb1e-541">驱动驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-541">driving license number</span></span>  <br/> <span data-ttu-id="9fb1e-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="9fb1e-542">dlno#</span></span>  <br/> <span data-ttu-id="9fb1e-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="9fb1e-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="9fb1e-544">马耳他</span><span class="sxs-lookup"><span data-stu-id="9fb1e-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="9fb1e-545">格式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-545">Format</span></span>

<span data-ttu-id="9fb1e-546">两个字符和指定的模式中的 6 个数字的组合</span><span class="sxs-lookup"><span data-stu-id="9fb1e-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9fb1e-547">模式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-547">Pattern</span></span>

<span data-ttu-id="9fb1e-548">两个字符和包含 6 位数字的组合：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="9fb1e-549">两个字符 （数字或字母、 不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="9fb1e-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="9fb1e-550">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="9fb1e-550">A space (optional)</span></span>
    
- <span data-ttu-id="9fb1e-551">三个数字 </span><span class="sxs-lookup"><span data-stu-id="9fb1e-551">Three digits</span></span>
    
- <span data-ttu-id="9fb1e-552">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="9fb1e-552">A space (optional)</span></span>
    
- <span data-ttu-id="9fb1e-553">3 位数</span><span class="sxs-lookup"><span data-stu-id="9fb1e-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9fb1e-554">校验和</span><span class="sxs-lookup"><span data-stu-id="9fb1e-554">Checksum</span></span>

<span data-ttu-id="9fb1e-555">否</span><span class="sxs-lookup"><span data-stu-id="9fb1e-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9fb1e-556">定义</span><span class="sxs-lookup"><span data-stu-id="9fb1e-556">Definition</span></span>

<span data-ttu-id="9fb1e-557">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9fb1e-558">正则表达式`Regex_malta_eu_driver's_license_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9fb1e-559">从关键字`Keywords_malta_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9fb1e-560">Keywords</span><span class="sxs-lookup"><span data-stu-id="9fb1e-560">Keywords</span></span>

<span data-ttu-id="9fb1e-561">| |</span><span class="sxs-lookup"><span data-stu-id="9fb1e-561"></span></span>
|<span data-ttu-id="9fb1e-562">**Keywords_malta_eu_driver s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9fb1e-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9fb1e-563">dl#</span><span class="sxs-lookup"><span data-stu-id="9fb1e-563">dl#</span></span>  <br/> <span data-ttu-id="9fb1e-564">driver license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-564">driver license</span></span>  <br/> <span data-ttu-id="9fb1e-565">驱动程序驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-565">driver license number</span></span>  <br/> <span data-ttu-id="9fb1e-566">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="9fb1e-566">driver licence</span></span>  <br/> <span data-ttu-id="9fb1e-567">驱动因素 lic。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-567">drivers lic.</span></span>  <br/> <span data-ttu-id="9fb1e-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-568">drivers license</span></span>  <br/> <span data-ttu-id="9fb1e-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9fb1e-569">drivers licence</span></span>  <br/> <span data-ttu-id="9fb1e-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-570">driver's license</span></span>  <br/> <span data-ttu-id="9fb1e-571">驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-571">driver's license number</span></span>  <br/> <span data-ttu-id="9fb1e-572">驱动程序的许可证数</span><span class="sxs-lookup"><span data-stu-id="9fb1e-572">driver's licence number</span></span>  <br/> <span data-ttu-id="9fb1e-573">驱动驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-573">driving license number</span></span>  <br/> <span data-ttu-id="9fb1e-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="9fb1e-574">dlno#</span></span>  <br/> <span data-ttu-id="9fb1e-575">liċenzja tas sewqan</span><span class="sxs-lookup"><span data-stu-id="9fb1e-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="9fb1e-576">荷兰</span><span class="sxs-lookup"><span data-stu-id="9fb1e-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="9fb1e-577">格式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-577">Format</span></span>

<span data-ttu-id="9fb1e-578">没有空格和分隔符的 10 位数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9fb1e-579">模式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-579">Pattern</span></span>

<span data-ttu-id="9fb1e-580">10 个数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9fb1e-581">校验和</span><span class="sxs-lookup"><span data-stu-id="9fb1e-581">Checksum</span></span>

<span data-ttu-id="9fb1e-582">否</span><span class="sxs-lookup"><span data-stu-id="9fb1e-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9fb1e-583">定义</span><span class="sxs-lookup"><span data-stu-id="9fb1e-583">Definition</span></span>

<span data-ttu-id="9fb1e-584">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9fb1e-585">正则表达式`Regex_netherlands_eu_driver's_license_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9fb1e-586">从关键字`Keywords_netherlands_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9fb1e-587">Keywords</span><span class="sxs-lookup"><span data-stu-id="9fb1e-587">Keywords</span></span>

<span data-ttu-id="9fb1e-588">| |</span><span class="sxs-lookup"><span data-stu-id="9fb1e-588"></span></span>
|<span data-ttu-id="9fb1e-589">**Keywords_netherlands_eu_driver s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9fb1e-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9fb1e-590">dl#</span><span class="sxs-lookup"><span data-stu-id="9fb1e-590">dl#</span></span>  <br/> <span data-ttu-id="9fb1e-591">driver license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-591">driver license</span></span>  <br/> <span data-ttu-id="9fb1e-592">驱动程序驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-592">driver license number</span></span>  <br/> <span data-ttu-id="9fb1e-593">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="9fb1e-593">driver licence</span></span>  <br/> <span data-ttu-id="9fb1e-594">驱动因素 lic。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-594">drivers lic.</span></span>  <br/> <span data-ttu-id="9fb1e-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-595">drivers license</span></span>  <br/> <span data-ttu-id="9fb1e-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9fb1e-596">drivers licence</span></span>  <br/> <span data-ttu-id="9fb1e-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-597">driver's license</span></span>  <br/> <span data-ttu-id="9fb1e-598">驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-598">driver's license number</span></span>  <br/> <span data-ttu-id="9fb1e-599">驱动程序的许可证数</span><span class="sxs-lookup"><span data-stu-id="9fb1e-599">driver's licence number</span></span>  <br/> <span data-ttu-id="9fb1e-600">驱动驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-600">driving license number</span></span>  <br/> <span data-ttu-id="9fb1e-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="9fb1e-601">dlno#</span></span>  <br/> <span data-ttu-id="9fb1e-602">
permis de conduire</span><span class="sxs-lookup"><span data-stu-id="9fb1e-602">permis de conduire</span></span>  <br/> <span data-ttu-id="9fb1e-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="9fb1e-603">rijbewijs</span></span>  <br/> <span data-ttu-id="9fb1e-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="9fb1e-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="9fb1e-605">波兰</span><span class="sxs-lookup"><span data-stu-id="9fb1e-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="9fb1e-606">格式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-606">Format</span></span>

<span data-ttu-id="9fb1e-607">包含 2 个正斜杠 14 数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9fb1e-608">模式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-608">Pattern</span></span>

<span data-ttu-id="9fb1e-609">14 数字和 2 正斜杠：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="9fb1e-610">五位数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-610">Five digits</span></span> 
    
- <span data-ttu-id="9fb1e-611">一个正斜杠 </span><span class="sxs-lookup"><span data-stu-id="9fb1e-611">A forward slash</span></span>
    
- <span data-ttu-id="9fb1e-612">两位数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-612">Two digits</span></span>
    
- <span data-ttu-id="9fb1e-613">一个正斜杠 </span><span class="sxs-lookup"><span data-stu-id="9fb1e-613">A forward slash</span></span>
    
- <span data-ttu-id="9fb1e-614">七个数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9fb1e-615">校验和</span><span class="sxs-lookup"><span data-stu-id="9fb1e-615">Checksum</span></span>

<span data-ttu-id="9fb1e-616">否</span><span class="sxs-lookup"><span data-stu-id="9fb1e-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9fb1e-617">定义</span><span class="sxs-lookup"><span data-stu-id="9fb1e-617">Definition</span></span>

<span data-ttu-id="9fb1e-618">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9fb1e-619">正则表达式`Regex_poland_eu_driver's_license_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9fb1e-620">从关键字`Keywords_poland_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9fb1e-621">Keywords</span><span class="sxs-lookup"><span data-stu-id="9fb1e-621">Keywords</span></span>

<span data-ttu-id="9fb1e-622">| |</span><span class="sxs-lookup"><span data-stu-id="9fb1e-622"></span></span>
|<span data-ttu-id="9fb1e-623">**Keywords_poland_eu_driver s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9fb1e-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9fb1e-624">dl#</span><span class="sxs-lookup"><span data-stu-id="9fb1e-624">dl#</span></span>  <br/> <span data-ttu-id="9fb1e-625">driver license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-625">driver license</span></span>  <br/> <span data-ttu-id="9fb1e-626">驱动程序驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-626">driver license number</span></span>  <br/> <span data-ttu-id="9fb1e-627">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="9fb1e-627">driver licence</span></span>  <br/> <span data-ttu-id="9fb1e-628">驱动因素 lic。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-628">drivers lic.</span></span>  <br/> <span data-ttu-id="9fb1e-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-629">drivers license</span></span>  <br/> <span data-ttu-id="9fb1e-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9fb1e-630">drivers licence</span></span>  <br/> <span data-ttu-id="9fb1e-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-631">driver's license</span></span>  <br/> <span data-ttu-id="9fb1e-632">驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-632">driver's license number</span></span>  <br/> <span data-ttu-id="9fb1e-633">驱动程序的许可证数</span><span class="sxs-lookup"><span data-stu-id="9fb1e-633">driver's licence number</span></span>  <br/> <span data-ttu-id="9fb1e-634">驱动驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-634">driving license number</span></span>  <br/> <span data-ttu-id="9fb1e-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="9fb1e-635">dlno#</span></span>  <br/> <span data-ttu-id="9fb1e-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="9fb1e-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="9fb1e-637">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="9fb1e-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="9fb1e-638">格式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-638">Format</span></span>

<span data-ttu-id="9fb1e-639">两个字母后跟中指定的模式七个数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9fb1e-640">模式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-640">Pattern</span></span>

<span data-ttu-id="9fb1e-641">具有特殊字符的七个数字后跟两个字母：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="9fb1e-642">两个字母 （不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="9fb1e-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="9fb1e-643">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="9fb1e-643">A hyphen</span></span>
    
- <span data-ttu-id="9fb1e-644">六位数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-644">Six digits</span></span>
    
- <span data-ttu-id="9fb1e-645">一个空格</span><span class="sxs-lookup"><span data-stu-id="9fb1e-645">A space</span></span>
    
- <span data-ttu-id="9fb1e-646">一个数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9fb1e-647">校验和</span><span class="sxs-lookup"><span data-stu-id="9fb1e-647">Checksum</span></span>

<span data-ttu-id="9fb1e-648">否</span><span class="sxs-lookup"><span data-stu-id="9fb1e-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9fb1e-649">定义</span><span class="sxs-lookup"><span data-stu-id="9fb1e-649">Definition</span></span>

<span data-ttu-id="9fb1e-650">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9fb1e-651">正则表达式`Regex_portugal_eu_driver's_license_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9fb1e-652">从关键字`Keywords_portugal_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9fb1e-653">Keywords</span><span class="sxs-lookup"><span data-stu-id="9fb1e-653">Keywords</span></span>

<span data-ttu-id="9fb1e-654">| |</span><span class="sxs-lookup"><span data-stu-id="9fb1e-654"></span></span>
|<span data-ttu-id="9fb1e-655">**Keywords_portugal_eu_driver s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9fb1e-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9fb1e-656">dl#</span><span class="sxs-lookup"><span data-stu-id="9fb1e-656">dl#</span></span>  <br/> <span data-ttu-id="9fb1e-657">driver license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-657">driver license</span></span>  <br/> <span data-ttu-id="9fb1e-658">驱动程序驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-658">driver license number</span></span>  <br/> <span data-ttu-id="9fb1e-659">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="9fb1e-659">driver licence</span></span>  <br/> <span data-ttu-id="9fb1e-660">驱动因素 lic。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-660">drivers lic.</span></span>  <br/> <span data-ttu-id="9fb1e-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-661">drivers license</span></span>  <br/> <span data-ttu-id="9fb1e-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9fb1e-662">drivers licence</span></span>  <br/> <span data-ttu-id="9fb1e-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-663">driver's license</span></span>  <br/> <span data-ttu-id="9fb1e-664">驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-664">driver's license number</span></span>  <br/> <span data-ttu-id="9fb1e-665">驱动程序的许可证数</span><span class="sxs-lookup"><span data-stu-id="9fb1e-665">driver's licence number</span></span>  <br/> <span data-ttu-id="9fb1e-666">驱动驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-666">driving license number</span></span>  <br/> <span data-ttu-id="9fb1e-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="9fb1e-667">dlno#</span></span>  <br/> <span data-ttu-id="9fb1e-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="9fb1e-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="9fb1e-669">罗马尼亚</span><span class="sxs-lookup"><span data-stu-id="9fb1e-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="9fb1e-670">格式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-670">Format</span></span>

<span data-ttu-id="9fb1e-671">一个跟八个数字的字符</span><span class="sxs-lookup"><span data-stu-id="9fb1e-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9fb1e-672">模式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-672">Pattern</span></span>

<span data-ttu-id="9fb1e-673">一个跟八个数字的字符：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="9fb1e-674">一个 （不区分大小写） 的字母或数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="9fb1e-675">八个数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9fb1e-676">校验和</span><span class="sxs-lookup"><span data-stu-id="9fb1e-676">Checksum</span></span>

<span data-ttu-id="9fb1e-677">否</span><span class="sxs-lookup"><span data-stu-id="9fb1e-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9fb1e-678">定义</span><span class="sxs-lookup"><span data-stu-id="9fb1e-678">Definition</span></span>

<span data-ttu-id="9fb1e-679">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9fb1e-680">正则表达式`Regex_romania_eu_driver's_license_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9fb1e-681">从关键字`Keywords_romania_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9fb1e-682">Keywords</span><span class="sxs-lookup"><span data-stu-id="9fb1e-682">Keywords</span></span>

<span data-ttu-id="9fb1e-683">| |</span><span class="sxs-lookup"><span data-stu-id="9fb1e-683"></span></span>
|<span data-ttu-id="9fb1e-684">**Keywords_romania_eu_driver s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9fb1e-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9fb1e-685">dl#</span><span class="sxs-lookup"><span data-stu-id="9fb1e-685">dl#</span></span>  <br/> <span data-ttu-id="9fb1e-686">driver license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-686">driver license</span></span>  <br/> <span data-ttu-id="9fb1e-687">驱动程序驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-687">driver license number</span></span>  <br/> <span data-ttu-id="9fb1e-688">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="9fb1e-688">driver licence</span></span>  <br/> <span data-ttu-id="9fb1e-689">驱动因素 lic。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-689">drivers lic.</span></span>  <br/> <span data-ttu-id="9fb1e-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-690">drivers license</span></span>  <br/> <span data-ttu-id="9fb1e-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9fb1e-691">drivers licence</span></span>  <br/> <span data-ttu-id="9fb1e-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-692">driver's license</span></span>  <br/> <span data-ttu-id="9fb1e-693">驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-693">driver's license number</span></span>  <br/> <span data-ttu-id="9fb1e-694">驱动程序的许可证数</span><span class="sxs-lookup"><span data-stu-id="9fb1e-694">driver's licence number</span></span>  <br/> <span data-ttu-id="9fb1e-695">驱动驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-695">driving license number</span></span>  <br/> <span data-ttu-id="9fb1e-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="9fb1e-696">dlno#</span></span>  <br/> <span data-ttu-id="9fb1e-697">permis de conducere</span><span class="sxs-lookup"><span data-stu-id="9fb1e-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="9fb1e-698">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="9fb1e-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="9fb1e-699">格式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-699">Format</span></span>

<span data-ttu-id="9fb1e-700">一个字符后跟七位数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9fb1e-701">模式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-701">Pattern</span></span>

<span data-ttu-id="9fb1e-702">一个字符后跟七位数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="9fb1e-703">一个 （不区分大小写） 的字母或数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="9fb1e-704">七个数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="9fb1e-705">校验和</span><span class="sxs-lookup"><span data-stu-id="9fb1e-705">Checksum</span></span>

<span data-ttu-id="9fb1e-706">否</span><span class="sxs-lookup"><span data-stu-id="9fb1e-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9fb1e-707">定义</span><span class="sxs-lookup"><span data-stu-id="9fb1e-707">Definition</span></span>

<span data-ttu-id="9fb1e-708">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9fb1e-709">正则表达式`Regex_slovakia_eu_driver's_license_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9fb1e-710">从关键字`Keywords_slovakia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9fb1e-711">Keywords</span><span class="sxs-lookup"><span data-stu-id="9fb1e-711">Keywords</span></span>

<span data-ttu-id="9fb1e-712">| |</span><span class="sxs-lookup"><span data-stu-id="9fb1e-712"></span></span>
|<span data-ttu-id="9fb1e-713">**Keywords_slovakia_eu_driver s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9fb1e-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9fb1e-714">dl#</span><span class="sxs-lookup"><span data-stu-id="9fb1e-714">dl#</span></span>  <br/> <span data-ttu-id="9fb1e-715">driver license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-715">driver license</span></span>  <br/> <span data-ttu-id="9fb1e-716">驱动程序驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-716">driver license number</span></span>  <br/> <span data-ttu-id="9fb1e-717">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="9fb1e-717">driver licence</span></span>  <br/> <span data-ttu-id="9fb1e-718">驱动因素 lic。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-718">drivers lic.</span></span>  <br/> <span data-ttu-id="9fb1e-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-719">drivers license</span></span>  <br/> <span data-ttu-id="9fb1e-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9fb1e-720">drivers licence</span></span>  <br/> <span data-ttu-id="9fb1e-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-721">driver's license</span></span>  <br/> <span data-ttu-id="9fb1e-722">驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-722">driver's license number</span></span>  <br/> <span data-ttu-id="9fb1e-723">驱动程序的许可证数</span><span class="sxs-lookup"><span data-stu-id="9fb1e-723">driver's licence number</span></span>  <br/> <span data-ttu-id="9fb1e-724">驱动驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-724">driving license number</span></span>  <br/> <span data-ttu-id="9fb1e-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="9fb1e-725">dlno#</span></span>  <br/> <span data-ttu-id="9fb1e-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="9fb1e-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="9fb1e-727">斯诺文尼亚</span><span class="sxs-lookup"><span data-stu-id="9fb1e-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="9fb1e-728">格式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-728">Format</span></span>

<span data-ttu-id="9fb1e-729">没有空格和分隔符的九个数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9fb1e-730">模式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-730">Pattern</span></span>

<span data-ttu-id="9fb1e-731">九个数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9fb1e-732">校验和</span><span class="sxs-lookup"><span data-stu-id="9fb1e-732">Checksum</span></span>

<span data-ttu-id="9fb1e-733">否</span><span class="sxs-lookup"><span data-stu-id="9fb1e-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9fb1e-734">定义</span><span class="sxs-lookup"><span data-stu-id="9fb1e-734">Definition</span></span>

<span data-ttu-id="9fb1e-735">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9fb1e-736">正则表达式`Regex_slovenia_eu_driver's_license_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9fb1e-737">从关键字`Keywords_slovenia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9fb1e-738">Keywords</span><span class="sxs-lookup"><span data-stu-id="9fb1e-738">Keywords</span></span>

<span data-ttu-id="9fb1e-739">| |</span><span class="sxs-lookup"><span data-stu-id="9fb1e-739"></span></span>
|<span data-ttu-id="9fb1e-740">**Keywords_slovenia_eu_driver s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9fb1e-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9fb1e-741">dl#</span><span class="sxs-lookup"><span data-stu-id="9fb1e-741">dl#</span></span>  <br/> <span data-ttu-id="9fb1e-742">driver license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-742">driver license</span></span>  <br/> <span data-ttu-id="9fb1e-743">驱动程序驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-743">driver license number</span></span>  <br/> <span data-ttu-id="9fb1e-744">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="9fb1e-744">driver licence</span></span>  <br/> <span data-ttu-id="9fb1e-745">驱动因素 lic。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-745">drivers lic.</span></span>  <br/> <span data-ttu-id="9fb1e-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-746">drivers license</span></span>  <br/> <span data-ttu-id="9fb1e-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9fb1e-747">drivers licence</span></span>  <br/> <span data-ttu-id="9fb1e-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-748">driver's license</span></span>  <br/> <span data-ttu-id="9fb1e-749">驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-749">driver's license number</span></span>  <br/> <span data-ttu-id="9fb1e-750">驱动程序的许可证数</span><span class="sxs-lookup"><span data-stu-id="9fb1e-750">driver's licence number</span></span>  <br/> <span data-ttu-id="9fb1e-751">驱动驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-751">driving license number</span></span>  <br/> <span data-ttu-id="9fb1e-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="9fb1e-752">dlno#</span></span>  <br/> <span data-ttu-id="9fb1e-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="9fb1e-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="9fb1e-754">西班牙</span><span class="sxs-lookup"><span data-stu-id="9fb1e-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="9fb1e-755">格式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-755">Format</span></span>

<span data-ttu-id="9fb1e-756">一个字符后跟八个数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9fb1e-757">模式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-757">Pattern</span></span>

<span data-ttu-id="9fb1e-758">一个字符后跟八个数字：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="9fb1e-759">八个数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-759">Eight digits</span></span> 
    
- <span data-ttu-id="9fb1e-760">一个数字或字母 （不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="9fb1e-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9fb1e-761">校验和</span><span class="sxs-lookup"><span data-stu-id="9fb1e-761">Checksum</span></span>

<span data-ttu-id="9fb1e-762">是</span><span class="sxs-lookup"><span data-stu-id="9fb1e-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9fb1e-763">定义</span><span class="sxs-lookup"><span data-stu-id="9fb1e-763">Definition</span></span>

<span data-ttu-id="9fb1e-764">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9fb1e-765">该函数`Func_spain_eu_driver's_license_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9fb1e-766">从关键字`Keywords_spain_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9fb1e-767">Keywords</span><span class="sxs-lookup"><span data-stu-id="9fb1e-767">Keywords</span></span>

<span data-ttu-id="9fb1e-768">| |</span><span class="sxs-lookup"><span data-stu-id="9fb1e-768"></span></span>
|<span data-ttu-id="9fb1e-769">**Keywords_spain_eu_driver s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9fb1e-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9fb1e-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="9fb1e-770">dlno#</span></span>  <br/> <span data-ttu-id="9fb1e-771">dl#</span><span class="sxs-lookup"><span data-stu-id="9fb1e-771">dl#</span></span>  <br/> <span data-ttu-id="9fb1e-772">驱动因素 lic。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-772">drivers lic.</span></span>  <br/> <span data-ttu-id="9fb1e-773">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="9fb1e-773">driver licence</span></span>  <br/> <span data-ttu-id="9fb1e-774">driver license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-774">driver license</span></span>  <br/> <span data-ttu-id="9fb1e-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9fb1e-775">drivers licence</span></span>  <br/> <span data-ttu-id="9fb1e-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-776">drivers license</span></span>  <br/> <span data-ttu-id="9fb1e-777">驱动程序的许可</span><span class="sxs-lookup"><span data-stu-id="9fb1e-777">driver's licence</span></span>  <br/> <span data-ttu-id="9fb1e-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-778">driver's license</span></span>  <br/> <span data-ttu-id="9fb1e-779">driving licence
</span><span class="sxs-lookup"><span data-stu-id="9fb1e-779">driving licence</span></span>  <br/> <span data-ttu-id="9fb1e-780">驱动许可证</span><span class="sxs-lookup"><span data-stu-id="9fb1e-780">driving license</span></span>  <br/> <span data-ttu-id="9fb1e-781">驱动程序许可数</span><span class="sxs-lookup"><span data-stu-id="9fb1e-781">driver licence number</span></span>  <br/> <span data-ttu-id="9fb1e-782">驱动程序驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-782">driver license number</span></span>  <br/> <span data-ttu-id="9fb1e-783">驱动程序许可数</span><span class="sxs-lookup"><span data-stu-id="9fb1e-783">drivers licence number</span></span>  <br/> <span data-ttu-id="9fb1e-784">驱动因素驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-784">drivers license number</span></span>  <br/> <span data-ttu-id="9fb1e-785">驱动程序的许可证数</span><span class="sxs-lookup"><span data-stu-id="9fb1e-785">driver's licence number</span></span>  <br/> <span data-ttu-id="9fb1e-786">驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-786">driver's license number</span></span>  <br/> <span data-ttu-id="9fb1e-787">驾驭许可证数</span><span class="sxs-lookup"><span data-stu-id="9fb1e-787">driving licence number</span></span>  <br/> <span data-ttu-id="9fb1e-788">驱动驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-788">driving license number</span></span>  <br/> <span data-ttu-id="9fb1e-789">驱动允许</span><span class="sxs-lookup"><span data-stu-id="9fb1e-789">driving permit</span></span>  <br/> <span data-ttu-id="9fb1e-790">驱动允许号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-790">driving permit number</span></span>  <br/> <span data-ttu-id="9fb1e-791">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="9fb1e-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="9fb1e-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="9fb1e-792">permiso conducción</span></span>  <br/> <span data-ttu-id="9fb1e-793">número licencia conducir</span><span class="sxs-lookup"><span data-stu-id="9fb1e-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="9fb1e-794">número de carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="9fb1e-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="9fb1e-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="9fb1e-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="9fb1e-796">licencia conducir</span><span class="sxs-lookup"><span data-stu-id="9fb1e-796">licencia conducir</span></span>  <br/> <span data-ttu-id="9fb1e-797">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="9fb1e-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="9fb1e-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="9fb1e-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="9fb1e-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="9fb1e-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="9fb1e-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="9fb1e-800">permiso conducir</span></span>  <br/> <span data-ttu-id="9fb1e-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="9fb1e-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="9fb1e-802">el carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="9fb1e-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="9fb1e-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="9fb1e-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="9fb1e-804">瑞典</span><span class="sxs-lookup"><span data-stu-id="9fb1e-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="9fb1e-805">格式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-805">Format</span></span>

<span data-ttu-id="9fb1e-806">包含连字符的 10 位数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9fb1e-807">模式</span><span class="sxs-lookup"><span data-stu-id="9fb1e-807">Pattern</span></span>

<span data-ttu-id="9fb1e-808">包含连字符的 10 位数字：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="9fb1e-809">六位数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-809">Six digits</span></span> 
    
- <span data-ttu-id="9fb1e-810">连字符</span><span class="sxs-lookup"><span data-stu-id="9fb1e-810">A hyphen</span></span>
    
- <span data-ttu-id="9fb1e-811">四位数字</span><span class="sxs-lookup"><span data-stu-id="9fb1e-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9fb1e-812">校验和</span><span class="sxs-lookup"><span data-stu-id="9fb1e-812">Checksum</span></span>

<span data-ttu-id="9fb1e-813">否</span><span class="sxs-lookup"><span data-stu-id="9fb1e-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9fb1e-814">定义</span><span class="sxs-lookup"><span data-stu-id="9fb1e-814">Definition</span></span>

<span data-ttu-id="9fb1e-815">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9fb1e-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9fb1e-816">正则表达式`Regex_sweden_eu_driver's_license_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9fb1e-817">从关键字`Keywords_sweden_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="9fb1e-818">Keywords</span><span class="sxs-lookup"><span data-stu-id="9fb1e-818">Keywords</span></span>

<span data-ttu-id="9fb1e-819">| |</span><span class="sxs-lookup"><span data-stu-id="9fb1e-819"></span></span>
|<span data-ttu-id="9fb1e-820">**Keywords_sweden_eu_driver s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9fb1e-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9fb1e-821">dl#</span><span class="sxs-lookup"><span data-stu-id="9fb1e-821">dl#</span></span>  <br/> <span data-ttu-id="9fb1e-822">driver license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-822">driver license</span></span>  <br/> <span data-ttu-id="9fb1e-823">驱动程序驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-823">driver license number</span></span>  <br/> <span data-ttu-id="9fb1e-824">驱动程序许可</span><span class="sxs-lookup"><span data-stu-id="9fb1e-824">driver licence</span></span>  <br/> <span data-ttu-id="9fb1e-825">驱动因素 lic。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-825">drivers lic.</span></span>  <br/> <span data-ttu-id="9fb1e-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-826">drivers license</span></span>  <br/> <span data-ttu-id="9fb1e-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9fb1e-827">drivers licence</span></span>  <br/> <span data-ttu-id="9fb1e-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="9fb1e-828">driver's license</span></span>  <br/> <span data-ttu-id="9fb1e-829">驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-829">driver's license number</span></span>  <br/> <span data-ttu-id="9fb1e-830">驱动程序的许可证数</span><span class="sxs-lookup"><span data-stu-id="9fb1e-830">driver's licence number</span></span>  <br/> <span data-ttu-id="9fb1e-831">驱动驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="9fb1e-831">driving license number</span></span>  <br/> <span data-ttu-id="9fb1e-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="9fb1e-832">dlno#</span></span>  <br/> <span data-ttu-id="9fb1e-833">körkort</span><span class="sxs-lookup"><span data-stu-id="9fb1e-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="9fb1e-834">英国</span><span class="sxs-lookup"><span data-stu-id="9fb1e-834">UK</span></span>

<span data-ttu-id="9fb1e-p103">有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"英国驾驶证号码"。</span><span class="sxs-lookup"><span data-stu-id="9fb1e-p103">For details, see the section "U.K. Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9fb1e-837">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9fb1e-837">See also</span></span>

[<span data-ttu-id="9fb1e-838">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="9fb1e-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

