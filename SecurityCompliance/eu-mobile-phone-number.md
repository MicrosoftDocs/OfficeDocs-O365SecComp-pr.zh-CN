---
title: 欧盟移动电话号码
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 555e7675-2ae8-42d1-9b8e-2c8f8cd21337
description: Office 365 安全性的数据丢失防护 (DLP)&amp;合规性中心包括许多可供您可以使用 DLP 策略中的敏感信息类型。本主题介绍欧盟移动电话号码敏感信息类型。
ms.openlocfilehash: d0818759dae8ed86cc9aef6f7fad48cbd2acf24f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525309"
---
# <a name="eu-mobile-phone-number"></a><span data-ttu-id="c3268-104">欧盟移动电话号码</span><span class="sxs-lookup"><span data-stu-id="c3268-104">EU Mobile Phone Number</span></span>

<span data-ttu-id="c3268-p102">Office 365 安全性的数据丢失防护 (DLP)&amp;合规性中心包括许多可供您可以使用 DLP 策略中的敏感信息类型。本主题介绍欧盟移动电话号码敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="c3268-p102">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies. This topic describes the EU Mobile Phone Number sensitive information type.</span></span> 
  
## <a name="austria"></a><span data-ttu-id="c3268-107">奥地利</span><span class="sxs-lookup"><span data-stu-id="c3268-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="c3268-108">格式</span><span class="sxs-lookup"><span data-stu-id="c3268-108">Format</span></span>

<span data-ttu-id="c3268-109">没有标准长度的数字</span><span class="sxs-lookup"><span data-stu-id="c3268-109">Digits without standard lengths</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c3268-110">模式</span><span class="sxs-lookup"><span data-stu-id="c3268-110">Pattern</span></span>

-  <span data-ttu-id="c3268-111">数字</span><span class="sxs-lookup"><span data-stu-id="c3268-111">Digits</span></span> 
    
### <a name="definition"></a><span data-ttu-id="c3268-112">定义</span><span class="sxs-lookup"><span data-stu-id="c3268-112">Definition</span></span>

<span data-ttu-id="c3268-113">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c3268-113">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c3268-114">正则表达式`Regex_austria_eu_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-114">The regular expression  `Regex_austria_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-115">正则表达式`Regex_austria_eu_formatted_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-115">The regular expression  `Regex_austria_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-116">从关键字`Keywords_austria_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c3268-116">A keyword from  `Keywords_austria_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_mobile_number"/>
          <Match idRef="Keywords_austria_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_austria_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="belgium"></a><span data-ttu-id="c3268-117">比利时</span><span class="sxs-lookup"><span data-stu-id="c3268-117">Belgium</span></span>

### <a name="pattern"></a><span data-ttu-id="c3268-118">模式</span><span class="sxs-lookup"><span data-stu-id="c3268-118">Pattern</span></span>

-  <span data-ttu-id="c3268-119">数字</span><span class="sxs-lookup"><span data-stu-id="c3268-119">Digits</span></span> 
    
### <a name="definition"></a><span data-ttu-id="c3268-120">定义</span><span class="sxs-lookup"><span data-stu-id="c3268-120">Definition</span></span>

<span data-ttu-id="c3268-121">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c3268-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c3268-122">正则表达式`Regex_belgium_eu_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-122">The regular expression  `Regex_belgium_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-123">正则表达式`Regex_belgium_eu_formatted_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-123">The regular expression  `Regex_belgium_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-124">从关键字`Keywords_belgium_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c3268-124">A keyword from  `Keywords_belgium_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_mobile_number"/>
          <Match idRef="Keywords_belgium_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_belgium_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="bulgaria"></a><span data-ttu-id="c3268-125">保加利亚</span><span class="sxs-lookup"><span data-stu-id="c3268-125">Bulgaria</span></span>

### <a name="pattern"></a><span data-ttu-id="c3268-126">模式</span><span class="sxs-lookup"><span data-stu-id="c3268-126">Pattern</span></span>

-  <span data-ttu-id="c3268-127">数字</span><span class="sxs-lookup"><span data-stu-id="c3268-127">Digits</span></span> 
    
### <a name="definition"></a><span data-ttu-id="c3268-128">定义</span><span class="sxs-lookup"><span data-stu-id="c3268-128">Definition</span></span>

<span data-ttu-id="c3268-129">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c3268-129">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c3268-130">正则表达式`Regex_bulgaria_eu_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-130">The regular expression  `Regex_bulgaria_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-131">正则表达式`Regex_bulgaria_eu_formatted_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-131">The regular expression  `Regex_bulgaria_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-132">从关键字`Keywords_bulgaria_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c3268-132">A keyword from  `Keywords_bulgaria_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_mobile_number"/>
          <Match idRef="Keywords_bulgaria_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_bulgaria_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="croatia"></a><span data-ttu-id="c3268-133">克罗地亚</span><span class="sxs-lookup"><span data-stu-id="c3268-133">Croatia</span></span>

### <a name="pattern"></a><span data-ttu-id="c3268-134">模式</span><span class="sxs-lookup"><span data-stu-id="c3268-134">Pattern</span></span>

-  <span data-ttu-id="c3268-135">数字</span><span class="sxs-lookup"><span data-stu-id="c3268-135">Digits</span></span> 
    
### <a name="definition"></a><span data-ttu-id="c3268-136">定义</span><span class="sxs-lookup"><span data-stu-id="c3268-136">Definition</span></span>

<span data-ttu-id="c3268-137">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c3268-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c3268-138">正则表达式`Regex_croatia_eu_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-138">The regular expression  `Regex_croatia_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-139">正则表达式`Regex_croatia_eu_formatted_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-139">The regular expression  `Regex_croatia_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-140">从关键字`Keywords_croatia_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c3268-140">A keyword from  `Keywords_croatia_eu_mobile_number` is found.</span></span> 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_mobile_number"/>
          <Match idRef="Keywords_croatia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_croatia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="cyprus"></a><span data-ttu-id="c3268-141">塞浦路斯</span><span class="sxs-lookup"><span data-stu-id="c3268-141">Cyprus</span></span>

### <a name="pattern"></a><span data-ttu-id="c3268-142">模式</span><span class="sxs-lookup"><span data-stu-id="c3268-142">Pattern</span></span>

-  <span data-ttu-id="c3268-143">数字</span><span class="sxs-lookup"><span data-stu-id="c3268-143">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c3268-144">校验和</span><span class="sxs-lookup"><span data-stu-id="c3268-144">Checksum</span></span>

<span data-ttu-id="c3268-145">不适用</span><span class="sxs-lookup"><span data-stu-id="c3268-145">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c3268-146">定义</span><span class="sxs-lookup"><span data-stu-id="c3268-146">Definition</span></span>

<span data-ttu-id="c3268-147">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c3268-147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c3268-148">正则表达式`Regex_cyprus_eu_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-148">The regular expression  `Regex_cyprus_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-149">正则表达式`Regex_cyprus_eu_formatted_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-149">The regular expression  `Regex_cyprus_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-150">从关键字`Keywords_cyprus_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c3268-150">A keyword from  `Keywords_cyprus_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_mobile_number"/>
          <Match idRef="Keywords_cyprus_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_cyprus_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="czech-republic"></a><span data-ttu-id="c3268-151">捷克共和国</span><span class="sxs-lookup"><span data-stu-id="c3268-151">Czech Republic</span></span>

### <a name="pattern"></a><span data-ttu-id="c3268-152">模式</span><span class="sxs-lookup"><span data-stu-id="c3268-152">Pattern</span></span>

-  <span data-ttu-id="c3268-153">数字</span><span class="sxs-lookup"><span data-stu-id="c3268-153">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c3268-154">校验和</span><span class="sxs-lookup"><span data-stu-id="c3268-154">Checksum</span></span>

<span data-ttu-id="c3268-155">不适用</span><span class="sxs-lookup"><span data-stu-id="c3268-155">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c3268-156">定义</span><span class="sxs-lookup"><span data-stu-id="c3268-156">Definition</span></span>

<span data-ttu-id="c3268-157">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c3268-157">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c3268-158">正则表达式`Regex_czech_republic_eu_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-158">The regular expression  `Regex_czech_republic_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-159">正则表达式`Regex_czech_republic_eu_formatted_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-159">The regular expression  `Regex_czech_republic_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-160">从关键字`Keywords_czech_republic_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c3268-160">A keyword from  `Keywords_czech_republic_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_mobile_number"/>
          <Match idRef="Keywords_czech_republic_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_czech_republic_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="denmark"></a><span data-ttu-id="c3268-161">丹麦</span><span class="sxs-lookup"><span data-stu-id="c3268-161">Denmark</span></span>

### <a name="pattern"></a><span data-ttu-id="c3268-162">模式</span><span class="sxs-lookup"><span data-stu-id="c3268-162">Pattern</span></span>

-  <span data-ttu-id="c3268-163">数字</span><span class="sxs-lookup"><span data-stu-id="c3268-163">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c3268-164">校验和</span><span class="sxs-lookup"><span data-stu-id="c3268-164">Checksum</span></span>

<span data-ttu-id="c3268-165">不适用</span><span class="sxs-lookup"><span data-stu-id="c3268-165">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c3268-166">定义</span><span class="sxs-lookup"><span data-stu-id="c3268-166">Definition</span></span>

<span data-ttu-id="c3268-167">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c3268-167">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c3268-168">正则表达式`Regex_denmark_eu_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-168">The regular expression  `Regex_denmark_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-169">正则表达式`Regex_denmark_eu_formatted_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-169">The regular expression  `Regex_denmark_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-170">从关键字`Keywords_denmark_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c3268-170">A keyword from  `Keywords_denmark_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_mobile_number"/>
          <Match idRef="Keywords_denmark_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_denmark_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="estonia"></a><span data-ttu-id="c3268-171">爱沙尼亚</span><span class="sxs-lookup"><span data-stu-id="c3268-171">Estonia</span></span>

### <a name="pattern"></a><span data-ttu-id="c3268-172">模式</span><span class="sxs-lookup"><span data-stu-id="c3268-172">Pattern</span></span>

-  <span data-ttu-id="c3268-173">数字</span><span class="sxs-lookup"><span data-stu-id="c3268-173">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c3268-174">校验和</span><span class="sxs-lookup"><span data-stu-id="c3268-174">Checksum</span></span>

<span data-ttu-id="c3268-175">不适用</span><span class="sxs-lookup"><span data-stu-id="c3268-175">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c3268-176">定义</span><span class="sxs-lookup"><span data-stu-id="c3268-176">Definition</span></span>

<span data-ttu-id="c3268-177">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c3268-177">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c3268-178">正则表达式`Regex_estonia_eu_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-178">The regular expression  `Regex_estonia_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-179">正则表达式`Regex_estonia_eu_formatted_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-179">The regular expression  `Regex_estonia_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-180">从关键字`Keywords_estonia_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c3268-180">A keyword from  `Keywords_estonia_eu_mobile_number` is found.</span></span> 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_mobile_number"/>
          <Match idRef="Keywords_estonia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_estonia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="finland"></a><span data-ttu-id="c3268-181">芬兰</span><span class="sxs-lookup"><span data-stu-id="c3268-181">Finland</span></span>

### <a name="pattern"></a><span data-ttu-id="c3268-182">模式</span><span class="sxs-lookup"><span data-stu-id="c3268-182">Pattern</span></span>

-  <span data-ttu-id="c3268-183">数字</span><span class="sxs-lookup"><span data-stu-id="c3268-183">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c3268-184">校验和</span><span class="sxs-lookup"><span data-stu-id="c3268-184">Checksum</span></span>

<span data-ttu-id="c3268-185">不适用</span><span class="sxs-lookup"><span data-stu-id="c3268-185">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c3268-186">定义</span><span class="sxs-lookup"><span data-stu-id="c3268-186">Definition</span></span>

<span data-ttu-id="c3268-187">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c3268-187">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c3268-188">正则表达式`Regex_finland_eu_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-188">The regular expression  `Regex_finland_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-189">正则表达式`Regex_finland_eu_formatted_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-189">The regular expression  `Regex_finland_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-190">从关键字`Keywords_finland_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c3268-190">A keyword from  `Keywords_finland_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_mobile_number"/>
          <Match idRef="Keywords_finland_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_finland_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="france"></a><span data-ttu-id="c3268-191">法国</span><span class="sxs-lookup"><span data-stu-id="c3268-191">France</span></span>

### <a name="pattern"></a><span data-ttu-id="c3268-192">模式</span><span class="sxs-lookup"><span data-stu-id="c3268-192">Pattern</span></span>

-  <span data-ttu-id="c3268-193">数字</span><span class="sxs-lookup"><span data-stu-id="c3268-193">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c3268-194">校验和</span><span class="sxs-lookup"><span data-stu-id="c3268-194">Checksum</span></span>

<span data-ttu-id="c3268-195">不适用</span><span class="sxs-lookup"><span data-stu-id="c3268-195">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c3268-196">定义</span><span class="sxs-lookup"><span data-stu-id="c3268-196">Definition</span></span>

<span data-ttu-id="c3268-197">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c3268-197">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c3268-198">正则表达式`Regex_france_eu_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-198">The regular expression  `Regex_france_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-199">正则表达式`Regex_france_eu_formatted_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-199">The regular expression  `Regex_france_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-200">从关键字`Keywords_france_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c3268-200">A keyword from  `Keywords_france_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_france_eu_mobile_number"/>
          <Match idRef="Keywords_france_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_france_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="germany"></a><span data-ttu-id="c3268-201">德国</span><span class="sxs-lookup"><span data-stu-id="c3268-201">Germany</span></span>

### <a name="pattern"></a><span data-ttu-id="c3268-202">模式</span><span class="sxs-lookup"><span data-stu-id="c3268-202">Pattern</span></span>

-  <span data-ttu-id="c3268-203">数字</span><span class="sxs-lookup"><span data-stu-id="c3268-203">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c3268-204">校验和</span><span class="sxs-lookup"><span data-stu-id="c3268-204">Checksum</span></span>

<span data-ttu-id="c3268-205">不适用</span><span class="sxs-lookup"><span data-stu-id="c3268-205">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c3268-206">定义</span><span class="sxs-lookup"><span data-stu-id="c3268-206">Definition</span></span>

<span data-ttu-id="c3268-207">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c3268-207">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c3268-208">正则表达式`Regex_germany_eu_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-208">The regular expression  `Regex_germany_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-209">正则表达式`Regex_germany_eu_formatted_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-209">The regular expression  `Regex_germany_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-210">从关键字`Keywords_germany_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c3268-210">A keyword from  `Keywords_germany_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_germany_eu_mobile_number"/>
          <Match idRef="Keywords_germany_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_germany_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="greece"></a><span data-ttu-id="c3268-211">希腊</span><span class="sxs-lookup"><span data-stu-id="c3268-211">Greece</span></span>

### <a name="pattern"></a><span data-ttu-id="c3268-212">模式</span><span class="sxs-lookup"><span data-stu-id="c3268-212">Pattern</span></span>

-  <span data-ttu-id="c3268-213">数字</span><span class="sxs-lookup"><span data-stu-id="c3268-213">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c3268-214">校验和</span><span class="sxs-lookup"><span data-stu-id="c3268-214">Checksum</span></span>

<span data-ttu-id="c3268-215">不适用</span><span class="sxs-lookup"><span data-stu-id="c3268-215">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c3268-216">定义</span><span class="sxs-lookup"><span data-stu-id="c3268-216">Definition</span></span>

<span data-ttu-id="c3268-217">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c3268-217">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c3268-218">正则表达式`Regex_greece_eu_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-218">The regular expression  `Regex_greece_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-219">正则表达式`Regex_greece_eu_formatted_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-219">The regular expression  `Regex_greece_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-220">从关键字`Keywords_greece_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c3268-220">A keyword from  `Keywords_greece_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_mobile_number"/>
          <Match idRef="Keywords_greece_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_greece_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="hungary"></a><span data-ttu-id="c3268-221">匈牙利</span><span class="sxs-lookup"><span data-stu-id="c3268-221">Hungary</span></span>

### <a name="pattern"></a><span data-ttu-id="c3268-222">模式</span><span class="sxs-lookup"><span data-stu-id="c3268-222">Pattern</span></span>

-  <span data-ttu-id="c3268-223">数字</span><span class="sxs-lookup"><span data-stu-id="c3268-223">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c3268-224">校验和</span><span class="sxs-lookup"><span data-stu-id="c3268-224">Checksum</span></span>

<span data-ttu-id="c3268-225">不适用</span><span class="sxs-lookup"><span data-stu-id="c3268-225">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c3268-226">定义</span><span class="sxs-lookup"><span data-stu-id="c3268-226">Definition</span></span>

<span data-ttu-id="c3268-227">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c3268-227">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c3268-228">正则表达式`Regex_hungary_eu_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-228">The regular expression  `Regex_hungary_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-229">正则表达式`Regex_hungary_eu_formatted_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-229">The regular expression  `Regex_hungary_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-230">从关键字`Keywords_hungary_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c3268-230">A keyword from  `Keywords_hungary_eu_mobile_number` is found.</span></span> 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_mobile_number"/>
          <Match idRef="Keywords_hungary_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_hungary_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="ireland"></a><span data-ttu-id="c3268-231">Ireland</span><span class="sxs-lookup"><span data-stu-id="c3268-231">Ireland</span></span>

### <a name="pattern"></a><span data-ttu-id="c3268-232">模式</span><span class="sxs-lookup"><span data-stu-id="c3268-232">Pattern</span></span>

-  <span data-ttu-id="c3268-233">数字</span><span class="sxs-lookup"><span data-stu-id="c3268-233">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c3268-234">校验和</span><span class="sxs-lookup"><span data-stu-id="c3268-234">Checksum</span></span>

<span data-ttu-id="c3268-235">不适用</span><span class="sxs-lookup"><span data-stu-id="c3268-235">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c3268-236">定义</span><span class="sxs-lookup"><span data-stu-id="c3268-236">Definition</span></span>

<span data-ttu-id="c3268-237">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c3268-237">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c3268-238">正则表达式`Regex_ireland_eu_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-238">The regular expression  `Regex_ireland_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-239">正则表达式`Regex_ireland_eu_formatted_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-239">The regular expression  `Regex_ireland_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-240">从关键字`Keywords_ireland_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c3268-240">A keyword from  `Keywords_ireland_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_mobile_number"/>
          <Match idRef="Keywords_ireland_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_ireland_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="italy"></a><span data-ttu-id="c3268-241">意大利</span><span class="sxs-lookup"><span data-stu-id="c3268-241">Italy</span></span>

### <a name="pattern"></a><span data-ttu-id="c3268-242">模式</span><span class="sxs-lookup"><span data-stu-id="c3268-242">Pattern</span></span>

-  <span data-ttu-id="c3268-243">数字</span><span class="sxs-lookup"><span data-stu-id="c3268-243">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c3268-244">校验和</span><span class="sxs-lookup"><span data-stu-id="c3268-244">Checksum</span></span>

<span data-ttu-id="c3268-245">不适用</span><span class="sxs-lookup"><span data-stu-id="c3268-245">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c3268-246">定义</span><span class="sxs-lookup"><span data-stu-id="c3268-246">Definition</span></span>

<span data-ttu-id="c3268-247">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c3268-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c3268-248">正则表达式`Regex_italy_eu_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-248">The regular expression  `Regex_italy_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-249">正则表达式`Regex_italy_eu_formatted_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-249">The regular expression  `Regex_italy_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-250">从关键字`Keywords_italy_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c3268-250">A keyword from  `Keywords_italy_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_mobile_number"/>
          <Match idRef="Keywords_italy_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_italy_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="latvia"></a><span data-ttu-id="c3268-251">拉脱维亚</span><span class="sxs-lookup"><span data-stu-id="c3268-251">Latvia</span></span>

### <a name="pattern"></a><span data-ttu-id="c3268-252">模式</span><span class="sxs-lookup"><span data-stu-id="c3268-252">Pattern</span></span>

-  <span data-ttu-id="c3268-253">数字</span><span class="sxs-lookup"><span data-stu-id="c3268-253">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c3268-254">校验和</span><span class="sxs-lookup"><span data-stu-id="c3268-254">Checksum</span></span>

<span data-ttu-id="c3268-255">不适用</span><span class="sxs-lookup"><span data-stu-id="c3268-255">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c3268-256">定义</span><span class="sxs-lookup"><span data-stu-id="c3268-256">Definition</span></span>

<span data-ttu-id="c3268-257">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c3268-257">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c3268-258">正则表达式`Regex_latvia_eu_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-258">The regular expression  `Regex_latvia_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-259">正则表达式`Regex_latvia_eu_formatted_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-259">The regular expression  `Regex_latvia_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-260">从关键字`Keywords_latvia_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c3268-260">A keyword from  `Keywords_latvia_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_mobile_number"/>
          <Match idRef="Keywords_latvia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_latvia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="lithuania"></a><span data-ttu-id="c3268-261">立陶宛</span><span class="sxs-lookup"><span data-stu-id="c3268-261">Lithuania</span></span>

### <a name="pattern"></a><span data-ttu-id="c3268-262">模式</span><span class="sxs-lookup"><span data-stu-id="c3268-262">Pattern</span></span>

-  <span data-ttu-id="c3268-263">数字</span><span class="sxs-lookup"><span data-stu-id="c3268-263">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c3268-264">校验和</span><span class="sxs-lookup"><span data-stu-id="c3268-264">Checksum</span></span>

<span data-ttu-id="c3268-265">不适用</span><span class="sxs-lookup"><span data-stu-id="c3268-265">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c3268-266">定义</span><span class="sxs-lookup"><span data-stu-id="c3268-266">Definition</span></span>

<span data-ttu-id="c3268-267">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c3268-267">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c3268-268">正则表达式`Regex_lithuania_eu_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-268">The regular expression  `Regex_lithuania_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-269">正则表达式`Regex_lithuania_eu_formatted_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-269">The regular expression  `Regex_lithuania_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-270">从关键字`Keywords_lithuania_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c3268-270">A keyword from  `Keywords_lithuania_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_mobile_number"/>
          <Match idRef="Keywords_lithuania_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_lithuania_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="luxemburg"></a><span data-ttu-id="c3268-271">卢森堡</span><span class="sxs-lookup"><span data-stu-id="c3268-271">Luxemburg</span></span>

### <a name="pattern"></a><span data-ttu-id="c3268-272">模式</span><span class="sxs-lookup"><span data-stu-id="c3268-272">Pattern</span></span>

-  <span data-ttu-id="c3268-273">数字</span><span class="sxs-lookup"><span data-stu-id="c3268-273">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c3268-274">校验和</span><span class="sxs-lookup"><span data-stu-id="c3268-274">Checksum</span></span>

<span data-ttu-id="c3268-275">不适用</span><span class="sxs-lookup"><span data-stu-id="c3268-275">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c3268-276">定义</span><span class="sxs-lookup"><span data-stu-id="c3268-276">Definition</span></span>

<span data-ttu-id="c3268-277">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c3268-277">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c3268-278">正则表达式`Regex_luxumburg_eu_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-278">The regular expression  `Regex_luxumburg_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-279">正则表达式`Regex_luxumburg_eu_formatted_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-279">The regular expression  `Regex_luxumburg_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-280">从关键字`Keywords_luxumburg_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c3268-280">A keyword from  `Keywords_luxumburg_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxumburg_eu_mobile_number"/>
          <Match idRef="Keywords_luxumburg_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_luxumburg_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="malta"></a><span data-ttu-id="c3268-281">马耳他</span><span class="sxs-lookup"><span data-stu-id="c3268-281">Malta</span></span>

### <a name="pattern"></a><span data-ttu-id="c3268-282">模式</span><span class="sxs-lookup"><span data-stu-id="c3268-282">Pattern</span></span>

-  <span data-ttu-id="c3268-283">数字</span><span class="sxs-lookup"><span data-stu-id="c3268-283">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c3268-284">校验和</span><span class="sxs-lookup"><span data-stu-id="c3268-284">Checksum</span></span>

<span data-ttu-id="c3268-285">不适用</span><span class="sxs-lookup"><span data-stu-id="c3268-285">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c3268-286">定义</span><span class="sxs-lookup"><span data-stu-id="c3268-286">Definition</span></span>

<span data-ttu-id="c3268-287">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c3268-287">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c3268-288">正则表达式`Regex_malta_eu_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-288">The regular expression  `Regex_malta_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-289">正则表达式`Regex_malta_eu_formatted_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-289">The regular expression  `Regex_malta_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-290">从关键字`Keywords_malta_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c3268-290">A keyword from  `Keywords_malta_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_mobile_number"/>
          <Match idRef="Keywords_malta_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_malta_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="netherlands"></a><span data-ttu-id="c3268-291">荷兰</span><span class="sxs-lookup"><span data-stu-id="c3268-291">Netherlands</span></span>

### <a name="pattern"></a><span data-ttu-id="c3268-292">模式</span><span class="sxs-lookup"><span data-stu-id="c3268-292">Pattern</span></span>

-  <span data-ttu-id="c3268-293">数字</span><span class="sxs-lookup"><span data-stu-id="c3268-293">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c3268-294">校验和</span><span class="sxs-lookup"><span data-stu-id="c3268-294">Checksum</span></span>

<span data-ttu-id="c3268-295">不适用</span><span class="sxs-lookup"><span data-stu-id="c3268-295">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c3268-296">定义</span><span class="sxs-lookup"><span data-stu-id="c3268-296">Definition</span></span>

<span data-ttu-id="c3268-297">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c3268-297">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c3268-298">正则表达式`Regex_netherlands_eu_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-298">The regular expression  `Regex_netherlands_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-299">正则表达式`Regex_netherlands_eu_formatted_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-299">The regular expression  `Regex_netherlands_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-300">从关键字`Keywords_netherlands_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c3268-300">A keyword from  `Keywords_netherlands_eu_mobile_number` is found.</span></span> 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_mobile_number"/>
          <Match idRef="Keywords_netherlands_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_netherlands_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="poland"></a><span data-ttu-id="c3268-301">波兰</span><span class="sxs-lookup"><span data-stu-id="c3268-301">Poland</span></span>

### <a name="pattern"></a><span data-ttu-id="c3268-302">模式</span><span class="sxs-lookup"><span data-stu-id="c3268-302">Pattern</span></span>

-  <span data-ttu-id="c3268-303">数字</span><span class="sxs-lookup"><span data-stu-id="c3268-303">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c3268-304">校验和</span><span class="sxs-lookup"><span data-stu-id="c3268-304">Checksum</span></span>

<span data-ttu-id="c3268-305">不适用</span><span class="sxs-lookup"><span data-stu-id="c3268-305">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c3268-306">定义</span><span class="sxs-lookup"><span data-stu-id="c3268-306">Definition</span></span>

<span data-ttu-id="c3268-307">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c3268-307">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c3268-308">正则表达式`Regex_poland_eu_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-308">The regular expression  `Regex_poland_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-309">正则表达式`Regex_poland_eu_formatted_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-309">The regular expression  `Regex_poland_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-310">从关键字`Keywords_poland_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c3268-310">A keyword from  `Keywords_poland_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_mobile_number"/>
          <Match idRef="Keywords_poland_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_poland_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="portugal"></a><span data-ttu-id="c3268-311">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="c3268-311">Portugal</span></span>

### <a name="pattern"></a><span data-ttu-id="c3268-312">模式</span><span class="sxs-lookup"><span data-stu-id="c3268-312">Pattern</span></span>

-  <span data-ttu-id="c3268-313">数字</span><span class="sxs-lookup"><span data-stu-id="c3268-313">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c3268-314">校验和</span><span class="sxs-lookup"><span data-stu-id="c3268-314">Checksum</span></span>

<span data-ttu-id="c3268-315">不适用</span><span class="sxs-lookup"><span data-stu-id="c3268-315">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c3268-316">定义</span><span class="sxs-lookup"><span data-stu-id="c3268-316">Definition</span></span>

<span data-ttu-id="c3268-317">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c3268-317">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c3268-318">正则表达式`Regex_portugal_eu_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-318">The regular expression  `Regex_portugal_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-319">正则表达式`Regex_portugal_eu_formatted_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-319">The regular expression  `Regex_portugal_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-320">从关键字`Keywords_portugal_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c3268-320">A keyword from  `Keywords_portugal_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_mobile_number"/>
          <Match idRef="Keywords_portugal_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_portugal_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="romania"></a><span data-ttu-id="c3268-321">罗马尼亚</span><span class="sxs-lookup"><span data-stu-id="c3268-321">Romania</span></span>

### <a name="pattern"></a><span data-ttu-id="c3268-322">模式</span><span class="sxs-lookup"><span data-stu-id="c3268-322">Pattern</span></span>

-  <span data-ttu-id="c3268-323">数字</span><span class="sxs-lookup"><span data-stu-id="c3268-323">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c3268-324">校验和</span><span class="sxs-lookup"><span data-stu-id="c3268-324">Checksum</span></span>

<span data-ttu-id="c3268-325">不适用</span><span class="sxs-lookup"><span data-stu-id="c3268-325">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c3268-326">定义</span><span class="sxs-lookup"><span data-stu-id="c3268-326">Definition</span></span>

<span data-ttu-id="c3268-327">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c3268-327">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c3268-328">正则表达式`Regex_romania_eu_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-328">The regular expression  `Regex_romania_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-329">正则表达式`Regex_romania_eu_formatted_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-329">The regular expression  `Regex_romania_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-330">从关键字`Keywords_romania_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c3268-330">A keyword from  `Keywords_romania_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_mobile_number"/>
          <Match idRef="Keywords_romania_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_romania_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="slovakia"></a><span data-ttu-id="c3268-331">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="c3268-331">Slovakia</span></span>

### <a name="pattern"></a><span data-ttu-id="c3268-332">模式</span><span class="sxs-lookup"><span data-stu-id="c3268-332">Pattern</span></span>

-  <span data-ttu-id="c3268-333">数字</span><span class="sxs-lookup"><span data-stu-id="c3268-333">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c3268-334">校验和</span><span class="sxs-lookup"><span data-stu-id="c3268-334">Checksum</span></span>

<span data-ttu-id="c3268-335">不适用</span><span class="sxs-lookup"><span data-stu-id="c3268-335">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c3268-336">定义</span><span class="sxs-lookup"><span data-stu-id="c3268-336">Definition</span></span>

<span data-ttu-id="c3268-337">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c3268-337">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c3268-338">正则表达式`Regex_slovakia_eu_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-338">The regular expression  `Regex_slovakia_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-339">正则表达式`Regex_slovakia_eu_formatted_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-339">The regular expression  `Regex_slovakia_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-340">从关键字`Keywords_slovakia_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c3268-340">A keyword from  `Keywords_slovakia_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_mobile_number"/>
          <Match idRef="Keywords_slovakia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_slovakia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="slovenia"></a><span data-ttu-id="c3268-341">斯诺文尼亚</span><span class="sxs-lookup"><span data-stu-id="c3268-341">Slovenia</span></span>

### <a name="pattern"></a><span data-ttu-id="c3268-342">模式</span><span class="sxs-lookup"><span data-stu-id="c3268-342">Pattern</span></span>

-  <span data-ttu-id="c3268-343">数字</span><span class="sxs-lookup"><span data-stu-id="c3268-343">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c3268-344">校验和</span><span class="sxs-lookup"><span data-stu-id="c3268-344">Checksum</span></span>

<span data-ttu-id="c3268-345">不适用</span><span class="sxs-lookup"><span data-stu-id="c3268-345">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c3268-346">定义</span><span class="sxs-lookup"><span data-stu-id="c3268-346">Definition</span></span>

<span data-ttu-id="c3268-347">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c3268-347">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c3268-348">正则表达式`Regex_slovenia_eu_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-348">The regular expression  `Regex_slovenia_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-349">正则表达式`Regex_slovenia_eu_formatted_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-349">The regular expression  `Regex_slovenia_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-350">从关键字`Keywords_slovenia_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c3268-350">A keyword from  `Keywords_slovenia_eu_mobile_number` is found.</span></span> 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_mobile_number"/>
          <Match idRef="Keywords_slovenia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_slovenia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="spain"></a><span data-ttu-id="c3268-351">西班牙</span><span class="sxs-lookup"><span data-stu-id="c3268-351">Spain</span></span>

### <a name="pattern"></a><span data-ttu-id="c3268-352">模式</span><span class="sxs-lookup"><span data-stu-id="c3268-352">Pattern</span></span>

-  <span data-ttu-id="c3268-353">数字</span><span class="sxs-lookup"><span data-stu-id="c3268-353">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c3268-354">校验和</span><span class="sxs-lookup"><span data-stu-id="c3268-354">Checksum</span></span>

<span data-ttu-id="c3268-355">不适用</span><span class="sxs-lookup"><span data-stu-id="c3268-355">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c3268-356">定义</span><span class="sxs-lookup"><span data-stu-id="c3268-356">Definition</span></span>

<span data-ttu-id="c3268-357">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c3268-357">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c3268-358">正则表达式`Regex_spain_eu_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-358">The regular expression  `Regex_spain_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-359">正则表达式`Regex_spain_eu_formatted_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-359">The regular expression  `Regex_spain_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-360">从关键字`Keywords_spain_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c3268-360">A keyword from  `Keywords_spain_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_mobile_number"/>
          <Match idRef="Keywords_spain_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_spain_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="sweden"></a><span data-ttu-id="c3268-361">瑞典</span><span class="sxs-lookup"><span data-stu-id="c3268-361">Sweden</span></span>

### <a name="pattern"></a><span data-ttu-id="c3268-362">模式</span><span class="sxs-lookup"><span data-stu-id="c3268-362">Pattern</span></span>

-  <span data-ttu-id="c3268-363">数字</span><span class="sxs-lookup"><span data-stu-id="c3268-363">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c3268-364">校验和</span><span class="sxs-lookup"><span data-stu-id="c3268-364">Checksum</span></span>

<span data-ttu-id="c3268-365">不适用</span><span class="sxs-lookup"><span data-stu-id="c3268-365">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c3268-366">定义</span><span class="sxs-lookup"><span data-stu-id="c3268-366">Definition</span></span>

<span data-ttu-id="c3268-367">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c3268-367">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c3268-368">正则表达式`Regex_sweden_eu_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-368">The regular expression  `Regex_sweden_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-369">正则表达式`Regex_sweden_eu_formatted_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-369">The regular expression  `Regex_sweden_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-370">从关键字`Keywords_sweden_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c3268-370">A keyword from  `Keywords_sweden_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_mobile_number"/>
          <Match idRef="Keywords_sweden_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_sweden_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="uk"></a><span data-ttu-id="c3268-371">英国</span><span class="sxs-lookup"><span data-stu-id="c3268-371">UK</span></span>

### <a name="pattern"></a><span data-ttu-id="c3268-372">模式</span><span class="sxs-lookup"><span data-stu-id="c3268-372">Pattern</span></span>

-  <span data-ttu-id="c3268-373">数字</span><span class="sxs-lookup"><span data-stu-id="c3268-373">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c3268-374">校验和</span><span class="sxs-lookup"><span data-stu-id="c3268-374">Checksum</span></span>

<span data-ttu-id="c3268-375">不适用</span><span class="sxs-lookup"><span data-stu-id="c3268-375">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c3268-376">定义</span><span class="sxs-lookup"><span data-stu-id="c3268-376">Definition</span></span>

<span data-ttu-id="c3268-377">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c3268-377">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c3268-378">正则表达式`Regex_uk_eu_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-378">The regular expression  `Regex_uk_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-379">正则表达式`Regex_uk_eu_formatted_mobile_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c3268-379">The regular expression  `Regex_uk_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c3268-380">从关键字`Keywords_uk_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c3268-380">A keyword from  `Keywords_uk_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_uk_eu_mobile_number"/>
          <Match idRef="Keywords_uk_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_uk_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="see-also"></a><span data-ttu-id="c3268-381">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c3268-381">See also</span></span>

[<span data-ttu-id="c3268-382">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="c3268-382">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

