---
title: 欧盟 GPS 坐标
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/14/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: fdf2aebc-d5a4-4138-b10f-4a81dd70415a
description: Office 365 安全性的数据丢失防护 (DLP)&amp;合规性中心包括许多可供您可以使用 DLP 策略中的敏感信息类型。本主题介绍的欧盟 GPS 协调敏感信息类型。
ms.openlocfilehash: 89fb8420e479b9f793fc2be9aa3a9a9fd5741691
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525322"
---
# <a name="eu-gps-coordinates"></a><span data-ttu-id="8508e-104">欧盟 GPS 坐标</span><span class="sxs-lookup"><span data-stu-id="8508e-104">EU GPS Coordinates</span></span>

<span data-ttu-id="8508e-p102">Office 365 安全性的数据丢失防护 (DLP)&amp;合规性中心包括许多可供您可以使用 DLP 策略中的敏感信息类型。本主题介绍的欧盟 GPS 协调敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="8508e-p102">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies. This topic describes the EU GPS Coordinates sensitive information type.</span></span>
  
## <a name="austria"></a><span data-ttu-id="8508e-107">奥地利</span><span class="sxs-lookup"><span data-stu-id="8508e-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="8508e-108">格式</span><span class="sxs-lookup"><span data-stu-id="8508e-108">Format</span></span>

<span data-ttu-id="8508e-109">协调的城市奥地利中的所处的区域中： 从 46.526 纬度 48.816 和从 9.6 16.945 到经度。</span><span class="sxs-lookup"><span data-stu-id="8508e-109">Coordinates for cities in Austria are in range: Latitude from 46.526 to 48.816 and longitude from 9.6 to 16.945.</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8508e-110">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-110">Pattern</span></span>

<span data-ttu-id="8508e-111">对于每个坐标，最多 6 位数和小数点的组合。</span><span class="sxs-lookup"><span data-stu-id="8508e-111">For each coordinate, combination of up to 6 digits and a decimal point.</span></span>
  
- <span data-ttu-id="8508e-112">最多 6 个数字</span><span class="sxs-lookup"><span data-stu-id="8508e-112">Up to 6 digits</span></span>
    
- <span data-ttu-id="8508e-113">小数点后第一个或第二个数字。</span><span class="sxs-lookup"><span data-stu-id="8508e-113">A decimal point after first or second digit.</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8508e-114">校验和</span><span class="sxs-lookup"><span data-stu-id="8508e-114">Checksum</span></span>

<span data-ttu-id="8508e-115">不适用</span><span class="sxs-lookup"><span data-stu-id="8508e-115">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-116">定义</span><span class="sxs-lookup"><span data-stu-id="8508e-116">Definition</span></span>

<span data-ttu-id="8508e-117">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8508e-117">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-118">正则表达式`Regex_austria_eu_gps_data_1`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8508e-118">The regular expression  `Regex_austria_eu_gps_data_1` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8508e-119">从关键字`Keywords_austria_eu_gps_data`找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-119">A keyword from  `Keywords_austria_eu_gps_data` is found.</span></span> 
    
<span data-ttu-id="8508e-120">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8508e-120">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-121">正则表达式`Regex_austria_eu_gps_data_1`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8508e-121">The regular expression  `Regex_austria_eu_gps_data_1` finds content that matches the pattern.</span></span> 
    
<span data-ttu-id="8508e-122">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8508e-122">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-123">正则表达式`Regex_austria_eu_gps_data_2`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8508e-123">The regular expression  `Regex_austria_eu_gps_data_2` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8508e-124">从关键字`Keywords_austria_eu_gps_data`找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-124">A keyword from  `Keywords_austria_eu_gps_data` is found.</span></span> 
    
<span data-ttu-id="8508e-125">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8508e-125">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-126">正则表达式`Regex_austria_eu_gps_data_2`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8508e-126">The regular expression  `Regex_austria_eu_gps_data_2` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_gps_data_1" />
          <Match idRef="Keywords_austria_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_austria_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_gps_data_2" />
          <Match idRef="Keywords_austria_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_austria_eu_gps_data_2" />
        </Pattern>

```

### <a name="keywords"></a><span data-ttu-id="8508e-127">Keywords</span><span class="sxs-lookup"><span data-stu-id="8508e-127">Keywords</span></span>

#### <a name="keywordsaustriaeugpsdata"></a><span data-ttu-id="8508e-128">Keywords_austria_eu_gps_data</span><span class="sxs-lookup"><span data-stu-id="8508e-128">Keywords_austria_eu_gps_data</span></span>

<span data-ttu-id="8508e-129">gps 跟踪程序</span><span class="sxs-lookup"><span data-stu-id="8508e-129">gps tracker</span></span>
  
<span data-ttu-id="8508e-130">gps 坐标</span><span class="sxs-lookup"><span data-stu-id="8508e-130">gps coordinates</span></span>
  
<span data-ttu-id="8508e-131">位置</span><span class="sxs-lookup"><span data-stu-id="8508e-131">location</span></span>
  
<span data-ttu-id="8508e-132">映射</span><span class="sxs-lookup"><span data-stu-id="8508e-132">map</span></span>
  
<span data-ttu-id="8508e-133">纬度</span><span class="sxs-lookup"><span data-stu-id="8508e-133">latitude</span></span>
  
<span data-ttu-id="8508e-134">经度</span><span class="sxs-lookup"><span data-stu-id="8508e-134">longitude</span></span>
  
<span data-ttu-id="8508e-135">GPS 跟踪程序</span><span class="sxs-lookup"><span data-stu-id="8508e-135">GPS-Tracker</span></span>
  
<span data-ttu-id="8508e-136">GPS Koordinaten</span><span class="sxs-lookup"><span data-stu-id="8508e-136">GPS-Koordinaten</span></span>
  
<span data-ttu-id="8508e-137">Standort Karte</span><span class="sxs-lookup"><span data-stu-id="8508e-137">Standort Karte</span></span>
  
<span data-ttu-id="8508e-138">Breitengrad</span><span class="sxs-lookup"><span data-stu-id="8508e-138">Breitengrad</span></span>
  
<span data-ttu-id="8508e-139">Längengrad</span><span class="sxs-lookup"><span data-stu-id="8508e-139">Längengrad</span></span>
  
## <a name="belgium"></a><span data-ttu-id="8508e-140">比利时</span><span class="sxs-lookup"><span data-stu-id="8508e-140">Belgium</span></span>

### <a name="pattern"></a><span data-ttu-id="8508e-141">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-141">Pattern</span></span>

-  <span data-ttu-id="8508e-142">数字</span><span class="sxs-lookup"><span data-stu-id="8508e-142">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8508e-143">校验和</span><span class="sxs-lookup"><span data-stu-id="8508e-143">Checksum</span></span>

<span data-ttu-id="8508e-144">不适用</span><span class="sxs-lookup"><span data-stu-id="8508e-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-145">定义</span><span class="sxs-lookup"><span data-stu-id="8508e-145">Definition</span></span>

<span data-ttu-id="8508e-146">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8508e-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-147">正则表达式可查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8508e-147">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="8508e-148">从关键字是找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-148">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75>">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_gps_data_1" />
          <Match idRef="Keywords_belgium_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_belgium_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_gps_data_2" />
          <Match idRef="Keywords_belgium_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_belgium_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="bulgaria"></a><span data-ttu-id="8508e-149">保加利亚</span><span class="sxs-lookup"><span data-stu-id="8508e-149">Bulgaria</span></span>

### <a name="pattern"></a><span data-ttu-id="8508e-150">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-150">Pattern</span></span>

-  <span data-ttu-id="8508e-151">数字</span><span class="sxs-lookup"><span data-stu-id="8508e-151">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8508e-152">校验和</span><span class="sxs-lookup"><span data-stu-id="8508e-152">Checksum</span></span>

<span data-ttu-id="8508e-153">不适用</span><span class="sxs-lookup"><span data-stu-id="8508e-153">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-154">定义</span><span class="sxs-lookup"><span data-stu-id="8508e-154">Definition</span></span>

<span data-ttu-id="8508e-155">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8508e-155">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-156">正则表达式可查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8508e-156">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="8508e-157">从关键字是找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-157">A keyword from is found.</span></span>
    
```
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75>
</Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_belgium_eu_gps_data_2" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_gps_data_1" />
          <Match idRef="Keywords_bulgaria_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_bulgaria_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_gps_data_2" />
          <Match idRef="Keywords_bulgaria_eu_gps_data" />
        </Pattern>
</Entity>
```

## <a name="croatia"></a><span data-ttu-id="8508e-158">克罗地亚</span><span class="sxs-lookup"><span data-stu-id="8508e-158">Croatia</span></span>

### <a name="pattern"></a><span data-ttu-id="8508e-159">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-159">Pattern</span></span>

-  <span data-ttu-id="8508e-160">数字</span><span class="sxs-lookup"><span data-stu-id="8508e-160">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8508e-161">校验和</span><span class="sxs-lookup"><span data-stu-id="8508e-161">Checksum</span></span>

<span data-ttu-id="8508e-162">不适用</span><span class="sxs-lookup"><span data-stu-id="8508e-162">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-163">定义</span><span class="sxs-lookup"><span data-stu-id="8508e-163">Definition</span></span>

<span data-ttu-id="8508e-164">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8508e-164">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-165">正则表达式可查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8508e-165">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="8508e-166">从关键字是找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-166">A keyword from is found.</span></span>
    
```
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_gps_data_1" />
          <Match idRef="Keywords_croatia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_croatia_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_gps_data_2" />
          <Match idRef="Keywords_croatia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_croatia_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="cyprus"></a><span data-ttu-id="8508e-167">塞浦路斯</span><span class="sxs-lookup"><span data-stu-id="8508e-167">Cyprus</span></span>

### <a name="pattern"></a><span data-ttu-id="8508e-168">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-168">Pattern</span></span>

-  <span data-ttu-id="8508e-169">数字</span><span class="sxs-lookup"><span data-stu-id="8508e-169">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8508e-170">校验和</span><span class="sxs-lookup"><span data-stu-id="8508e-170">Checksum</span></span>

<span data-ttu-id="8508e-171">不适用</span><span class="sxs-lookup"><span data-stu-id="8508e-171">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-172">定义</span><span class="sxs-lookup"><span data-stu-id="8508e-172">Definition</span></span>

<span data-ttu-id="8508e-173">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8508e-173">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-174">正则表达式可查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8508e-174">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="8508e-175">从关键字是找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-175">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_gps_data_1" />
          <Match idRef="Keywords_cyprus_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_cyprus_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_gps_data_2" />
          <Match idRef="Keywords_cyprus_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_cyprus_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="czech-republic"></a><span data-ttu-id="8508e-176">捷克共和国</span><span class="sxs-lookup"><span data-stu-id="8508e-176">Czech Republic</span></span>

### <a name="pattern"></a><span data-ttu-id="8508e-177">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-177">Pattern</span></span>

-  <span data-ttu-id="8508e-178">数字</span><span class="sxs-lookup"><span data-stu-id="8508e-178">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8508e-179">校验和</span><span class="sxs-lookup"><span data-stu-id="8508e-179">Checksum</span></span>

<span data-ttu-id="8508e-180">不适用</span><span class="sxs-lookup"><span data-stu-id="8508e-180">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-181">定义</span><span class="sxs-lookup"><span data-stu-id="8508e-181">Definition</span></span>

<span data-ttu-id="8508e-182">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8508e-182">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
<span data-ttu-id="8508e-183">DLP 策略是 %相信它已检测到此类型的敏感信息 if、 中字符的邻近性：</span><span class="sxs-lookup"><span data-stu-id="8508e-183">A DLP policy is % confident that it's detected this type of sensitive information if, within a proximity of characters:</span></span>
  
- <span data-ttu-id="8508e-184">正则表达式可查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8508e-184">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="8508e-185">从关键字是找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-185">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_gps_data_1" />
          <Match idRef="Keywords_czech_republic_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_czech_republic_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_gps_data_2" />
          <Match idRef="Keywords_czech_republic_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_czech_republic_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="denmark"></a><span data-ttu-id="8508e-186">丹麦</span><span class="sxs-lookup"><span data-stu-id="8508e-186">Denmark</span></span>

### <a name="pattern"></a><span data-ttu-id="8508e-187">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-187">Pattern</span></span>

-  <span data-ttu-id="8508e-188">数字</span><span class="sxs-lookup"><span data-stu-id="8508e-188">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8508e-189">校验和</span><span class="sxs-lookup"><span data-stu-id="8508e-189">Checksum</span></span>

<span data-ttu-id="8508e-190">不适用</span><span class="sxs-lookup"><span data-stu-id="8508e-190">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-191">定义</span><span class="sxs-lookup"><span data-stu-id="8508e-191">Definition</span></span>

<span data-ttu-id="8508e-192">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8508e-192">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-193">正则表达式可查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8508e-193">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="8508e-194">从关键字是找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-194">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_gps_data_1" />
          <Match idRef="Keywords_denmark_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_denmark_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_gps_data_2" />
          <Match idRef="Keywords_denmark_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_denmark_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="estonia"></a><span data-ttu-id="8508e-195">爱沙尼亚</span><span class="sxs-lookup"><span data-stu-id="8508e-195">Estonia</span></span>

### <a name="pattern"></a><span data-ttu-id="8508e-196">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-196">Pattern</span></span>

-  <span data-ttu-id="8508e-197">数字</span><span class="sxs-lookup"><span data-stu-id="8508e-197">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8508e-198">校验和</span><span class="sxs-lookup"><span data-stu-id="8508e-198">Checksum</span></span>

<span data-ttu-id="8508e-199">不适用</span><span class="sxs-lookup"><span data-stu-id="8508e-199">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-200">定义</span><span class="sxs-lookup"><span data-stu-id="8508e-200">Definition</span></span>

<span data-ttu-id="8508e-201">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8508e-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-202">正则表达式可查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8508e-202">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="8508e-203">从关键字是找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-203">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_gps_data_1" />
          <Match idRef="Keywords_estonia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_estonia_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_gps_data_2" />
          <Match idRef="Keywords_estonia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_estonia_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="finland"></a><span data-ttu-id="8508e-204">芬兰</span><span class="sxs-lookup"><span data-stu-id="8508e-204">Finland</span></span>

### <a name="pattern"></a><span data-ttu-id="8508e-205">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-205">Pattern</span></span>

-  <span data-ttu-id="8508e-206">数字</span><span class="sxs-lookup"><span data-stu-id="8508e-206">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8508e-207">校验和</span><span class="sxs-lookup"><span data-stu-id="8508e-207">Checksum</span></span>

<span data-ttu-id="8508e-208">不适用</span><span class="sxs-lookup"><span data-stu-id="8508e-208">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-209">定义</span><span class="sxs-lookup"><span data-stu-id="8508e-209">Definition</span></span>

<span data-ttu-id="8508e-210">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8508e-210">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-211">正则表达式可查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8508e-211">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="8508e-212">从关键字是找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-212">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_gps_data_1" />
          <Match idRef="Keywords_finland_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_finland_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_gps_data_2" />
          <Match idRef="Keywords_finland_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_finland_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="france"></a><span data-ttu-id="8508e-213">法国</span><span class="sxs-lookup"><span data-stu-id="8508e-213">France</span></span>

### <a name="pattern"></a><span data-ttu-id="8508e-214">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-214">Pattern</span></span>

-  <span data-ttu-id="8508e-215">数字</span><span class="sxs-lookup"><span data-stu-id="8508e-215">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8508e-216">校验和</span><span class="sxs-lookup"><span data-stu-id="8508e-216">Checksum</span></span>

<span data-ttu-id="8508e-217">不适用</span><span class="sxs-lookup"><span data-stu-id="8508e-217">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-218">定义</span><span class="sxs-lookup"><span data-stu-id="8508e-218">Definition</span></span>

<span data-ttu-id="8508e-219">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8508e-219">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-220">正则表达式可查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8508e-220">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="8508e-221">从关键字是找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-221">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_france_eu_gps_data_1" />
          <Match idRef="Keywords_france_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_france_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_france_eu_gps_data_2" />
          <Match idRef="Keywords_france_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_france_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="germany"></a><span data-ttu-id="8508e-222">德国</span><span class="sxs-lookup"><span data-stu-id="8508e-222">Germany</span></span>

### <a name="pattern"></a><span data-ttu-id="8508e-223">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-223">Pattern</span></span>

-  <span data-ttu-id="8508e-224">数字</span><span class="sxs-lookup"><span data-stu-id="8508e-224">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8508e-225">校验和</span><span class="sxs-lookup"><span data-stu-id="8508e-225">Checksum</span></span>

<span data-ttu-id="8508e-226">不适用</span><span class="sxs-lookup"><span data-stu-id="8508e-226">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-227">定义</span><span class="sxs-lookup"><span data-stu-id="8508e-227">Definition</span></span>

<span data-ttu-id="8508e-228">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8508e-228">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-229">正则表达式可查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8508e-229">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="8508e-230">从关键字是找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-230">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_germany_eu_gps_data_1" />
          <Match idRef="Keywords_germany_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_germany_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_germany_eu_gps_data_2" />
          <Match idRef="Keywords_germany_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_germany_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="greece"></a><span data-ttu-id="8508e-231">希腊</span><span class="sxs-lookup"><span data-stu-id="8508e-231">Greece</span></span>

### <a name="pattern"></a><span data-ttu-id="8508e-232">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-232">Pattern</span></span>

-  <span data-ttu-id="8508e-233">数字</span><span class="sxs-lookup"><span data-stu-id="8508e-233">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8508e-234">校验和</span><span class="sxs-lookup"><span data-stu-id="8508e-234">Checksum</span></span>

<span data-ttu-id="8508e-235">不适用</span><span class="sxs-lookup"><span data-stu-id="8508e-235">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-236">定义</span><span class="sxs-lookup"><span data-stu-id="8508e-236">Definition</span></span>

<span data-ttu-id="8508e-237">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8508e-237">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-238">正则表达式可查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8508e-238">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="8508e-239">从关键字是找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-239">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_gps_data_1" />
          <Match idRef="Keywords_greece_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_greece_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_gps_data_2" />
          <Match idRef="Keywords_greece_eu_gps_data" />
        </Pattern>
</Entity>
```

## <a name="hungary"></a><span data-ttu-id="8508e-240">匈牙利</span><span class="sxs-lookup"><span data-stu-id="8508e-240">Hungary</span></span>

### <a name="pattern"></a><span data-ttu-id="8508e-241">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-241">Pattern</span></span>

-  <span data-ttu-id="8508e-242">数字</span><span class="sxs-lookup"><span data-stu-id="8508e-242">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8508e-243">校验和</span><span class="sxs-lookup"><span data-stu-id="8508e-243">Checksum</span></span>

<span data-ttu-id="8508e-244">不适用</span><span class="sxs-lookup"><span data-stu-id="8508e-244">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-245">定义</span><span class="sxs-lookup"><span data-stu-id="8508e-245">Definition</span></span>

<span data-ttu-id="8508e-246">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8508e-246">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-247">正则表达式可查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8508e-247">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="8508e-248">从关键字是找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-248">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_gps_data_1" />
          <Match idRef="Keywords_hungary_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_hungary_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_gps_data_2" />
          <Match idRef="Keywords_hungary_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_hungary_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="ireland"></a><span data-ttu-id="8508e-249">Ireland</span><span class="sxs-lookup"><span data-stu-id="8508e-249">Ireland</span></span>

### <a name="pattern"></a><span data-ttu-id="8508e-250">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-250">Pattern</span></span>

-  <span data-ttu-id="8508e-251">数字</span><span class="sxs-lookup"><span data-stu-id="8508e-251">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8508e-252">校验和</span><span class="sxs-lookup"><span data-stu-id="8508e-252">Checksum</span></span>

<span data-ttu-id="8508e-253">不适用</span><span class="sxs-lookup"><span data-stu-id="8508e-253">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-254">定义</span><span class="sxs-lookup"><span data-stu-id="8508e-254">Definition</span></span>

<span data-ttu-id="8508e-255">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8508e-255">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-256">正则表达式可查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8508e-256">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="8508e-257">从关键字是找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-257">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_gps_data_1" />
          <Match idRef="Keywords_ireland_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_ireland_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_gps_data_2" />
          <Match idRef="Keywords_ireland_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_ireland_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="italy"></a><span data-ttu-id="8508e-258">意大利</span><span class="sxs-lookup"><span data-stu-id="8508e-258">Italy</span></span>

### <a name="pattern"></a><span data-ttu-id="8508e-259">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-259">Pattern</span></span>

-  <span data-ttu-id="8508e-260">数字</span><span class="sxs-lookup"><span data-stu-id="8508e-260">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8508e-261">校验和</span><span class="sxs-lookup"><span data-stu-id="8508e-261">Checksum</span></span>

<span data-ttu-id="8508e-262">不适用</span><span class="sxs-lookup"><span data-stu-id="8508e-262">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-263">定义</span><span class="sxs-lookup"><span data-stu-id="8508e-263">Definition</span></span>

<span data-ttu-id="8508e-264">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8508e-264">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-265">正则表达式可查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8508e-265">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="8508e-266">从关键字是找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-266">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_gps_data_1" />
          <Match idRef="Keywords_italy_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_italy_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_gps_data_2" />
          <Match idRef="Keywords_italy_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_italy_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="latvia"></a><span data-ttu-id="8508e-267">拉脱维亚</span><span class="sxs-lookup"><span data-stu-id="8508e-267">Latvia</span></span>

### <a name="pattern"></a><span data-ttu-id="8508e-268">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-268">Pattern</span></span>

-  <span data-ttu-id="8508e-269">数字</span><span class="sxs-lookup"><span data-stu-id="8508e-269">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8508e-270">校验和</span><span class="sxs-lookup"><span data-stu-id="8508e-270">Checksum</span></span>

<span data-ttu-id="8508e-271">不适用</span><span class="sxs-lookup"><span data-stu-id="8508e-271">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-272">定义</span><span class="sxs-lookup"><span data-stu-id="8508e-272">Definition</span></span>

<span data-ttu-id="8508e-273">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8508e-273">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-274">正则表达式可查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8508e-274">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="8508e-275">从关键字是找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-275">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_gps_data_1" />
          <Match idRef="Keywords_latvia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_latvia_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_gps_data_2" />
          <Match idRef="Keywords_latvia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_latvia_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="lithuania"></a><span data-ttu-id="8508e-276">立陶宛</span><span class="sxs-lookup"><span data-stu-id="8508e-276">Lithuania</span></span>

### <a name="pattern"></a><span data-ttu-id="8508e-277">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-277">Pattern</span></span>

-  <span data-ttu-id="8508e-278">数字</span><span class="sxs-lookup"><span data-stu-id="8508e-278">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8508e-279">校验和</span><span class="sxs-lookup"><span data-stu-id="8508e-279">Checksum</span></span>

<span data-ttu-id="8508e-280">不适用</span><span class="sxs-lookup"><span data-stu-id="8508e-280">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-281">定义</span><span class="sxs-lookup"><span data-stu-id="8508e-281">Definition</span></span>

<span data-ttu-id="8508e-282">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8508e-282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-283">正则表达式可查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8508e-283">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="8508e-284">从关键字是找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-284">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_gps_data_1" />
          <Match idRef="Keywords_lithuania_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_lithuania_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_gps_data_2" />
          <Match idRef="Keywords_lithuania_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_lithuania_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="luxemburg"></a><span data-ttu-id="8508e-285">卢森堡</span><span class="sxs-lookup"><span data-stu-id="8508e-285">Luxemburg</span></span>

### <a name="pattern"></a><span data-ttu-id="8508e-286">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-286">Pattern</span></span>

-  <span data-ttu-id="8508e-287">数字</span><span class="sxs-lookup"><span data-stu-id="8508e-287">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8508e-288">校验和</span><span class="sxs-lookup"><span data-stu-id="8508e-288">Checksum</span></span>

<span data-ttu-id="8508e-289">不适用</span><span class="sxs-lookup"><span data-stu-id="8508e-289">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-290">定义</span><span class="sxs-lookup"><span data-stu-id="8508e-290">Definition</span></span>

<span data-ttu-id="8508e-291">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8508e-291">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-292">正则表达式可查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8508e-292">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="8508e-293">从关键字是找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-293">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_gps_data_1" />
          <Match idRef="Keywords_luxemburg_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_luxemburg_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_gps_data_2" />
          <Match idRef="Keywords_luxemburg_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_luxemburg_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="malta"></a><span data-ttu-id="8508e-294">马耳他</span><span class="sxs-lookup"><span data-stu-id="8508e-294">Malta</span></span>

### <a name="pattern"></a><span data-ttu-id="8508e-295">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-295">Pattern</span></span>

-  <span data-ttu-id="8508e-296">数字</span><span class="sxs-lookup"><span data-stu-id="8508e-296">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8508e-297">校验和</span><span class="sxs-lookup"><span data-stu-id="8508e-297">Checksum</span></span>

<span data-ttu-id="8508e-298">不适用</span><span class="sxs-lookup"><span data-stu-id="8508e-298">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-299">定义</span><span class="sxs-lookup"><span data-stu-id="8508e-299">Definition</span></span>

<span data-ttu-id="8508e-300">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8508e-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-301">正则表达式可查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8508e-301">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="8508e-302">从关键字是找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-302">A keyword from is found.</span></span>
    
```
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_gps_data_1" />
          <Match idRef="Keywords_malta_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_gps_data_2" />
          <Match idRef="Keywords_malta_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="netherlands"></a><span data-ttu-id="8508e-303">荷兰</span><span class="sxs-lookup"><span data-stu-id="8508e-303">Netherlands</span></span>

### <a name="pattern"></a><span data-ttu-id="8508e-304">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-304">Pattern</span></span>

-  <span data-ttu-id="8508e-305">数字</span><span class="sxs-lookup"><span data-stu-id="8508e-305">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8508e-306">校验和</span><span class="sxs-lookup"><span data-stu-id="8508e-306">Checksum</span></span>

<span data-ttu-id="8508e-307">不适用</span><span class="sxs-lookup"><span data-stu-id="8508e-307">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-308">定义</span><span class="sxs-lookup"><span data-stu-id="8508e-308">Definition</span></span>

<span data-ttu-id="8508e-309">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8508e-309">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-310">正则表达式可查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8508e-310">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="8508e-311">从关键字是找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-311">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_gps_data_1" />
          <Match idRef="Keywords_netherlands_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_netherlands_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_gps_data_2" />
          <Match idRef="Keywords_netherlands_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_netherlands_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="poland"></a><span data-ttu-id="8508e-312">波兰</span><span class="sxs-lookup"><span data-stu-id="8508e-312">Poland</span></span>

### <a name="pattern"></a><span data-ttu-id="8508e-313">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-313">Pattern</span></span>

-  <span data-ttu-id="8508e-314">数字</span><span class="sxs-lookup"><span data-stu-id="8508e-314">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8508e-315">校验和</span><span class="sxs-lookup"><span data-stu-id="8508e-315">Checksum</span></span>

<span data-ttu-id="8508e-316">不适用</span><span class="sxs-lookup"><span data-stu-id="8508e-316">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-317">定义</span><span class="sxs-lookup"><span data-stu-id="8508e-317">Definition</span></span>

<span data-ttu-id="8508e-318">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8508e-318">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-319">正则表达式可查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8508e-319">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="8508e-320">从关键字是找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-320">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_gps_data_1" />
          <Match idRef="Keywords_poland_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_poland_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_gps_data_2" />
          <Match idRef="Keywords_poland_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_poland_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="portugal"></a><span data-ttu-id="8508e-321">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="8508e-321">Portugal</span></span>

### <a name="pattern"></a><span data-ttu-id="8508e-322">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-322">Pattern</span></span>

-  <span data-ttu-id="8508e-323">数字</span><span class="sxs-lookup"><span data-stu-id="8508e-323">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8508e-324">校验和</span><span class="sxs-lookup"><span data-stu-id="8508e-324">Checksum</span></span>

<span data-ttu-id="8508e-325">不适用</span><span class="sxs-lookup"><span data-stu-id="8508e-325">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-326">定义</span><span class="sxs-lookup"><span data-stu-id="8508e-326">Definition</span></span>

<span data-ttu-id="8508e-327">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8508e-327">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-328">正则表达式可查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8508e-328">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="8508e-329">从关键字是找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-329">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_gps_data_1" />
          <Match idRef="Keywords_portugal_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_portugal_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_gps_data_2" />
          <Match idRef="Keywords_portugal_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_portugal_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="romania"></a><span data-ttu-id="8508e-330">罗马尼亚</span><span class="sxs-lookup"><span data-stu-id="8508e-330">Romania</span></span>

### <a name="pattern"></a><span data-ttu-id="8508e-331">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-331">Pattern</span></span>

-  <span data-ttu-id="8508e-332">数字</span><span class="sxs-lookup"><span data-stu-id="8508e-332">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8508e-333">校验和</span><span class="sxs-lookup"><span data-stu-id="8508e-333">Checksum</span></span>

<span data-ttu-id="8508e-334">不适用</span><span class="sxs-lookup"><span data-stu-id="8508e-334">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-335">定义</span><span class="sxs-lookup"><span data-stu-id="8508e-335">Definition</span></span>

<span data-ttu-id="8508e-336">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8508e-336">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-337">正则表达式可查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8508e-337">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="8508e-338">从关键字是找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-338">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_gps_data_1" />
          <Match idRef="Keywords_romania_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_romania_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_gps_data_2" />
          <Match idRef="Keywords_romania_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_romania_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="slovakia"></a><span data-ttu-id="8508e-339">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="8508e-339">Slovakia</span></span>

### <a name="pattern"></a><span data-ttu-id="8508e-340">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-340">Pattern</span></span>

-  <span data-ttu-id="8508e-341">数字</span><span class="sxs-lookup"><span data-stu-id="8508e-341">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8508e-342">校验和</span><span class="sxs-lookup"><span data-stu-id="8508e-342">Checksum</span></span>

<span data-ttu-id="8508e-343">不适用</span><span class="sxs-lookup"><span data-stu-id="8508e-343">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-344">定义</span><span class="sxs-lookup"><span data-stu-id="8508e-344">Definition</span></span>

<span data-ttu-id="8508e-345">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8508e-345">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-346">正则表达式可查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8508e-346">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="8508e-347">从关键字是找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-347">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_gps_data_1" />
          <Match idRef="Keywords_slovakia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_slovakia_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_gps_data_2" />
          <Match idRef="Keywords_slovakia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_slovakia_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="slovenia"></a><span data-ttu-id="8508e-348">斯诺文尼亚</span><span class="sxs-lookup"><span data-stu-id="8508e-348">Slovenia</span></span>

### <a name="pattern"></a><span data-ttu-id="8508e-349">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-349">Pattern</span></span>

-  <span data-ttu-id="8508e-350">数字</span><span class="sxs-lookup"><span data-stu-id="8508e-350">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8508e-351">校验和</span><span class="sxs-lookup"><span data-stu-id="8508e-351">Checksum</span></span>

<span data-ttu-id="8508e-352">不适用</span><span class="sxs-lookup"><span data-stu-id="8508e-352">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-353">定义</span><span class="sxs-lookup"><span data-stu-id="8508e-353">Definition</span></span>

<span data-ttu-id="8508e-354">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8508e-354">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-355">正则表达式可查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8508e-355">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="8508e-356">从关键字是找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-356">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_gps_data_1" />
          <Match idRef="Keywords_slovenia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_slovenia_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_gps_data_2" />
          <Match idRef="Keywords_slovenia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_slovenia_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="spain"></a><span data-ttu-id="8508e-357">西班牙</span><span class="sxs-lookup"><span data-stu-id="8508e-357">Spain</span></span>

### <a name="pattern"></a><span data-ttu-id="8508e-358">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-358">Pattern</span></span>

-  <span data-ttu-id="8508e-359">数字</span><span class="sxs-lookup"><span data-stu-id="8508e-359">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8508e-360">校验和</span><span class="sxs-lookup"><span data-stu-id="8508e-360">Checksum</span></span>

<span data-ttu-id="8508e-361">不适用</span><span class="sxs-lookup"><span data-stu-id="8508e-361">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-362">定义</span><span class="sxs-lookup"><span data-stu-id="8508e-362">Definition</span></span>

<span data-ttu-id="8508e-363">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8508e-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-364">正则表达式可查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8508e-364">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="8508e-365">从关键字是找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-365">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_gps_data_1" />
          <Match idRef="Keywords_spain_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_spain_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_gps_data_2" />
          <Match idRef="Keywords_spain_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_spain_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="sweden"></a><span data-ttu-id="8508e-366">瑞典</span><span class="sxs-lookup"><span data-stu-id="8508e-366">Sweden</span></span>

### <a name="pattern"></a><span data-ttu-id="8508e-367">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-367">Pattern</span></span>

-  <span data-ttu-id="8508e-368">数字</span><span class="sxs-lookup"><span data-stu-id="8508e-368">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8508e-369">校验和</span><span class="sxs-lookup"><span data-stu-id="8508e-369">Checksum</span></span>

<span data-ttu-id="8508e-370">不适用</span><span class="sxs-lookup"><span data-stu-id="8508e-370">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-371">定义</span><span class="sxs-lookup"><span data-stu-id="8508e-371">Definition</span></span>

<span data-ttu-id="8508e-372">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8508e-372">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-373">正则表达式可查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8508e-373">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="8508e-374">从关键字是找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-374">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_gps_data_1" />
          <Match idRef="Keywords_sweden_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_sweden_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_gps_data_2" />
          <Match idRef="Keywords_sweden_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_sweden_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="uk"></a><span data-ttu-id="8508e-375">英国</span><span class="sxs-lookup"><span data-stu-id="8508e-375">UK</span></span>

### <a name="pattern"></a><span data-ttu-id="8508e-376">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-376">Pattern</span></span>

-  <span data-ttu-id="8508e-377">数字</span><span class="sxs-lookup"><span data-stu-id="8508e-377">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8508e-378">校验和</span><span class="sxs-lookup"><span data-stu-id="8508e-378">Checksum</span></span>

<span data-ttu-id="8508e-379">不适用</span><span class="sxs-lookup"><span data-stu-id="8508e-379">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-380">定义</span><span class="sxs-lookup"><span data-stu-id="8508e-380">Definition</span></span>

<span data-ttu-id="8508e-381">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8508e-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-382">正则表达式可查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8508e-382">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="8508e-383">从关键字是找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-383">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_uk_eu_gps_data_1" />
          <Match idRef="Keywords_uk_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_uk_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_uk_eu_gps_data_2" />
          <Match idRef="Keywords_uk_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_uk_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="see-also"></a><span data-ttu-id="8508e-384">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8508e-384">See also</span></span>

[<span data-ttu-id="8508e-385">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="8508e-385">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

