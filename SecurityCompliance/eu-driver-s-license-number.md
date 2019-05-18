---
title: 欧盟驾驶执照号码
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主题介绍当数据丢失防护 (DLP) 策略检测到欧盟驱动程序的敏感信息类型时, 应查找什么内容。 此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。
ms.openlocfilehash: f1a95ecbaf6b6d1ac189290dd6d076cfd91ab30f
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152974"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="83543-104">欧盟驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-104">EU Driver's License Number</span></span>

<span data-ttu-id="83543-105">本主题介绍当数据丢失防护 (DLP) 策略检测到欧盟驱动程序的敏感信息类型时, 应查找什么内容。</span><span class="sxs-lookup"><span data-stu-id="83543-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="83543-106">此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。</span><span class="sxs-lookup"><span data-stu-id="83543-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="83543-107">奥地利</span><span class="sxs-lookup"><span data-stu-id="83543-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="83543-108">Format</span><span class="sxs-lookup"><span data-stu-id="83543-108">Format</span></span>

<span data-ttu-id="83543-109">8位数, 不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="83543-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="83543-110">模式</span><span class="sxs-lookup"><span data-stu-id="83543-110">Pattern</span></span>

<span data-ttu-id="83543-111">八个数字</span><span class="sxs-lookup"><span data-stu-id="83543-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="83543-112">校验和</span><span class="sxs-lookup"><span data-stu-id="83543-112">Checksum</span></span>

<span data-ttu-id="83543-113">否</span><span class="sxs-lookup"><span data-stu-id="83543-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="83543-114">定义</span><span class="sxs-lookup"><span data-stu-id="83543-114">Definition</span></span>

<span data-ttu-id="83543-115">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="83543-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="83543-116">正则表达式`Regex_austria_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="83543-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="83543-117">找到了中`Keywords_austria_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="83543-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="83543-118">关键字</span><span class="sxs-lookup"><span data-stu-id="83543-118">Keywords</span></span>

<span data-ttu-id="83543-119">| |</span><span class="sxs-lookup"><span data-stu-id="83543-119"></span></span>
|<span data-ttu-id="83543-120">**Keywords_austria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="83543-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="83543-121">通讯</span><span class="sxs-lookup"><span data-stu-id="83543-121">dl#</span></span>  <br/> <span data-ttu-id="83543-122">driver license</span><span class="sxs-lookup"><span data-stu-id="83543-122">driver license</span></span>  <br/> <span data-ttu-id="83543-123">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-123">driver license number</span></span>  <br/> <span data-ttu-id="83543-124">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="83543-124">driver licence</span></span>  <br/> <span data-ttu-id="83543-125">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="83543-125">drivers lic.</span></span>  <br/> <span data-ttu-id="83543-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="83543-126">drivers license</span></span>  <br/> <span data-ttu-id="83543-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="83543-127">driver's licence</span></span>  <br/> <span data-ttu-id="83543-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="83543-128">driver's license</span></span>  <br/> <span data-ttu-id="83543-129">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-129">driver's license number</span></span>  <br/> <span data-ttu-id="83543-130">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="83543-131">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-131">driving license number</span></span>  <br/> <span data-ttu-id="83543-132">dlno#</span><span class="sxs-lookup"><span data-stu-id="83543-132">dlno#</span></span>  <br/> <span data-ttu-id="83543-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="83543-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="83543-134">fuhrerschein republik osterreich</span><span class="sxs-lookup"><span data-stu-id="83543-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="83543-135">比利时</span><span class="sxs-lookup"><span data-stu-id="83543-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="83543-136">Format</span><span class="sxs-lookup"><span data-stu-id="83543-136">Format</span></span>

<span data-ttu-id="83543-137">10个数字, 不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="83543-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="83543-138">模式</span><span class="sxs-lookup"><span data-stu-id="83543-138">Pattern</span></span>

<span data-ttu-id="83543-139">10 个数字</span><span class="sxs-lookup"><span data-stu-id="83543-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="83543-140">校验和</span><span class="sxs-lookup"><span data-stu-id="83543-140">Checksum</span></span>

<span data-ttu-id="83543-141">否</span><span class="sxs-lookup"><span data-stu-id="83543-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="83543-142">定义</span><span class="sxs-lookup"><span data-stu-id="83543-142">Definition</span></span>

<span data-ttu-id="83543-143">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="83543-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="83543-144">正则表达式`Regex_belgium_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="83543-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="83543-145">找到了中`Keywords_belgium_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="83543-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="83543-146">关键字</span><span class="sxs-lookup"><span data-stu-id="83543-146">Keywords</span></span>

<span data-ttu-id="83543-147">| |</span><span class="sxs-lookup"><span data-stu-id="83543-147"></span></span>
|<span data-ttu-id="83543-148">**Keywords__belgium_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="83543-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="83543-149">通讯</span><span class="sxs-lookup"><span data-stu-id="83543-149">dl#</span></span>  <br/> <span data-ttu-id="83543-150">driver license</span><span class="sxs-lookup"><span data-stu-id="83543-150">driver license</span></span>  <br/> <span data-ttu-id="83543-151">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-151">driver license number</span></span>  <br/> <span data-ttu-id="83543-152">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="83543-152">driver licence</span></span>  <br/> <span data-ttu-id="83543-153">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="83543-153">drivers lic.</span></span>  <br/> <span data-ttu-id="83543-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="83543-154">drivers license</span></span>  <br/> <span data-ttu-id="83543-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="83543-155">drivers licence</span></span>  <br/> <span data-ttu-id="83543-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="83543-156">driver's license</span></span>  <br/> <span data-ttu-id="83543-157">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-157">driver's license number</span></span>  <br/> <span data-ttu-id="83543-158">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-158">driver's licence number</span></span>  <br/> <span data-ttu-id="83543-159">dlno#</span><span class="sxs-lookup"><span data-stu-id="83543-159">dlno#</span></span>  <br/> <span data-ttu-id="83543-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="83543-160">rijbewijs</span></span>  <br/> <span data-ttu-id="83543-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="83543-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="83543-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="83543-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="83543-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="83543-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="83543-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="83543-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="83543-165">führerschein-nr-nr</span><span class="sxs-lookup"><span data-stu-id="83543-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="83543-166">fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="83543-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="83543-167">fuehrerschein-nr</span><span class="sxs-lookup"><span data-stu-id="83543-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="83543-168">保加利亚语</span><span class="sxs-lookup"><span data-stu-id="83543-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="83543-169">Format</span><span class="sxs-lookup"><span data-stu-id="83543-169">Format</span></span>

<span data-ttu-id="83543-170">9个数字, 不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="83543-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="83543-171">模式</span><span class="sxs-lookup"><span data-stu-id="83543-171">Pattern</span></span>

<span data-ttu-id="83543-172">九个数字</span><span class="sxs-lookup"><span data-stu-id="83543-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="83543-173">校验和</span><span class="sxs-lookup"><span data-stu-id="83543-173">Checksum</span></span>

<span data-ttu-id="83543-174">否</span><span class="sxs-lookup"><span data-stu-id="83543-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="83543-175">定义</span><span class="sxs-lookup"><span data-stu-id="83543-175">Definition</span></span>

<span data-ttu-id="83543-176">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="83543-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="83543-177">正则表达式`Regex_bulgaria_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="83543-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="83543-178">找到了中`Keywords_bulgaria_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="83543-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="83543-179">关键字</span><span class="sxs-lookup"><span data-stu-id="83543-179">Keywords</span></span>

<span data-ttu-id="83543-180">| |</span><span class="sxs-lookup"><span data-stu-id="83543-180"></span></span>
|<span data-ttu-id="83543-181">**Keywords_bulgaria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="83543-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="83543-182">通讯</span><span class="sxs-lookup"><span data-stu-id="83543-182">dl#</span></span>  <br/> <span data-ttu-id="83543-183">driver license</span><span class="sxs-lookup"><span data-stu-id="83543-183">driver license</span></span>  <br/> <span data-ttu-id="83543-184">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-184">driver license number</span></span>  <br/> <span data-ttu-id="83543-185">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="83543-185">driver licence</span></span>  <br/> <span data-ttu-id="83543-186">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="83543-186">drivers lic.</span></span>  <br/> <span data-ttu-id="83543-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="83543-187">drivers license</span></span>  <br/> <span data-ttu-id="83543-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="83543-188">drivers licence</span></span>  <br/> <span data-ttu-id="83543-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="83543-189">driver's license</span></span>  <br/> <span data-ttu-id="83543-190">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-190">driver's license number</span></span>  <br/> <span data-ttu-id="83543-191">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-191">driver's licence number</span></span>  <br/> <span data-ttu-id="83543-192">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-192">driving license number</span></span>  <br/> <span data-ttu-id="83543-193">dlno#</span><span class="sxs-lookup"><span data-stu-id="83543-193">dlno#</span></span>  <br/> <span data-ttu-id="83543-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="83543-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="83543-195">свидетелство за управление на моторно превозно средство</span><span class="sxs-lookup"><span data-stu-id="83543-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="83543-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="83543-196">сумпс</span></span>  <br/> <span data-ttu-id="83543-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="83543-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="83543-198">克罗地亚</span><span class="sxs-lookup"><span data-stu-id="83543-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="83543-199">Format</span><span class="sxs-lookup"><span data-stu-id="83543-199">Format</span></span>

<span data-ttu-id="83543-200">8位数, 不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="83543-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="83543-201">模式</span><span class="sxs-lookup"><span data-stu-id="83543-201">Pattern</span></span>

<span data-ttu-id="83543-202">八个数字</span><span class="sxs-lookup"><span data-stu-id="83543-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="83543-203">校验和</span><span class="sxs-lookup"><span data-stu-id="83543-203">Checksum</span></span>

<span data-ttu-id="83543-204">否</span><span class="sxs-lookup"><span data-stu-id="83543-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="83543-205">定义</span><span class="sxs-lookup"><span data-stu-id="83543-205">Definition</span></span>

<span data-ttu-id="83543-206">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="83543-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="83543-207">正则表达式`Regex_croatia_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="83543-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="83543-208">找到了中`Keywords_croatia_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="83543-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="83543-209">关键字</span><span class="sxs-lookup"><span data-stu-id="83543-209">Keywords</span></span>

<span data-ttu-id="83543-210">| |</span><span class="sxs-lookup"><span data-stu-id="83543-210"></span></span>
|<span data-ttu-id="83543-211">**Keywords_croatia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="83543-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="83543-212">通讯</span><span class="sxs-lookup"><span data-stu-id="83543-212">dl#</span></span>  <br/> <span data-ttu-id="83543-213">driver license</span><span class="sxs-lookup"><span data-stu-id="83543-213">driver license</span></span>  <br/> <span data-ttu-id="83543-214">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-214">driver license number</span></span>  <br/> <span data-ttu-id="83543-215">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="83543-215">driver licence</span></span>  <br/> <span data-ttu-id="83543-216">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="83543-216">drivers lic.</span></span>  <br/> <span data-ttu-id="83543-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="83543-217">drivers license</span></span>  <br/> <span data-ttu-id="83543-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="83543-218">drivers licence</span></span>  <br/> <span data-ttu-id="83543-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="83543-219">driver's license</span></span>  <br/> <span data-ttu-id="83543-220">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-220">driver's license number</span></span>  <br/> <span data-ttu-id="83543-221">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-221">driver's licence number</span></span>  <br/> <span data-ttu-id="83543-222">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-222">driving license number</span></span>  <br/> <span data-ttu-id="83543-223">dlno#</span><span class="sxs-lookup"><span data-stu-id="83543-223">dlno#</span></span>  <br/> <span data-ttu-id="83543-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="83543-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="83543-225">塞浦路斯</span><span class="sxs-lookup"><span data-stu-id="83543-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="83543-226">Format</span><span class="sxs-lookup"><span data-stu-id="83543-226">Format</span></span>

<span data-ttu-id="83543-227">12个数字, 不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="83543-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="83543-228">模式</span><span class="sxs-lookup"><span data-stu-id="83543-228">Pattern</span></span>

<span data-ttu-id="83543-229">12 个数字</span><span class="sxs-lookup"><span data-stu-id="83543-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="83543-230">校验和</span><span class="sxs-lookup"><span data-stu-id="83543-230">Checksum</span></span>

<span data-ttu-id="83543-231">否</span><span class="sxs-lookup"><span data-stu-id="83543-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="83543-232">定义</span><span class="sxs-lookup"><span data-stu-id="83543-232">Definition</span></span>

<span data-ttu-id="83543-233">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="83543-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="83543-234">正则表达式`Regex_cyprus_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="83543-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="83543-235">找到了中`Keywords_cyprus_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="83543-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="83543-236">关键字</span><span class="sxs-lookup"><span data-stu-id="83543-236">Keywords</span></span>

<span data-ttu-id="83543-237">| |</span><span class="sxs-lookup"><span data-stu-id="83543-237"></span></span>
|<span data-ttu-id="83543-238">**Keywords_cyprus_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="83543-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="83543-239">通讯</span><span class="sxs-lookup"><span data-stu-id="83543-239">dl#</span></span>  <br/> <span data-ttu-id="83543-240">driver license</span><span class="sxs-lookup"><span data-stu-id="83543-240">driver license</span></span>  <br/> <span data-ttu-id="83543-241">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-241">driver license number</span></span>  <br/> <span data-ttu-id="83543-242">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="83543-242">driver licence</span></span>  <br/> <span data-ttu-id="83543-243">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="83543-243">drivers lic.</span></span>  <br/> <span data-ttu-id="83543-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="83543-244">drivers license</span></span>  <br/> <span data-ttu-id="83543-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="83543-245">drivers licence</span></span>  <br/> <span data-ttu-id="83543-246">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-246">driver's license number</span></span>  <br/> <span data-ttu-id="83543-247">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-247">driver's licence number</span></span>  <br/> <span data-ttu-id="83543-248">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-248">driving license number</span></span>  <br/> <span data-ttu-id="83543-249">dlno#</span><span class="sxs-lookup"><span data-stu-id="83543-249">dlno#</span></span>  <br/> <span data-ttu-id="83543-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="83543-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="83543-251">捷克共和国</span><span class="sxs-lookup"><span data-stu-id="83543-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="83543-252">Format</span><span class="sxs-lookup"><span data-stu-id="83543-252">Format</span></span>

<span data-ttu-id="83543-253">两个字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="83543-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="83543-254">模式</span><span class="sxs-lookup"><span data-stu-id="83543-254">Pattern</span></span>

<span data-ttu-id="83543-255">八个字母和数字:</span><span class="sxs-lookup"><span data-stu-id="83543-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="83543-256">两个字母 (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="83543-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="83543-257">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="83543-257">A space (optional)</span></span>
    
- <span data-ttu-id="83543-258">六个数字</span><span class="sxs-lookup"><span data-stu-id="83543-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="83543-259">校验和</span><span class="sxs-lookup"><span data-stu-id="83543-259">Checksum</span></span>

<span data-ttu-id="83543-260">否</span><span class="sxs-lookup"><span data-stu-id="83543-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="83543-261">定义</span><span class="sxs-lookup"><span data-stu-id="83543-261">Definition</span></span>

<span data-ttu-id="83543-262">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="83543-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="83543-263">正则表达式`Regex_czech_republic_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="83543-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="83543-264">找到了中`Keywords_czech_republic_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="83543-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="83543-265">关键字</span><span class="sxs-lookup"><span data-stu-id="83543-265">Keywords</span></span>

<span data-ttu-id="83543-266">| |</span><span class="sxs-lookup"><span data-stu-id="83543-266"></span></span>
|<span data-ttu-id="83543-267">**Keywords_czech_republic_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="83543-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="83543-268">通讯</span><span class="sxs-lookup"><span data-stu-id="83543-268">dl#</span></span>  <br/> <span data-ttu-id="83543-269">driver license</span><span class="sxs-lookup"><span data-stu-id="83543-269">driver license</span></span>  <br/> <span data-ttu-id="83543-270">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-270">driver license number</span></span>  <br/> <span data-ttu-id="83543-271">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="83543-271">driver licence</span></span>  <br/> <span data-ttu-id="83543-272">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="83543-272">drivers lic.</span></span>  <br/> <span data-ttu-id="83543-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="83543-273">drivers license</span></span>  <br/> <span data-ttu-id="83543-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="83543-274">drivers licence</span></span>  <br/> <span data-ttu-id="83543-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="83543-275">driver's license</span></span>  <br/> <span data-ttu-id="83543-276">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-276">driver's license number</span></span>  <br/> <span data-ttu-id="83543-277">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-277">driver's license number</span></span>  <br/> <span data-ttu-id="83543-278">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-278">driver's licence number</span></span>  <br/> <span data-ttu-id="83543-279">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-279">driving license number</span></span>  <br/> <span data-ttu-id="83543-280">dlno#</span><span class="sxs-lookup"><span data-stu-id="83543-280">dlno#</span></span>  <br/> <span data-ttu-id="83543-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="83543-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="83543-282">丹麦</span><span class="sxs-lookup"><span data-stu-id="83543-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="83543-283">Format</span><span class="sxs-lookup"><span data-stu-id="83543-283">Format</span></span>

<span data-ttu-id="83543-284">8位数, 不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="83543-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="83543-285">模式</span><span class="sxs-lookup"><span data-stu-id="83543-285">Pattern</span></span>

<span data-ttu-id="83543-286">八个数字</span><span class="sxs-lookup"><span data-stu-id="83543-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="83543-287">校验和</span><span class="sxs-lookup"><span data-stu-id="83543-287">Checksum</span></span>

<span data-ttu-id="83543-288">是</span><span class="sxs-lookup"><span data-stu-id="83543-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="83543-289">定义</span><span class="sxs-lookup"><span data-stu-id="83543-289">Definition</span></span>

<span data-ttu-id="83543-290">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="83543-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="83543-291">正则表达式`Regex_denmark_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="83543-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="83543-292">找到了中`Keywords_denmark_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="83543-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="83543-293">关键字</span><span class="sxs-lookup"><span data-stu-id="83543-293">Keywords</span></span>

<span data-ttu-id="83543-294">| |</span><span class="sxs-lookup"><span data-stu-id="83543-294"></span></span>
|<span data-ttu-id="83543-295">**Keywords_denmark_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="83543-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="83543-296">通讯</span><span class="sxs-lookup"><span data-stu-id="83543-296">dl#</span></span>  <br/> <span data-ttu-id="83543-297">driver license</span><span class="sxs-lookup"><span data-stu-id="83543-297">driver license</span></span>  <br/> <span data-ttu-id="83543-298">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-298">driver license number</span></span>  <br/> <span data-ttu-id="83543-299">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="83543-299">driver licence</span></span>  <br/> <span data-ttu-id="83543-300">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="83543-300">drivers lic.</span></span>  <br/> <span data-ttu-id="83543-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="83543-301">drivers license</span></span>  <br/> <span data-ttu-id="83543-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="83543-302">drivers licence</span></span>  <br/> <span data-ttu-id="83543-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="83543-303">driver's license</span></span>  <br/> <span data-ttu-id="83543-304">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-304">driver's license number</span></span>  <br/> <span data-ttu-id="83543-305">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-305">driver's licence number</span></span>  <br/> <span data-ttu-id="83543-306">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-306">driving license number</span></span>  <br/> <span data-ttu-id="83543-307">dlno#</span><span class="sxs-lookup"><span data-stu-id="83543-307">dlno#</span></span>  <br/> <span data-ttu-id="83543-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="83543-308">kørekort</span></span>  <br/> <span data-ttu-id="83543-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="83543-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="83543-310">爱沙尼亚</span><span class="sxs-lookup"><span data-stu-id="83543-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="83543-311">Format</span><span class="sxs-lookup"><span data-stu-id="83543-311">Format</span></span>

<span data-ttu-id="83543-312">两个字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="83543-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="83543-313">模式</span><span class="sxs-lookup"><span data-stu-id="83543-313">Pattern</span></span>

<span data-ttu-id="83543-314">两个字母和六个数字:</span><span class="sxs-lookup"><span data-stu-id="83543-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="83543-315">字母 "ET" (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="83543-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="83543-316">六个数字</span><span class="sxs-lookup"><span data-stu-id="83543-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="83543-317">校验和</span><span class="sxs-lookup"><span data-stu-id="83543-317">Checksum</span></span>

<span data-ttu-id="83543-318">否</span><span class="sxs-lookup"><span data-stu-id="83543-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="83543-319">定义</span><span class="sxs-lookup"><span data-stu-id="83543-319">Definition</span></span>

<span data-ttu-id="83543-320">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="83543-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="83543-321">正则表达式`Regex_estonia_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="83543-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="83543-322">找到了中`Keywords_estonia_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="83543-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="83543-323">关键字</span><span class="sxs-lookup"><span data-stu-id="83543-323">Keywords</span></span>

<span data-ttu-id="83543-324">| |</span><span class="sxs-lookup"><span data-stu-id="83543-324"></span></span>
|<span data-ttu-id="83543-325">**Keywords_estonia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="83543-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="83543-326">通讯</span><span class="sxs-lookup"><span data-stu-id="83543-326">dl#</span></span>  <br/> <span data-ttu-id="83543-327">driver license</span><span class="sxs-lookup"><span data-stu-id="83543-327">driver license</span></span>  <br/> <span data-ttu-id="83543-328">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-328">driver license number</span></span>  <br/> <span data-ttu-id="83543-329">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-329">driver license number</span></span>  <br/> <span data-ttu-id="83543-330">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="83543-330">driver licence</span></span>  <br/> <span data-ttu-id="83543-331">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="83543-331">drivers lic.</span></span>  <br/> <span data-ttu-id="83543-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="83543-332">drivers license</span></span>  <br/> <span data-ttu-id="83543-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="83543-333">drivers licence</span></span>  <br/> <span data-ttu-id="83543-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="83543-334">driver's license</span></span>  <br/> <span data-ttu-id="83543-335">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-335">driver's license number</span></span>  <br/> <span data-ttu-id="83543-336">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-336">driving license number</span></span>  <br/> <span data-ttu-id="83543-337">dlno#</span><span class="sxs-lookup"><span data-stu-id="83543-337">dlno#</span></span>  <br/> <span data-ttu-id="83543-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="83543-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="83543-339">芬兰</span><span class="sxs-lookup"><span data-stu-id="83543-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="83543-340">Format</span><span class="sxs-lookup"><span data-stu-id="83543-340">Format</span></span>

<span data-ttu-id="83543-341">10 个数字，包含连字符</span><span class="sxs-lookup"><span data-stu-id="83543-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="83543-342">模式</span><span class="sxs-lookup"><span data-stu-id="83543-342">Pattern</span></span>

<span data-ttu-id="83543-343">10个数字, 包含连字符:</span><span class="sxs-lookup"><span data-stu-id="83543-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="83543-344">六位数字</span><span class="sxs-lookup"><span data-stu-id="83543-344">Six digits</span></span> 
    
- <span data-ttu-id="83543-345">一个连字符</span><span class="sxs-lookup"><span data-stu-id="83543-345">A hyphen</span></span>
    
-  <span data-ttu-id="83543-346">四个数字</span><span class="sxs-lookup"><span data-stu-id="83543-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="83543-347">校验和</span><span class="sxs-lookup"><span data-stu-id="83543-347">Checksum</span></span>

<span data-ttu-id="83543-348">否</span><span class="sxs-lookup"><span data-stu-id="83543-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="83543-349">定义</span><span class="sxs-lookup"><span data-stu-id="83543-349">Definition</span></span>

<span data-ttu-id="83543-350">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="83543-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="83543-351">正则表达式`Regex_finland_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="83543-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="83543-352">找到了中`Keywords_finland_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="83543-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="83543-353">关键字</span><span class="sxs-lookup"><span data-stu-id="83543-353">Keywords</span></span>

<span data-ttu-id="83543-354">| |</span><span class="sxs-lookup"><span data-stu-id="83543-354"></span></span>
|<span data-ttu-id="83543-355">**Keywords_finland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="83543-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="83543-356">通讯</span><span class="sxs-lookup"><span data-stu-id="83543-356">dl#</span></span>  <br/> <span data-ttu-id="83543-357">driver license</span><span class="sxs-lookup"><span data-stu-id="83543-357">driver license</span></span>  <br/> <span data-ttu-id="83543-358">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-358">driver license number</span></span>  <br/> <span data-ttu-id="83543-359">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="83543-359">driver licence</span></span>  <br/> <span data-ttu-id="83543-360">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="83543-360">drivers lic.</span></span>  <br/> <span data-ttu-id="83543-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="83543-361">drivers license</span></span>  <br/> <span data-ttu-id="83543-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="83543-362">drivers licence</span></span>  <br/> <span data-ttu-id="83543-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="83543-363">driver's license</span></span>  <br/> <span data-ttu-id="83543-364">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-364">driver's license number</span></span>  <br/> <span data-ttu-id="83543-365">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-365">driver's licence number</span></span>  <br/> <span data-ttu-id="83543-366">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-366">driving license number</span></span>  <br/> <span data-ttu-id="83543-367">dlno#</span><span class="sxs-lookup"><span data-stu-id="83543-367">dlno#</span></span>  <br/> <span data-ttu-id="83543-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="83543-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="83543-369">法国</span><span class="sxs-lookup"><span data-stu-id="83543-369">France</span></span>

<span data-ttu-id="83543-370">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "法国驾 License 号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="83543-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="83543-371">德国</span><span class="sxs-lookup"><span data-stu-id="83543-371">Germany</span></span>

<span data-ttu-id="83543-372">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "德语驱动程序号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="83543-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="83543-373">希腊</span><span class="sxs-lookup"><span data-stu-id="83543-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="83543-374">Format</span><span class="sxs-lookup"><span data-stu-id="83543-374">Format</span></span>

<span data-ttu-id="83543-375">9个数字, 不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="83543-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="83543-376">模式</span><span class="sxs-lookup"><span data-stu-id="83543-376">Pattern</span></span>

 <span data-ttu-id="83543-377">九个数字</span><span class="sxs-lookup"><span data-stu-id="83543-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="83543-378">校验和</span><span class="sxs-lookup"><span data-stu-id="83543-378">Checksum</span></span>

<span data-ttu-id="83543-379">否</span><span class="sxs-lookup"><span data-stu-id="83543-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="83543-380">定义</span><span class="sxs-lookup"><span data-stu-id="83543-380">Definition</span></span>

<span data-ttu-id="83543-381">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="83543-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="83543-382">正则表达式`Regex_greece_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="83543-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="83543-383">找到了中`Keywords_greece_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="83543-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="83543-384">关键字</span><span class="sxs-lookup"><span data-stu-id="83543-384">Keywords</span></span>

<span data-ttu-id="83543-385">| |</span><span class="sxs-lookup"><span data-stu-id="83543-385"></span></span>
|<span data-ttu-id="83543-386">**Keywords_greece_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="83543-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="83543-387">DlL</span><span class="sxs-lookup"><span data-stu-id="83543-387">dlL#</span></span>  <br/> <span data-ttu-id="83543-388">driver license</span><span class="sxs-lookup"><span data-stu-id="83543-388">driver license</span></span>  <br/> <span data-ttu-id="83543-389">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-389">driver license number</span></span>  <br/> <span data-ttu-id="83543-390">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="83543-390">driver licence</span></span>  <br/> <span data-ttu-id="83543-391">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="83543-391">drivers lic.</span></span>  <br/> <span data-ttu-id="83543-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="83543-392">drivers license</span></span>  <br/> <span data-ttu-id="83543-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="83543-393">drivers licence</span></span>  <br/> <span data-ttu-id="83543-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="83543-394">driver's license</span></span>  <br/> <span data-ttu-id="83543-395">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-395">driver's license number</span></span>  <br/> <span data-ttu-id="83543-396">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-396">driver's licence number</span></span>  <br/> <span data-ttu-id="83543-397">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-397">driving license number</span></span>  <br/> <span data-ttu-id="83543-398">dlno#</span><span class="sxs-lookup"><span data-stu-id="83543-398">dlno#</span></span>  <br/> <span data-ttu-id="83543-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="83543-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="83543-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="83543-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="83543-401">匈牙利</span><span class="sxs-lookup"><span data-stu-id="83543-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="83543-402">Format</span><span class="sxs-lookup"><span data-stu-id="83543-402">Format</span></span>

<span data-ttu-id="83543-403">两个字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="83543-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="83543-404">模式</span><span class="sxs-lookup"><span data-stu-id="83543-404">Pattern</span></span>

<span data-ttu-id="83543-405">两个字母和六个数字:</span><span class="sxs-lookup"><span data-stu-id="83543-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="83543-406">两个字母 (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="83543-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="83543-407">六个数字</span><span class="sxs-lookup"><span data-stu-id="83543-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="83543-408">校验和</span><span class="sxs-lookup"><span data-stu-id="83543-408">Checksum</span></span>

<span data-ttu-id="83543-409">否</span><span class="sxs-lookup"><span data-stu-id="83543-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="83543-410">定义</span><span class="sxs-lookup"><span data-stu-id="83543-410">Definition</span></span>

<span data-ttu-id="83543-411">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="83543-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="83543-412">正则表达式`Regex_hungary_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="83543-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="83543-413">找到了中`Keywords_hungary_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="83543-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="83543-414">关键字</span><span class="sxs-lookup"><span data-stu-id="83543-414">Keywords</span></span>

<span data-ttu-id="83543-415">| |</span><span class="sxs-lookup"><span data-stu-id="83543-415"></span></span>
|<span data-ttu-id="83543-416">**Keywords_hungary_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="83543-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="83543-417">通讯</span><span class="sxs-lookup"><span data-stu-id="83543-417">dl#</span></span>  <br/> <span data-ttu-id="83543-418">driver license</span><span class="sxs-lookup"><span data-stu-id="83543-418">driver license</span></span>  <br/> <span data-ttu-id="83543-419">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-419">driver license number</span></span>  <br/> <span data-ttu-id="83543-420">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="83543-420">driver licence</span></span>  <br/> <span data-ttu-id="83543-421">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="83543-421">drivers lic.</span></span>  <br/> <span data-ttu-id="83543-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="83543-422">drivers license</span></span>  <br/> <span data-ttu-id="83543-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="83543-423">drivers licence</span></span>  <br/> <span data-ttu-id="83543-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="83543-424">driver's license</span></span>  <br/> <span data-ttu-id="83543-425">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-425">driver's license number</span></span>  <br/> <span data-ttu-id="83543-426">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-426">driver's licence number</span></span>  <br/> <span data-ttu-id="83543-427">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-427">driving license number</span></span>  <br/> <span data-ttu-id="83543-428">dlno#</span><span class="sxs-lookup"><span data-stu-id="83543-428">dlno#</span></span>  <br/> <span data-ttu-id="83543-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="83543-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="83543-430">爱尔兰</span><span class="sxs-lookup"><span data-stu-id="83543-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="83543-431">Format</span><span class="sxs-lookup"><span data-stu-id="83543-431">Format</span></span>

<span data-ttu-id="83543-432">6位数, 后跟四个字母</span><span class="sxs-lookup"><span data-stu-id="83543-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="83543-433">模式</span><span class="sxs-lookup"><span data-stu-id="83543-433">Pattern</span></span>

<span data-ttu-id="83543-434">6位数字和四个字母:</span><span class="sxs-lookup"><span data-stu-id="83543-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="83543-435">六位数字</span><span class="sxs-lookup"><span data-stu-id="83543-435">Six digits</span></span>
    
- <span data-ttu-id="83543-436">四个字母 (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="83543-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="83543-437">校验和</span><span class="sxs-lookup"><span data-stu-id="83543-437">Checksum</span></span>

<span data-ttu-id="83543-438">否</span><span class="sxs-lookup"><span data-stu-id="83543-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="83543-439">定义</span><span class="sxs-lookup"><span data-stu-id="83543-439">Definition</span></span>

<span data-ttu-id="83543-440">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="83543-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="83543-441">正则表达式`Regex_ireland_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="83543-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="83543-442">找到了中`Keywords_ireland_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="83543-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="83543-443">关键字</span><span class="sxs-lookup"><span data-stu-id="83543-443">Keywords</span></span>

<span data-ttu-id="83543-444">| |</span><span class="sxs-lookup"><span data-stu-id="83543-444"></span></span>
|<span data-ttu-id="83543-445">**Keywords_ireland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="83543-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="83543-446">通讯</span><span class="sxs-lookup"><span data-stu-id="83543-446">dl#</span></span>  <br/> <span data-ttu-id="83543-447">driver license</span><span class="sxs-lookup"><span data-stu-id="83543-447">driver license</span></span>  <br/> <span data-ttu-id="83543-448">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-448">driver license number</span></span>  <br/> <span data-ttu-id="83543-449">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="83543-449">driver licence</span></span>  <br/> <span data-ttu-id="83543-450">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="83543-450">drivers lic.</span></span>  <br/> <span data-ttu-id="83543-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="83543-451">drivers license</span></span>  <br/> <span data-ttu-id="83543-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="83543-452">drivers licence</span></span>  <br/> <span data-ttu-id="83543-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="83543-453">driver's license</span></span>  <br/> <span data-ttu-id="83543-454">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-454">driver's license number</span></span>  <br/> <span data-ttu-id="83543-455">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-455">driver's licence number</span></span>  <br/> <span data-ttu-id="83543-456">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-456">driving license number</span></span>  <br/> <span data-ttu-id="83543-457">dlno#</span><span class="sxs-lookup"><span data-stu-id="83543-457">dlno#</span></span>  <br/> <span data-ttu-id="83543-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="83543-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="83543-459">意大利</span><span class="sxs-lookup"><span data-stu-id="83543-459">Italy</span></span>

<span data-ttu-id="83543-460">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "意大利驾驶执照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="83543-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="83543-461">拉脱维亚</span><span class="sxs-lookup"><span data-stu-id="83543-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="83543-462">Format</span><span class="sxs-lookup"><span data-stu-id="83543-462">Format</span></span>

<span data-ttu-id="83543-463">三个字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="83543-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="83543-464">模式</span><span class="sxs-lookup"><span data-stu-id="83543-464">Pattern</span></span>

<span data-ttu-id="83543-465">三个字母和六个数字:</span><span class="sxs-lookup"><span data-stu-id="83543-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="83543-466">三个字母 (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="83543-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="83543-467">六个数字</span><span class="sxs-lookup"><span data-stu-id="83543-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="83543-468">校验和</span><span class="sxs-lookup"><span data-stu-id="83543-468">Checksum</span></span>

<span data-ttu-id="83543-469">否</span><span class="sxs-lookup"><span data-stu-id="83543-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="83543-470">定义</span><span class="sxs-lookup"><span data-stu-id="83543-470">Definition</span></span>

<span data-ttu-id="83543-471">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="83543-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="83543-472">正则表达式`Regex_latvia_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="83543-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="83543-473">找到了中`Keywords_latvia_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="83543-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="83543-474">关键字</span><span class="sxs-lookup"><span data-stu-id="83543-474">Keywords</span></span>

<span data-ttu-id="83543-475">| |</span><span class="sxs-lookup"><span data-stu-id="83543-475"></span></span>
|<span data-ttu-id="83543-476">**Keywords_latvia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="83543-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="83543-477">通讯</span><span class="sxs-lookup"><span data-stu-id="83543-477">dl#</span></span>  <br/> <span data-ttu-id="83543-478">driver license</span><span class="sxs-lookup"><span data-stu-id="83543-478">driver license</span></span>  <br/> <span data-ttu-id="83543-479">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-479">driver license number</span></span>  <br/> <span data-ttu-id="83543-480">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="83543-480">driver licence</span></span>  <br/> <span data-ttu-id="83543-481">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="83543-481">drivers lic.</span></span>  <br/> <span data-ttu-id="83543-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="83543-482">drivers license</span></span>  <br/> <span data-ttu-id="83543-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="83543-483">drivers licence</span></span>  <br/> <span data-ttu-id="83543-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="83543-484">driver's license</span></span>  <br/> <span data-ttu-id="83543-485">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-485">driver's license number</span></span>  <br/> <span data-ttu-id="83543-486">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-486">driver's licence number</span></span>  <br/> <span data-ttu-id="83543-487">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-487">driving license number</span></span>  <br/> <span data-ttu-id="83543-488">dlno#</span><span class="sxs-lookup"><span data-stu-id="83543-488">dlno#</span></span>  <br/> <span data-ttu-id="83543-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="83543-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="83543-490">立陶宛</span><span class="sxs-lookup"><span data-stu-id="83543-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="83543-491">Format</span><span class="sxs-lookup"><span data-stu-id="83543-491">Format</span></span>

<span data-ttu-id="83543-492">8位数, 不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="83543-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="83543-493">模式</span><span class="sxs-lookup"><span data-stu-id="83543-493">Pattern</span></span>

 <span data-ttu-id="83543-494">八个数字</span><span class="sxs-lookup"><span data-stu-id="83543-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="83543-495">校验和</span><span class="sxs-lookup"><span data-stu-id="83543-495">Checksum</span></span>

<span data-ttu-id="83543-496">否</span><span class="sxs-lookup"><span data-stu-id="83543-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="83543-497">定义</span><span class="sxs-lookup"><span data-stu-id="83543-497">Definition</span></span>

<span data-ttu-id="83543-498">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="83543-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="83543-499">正则表达式`Regex_lithuania_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="83543-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="83543-500">找到了中`Keywords_lithuania_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="83543-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="83543-501">关键字</span><span class="sxs-lookup"><span data-stu-id="83543-501">Keywords</span></span>

<span data-ttu-id="83543-502">| |</span><span class="sxs-lookup"><span data-stu-id="83543-502"></span></span>
|<span data-ttu-id="83543-503">**Keywords_lithuania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="83543-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="83543-504">通讯</span><span class="sxs-lookup"><span data-stu-id="83543-504">dl#</span></span>  <br/> <span data-ttu-id="83543-505">driver license</span><span class="sxs-lookup"><span data-stu-id="83543-505">driver license</span></span>  <br/> <span data-ttu-id="83543-506">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-506">driver license number</span></span>  <br/> <span data-ttu-id="83543-507">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="83543-507">driver licence</span></span>  <br/> <span data-ttu-id="83543-508">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="83543-508">drivers lic.</span></span>  <br/> <span data-ttu-id="83543-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="83543-509">drivers license</span></span>  <br/> <span data-ttu-id="83543-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="83543-510">drivers licence</span></span>  <br/> <span data-ttu-id="83543-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="83543-511">driver's license</span></span>  <br/> <span data-ttu-id="83543-512">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-512">driver's license number</span></span>  <br/> <span data-ttu-id="83543-513">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-513">driver's licence number</span></span>  <br/> <span data-ttu-id="83543-514">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-514">driving license number</span></span>  <br/> <span data-ttu-id="83543-515">dlno#</span><span class="sxs-lookup"><span data-stu-id="83543-515">dlno#</span></span>  <br/> <span data-ttu-id="83543-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="83543-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="83543-517">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="83543-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="83543-518">Format</span><span class="sxs-lookup"><span data-stu-id="83543-518">Format</span></span>

<span data-ttu-id="83543-519">6位数, 不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="83543-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="83543-520">模式</span><span class="sxs-lookup"><span data-stu-id="83543-520">Pattern</span></span>

 <span data-ttu-id="83543-521">六个数字</span><span class="sxs-lookup"><span data-stu-id="83543-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="83543-522">校验和</span><span class="sxs-lookup"><span data-stu-id="83543-522">Checksum</span></span>

<span data-ttu-id="83543-523">否</span><span class="sxs-lookup"><span data-stu-id="83543-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="83543-524">定义</span><span class="sxs-lookup"><span data-stu-id="83543-524">Definition</span></span>

<span data-ttu-id="83543-525">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="83543-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="83543-526">正则表达式`Regex_luxemburg_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="83543-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="83543-527">找到了中`Keywords_luxemburg_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="83543-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="83543-528">关键字</span><span class="sxs-lookup"><span data-stu-id="83543-528">Keywords</span></span>

<span data-ttu-id="83543-529">| |</span><span class="sxs-lookup"><span data-stu-id="83543-529"></span></span>
|<span data-ttu-id="83543-530">**Keywords_luxemburg_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="83543-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="83543-531">通讯</span><span class="sxs-lookup"><span data-stu-id="83543-531">dl#</span></span>  <br/> <span data-ttu-id="83543-532">driver license</span><span class="sxs-lookup"><span data-stu-id="83543-532">driver license</span></span>  <br/> <span data-ttu-id="83543-533">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-533">driver license number</span></span>  <br/> <span data-ttu-id="83543-534">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="83543-534">driver licence</span></span>  <br/> <span data-ttu-id="83543-535">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="83543-535">drivers lic.</span></span>  <br/> <span data-ttu-id="83543-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="83543-536">drivers license</span></span>  <br/> <span data-ttu-id="83543-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="83543-537">drivers licence</span></span>  <br/> <span data-ttu-id="83543-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="83543-538">driver's license</span></span>  <br/> <span data-ttu-id="83543-539">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-539">driver's license number</span></span>  <br/> <span data-ttu-id="83543-540">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-540">driver's licence number</span></span>  <br/> <span data-ttu-id="83543-541">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-541">driving license number</span></span>  <br/> <span data-ttu-id="83543-542">dlno#</span><span class="sxs-lookup"><span data-stu-id="83543-542">dlno#</span></span>  <br/> <span data-ttu-id="83543-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="83543-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="83543-544">马耳他</span><span class="sxs-lookup"><span data-stu-id="83543-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="83543-545">Format</span><span class="sxs-lookup"><span data-stu-id="83543-545">Format</span></span>

<span data-ttu-id="83543-546">两个字符与指定模式中的六个数字的组合</span><span class="sxs-lookup"><span data-stu-id="83543-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="83543-547">模式</span><span class="sxs-lookup"><span data-stu-id="83543-547">Pattern</span></span>

<span data-ttu-id="83543-548">两个字符和六个数字的组合:</span><span class="sxs-lookup"><span data-stu-id="83543-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="83543-549">两个字符 (数字或字母, 而不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="83543-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="83543-550">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="83543-550">A space (optional)</span></span>
    
- <span data-ttu-id="83543-551">三个数字 </span><span class="sxs-lookup"><span data-stu-id="83543-551">Three digits</span></span>
    
- <span data-ttu-id="83543-552">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="83543-552">A space (optional)</span></span>
    
- <span data-ttu-id="83543-553">三位数字</span><span class="sxs-lookup"><span data-stu-id="83543-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="83543-554">校验和</span><span class="sxs-lookup"><span data-stu-id="83543-554">Checksum</span></span>

<span data-ttu-id="83543-555">否</span><span class="sxs-lookup"><span data-stu-id="83543-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="83543-556">定义</span><span class="sxs-lookup"><span data-stu-id="83543-556">Definition</span></span>

<span data-ttu-id="83543-557">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="83543-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="83543-558">正则表达式`Regex_malta_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="83543-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="83543-559">找到了中`Keywords_malta_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="83543-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="83543-560">关键字</span><span class="sxs-lookup"><span data-stu-id="83543-560">Keywords</span></span>

<span data-ttu-id="83543-561">| |</span><span class="sxs-lookup"><span data-stu-id="83543-561"></span></span>
|<span data-ttu-id="83543-562">**Keywords_malta_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="83543-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="83543-563">通讯</span><span class="sxs-lookup"><span data-stu-id="83543-563">dl#</span></span>  <br/> <span data-ttu-id="83543-564">driver license</span><span class="sxs-lookup"><span data-stu-id="83543-564">driver license</span></span>  <br/> <span data-ttu-id="83543-565">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-565">driver license number</span></span>  <br/> <span data-ttu-id="83543-566">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="83543-566">driver licence</span></span>  <br/> <span data-ttu-id="83543-567">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="83543-567">drivers lic.</span></span>  <br/> <span data-ttu-id="83543-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="83543-568">drivers license</span></span>  <br/> <span data-ttu-id="83543-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="83543-569">drivers licence</span></span>  <br/> <span data-ttu-id="83543-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="83543-570">driver's license</span></span>  <br/> <span data-ttu-id="83543-571">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-571">driver's license number</span></span>  <br/> <span data-ttu-id="83543-572">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-572">driver's licence number</span></span>  <br/> <span data-ttu-id="83543-573">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-573">driving license number</span></span>  <br/> <span data-ttu-id="83543-574">dlno#</span><span class="sxs-lookup"><span data-stu-id="83543-574">dlno#</span></span>  <br/> <span data-ttu-id="83543-575">liċenzja tas-sewqan</span><span class="sxs-lookup"><span data-stu-id="83543-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="83543-576">荷兰</span><span class="sxs-lookup"><span data-stu-id="83543-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="83543-577">Format</span><span class="sxs-lookup"><span data-stu-id="83543-577">Format</span></span>

<span data-ttu-id="83543-578">10个数字, 不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="83543-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="83543-579">模式</span><span class="sxs-lookup"><span data-stu-id="83543-579">Pattern</span></span>

<span data-ttu-id="83543-580">10 个数字</span><span class="sxs-lookup"><span data-stu-id="83543-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="83543-581">校验和</span><span class="sxs-lookup"><span data-stu-id="83543-581">Checksum</span></span>

<span data-ttu-id="83543-582">否</span><span class="sxs-lookup"><span data-stu-id="83543-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="83543-583">定义</span><span class="sxs-lookup"><span data-stu-id="83543-583">Definition</span></span>

<span data-ttu-id="83543-584">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="83543-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="83543-585">正则表达式`Regex_netherlands_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="83543-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="83543-586">找到了中`Keywords_netherlands_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="83543-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="83543-587">关键字</span><span class="sxs-lookup"><span data-stu-id="83543-587">Keywords</span></span>

<span data-ttu-id="83543-588">| |</span><span class="sxs-lookup"><span data-stu-id="83543-588"></span></span>
|<span data-ttu-id="83543-589">**Keywords_netherlands_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="83543-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="83543-590">通讯</span><span class="sxs-lookup"><span data-stu-id="83543-590">dl#</span></span>  <br/> <span data-ttu-id="83543-591">driver license</span><span class="sxs-lookup"><span data-stu-id="83543-591">driver license</span></span>  <br/> <span data-ttu-id="83543-592">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-592">driver license number</span></span>  <br/> <span data-ttu-id="83543-593">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="83543-593">driver licence</span></span>  <br/> <span data-ttu-id="83543-594">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="83543-594">drivers lic.</span></span>  <br/> <span data-ttu-id="83543-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="83543-595">drivers license</span></span>  <br/> <span data-ttu-id="83543-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="83543-596">drivers licence</span></span>  <br/> <span data-ttu-id="83543-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="83543-597">driver's license</span></span>  <br/> <span data-ttu-id="83543-598">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-598">driver's license number</span></span>  <br/> <span data-ttu-id="83543-599">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-599">driver's licence number</span></span>  <br/> <span data-ttu-id="83543-600">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-600">driving license number</span></span>  <br/> <span data-ttu-id="83543-601">dlno#</span><span class="sxs-lookup"><span data-stu-id="83543-601">dlno#</span></span>  <br/> <span data-ttu-id="83543-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="83543-602">permis de conduire</span></span>  <br/> <span data-ttu-id="83543-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="83543-603">rijbewijs</span></span>  <br/> <span data-ttu-id="83543-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="83543-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="83543-605">波兰</span><span class="sxs-lookup"><span data-stu-id="83543-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="83543-606">Format</span><span class="sxs-lookup"><span data-stu-id="83543-606">Format</span></span>

<span data-ttu-id="83543-607">14位数, 包含2个正斜杠</span><span class="sxs-lookup"><span data-stu-id="83543-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="83543-608">模式</span><span class="sxs-lookup"><span data-stu-id="83543-608">Pattern</span></span>

<span data-ttu-id="83543-609">14位数和2正斜杠:</span><span class="sxs-lookup"><span data-stu-id="83543-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="83543-610">五位数字</span><span class="sxs-lookup"><span data-stu-id="83543-610">Five digits</span></span> 
    
- <span data-ttu-id="83543-611">一个正斜杠 </span><span class="sxs-lookup"><span data-stu-id="83543-611">A forward slash</span></span>
    
- <span data-ttu-id="83543-612">两位数字</span><span class="sxs-lookup"><span data-stu-id="83543-612">Two digits</span></span>
    
- <span data-ttu-id="83543-613">一个正斜杠 </span><span class="sxs-lookup"><span data-stu-id="83543-613">A forward slash</span></span>
    
- <span data-ttu-id="83543-614">七个数字</span><span class="sxs-lookup"><span data-stu-id="83543-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="83543-615">校验和</span><span class="sxs-lookup"><span data-stu-id="83543-615">Checksum</span></span>

<span data-ttu-id="83543-616">否</span><span class="sxs-lookup"><span data-stu-id="83543-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="83543-617">定义</span><span class="sxs-lookup"><span data-stu-id="83543-617">Definition</span></span>

<span data-ttu-id="83543-618">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="83543-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="83543-619">正则表达式`Regex_poland_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="83543-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="83543-620">找到了中`Keywords_poland_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="83543-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="83543-621">关键字</span><span class="sxs-lookup"><span data-stu-id="83543-621">Keywords</span></span>

<span data-ttu-id="83543-622">| |</span><span class="sxs-lookup"><span data-stu-id="83543-622"></span></span>
|<span data-ttu-id="83543-623">**Keywords_poland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="83543-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="83543-624">通讯</span><span class="sxs-lookup"><span data-stu-id="83543-624">dl#</span></span>  <br/> <span data-ttu-id="83543-625">driver license</span><span class="sxs-lookup"><span data-stu-id="83543-625">driver license</span></span>  <br/> <span data-ttu-id="83543-626">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-626">driver license number</span></span>  <br/> <span data-ttu-id="83543-627">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="83543-627">driver licence</span></span>  <br/> <span data-ttu-id="83543-628">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="83543-628">drivers lic.</span></span>  <br/> <span data-ttu-id="83543-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="83543-629">drivers license</span></span>  <br/> <span data-ttu-id="83543-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="83543-630">drivers licence</span></span>  <br/> <span data-ttu-id="83543-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="83543-631">driver's license</span></span>  <br/> <span data-ttu-id="83543-632">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-632">driver's license number</span></span>  <br/> <span data-ttu-id="83543-633">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-633">driver's licence number</span></span>  <br/> <span data-ttu-id="83543-634">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-634">driving license number</span></span>  <br/> <span data-ttu-id="83543-635">dlno#</span><span class="sxs-lookup"><span data-stu-id="83543-635">dlno#</span></span>  <br/> <span data-ttu-id="83543-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="83543-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="83543-637">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="83543-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="83543-638">Format</span><span class="sxs-lookup"><span data-stu-id="83543-638">Format</span></span>

<span data-ttu-id="83543-639">两个字母后跟指定模式中的七个数字</span><span class="sxs-lookup"><span data-stu-id="83543-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="83543-640">模式</span><span class="sxs-lookup"><span data-stu-id="83543-640">Pattern</span></span>

<span data-ttu-id="83543-641">两个字母后跟七个包含特殊字符的数字:</span><span class="sxs-lookup"><span data-stu-id="83543-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="83543-642">两个字母 (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="83543-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="83543-643">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="83543-643">A hyphen</span></span>
    
- <span data-ttu-id="83543-644">六位数字</span><span class="sxs-lookup"><span data-stu-id="83543-644">Six digits</span></span>
    
- <span data-ttu-id="83543-645">一个空格</span><span class="sxs-lookup"><span data-stu-id="83543-645">A space</span></span>
    
- <span data-ttu-id="83543-646">一个数字</span><span class="sxs-lookup"><span data-stu-id="83543-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="83543-647">校验和</span><span class="sxs-lookup"><span data-stu-id="83543-647">Checksum</span></span>

<span data-ttu-id="83543-648">否</span><span class="sxs-lookup"><span data-stu-id="83543-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="83543-649">定义</span><span class="sxs-lookup"><span data-stu-id="83543-649">Definition</span></span>

<span data-ttu-id="83543-650">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="83543-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="83543-651">正则表达式`Regex_portugal_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="83543-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="83543-652">找到了中`Keywords_portugal_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="83543-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="83543-653">关键字</span><span class="sxs-lookup"><span data-stu-id="83543-653">Keywords</span></span>

<span data-ttu-id="83543-654">| |</span><span class="sxs-lookup"><span data-stu-id="83543-654"></span></span>
|<span data-ttu-id="83543-655">**Keywords_portugal_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="83543-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="83543-656">通讯</span><span class="sxs-lookup"><span data-stu-id="83543-656">dl#</span></span>  <br/> <span data-ttu-id="83543-657">driver license</span><span class="sxs-lookup"><span data-stu-id="83543-657">driver license</span></span>  <br/> <span data-ttu-id="83543-658">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-658">driver license number</span></span>  <br/> <span data-ttu-id="83543-659">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="83543-659">driver licence</span></span>  <br/> <span data-ttu-id="83543-660">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="83543-660">drivers lic.</span></span>  <br/> <span data-ttu-id="83543-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="83543-661">drivers license</span></span>  <br/> <span data-ttu-id="83543-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="83543-662">drivers licence</span></span>  <br/> <span data-ttu-id="83543-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="83543-663">driver's license</span></span>  <br/> <span data-ttu-id="83543-664">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-664">driver's license number</span></span>  <br/> <span data-ttu-id="83543-665">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-665">driver's licence number</span></span>  <br/> <span data-ttu-id="83543-666">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-666">driving license number</span></span>  <br/> <span data-ttu-id="83543-667">dlno#</span><span class="sxs-lookup"><span data-stu-id="83543-667">dlno#</span></span>  <br/> <span data-ttu-id="83543-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="83543-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="83543-669">罗马尼亚</span><span class="sxs-lookup"><span data-stu-id="83543-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="83543-670">Format</span><span class="sxs-lookup"><span data-stu-id="83543-670">Format</span></span>

<span data-ttu-id="83543-671">一个字符后跟八个数字</span><span class="sxs-lookup"><span data-stu-id="83543-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="83543-672">模式</span><span class="sxs-lookup"><span data-stu-id="83543-672">Pattern</span></span>

<span data-ttu-id="83543-673">一个字符后跟八个数字:</span><span class="sxs-lookup"><span data-stu-id="83543-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="83543-674">一个字母 (不区分大小写) 或数字</span><span class="sxs-lookup"><span data-stu-id="83543-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="83543-675">八个数字</span><span class="sxs-lookup"><span data-stu-id="83543-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="83543-676">校验和</span><span class="sxs-lookup"><span data-stu-id="83543-676">Checksum</span></span>

<span data-ttu-id="83543-677">否</span><span class="sxs-lookup"><span data-stu-id="83543-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="83543-678">定义</span><span class="sxs-lookup"><span data-stu-id="83543-678">Definition</span></span>

<span data-ttu-id="83543-679">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="83543-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="83543-680">正则表达式`Regex_romania_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="83543-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="83543-681">找到了中`Keywords_romania_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="83543-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="83543-682">关键字</span><span class="sxs-lookup"><span data-stu-id="83543-682">Keywords</span></span>

<span data-ttu-id="83543-683">| |</span><span class="sxs-lookup"><span data-stu-id="83543-683"></span></span>
|<span data-ttu-id="83543-684">**Keywords_romania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="83543-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="83543-685">通讯</span><span class="sxs-lookup"><span data-stu-id="83543-685">dl#</span></span>  <br/> <span data-ttu-id="83543-686">driver license</span><span class="sxs-lookup"><span data-stu-id="83543-686">driver license</span></span>  <br/> <span data-ttu-id="83543-687">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-687">driver license number</span></span>  <br/> <span data-ttu-id="83543-688">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="83543-688">driver licence</span></span>  <br/> <span data-ttu-id="83543-689">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="83543-689">drivers lic.</span></span>  <br/> <span data-ttu-id="83543-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="83543-690">drivers license</span></span>  <br/> <span data-ttu-id="83543-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="83543-691">drivers licence</span></span>  <br/> <span data-ttu-id="83543-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="83543-692">driver's license</span></span>  <br/> <span data-ttu-id="83543-693">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-693">driver's license number</span></span>  <br/> <span data-ttu-id="83543-694">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-694">driver's licence number</span></span>  <br/> <span data-ttu-id="83543-695">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-695">driving license number</span></span>  <br/> <span data-ttu-id="83543-696">dlno#</span><span class="sxs-lookup"><span data-stu-id="83543-696">dlno#</span></span>  <br/> <span data-ttu-id="83543-697">permis de conducere</span><span class="sxs-lookup"><span data-stu-id="83543-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="83543-698">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="83543-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="83543-699">Format</span><span class="sxs-lookup"><span data-stu-id="83543-699">Format</span></span>

<span data-ttu-id="83543-700">一个字符后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="83543-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="83543-701">模式</span><span class="sxs-lookup"><span data-stu-id="83543-701">Pattern</span></span>

<span data-ttu-id="83543-702">一个字符后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="83543-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="83543-703">一个字母 (不区分大小写) 或数字</span><span class="sxs-lookup"><span data-stu-id="83543-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="83543-704">七个数字</span><span class="sxs-lookup"><span data-stu-id="83543-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="83543-705">校验和</span><span class="sxs-lookup"><span data-stu-id="83543-705">Checksum</span></span>

<span data-ttu-id="83543-706">否</span><span class="sxs-lookup"><span data-stu-id="83543-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="83543-707">定义</span><span class="sxs-lookup"><span data-stu-id="83543-707">Definition</span></span>

<span data-ttu-id="83543-708">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="83543-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="83543-709">正则表达式`Regex_slovakia_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="83543-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="83543-710">找到了中`Keywords_slovakia_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="83543-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="83543-711">关键字</span><span class="sxs-lookup"><span data-stu-id="83543-711">Keywords</span></span>

<span data-ttu-id="83543-712">| |</span><span class="sxs-lookup"><span data-stu-id="83543-712"></span></span>
|<span data-ttu-id="83543-713">**Keywords_slovakia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="83543-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="83543-714">通讯</span><span class="sxs-lookup"><span data-stu-id="83543-714">dl#</span></span>  <br/> <span data-ttu-id="83543-715">driver license</span><span class="sxs-lookup"><span data-stu-id="83543-715">driver license</span></span>  <br/> <span data-ttu-id="83543-716">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-716">driver license number</span></span>  <br/> <span data-ttu-id="83543-717">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="83543-717">driver licence</span></span>  <br/> <span data-ttu-id="83543-718">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="83543-718">drivers lic.</span></span>  <br/> <span data-ttu-id="83543-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="83543-719">drivers license</span></span>  <br/> <span data-ttu-id="83543-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="83543-720">drivers licence</span></span>  <br/> <span data-ttu-id="83543-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="83543-721">driver's license</span></span>  <br/> <span data-ttu-id="83543-722">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-722">driver's license number</span></span>  <br/> <span data-ttu-id="83543-723">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-723">driver's licence number</span></span>  <br/> <span data-ttu-id="83543-724">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-724">driving license number</span></span>  <br/> <span data-ttu-id="83543-725">dlno#</span><span class="sxs-lookup"><span data-stu-id="83543-725">dlno#</span></span>  <br/> <span data-ttu-id="83543-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="83543-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="83543-727">斯洛文尼亚</span><span class="sxs-lookup"><span data-stu-id="83543-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="83543-728">Format</span><span class="sxs-lookup"><span data-stu-id="83543-728">Format</span></span>

<span data-ttu-id="83543-729">9个数字, 不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="83543-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="83543-730">模式</span><span class="sxs-lookup"><span data-stu-id="83543-730">Pattern</span></span>

<span data-ttu-id="83543-731">九个数字</span><span class="sxs-lookup"><span data-stu-id="83543-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="83543-732">校验和</span><span class="sxs-lookup"><span data-stu-id="83543-732">Checksum</span></span>

<span data-ttu-id="83543-733">否</span><span class="sxs-lookup"><span data-stu-id="83543-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="83543-734">定义</span><span class="sxs-lookup"><span data-stu-id="83543-734">Definition</span></span>

<span data-ttu-id="83543-735">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="83543-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="83543-736">正则表达式`Regex_slovenia_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="83543-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="83543-737">找到了中`Keywords_slovenia_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="83543-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="83543-738">关键字</span><span class="sxs-lookup"><span data-stu-id="83543-738">Keywords</span></span>

<span data-ttu-id="83543-739">| |</span><span class="sxs-lookup"><span data-stu-id="83543-739"></span></span>
|<span data-ttu-id="83543-740">**Keywords_slovenia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="83543-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="83543-741">通讯</span><span class="sxs-lookup"><span data-stu-id="83543-741">dl#</span></span>  <br/> <span data-ttu-id="83543-742">driver license</span><span class="sxs-lookup"><span data-stu-id="83543-742">driver license</span></span>  <br/> <span data-ttu-id="83543-743">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-743">driver license number</span></span>  <br/> <span data-ttu-id="83543-744">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="83543-744">driver licence</span></span>  <br/> <span data-ttu-id="83543-745">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="83543-745">drivers lic.</span></span>  <br/> <span data-ttu-id="83543-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="83543-746">drivers license</span></span>  <br/> <span data-ttu-id="83543-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="83543-747">drivers licence</span></span>  <br/> <span data-ttu-id="83543-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="83543-748">driver's license</span></span>  <br/> <span data-ttu-id="83543-749">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-749">driver's license number</span></span>  <br/> <span data-ttu-id="83543-750">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-750">driver's licence number</span></span>  <br/> <span data-ttu-id="83543-751">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-751">driving license number</span></span>  <br/> <span data-ttu-id="83543-752">dlno#</span><span class="sxs-lookup"><span data-stu-id="83543-752">dlno#</span></span>  <br/> <span data-ttu-id="83543-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="83543-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="83543-754">西班牙</span><span class="sxs-lookup"><span data-stu-id="83543-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="83543-755">Format</span><span class="sxs-lookup"><span data-stu-id="83543-755">Format</span></span>

<span data-ttu-id="83543-756">8位数, 后跟一个字符</span><span class="sxs-lookup"><span data-stu-id="83543-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="83543-757">模式</span><span class="sxs-lookup"><span data-stu-id="83543-757">Pattern</span></span>

<span data-ttu-id="83543-758">8位数, 后跟一个字符:</span><span class="sxs-lookup"><span data-stu-id="83543-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="83543-759">八个数字</span><span class="sxs-lookup"><span data-stu-id="83543-759">Eight digits</span></span> 
    
- <span data-ttu-id="83543-760">一个数字或字母 (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="83543-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="83543-761">校验和</span><span class="sxs-lookup"><span data-stu-id="83543-761">Checksum</span></span>

<span data-ttu-id="83543-762">是</span><span class="sxs-lookup"><span data-stu-id="83543-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="83543-763">定义</span><span class="sxs-lookup"><span data-stu-id="83543-763">Definition</span></span>

<span data-ttu-id="83543-764">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="83543-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="83543-765">函数`Func_spain_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="83543-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="83543-766">找到了中`Keywords_spain_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="83543-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="83543-767">关键字</span><span class="sxs-lookup"><span data-stu-id="83543-767">Keywords</span></span>

<span data-ttu-id="83543-768">| |</span><span class="sxs-lookup"><span data-stu-id="83543-768"></span></span>
|<span data-ttu-id="83543-769">**Keywords_spain_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="83543-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="83543-770">dlno#</span><span class="sxs-lookup"><span data-stu-id="83543-770">dlno#</span></span>  <br/> <span data-ttu-id="83543-771">通讯</span><span class="sxs-lookup"><span data-stu-id="83543-771">dl#</span></span>  <br/> <span data-ttu-id="83543-772">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="83543-772">drivers lic.</span></span>  <br/> <span data-ttu-id="83543-773">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="83543-773">driver licence</span></span>  <br/> <span data-ttu-id="83543-774">driver license</span><span class="sxs-lookup"><span data-stu-id="83543-774">driver license</span></span>  <br/> <span data-ttu-id="83543-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="83543-775">drivers licence</span></span>  <br/> <span data-ttu-id="83543-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="83543-776">drivers license</span></span>  <br/> <span data-ttu-id="83543-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="83543-777">driver's licence</span></span>  <br/> <span data-ttu-id="83543-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="83543-778">driver's license</span></span>  <br/> <span data-ttu-id="83543-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="83543-779">driving licence</span></span>  <br/> <span data-ttu-id="83543-780">driving license</span><span class="sxs-lookup"><span data-stu-id="83543-780">driving license</span></span>  <br/> <span data-ttu-id="83543-781">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-781">driver licence number</span></span>  <br/> <span data-ttu-id="83543-782">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-782">driver license number</span></span>  <br/> <span data-ttu-id="83543-783">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-783">drivers licence number</span></span>  <br/> <span data-ttu-id="83543-784">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-784">drivers license number</span></span>  <br/> <span data-ttu-id="83543-785">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-785">driver's licence number</span></span>  <br/> <span data-ttu-id="83543-786">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-786">driver's license number</span></span>  <br/> <span data-ttu-id="83543-787">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-787">driving licence number</span></span>  <br/> <span data-ttu-id="83543-788">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-788">driving license number</span></span>  <br/> <span data-ttu-id="83543-789">促进允许</span><span class="sxs-lookup"><span data-stu-id="83543-789">driving permit</span></span>  <br/> <span data-ttu-id="83543-790">驾驶允许号码</span><span class="sxs-lookup"><span data-stu-id="83543-790">driving permit number</span></span>  <br/> <span data-ttu-id="83543-791">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="83543-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="83543-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="83543-792">permiso conducción</span></span>  <br/> <span data-ttu-id="83543-793">número licencia conducir</span><span class="sxs-lookup"><span data-stu-id="83543-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="83543-794">número de carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="83543-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="83543-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="83543-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="83543-796">licencia conducir</span><span class="sxs-lookup"><span data-stu-id="83543-796">licencia conducir</span></span>  <br/> <span data-ttu-id="83543-797">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="83543-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="83543-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="83543-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="83543-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="83543-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="83543-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="83543-800">permiso conducir</span></span>  <br/> <span data-ttu-id="83543-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="83543-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="83543-802">el carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="83543-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="83543-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="83543-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="83543-804">瑞典</span><span class="sxs-lookup"><span data-stu-id="83543-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="83543-805">Format</span><span class="sxs-lookup"><span data-stu-id="83543-805">Format</span></span>

<span data-ttu-id="83543-806">10个数字, 包含连字符</span><span class="sxs-lookup"><span data-stu-id="83543-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="83543-807">模式</span><span class="sxs-lookup"><span data-stu-id="83543-807">Pattern</span></span>

<span data-ttu-id="83543-808">10位数, 包含连字符:</span><span class="sxs-lookup"><span data-stu-id="83543-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="83543-809">六位数字</span><span class="sxs-lookup"><span data-stu-id="83543-809">Six digits</span></span> 
    
- <span data-ttu-id="83543-810">一个连字符</span><span class="sxs-lookup"><span data-stu-id="83543-810">A hyphen</span></span>
    
- <span data-ttu-id="83543-811">四个数字</span><span class="sxs-lookup"><span data-stu-id="83543-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="83543-812">校验和</span><span class="sxs-lookup"><span data-stu-id="83543-812">Checksum</span></span>

<span data-ttu-id="83543-813">否</span><span class="sxs-lookup"><span data-stu-id="83543-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="83543-814">定义</span><span class="sxs-lookup"><span data-stu-id="83543-814">Definition</span></span>

<span data-ttu-id="83543-815">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="83543-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="83543-816">正则表达式`Regex_sweden_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="83543-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="83543-817">找到了中`Keywords_sweden_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="83543-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="83543-818">关键字</span><span class="sxs-lookup"><span data-stu-id="83543-818">Keywords</span></span>

<span data-ttu-id="83543-819">| |</span><span class="sxs-lookup"><span data-stu-id="83543-819"></span></span>
|<span data-ttu-id="83543-820">**Keywords_sweden_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="83543-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="83543-821">通讯</span><span class="sxs-lookup"><span data-stu-id="83543-821">dl#</span></span>  <br/> <span data-ttu-id="83543-822">driver license</span><span class="sxs-lookup"><span data-stu-id="83543-822">driver license</span></span>  <br/> <span data-ttu-id="83543-823">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-823">driver license number</span></span>  <br/> <span data-ttu-id="83543-824">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="83543-824">driver licence</span></span>  <br/> <span data-ttu-id="83543-825">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="83543-825">drivers lic.</span></span>  <br/> <span data-ttu-id="83543-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="83543-826">drivers license</span></span>  <br/> <span data-ttu-id="83543-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="83543-827">drivers licence</span></span>  <br/> <span data-ttu-id="83543-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="83543-828">driver's license</span></span>  <br/> <span data-ttu-id="83543-829">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-829">driver's license number</span></span>  <br/> <span data-ttu-id="83543-830">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="83543-830">driver's licence number</span></span>  <br/> <span data-ttu-id="83543-831">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="83543-831">driving license number</span></span>  <br/> <span data-ttu-id="83543-832">dlno#</span><span class="sxs-lookup"><span data-stu-id="83543-832">dlno#</span></span>  <br/> <span data-ttu-id="83543-833">körkort</span><span class="sxs-lookup"><span data-stu-id="83543-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="83543-834">英国</span><span class="sxs-lookup"><span data-stu-id="83543-834">UK</span></span>

<span data-ttu-id="83543-835">有关详细信息, 请参阅部分 "英国</span><span class="sxs-lookup"><span data-stu-id="83543-835">For details, see the section "U.K.</span></span> <span data-ttu-id="83543-836">"[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)" 中的 "驾驶执照号码"。</span><span class="sxs-lookup"><span data-stu-id="83543-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="83543-837">另请参阅</span><span class="sxs-lookup"><span data-stu-id="83543-837">See also</span></span>

[<span data-ttu-id="83543-838">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="83543-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

