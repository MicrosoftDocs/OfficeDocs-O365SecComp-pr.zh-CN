---
title: 欧盟电话号码
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 1c90ca41-1681-46bf-8ad6-6bf4cec5c426
description: Office 365 安全性的数据丢失防护 (DLP)&amp;合规性中心包括许多可供您可以使用 DLP 策略中的敏感信息类型。本主题介绍欧盟电话号码敏感信息类型。
ms.openlocfilehash: 9dd878e3385312982f9f3a4927205e3ebb27aabb
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525477"
---
# <a name="eu-phone-number"></a><span data-ttu-id="1e104-104">欧盟电话号码</span><span class="sxs-lookup"><span data-stu-id="1e104-104">EU Phone Number</span></span>

<span data-ttu-id="1e104-p102">Office 365 安全性的数据丢失防护 (DLP)&amp;合规性中心包括许多可供您可以使用 DLP 策略中的敏感信息类型。本主题介绍欧盟电话号码敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="1e104-p102">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies. This topic describes the EU Phone Number sensitive information type.</span></span> 
  
## <a name="austria"></a><span data-ttu-id="1e104-107">奥地利</span><span class="sxs-lookup"><span data-stu-id="1e104-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="1e104-108">格式</span><span class="sxs-lookup"><span data-stu-id="1e104-108">Format</span></span>

<span data-ttu-id="1e104-109">没有标准长度</span><span class="sxs-lookup"><span data-stu-id="1e104-109">No standard length</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1e104-110">模式</span><span class="sxs-lookup"><span data-stu-id="1e104-110">Pattern</span></span>

- <span data-ttu-id="1e104-111">数字</span><span class="sxs-lookup"><span data-stu-id="1e104-111">Digits</span></span> 
    
- <span data-ttu-id="1e104-112">仅移动电话号码开始的数字"6"</span><span class="sxs-lookup"><span data-stu-id="1e104-112">Only mobile phone numbers begin with the digit "6"</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="1e104-113">校验和</span><span class="sxs-lookup"><span data-stu-id="1e104-113">Checksum</span></span>

<span data-ttu-id="1e104-114">不适用</span><span class="sxs-lookup"><span data-stu-id="1e104-114">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e104-115">定义</span><span class="sxs-lookup"><span data-stu-id="1e104-115">Definition</span></span>

<span data-ttu-id="1e104-116">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-116">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-117">正则表达式`Regex_austria_eu_telephone_number_1`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-117">The regular expression  `Regex_austria_eu_telephone_number_1` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e104-118">从关键字`Keywords_austria_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1e104-118">A keyword from  `Keywords_austria_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="1e104-119">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-119">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-120">正则表达式`Regex_austria_eu_telephone_number_2`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-120">The regular expression  `Regex_austria_eu_telephone_number_2` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e104-121">从关键字`Keywords_austria_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1e104-121">A keyword from  `Keywords_austria_eu_telephone_number` is found.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_telephone_number_1" />
          <Match idRef="Keywords_austria_eu_telephone_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_telephone_number_2" />
          <Match idRef="Keywords_austria_eu_telephone_number" />
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_austria_eu_formatted_telephone_number_1" />
          </Pattern>
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_austria_eu_formatted_telephone_number_2" />
          </Pattern>
</Entity>
```

## <a name="belgium"></a><span data-ttu-id="1e104-122">比利时</span><span class="sxs-lookup"><span data-stu-id="1e104-122">Belgium</span></span>

### <a name="definition"></a><span data-ttu-id="1e104-123">定义</span><span class="sxs-lookup"><span data-stu-id="1e104-123">Definition</span></span>

<span data-ttu-id="1e104-124">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-125">正则表达式`Regex_belgium_eu_telephone_number_1`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-125">The regular expression  `Regex_belgium_eu_telephone_number_1` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e104-126">从关键字`Keywords_belgium_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1e104-126">A keyword from  `Keywords_belgium_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="1e104-127">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-127">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-128">正则表达式`Regex_belgium_eu_telephone_number_2`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-128">The regular expression  `Regex_belgium_eu_telephone_number_2` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e104-129">从关键字`Keywords_belgium_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1e104-129">A keyword from  `Keywords_belgium_eu_telephone_number` is found.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_telephone_number_1" />
          <Match idRef="Keywords_belgium_eu_telephone_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_telephone_number_2" />
          <Match idRef="Keywords_belgium_eu_telephone_number" />
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_belgium_eu_formatted_telephone_number_1" />
          </Pattern>
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_belgium_eu_formatted_telephone_number_2" />
          </Pattern></Entity>
```

## <a name="bulgaria"></a><span data-ttu-id="1e104-130">保加利亚</span><span class="sxs-lookup"><span data-stu-id="1e104-130">Bulgaria</span></span>

### <a name="pattern"></a><span data-ttu-id="1e104-131">模式</span><span class="sxs-lookup"><span data-stu-id="1e104-131">Pattern</span></span>

- <span data-ttu-id="1e104-132">数字</span><span class="sxs-lookup"><span data-stu-id="1e104-132">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="1e104-133">校验和</span><span class="sxs-lookup"><span data-stu-id="1e104-133">Checksum</span></span>

<span data-ttu-id="1e104-134">不适用</span><span class="sxs-lookup"><span data-stu-id="1e104-134">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e104-135">定义</span><span class="sxs-lookup"><span data-stu-id="1e104-135">Definition</span></span>

<span data-ttu-id="1e104-136">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-136">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-137">正则表达式`Regex_bulgaria_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-137">The regular expression  `Regex_bulgaria_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e104-138">从关键字`Keywords_bulgaria_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1e104-138">A keyword from  `Keywords_bulgaria_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="1e104-139">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-139">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-140">正则表达式`Regex_bulgaria_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-140">The regular expression  `Regex_bulgaria_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_telephone_number" />
          <Match idRef="Keywords_bulgaria_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_bulgaria_eu_formatted_telephone_number" />
          </Pattern>
          
</Entity>
```

## <a name="croatia"></a><span data-ttu-id="1e104-141">克罗地亚</span><span class="sxs-lookup"><span data-stu-id="1e104-141">Croatia</span></span>

### <a name="pattern"></a><span data-ttu-id="1e104-142">模式</span><span class="sxs-lookup"><span data-stu-id="1e104-142">Pattern</span></span>

- <span data-ttu-id="1e104-143">数字</span><span class="sxs-lookup"><span data-stu-id="1e104-143">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="1e104-144">校验和</span><span class="sxs-lookup"><span data-stu-id="1e104-144">Checksum</span></span>

<span data-ttu-id="1e104-145">不适用</span><span class="sxs-lookup"><span data-stu-id="1e104-145">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e104-146">定义</span><span class="sxs-lookup"><span data-stu-id="1e104-146">Definition</span></span>

<span data-ttu-id="1e104-147">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-148">正则表达式`Regex_croatia_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-148">The regular expression  `Regex_croatia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e104-149">从关键字`Keywords_croatia_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1e104-149">A keyword from  `Keywords_croatia_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="1e104-150">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-150">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-151">正则表达式`Regex_croatia_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-151">The regular expression  `Regex_croatia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_telephone_number" />
          <Match idRef="Keywords_croatia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_croatia_eu_formatted_telephone_number" />
          </Pattern>
         </Entity>
```

## <a name="cyprus"></a><span data-ttu-id="1e104-152">塞浦路斯</span><span class="sxs-lookup"><span data-stu-id="1e104-152">Cyprus</span></span>

### <a name="pattern"></a><span data-ttu-id="1e104-153">模式</span><span class="sxs-lookup"><span data-stu-id="1e104-153">Pattern</span></span>

- <span data-ttu-id="1e104-154">数字</span><span class="sxs-lookup"><span data-stu-id="1e104-154">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="1e104-155">校验和</span><span class="sxs-lookup"><span data-stu-id="1e104-155">Checksum</span></span>

<span data-ttu-id="1e104-156">不适用</span><span class="sxs-lookup"><span data-stu-id="1e104-156">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e104-157">定义</span><span class="sxs-lookup"><span data-stu-id="1e104-157">Definition</span></span>

<span data-ttu-id="1e104-158">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-159">正则表达式`Regex_cyprus_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-159">The regular expression  `Regex_cyprus_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e104-160">从关键字`Keywords_cyprus_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1e104-160">A keyword from  `Keywords_cyprus_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="1e104-161">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-161">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-162">正则表达式`Regex_cyprus_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-162">The regular expression  `Regex_cyprus_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_telephone_number" />
          <Match idRef="Keywords_cyprus_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_cyprus_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="czech-republic"></a><span data-ttu-id="1e104-163">捷克共和国</span><span class="sxs-lookup"><span data-stu-id="1e104-163">Czech Republic</span></span>

### <a name="pattern"></a><span data-ttu-id="1e104-164">模式</span><span class="sxs-lookup"><span data-stu-id="1e104-164">Pattern</span></span>

- <span data-ttu-id="1e104-165">数字</span><span class="sxs-lookup"><span data-stu-id="1e104-165">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="1e104-166">校验和</span><span class="sxs-lookup"><span data-stu-id="1e104-166">Checksum</span></span>

<span data-ttu-id="1e104-167">不适用</span><span class="sxs-lookup"><span data-stu-id="1e104-167">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e104-168">定义</span><span class="sxs-lookup"><span data-stu-id="1e104-168">Definition</span></span>

<span data-ttu-id="1e104-169">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-169">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-170">正则表达式`Regex_czech_republic_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-170">The regular expression  `Regex_czech_republic_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e104-171">从关键字`Keywords_czech_republic_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1e104-171">A keyword from  `Keywords_czech_republic_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="1e104-172">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-172">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-173">正则表达式`Regex_czech_republic_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-173">The regular expression  `Regex_czech_republic_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_telephone_number" />
          <Match idRef="Keywords_czech_republic_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_czech_republic_eu_formatted_telephone_number" />
          </Pattern>
        </Entity>
```

## <a name="denmark"></a><span data-ttu-id="1e104-174">丹麦</span><span class="sxs-lookup"><span data-stu-id="1e104-174">Denmark</span></span>

### <a name="pattern"></a><span data-ttu-id="1e104-175">模式</span><span class="sxs-lookup"><span data-stu-id="1e104-175">Pattern</span></span>

- <span data-ttu-id="1e104-176">数字</span><span class="sxs-lookup"><span data-stu-id="1e104-176">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="1e104-177">校验和</span><span class="sxs-lookup"><span data-stu-id="1e104-177">Checksum</span></span>

<span data-ttu-id="1e104-178">不适用</span><span class="sxs-lookup"><span data-stu-id="1e104-178">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e104-179">定义</span><span class="sxs-lookup"><span data-stu-id="1e104-179">Definition</span></span>

<span data-ttu-id="1e104-180">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-180">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-181">正则表达式`Regex_denmark_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-181">The regular expression  `Regex_denmark_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e104-182">从关键字`Keywords_denmark_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1e104-182">A keyword from  `Keywords_denmark_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="1e104-183">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-184">正则表达式`Regex_denmark_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-184">The regular expression  `Regex_denmark_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_telephone_number" />
          <Match idRef="Keywords_denmark_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_denmark_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="estonia"></a><span data-ttu-id="1e104-185">爱沙尼亚</span><span class="sxs-lookup"><span data-stu-id="1e104-185">Estonia</span></span>

### <a name="pattern"></a><span data-ttu-id="1e104-186">模式</span><span class="sxs-lookup"><span data-stu-id="1e104-186">Pattern</span></span>

- <span data-ttu-id="1e104-187">数字</span><span class="sxs-lookup"><span data-stu-id="1e104-187">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="1e104-188">校验和</span><span class="sxs-lookup"><span data-stu-id="1e104-188">Checksum</span></span>

<span data-ttu-id="1e104-189">不适用</span><span class="sxs-lookup"><span data-stu-id="1e104-189">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e104-190">定义</span><span class="sxs-lookup"><span data-stu-id="1e104-190">Definition</span></span>

<span data-ttu-id="1e104-191">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-191">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-192">正则表达式`Regex_estonia_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-192">The regular expression  `Regex_estonia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e104-193">从关键字`Keywords_estonia_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1e104-193">A keyword from  `Keywords_estonia_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="1e104-194">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-195">正则表达式`Regex_estonia_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-195">The regular expression  `Regex_estonia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_telephone_number" />
          <Match idRef="Keywords_estonia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_estonia_eu_formatted_telephone_number" />
          </Pattern>
       </Entity>
```

## <a name="finland"></a><span data-ttu-id="1e104-196">芬兰</span><span class="sxs-lookup"><span data-stu-id="1e104-196">Finland</span></span>

### <a name="pattern"></a><span data-ttu-id="1e104-197">模式</span><span class="sxs-lookup"><span data-stu-id="1e104-197">Pattern</span></span>

- <span data-ttu-id="1e104-198">数字</span><span class="sxs-lookup"><span data-stu-id="1e104-198">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="1e104-199">校验和</span><span class="sxs-lookup"><span data-stu-id="1e104-199">Checksum</span></span>

<span data-ttu-id="1e104-200">不适用</span><span class="sxs-lookup"><span data-stu-id="1e104-200">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e104-201">定义</span><span class="sxs-lookup"><span data-stu-id="1e104-201">Definition</span></span>

<span data-ttu-id="1e104-202">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-203">正则表达式`Regex_finland_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-203">The regular expression  `Regex_finland_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e104-204">从关键字`Keywords_finland_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1e104-204">A keyword from  `Keywords_finland_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="1e104-205">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-205">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-206">正则表达式`Regex_finland_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-206">The regular expression  `Regex_finland_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_telephone_number" />
          <Match idRef="Keywords_finland_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_finland_eu_formatted_telephone_number" />
             </Pattern>
</Entity>
```

## <a name="france"></a><span data-ttu-id="1e104-207">法国</span><span class="sxs-lookup"><span data-stu-id="1e104-207">France</span></span>

### <a name="pattern"></a><span data-ttu-id="1e104-208">模式</span><span class="sxs-lookup"><span data-stu-id="1e104-208">Pattern</span></span>

- <span data-ttu-id="1e104-209">数字</span><span class="sxs-lookup"><span data-stu-id="1e104-209">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="1e104-210">校验和</span><span class="sxs-lookup"><span data-stu-id="1e104-210">Checksum</span></span>

<span data-ttu-id="1e104-211">不适用</span><span class="sxs-lookup"><span data-stu-id="1e104-211">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e104-212">定义</span><span class="sxs-lookup"><span data-stu-id="1e104-212">Definition</span></span>

<span data-ttu-id="1e104-213">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-213">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-214">正则表达式`Regex_france_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-214">The regular expression  `Regex_france_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e104-215">从关键字`Keywords_france_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1e104-215">A keyword from  `Keywords_france_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="1e104-216">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-217">正则表达式`Regex_france_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-217">The regular expression  `Regex_france_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_france_eu_telephone_number" />
          <Match idRef="Keywords_france_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_france_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="germany"></a><span data-ttu-id="1e104-218">德国</span><span class="sxs-lookup"><span data-stu-id="1e104-218">Germany</span></span>

### <a name="pattern"></a><span data-ttu-id="1e104-219">模式</span><span class="sxs-lookup"><span data-stu-id="1e104-219">Pattern</span></span>

- <span data-ttu-id="1e104-220">数字</span><span class="sxs-lookup"><span data-stu-id="1e104-220">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="1e104-221">校验和</span><span class="sxs-lookup"><span data-stu-id="1e104-221">Checksum</span></span>

<span data-ttu-id="1e104-222">不适用</span><span class="sxs-lookup"><span data-stu-id="1e104-222">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e104-223">定义</span><span class="sxs-lookup"><span data-stu-id="1e104-223">Definition</span></span>

<span data-ttu-id="1e104-224">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-224">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-225">正则表达式`Regex_germany_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-225">The regular expression  `Regex_germany_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e104-226">从关键字`Keywords_germany_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1e104-226">A keyword from  `Keywords_germany_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="1e104-227">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-227">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-228">正则表达式`Regex_germany_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-228">The regular expression  `Regex_germany_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_germany_eu_telephone_number" />
          <Match idRef="Keywords_germany_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_germany_eu_formatted_telephone_number" />
          </Pattern>
        </Entity>
```

## <a name="greece"></a><span data-ttu-id="1e104-229">希腊</span><span class="sxs-lookup"><span data-stu-id="1e104-229">Greece</span></span>

### <a name="pattern"></a><span data-ttu-id="1e104-230">模式</span><span class="sxs-lookup"><span data-stu-id="1e104-230">Pattern</span></span>

- <span data-ttu-id="1e104-231">数字</span><span class="sxs-lookup"><span data-stu-id="1e104-231">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="1e104-232">校验和</span><span class="sxs-lookup"><span data-stu-id="1e104-232">Checksum</span></span>

<span data-ttu-id="1e104-233">不适用</span><span class="sxs-lookup"><span data-stu-id="1e104-233">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e104-234">定义</span><span class="sxs-lookup"><span data-stu-id="1e104-234">Definition</span></span>

<span data-ttu-id="1e104-235">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-235">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-236">正则表达式`Regex_greece_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-236">The regular expression  `Regex_greece_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e104-237">从关键字`Keywords_greece_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1e104-237">A keyword from  `Keywords_greece_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="1e104-238">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-238">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-239">正则表达式`Regex_greece_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-239">The regular expression  `Regex_greece_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_telephone_number" />
          <Match idRef="Keywords_greece_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_greece_eu_formatted_telephone_number" />
          </Pattern>
        </Entity>
```

## <a name="hungary"></a><span data-ttu-id="1e104-240">匈牙利</span><span class="sxs-lookup"><span data-stu-id="1e104-240">Hungary</span></span>

### <a name="pattern"></a><span data-ttu-id="1e104-241">模式</span><span class="sxs-lookup"><span data-stu-id="1e104-241">Pattern</span></span>

- <span data-ttu-id="1e104-242">数字</span><span class="sxs-lookup"><span data-stu-id="1e104-242">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="1e104-243">校验和</span><span class="sxs-lookup"><span data-stu-id="1e104-243">Checksum</span></span>

<span data-ttu-id="1e104-244">不适用</span><span class="sxs-lookup"><span data-stu-id="1e104-244">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e104-245">定义</span><span class="sxs-lookup"><span data-stu-id="1e104-245">Definition</span></span>

<span data-ttu-id="1e104-246">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-246">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-247">正则表达式`Regex_hungary_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-247">The regular expression  `Regex_hungary_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e104-248">从关键字`Keywords_hungary_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1e104-248">A keyword from  `Keywords_hungary_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="1e104-249">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-250">正则表达式`Regex_hungary_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-250">The regular expression  `Regex_hungary_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_telephone_number" />
          <Match idRef="Keywords_hungary_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_hungary_eu_formatted_telephone_number" />
          </Pattern>
       </Entity>
```

## <a name="ireland"></a><span data-ttu-id="1e104-251">Ireland</span><span class="sxs-lookup"><span data-stu-id="1e104-251">Ireland</span></span>

### <a name="pattern"></a><span data-ttu-id="1e104-252">模式</span><span class="sxs-lookup"><span data-stu-id="1e104-252">Pattern</span></span>

- <span data-ttu-id="1e104-253">数字</span><span class="sxs-lookup"><span data-stu-id="1e104-253">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="1e104-254">校验和</span><span class="sxs-lookup"><span data-stu-id="1e104-254">Checksum</span></span>

<span data-ttu-id="1e104-255">不适用</span><span class="sxs-lookup"><span data-stu-id="1e104-255">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e104-256">定义</span><span class="sxs-lookup"><span data-stu-id="1e104-256">Definition</span></span>

<span data-ttu-id="1e104-257">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-257">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-258">正则表达式`Regex_ireland_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-258">The regular expression  `Regex_ireland_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e104-259">从关键字`Keywords_ireland_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1e104-259">A keyword from  `Keywords_ireland_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="1e104-260">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-260">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-261">正则表达式`Regex_ireland_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-261">The regular expression  `Regex_ireland_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_telephone_number" />
          <Match idRef="Keywords_ireland_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_ireland_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="italy"></a><span data-ttu-id="1e104-262">意大利</span><span class="sxs-lookup"><span data-stu-id="1e104-262">Italy</span></span>

### <a name="pattern"></a><span data-ttu-id="1e104-263">模式</span><span class="sxs-lookup"><span data-stu-id="1e104-263">Pattern</span></span>

- <span data-ttu-id="1e104-264">数字</span><span class="sxs-lookup"><span data-stu-id="1e104-264">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="1e104-265">校验和</span><span class="sxs-lookup"><span data-stu-id="1e104-265">Checksum</span></span>

<span data-ttu-id="1e104-266">不适用</span><span class="sxs-lookup"><span data-stu-id="1e104-266">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e104-267">定义</span><span class="sxs-lookup"><span data-stu-id="1e104-267">Definition</span></span>

<span data-ttu-id="1e104-268">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-268">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-269">正则表达式`Regex_italy_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-269">The regular expression  `Regex_italy_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e104-270">从关键字`Keywords_italy_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1e104-270">A keyword from  `Keywords_italy_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="1e104-271">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-271">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-272">正则表达式`Regex_italy_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-272">The regular expression  `Regex_italy_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_telephone_number" />
          <Match idRef="Keywords_italy_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_italy_eu_formatted_telephone_number" />
          </Pattern>
         </Entity>
```

## <a name="latvia"></a><span data-ttu-id="1e104-273">拉脱维亚</span><span class="sxs-lookup"><span data-stu-id="1e104-273">Latvia</span></span>

### <a name="pattern"></a><span data-ttu-id="1e104-274">模式</span><span class="sxs-lookup"><span data-stu-id="1e104-274">Pattern</span></span>

- <span data-ttu-id="1e104-275">数字</span><span class="sxs-lookup"><span data-stu-id="1e104-275">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="1e104-276">校验和</span><span class="sxs-lookup"><span data-stu-id="1e104-276">Checksum</span></span>

<span data-ttu-id="1e104-277">不适用</span><span class="sxs-lookup"><span data-stu-id="1e104-277">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e104-278">定义</span><span class="sxs-lookup"><span data-stu-id="1e104-278">Definition</span></span>

<span data-ttu-id="1e104-279">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-279">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-280">正则表达式`Regex_latvia_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-280">The regular expression  `Regex_latvia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e104-281">从关键字`Keywords_latvia_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1e104-281">A keyword from  `Keywords_latvia_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="1e104-282">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-283">正则表达式`Regex_latvia_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-283">The regular expression  `Regex_latvia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_telephone_number" />
          <Match idRef="Keywords_latvia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_latvia_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="lithuania"></a><span data-ttu-id="1e104-284">立陶宛</span><span class="sxs-lookup"><span data-stu-id="1e104-284">Lithuania</span></span>

### <a name="pattern"></a><span data-ttu-id="1e104-285">模式</span><span class="sxs-lookup"><span data-stu-id="1e104-285">Pattern</span></span>

- <span data-ttu-id="1e104-286">数字</span><span class="sxs-lookup"><span data-stu-id="1e104-286">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="1e104-287">校验和</span><span class="sxs-lookup"><span data-stu-id="1e104-287">Checksum</span></span>

<span data-ttu-id="1e104-288">不适用</span><span class="sxs-lookup"><span data-stu-id="1e104-288">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e104-289">定义</span><span class="sxs-lookup"><span data-stu-id="1e104-289">Definition</span></span>

<span data-ttu-id="1e104-290">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-291">正则表达式`Regex_lithuania_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-291">The regular expression  `Regex_lithuania_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e104-292">从关键字`Keywords_lithuania_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1e104-292">A keyword from  `Keywords_lithuania_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="1e104-293">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-293">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-294">正则表达式`Regex_lithuania_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-294">The regular expression  `Regex_lithuania_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_telephone_number" />
          <Match idRef="Keywords_lithuania_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_lithuania_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="luxemburg"></a><span data-ttu-id="1e104-295">卢森堡</span><span class="sxs-lookup"><span data-stu-id="1e104-295">Luxemburg</span></span>

### <a name="pattern"></a><span data-ttu-id="1e104-296">模式</span><span class="sxs-lookup"><span data-stu-id="1e104-296">Pattern</span></span>

- <span data-ttu-id="1e104-297">数字</span><span class="sxs-lookup"><span data-stu-id="1e104-297">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="1e104-298">校验和</span><span class="sxs-lookup"><span data-stu-id="1e104-298">Checksum</span></span>

<span data-ttu-id="1e104-299">不适用</span><span class="sxs-lookup"><span data-stu-id="1e104-299">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e104-300">定义</span><span class="sxs-lookup"><span data-stu-id="1e104-300">Definition</span></span>

<span data-ttu-id="1e104-301">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-301">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-302">正则表达式`Regex_luxemburg_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-302">The regular expression  `Regex_luxemburg_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e104-303">从关键字`Keywords_luxemburg_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1e104-303">A keyword from  `Keywords_luxemburg_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="1e104-304">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-304">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-305">正则表达式`Regex_luxemburg_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-305">The regular expression  `Regex_luxemburg_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_telephone_number" />
          <Match idRef="Keywords_luxemburg_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_luxemburg_eu_formatted_telephone_number" />
                  </Pattern>
</Entity>
```

## <a name="malta"></a><span data-ttu-id="1e104-306">马耳他</span><span class="sxs-lookup"><span data-stu-id="1e104-306">Malta</span></span>

### <a name="pattern"></a><span data-ttu-id="1e104-307">模式</span><span class="sxs-lookup"><span data-stu-id="1e104-307">Pattern</span></span>

- <span data-ttu-id="1e104-308">数字</span><span class="sxs-lookup"><span data-stu-id="1e104-308">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="1e104-309">校验和</span><span class="sxs-lookup"><span data-stu-id="1e104-309">Checksum</span></span>

<span data-ttu-id="1e104-310">不适用</span><span class="sxs-lookup"><span data-stu-id="1e104-310">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e104-311">定义</span><span class="sxs-lookup"><span data-stu-id="1e104-311">Definition</span></span>

<span data-ttu-id="1e104-312">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-313">正则表达式`Regex_malta_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-313">The regular expression  `Regex_malta_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e104-314">从关键字`Keywords_malta_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1e104-314">A keyword from  `Keywords_malta_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="1e104-315">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-315">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-316">正则表达式`Regex_malta_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-316">The regular expression  `Regex_malta_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_telephone_number" />
          <Match idRef="Keywords_malta_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_malta_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="netherlands"></a><span data-ttu-id="1e104-317">荷兰</span><span class="sxs-lookup"><span data-stu-id="1e104-317">Netherlands</span></span>

### <a name="pattern"></a><span data-ttu-id="1e104-318">模式</span><span class="sxs-lookup"><span data-stu-id="1e104-318">Pattern</span></span>

- <span data-ttu-id="1e104-319">数字</span><span class="sxs-lookup"><span data-stu-id="1e104-319">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="1e104-320">校验和</span><span class="sxs-lookup"><span data-stu-id="1e104-320">Checksum</span></span>

<span data-ttu-id="1e104-321">不适用</span><span class="sxs-lookup"><span data-stu-id="1e104-321">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e104-322">定义</span><span class="sxs-lookup"><span data-stu-id="1e104-322">Definition</span></span>

<span data-ttu-id="1e104-323">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-323">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-324">正则表达式`Regex_netherlands_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-324">The regular expression  `Regex_netherlands_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e104-325">从关键字`Keywords_netherlands_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1e104-325">A keyword from  `Keywords_netherlands_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="1e104-326">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-327">正则表达式`Regex_netherlands_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-327">The regular expression  `Regex_netherlands_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_telephone_number" />
          <Match idRef="Keywords_netherlands_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_netherlands_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="poland"></a><span data-ttu-id="1e104-328">波兰</span><span class="sxs-lookup"><span data-stu-id="1e104-328">Poland</span></span>

### <a name="pattern"></a><span data-ttu-id="1e104-329">模式</span><span class="sxs-lookup"><span data-stu-id="1e104-329">Pattern</span></span>

- <span data-ttu-id="1e104-330">数字</span><span class="sxs-lookup"><span data-stu-id="1e104-330">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="1e104-331">校验和</span><span class="sxs-lookup"><span data-stu-id="1e104-331">Checksum</span></span>

<span data-ttu-id="1e104-332">不适用</span><span class="sxs-lookup"><span data-stu-id="1e104-332">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e104-333">定义</span><span class="sxs-lookup"><span data-stu-id="1e104-333">Definition</span></span>

<span data-ttu-id="1e104-334">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-334">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-335">正则表达式`Regex_poland_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-335">The regular expression  `Regex_poland_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e104-336">从关键字`Keywords_poland_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1e104-336">A keyword from  `Keywords_poland_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="1e104-337">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-337">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-338">正则表达式`Regex_poland_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-338">The regular expression  `Regex_poland_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_telephone_number" />
          <Match idRef="Keywords_poland_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_poland_eu_formatted_telephone_number" />
             </Pattern>
</Entity>
```

## <a name="portugal"></a><span data-ttu-id="1e104-339">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="1e104-339">Portugal</span></span>

### <a name="pattern"></a><span data-ttu-id="1e104-340">模式</span><span class="sxs-lookup"><span data-stu-id="1e104-340">Pattern</span></span>

- <span data-ttu-id="1e104-341">数字</span><span class="sxs-lookup"><span data-stu-id="1e104-341">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="1e104-342">校验和</span><span class="sxs-lookup"><span data-stu-id="1e104-342">Checksum</span></span>

<span data-ttu-id="1e104-343">不适用</span><span class="sxs-lookup"><span data-stu-id="1e104-343">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e104-344">定义</span><span class="sxs-lookup"><span data-stu-id="1e104-344">Definition</span></span>

<span data-ttu-id="1e104-345">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-345">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-346">正则表达式`Regex_portugal_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-346">The regular expression  `Regex_portugal_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e104-347">从关键字`Keywords_portugal_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1e104-347">A keyword from  `Keywords_portugal_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="1e104-348">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-348">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-349">正则表达式`Regex_portugal_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-349">The regular expression  `Regex_portugal_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_telephone_number" />
          <Match idRef="Keywords_portugal_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_portugal_eu_formatted_telephone_number" />
          </Pattern>
        </Entity>
```

## <a name="romania"></a><span data-ttu-id="1e104-350">罗马尼亚</span><span class="sxs-lookup"><span data-stu-id="1e104-350">Romania</span></span>

### <a name="pattern"></a><span data-ttu-id="1e104-351">模式</span><span class="sxs-lookup"><span data-stu-id="1e104-351">Pattern</span></span>

- <span data-ttu-id="1e104-352">数字</span><span class="sxs-lookup"><span data-stu-id="1e104-352">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="1e104-353">校验和</span><span class="sxs-lookup"><span data-stu-id="1e104-353">Checksum</span></span>

<span data-ttu-id="1e104-354">不适用</span><span class="sxs-lookup"><span data-stu-id="1e104-354">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e104-355">定义</span><span class="sxs-lookup"><span data-stu-id="1e104-355">Definition</span></span>

<span data-ttu-id="1e104-356">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-356">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-357">正则表达式`Regex_romania_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-357">The regular expression  `Regex_romania_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e104-358">从关键字`Keywords_romania_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1e104-358">A keyword from  `Keywords_romania_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="1e104-359">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-359">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-360">正则表达式`Regex_romania_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-360">The regular expression  `Regex_romania_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_telephone_number" />
          <Match idRef="Keywords_romania_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_romania_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="slovakia"></a><span data-ttu-id="1e104-361">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="1e104-361">Slovakia</span></span>

### <a name="pattern"></a><span data-ttu-id="1e104-362">模式</span><span class="sxs-lookup"><span data-stu-id="1e104-362">Pattern</span></span>

- <span data-ttu-id="1e104-363">数字</span><span class="sxs-lookup"><span data-stu-id="1e104-363">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="1e104-364">校验和</span><span class="sxs-lookup"><span data-stu-id="1e104-364">Checksum</span></span>

<span data-ttu-id="1e104-365">不适用</span><span class="sxs-lookup"><span data-stu-id="1e104-365">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e104-366">定义</span><span class="sxs-lookup"><span data-stu-id="1e104-366">Definition</span></span>

<span data-ttu-id="1e104-367">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-367">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-368">正则表达式`Regex_slovakia_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-368">The regular expression  `Regex_slovakia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e104-369">从关键字`Keywords_slovakia_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1e104-369">A keyword from  `Keywords_slovakia_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="1e104-370">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-370">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-371">正则表达式`Regex_slovakia_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-371">The regular expression  `Regex_slovakia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_telephone_number" />
          <Match idRef="Keywords_slovakia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_slovakia_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="slovenia"></a><span data-ttu-id="1e104-372">斯诺文尼亚</span><span class="sxs-lookup"><span data-stu-id="1e104-372">Slovenia</span></span>

### <a name="pattern"></a><span data-ttu-id="1e104-373">模式</span><span class="sxs-lookup"><span data-stu-id="1e104-373">Pattern</span></span>

- <span data-ttu-id="1e104-374">数字</span><span class="sxs-lookup"><span data-stu-id="1e104-374">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="1e104-375">校验和</span><span class="sxs-lookup"><span data-stu-id="1e104-375">Checksum</span></span>

<span data-ttu-id="1e104-376">不适用</span><span class="sxs-lookup"><span data-stu-id="1e104-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e104-377">定义</span><span class="sxs-lookup"><span data-stu-id="1e104-377">Definition</span></span>

<span data-ttu-id="1e104-378">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-379">正则表达式`Regex_slovenia_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-379">The regular expression  `Regex_slovenia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e104-380">从关键字`Keywords_slovenia_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1e104-380">A keyword from  `Keywords_slovenia_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="1e104-381">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-382">正则表达式`Regex_slovenia_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-382">The regular expression  `Regex_slovenia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_telephone_number" />
          <Match idRef="Keywords_slovenia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_slovenia_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="spain"></a><span data-ttu-id="1e104-383">西班牙</span><span class="sxs-lookup"><span data-stu-id="1e104-383">Spain</span></span>

### <a name="pattern"></a><span data-ttu-id="1e104-384">模式</span><span class="sxs-lookup"><span data-stu-id="1e104-384">Pattern</span></span>

- <span data-ttu-id="1e104-385">数字</span><span class="sxs-lookup"><span data-stu-id="1e104-385">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="1e104-386">校验和</span><span class="sxs-lookup"><span data-stu-id="1e104-386">Checksum</span></span>

<span data-ttu-id="1e104-387">不适用</span><span class="sxs-lookup"><span data-stu-id="1e104-387">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e104-388">定义</span><span class="sxs-lookup"><span data-stu-id="1e104-388">Definition</span></span>

<span data-ttu-id="1e104-389">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-389">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-390">正则表达式`Regex_spain_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-390">The regular expression  `Regex_spain_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e104-391">从关键字`Keywords_spain_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1e104-391">A keyword from  `Keywords_spain_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="1e104-392">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-392">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-393">正则表达式`Regex_spain_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-393">The regular expression  `Regex_spain_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_telephone_number" />
          <Match idRef="Keywords_spain_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_spain_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="sweden"></a><span data-ttu-id="1e104-394">瑞典</span><span class="sxs-lookup"><span data-stu-id="1e104-394">Sweden</span></span>

### <a name="pattern"></a><span data-ttu-id="1e104-395">模式</span><span class="sxs-lookup"><span data-stu-id="1e104-395">Pattern</span></span>

- <span data-ttu-id="1e104-396">数字</span><span class="sxs-lookup"><span data-stu-id="1e104-396">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="1e104-397">校验和</span><span class="sxs-lookup"><span data-stu-id="1e104-397">Checksum</span></span>

<span data-ttu-id="1e104-398">不适用</span><span class="sxs-lookup"><span data-stu-id="1e104-398">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e104-399">定义</span><span class="sxs-lookup"><span data-stu-id="1e104-399">Definition</span></span>

<span data-ttu-id="1e104-400">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-400">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-401">正则表达式`Regex_sweden_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-401">The regular expression  `Regex_sweden_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e104-402">从关键字`Keywords_sweden_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1e104-402">A keyword from  `Keywords_sweden_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="1e104-403">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-403">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-404">正则表达式`Regex_sweden_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-404">The regular expression  `Regex_sweden_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_telephone_number" />
          <Match idRef="Keywords_sweden_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_sweden_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="uk"></a><span data-ttu-id="1e104-405">英国</span><span class="sxs-lookup"><span data-stu-id="1e104-405">UK</span></span>

### <a name="pattern"></a><span data-ttu-id="1e104-406">模式</span><span class="sxs-lookup"><span data-stu-id="1e104-406">Pattern</span></span>

- <span data-ttu-id="1e104-407">数字</span><span class="sxs-lookup"><span data-stu-id="1e104-407">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="1e104-408">校验和</span><span class="sxs-lookup"><span data-stu-id="1e104-408">Checksum</span></span>

<span data-ttu-id="1e104-409">不适用</span><span class="sxs-lookup"><span data-stu-id="1e104-409">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e104-410">定义</span><span class="sxs-lookup"><span data-stu-id="1e104-410">Definition</span></span>

<span data-ttu-id="1e104-411">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-412">正则表达式`Regex_uk_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-412">The regular expression  `Regex_uk_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e104-413">从关键字`Keywords_uk_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1e104-413">A keyword from  `Keywords_uk_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="1e104-414">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="1e104-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e104-415">正则表达式`Regex_uk_eu_telephone_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="1e104-415">The regular expression  `Regex_uk_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_uk_eu_telephone_number" />
          <Match idRef="Keywords_uk_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_uk_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="see-also"></a><span data-ttu-id="1e104-416">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1e104-416">See also</span></span>

[<span data-ttu-id="1e104-417">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="1e104-417">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

