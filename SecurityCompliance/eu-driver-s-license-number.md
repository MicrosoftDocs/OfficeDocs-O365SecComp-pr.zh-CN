---
title: 欧盟驾驶执照号码
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: c3923cd3-ec84-435f-bf41-cadc37996a4b
description: 本主题介绍当数据丢失防护 (DLP) 策略检测到欧盟驱动程序的敏感信息类型时, 应查找什么内容。此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。
ms.openlocfilehash: 86be7b52aed7581fd62ab595ac2c4b63ab33aab3
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217742"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="7478b-104">欧盟驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-104">EU Driver's License Number</span></span>

<span data-ttu-id="7478b-p102">本主题介绍当数据丢失防护 (DLP) 策略检测到欧盟驱动程序的敏感信息类型时, 应查找什么内容。此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。</span><span class="sxs-lookup"><span data-stu-id="7478b-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="7478b-107">奥地利</span><span class="sxs-lookup"><span data-stu-id="7478b-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="7478b-108">格式</span><span class="sxs-lookup"><span data-stu-id="7478b-108">Format</span></span>

<span data-ttu-id="7478b-109">8位数, 不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="7478b-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7478b-110">模式</span><span class="sxs-lookup"><span data-stu-id="7478b-110">Pattern</span></span>

<span data-ttu-id="7478b-111">八个数字</span><span class="sxs-lookup"><span data-stu-id="7478b-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="7478b-112">校验和</span><span class="sxs-lookup"><span data-stu-id="7478b-112">Checksum</span></span>

<span data-ttu-id="7478b-113">否</span><span class="sxs-lookup"><span data-stu-id="7478b-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7478b-114">定义</span><span class="sxs-lookup"><span data-stu-id="7478b-114">Definition</span></span>

<span data-ttu-id="7478b-115">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7478b-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7478b-116">正则表达式`Regex_austria_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7478b-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7478b-117">找到了中`Keywords_austria_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="7478b-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="7478b-118">关键字</span><span class="sxs-lookup"><span data-stu-id="7478b-118">Keywords</span></span>

<span data-ttu-id="7478b-119">| |</span><span class="sxs-lookup"><span data-stu-id="7478b-119"></span></span>
|<span data-ttu-id="7478b-120">**Keywords_austria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="7478b-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7478b-121">dl#</span><span class="sxs-lookup"><span data-stu-id="7478b-121">dl#</span></span>  <br/> <span data-ttu-id="7478b-122">driver license</span><span class="sxs-lookup"><span data-stu-id="7478b-122">driver license</span></span>  <br/> <span data-ttu-id="7478b-123">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-123">driver license number</span></span>  <br/> <span data-ttu-id="7478b-124">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="7478b-124">driver licence</span></span>  <br/> <span data-ttu-id="7478b-125">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="7478b-125">drivers lic.</span></span>  <br/> <span data-ttu-id="7478b-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="7478b-126">drivers license</span></span>  <br/> <span data-ttu-id="7478b-127">驾驶许可证</span><span class="sxs-lookup"><span data-stu-id="7478b-127">driver's licence</span></span>  <br/> <span data-ttu-id="7478b-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="7478b-128">driver's license</span></span>  <br/> <span data-ttu-id="7478b-129">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-129">driver's license number</span></span>  <br/> <span data-ttu-id="7478b-130">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="7478b-131">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-131">driving license number</span></span>  <br/> <span data-ttu-id="7478b-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="7478b-132">dlno#</span></span>  <br/> <span data-ttu-id="7478b-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="7478b-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="7478b-134">fuhrerschein republik osterreich</span><span class="sxs-lookup"><span data-stu-id="7478b-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="7478b-135">比利时</span><span class="sxs-lookup"><span data-stu-id="7478b-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="7478b-136">格式</span><span class="sxs-lookup"><span data-stu-id="7478b-136">Format</span></span>

<span data-ttu-id="7478b-137">10个数字, 不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="7478b-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7478b-138">模式</span><span class="sxs-lookup"><span data-stu-id="7478b-138">Pattern</span></span>

<span data-ttu-id="7478b-139">10 个数字</span><span class="sxs-lookup"><span data-stu-id="7478b-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="7478b-140">校验和</span><span class="sxs-lookup"><span data-stu-id="7478b-140">Checksum</span></span>

<span data-ttu-id="7478b-141">否</span><span class="sxs-lookup"><span data-stu-id="7478b-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7478b-142">定义</span><span class="sxs-lookup"><span data-stu-id="7478b-142">Definition</span></span>

<span data-ttu-id="7478b-143">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7478b-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7478b-144">正则表达式`Regex_belgium_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7478b-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7478b-145">找到了中`Keywords_belgium_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="7478b-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="7478b-146">关键字</span><span class="sxs-lookup"><span data-stu-id="7478b-146">Keywords</span></span>

<span data-ttu-id="7478b-147">| |</span><span class="sxs-lookup"><span data-stu-id="7478b-147"></span></span>
|<span data-ttu-id="7478b-148">**Keywords__belgium_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="7478b-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7478b-149">dl#</span><span class="sxs-lookup"><span data-stu-id="7478b-149">dl#</span></span>  <br/> <span data-ttu-id="7478b-150">driver license</span><span class="sxs-lookup"><span data-stu-id="7478b-150">driver license</span></span>  <br/> <span data-ttu-id="7478b-151">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-151">driver license number</span></span>  <br/> <span data-ttu-id="7478b-152">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="7478b-152">driver licence</span></span>  <br/> <span data-ttu-id="7478b-153">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="7478b-153">drivers lic.</span></span>  <br/> <span data-ttu-id="7478b-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="7478b-154">drivers license</span></span>  <br/> <span data-ttu-id="7478b-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7478b-155">drivers licence</span></span>  <br/> <span data-ttu-id="7478b-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="7478b-156">driver's license</span></span>  <br/> <span data-ttu-id="7478b-157">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-157">driver's license number</span></span>  <br/> <span data-ttu-id="7478b-158">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-158">driver's licence number</span></span>  <br/> <span data-ttu-id="7478b-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="7478b-159">dlno#</span></span>  <br/> <span data-ttu-id="7478b-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="7478b-160">rijbewijs</span></span>  <br/> <span data-ttu-id="7478b-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="7478b-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="7478b-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="7478b-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="7478b-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="7478b-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="7478b-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="7478b-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="7478b-165">führerschein-nr-nr</span><span class="sxs-lookup"><span data-stu-id="7478b-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="7478b-166">fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="7478b-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="7478b-167">fuehrerschein-nr</span><span class="sxs-lookup"><span data-stu-id="7478b-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="7478b-168">保加利亚</span><span class="sxs-lookup"><span data-stu-id="7478b-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="7478b-169">格式</span><span class="sxs-lookup"><span data-stu-id="7478b-169">Format</span></span>

<span data-ttu-id="7478b-170">9个数字, 不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="7478b-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7478b-171">模式</span><span class="sxs-lookup"><span data-stu-id="7478b-171">Pattern</span></span>

<span data-ttu-id="7478b-172">九个数字</span><span class="sxs-lookup"><span data-stu-id="7478b-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="7478b-173">校验和</span><span class="sxs-lookup"><span data-stu-id="7478b-173">Checksum</span></span>

<span data-ttu-id="7478b-174">否</span><span class="sxs-lookup"><span data-stu-id="7478b-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7478b-175">定义</span><span class="sxs-lookup"><span data-stu-id="7478b-175">Definition</span></span>

<span data-ttu-id="7478b-176">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7478b-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7478b-177">正则表达式`Regex_bulgaria_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7478b-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7478b-178">找到了中`Keywords_bulgaria_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="7478b-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="7478b-179">关键字</span><span class="sxs-lookup"><span data-stu-id="7478b-179">Keywords</span></span>

<span data-ttu-id="7478b-180">| |</span><span class="sxs-lookup"><span data-stu-id="7478b-180"></span></span>
|<span data-ttu-id="7478b-181">**Keywords_bulgaria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="7478b-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7478b-182">dl#</span><span class="sxs-lookup"><span data-stu-id="7478b-182">dl#</span></span>  <br/> <span data-ttu-id="7478b-183">driver license</span><span class="sxs-lookup"><span data-stu-id="7478b-183">driver license</span></span>  <br/> <span data-ttu-id="7478b-184">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-184">driver license number</span></span>  <br/> <span data-ttu-id="7478b-185">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="7478b-185">driver licence</span></span>  <br/> <span data-ttu-id="7478b-186">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="7478b-186">drivers lic.</span></span>  <br/> <span data-ttu-id="7478b-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="7478b-187">drivers license</span></span>  <br/> <span data-ttu-id="7478b-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7478b-188">drivers licence</span></span>  <br/> <span data-ttu-id="7478b-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="7478b-189">driver's license</span></span>  <br/> <span data-ttu-id="7478b-190">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-190">driver's license number</span></span>  <br/> <span data-ttu-id="7478b-191">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-191">driver's licence number</span></span>  <br/> <span data-ttu-id="7478b-192">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-192">driving license number</span></span>  <br/> <span data-ttu-id="7478b-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="7478b-193">dlno#</span></span>  <br/> <span data-ttu-id="7478b-194">свидетелствозауправлениенампс</span><span class="sxs-lookup"><span data-stu-id="7478b-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="7478b-195">свидетелствозауправлениенамоторнопревозносредство</span><span class="sxs-lookup"><span data-stu-id="7478b-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="7478b-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="7478b-196">сумпс</span></span>  <br/> <span data-ttu-id="7478b-197">шофьорскакнижка</span><span class="sxs-lookup"><span data-stu-id="7478b-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="7478b-198">克罗地亚</span><span class="sxs-lookup"><span data-stu-id="7478b-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="7478b-199">格式</span><span class="sxs-lookup"><span data-stu-id="7478b-199">Format</span></span>

<span data-ttu-id="7478b-200">8位数, 不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="7478b-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7478b-201">模式</span><span class="sxs-lookup"><span data-stu-id="7478b-201">Pattern</span></span>

<span data-ttu-id="7478b-202">八个数字</span><span class="sxs-lookup"><span data-stu-id="7478b-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="7478b-203">校验和</span><span class="sxs-lookup"><span data-stu-id="7478b-203">Checksum</span></span>

<span data-ttu-id="7478b-204">否</span><span class="sxs-lookup"><span data-stu-id="7478b-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7478b-205">定义</span><span class="sxs-lookup"><span data-stu-id="7478b-205">Definition</span></span>

<span data-ttu-id="7478b-206">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7478b-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7478b-207">正则表达式`Regex_croatia_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7478b-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7478b-208">找到了中`Keywords_croatia_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="7478b-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="7478b-209">关键字</span><span class="sxs-lookup"><span data-stu-id="7478b-209">Keywords</span></span>

<span data-ttu-id="7478b-210">| |</span><span class="sxs-lookup"><span data-stu-id="7478b-210"></span></span>
|<span data-ttu-id="7478b-211">**Keywords_croatia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="7478b-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7478b-212">dl#</span><span class="sxs-lookup"><span data-stu-id="7478b-212">dl#</span></span>  <br/> <span data-ttu-id="7478b-213">driver license</span><span class="sxs-lookup"><span data-stu-id="7478b-213">driver license</span></span>  <br/> <span data-ttu-id="7478b-214">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-214">driver license number</span></span>  <br/> <span data-ttu-id="7478b-215">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="7478b-215">driver licence</span></span>  <br/> <span data-ttu-id="7478b-216">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="7478b-216">drivers lic.</span></span>  <br/> <span data-ttu-id="7478b-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="7478b-217">drivers license</span></span>  <br/> <span data-ttu-id="7478b-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7478b-218">drivers licence</span></span>  <br/> <span data-ttu-id="7478b-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="7478b-219">driver's license</span></span>  <br/> <span data-ttu-id="7478b-220">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-220">driver's license number</span></span>  <br/> <span data-ttu-id="7478b-221">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-221">driver's licence number</span></span>  <br/> <span data-ttu-id="7478b-222">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-222">driving license number</span></span>  <br/> <span data-ttu-id="7478b-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="7478b-223">dlno#</span></span>  <br/> <span data-ttu-id="7478b-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="7478b-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="7478b-225">塞浦路斯</span><span class="sxs-lookup"><span data-stu-id="7478b-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="7478b-226">格式</span><span class="sxs-lookup"><span data-stu-id="7478b-226">Format</span></span>

<span data-ttu-id="7478b-227">12个数字, 不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="7478b-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7478b-228">模式</span><span class="sxs-lookup"><span data-stu-id="7478b-228">Pattern</span></span>

<span data-ttu-id="7478b-229">12 个数字</span><span class="sxs-lookup"><span data-stu-id="7478b-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="7478b-230">校验和</span><span class="sxs-lookup"><span data-stu-id="7478b-230">Checksum</span></span>

<span data-ttu-id="7478b-231">否</span><span class="sxs-lookup"><span data-stu-id="7478b-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7478b-232">定义</span><span class="sxs-lookup"><span data-stu-id="7478b-232">Definition</span></span>

<span data-ttu-id="7478b-233">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7478b-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7478b-234">正则表达式`Regex_cyprus_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7478b-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7478b-235">找到了中`Keywords_cyprus_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="7478b-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7478b-236">关键字</span><span class="sxs-lookup"><span data-stu-id="7478b-236">Keywords</span></span>

<span data-ttu-id="7478b-237">| |</span><span class="sxs-lookup"><span data-stu-id="7478b-237"></span></span>
|<span data-ttu-id="7478b-238">**Keywords_cyprus_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="7478b-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7478b-239">dl#</span><span class="sxs-lookup"><span data-stu-id="7478b-239">dl#</span></span>  <br/> <span data-ttu-id="7478b-240">driver license</span><span class="sxs-lookup"><span data-stu-id="7478b-240">driver license</span></span>  <br/> <span data-ttu-id="7478b-241">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-241">driver license number</span></span>  <br/> <span data-ttu-id="7478b-242">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="7478b-242">driver licence</span></span>  <br/> <span data-ttu-id="7478b-243">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="7478b-243">drivers lic.</span></span>  <br/> <span data-ttu-id="7478b-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="7478b-244">drivers license</span></span>  <br/> <span data-ttu-id="7478b-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7478b-245">drivers licence</span></span>  <br/> <span data-ttu-id="7478b-246">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-246">driver's license number</span></span>  <br/> <span data-ttu-id="7478b-247">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-247">driver's licence number</span></span>  <br/> <span data-ttu-id="7478b-248">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-248">driving license number</span></span>  <br/> <span data-ttu-id="7478b-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="7478b-249">dlno#</span></span>  <br/> <span data-ttu-id="7478b-250">άδειαοδήγησης</span><span class="sxs-lookup"><span data-stu-id="7478b-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="7478b-251">捷克共和国</span><span class="sxs-lookup"><span data-stu-id="7478b-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="7478b-252">格式</span><span class="sxs-lookup"><span data-stu-id="7478b-252">Format</span></span>

<span data-ttu-id="7478b-253">两个字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="7478b-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7478b-254">模式</span><span class="sxs-lookup"><span data-stu-id="7478b-254">Pattern</span></span>

<span data-ttu-id="7478b-255">八个字母和数字:</span><span class="sxs-lookup"><span data-stu-id="7478b-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="7478b-256">两个字母 (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="7478b-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="7478b-257">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="7478b-257">A space (optional)</span></span>
    
- <span data-ttu-id="7478b-258">六个数字</span><span class="sxs-lookup"><span data-stu-id="7478b-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7478b-259">校验和</span><span class="sxs-lookup"><span data-stu-id="7478b-259">Checksum</span></span>

<span data-ttu-id="7478b-260">否</span><span class="sxs-lookup"><span data-stu-id="7478b-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7478b-261">定义</span><span class="sxs-lookup"><span data-stu-id="7478b-261">Definition</span></span>

<span data-ttu-id="7478b-262">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7478b-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7478b-263">正则表达式`Regex_czech_republic_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7478b-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7478b-264">找到了中`Keywords_czech_republic_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="7478b-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="7478b-265">关键字</span><span class="sxs-lookup"><span data-stu-id="7478b-265">Keywords</span></span>

<span data-ttu-id="7478b-266">| |</span><span class="sxs-lookup"><span data-stu-id="7478b-266"></span></span>
|<span data-ttu-id="7478b-267">**Keywords_czech_republic_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="7478b-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7478b-268">dl#</span><span class="sxs-lookup"><span data-stu-id="7478b-268">dl#</span></span>  <br/> <span data-ttu-id="7478b-269">driver license</span><span class="sxs-lookup"><span data-stu-id="7478b-269">driver license</span></span>  <br/> <span data-ttu-id="7478b-270">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-270">driver license number</span></span>  <br/> <span data-ttu-id="7478b-271">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="7478b-271">driver licence</span></span>  <br/> <span data-ttu-id="7478b-272">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="7478b-272">drivers lic.</span></span>  <br/> <span data-ttu-id="7478b-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="7478b-273">drivers license</span></span>  <br/> <span data-ttu-id="7478b-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7478b-274">drivers licence</span></span>  <br/> <span data-ttu-id="7478b-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="7478b-275">driver's license</span></span>  <br/> <span data-ttu-id="7478b-276">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-276">driver's license number</span></span>  <br/> <span data-ttu-id="7478b-277">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-277">driver's license number</span></span>  <br/> <span data-ttu-id="7478b-278">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-278">driver's licence number</span></span>  <br/> <span data-ttu-id="7478b-279">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-279">driving license number</span></span>  <br/> <span data-ttu-id="7478b-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="7478b-280">dlno#</span></span>  <br/> <span data-ttu-id="7478b-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="7478b-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="7478b-282">丹麦</span><span class="sxs-lookup"><span data-stu-id="7478b-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="7478b-283">格式</span><span class="sxs-lookup"><span data-stu-id="7478b-283">Format</span></span>

<span data-ttu-id="7478b-284">8位数, 不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="7478b-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7478b-285">模式</span><span class="sxs-lookup"><span data-stu-id="7478b-285">Pattern</span></span>

<span data-ttu-id="7478b-286">八个数字</span><span class="sxs-lookup"><span data-stu-id="7478b-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="7478b-287">校验和</span><span class="sxs-lookup"><span data-stu-id="7478b-287">Checksum</span></span>

<span data-ttu-id="7478b-288">是</span><span class="sxs-lookup"><span data-stu-id="7478b-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7478b-289">定义</span><span class="sxs-lookup"><span data-stu-id="7478b-289">Definition</span></span>

<span data-ttu-id="7478b-290">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7478b-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7478b-291">正则表达式`Regex_denmark_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7478b-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7478b-292">找到了中`Keywords_denmark_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="7478b-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="7478b-293">关键字</span><span class="sxs-lookup"><span data-stu-id="7478b-293">Keywords</span></span>

<span data-ttu-id="7478b-294">| |</span><span class="sxs-lookup"><span data-stu-id="7478b-294"></span></span>
|<span data-ttu-id="7478b-295">**Keywords_denmark_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="7478b-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7478b-296">dl#</span><span class="sxs-lookup"><span data-stu-id="7478b-296">dl#</span></span>  <br/> <span data-ttu-id="7478b-297">driver license</span><span class="sxs-lookup"><span data-stu-id="7478b-297">driver license</span></span>  <br/> <span data-ttu-id="7478b-298">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-298">driver license number</span></span>  <br/> <span data-ttu-id="7478b-299">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="7478b-299">driver licence</span></span>  <br/> <span data-ttu-id="7478b-300">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="7478b-300">drivers lic.</span></span>  <br/> <span data-ttu-id="7478b-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="7478b-301">drivers license</span></span>  <br/> <span data-ttu-id="7478b-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7478b-302">drivers licence</span></span>  <br/> <span data-ttu-id="7478b-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="7478b-303">driver's license</span></span>  <br/> <span data-ttu-id="7478b-304">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-304">driver's license number</span></span>  <br/> <span data-ttu-id="7478b-305">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-305">driver's licence number</span></span>  <br/> <span data-ttu-id="7478b-306">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-306">driving license number</span></span>  <br/> <span data-ttu-id="7478b-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="7478b-307">dlno#</span></span>  <br/> <span data-ttu-id="7478b-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="7478b-308">kørekort</span></span>  <br/> <span data-ttu-id="7478b-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="7478b-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="7478b-310">爱沙尼亚</span><span class="sxs-lookup"><span data-stu-id="7478b-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="7478b-311">格式</span><span class="sxs-lookup"><span data-stu-id="7478b-311">Format</span></span>

<span data-ttu-id="7478b-312">两个字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="7478b-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7478b-313">模式</span><span class="sxs-lookup"><span data-stu-id="7478b-313">Pattern</span></span>

<span data-ttu-id="7478b-314">两个字母和六个数字:</span><span class="sxs-lookup"><span data-stu-id="7478b-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="7478b-315">字母 "ET" (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="7478b-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="7478b-316">六个数字</span><span class="sxs-lookup"><span data-stu-id="7478b-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7478b-317">校验和</span><span class="sxs-lookup"><span data-stu-id="7478b-317">Checksum</span></span>

<span data-ttu-id="7478b-318">否</span><span class="sxs-lookup"><span data-stu-id="7478b-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7478b-319">定义</span><span class="sxs-lookup"><span data-stu-id="7478b-319">Definition</span></span>

<span data-ttu-id="7478b-320">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7478b-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7478b-321">正则表达式`Regex_estonia_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7478b-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7478b-322">找到了中`Keywords_estonia_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="7478b-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7478b-323">关键字</span><span class="sxs-lookup"><span data-stu-id="7478b-323">Keywords</span></span>

<span data-ttu-id="7478b-324">| |</span><span class="sxs-lookup"><span data-stu-id="7478b-324"></span></span>
|<span data-ttu-id="7478b-325">**Keywords_estonia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="7478b-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7478b-326">dl#</span><span class="sxs-lookup"><span data-stu-id="7478b-326">dl#</span></span>  <br/> <span data-ttu-id="7478b-327">driver license</span><span class="sxs-lookup"><span data-stu-id="7478b-327">driver license</span></span>  <br/> <span data-ttu-id="7478b-328">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-328">driver license number</span></span>  <br/> <span data-ttu-id="7478b-329">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-329">driver license number</span></span>  <br/> <span data-ttu-id="7478b-330">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="7478b-330">driver licence</span></span>  <br/> <span data-ttu-id="7478b-331">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="7478b-331">drivers lic.</span></span>  <br/> <span data-ttu-id="7478b-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="7478b-332">drivers license</span></span>  <br/> <span data-ttu-id="7478b-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7478b-333">drivers licence</span></span>  <br/> <span data-ttu-id="7478b-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="7478b-334">driver's license</span></span>  <br/> <span data-ttu-id="7478b-335">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-335">driver's license number</span></span>  <br/> <span data-ttu-id="7478b-336">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-336">driving license number</span></span>  <br/> <span data-ttu-id="7478b-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="7478b-337">dlno#</span></span>  <br/> <span data-ttu-id="7478b-338">
permis de conduire</span><span class="sxs-lookup"><span data-stu-id="7478b-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="7478b-339">芬兰</span><span class="sxs-lookup"><span data-stu-id="7478b-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="7478b-340">格式</span><span class="sxs-lookup"><span data-stu-id="7478b-340">Format</span></span>

<span data-ttu-id="7478b-341">10 个数字，包含连字符</span><span class="sxs-lookup"><span data-stu-id="7478b-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7478b-342">模式</span><span class="sxs-lookup"><span data-stu-id="7478b-342">Pattern</span></span>

<span data-ttu-id="7478b-343">10个数字, 包含连字符:</span><span class="sxs-lookup"><span data-stu-id="7478b-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="7478b-344">六位数字</span><span class="sxs-lookup"><span data-stu-id="7478b-344">Six digits</span></span> 
    
- <span data-ttu-id="7478b-345">连字符</span><span class="sxs-lookup"><span data-stu-id="7478b-345">A hyphen</span></span>
    
-  <span data-ttu-id="7478b-346">四位数字</span><span class="sxs-lookup"><span data-stu-id="7478b-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="7478b-347">校验和</span><span class="sxs-lookup"><span data-stu-id="7478b-347">Checksum</span></span>

<span data-ttu-id="7478b-348">否</span><span class="sxs-lookup"><span data-stu-id="7478b-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7478b-349">定义</span><span class="sxs-lookup"><span data-stu-id="7478b-349">Definition</span></span>

<span data-ttu-id="7478b-350">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7478b-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7478b-351">正则表达式`Regex_finland_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7478b-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7478b-352">找到了中`Keywords_finland_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="7478b-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7478b-353">关键字</span><span class="sxs-lookup"><span data-stu-id="7478b-353">Keywords</span></span>

<span data-ttu-id="7478b-354">| |</span><span class="sxs-lookup"><span data-stu-id="7478b-354"></span></span>
|<span data-ttu-id="7478b-355">**Keywords_finland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="7478b-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7478b-356">dl#</span><span class="sxs-lookup"><span data-stu-id="7478b-356">dl#</span></span>  <br/> <span data-ttu-id="7478b-357">driver license</span><span class="sxs-lookup"><span data-stu-id="7478b-357">driver license</span></span>  <br/> <span data-ttu-id="7478b-358">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-358">driver license number</span></span>  <br/> <span data-ttu-id="7478b-359">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="7478b-359">driver licence</span></span>  <br/> <span data-ttu-id="7478b-360">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="7478b-360">drivers lic.</span></span>  <br/> <span data-ttu-id="7478b-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="7478b-361">drivers license</span></span>  <br/> <span data-ttu-id="7478b-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7478b-362">drivers licence</span></span>  <br/> <span data-ttu-id="7478b-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="7478b-363">driver's license</span></span>  <br/> <span data-ttu-id="7478b-364">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-364">driver's license number</span></span>  <br/> <span data-ttu-id="7478b-365">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-365">driver's licence number</span></span>  <br/> <span data-ttu-id="7478b-366">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-366">driving license number</span></span>  <br/> <span data-ttu-id="7478b-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="7478b-367">dlno#</span></span>  <br/> <span data-ttu-id="7478b-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="7478b-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="7478b-369">法国</span><span class="sxs-lookup"><span data-stu-id="7478b-369">France</span></span>

<span data-ttu-id="7478b-370">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "法国驾 License 号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="7478b-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="7478b-371">德国</span><span class="sxs-lookup"><span data-stu-id="7478b-371">Germany</span></span>

<span data-ttu-id="7478b-372">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "德语驱动程序号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="7478b-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="7478b-373">希腊</span><span class="sxs-lookup"><span data-stu-id="7478b-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="7478b-374">格式</span><span class="sxs-lookup"><span data-stu-id="7478b-374">Format</span></span>

<span data-ttu-id="7478b-375">9个数字, 不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="7478b-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7478b-376">模式</span><span class="sxs-lookup"><span data-stu-id="7478b-376">Pattern</span></span>

 <span data-ttu-id="7478b-377">九个数字</span><span class="sxs-lookup"><span data-stu-id="7478b-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="7478b-378">校验和</span><span class="sxs-lookup"><span data-stu-id="7478b-378">Checksum</span></span>

<span data-ttu-id="7478b-379">否</span><span class="sxs-lookup"><span data-stu-id="7478b-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7478b-380">定义</span><span class="sxs-lookup"><span data-stu-id="7478b-380">Definition</span></span>

<span data-ttu-id="7478b-381">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7478b-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7478b-382">正则表达式`Regex_greece_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7478b-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7478b-383">找到了中`Keywords_greece_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="7478b-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7478b-384">关键字</span><span class="sxs-lookup"><span data-stu-id="7478b-384">Keywords</span></span>

<span data-ttu-id="7478b-385">| |</span><span class="sxs-lookup"><span data-stu-id="7478b-385"></span></span>
|<span data-ttu-id="7478b-386">**Keywords_greece_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="7478b-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7478b-387">dlL</span><span class="sxs-lookup"><span data-stu-id="7478b-387">dlL#</span></span>  <br/> <span data-ttu-id="7478b-388">driver license</span><span class="sxs-lookup"><span data-stu-id="7478b-388">driver license</span></span>  <br/> <span data-ttu-id="7478b-389">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-389">driver license number</span></span>  <br/> <span data-ttu-id="7478b-390">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="7478b-390">driver licence</span></span>  <br/> <span data-ttu-id="7478b-391">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="7478b-391">drivers lic.</span></span>  <br/> <span data-ttu-id="7478b-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="7478b-392">drivers license</span></span>  <br/> <span data-ttu-id="7478b-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7478b-393">drivers licence</span></span>  <br/> <span data-ttu-id="7478b-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="7478b-394">driver's license</span></span>  <br/> <span data-ttu-id="7478b-395">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-395">driver's license number</span></span>  <br/> <span data-ttu-id="7478b-396">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-396">driver's licence number</span></span>  <br/> <span data-ttu-id="7478b-397">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-397">driving license number</span></span>  <br/> <span data-ttu-id="7478b-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="7478b-398">dlno#</span></span>  <br/> <span data-ttu-id="7478b-399">δειαοδήγησης</span><span class="sxs-lookup"><span data-stu-id="7478b-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="7478b-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="7478b-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="7478b-401">匈牙利</span><span class="sxs-lookup"><span data-stu-id="7478b-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="7478b-402">格式</span><span class="sxs-lookup"><span data-stu-id="7478b-402">Format</span></span>

<span data-ttu-id="7478b-403">两个字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="7478b-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7478b-404">模式</span><span class="sxs-lookup"><span data-stu-id="7478b-404">Pattern</span></span>

<span data-ttu-id="7478b-405">两个字母和六个数字:</span><span class="sxs-lookup"><span data-stu-id="7478b-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="7478b-406">两个字母 (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="7478b-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="7478b-407">六个数字</span><span class="sxs-lookup"><span data-stu-id="7478b-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7478b-408">校验和</span><span class="sxs-lookup"><span data-stu-id="7478b-408">Checksum</span></span>

<span data-ttu-id="7478b-409">否</span><span class="sxs-lookup"><span data-stu-id="7478b-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7478b-410">定义</span><span class="sxs-lookup"><span data-stu-id="7478b-410">Definition</span></span>

<span data-ttu-id="7478b-411">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7478b-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7478b-412">正则表达式`Regex_hungary_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7478b-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7478b-413">找到了中`Keywords_hungary_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="7478b-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7478b-414">关键字</span><span class="sxs-lookup"><span data-stu-id="7478b-414">Keywords</span></span>

<span data-ttu-id="7478b-415">| |</span><span class="sxs-lookup"><span data-stu-id="7478b-415"></span></span>
|<span data-ttu-id="7478b-416">**Keywords_hungary_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="7478b-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7478b-417">dl#</span><span class="sxs-lookup"><span data-stu-id="7478b-417">dl#</span></span>  <br/> <span data-ttu-id="7478b-418">driver license</span><span class="sxs-lookup"><span data-stu-id="7478b-418">driver license</span></span>  <br/> <span data-ttu-id="7478b-419">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-419">driver license number</span></span>  <br/> <span data-ttu-id="7478b-420">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="7478b-420">driver licence</span></span>  <br/> <span data-ttu-id="7478b-421">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="7478b-421">drivers lic.</span></span>  <br/> <span data-ttu-id="7478b-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="7478b-422">drivers license</span></span>  <br/> <span data-ttu-id="7478b-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7478b-423">drivers licence</span></span>  <br/> <span data-ttu-id="7478b-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="7478b-424">driver's license</span></span>  <br/> <span data-ttu-id="7478b-425">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-425">driver's license number</span></span>  <br/> <span data-ttu-id="7478b-426">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-426">driver's licence number</span></span>  <br/> <span data-ttu-id="7478b-427">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-427">driving license number</span></span>  <br/> <span data-ttu-id="7478b-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="7478b-428">dlno#</span></span>  <br/> <span data-ttu-id="7478b-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="7478b-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="7478b-430">Ireland</span><span class="sxs-lookup"><span data-stu-id="7478b-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="7478b-431">格式</span><span class="sxs-lookup"><span data-stu-id="7478b-431">Format</span></span>

<span data-ttu-id="7478b-432">6位数, 后跟四个字母</span><span class="sxs-lookup"><span data-stu-id="7478b-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7478b-433">模式</span><span class="sxs-lookup"><span data-stu-id="7478b-433">Pattern</span></span>

<span data-ttu-id="7478b-434">6位数字和四个字母:</span><span class="sxs-lookup"><span data-stu-id="7478b-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="7478b-435">六位数字</span><span class="sxs-lookup"><span data-stu-id="7478b-435">Six digits</span></span>
    
- <span data-ttu-id="7478b-436">四个字母 (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="7478b-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7478b-437">校验和</span><span class="sxs-lookup"><span data-stu-id="7478b-437">Checksum</span></span>

<span data-ttu-id="7478b-438">否</span><span class="sxs-lookup"><span data-stu-id="7478b-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7478b-439">定义</span><span class="sxs-lookup"><span data-stu-id="7478b-439">Definition</span></span>

<span data-ttu-id="7478b-440">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7478b-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7478b-441">正则表达式`Regex_ireland_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7478b-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7478b-442">找到了中`Keywords_ireland_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="7478b-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7478b-443">关键字</span><span class="sxs-lookup"><span data-stu-id="7478b-443">Keywords</span></span>

<span data-ttu-id="7478b-444">| |</span><span class="sxs-lookup"><span data-stu-id="7478b-444"></span></span>
|<span data-ttu-id="7478b-445">**Keywords_ireland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="7478b-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7478b-446">dl#</span><span class="sxs-lookup"><span data-stu-id="7478b-446">dl#</span></span>  <br/> <span data-ttu-id="7478b-447">driver license</span><span class="sxs-lookup"><span data-stu-id="7478b-447">driver license</span></span>  <br/> <span data-ttu-id="7478b-448">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-448">driver license number</span></span>  <br/> <span data-ttu-id="7478b-449">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="7478b-449">driver licence</span></span>  <br/> <span data-ttu-id="7478b-450">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="7478b-450">drivers lic.</span></span>  <br/> <span data-ttu-id="7478b-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="7478b-451">drivers license</span></span>  <br/> <span data-ttu-id="7478b-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7478b-452">drivers licence</span></span>  <br/> <span data-ttu-id="7478b-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="7478b-453">driver's license</span></span>  <br/> <span data-ttu-id="7478b-454">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-454">driver's license number</span></span>  <br/> <span data-ttu-id="7478b-455">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-455">driver's licence number</span></span>  <br/> <span data-ttu-id="7478b-456">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-456">driving license number</span></span>  <br/> <span data-ttu-id="7478b-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="7478b-457">dlno#</span></span>  <br/> <span data-ttu-id="7478b-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="7478b-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="7478b-459">意大利</span><span class="sxs-lookup"><span data-stu-id="7478b-459">Italy</span></span>

<span data-ttu-id="7478b-460">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "意大利驾驶执照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="7478b-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="7478b-461">拉脱维亚</span><span class="sxs-lookup"><span data-stu-id="7478b-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="7478b-462">格式</span><span class="sxs-lookup"><span data-stu-id="7478b-462">Format</span></span>

<span data-ttu-id="7478b-463">三个字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="7478b-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7478b-464">模式</span><span class="sxs-lookup"><span data-stu-id="7478b-464">Pattern</span></span>

<span data-ttu-id="7478b-465">三个字母和六个数字:</span><span class="sxs-lookup"><span data-stu-id="7478b-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="7478b-466">三个字母 (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="7478b-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="7478b-467">六个数字</span><span class="sxs-lookup"><span data-stu-id="7478b-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7478b-468">校验和</span><span class="sxs-lookup"><span data-stu-id="7478b-468">Checksum</span></span>

<span data-ttu-id="7478b-469">否</span><span class="sxs-lookup"><span data-stu-id="7478b-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7478b-470">定义</span><span class="sxs-lookup"><span data-stu-id="7478b-470">Definition</span></span>

<span data-ttu-id="7478b-471">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7478b-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7478b-472">正则表达式`Regex_latvia_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7478b-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7478b-473">找到了中`Keywords_latvia_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="7478b-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7478b-474">关键字</span><span class="sxs-lookup"><span data-stu-id="7478b-474">Keywords</span></span>

<span data-ttu-id="7478b-475">| |</span><span class="sxs-lookup"><span data-stu-id="7478b-475"></span></span>
|<span data-ttu-id="7478b-476">**Keywords_latvia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="7478b-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7478b-477">dl#</span><span class="sxs-lookup"><span data-stu-id="7478b-477">dl#</span></span>  <br/> <span data-ttu-id="7478b-478">driver license</span><span class="sxs-lookup"><span data-stu-id="7478b-478">driver license</span></span>  <br/> <span data-ttu-id="7478b-479">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-479">driver license number</span></span>  <br/> <span data-ttu-id="7478b-480">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="7478b-480">driver licence</span></span>  <br/> <span data-ttu-id="7478b-481">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="7478b-481">drivers lic.</span></span>  <br/> <span data-ttu-id="7478b-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="7478b-482">drivers license</span></span>  <br/> <span data-ttu-id="7478b-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7478b-483">drivers licence</span></span>  <br/> <span data-ttu-id="7478b-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="7478b-484">driver's license</span></span>  <br/> <span data-ttu-id="7478b-485">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-485">driver's license number</span></span>  <br/> <span data-ttu-id="7478b-486">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-486">driver's licence number</span></span>  <br/> <span data-ttu-id="7478b-487">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-487">driving license number</span></span>  <br/> <span data-ttu-id="7478b-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="7478b-488">dlno#</span></span>  <br/> <span data-ttu-id="7478b-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="7478b-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="7478b-490">立陶宛</span><span class="sxs-lookup"><span data-stu-id="7478b-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="7478b-491">格式</span><span class="sxs-lookup"><span data-stu-id="7478b-491">Format</span></span>

<span data-ttu-id="7478b-492">8位数, 不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="7478b-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7478b-493">模式</span><span class="sxs-lookup"><span data-stu-id="7478b-493">Pattern</span></span>

 <span data-ttu-id="7478b-494">八个数字</span><span class="sxs-lookup"><span data-stu-id="7478b-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="7478b-495">校验和</span><span class="sxs-lookup"><span data-stu-id="7478b-495">Checksum</span></span>

<span data-ttu-id="7478b-496">否</span><span class="sxs-lookup"><span data-stu-id="7478b-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7478b-497">定义</span><span class="sxs-lookup"><span data-stu-id="7478b-497">Definition</span></span>

<span data-ttu-id="7478b-498">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7478b-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7478b-499">正则表达式`Regex_lithuania_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7478b-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7478b-500">找到了中`Keywords_lithuania_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="7478b-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7478b-501">关键字</span><span class="sxs-lookup"><span data-stu-id="7478b-501">Keywords</span></span>

<span data-ttu-id="7478b-502">| |</span><span class="sxs-lookup"><span data-stu-id="7478b-502"></span></span>
|<span data-ttu-id="7478b-503">**Keywords_lithuania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="7478b-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7478b-504">dl#</span><span class="sxs-lookup"><span data-stu-id="7478b-504">dl#</span></span>  <br/> <span data-ttu-id="7478b-505">driver license</span><span class="sxs-lookup"><span data-stu-id="7478b-505">driver license</span></span>  <br/> <span data-ttu-id="7478b-506">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-506">driver license number</span></span>  <br/> <span data-ttu-id="7478b-507">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="7478b-507">driver licence</span></span>  <br/> <span data-ttu-id="7478b-508">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="7478b-508">drivers lic.</span></span>  <br/> <span data-ttu-id="7478b-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="7478b-509">drivers license</span></span>  <br/> <span data-ttu-id="7478b-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7478b-510">drivers licence</span></span>  <br/> <span data-ttu-id="7478b-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="7478b-511">driver's license</span></span>  <br/> <span data-ttu-id="7478b-512">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-512">driver's license number</span></span>  <br/> <span data-ttu-id="7478b-513">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-513">driver's licence number</span></span>  <br/> <span data-ttu-id="7478b-514">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-514">driving license number</span></span>  <br/> <span data-ttu-id="7478b-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="7478b-515">dlno#</span></span>  <br/> <span data-ttu-id="7478b-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="7478b-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="7478b-517">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="7478b-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="7478b-518">格式</span><span class="sxs-lookup"><span data-stu-id="7478b-518">Format</span></span>

<span data-ttu-id="7478b-519">6位数, 不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="7478b-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7478b-520">模式</span><span class="sxs-lookup"><span data-stu-id="7478b-520">Pattern</span></span>

 <span data-ttu-id="7478b-521">六个数字</span><span class="sxs-lookup"><span data-stu-id="7478b-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="7478b-522">校验和</span><span class="sxs-lookup"><span data-stu-id="7478b-522">Checksum</span></span>

<span data-ttu-id="7478b-523">否</span><span class="sxs-lookup"><span data-stu-id="7478b-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7478b-524">定义</span><span class="sxs-lookup"><span data-stu-id="7478b-524">Definition</span></span>

<span data-ttu-id="7478b-525">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7478b-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7478b-526">正则表达式`Regex_luxemburg_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7478b-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7478b-527">找到了中`Keywords_luxemburg_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="7478b-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7478b-528">关键字</span><span class="sxs-lookup"><span data-stu-id="7478b-528">Keywords</span></span>

<span data-ttu-id="7478b-529">| |</span><span class="sxs-lookup"><span data-stu-id="7478b-529"></span></span>
|<span data-ttu-id="7478b-530">**Keywords_luxemburg_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="7478b-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7478b-531">dl#</span><span class="sxs-lookup"><span data-stu-id="7478b-531">dl#</span></span>  <br/> <span data-ttu-id="7478b-532">driver license</span><span class="sxs-lookup"><span data-stu-id="7478b-532">driver license</span></span>  <br/> <span data-ttu-id="7478b-533">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-533">driver license number</span></span>  <br/> <span data-ttu-id="7478b-534">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="7478b-534">driver licence</span></span>  <br/> <span data-ttu-id="7478b-535">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="7478b-535">drivers lic.</span></span>  <br/> <span data-ttu-id="7478b-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="7478b-536">drivers license</span></span>  <br/> <span data-ttu-id="7478b-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7478b-537">drivers licence</span></span>  <br/> <span data-ttu-id="7478b-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="7478b-538">driver's license</span></span>  <br/> <span data-ttu-id="7478b-539">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-539">driver's license number</span></span>  <br/> <span data-ttu-id="7478b-540">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-540">driver's licence number</span></span>  <br/> <span data-ttu-id="7478b-541">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-541">driving license number</span></span>  <br/> <span data-ttu-id="7478b-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="7478b-542">dlno#</span></span>  <br/> <span data-ttu-id="7478b-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="7478b-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="7478b-544">马耳他</span><span class="sxs-lookup"><span data-stu-id="7478b-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="7478b-545">格式</span><span class="sxs-lookup"><span data-stu-id="7478b-545">Format</span></span>

<span data-ttu-id="7478b-546">两个字符与指定模式中的六个数字的组合</span><span class="sxs-lookup"><span data-stu-id="7478b-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7478b-547">模式</span><span class="sxs-lookup"><span data-stu-id="7478b-547">Pattern</span></span>

<span data-ttu-id="7478b-548">两个字符和六个数字的组合:</span><span class="sxs-lookup"><span data-stu-id="7478b-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="7478b-549">两个字符 (数字或字母, 而不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="7478b-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="7478b-550">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="7478b-550">A space (optional)</span></span>
    
- <span data-ttu-id="7478b-551">三个数字 </span><span class="sxs-lookup"><span data-stu-id="7478b-551">Three digits</span></span>
    
- <span data-ttu-id="7478b-552">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="7478b-552">A space (optional)</span></span>
    
- <span data-ttu-id="7478b-553">三位数字</span><span class="sxs-lookup"><span data-stu-id="7478b-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7478b-554">校验和</span><span class="sxs-lookup"><span data-stu-id="7478b-554">Checksum</span></span>

<span data-ttu-id="7478b-555">否</span><span class="sxs-lookup"><span data-stu-id="7478b-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7478b-556">定义</span><span class="sxs-lookup"><span data-stu-id="7478b-556">Definition</span></span>

<span data-ttu-id="7478b-557">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7478b-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7478b-558">正则表达式`Regex_malta_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7478b-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7478b-559">找到了中`Keywords_malta_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="7478b-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7478b-560">关键字</span><span class="sxs-lookup"><span data-stu-id="7478b-560">Keywords</span></span>

<span data-ttu-id="7478b-561">| |</span><span class="sxs-lookup"><span data-stu-id="7478b-561"></span></span>
|<span data-ttu-id="7478b-562">**Keywords_malta_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="7478b-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7478b-563">dl#</span><span class="sxs-lookup"><span data-stu-id="7478b-563">dl#</span></span>  <br/> <span data-ttu-id="7478b-564">driver license</span><span class="sxs-lookup"><span data-stu-id="7478b-564">driver license</span></span>  <br/> <span data-ttu-id="7478b-565">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-565">driver license number</span></span>  <br/> <span data-ttu-id="7478b-566">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="7478b-566">driver licence</span></span>  <br/> <span data-ttu-id="7478b-567">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="7478b-567">drivers lic.</span></span>  <br/> <span data-ttu-id="7478b-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="7478b-568">drivers license</span></span>  <br/> <span data-ttu-id="7478b-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7478b-569">drivers licence</span></span>  <br/> <span data-ttu-id="7478b-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="7478b-570">driver's license</span></span>  <br/> <span data-ttu-id="7478b-571">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-571">driver's license number</span></span>  <br/> <span data-ttu-id="7478b-572">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-572">driver's licence number</span></span>  <br/> <span data-ttu-id="7478b-573">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-573">driving license number</span></span>  <br/> <span data-ttu-id="7478b-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="7478b-574">dlno#</span></span>  <br/> <span data-ttu-id="7478b-575">liċenzja tas-sewqan</span><span class="sxs-lookup"><span data-stu-id="7478b-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="7478b-576">荷兰</span><span class="sxs-lookup"><span data-stu-id="7478b-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="7478b-577">格式</span><span class="sxs-lookup"><span data-stu-id="7478b-577">Format</span></span>

<span data-ttu-id="7478b-578">10个数字, 不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="7478b-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7478b-579">模式</span><span class="sxs-lookup"><span data-stu-id="7478b-579">Pattern</span></span>

<span data-ttu-id="7478b-580">10 个数字</span><span class="sxs-lookup"><span data-stu-id="7478b-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="7478b-581">校验和</span><span class="sxs-lookup"><span data-stu-id="7478b-581">Checksum</span></span>

<span data-ttu-id="7478b-582">否</span><span class="sxs-lookup"><span data-stu-id="7478b-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7478b-583">定义</span><span class="sxs-lookup"><span data-stu-id="7478b-583">Definition</span></span>

<span data-ttu-id="7478b-584">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7478b-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7478b-585">正则表达式`Regex_netherlands_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7478b-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7478b-586">找到了中`Keywords_netherlands_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="7478b-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7478b-587">关键字</span><span class="sxs-lookup"><span data-stu-id="7478b-587">Keywords</span></span>

<span data-ttu-id="7478b-588">| |</span><span class="sxs-lookup"><span data-stu-id="7478b-588"></span></span>
|<span data-ttu-id="7478b-589">**Keywords_netherlands_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="7478b-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7478b-590">dl#</span><span class="sxs-lookup"><span data-stu-id="7478b-590">dl#</span></span>  <br/> <span data-ttu-id="7478b-591">driver license</span><span class="sxs-lookup"><span data-stu-id="7478b-591">driver license</span></span>  <br/> <span data-ttu-id="7478b-592">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-592">driver license number</span></span>  <br/> <span data-ttu-id="7478b-593">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="7478b-593">driver licence</span></span>  <br/> <span data-ttu-id="7478b-594">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="7478b-594">drivers lic.</span></span>  <br/> <span data-ttu-id="7478b-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="7478b-595">drivers license</span></span>  <br/> <span data-ttu-id="7478b-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7478b-596">drivers licence</span></span>  <br/> <span data-ttu-id="7478b-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="7478b-597">driver's license</span></span>  <br/> <span data-ttu-id="7478b-598">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-598">driver's license number</span></span>  <br/> <span data-ttu-id="7478b-599">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-599">driver's licence number</span></span>  <br/> <span data-ttu-id="7478b-600">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-600">driving license number</span></span>  <br/> <span data-ttu-id="7478b-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="7478b-601">dlno#</span></span>  <br/> <span data-ttu-id="7478b-602">
permis de conduire</span><span class="sxs-lookup"><span data-stu-id="7478b-602">permis de conduire</span></span>  <br/> <span data-ttu-id="7478b-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="7478b-603">rijbewijs</span></span>  <br/> <span data-ttu-id="7478b-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="7478b-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="7478b-605">波兰</span><span class="sxs-lookup"><span data-stu-id="7478b-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="7478b-606">格式</span><span class="sxs-lookup"><span data-stu-id="7478b-606">Format</span></span>

<span data-ttu-id="7478b-607">14位数, 包含2个正斜杠</span><span class="sxs-lookup"><span data-stu-id="7478b-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7478b-608">模式</span><span class="sxs-lookup"><span data-stu-id="7478b-608">Pattern</span></span>

<span data-ttu-id="7478b-609">14位数和2正斜杠:</span><span class="sxs-lookup"><span data-stu-id="7478b-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="7478b-610">五位数字</span><span class="sxs-lookup"><span data-stu-id="7478b-610">Five digits</span></span> 
    
- <span data-ttu-id="7478b-611">一个正斜杠 </span><span class="sxs-lookup"><span data-stu-id="7478b-611">A forward slash</span></span>
    
- <span data-ttu-id="7478b-612">两位数字</span><span class="sxs-lookup"><span data-stu-id="7478b-612">Two digits</span></span>
    
- <span data-ttu-id="7478b-613">一个正斜杠 </span><span class="sxs-lookup"><span data-stu-id="7478b-613">A forward slash</span></span>
    
- <span data-ttu-id="7478b-614">七个数字</span><span class="sxs-lookup"><span data-stu-id="7478b-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7478b-615">校验和</span><span class="sxs-lookup"><span data-stu-id="7478b-615">Checksum</span></span>

<span data-ttu-id="7478b-616">否</span><span class="sxs-lookup"><span data-stu-id="7478b-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7478b-617">定义</span><span class="sxs-lookup"><span data-stu-id="7478b-617">Definition</span></span>

<span data-ttu-id="7478b-618">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7478b-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7478b-619">正则表达式`Regex_poland_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7478b-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7478b-620">找到了中`Keywords_poland_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="7478b-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7478b-621">关键字</span><span class="sxs-lookup"><span data-stu-id="7478b-621">Keywords</span></span>

<span data-ttu-id="7478b-622">| |</span><span class="sxs-lookup"><span data-stu-id="7478b-622"></span></span>
|<span data-ttu-id="7478b-623">**Keywords_poland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="7478b-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7478b-624">dl#</span><span class="sxs-lookup"><span data-stu-id="7478b-624">dl#</span></span>  <br/> <span data-ttu-id="7478b-625">driver license</span><span class="sxs-lookup"><span data-stu-id="7478b-625">driver license</span></span>  <br/> <span data-ttu-id="7478b-626">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-626">driver license number</span></span>  <br/> <span data-ttu-id="7478b-627">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="7478b-627">driver licence</span></span>  <br/> <span data-ttu-id="7478b-628">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="7478b-628">drivers lic.</span></span>  <br/> <span data-ttu-id="7478b-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="7478b-629">drivers license</span></span>  <br/> <span data-ttu-id="7478b-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7478b-630">drivers licence</span></span>  <br/> <span data-ttu-id="7478b-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="7478b-631">driver's license</span></span>  <br/> <span data-ttu-id="7478b-632">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-632">driver's license number</span></span>  <br/> <span data-ttu-id="7478b-633">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-633">driver's licence number</span></span>  <br/> <span data-ttu-id="7478b-634">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-634">driving license number</span></span>  <br/> <span data-ttu-id="7478b-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="7478b-635">dlno#</span></span>  <br/> <span data-ttu-id="7478b-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="7478b-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="7478b-637">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="7478b-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="7478b-638">格式</span><span class="sxs-lookup"><span data-stu-id="7478b-638">Format</span></span>

<span data-ttu-id="7478b-639">两个字母后跟指定模式中的七个数字</span><span class="sxs-lookup"><span data-stu-id="7478b-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7478b-640">模式</span><span class="sxs-lookup"><span data-stu-id="7478b-640">Pattern</span></span>

<span data-ttu-id="7478b-641">两个字母后跟七个包含特殊字符的数字:</span><span class="sxs-lookup"><span data-stu-id="7478b-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="7478b-642">两个字母 (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="7478b-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="7478b-643">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="7478b-643">A hyphen</span></span>
    
- <span data-ttu-id="7478b-644">六位数字</span><span class="sxs-lookup"><span data-stu-id="7478b-644">Six digits</span></span>
    
- <span data-ttu-id="7478b-645">一个空格</span><span class="sxs-lookup"><span data-stu-id="7478b-645">A space</span></span>
    
- <span data-ttu-id="7478b-646">一个数字</span><span class="sxs-lookup"><span data-stu-id="7478b-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7478b-647">校验和</span><span class="sxs-lookup"><span data-stu-id="7478b-647">Checksum</span></span>

<span data-ttu-id="7478b-648">否</span><span class="sxs-lookup"><span data-stu-id="7478b-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7478b-649">定义</span><span class="sxs-lookup"><span data-stu-id="7478b-649">Definition</span></span>

<span data-ttu-id="7478b-650">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7478b-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7478b-651">正则表达式`Regex_portugal_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7478b-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7478b-652">找到了中`Keywords_portugal_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="7478b-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7478b-653">关键字</span><span class="sxs-lookup"><span data-stu-id="7478b-653">Keywords</span></span>

<span data-ttu-id="7478b-654">| |</span><span class="sxs-lookup"><span data-stu-id="7478b-654"></span></span>
|<span data-ttu-id="7478b-655">**Keywords_portugal_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="7478b-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7478b-656">dl#</span><span class="sxs-lookup"><span data-stu-id="7478b-656">dl#</span></span>  <br/> <span data-ttu-id="7478b-657">driver license</span><span class="sxs-lookup"><span data-stu-id="7478b-657">driver license</span></span>  <br/> <span data-ttu-id="7478b-658">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-658">driver license number</span></span>  <br/> <span data-ttu-id="7478b-659">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="7478b-659">driver licence</span></span>  <br/> <span data-ttu-id="7478b-660">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="7478b-660">drivers lic.</span></span>  <br/> <span data-ttu-id="7478b-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="7478b-661">drivers license</span></span>  <br/> <span data-ttu-id="7478b-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7478b-662">drivers licence</span></span>  <br/> <span data-ttu-id="7478b-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="7478b-663">driver's license</span></span>  <br/> <span data-ttu-id="7478b-664">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-664">driver's license number</span></span>  <br/> <span data-ttu-id="7478b-665">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-665">driver's licence number</span></span>  <br/> <span data-ttu-id="7478b-666">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-666">driving license number</span></span>  <br/> <span data-ttu-id="7478b-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="7478b-667">dlno#</span></span>  <br/> <span data-ttu-id="7478b-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="7478b-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="7478b-669">罗马尼亚</span><span class="sxs-lookup"><span data-stu-id="7478b-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="7478b-670">格式</span><span class="sxs-lookup"><span data-stu-id="7478b-670">Format</span></span>

<span data-ttu-id="7478b-671">一个字符后跟八个数字</span><span class="sxs-lookup"><span data-stu-id="7478b-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7478b-672">模式</span><span class="sxs-lookup"><span data-stu-id="7478b-672">Pattern</span></span>

<span data-ttu-id="7478b-673">一个字符后跟八个数字:</span><span class="sxs-lookup"><span data-stu-id="7478b-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="7478b-674">一个字母 (不区分大小写) 或数字</span><span class="sxs-lookup"><span data-stu-id="7478b-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="7478b-675">八个数字</span><span class="sxs-lookup"><span data-stu-id="7478b-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7478b-676">校验和</span><span class="sxs-lookup"><span data-stu-id="7478b-676">Checksum</span></span>

<span data-ttu-id="7478b-677">否</span><span class="sxs-lookup"><span data-stu-id="7478b-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7478b-678">定义</span><span class="sxs-lookup"><span data-stu-id="7478b-678">Definition</span></span>

<span data-ttu-id="7478b-679">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7478b-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7478b-680">正则表达式`Regex_romania_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7478b-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7478b-681">找到了中`Keywords_romania_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="7478b-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7478b-682">关键字</span><span class="sxs-lookup"><span data-stu-id="7478b-682">Keywords</span></span>

<span data-ttu-id="7478b-683">| |</span><span class="sxs-lookup"><span data-stu-id="7478b-683"></span></span>
|<span data-ttu-id="7478b-684">**Keywords_romania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="7478b-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7478b-685">dl#</span><span class="sxs-lookup"><span data-stu-id="7478b-685">dl#</span></span>  <br/> <span data-ttu-id="7478b-686">driver license</span><span class="sxs-lookup"><span data-stu-id="7478b-686">driver license</span></span>  <br/> <span data-ttu-id="7478b-687">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-687">driver license number</span></span>  <br/> <span data-ttu-id="7478b-688">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="7478b-688">driver licence</span></span>  <br/> <span data-ttu-id="7478b-689">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="7478b-689">drivers lic.</span></span>  <br/> <span data-ttu-id="7478b-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="7478b-690">drivers license</span></span>  <br/> <span data-ttu-id="7478b-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7478b-691">drivers licence</span></span>  <br/> <span data-ttu-id="7478b-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="7478b-692">driver's license</span></span>  <br/> <span data-ttu-id="7478b-693">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-693">driver's license number</span></span>  <br/> <span data-ttu-id="7478b-694">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-694">driver's licence number</span></span>  <br/> <span data-ttu-id="7478b-695">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-695">driving license number</span></span>  <br/> <span data-ttu-id="7478b-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="7478b-696">dlno#</span></span>  <br/> <span data-ttu-id="7478b-697">permis de conducere</span><span class="sxs-lookup"><span data-stu-id="7478b-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="7478b-698">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="7478b-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="7478b-699">格式</span><span class="sxs-lookup"><span data-stu-id="7478b-699">Format</span></span>

<span data-ttu-id="7478b-700">一个字符后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="7478b-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7478b-701">模式</span><span class="sxs-lookup"><span data-stu-id="7478b-701">Pattern</span></span>

<span data-ttu-id="7478b-702">一个字符后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="7478b-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="7478b-703">一个字母 (不区分大小写) 或数字</span><span class="sxs-lookup"><span data-stu-id="7478b-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="7478b-704">七个数字</span><span class="sxs-lookup"><span data-stu-id="7478b-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="7478b-705">校验和</span><span class="sxs-lookup"><span data-stu-id="7478b-705">Checksum</span></span>

<span data-ttu-id="7478b-706">否</span><span class="sxs-lookup"><span data-stu-id="7478b-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7478b-707">定义</span><span class="sxs-lookup"><span data-stu-id="7478b-707">Definition</span></span>

<span data-ttu-id="7478b-708">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7478b-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7478b-709">正则表达式`Regex_slovakia_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7478b-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7478b-710">找到了中`Keywords_slovakia_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="7478b-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7478b-711">关键字</span><span class="sxs-lookup"><span data-stu-id="7478b-711">Keywords</span></span>

<span data-ttu-id="7478b-712">| |</span><span class="sxs-lookup"><span data-stu-id="7478b-712"></span></span>
|<span data-ttu-id="7478b-713">**Keywords_slovakia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="7478b-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7478b-714">dl#</span><span class="sxs-lookup"><span data-stu-id="7478b-714">dl#</span></span>  <br/> <span data-ttu-id="7478b-715">driver license</span><span class="sxs-lookup"><span data-stu-id="7478b-715">driver license</span></span>  <br/> <span data-ttu-id="7478b-716">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-716">driver license number</span></span>  <br/> <span data-ttu-id="7478b-717">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="7478b-717">driver licence</span></span>  <br/> <span data-ttu-id="7478b-718">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="7478b-718">drivers lic.</span></span>  <br/> <span data-ttu-id="7478b-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="7478b-719">drivers license</span></span>  <br/> <span data-ttu-id="7478b-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7478b-720">drivers licence</span></span>  <br/> <span data-ttu-id="7478b-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="7478b-721">driver's license</span></span>  <br/> <span data-ttu-id="7478b-722">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-722">driver's license number</span></span>  <br/> <span data-ttu-id="7478b-723">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-723">driver's licence number</span></span>  <br/> <span data-ttu-id="7478b-724">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-724">driving license number</span></span>  <br/> <span data-ttu-id="7478b-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="7478b-725">dlno#</span></span>  <br/> <span data-ttu-id="7478b-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="7478b-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="7478b-727">斯诺文尼亚</span><span class="sxs-lookup"><span data-stu-id="7478b-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="7478b-728">格式</span><span class="sxs-lookup"><span data-stu-id="7478b-728">Format</span></span>

<span data-ttu-id="7478b-729">9个数字, 不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="7478b-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7478b-730">模式</span><span class="sxs-lookup"><span data-stu-id="7478b-730">Pattern</span></span>

<span data-ttu-id="7478b-731">九个数字</span><span class="sxs-lookup"><span data-stu-id="7478b-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="7478b-732">校验和</span><span class="sxs-lookup"><span data-stu-id="7478b-732">Checksum</span></span>

<span data-ttu-id="7478b-733">否</span><span class="sxs-lookup"><span data-stu-id="7478b-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7478b-734">定义</span><span class="sxs-lookup"><span data-stu-id="7478b-734">Definition</span></span>

<span data-ttu-id="7478b-735">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7478b-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7478b-736">正则表达式`Regex_slovenia_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7478b-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7478b-737">找到了中`Keywords_slovenia_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="7478b-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7478b-738">关键字</span><span class="sxs-lookup"><span data-stu-id="7478b-738">Keywords</span></span>

<span data-ttu-id="7478b-739">| |</span><span class="sxs-lookup"><span data-stu-id="7478b-739"></span></span>
|<span data-ttu-id="7478b-740">**Keywords_slovenia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="7478b-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7478b-741">dl#</span><span class="sxs-lookup"><span data-stu-id="7478b-741">dl#</span></span>  <br/> <span data-ttu-id="7478b-742">driver license</span><span class="sxs-lookup"><span data-stu-id="7478b-742">driver license</span></span>  <br/> <span data-ttu-id="7478b-743">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-743">driver license number</span></span>  <br/> <span data-ttu-id="7478b-744">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="7478b-744">driver licence</span></span>  <br/> <span data-ttu-id="7478b-745">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="7478b-745">drivers lic.</span></span>  <br/> <span data-ttu-id="7478b-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="7478b-746">drivers license</span></span>  <br/> <span data-ttu-id="7478b-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7478b-747">drivers licence</span></span>  <br/> <span data-ttu-id="7478b-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="7478b-748">driver's license</span></span>  <br/> <span data-ttu-id="7478b-749">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-749">driver's license number</span></span>  <br/> <span data-ttu-id="7478b-750">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-750">driver's licence number</span></span>  <br/> <span data-ttu-id="7478b-751">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-751">driving license number</span></span>  <br/> <span data-ttu-id="7478b-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="7478b-752">dlno#</span></span>  <br/> <span data-ttu-id="7478b-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="7478b-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="7478b-754">西班牙</span><span class="sxs-lookup"><span data-stu-id="7478b-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="7478b-755">格式</span><span class="sxs-lookup"><span data-stu-id="7478b-755">Format</span></span>

<span data-ttu-id="7478b-756">8位数, 后跟一个字符</span><span class="sxs-lookup"><span data-stu-id="7478b-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7478b-757">模式</span><span class="sxs-lookup"><span data-stu-id="7478b-757">Pattern</span></span>

<span data-ttu-id="7478b-758">8位数, 后跟一个字符:</span><span class="sxs-lookup"><span data-stu-id="7478b-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="7478b-759">八个数字</span><span class="sxs-lookup"><span data-stu-id="7478b-759">Eight digits</span></span> 
    
- <span data-ttu-id="7478b-760">一个数字或字母 (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="7478b-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7478b-761">校验和</span><span class="sxs-lookup"><span data-stu-id="7478b-761">Checksum</span></span>

<span data-ttu-id="7478b-762">是</span><span class="sxs-lookup"><span data-stu-id="7478b-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7478b-763">定义</span><span class="sxs-lookup"><span data-stu-id="7478b-763">Definition</span></span>

<span data-ttu-id="7478b-764">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7478b-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7478b-765">函数`Func_spain_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7478b-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7478b-766">找到了中`Keywords_spain_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="7478b-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7478b-767">关键字</span><span class="sxs-lookup"><span data-stu-id="7478b-767">Keywords</span></span>

<span data-ttu-id="7478b-768">| |</span><span class="sxs-lookup"><span data-stu-id="7478b-768"></span></span>
|<span data-ttu-id="7478b-769">**Keywords_spain_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="7478b-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7478b-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="7478b-770">dlno#</span></span>  <br/> <span data-ttu-id="7478b-771">dl#</span><span class="sxs-lookup"><span data-stu-id="7478b-771">dl#</span></span>  <br/> <span data-ttu-id="7478b-772">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="7478b-772">drivers lic.</span></span>  <br/> <span data-ttu-id="7478b-773">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="7478b-773">driver licence</span></span>  <br/> <span data-ttu-id="7478b-774">driver license</span><span class="sxs-lookup"><span data-stu-id="7478b-774">driver license</span></span>  <br/> <span data-ttu-id="7478b-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7478b-775">drivers licence</span></span>  <br/> <span data-ttu-id="7478b-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="7478b-776">drivers license</span></span>  <br/> <span data-ttu-id="7478b-777">驾驶许可证</span><span class="sxs-lookup"><span data-stu-id="7478b-777">driver's licence</span></span>  <br/> <span data-ttu-id="7478b-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="7478b-778">driver's license</span></span>  <br/> <span data-ttu-id="7478b-779">driving licence
</span><span class="sxs-lookup"><span data-stu-id="7478b-779">driving licence</span></span>  <br/> <span data-ttu-id="7478b-780">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="7478b-780">driving license</span></span>  <br/> <span data-ttu-id="7478b-781">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-781">driver licence number</span></span>  <br/> <span data-ttu-id="7478b-782">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-782">driver license number</span></span>  <br/> <span data-ttu-id="7478b-783">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-783">drivers licence number</span></span>  <br/> <span data-ttu-id="7478b-784">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-784">drivers license number</span></span>  <br/> <span data-ttu-id="7478b-785">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-785">driver's licence number</span></span>  <br/> <span data-ttu-id="7478b-786">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-786">driver's license number</span></span>  <br/> <span data-ttu-id="7478b-787">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-787">driving licence number</span></span>  <br/> <span data-ttu-id="7478b-788">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-788">driving license number</span></span>  <br/> <span data-ttu-id="7478b-789">促进允许</span><span class="sxs-lookup"><span data-stu-id="7478b-789">driving permit</span></span>  <br/> <span data-ttu-id="7478b-790">驾驶允许号码</span><span class="sxs-lookup"><span data-stu-id="7478b-790">driving permit number</span></span>  <br/> <span data-ttu-id="7478b-791">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="7478b-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="7478b-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="7478b-792">permiso conducción</span></span>  <br/> <span data-ttu-id="7478b-793">número licencia conducir</span><span class="sxs-lookup"><span data-stu-id="7478b-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="7478b-794">número de carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="7478b-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="7478b-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="7478b-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="7478b-796">licencia conducir</span><span class="sxs-lookup"><span data-stu-id="7478b-796">licencia conducir</span></span>  <br/> <span data-ttu-id="7478b-797">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="7478b-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="7478b-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="7478b-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="7478b-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="7478b-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="7478b-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="7478b-800">permiso conducir</span></span>  <br/> <span data-ttu-id="7478b-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="7478b-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="7478b-802">el carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="7478b-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="7478b-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="7478b-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="7478b-804">瑞典</span><span class="sxs-lookup"><span data-stu-id="7478b-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="7478b-805">格式</span><span class="sxs-lookup"><span data-stu-id="7478b-805">Format</span></span>

<span data-ttu-id="7478b-806">10个数字, 包含连字符</span><span class="sxs-lookup"><span data-stu-id="7478b-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7478b-807">模式</span><span class="sxs-lookup"><span data-stu-id="7478b-807">Pattern</span></span>

<span data-ttu-id="7478b-808">10位数, 包含连字符:</span><span class="sxs-lookup"><span data-stu-id="7478b-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="7478b-809">六位数字</span><span class="sxs-lookup"><span data-stu-id="7478b-809">Six digits</span></span> 
    
- <span data-ttu-id="7478b-810">连字符</span><span class="sxs-lookup"><span data-stu-id="7478b-810">A hyphen</span></span>
    
- <span data-ttu-id="7478b-811">四位数字</span><span class="sxs-lookup"><span data-stu-id="7478b-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7478b-812">校验和</span><span class="sxs-lookup"><span data-stu-id="7478b-812">Checksum</span></span>

<span data-ttu-id="7478b-813">否</span><span class="sxs-lookup"><span data-stu-id="7478b-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7478b-814">定义</span><span class="sxs-lookup"><span data-stu-id="7478b-814">Definition</span></span>

<span data-ttu-id="7478b-815">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7478b-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7478b-816">正则表达式`Regex_sweden_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7478b-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7478b-817">找到了中`Keywords_sweden_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="7478b-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="7478b-818">关键字</span><span class="sxs-lookup"><span data-stu-id="7478b-818">Keywords</span></span>

<span data-ttu-id="7478b-819">| |</span><span class="sxs-lookup"><span data-stu-id="7478b-819"></span></span>
|<span data-ttu-id="7478b-820">**Keywords_sweden_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="7478b-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7478b-821">dl#</span><span class="sxs-lookup"><span data-stu-id="7478b-821">dl#</span></span>  <br/> <span data-ttu-id="7478b-822">driver license</span><span class="sxs-lookup"><span data-stu-id="7478b-822">driver license</span></span>  <br/> <span data-ttu-id="7478b-823">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-823">driver license number</span></span>  <br/> <span data-ttu-id="7478b-824">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="7478b-824">driver licence</span></span>  <br/> <span data-ttu-id="7478b-825">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="7478b-825">drivers lic.</span></span>  <br/> <span data-ttu-id="7478b-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="7478b-826">drivers license</span></span>  <br/> <span data-ttu-id="7478b-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7478b-827">drivers licence</span></span>  <br/> <span data-ttu-id="7478b-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="7478b-828">driver's license</span></span>  <br/> <span data-ttu-id="7478b-829">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-829">driver's license number</span></span>  <br/> <span data-ttu-id="7478b-830">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="7478b-830">driver's licence number</span></span>  <br/> <span data-ttu-id="7478b-831">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="7478b-831">driving license number</span></span>  <br/> <span data-ttu-id="7478b-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="7478b-832">dlno#</span></span>  <br/> <span data-ttu-id="7478b-833">körkort</span><span class="sxs-lookup"><span data-stu-id="7478b-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="7478b-834">英国</span><span class="sxs-lookup"><span data-stu-id="7478b-834">UK</span></span>

<span data-ttu-id="7478b-p103">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)部分的 "英国驾 License 号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="7478b-p103">For details, see the section "U.K. Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7478b-837">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7478b-837">See also</span></span>

[<span data-ttu-id="7478b-838">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="7478b-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

