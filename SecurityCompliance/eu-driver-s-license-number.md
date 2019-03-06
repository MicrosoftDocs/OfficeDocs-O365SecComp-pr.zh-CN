---
title: 欧盟驾驶执照号码
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主题介绍当数据丢失防护 (DLP) 策略检测到欧盟驱动程序的敏感信息类型时, 应查找什么内容。 此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。
ms.openlocfilehash: be9497c325866a670dff8d82b5170f4ca947c4ad
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410747"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="3c15a-104">欧盟驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-104">EU Driver's License Number</span></span>

<span data-ttu-id="3c15a-105">本主题介绍当数据丢失防护 (DLP) 策略检测到欧盟驱动程序的敏感信息类型时, 应查找什么内容。</span><span class="sxs-lookup"><span data-stu-id="3c15a-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="3c15a-106">此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。</span><span class="sxs-lookup"><span data-stu-id="3c15a-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="3c15a-107">奥地利</span><span class="sxs-lookup"><span data-stu-id="3c15a-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="3c15a-108">格式</span><span class="sxs-lookup"><span data-stu-id="3c15a-108">Format</span></span>

<span data-ttu-id="3c15a-109">8位数, 不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="3c15a-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c15a-110">模式</span><span class="sxs-lookup"><span data-stu-id="3c15a-110">Pattern</span></span>

<span data-ttu-id="3c15a-111">八个数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3c15a-112">校验和</span><span class="sxs-lookup"><span data-stu-id="3c15a-112">Checksum</span></span>

<span data-ttu-id="3c15a-113">否</span><span class="sxs-lookup"><span data-stu-id="3c15a-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c15a-114">定义</span><span class="sxs-lookup"><span data-stu-id="3c15a-114">Definition</span></span>

<span data-ttu-id="3c15a-115">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c15a-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c15a-116">正则表达式`Regex_austria_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c15a-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c15a-117">找到了中`Keywords_austria_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c15a-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="3c15a-118">关键字</span><span class="sxs-lookup"><span data-stu-id="3c15a-118">Keywords</span></span>

<span data-ttu-id="3c15a-119">| |</span><span class="sxs-lookup"><span data-stu-id="3c15a-119"></span></span>
|<span data-ttu-id="3c15a-120">**Keywords_austria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3c15a-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3c15a-121">通讯</span><span class="sxs-lookup"><span data-stu-id="3c15a-121">dl#</span></span>  <br/> <span data-ttu-id="3c15a-122">driver license</span><span class="sxs-lookup"><span data-stu-id="3c15a-122">driver license</span></span>  <br/> <span data-ttu-id="3c15a-123">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-123">driver license number</span></span>  <br/> <span data-ttu-id="3c15a-124">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="3c15a-124">driver licence</span></span>  <br/> <span data-ttu-id="3c15a-125">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="3c15a-125">drivers lic.</span></span>  <br/> <span data-ttu-id="3c15a-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="3c15a-126">drivers license</span></span>  <br/> <span data-ttu-id="3c15a-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="3c15a-127">driver's licence</span></span>  <br/> <span data-ttu-id="3c15a-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="3c15a-128">driver's license</span></span>  <br/> <span data-ttu-id="3c15a-129">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-129">driver's license number</span></span>  <br/> <span data-ttu-id="3c15a-130">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="3c15a-131">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-131">driving license number</span></span>  <br/> <span data-ttu-id="3c15a-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="3c15a-132">dlno#</span></span>  <br/> <span data-ttu-id="3c15a-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="3c15a-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="3c15a-134">fuhrerschein republik osterreich</span><span class="sxs-lookup"><span data-stu-id="3c15a-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="3c15a-135">比利时</span><span class="sxs-lookup"><span data-stu-id="3c15a-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="3c15a-136">格式</span><span class="sxs-lookup"><span data-stu-id="3c15a-136">Format</span></span>

<span data-ttu-id="3c15a-137">10个数字, 不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="3c15a-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c15a-138">模式</span><span class="sxs-lookup"><span data-stu-id="3c15a-138">Pattern</span></span>

<span data-ttu-id="3c15a-139">10 个数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3c15a-140">校验和</span><span class="sxs-lookup"><span data-stu-id="3c15a-140">Checksum</span></span>

<span data-ttu-id="3c15a-141">否</span><span class="sxs-lookup"><span data-stu-id="3c15a-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c15a-142">定义</span><span class="sxs-lookup"><span data-stu-id="3c15a-142">Definition</span></span>

<span data-ttu-id="3c15a-143">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c15a-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c15a-144">正则表达式`Regex_belgium_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c15a-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c15a-145">找到了中`Keywords_belgium_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c15a-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="3c15a-146">关键字</span><span class="sxs-lookup"><span data-stu-id="3c15a-146">Keywords</span></span>

<span data-ttu-id="3c15a-147">| |</span><span class="sxs-lookup"><span data-stu-id="3c15a-147"></span></span>
|<span data-ttu-id="3c15a-148">**Keywords__belgium_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3c15a-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3c15a-149">通讯</span><span class="sxs-lookup"><span data-stu-id="3c15a-149">dl#</span></span>  <br/> <span data-ttu-id="3c15a-150">driver license</span><span class="sxs-lookup"><span data-stu-id="3c15a-150">driver license</span></span>  <br/> <span data-ttu-id="3c15a-151">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-151">driver license number</span></span>  <br/> <span data-ttu-id="3c15a-152">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="3c15a-152">driver licence</span></span>  <br/> <span data-ttu-id="3c15a-153">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="3c15a-153">drivers lic.</span></span>  <br/> <span data-ttu-id="3c15a-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="3c15a-154">drivers license</span></span>  <br/> <span data-ttu-id="3c15a-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3c15a-155">drivers licence</span></span>  <br/> <span data-ttu-id="3c15a-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="3c15a-156">driver's license</span></span>  <br/> <span data-ttu-id="3c15a-157">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-157">driver's license number</span></span>  <br/> <span data-ttu-id="3c15a-158">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-158">driver's licence number</span></span>  <br/> <span data-ttu-id="3c15a-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="3c15a-159">dlno#</span></span>  <br/> <span data-ttu-id="3c15a-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="3c15a-160">rijbewijs</span></span>  <br/> <span data-ttu-id="3c15a-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="3c15a-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="3c15a-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="3c15a-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="3c15a-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="3c15a-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="3c15a-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="3c15a-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="3c15a-165">führerschein-nr-nr</span><span class="sxs-lookup"><span data-stu-id="3c15a-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="3c15a-166">fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="3c15a-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="3c15a-167">fuehrerschein-nr</span><span class="sxs-lookup"><span data-stu-id="3c15a-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="3c15a-168">保加利亚语</span><span class="sxs-lookup"><span data-stu-id="3c15a-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="3c15a-169">格式</span><span class="sxs-lookup"><span data-stu-id="3c15a-169">Format</span></span>

<span data-ttu-id="3c15a-170">9个数字, 不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="3c15a-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c15a-171">模式</span><span class="sxs-lookup"><span data-stu-id="3c15a-171">Pattern</span></span>

<span data-ttu-id="3c15a-172">九个数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3c15a-173">校验和</span><span class="sxs-lookup"><span data-stu-id="3c15a-173">Checksum</span></span>

<span data-ttu-id="3c15a-174">否</span><span class="sxs-lookup"><span data-stu-id="3c15a-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c15a-175">定义</span><span class="sxs-lookup"><span data-stu-id="3c15a-175">Definition</span></span>

<span data-ttu-id="3c15a-176">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c15a-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c15a-177">正则表达式`Regex_bulgaria_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c15a-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c15a-178">找到了中`Keywords_bulgaria_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c15a-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="3c15a-179">关键字</span><span class="sxs-lookup"><span data-stu-id="3c15a-179">Keywords</span></span>

<span data-ttu-id="3c15a-180">| |</span><span class="sxs-lookup"><span data-stu-id="3c15a-180"></span></span>
|<span data-ttu-id="3c15a-181">**Keywords_bulgaria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3c15a-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3c15a-182">通讯</span><span class="sxs-lookup"><span data-stu-id="3c15a-182">dl#</span></span>  <br/> <span data-ttu-id="3c15a-183">driver license</span><span class="sxs-lookup"><span data-stu-id="3c15a-183">driver license</span></span>  <br/> <span data-ttu-id="3c15a-184">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-184">driver license number</span></span>  <br/> <span data-ttu-id="3c15a-185">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="3c15a-185">driver licence</span></span>  <br/> <span data-ttu-id="3c15a-186">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="3c15a-186">drivers lic.</span></span>  <br/> <span data-ttu-id="3c15a-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="3c15a-187">drivers license</span></span>  <br/> <span data-ttu-id="3c15a-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3c15a-188">drivers licence</span></span>  <br/> <span data-ttu-id="3c15a-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="3c15a-189">driver's license</span></span>  <br/> <span data-ttu-id="3c15a-190">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-190">driver's license number</span></span>  <br/> <span data-ttu-id="3c15a-191">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-191">driver's licence number</span></span>  <br/> <span data-ttu-id="3c15a-192">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-192">driving license number</span></span>  <br/> <span data-ttu-id="3c15a-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="3c15a-193">dlno#</span></span>  <br/> <span data-ttu-id="3c15a-194">свидетелствозауправлениенампс</span><span class="sxs-lookup"><span data-stu-id="3c15a-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="3c15a-195">свидетелствозауправлениенамоторнопревозносредство</span><span class="sxs-lookup"><span data-stu-id="3c15a-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="3c15a-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="3c15a-196">сумпс</span></span>  <br/> <span data-ttu-id="3c15a-197">шофьорскакнижка</span><span class="sxs-lookup"><span data-stu-id="3c15a-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="3c15a-198">克罗地亚</span><span class="sxs-lookup"><span data-stu-id="3c15a-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="3c15a-199">格式</span><span class="sxs-lookup"><span data-stu-id="3c15a-199">Format</span></span>

<span data-ttu-id="3c15a-200">8位数, 不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="3c15a-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c15a-201">模式</span><span class="sxs-lookup"><span data-stu-id="3c15a-201">Pattern</span></span>

<span data-ttu-id="3c15a-202">八个数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3c15a-203">校验和</span><span class="sxs-lookup"><span data-stu-id="3c15a-203">Checksum</span></span>

<span data-ttu-id="3c15a-204">否</span><span class="sxs-lookup"><span data-stu-id="3c15a-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c15a-205">定义</span><span class="sxs-lookup"><span data-stu-id="3c15a-205">Definition</span></span>

<span data-ttu-id="3c15a-206">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c15a-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c15a-207">正则表达式`Regex_croatia_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c15a-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c15a-208">找到了中`Keywords_croatia_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c15a-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="3c15a-209">关键字</span><span class="sxs-lookup"><span data-stu-id="3c15a-209">Keywords</span></span>

<span data-ttu-id="3c15a-210">| |</span><span class="sxs-lookup"><span data-stu-id="3c15a-210"></span></span>
|<span data-ttu-id="3c15a-211">**Keywords_croatia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3c15a-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3c15a-212">通讯</span><span class="sxs-lookup"><span data-stu-id="3c15a-212">dl#</span></span>  <br/> <span data-ttu-id="3c15a-213">driver license</span><span class="sxs-lookup"><span data-stu-id="3c15a-213">driver license</span></span>  <br/> <span data-ttu-id="3c15a-214">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-214">driver license number</span></span>  <br/> <span data-ttu-id="3c15a-215">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="3c15a-215">driver licence</span></span>  <br/> <span data-ttu-id="3c15a-216">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="3c15a-216">drivers lic.</span></span>  <br/> <span data-ttu-id="3c15a-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="3c15a-217">drivers license</span></span>  <br/> <span data-ttu-id="3c15a-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3c15a-218">drivers licence</span></span>  <br/> <span data-ttu-id="3c15a-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="3c15a-219">driver's license</span></span>  <br/> <span data-ttu-id="3c15a-220">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-220">driver's license number</span></span>  <br/> <span data-ttu-id="3c15a-221">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-221">driver's licence number</span></span>  <br/> <span data-ttu-id="3c15a-222">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-222">driving license number</span></span>  <br/> <span data-ttu-id="3c15a-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="3c15a-223">dlno#</span></span>  <br/> <span data-ttu-id="3c15a-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="3c15a-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="3c15a-225">塞浦路斯</span><span class="sxs-lookup"><span data-stu-id="3c15a-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="3c15a-226">格式</span><span class="sxs-lookup"><span data-stu-id="3c15a-226">Format</span></span>

<span data-ttu-id="3c15a-227">12个数字, 不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="3c15a-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c15a-228">模式</span><span class="sxs-lookup"><span data-stu-id="3c15a-228">Pattern</span></span>

<span data-ttu-id="3c15a-229">12 个数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3c15a-230">校验和</span><span class="sxs-lookup"><span data-stu-id="3c15a-230">Checksum</span></span>

<span data-ttu-id="3c15a-231">否</span><span class="sxs-lookup"><span data-stu-id="3c15a-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c15a-232">定义</span><span class="sxs-lookup"><span data-stu-id="3c15a-232">Definition</span></span>

<span data-ttu-id="3c15a-233">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c15a-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c15a-234">正则表达式`Regex_cyprus_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c15a-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c15a-235">找到了中`Keywords_cyprus_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c15a-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c15a-236">关键字</span><span class="sxs-lookup"><span data-stu-id="3c15a-236">Keywords</span></span>

<span data-ttu-id="3c15a-237">| |</span><span class="sxs-lookup"><span data-stu-id="3c15a-237"></span></span>
|<span data-ttu-id="3c15a-238">**Keywords_cyprus_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3c15a-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3c15a-239">通讯</span><span class="sxs-lookup"><span data-stu-id="3c15a-239">dl#</span></span>  <br/> <span data-ttu-id="3c15a-240">driver license</span><span class="sxs-lookup"><span data-stu-id="3c15a-240">driver license</span></span>  <br/> <span data-ttu-id="3c15a-241">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-241">driver license number</span></span>  <br/> <span data-ttu-id="3c15a-242">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="3c15a-242">driver licence</span></span>  <br/> <span data-ttu-id="3c15a-243">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="3c15a-243">drivers lic.</span></span>  <br/> <span data-ttu-id="3c15a-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="3c15a-244">drivers license</span></span>  <br/> <span data-ttu-id="3c15a-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3c15a-245">drivers licence</span></span>  <br/> <span data-ttu-id="3c15a-246">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-246">driver's license number</span></span>  <br/> <span data-ttu-id="3c15a-247">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-247">driver's licence number</span></span>  <br/> <span data-ttu-id="3c15a-248">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-248">driving license number</span></span>  <br/> <span data-ttu-id="3c15a-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="3c15a-249">dlno#</span></span>  <br/> <span data-ttu-id="3c15a-250">άδειαοδήγησης</span><span class="sxs-lookup"><span data-stu-id="3c15a-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="3c15a-251">捷克共和国</span><span class="sxs-lookup"><span data-stu-id="3c15a-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="3c15a-252">格式</span><span class="sxs-lookup"><span data-stu-id="3c15a-252">Format</span></span>

<span data-ttu-id="3c15a-253">两个字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c15a-254">模式</span><span class="sxs-lookup"><span data-stu-id="3c15a-254">Pattern</span></span>

<span data-ttu-id="3c15a-255">八个字母和数字:</span><span class="sxs-lookup"><span data-stu-id="3c15a-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="3c15a-256">两个字母 (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="3c15a-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="3c15a-257">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="3c15a-257">A space (optional)</span></span>
    
- <span data-ttu-id="3c15a-258">六个数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3c15a-259">校验和</span><span class="sxs-lookup"><span data-stu-id="3c15a-259">Checksum</span></span>

<span data-ttu-id="3c15a-260">否</span><span class="sxs-lookup"><span data-stu-id="3c15a-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c15a-261">定义</span><span class="sxs-lookup"><span data-stu-id="3c15a-261">Definition</span></span>

<span data-ttu-id="3c15a-262">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c15a-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c15a-263">正则表达式`Regex_czech_republic_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c15a-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c15a-264">找到了中`Keywords_czech_republic_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c15a-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="3c15a-265">关键字</span><span class="sxs-lookup"><span data-stu-id="3c15a-265">Keywords</span></span>

<span data-ttu-id="3c15a-266">| |</span><span class="sxs-lookup"><span data-stu-id="3c15a-266"></span></span>
|<span data-ttu-id="3c15a-267">**Keywords_czech_republic_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3c15a-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3c15a-268">通讯</span><span class="sxs-lookup"><span data-stu-id="3c15a-268">dl#</span></span>  <br/> <span data-ttu-id="3c15a-269">driver license</span><span class="sxs-lookup"><span data-stu-id="3c15a-269">driver license</span></span>  <br/> <span data-ttu-id="3c15a-270">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-270">driver license number</span></span>  <br/> <span data-ttu-id="3c15a-271">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="3c15a-271">driver licence</span></span>  <br/> <span data-ttu-id="3c15a-272">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="3c15a-272">drivers lic.</span></span>  <br/> <span data-ttu-id="3c15a-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="3c15a-273">drivers license</span></span>  <br/> <span data-ttu-id="3c15a-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3c15a-274">drivers licence</span></span>  <br/> <span data-ttu-id="3c15a-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="3c15a-275">driver's license</span></span>  <br/> <span data-ttu-id="3c15a-276">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-276">driver's license number</span></span>  <br/> <span data-ttu-id="3c15a-277">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-277">driver's license number</span></span>  <br/> <span data-ttu-id="3c15a-278">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-278">driver's licence number</span></span>  <br/> <span data-ttu-id="3c15a-279">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-279">driving license number</span></span>  <br/> <span data-ttu-id="3c15a-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="3c15a-280">dlno#</span></span>  <br/> <span data-ttu-id="3c15a-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="3c15a-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="3c15a-282">丹麦</span><span class="sxs-lookup"><span data-stu-id="3c15a-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="3c15a-283">格式</span><span class="sxs-lookup"><span data-stu-id="3c15a-283">Format</span></span>

<span data-ttu-id="3c15a-284">8位数, 不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="3c15a-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c15a-285">模式</span><span class="sxs-lookup"><span data-stu-id="3c15a-285">Pattern</span></span>

<span data-ttu-id="3c15a-286">八个数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3c15a-287">校验和</span><span class="sxs-lookup"><span data-stu-id="3c15a-287">Checksum</span></span>

<span data-ttu-id="3c15a-288">是</span><span class="sxs-lookup"><span data-stu-id="3c15a-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c15a-289">定义</span><span class="sxs-lookup"><span data-stu-id="3c15a-289">Definition</span></span>

<span data-ttu-id="3c15a-290">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c15a-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c15a-291">正则表达式`Regex_denmark_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c15a-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c15a-292">找到了中`Keywords_denmark_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c15a-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="3c15a-293">关键字</span><span class="sxs-lookup"><span data-stu-id="3c15a-293">Keywords</span></span>

<span data-ttu-id="3c15a-294">| |</span><span class="sxs-lookup"><span data-stu-id="3c15a-294"></span></span>
|<span data-ttu-id="3c15a-295">**Keywords_denmark_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3c15a-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3c15a-296">通讯</span><span class="sxs-lookup"><span data-stu-id="3c15a-296">dl#</span></span>  <br/> <span data-ttu-id="3c15a-297">driver license</span><span class="sxs-lookup"><span data-stu-id="3c15a-297">driver license</span></span>  <br/> <span data-ttu-id="3c15a-298">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-298">driver license number</span></span>  <br/> <span data-ttu-id="3c15a-299">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="3c15a-299">driver licence</span></span>  <br/> <span data-ttu-id="3c15a-300">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="3c15a-300">drivers lic.</span></span>  <br/> <span data-ttu-id="3c15a-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="3c15a-301">drivers license</span></span>  <br/> <span data-ttu-id="3c15a-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3c15a-302">drivers licence</span></span>  <br/> <span data-ttu-id="3c15a-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="3c15a-303">driver's license</span></span>  <br/> <span data-ttu-id="3c15a-304">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-304">driver's license number</span></span>  <br/> <span data-ttu-id="3c15a-305">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-305">driver's licence number</span></span>  <br/> <span data-ttu-id="3c15a-306">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-306">driving license number</span></span>  <br/> <span data-ttu-id="3c15a-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="3c15a-307">dlno#</span></span>  <br/> <span data-ttu-id="3c15a-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="3c15a-308">kørekort</span></span>  <br/> <span data-ttu-id="3c15a-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="3c15a-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="3c15a-310">爱沙尼亚</span><span class="sxs-lookup"><span data-stu-id="3c15a-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="3c15a-311">格式</span><span class="sxs-lookup"><span data-stu-id="3c15a-311">Format</span></span>

<span data-ttu-id="3c15a-312">两个字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c15a-313">模式</span><span class="sxs-lookup"><span data-stu-id="3c15a-313">Pattern</span></span>

<span data-ttu-id="3c15a-314">两个字母和六个数字:</span><span class="sxs-lookup"><span data-stu-id="3c15a-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="3c15a-315">字母 "ET" (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="3c15a-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="3c15a-316">六个数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3c15a-317">校验和</span><span class="sxs-lookup"><span data-stu-id="3c15a-317">Checksum</span></span>

<span data-ttu-id="3c15a-318">否</span><span class="sxs-lookup"><span data-stu-id="3c15a-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c15a-319">定义</span><span class="sxs-lookup"><span data-stu-id="3c15a-319">Definition</span></span>

<span data-ttu-id="3c15a-320">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c15a-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c15a-321">正则表达式`Regex_estonia_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c15a-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c15a-322">找到了中`Keywords_estonia_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c15a-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c15a-323">关键字</span><span class="sxs-lookup"><span data-stu-id="3c15a-323">Keywords</span></span>

<span data-ttu-id="3c15a-324">| |</span><span class="sxs-lookup"><span data-stu-id="3c15a-324"></span></span>
|<span data-ttu-id="3c15a-325">**Keywords_estonia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3c15a-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3c15a-326">通讯</span><span class="sxs-lookup"><span data-stu-id="3c15a-326">dl#</span></span>  <br/> <span data-ttu-id="3c15a-327">driver license</span><span class="sxs-lookup"><span data-stu-id="3c15a-327">driver license</span></span>  <br/> <span data-ttu-id="3c15a-328">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-328">driver license number</span></span>  <br/> <span data-ttu-id="3c15a-329">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-329">driver license number</span></span>  <br/> <span data-ttu-id="3c15a-330">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="3c15a-330">driver licence</span></span>  <br/> <span data-ttu-id="3c15a-331">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="3c15a-331">drivers lic.</span></span>  <br/> <span data-ttu-id="3c15a-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="3c15a-332">drivers license</span></span>  <br/> <span data-ttu-id="3c15a-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3c15a-333">drivers licence</span></span>  <br/> <span data-ttu-id="3c15a-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="3c15a-334">driver's license</span></span>  <br/> <span data-ttu-id="3c15a-335">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-335">driver's license number</span></span>  <br/> <span data-ttu-id="3c15a-336">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-336">driving license number</span></span>  <br/> <span data-ttu-id="3c15a-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="3c15a-337">dlno#</span></span>  <br/> <span data-ttu-id="3c15a-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="3c15a-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="3c15a-339">芬兰</span><span class="sxs-lookup"><span data-stu-id="3c15a-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="3c15a-340">格式</span><span class="sxs-lookup"><span data-stu-id="3c15a-340">Format</span></span>

<span data-ttu-id="3c15a-341">10 个数字，包含连字符</span><span class="sxs-lookup"><span data-stu-id="3c15a-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c15a-342">模式</span><span class="sxs-lookup"><span data-stu-id="3c15a-342">Pattern</span></span>

<span data-ttu-id="3c15a-343">10个数字, 包含连字符:</span><span class="sxs-lookup"><span data-stu-id="3c15a-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="3c15a-344">六位数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-344">Six digits</span></span> 
    
- <span data-ttu-id="3c15a-345">一个连字符</span><span class="sxs-lookup"><span data-stu-id="3c15a-345">A hyphen</span></span>
    
-  <span data-ttu-id="3c15a-346">四个数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="3c15a-347">校验和</span><span class="sxs-lookup"><span data-stu-id="3c15a-347">Checksum</span></span>

<span data-ttu-id="3c15a-348">否</span><span class="sxs-lookup"><span data-stu-id="3c15a-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c15a-349">定义</span><span class="sxs-lookup"><span data-stu-id="3c15a-349">Definition</span></span>

<span data-ttu-id="3c15a-350">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c15a-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c15a-351">正则表达式`Regex_finland_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c15a-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c15a-352">找到了中`Keywords_finland_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c15a-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c15a-353">关键字</span><span class="sxs-lookup"><span data-stu-id="3c15a-353">Keywords</span></span>

<span data-ttu-id="3c15a-354">| |</span><span class="sxs-lookup"><span data-stu-id="3c15a-354"></span></span>
|<span data-ttu-id="3c15a-355">**Keywords_finland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3c15a-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3c15a-356">通讯</span><span class="sxs-lookup"><span data-stu-id="3c15a-356">dl#</span></span>  <br/> <span data-ttu-id="3c15a-357">driver license</span><span class="sxs-lookup"><span data-stu-id="3c15a-357">driver license</span></span>  <br/> <span data-ttu-id="3c15a-358">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-358">driver license number</span></span>  <br/> <span data-ttu-id="3c15a-359">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="3c15a-359">driver licence</span></span>  <br/> <span data-ttu-id="3c15a-360">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="3c15a-360">drivers lic.</span></span>  <br/> <span data-ttu-id="3c15a-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="3c15a-361">drivers license</span></span>  <br/> <span data-ttu-id="3c15a-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3c15a-362">drivers licence</span></span>  <br/> <span data-ttu-id="3c15a-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="3c15a-363">driver's license</span></span>  <br/> <span data-ttu-id="3c15a-364">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-364">driver's license number</span></span>  <br/> <span data-ttu-id="3c15a-365">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-365">driver's licence number</span></span>  <br/> <span data-ttu-id="3c15a-366">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-366">driving license number</span></span>  <br/> <span data-ttu-id="3c15a-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="3c15a-367">dlno#</span></span>  <br/> <span data-ttu-id="3c15a-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="3c15a-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="3c15a-369">法国</span><span class="sxs-lookup"><span data-stu-id="3c15a-369">France</span></span>

<span data-ttu-id="3c15a-370">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "法国驾 License 号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="3c15a-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="3c15a-371">德国</span><span class="sxs-lookup"><span data-stu-id="3c15a-371">Germany</span></span>

<span data-ttu-id="3c15a-372">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "德语驱动程序号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="3c15a-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="3c15a-373">希腊</span><span class="sxs-lookup"><span data-stu-id="3c15a-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="3c15a-374">格式</span><span class="sxs-lookup"><span data-stu-id="3c15a-374">Format</span></span>

<span data-ttu-id="3c15a-375">9个数字, 不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="3c15a-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c15a-376">模式</span><span class="sxs-lookup"><span data-stu-id="3c15a-376">Pattern</span></span>

 <span data-ttu-id="3c15a-377">九个数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="3c15a-378">校验和</span><span class="sxs-lookup"><span data-stu-id="3c15a-378">Checksum</span></span>

<span data-ttu-id="3c15a-379">否</span><span class="sxs-lookup"><span data-stu-id="3c15a-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c15a-380">定义</span><span class="sxs-lookup"><span data-stu-id="3c15a-380">Definition</span></span>

<span data-ttu-id="3c15a-381">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c15a-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c15a-382">正则表达式`Regex_greece_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c15a-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c15a-383">找到了中`Keywords_greece_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c15a-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c15a-384">关键字</span><span class="sxs-lookup"><span data-stu-id="3c15a-384">Keywords</span></span>

<span data-ttu-id="3c15a-385">| |</span><span class="sxs-lookup"><span data-stu-id="3c15a-385"></span></span>
|<span data-ttu-id="3c15a-386">**Keywords_greece_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3c15a-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3c15a-387">dlL</span><span class="sxs-lookup"><span data-stu-id="3c15a-387">dlL#</span></span>  <br/> <span data-ttu-id="3c15a-388">driver license</span><span class="sxs-lookup"><span data-stu-id="3c15a-388">driver license</span></span>  <br/> <span data-ttu-id="3c15a-389">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-389">driver license number</span></span>  <br/> <span data-ttu-id="3c15a-390">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="3c15a-390">driver licence</span></span>  <br/> <span data-ttu-id="3c15a-391">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="3c15a-391">drivers lic.</span></span>  <br/> <span data-ttu-id="3c15a-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="3c15a-392">drivers license</span></span>  <br/> <span data-ttu-id="3c15a-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3c15a-393">drivers licence</span></span>  <br/> <span data-ttu-id="3c15a-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="3c15a-394">driver's license</span></span>  <br/> <span data-ttu-id="3c15a-395">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-395">driver's license number</span></span>  <br/> <span data-ttu-id="3c15a-396">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-396">driver's licence number</span></span>  <br/> <span data-ttu-id="3c15a-397">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-397">driving license number</span></span>  <br/> <span data-ttu-id="3c15a-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="3c15a-398">dlno#</span></span>  <br/> <span data-ttu-id="3c15a-399">δειαοδήγησης</span><span class="sxs-lookup"><span data-stu-id="3c15a-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="3c15a-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="3c15a-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="3c15a-401">匈牙利</span><span class="sxs-lookup"><span data-stu-id="3c15a-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="3c15a-402">格式</span><span class="sxs-lookup"><span data-stu-id="3c15a-402">Format</span></span>

<span data-ttu-id="3c15a-403">两个字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c15a-404">模式</span><span class="sxs-lookup"><span data-stu-id="3c15a-404">Pattern</span></span>

<span data-ttu-id="3c15a-405">两个字母和六个数字:</span><span class="sxs-lookup"><span data-stu-id="3c15a-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="3c15a-406">两个字母 (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="3c15a-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="3c15a-407">六个数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3c15a-408">校验和</span><span class="sxs-lookup"><span data-stu-id="3c15a-408">Checksum</span></span>

<span data-ttu-id="3c15a-409">否</span><span class="sxs-lookup"><span data-stu-id="3c15a-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c15a-410">定义</span><span class="sxs-lookup"><span data-stu-id="3c15a-410">Definition</span></span>

<span data-ttu-id="3c15a-411">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c15a-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c15a-412">正则表达式`Regex_hungary_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c15a-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c15a-413">找到了中`Keywords_hungary_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c15a-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c15a-414">关键字</span><span class="sxs-lookup"><span data-stu-id="3c15a-414">Keywords</span></span>

<span data-ttu-id="3c15a-415">| |</span><span class="sxs-lookup"><span data-stu-id="3c15a-415"></span></span>
|<span data-ttu-id="3c15a-416">**Keywords_hungary_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3c15a-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3c15a-417">通讯</span><span class="sxs-lookup"><span data-stu-id="3c15a-417">dl#</span></span>  <br/> <span data-ttu-id="3c15a-418">driver license</span><span class="sxs-lookup"><span data-stu-id="3c15a-418">driver license</span></span>  <br/> <span data-ttu-id="3c15a-419">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-419">driver license number</span></span>  <br/> <span data-ttu-id="3c15a-420">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="3c15a-420">driver licence</span></span>  <br/> <span data-ttu-id="3c15a-421">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="3c15a-421">drivers lic.</span></span>  <br/> <span data-ttu-id="3c15a-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="3c15a-422">drivers license</span></span>  <br/> <span data-ttu-id="3c15a-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3c15a-423">drivers licence</span></span>  <br/> <span data-ttu-id="3c15a-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="3c15a-424">driver's license</span></span>  <br/> <span data-ttu-id="3c15a-425">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-425">driver's license number</span></span>  <br/> <span data-ttu-id="3c15a-426">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-426">driver's licence number</span></span>  <br/> <span data-ttu-id="3c15a-427">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-427">driving license number</span></span>  <br/> <span data-ttu-id="3c15a-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="3c15a-428">dlno#</span></span>  <br/> <span data-ttu-id="3c15a-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="3c15a-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="3c15a-430">Ireland</span><span class="sxs-lookup"><span data-stu-id="3c15a-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="3c15a-431">格式</span><span class="sxs-lookup"><span data-stu-id="3c15a-431">Format</span></span>

<span data-ttu-id="3c15a-432">6位数, 后跟四个字母</span><span class="sxs-lookup"><span data-stu-id="3c15a-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c15a-433">模式</span><span class="sxs-lookup"><span data-stu-id="3c15a-433">Pattern</span></span>

<span data-ttu-id="3c15a-434">6位数字和四个字母:</span><span class="sxs-lookup"><span data-stu-id="3c15a-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="3c15a-435">六位数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-435">Six digits</span></span>
    
- <span data-ttu-id="3c15a-436">四个字母 (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="3c15a-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3c15a-437">校验和</span><span class="sxs-lookup"><span data-stu-id="3c15a-437">Checksum</span></span>

<span data-ttu-id="3c15a-438">否</span><span class="sxs-lookup"><span data-stu-id="3c15a-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c15a-439">定义</span><span class="sxs-lookup"><span data-stu-id="3c15a-439">Definition</span></span>

<span data-ttu-id="3c15a-440">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c15a-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c15a-441">正则表达式`Regex_ireland_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c15a-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c15a-442">找到了中`Keywords_ireland_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c15a-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c15a-443">关键字</span><span class="sxs-lookup"><span data-stu-id="3c15a-443">Keywords</span></span>

<span data-ttu-id="3c15a-444">| |</span><span class="sxs-lookup"><span data-stu-id="3c15a-444"></span></span>
|<span data-ttu-id="3c15a-445">**Keywords_ireland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3c15a-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3c15a-446">通讯</span><span class="sxs-lookup"><span data-stu-id="3c15a-446">dl#</span></span>  <br/> <span data-ttu-id="3c15a-447">driver license</span><span class="sxs-lookup"><span data-stu-id="3c15a-447">driver license</span></span>  <br/> <span data-ttu-id="3c15a-448">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-448">driver license number</span></span>  <br/> <span data-ttu-id="3c15a-449">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="3c15a-449">driver licence</span></span>  <br/> <span data-ttu-id="3c15a-450">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="3c15a-450">drivers lic.</span></span>  <br/> <span data-ttu-id="3c15a-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="3c15a-451">drivers license</span></span>  <br/> <span data-ttu-id="3c15a-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3c15a-452">drivers licence</span></span>  <br/> <span data-ttu-id="3c15a-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="3c15a-453">driver's license</span></span>  <br/> <span data-ttu-id="3c15a-454">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-454">driver's license number</span></span>  <br/> <span data-ttu-id="3c15a-455">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-455">driver's licence number</span></span>  <br/> <span data-ttu-id="3c15a-456">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-456">driving license number</span></span>  <br/> <span data-ttu-id="3c15a-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="3c15a-457">dlno#</span></span>  <br/> <span data-ttu-id="3c15a-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="3c15a-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="3c15a-459">意大利</span><span class="sxs-lookup"><span data-stu-id="3c15a-459">Italy</span></span>

<span data-ttu-id="3c15a-460">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "意大利驾驶执照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="3c15a-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="3c15a-461">拉脱维亚</span><span class="sxs-lookup"><span data-stu-id="3c15a-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="3c15a-462">格式</span><span class="sxs-lookup"><span data-stu-id="3c15a-462">Format</span></span>

<span data-ttu-id="3c15a-463">三个字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c15a-464">模式</span><span class="sxs-lookup"><span data-stu-id="3c15a-464">Pattern</span></span>

<span data-ttu-id="3c15a-465">三个字母和六个数字:</span><span class="sxs-lookup"><span data-stu-id="3c15a-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="3c15a-466">三个字母 (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="3c15a-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="3c15a-467">六个数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3c15a-468">校验和</span><span class="sxs-lookup"><span data-stu-id="3c15a-468">Checksum</span></span>

<span data-ttu-id="3c15a-469">否</span><span class="sxs-lookup"><span data-stu-id="3c15a-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c15a-470">定义</span><span class="sxs-lookup"><span data-stu-id="3c15a-470">Definition</span></span>

<span data-ttu-id="3c15a-471">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c15a-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c15a-472">正则表达式`Regex_latvia_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c15a-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c15a-473">找到了中`Keywords_latvia_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c15a-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c15a-474">关键字</span><span class="sxs-lookup"><span data-stu-id="3c15a-474">Keywords</span></span>

<span data-ttu-id="3c15a-475">| |</span><span class="sxs-lookup"><span data-stu-id="3c15a-475"></span></span>
|<span data-ttu-id="3c15a-476">**Keywords_latvia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3c15a-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3c15a-477">通讯</span><span class="sxs-lookup"><span data-stu-id="3c15a-477">dl#</span></span>  <br/> <span data-ttu-id="3c15a-478">driver license</span><span class="sxs-lookup"><span data-stu-id="3c15a-478">driver license</span></span>  <br/> <span data-ttu-id="3c15a-479">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-479">driver license number</span></span>  <br/> <span data-ttu-id="3c15a-480">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="3c15a-480">driver licence</span></span>  <br/> <span data-ttu-id="3c15a-481">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="3c15a-481">drivers lic.</span></span>  <br/> <span data-ttu-id="3c15a-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="3c15a-482">drivers license</span></span>  <br/> <span data-ttu-id="3c15a-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3c15a-483">drivers licence</span></span>  <br/> <span data-ttu-id="3c15a-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="3c15a-484">driver's license</span></span>  <br/> <span data-ttu-id="3c15a-485">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-485">driver's license number</span></span>  <br/> <span data-ttu-id="3c15a-486">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-486">driver's licence number</span></span>  <br/> <span data-ttu-id="3c15a-487">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-487">driving license number</span></span>  <br/> <span data-ttu-id="3c15a-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="3c15a-488">dlno#</span></span>  <br/> <span data-ttu-id="3c15a-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="3c15a-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="3c15a-490">立陶宛</span><span class="sxs-lookup"><span data-stu-id="3c15a-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="3c15a-491">格式</span><span class="sxs-lookup"><span data-stu-id="3c15a-491">Format</span></span>

<span data-ttu-id="3c15a-492">8位数, 不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="3c15a-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c15a-493">模式</span><span class="sxs-lookup"><span data-stu-id="3c15a-493">Pattern</span></span>

 <span data-ttu-id="3c15a-494">八个数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="3c15a-495">校验和</span><span class="sxs-lookup"><span data-stu-id="3c15a-495">Checksum</span></span>

<span data-ttu-id="3c15a-496">否</span><span class="sxs-lookup"><span data-stu-id="3c15a-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c15a-497">定义</span><span class="sxs-lookup"><span data-stu-id="3c15a-497">Definition</span></span>

<span data-ttu-id="3c15a-498">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c15a-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c15a-499">正则表达式`Regex_lithuania_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c15a-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c15a-500">找到了中`Keywords_lithuania_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c15a-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c15a-501">关键字</span><span class="sxs-lookup"><span data-stu-id="3c15a-501">Keywords</span></span>

<span data-ttu-id="3c15a-502">| |</span><span class="sxs-lookup"><span data-stu-id="3c15a-502"></span></span>
|<span data-ttu-id="3c15a-503">**Keywords_lithuania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3c15a-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3c15a-504">通讯</span><span class="sxs-lookup"><span data-stu-id="3c15a-504">dl#</span></span>  <br/> <span data-ttu-id="3c15a-505">driver license</span><span class="sxs-lookup"><span data-stu-id="3c15a-505">driver license</span></span>  <br/> <span data-ttu-id="3c15a-506">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-506">driver license number</span></span>  <br/> <span data-ttu-id="3c15a-507">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="3c15a-507">driver licence</span></span>  <br/> <span data-ttu-id="3c15a-508">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="3c15a-508">drivers lic.</span></span>  <br/> <span data-ttu-id="3c15a-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="3c15a-509">drivers license</span></span>  <br/> <span data-ttu-id="3c15a-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3c15a-510">drivers licence</span></span>  <br/> <span data-ttu-id="3c15a-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="3c15a-511">driver's license</span></span>  <br/> <span data-ttu-id="3c15a-512">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-512">driver's license number</span></span>  <br/> <span data-ttu-id="3c15a-513">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-513">driver's licence number</span></span>  <br/> <span data-ttu-id="3c15a-514">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-514">driving license number</span></span>  <br/> <span data-ttu-id="3c15a-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="3c15a-515">dlno#</span></span>  <br/> <span data-ttu-id="3c15a-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="3c15a-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="3c15a-517">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="3c15a-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="3c15a-518">格式</span><span class="sxs-lookup"><span data-stu-id="3c15a-518">Format</span></span>

<span data-ttu-id="3c15a-519">6位数, 不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="3c15a-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c15a-520">模式</span><span class="sxs-lookup"><span data-stu-id="3c15a-520">Pattern</span></span>

 <span data-ttu-id="3c15a-521">六个数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="3c15a-522">校验和</span><span class="sxs-lookup"><span data-stu-id="3c15a-522">Checksum</span></span>

<span data-ttu-id="3c15a-523">否</span><span class="sxs-lookup"><span data-stu-id="3c15a-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c15a-524">定义</span><span class="sxs-lookup"><span data-stu-id="3c15a-524">Definition</span></span>

<span data-ttu-id="3c15a-525">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c15a-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c15a-526">正则表达式`Regex_luxemburg_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c15a-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c15a-527">找到了中`Keywords_luxemburg_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c15a-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c15a-528">关键字</span><span class="sxs-lookup"><span data-stu-id="3c15a-528">Keywords</span></span>

<span data-ttu-id="3c15a-529">| |</span><span class="sxs-lookup"><span data-stu-id="3c15a-529"></span></span>
|<span data-ttu-id="3c15a-530">**Keywords_luxemburg_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3c15a-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3c15a-531">通讯</span><span class="sxs-lookup"><span data-stu-id="3c15a-531">dl#</span></span>  <br/> <span data-ttu-id="3c15a-532">driver license</span><span class="sxs-lookup"><span data-stu-id="3c15a-532">driver license</span></span>  <br/> <span data-ttu-id="3c15a-533">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-533">driver license number</span></span>  <br/> <span data-ttu-id="3c15a-534">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="3c15a-534">driver licence</span></span>  <br/> <span data-ttu-id="3c15a-535">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="3c15a-535">drivers lic.</span></span>  <br/> <span data-ttu-id="3c15a-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="3c15a-536">drivers license</span></span>  <br/> <span data-ttu-id="3c15a-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3c15a-537">drivers licence</span></span>  <br/> <span data-ttu-id="3c15a-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="3c15a-538">driver's license</span></span>  <br/> <span data-ttu-id="3c15a-539">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-539">driver's license number</span></span>  <br/> <span data-ttu-id="3c15a-540">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-540">driver's licence number</span></span>  <br/> <span data-ttu-id="3c15a-541">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-541">driving license number</span></span>  <br/> <span data-ttu-id="3c15a-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="3c15a-542">dlno#</span></span>  <br/> <span data-ttu-id="3c15a-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="3c15a-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="3c15a-544">Malta（马耳他）</span><span class="sxs-lookup"><span data-stu-id="3c15a-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="3c15a-545">格式</span><span class="sxs-lookup"><span data-stu-id="3c15a-545">Format</span></span>

<span data-ttu-id="3c15a-546">两个字符与指定模式中的六个数字的组合</span><span class="sxs-lookup"><span data-stu-id="3c15a-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c15a-547">模式</span><span class="sxs-lookup"><span data-stu-id="3c15a-547">Pattern</span></span>

<span data-ttu-id="3c15a-548">两个字符和六个数字的组合:</span><span class="sxs-lookup"><span data-stu-id="3c15a-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="3c15a-549">两个字符 (数字或字母, 而不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="3c15a-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="3c15a-550">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="3c15a-550">A space (optional)</span></span>
    
- <span data-ttu-id="3c15a-551">三个数字 </span><span class="sxs-lookup"><span data-stu-id="3c15a-551">Three digits</span></span>
    
- <span data-ttu-id="3c15a-552">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="3c15a-552">A space (optional)</span></span>
    
- <span data-ttu-id="3c15a-553">三位数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3c15a-554">校验和</span><span class="sxs-lookup"><span data-stu-id="3c15a-554">Checksum</span></span>

<span data-ttu-id="3c15a-555">否</span><span class="sxs-lookup"><span data-stu-id="3c15a-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c15a-556">定义</span><span class="sxs-lookup"><span data-stu-id="3c15a-556">Definition</span></span>

<span data-ttu-id="3c15a-557">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c15a-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c15a-558">正则表达式`Regex_malta_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c15a-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c15a-559">找到了中`Keywords_malta_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c15a-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c15a-560">关键字</span><span class="sxs-lookup"><span data-stu-id="3c15a-560">Keywords</span></span>

<span data-ttu-id="3c15a-561">| |</span><span class="sxs-lookup"><span data-stu-id="3c15a-561"></span></span>
|<span data-ttu-id="3c15a-562">**Keywords_malta_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3c15a-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3c15a-563">通讯</span><span class="sxs-lookup"><span data-stu-id="3c15a-563">dl#</span></span>  <br/> <span data-ttu-id="3c15a-564">driver license</span><span class="sxs-lookup"><span data-stu-id="3c15a-564">driver license</span></span>  <br/> <span data-ttu-id="3c15a-565">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-565">driver license number</span></span>  <br/> <span data-ttu-id="3c15a-566">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="3c15a-566">driver licence</span></span>  <br/> <span data-ttu-id="3c15a-567">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="3c15a-567">drivers lic.</span></span>  <br/> <span data-ttu-id="3c15a-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="3c15a-568">drivers license</span></span>  <br/> <span data-ttu-id="3c15a-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3c15a-569">drivers licence</span></span>  <br/> <span data-ttu-id="3c15a-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="3c15a-570">driver's license</span></span>  <br/> <span data-ttu-id="3c15a-571">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-571">driver's license number</span></span>  <br/> <span data-ttu-id="3c15a-572">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-572">driver's licence number</span></span>  <br/> <span data-ttu-id="3c15a-573">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-573">driving license number</span></span>  <br/> <span data-ttu-id="3c15a-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="3c15a-574">dlno#</span></span>  <br/> <span data-ttu-id="3c15a-575">liċenzja tas-sewqan</span><span class="sxs-lookup"><span data-stu-id="3c15a-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="3c15a-576">荷兰</span><span class="sxs-lookup"><span data-stu-id="3c15a-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="3c15a-577">格式</span><span class="sxs-lookup"><span data-stu-id="3c15a-577">Format</span></span>

<span data-ttu-id="3c15a-578">10个数字, 不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="3c15a-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c15a-579">模式</span><span class="sxs-lookup"><span data-stu-id="3c15a-579">Pattern</span></span>

<span data-ttu-id="3c15a-580">10 个数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3c15a-581">校验和</span><span class="sxs-lookup"><span data-stu-id="3c15a-581">Checksum</span></span>

<span data-ttu-id="3c15a-582">否</span><span class="sxs-lookup"><span data-stu-id="3c15a-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c15a-583">定义</span><span class="sxs-lookup"><span data-stu-id="3c15a-583">Definition</span></span>

<span data-ttu-id="3c15a-584">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c15a-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c15a-585">正则表达式`Regex_netherlands_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c15a-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c15a-586">找到了中`Keywords_netherlands_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c15a-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c15a-587">关键字</span><span class="sxs-lookup"><span data-stu-id="3c15a-587">Keywords</span></span>

<span data-ttu-id="3c15a-588">| |</span><span class="sxs-lookup"><span data-stu-id="3c15a-588"></span></span>
|<span data-ttu-id="3c15a-589">**Keywords_netherlands_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3c15a-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3c15a-590">通讯</span><span class="sxs-lookup"><span data-stu-id="3c15a-590">dl#</span></span>  <br/> <span data-ttu-id="3c15a-591">driver license</span><span class="sxs-lookup"><span data-stu-id="3c15a-591">driver license</span></span>  <br/> <span data-ttu-id="3c15a-592">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-592">driver license number</span></span>  <br/> <span data-ttu-id="3c15a-593">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="3c15a-593">driver licence</span></span>  <br/> <span data-ttu-id="3c15a-594">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="3c15a-594">drivers lic.</span></span>  <br/> <span data-ttu-id="3c15a-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="3c15a-595">drivers license</span></span>  <br/> <span data-ttu-id="3c15a-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3c15a-596">drivers licence</span></span>  <br/> <span data-ttu-id="3c15a-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="3c15a-597">driver's license</span></span>  <br/> <span data-ttu-id="3c15a-598">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-598">driver's license number</span></span>  <br/> <span data-ttu-id="3c15a-599">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-599">driver's licence number</span></span>  <br/> <span data-ttu-id="3c15a-600">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-600">driving license number</span></span>  <br/> <span data-ttu-id="3c15a-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="3c15a-601">dlno#</span></span>  <br/> <span data-ttu-id="3c15a-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="3c15a-602">permis de conduire</span></span>  <br/> <span data-ttu-id="3c15a-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="3c15a-603">rijbewijs</span></span>  <br/> <span data-ttu-id="3c15a-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="3c15a-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="3c15a-605">波兰</span><span class="sxs-lookup"><span data-stu-id="3c15a-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="3c15a-606">格式</span><span class="sxs-lookup"><span data-stu-id="3c15a-606">Format</span></span>

<span data-ttu-id="3c15a-607">14位数, 包含2个正斜杠</span><span class="sxs-lookup"><span data-stu-id="3c15a-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c15a-608">模式</span><span class="sxs-lookup"><span data-stu-id="3c15a-608">Pattern</span></span>

<span data-ttu-id="3c15a-609">14位数和2正斜杠:</span><span class="sxs-lookup"><span data-stu-id="3c15a-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="3c15a-610">五位数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-610">Five digits</span></span> 
    
- <span data-ttu-id="3c15a-611">一个正斜杠 </span><span class="sxs-lookup"><span data-stu-id="3c15a-611">A forward slash</span></span>
    
- <span data-ttu-id="3c15a-612">两位数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-612">Two digits</span></span>
    
- <span data-ttu-id="3c15a-613">一个正斜杠 </span><span class="sxs-lookup"><span data-stu-id="3c15a-613">A forward slash</span></span>
    
- <span data-ttu-id="3c15a-614">七个数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3c15a-615">校验和</span><span class="sxs-lookup"><span data-stu-id="3c15a-615">Checksum</span></span>

<span data-ttu-id="3c15a-616">否</span><span class="sxs-lookup"><span data-stu-id="3c15a-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c15a-617">定义</span><span class="sxs-lookup"><span data-stu-id="3c15a-617">Definition</span></span>

<span data-ttu-id="3c15a-618">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c15a-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c15a-619">正则表达式`Regex_poland_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c15a-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c15a-620">找到了中`Keywords_poland_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c15a-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c15a-621">关键字</span><span class="sxs-lookup"><span data-stu-id="3c15a-621">Keywords</span></span>

<span data-ttu-id="3c15a-622">| |</span><span class="sxs-lookup"><span data-stu-id="3c15a-622"></span></span>
|<span data-ttu-id="3c15a-623">**Keywords_poland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3c15a-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3c15a-624">通讯</span><span class="sxs-lookup"><span data-stu-id="3c15a-624">dl#</span></span>  <br/> <span data-ttu-id="3c15a-625">driver license</span><span class="sxs-lookup"><span data-stu-id="3c15a-625">driver license</span></span>  <br/> <span data-ttu-id="3c15a-626">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-626">driver license number</span></span>  <br/> <span data-ttu-id="3c15a-627">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="3c15a-627">driver licence</span></span>  <br/> <span data-ttu-id="3c15a-628">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="3c15a-628">drivers lic.</span></span>  <br/> <span data-ttu-id="3c15a-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="3c15a-629">drivers license</span></span>  <br/> <span data-ttu-id="3c15a-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3c15a-630">drivers licence</span></span>  <br/> <span data-ttu-id="3c15a-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="3c15a-631">driver's license</span></span>  <br/> <span data-ttu-id="3c15a-632">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-632">driver's license number</span></span>  <br/> <span data-ttu-id="3c15a-633">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-633">driver's licence number</span></span>  <br/> <span data-ttu-id="3c15a-634">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-634">driving license number</span></span>  <br/> <span data-ttu-id="3c15a-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="3c15a-635">dlno#</span></span>  <br/> <span data-ttu-id="3c15a-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="3c15a-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="3c15a-637">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="3c15a-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="3c15a-638">格式</span><span class="sxs-lookup"><span data-stu-id="3c15a-638">Format</span></span>

<span data-ttu-id="3c15a-639">两个字母后跟指定模式中的七个数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c15a-640">模式</span><span class="sxs-lookup"><span data-stu-id="3c15a-640">Pattern</span></span>

<span data-ttu-id="3c15a-641">两个字母后跟七个包含特殊字符的数字:</span><span class="sxs-lookup"><span data-stu-id="3c15a-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="3c15a-642">两个字母 (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="3c15a-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="3c15a-643">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="3c15a-643">A hyphen</span></span>
    
- <span data-ttu-id="3c15a-644">六位数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-644">Six digits</span></span>
    
- <span data-ttu-id="3c15a-645">一个空格</span><span class="sxs-lookup"><span data-stu-id="3c15a-645">A space</span></span>
    
- <span data-ttu-id="3c15a-646">一个数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3c15a-647">校验和</span><span class="sxs-lookup"><span data-stu-id="3c15a-647">Checksum</span></span>

<span data-ttu-id="3c15a-648">否</span><span class="sxs-lookup"><span data-stu-id="3c15a-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c15a-649">定义</span><span class="sxs-lookup"><span data-stu-id="3c15a-649">Definition</span></span>

<span data-ttu-id="3c15a-650">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c15a-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c15a-651">正则表达式`Regex_portugal_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c15a-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c15a-652">找到了中`Keywords_portugal_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c15a-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c15a-653">关键字</span><span class="sxs-lookup"><span data-stu-id="3c15a-653">Keywords</span></span>

<span data-ttu-id="3c15a-654">| |</span><span class="sxs-lookup"><span data-stu-id="3c15a-654"></span></span>
|<span data-ttu-id="3c15a-655">**Keywords_portugal_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3c15a-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3c15a-656">通讯</span><span class="sxs-lookup"><span data-stu-id="3c15a-656">dl#</span></span>  <br/> <span data-ttu-id="3c15a-657">driver license</span><span class="sxs-lookup"><span data-stu-id="3c15a-657">driver license</span></span>  <br/> <span data-ttu-id="3c15a-658">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-658">driver license number</span></span>  <br/> <span data-ttu-id="3c15a-659">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="3c15a-659">driver licence</span></span>  <br/> <span data-ttu-id="3c15a-660">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="3c15a-660">drivers lic.</span></span>  <br/> <span data-ttu-id="3c15a-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="3c15a-661">drivers license</span></span>  <br/> <span data-ttu-id="3c15a-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3c15a-662">drivers licence</span></span>  <br/> <span data-ttu-id="3c15a-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="3c15a-663">driver's license</span></span>  <br/> <span data-ttu-id="3c15a-664">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-664">driver's license number</span></span>  <br/> <span data-ttu-id="3c15a-665">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-665">driver's licence number</span></span>  <br/> <span data-ttu-id="3c15a-666">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-666">driving license number</span></span>  <br/> <span data-ttu-id="3c15a-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="3c15a-667">dlno#</span></span>  <br/> <span data-ttu-id="3c15a-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="3c15a-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="3c15a-669">罗马尼亚</span><span class="sxs-lookup"><span data-stu-id="3c15a-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="3c15a-670">格式</span><span class="sxs-lookup"><span data-stu-id="3c15a-670">Format</span></span>

<span data-ttu-id="3c15a-671">一个字符后跟八个数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c15a-672">模式</span><span class="sxs-lookup"><span data-stu-id="3c15a-672">Pattern</span></span>

<span data-ttu-id="3c15a-673">一个字符后跟八个数字:</span><span class="sxs-lookup"><span data-stu-id="3c15a-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="3c15a-674">一个字母 (不区分大小写) 或数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="3c15a-675">八个数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3c15a-676">校验和</span><span class="sxs-lookup"><span data-stu-id="3c15a-676">Checksum</span></span>

<span data-ttu-id="3c15a-677">否</span><span class="sxs-lookup"><span data-stu-id="3c15a-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c15a-678">定义</span><span class="sxs-lookup"><span data-stu-id="3c15a-678">Definition</span></span>

<span data-ttu-id="3c15a-679">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c15a-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c15a-680">正则表达式`Regex_romania_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c15a-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c15a-681">找到了中`Keywords_romania_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c15a-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c15a-682">关键字</span><span class="sxs-lookup"><span data-stu-id="3c15a-682">Keywords</span></span>

<span data-ttu-id="3c15a-683">| |</span><span class="sxs-lookup"><span data-stu-id="3c15a-683"></span></span>
|<span data-ttu-id="3c15a-684">**Keywords_romania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3c15a-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3c15a-685">通讯</span><span class="sxs-lookup"><span data-stu-id="3c15a-685">dl#</span></span>  <br/> <span data-ttu-id="3c15a-686">driver license</span><span class="sxs-lookup"><span data-stu-id="3c15a-686">driver license</span></span>  <br/> <span data-ttu-id="3c15a-687">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-687">driver license number</span></span>  <br/> <span data-ttu-id="3c15a-688">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="3c15a-688">driver licence</span></span>  <br/> <span data-ttu-id="3c15a-689">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="3c15a-689">drivers lic.</span></span>  <br/> <span data-ttu-id="3c15a-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="3c15a-690">drivers license</span></span>  <br/> <span data-ttu-id="3c15a-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3c15a-691">drivers licence</span></span>  <br/> <span data-ttu-id="3c15a-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="3c15a-692">driver's license</span></span>  <br/> <span data-ttu-id="3c15a-693">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-693">driver's license number</span></span>  <br/> <span data-ttu-id="3c15a-694">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-694">driver's licence number</span></span>  <br/> <span data-ttu-id="3c15a-695">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-695">driving license number</span></span>  <br/> <span data-ttu-id="3c15a-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="3c15a-696">dlno#</span></span>  <br/> <span data-ttu-id="3c15a-697">permis de conducere</span><span class="sxs-lookup"><span data-stu-id="3c15a-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="3c15a-698">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="3c15a-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="3c15a-699">格式</span><span class="sxs-lookup"><span data-stu-id="3c15a-699">Format</span></span>

<span data-ttu-id="3c15a-700">一个字符后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c15a-701">模式</span><span class="sxs-lookup"><span data-stu-id="3c15a-701">Pattern</span></span>

<span data-ttu-id="3c15a-702">一个字符后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="3c15a-703">一个字母 (不区分大小写) 或数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="3c15a-704">七个数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="3c15a-705">校验和</span><span class="sxs-lookup"><span data-stu-id="3c15a-705">Checksum</span></span>

<span data-ttu-id="3c15a-706">否</span><span class="sxs-lookup"><span data-stu-id="3c15a-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c15a-707">定义</span><span class="sxs-lookup"><span data-stu-id="3c15a-707">Definition</span></span>

<span data-ttu-id="3c15a-708">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c15a-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c15a-709">正则表达式`Regex_slovakia_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c15a-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c15a-710">找到了中`Keywords_slovakia_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c15a-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c15a-711">关键字</span><span class="sxs-lookup"><span data-stu-id="3c15a-711">Keywords</span></span>

<span data-ttu-id="3c15a-712">| |</span><span class="sxs-lookup"><span data-stu-id="3c15a-712"></span></span>
|<span data-ttu-id="3c15a-713">**Keywords_slovakia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3c15a-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3c15a-714">通讯</span><span class="sxs-lookup"><span data-stu-id="3c15a-714">dl#</span></span>  <br/> <span data-ttu-id="3c15a-715">driver license</span><span class="sxs-lookup"><span data-stu-id="3c15a-715">driver license</span></span>  <br/> <span data-ttu-id="3c15a-716">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-716">driver license number</span></span>  <br/> <span data-ttu-id="3c15a-717">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="3c15a-717">driver licence</span></span>  <br/> <span data-ttu-id="3c15a-718">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="3c15a-718">drivers lic.</span></span>  <br/> <span data-ttu-id="3c15a-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="3c15a-719">drivers license</span></span>  <br/> <span data-ttu-id="3c15a-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3c15a-720">drivers licence</span></span>  <br/> <span data-ttu-id="3c15a-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="3c15a-721">driver's license</span></span>  <br/> <span data-ttu-id="3c15a-722">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-722">driver's license number</span></span>  <br/> <span data-ttu-id="3c15a-723">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-723">driver's licence number</span></span>  <br/> <span data-ttu-id="3c15a-724">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-724">driving license number</span></span>  <br/> <span data-ttu-id="3c15a-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="3c15a-725">dlno#</span></span>  <br/> <span data-ttu-id="3c15a-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="3c15a-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="3c15a-727">斯洛文尼亚</span><span class="sxs-lookup"><span data-stu-id="3c15a-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="3c15a-728">格式</span><span class="sxs-lookup"><span data-stu-id="3c15a-728">Format</span></span>

<span data-ttu-id="3c15a-729">9个数字, 不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="3c15a-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c15a-730">模式</span><span class="sxs-lookup"><span data-stu-id="3c15a-730">Pattern</span></span>

<span data-ttu-id="3c15a-731">九个数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3c15a-732">校验和</span><span class="sxs-lookup"><span data-stu-id="3c15a-732">Checksum</span></span>

<span data-ttu-id="3c15a-733">否</span><span class="sxs-lookup"><span data-stu-id="3c15a-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c15a-734">定义</span><span class="sxs-lookup"><span data-stu-id="3c15a-734">Definition</span></span>

<span data-ttu-id="3c15a-735">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c15a-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c15a-736">正则表达式`Regex_slovenia_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c15a-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c15a-737">找到了中`Keywords_slovenia_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c15a-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c15a-738">关键字</span><span class="sxs-lookup"><span data-stu-id="3c15a-738">Keywords</span></span>

<span data-ttu-id="3c15a-739">| |</span><span class="sxs-lookup"><span data-stu-id="3c15a-739"></span></span>
|<span data-ttu-id="3c15a-740">**Keywords_slovenia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3c15a-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3c15a-741">通讯</span><span class="sxs-lookup"><span data-stu-id="3c15a-741">dl#</span></span>  <br/> <span data-ttu-id="3c15a-742">driver license</span><span class="sxs-lookup"><span data-stu-id="3c15a-742">driver license</span></span>  <br/> <span data-ttu-id="3c15a-743">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-743">driver license number</span></span>  <br/> <span data-ttu-id="3c15a-744">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="3c15a-744">driver licence</span></span>  <br/> <span data-ttu-id="3c15a-745">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="3c15a-745">drivers lic.</span></span>  <br/> <span data-ttu-id="3c15a-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="3c15a-746">drivers license</span></span>  <br/> <span data-ttu-id="3c15a-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3c15a-747">drivers licence</span></span>  <br/> <span data-ttu-id="3c15a-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="3c15a-748">driver's license</span></span>  <br/> <span data-ttu-id="3c15a-749">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-749">driver's license number</span></span>  <br/> <span data-ttu-id="3c15a-750">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-750">driver's licence number</span></span>  <br/> <span data-ttu-id="3c15a-751">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-751">driving license number</span></span>  <br/> <span data-ttu-id="3c15a-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="3c15a-752">dlno#</span></span>  <br/> <span data-ttu-id="3c15a-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="3c15a-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="3c15a-754">西班牙</span><span class="sxs-lookup"><span data-stu-id="3c15a-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="3c15a-755">格式</span><span class="sxs-lookup"><span data-stu-id="3c15a-755">Format</span></span>

<span data-ttu-id="3c15a-756">8位数, 后跟一个字符</span><span class="sxs-lookup"><span data-stu-id="3c15a-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c15a-757">模式</span><span class="sxs-lookup"><span data-stu-id="3c15a-757">Pattern</span></span>

<span data-ttu-id="3c15a-758">8位数, 后跟一个字符:</span><span class="sxs-lookup"><span data-stu-id="3c15a-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="3c15a-759">八个数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-759">Eight digits</span></span> 
    
- <span data-ttu-id="3c15a-760">一个数字或字母 (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="3c15a-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3c15a-761">校验和</span><span class="sxs-lookup"><span data-stu-id="3c15a-761">Checksum</span></span>

<span data-ttu-id="3c15a-762">是</span><span class="sxs-lookup"><span data-stu-id="3c15a-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c15a-763">定义</span><span class="sxs-lookup"><span data-stu-id="3c15a-763">Definition</span></span>

<span data-ttu-id="3c15a-764">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c15a-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c15a-765">函数`Func_spain_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c15a-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c15a-766">找到了中`Keywords_spain_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c15a-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3c15a-767">关键字</span><span class="sxs-lookup"><span data-stu-id="3c15a-767">Keywords</span></span>

<span data-ttu-id="3c15a-768">| |</span><span class="sxs-lookup"><span data-stu-id="3c15a-768"></span></span>
|<span data-ttu-id="3c15a-769">**Keywords_spain_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3c15a-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3c15a-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="3c15a-770">dlno#</span></span>  <br/> <span data-ttu-id="3c15a-771">通讯</span><span class="sxs-lookup"><span data-stu-id="3c15a-771">dl#</span></span>  <br/> <span data-ttu-id="3c15a-772">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="3c15a-772">drivers lic.</span></span>  <br/> <span data-ttu-id="3c15a-773">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="3c15a-773">driver licence</span></span>  <br/> <span data-ttu-id="3c15a-774">driver license</span><span class="sxs-lookup"><span data-stu-id="3c15a-774">driver license</span></span>  <br/> <span data-ttu-id="3c15a-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3c15a-775">drivers licence</span></span>  <br/> <span data-ttu-id="3c15a-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="3c15a-776">drivers license</span></span>  <br/> <span data-ttu-id="3c15a-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="3c15a-777">driver's licence</span></span>  <br/> <span data-ttu-id="3c15a-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="3c15a-778">driver's license</span></span>  <br/> <span data-ttu-id="3c15a-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="3c15a-779">driving licence</span></span>  <br/> <span data-ttu-id="3c15a-780">driving license</span><span class="sxs-lookup"><span data-stu-id="3c15a-780">driving license</span></span>  <br/> <span data-ttu-id="3c15a-781">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-781">driver licence number</span></span>  <br/> <span data-ttu-id="3c15a-782">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-782">driver license number</span></span>  <br/> <span data-ttu-id="3c15a-783">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-783">drivers licence number</span></span>  <br/> <span data-ttu-id="3c15a-784">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-784">drivers license number</span></span>  <br/> <span data-ttu-id="3c15a-785">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-785">driver's licence number</span></span>  <br/> <span data-ttu-id="3c15a-786">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-786">driver's license number</span></span>  <br/> <span data-ttu-id="3c15a-787">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-787">driving licence number</span></span>  <br/> <span data-ttu-id="3c15a-788">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-788">driving license number</span></span>  <br/> <span data-ttu-id="3c15a-789">促进允许</span><span class="sxs-lookup"><span data-stu-id="3c15a-789">driving permit</span></span>  <br/> <span data-ttu-id="3c15a-790">驾驶允许号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-790">driving permit number</span></span>  <br/> <span data-ttu-id="3c15a-791">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="3c15a-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="3c15a-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="3c15a-792">permiso conducción</span></span>  <br/> <span data-ttu-id="3c15a-793">número licencia conducir</span><span class="sxs-lookup"><span data-stu-id="3c15a-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="3c15a-794">número de carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="3c15a-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="3c15a-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="3c15a-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="3c15a-796">licencia conducir</span><span class="sxs-lookup"><span data-stu-id="3c15a-796">licencia conducir</span></span>  <br/> <span data-ttu-id="3c15a-797">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="3c15a-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="3c15a-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="3c15a-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="3c15a-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="3c15a-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="3c15a-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="3c15a-800">permiso conducir</span></span>  <br/> <span data-ttu-id="3c15a-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="3c15a-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="3c15a-802">el carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="3c15a-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="3c15a-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="3c15a-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="3c15a-804">瑞典</span><span class="sxs-lookup"><span data-stu-id="3c15a-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="3c15a-805">格式</span><span class="sxs-lookup"><span data-stu-id="3c15a-805">Format</span></span>

<span data-ttu-id="3c15a-806">10个数字, 包含连字符</span><span class="sxs-lookup"><span data-stu-id="3c15a-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3c15a-807">模式</span><span class="sxs-lookup"><span data-stu-id="3c15a-807">Pattern</span></span>

<span data-ttu-id="3c15a-808">10位数, 包含连字符:</span><span class="sxs-lookup"><span data-stu-id="3c15a-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="3c15a-809">六位数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-809">Six digits</span></span> 
    
- <span data-ttu-id="3c15a-810">一个连字符</span><span class="sxs-lookup"><span data-stu-id="3c15a-810">A hyphen</span></span>
    
- <span data-ttu-id="3c15a-811">四个数字</span><span class="sxs-lookup"><span data-stu-id="3c15a-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3c15a-812">校验和</span><span class="sxs-lookup"><span data-stu-id="3c15a-812">Checksum</span></span>

<span data-ttu-id="3c15a-813">否</span><span class="sxs-lookup"><span data-stu-id="3c15a-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3c15a-814">定义</span><span class="sxs-lookup"><span data-stu-id="3c15a-814">Definition</span></span>

<span data-ttu-id="3c15a-815">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3c15a-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3c15a-816">正则表达式`Regex_sweden_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3c15a-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3c15a-817">找到了中`Keywords_sweden_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3c15a-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="3c15a-818">关键字</span><span class="sxs-lookup"><span data-stu-id="3c15a-818">Keywords</span></span>

<span data-ttu-id="3c15a-819">| |</span><span class="sxs-lookup"><span data-stu-id="3c15a-819"></span></span>
|<span data-ttu-id="3c15a-820">**Keywords_sweden_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3c15a-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3c15a-821">通讯</span><span class="sxs-lookup"><span data-stu-id="3c15a-821">dl#</span></span>  <br/> <span data-ttu-id="3c15a-822">driver license</span><span class="sxs-lookup"><span data-stu-id="3c15a-822">driver license</span></span>  <br/> <span data-ttu-id="3c15a-823">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-823">driver license number</span></span>  <br/> <span data-ttu-id="3c15a-824">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="3c15a-824">driver licence</span></span>  <br/> <span data-ttu-id="3c15a-825">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="3c15a-825">drivers lic.</span></span>  <br/> <span data-ttu-id="3c15a-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="3c15a-826">drivers license</span></span>  <br/> <span data-ttu-id="3c15a-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3c15a-827">drivers licence</span></span>  <br/> <span data-ttu-id="3c15a-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="3c15a-828">driver's license</span></span>  <br/> <span data-ttu-id="3c15a-829">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-829">driver's license number</span></span>  <br/> <span data-ttu-id="3c15a-830">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="3c15a-830">driver's licence number</span></span>  <br/> <span data-ttu-id="3c15a-831">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="3c15a-831">driving license number</span></span>  <br/> <span data-ttu-id="3c15a-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="3c15a-832">dlno#</span></span>  <br/> <span data-ttu-id="3c15a-833">körkort</span><span class="sxs-lookup"><span data-stu-id="3c15a-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="3c15a-834">英国</span><span class="sxs-lookup"><span data-stu-id="3c15a-834">UK</span></span>

<span data-ttu-id="3c15a-835">有关详细信息, 请参阅部分 "英国</span><span class="sxs-lookup"><span data-stu-id="3c15a-835">For details, see the section "U.K.</span></span> <span data-ttu-id="3c15a-836">"[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)" 中的 "驾驶执照号码"。</span><span class="sxs-lookup"><span data-stu-id="3c15a-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3c15a-837">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3c15a-837">See also</span></span>

[<span data-ttu-id="3c15a-838">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="3c15a-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

