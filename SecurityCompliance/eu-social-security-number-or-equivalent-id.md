---
title: 欧盟社会安全号码或等效 ID
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 1fabd341-e594-4bfe-961c-62aa82893f60
description: 本主题介绍当数据丢失防护 (DLP) 策略检测到欧盟社会保险号码或等效 ID 敏感信息类型时, 将会查找什么。此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。
ms.openlocfilehash: abcefb6930e9c02d2f32d84b65accfecf1e20d95
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216522"
---
# <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="845bf-104">欧盟社会安全号码或等效 ID</span><span class="sxs-lookup"><span data-stu-id="845bf-104">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="845bf-p102">本主题介绍当数据丢失防护 (DLP) 策略检测到欧盟社会保险号码 (SSN) 或等效 ID 敏感信息类型时, 会查找什么内容。此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。</span><span class="sxs-lookup"><span data-stu-id="845bf-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Social Security Number (SSN) or Equivalent ID sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="845bf-107">奥地利</span><span class="sxs-lookup"><span data-stu-id="845bf-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="845bf-108">格式</span><span class="sxs-lookup"><span data-stu-id="845bf-108">Format</span></span>

<span data-ttu-id="845bf-109">以指定格式表示的10个数字</span><span class="sxs-lookup"><span data-stu-id="845bf-109">10 digits in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="845bf-110">模式</span><span class="sxs-lookup"><span data-stu-id="845bf-110">Pattern</span></span>

<span data-ttu-id="845bf-111">10 个数字：</span><span class="sxs-lookup"><span data-stu-id="845bf-111">10 digits:</span></span>
  
-  <span data-ttu-id="845bf-112">与序列号对应的三个数字</span><span class="sxs-lookup"><span data-stu-id="845bf-112">Three digits that correspond to a serial number</span></span> 
    
- <span data-ttu-id="845bf-113">一个校验位</span><span class="sxs-lookup"><span data-stu-id="845bf-113">One check digit</span></span>
    
- <span data-ttu-id="845bf-114">与出生日期对应的6个数字 (DDMMYY)</span><span class="sxs-lookup"><span data-stu-id="845bf-114">Six digits that correspond to the birth date (DDMMYY)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="845bf-115">校验和</span><span class="sxs-lookup"><span data-stu-id="845bf-115">Checksum</span></span>

<span data-ttu-id="845bf-116">是</span><span class="sxs-lookup"><span data-stu-id="845bf-116">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="845bf-117">定义</span><span class="sxs-lookup"><span data-stu-id="845bf-117">Definition</span></span>

<span data-ttu-id="845bf-118">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="845bf-118">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="845bf-119">函数`Func_austria_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="845bf-119">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="845bf-120">找到了中`Keywords_austria_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="845bf-120">A keyword from  `Keywords_austria_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="845bf-121">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="845bf-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="845bf-122">函数`Func_austria_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="845bf-122">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
<Pattern confidenceLevel="75">
            <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="845bf-123">关键字</span><span class="sxs-lookup"><span data-stu-id="845bf-123">Keywords</span></span>

#### <a name="keywordsaustriaeussnorequivalent"></a><span data-ttu-id="845bf-124">Keywords_austria_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="845bf-124">Keywords_austria_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="845bf-125">社会保障号</span><span class="sxs-lookup"><span data-stu-id="845bf-125">social security no</span></span>
  
<span data-ttu-id="845bf-126">social security number
</span><span class="sxs-lookup"><span data-stu-id="845bf-126">social security number</span></span>
  
<span data-ttu-id="845bf-127">
social security code</span><span class="sxs-lookup"><span data-stu-id="845bf-127">social security code</span></span>
  
<span data-ttu-id="845bf-128">保险号</span><span class="sxs-lookup"><span data-stu-id="845bf-128">insurance number</span></span>
  
<span data-ttu-id="845bf-129">奥地利 ssn</span><span class="sxs-lookup"><span data-stu-id="845bf-129">austrian ssn</span></span>
  
<span data-ttu-id="845bf-130">ssn</span><span class="sxs-lookup"><span data-stu-id="845bf-130">ssn#</span></span>
  
<span data-ttu-id="845bf-131">ssn</span><span class="sxs-lookup"><span data-stu-id="845bf-131">ssn</span></span>
  
<span data-ttu-id="845bf-132">保险费代码</span><span class="sxs-lookup"><span data-stu-id="845bf-132">insurance code</span></span>
  
<span data-ttu-id="845bf-133">保险代码 #</span><span class="sxs-lookup"><span data-stu-id="845bf-133">insurance code#</span></span>
  
<span data-ttu-id="845bf-134">socialsecurityno #</span><span class="sxs-lookup"><span data-stu-id="845bf-134">socialsecurityno#</span></span>
  
<span data-ttu-id="845bf-135">sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="845bf-135">sozialversicherungsnummer</span></span>
  
<span data-ttu-id="845bf-136">soziale sicherheit kein</span><span class="sxs-lookup"><span data-stu-id="845bf-136">soziale sicherheit kein</span></span>
  
<span data-ttu-id="845bf-137">versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="845bf-137">versicherungsnummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="845bf-138">比利时</span><span class="sxs-lookup"><span data-stu-id="845bf-138">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="845bf-139">格式</span><span class="sxs-lookup"><span data-stu-id="845bf-139">Format</span></span>

<span data-ttu-id="845bf-140">11位数, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="845bf-140">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="845bf-141">模式</span><span class="sxs-lookup"><span data-stu-id="845bf-141">Pattern</span></span>

<span data-ttu-id="845bf-142">11 个数字</span><span class="sxs-lookup"><span data-stu-id="845bf-142">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="845bf-143">校验和</span><span class="sxs-lookup"><span data-stu-id="845bf-143">Checksum</span></span>

<span data-ttu-id="845bf-144">是</span><span class="sxs-lookup"><span data-stu-id="845bf-144">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="845bf-145">定义</span><span class="sxs-lookup"><span data-stu-id="845bf-145">Definition</span></span>

<span data-ttu-id="845bf-146">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="845bf-146">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="845bf-147">函数`Func_belgium_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="845bf-147">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="845bf-148">找到了中`Keywords_belgium_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="845bf-148">A keyword from  `Keywords_belgium_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="845bf-149">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="845bf-149">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="845bf-150">函数`Func_belgium_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="845bf-150">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_belgium_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="845bf-151">关键字</span><span class="sxs-lookup"><span data-stu-id="845bf-151">Keywords</span></span>

#### <a name="keywordsbelgiumeussnorequivalent"></a><span data-ttu-id="845bf-152">Keywords_belgium_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="845bf-152">Keywords_belgium_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="845bf-153">比利时国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="845bf-153">belgian national number</span></span>
  
<span data-ttu-id="845bf-154">国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="845bf-154">national number</span></span>
  
<span data-ttu-id="845bf-155">social security number
</span><span class="sxs-lookup"><span data-stu-id="845bf-155">social security number</span></span>
  
<span data-ttu-id="845bf-156">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="845bf-156">nationalnumber#</span></span>
  
<span data-ttu-id="845bf-157">ssn</span><span class="sxs-lookup"><span data-stu-id="845bf-157">ssn#</span></span>
  
<span data-ttu-id="845bf-158">ssn</span><span class="sxs-lookup"><span data-stu-id="845bf-158">ssn</span></span>
  
<span data-ttu-id="845bf-159">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="845bf-159">nationalnumber</span></span>
  
<span data-ttu-id="845bf-160">bnn #</span><span class="sxs-lookup"><span data-stu-id="845bf-160">bnn#</span></span>
  
<span data-ttu-id="845bf-161">bnn</span><span class="sxs-lookup"><span data-stu-id="845bf-161">bnn</span></span>
  
<span data-ttu-id="845bf-162">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="845bf-162">personal id number</span></span>
  
<span data-ttu-id="845bf-163">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="845bf-163">personalidnumber#</span></span>
  
<span data-ttu-id="845bf-164">numéro 国家</span><span class="sxs-lookup"><span data-stu-id="845bf-164">numéro national</span></span>
  
<span data-ttu-id="845bf-165">numéro de sécurité
</span><span class="sxs-lookup"><span data-stu-id="845bf-165">numéro de sécurité</span></span>
  
<span data-ttu-id="845bf-166">numéro d'assuré</span><span class="sxs-lookup"><span data-stu-id="845bf-166">numéro d'assuré</span></span>
  
<span data-ttu-id="845bf-167">identifiant 国家</span><span class="sxs-lookup"><span data-stu-id="845bf-167">identifiant national</span></span>
  
<span data-ttu-id="845bf-168">identifiantnational #</span><span class="sxs-lookup"><span data-stu-id="845bf-168">identifiantnational#</span></span>
  
<span data-ttu-id="845bf-169">numéronational #</span><span class="sxs-lookup"><span data-stu-id="845bf-169">numéronational#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="845bf-170">克罗地亚</span><span class="sxs-lookup"><span data-stu-id="845bf-170">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="845bf-171">格式</span><span class="sxs-lookup"><span data-stu-id="845bf-171">Format</span></span>

<span data-ttu-id="845bf-172">11个数字, 无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="845bf-172">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="845bf-173">模式</span><span class="sxs-lookup"><span data-stu-id="845bf-173">Pattern</span></span>

 <span data-ttu-id="845bf-174">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="845bf-174">11 digits:</span></span> 
  
-  <span data-ttu-id="845bf-175">10位数字</span><span class="sxs-lookup"><span data-stu-id="845bf-175">Ten digits</span></span> 
    
- <span data-ttu-id="845bf-176">一个校验位</span><span class="sxs-lookup"><span data-stu-id="845bf-176">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="845bf-177">校验和</span><span class="sxs-lookup"><span data-stu-id="845bf-177">Checksum</span></span>

<span data-ttu-id="845bf-178">是</span><span class="sxs-lookup"><span data-stu-id="845bf-178">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="845bf-179">定义</span><span class="sxs-lookup"><span data-stu-id="845bf-179">Definition</span></span>

<span data-ttu-id="845bf-180">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="845bf-180">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="845bf-181">函数`Func_croatia_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="845bf-181">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="845bf-182">找到了中`Keywords_croatia_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="845bf-182">A keyword from  `Keywords_croatia_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="845bf-183">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="845bf-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="845bf-184">函数`Func_croatia_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="845bf-184">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_croatia_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="845bf-185">关键字</span><span class="sxs-lookup"><span data-stu-id="845bf-185">Keywords</span></span>

#### <a name="keywordscroatiaeussnorequivalent"></a><span data-ttu-id="845bf-186">Keywords_croatia_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="845bf-186">Keywords_croatia_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="845bf-187">个人标识号</span><span class="sxs-lookup"><span data-stu-id="845bf-187">personal identification number</span></span>
  
<span data-ttu-id="845bf-188">主公民号码</span><span class="sxs-lookup"><span data-stu-id="845bf-188">master citizen number</span></span>
  
<span data-ttu-id="845bf-189">国家/地区标识号</span><span class="sxs-lookup"><span data-stu-id="845bf-189">national identification number</span></span>
  
<span data-ttu-id="845bf-190">social security number
</span><span class="sxs-lookup"><span data-stu-id="845bf-190">social security number</span></span>
  
<span data-ttu-id="845bf-191">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="845bf-191">nationalnumber#</span></span>
  
<span data-ttu-id="845bf-192">ssn</span><span class="sxs-lookup"><span data-stu-id="845bf-192">ssn#</span></span>
  
<span data-ttu-id="845bf-193">ssn</span><span class="sxs-lookup"><span data-stu-id="845bf-193">ssn</span></span>
  
<span data-ttu-id="845bf-194">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="845bf-194">nationalnumber</span></span>
  
<span data-ttu-id="845bf-195">bnn #</span><span class="sxs-lookup"><span data-stu-id="845bf-195">bnn#</span></span>
  
<span data-ttu-id="845bf-196">bnn</span><span class="sxs-lookup"><span data-stu-id="845bf-196">bnn</span></span>
  
<span data-ttu-id="845bf-197">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="845bf-197">personal id number</span></span>
  
<span data-ttu-id="845bf-198">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="845bf-198">personalidnumber#</span></span>
  
<span data-ttu-id="845bf-199">oib</span><span class="sxs-lookup"><span data-stu-id="845bf-199">oib</span></span>
  
<span data-ttu-id="845bf-200">osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="845bf-200">osobni identifikacijski broj</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="845bf-201">捷克共和国</span><span class="sxs-lookup"><span data-stu-id="845bf-201">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="845bf-202">格式</span><span class="sxs-lookup"><span data-stu-id="845bf-202">Format</span></span>

<span data-ttu-id="845bf-203">指定模式中的10个数字和一个反斜杠</span><span class="sxs-lookup"><span data-stu-id="845bf-203">Ten digits and a backslash in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="845bf-204">模式</span><span class="sxs-lookup"><span data-stu-id="845bf-204">Pattern</span></span>

<span data-ttu-id="845bf-205">10个数字和一个反斜杠:</span><span class="sxs-lookup"><span data-stu-id="845bf-205">Ten digits and a backslash:</span></span>
  
- <span data-ttu-id="845bf-206">与出生日期对应的6个数字 (YYMMDD):</span><span class="sxs-lookup"><span data-stu-id="845bf-206">Six digits that correspond to the birth date (YYMMDD):</span></span> 
    
- <span data-ttu-id="845bf-207">反斜杠</span><span class="sxs-lookup"><span data-stu-id="845bf-207">A backslash</span></span>
    
- <span data-ttu-id="845bf-208">与一个序列号相对应的三个数字, 用于分隔出生于同一日期的人员</span><span class="sxs-lookup"><span data-stu-id="845bf-208">Three digits that correspond to a serial number that separates persons born on the same date</span></span>
    
- <span data-ttu-id="845bf-209">一个校验位</span><span class="sxs-lookup"><span data-stu-id="845bf-209">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="845bf-210">校验和</span><span class="sxs-lookup"><span data-stu-id="845bf-210">Checksum</span></span>

<span data-ttu-id="845bf-211">是</span><span class="sxs-lookup"><span data-stu-id="845bf-211">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="845bf-212">定义</span><span class="sxs-lookup"><span data-stu-id="845bf-212">Definition</span></span>

<span data-ttu-id="845bf-213">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="845bf-213">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="845bf-214">函数`Func_czech_republic_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="845bf-214">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="845bf-215">找到了中`Keywords_czech_republic_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="845bf-215">A keyword from  `Keywords_czech_republic_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="845bf-216">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="845bf-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="845bf-217">函数`Func_czech_republic_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="845bf-217">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_czech_republic_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="845bf-218">关键字</span><span class="sxs-lookup"><span data-stu-id="845bf-218">Keywords</span></span>

#### <a name="keywordsczechrepubliceussnorequivalent"></a><span data-ttu-id="845bf-219">Keywords_czech_republic_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="845bf-219">Keywords_czech_republic_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="845bf-220">出生号码</span><span class="sxs-lookup"><span data-stu-id="845bf-220">birth number</span></span>
  
<span data-ttu-id="845bf-221">国家/地区标识号</span><span class="sxs-lookup"><span data-stu-id="845bf-221">national identification number</span></span>
  
<span data-ttu-id="845bf-222">个人标识号</span><span class="sxs-lookup"><span data-stu-id="845bf-222">personal identification number</span></span>
  
<span data-ttu-id="845bf-223">social security number
</span><span class="sxs-lookup"><span data-stu-id="845bf-223">social security number</span></span>
  
<span data-ttu-id="845bf-224">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="845bf-224">nationalnumber#</span></span>
  
<span data-ttu-id="845bf-225">ssn</span><span class="sxs-lookup"><span data-stu-id="845bf-225">ssn#</span></span>
  
<span data-ttu-id="845bf-226">ssn</span><span class="sxs-lookup"><span data-stu-id="845bf-226">ssn</span></span>
  
<span data-ttu-id="845bf-227">国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="845bf-227">national number</span></span>
  
<span data-ttu-id="845bf-228">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="845bf-228">personal id number</span></span>
  
<span data-ttu-id="845bf-229">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="845bf-229">personalidnumber#</span></span>
  
<span data-ttu-id="845bf-230">rč</span><span class="sxs-lookup"><span data-stu-id="845bf-230">rč</span></span>
  
<span data-ttu-id="845bf-231">rodnéčíslo</span><span class="sxs-lookup"><span data-stu-id="845bf-231">rodné číslo</span></span>
  
<span data-ttu-id="845bf-232">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="845bf-232">rodne cislo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="845bf-233">丹麦</span><span class="sxs-lookup"><span data-stu-id="845bf-233">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="845bf-234">格式</span><span class="sxs-lookup"><span data-stu-id="845bf-234">Format</span></span>

<span data-ttu-id="845bf-235">指定模式中的10个数字和一个连字符</span><span class="sxs-lookup"><span data-stu-id="845bf-235">Ten digits and a hyphen in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="845bf-236">模式</span><span class="sxs-lookup"><span data-stu-id="845bf-236">Pattern</span></span>

<span data-ttu-id="845bf-237">10个数字和一个连字符:</span><span class="sxs-lookup"><span data-stu-id="845bf-237">Ten digits and a hyphen:</span></span>
  
- <span data-ttu-id="845bf-238">与出生日期对应的6个数字 (DDMMYY)</span><span class="sxs-lookup"><span data-stu-id="845bf-238">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="845bf-239">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="845bf-239">A hyphen</span></span>
    
- <span data-ttu-id="845bf-240">与序列号对应的四个数字</span><span class="sxs-lookup"><span data-stu-id="845bf-240">Four digits that correspond to a sequence number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="845bf-241">校验和</span><span class="sxs-lookup"><span data-stu-id="845bf-241">Checksum</span></span>

<span data-ttu-id="845bf-242">是</span><span class="sxs-lookup"><span data-stu-id="845bf-242">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="845bf-243">定义</span><span class="sxs-lookup"><span data-stu-id="845bf-243">Definition</span></span>

<span data-ttu-id="845bf-244">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="845bf-244">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="845bf-245">函数`Func_denmark_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="845bf-245">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="845bf-246">找到了中`Keywords_denmark_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="845bf-246">A keyword from  `Keywords_denmark_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="845bf-247">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="845bf-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="845bf-248">函数`Func_denmark_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="845bf-248">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_denmark_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="845bf-249">关键字</span><span class="sxs-lookup"><span data-stu-id="845bf-249">Keywords</span></span>

#### <a name="keywordsdenmarkeussnorequivalent"></a><span data-ttu-id="845bf-250">Keywords_denmark_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="845bf-250">Keywords_denmark_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="845bf-251">个人标识号</span><span class="sxs-lookup"><span data-stu-id="845bf-251">personal identification number</span></span>
  
<span data-ttu-id="845bf-252">国家/地区标识号</span><span class="sxs-lookup"><span data-stu-id="845bf-252">national identification number</span></span>
  
<span data-ttu-id="845bf-253">social security number
</span><span class="sxs-lookup"><span data-stu-id="845bf-253">social security number</span></span>
  
<span data-ttu-id="845bf-254">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="845bf-254">nationalnumber#</span></span>
  
<span data-ttu-id="845bf-255">ssn</span><span class="sxs-lookup"><span data-stu-id="845bf-255">ssn#</span></span>
  
<span data-ttu-id="845bf-256">ssn</span><span class="sxs-lookup"><span data-stu-id="845bf-256">ssn</span></span>
  
<span data-ttu-id="845bf-257">国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="845bf-257">national number</span></span>
  
<span data-ttu-id="845bf-258">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="845bf-258">personal id number</span></span>
  
<span data-ttu-id="845bf-259">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="845bf-259">personalidnumber#</span></span>
  
<span data-ttu-id="845bf-260">cpr-nummer</span><span class="sxs-lookup"><span data-stu-id="845bf-260">cpr-nummer</span></span>
  
<span data-ttu-id="845bf-261">personnummer</span><span class="sxs-lookup"><span data-stu-id="845bf-261">personnummer</span></span>
  
## <a name="finland"></a><span data-ttu-id="845bf-262">芬兰</span><span class="sxs-lookup"><span data-stu-id="845bf-262">Finland</span></span>

### <a name="format"></a><span data-ttu-id="845bf-263">格式</span><span class="sxs-lookup"><span data-stu-id="845bf-263">Format</span></span>

<span data-ttu-id="845bf-264">指定格式的11个字符的组合</span><span class="sxs-lookup"><span data-stu-id="845bf-264">An 11-character combination in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="845bf-265">模式</span><span class="sxs-lookup"><span data-stu-id="845bf-265">Pattern</span></span>

<span data-ttu-id="845bf-266">指定格式的11个字符的组合:</span><span class="sxs-lookup"><span data-stu-id="845bf-266">An 11-character combination in the specified format:</span></span>
  
-  <span data-ttu-id="845bf-267">六位数字</span><span class="sxs-lookup"><span data-stu-id="845bf-267">Six digits</span></span> 
    
- <span data-ttu-id="845bf-268">以下任一实例:</span><span class="sxs-lookup"><span data-stu-id="845bf-268">One instance of one of the following:</span></span>
    
  - <span data-ttu-id="845bf-269">加号符号</span><span class="sxs-lookup"><span data-stu-id="845bf-269">Plus symbol</span></span>
    
  - <span data-ttu-id="845bf-270">负号</span><span class="sxs-lookup"><span data-stu-id="845bf-270">Minus symbol</span></span>
    
  - <span data-ttu-id="845bf-271">字母 "A" (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="845bf-271">The letter "A" (not case-sensitive)</span></span>
    
- <span data-ttu-id="845bf-272">三位数字</span><span class="sxs-lookup"><span data-stu-id="845bf-272">Three digits</span></span>
    
- <span data-ttu-id="845bf-273">一个字母或一个数字</span><span class="sxs-lookup"><span data-stu-id="845bf-273">One letter or one digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="845bf-274">校验和</span><span class="sxs-lookup"><span data-stu-id="845bf-274">Checksum</span></span>

<span data-ttu-id="845bf-275">是</span><span class="sxs-lookup"><span data-stu-id="845bf-275">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="845bf-276">定义</span><span class="sxs-lookup"><span data-stu-id="845bf-276">Definition</span></span>

<span data-ttu-id="845bf-277">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="845bf-277">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="845bf-278">函数`Func_finland_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="845bf-278">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="845bf-279">找到了中`Keywords_finland_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="845bf-279">A keyword from  `Keywords_finland_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="845bf-280">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="845bf-280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="845bf-281">函数`Func_finland_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="845bf-281">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_finland_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="845bf-282">关键字</span><span class="sxs-lookup"><span data-stu-id="845bf-282">Keywords</span></span>

#### <a name="keywordsfinlandeussnorequivalent"></a><span data-ttu-id="845bf-283">Keywords_finland_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="845bf-283">Keywords_finland_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="845bf-284">identification number
</span><span class="sxs-lookup"><span data-stu-id="845bf-284">identification number</span></span>
  
<span data-ttu-id="845bf-285">个人 id</span><span class="sxs-lookup"><span data-stu-id="845bf-285">personal id</span></span>
  
<span data-ttu-id="845bf-286">标识号码</span><span class="sxs-lookup"><span data-stu-id="845bf-286">identity number</span></span>
  
<span data-ttu-id="845bf-287">芬兰国家/地区 id 号</span><span class="sxs-lookup"><span data-stu-id="845bf-287">finnish national id number</span></span>
  
<span data-ttu-id="845bf-288">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="845bf-288">personalidnumber#</span></span>
  
<span data-ttu-id="845bf-289">国家/地区标识号</span><span class="sxs-lookup"><span data-stu-id="845bf-289">national identification number</span></span>
  
<span data-ttu-id="845bf-290">id 号</span><span class="sxs-lookup"><span data-stu-id="845bf-290">id number</span></span>
  
<span data-ttu-id="845bf-291">国家/地区 id 编号。</span><span class="sxs-lookup"><span data-stu-id="845bf-291">national id no.</span></span>
  
<span data-ttu-id="845bf-292">国家/地区 id 号</span><span class="sxs-lookup"><span data-stu-id="845bf-292">national id number</span></span>
  
<span data-ttu-id="845bf-293">id 号</span><span class="sxs-lookup"><span data-stu-id="845bf-293">id no</span></span>
  
<span data-ttu-id="845bf-294">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="845bf-294">tunnistenumero</span></span>
  
<span data-ttu-id="845bf-295">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="845bf-295">henkilötunnus</span></span>
  
<span data-ttu-id="845bf-296">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="845bf-296">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="845bf-297">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="845bf-297">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="845bf-298">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="845bf-298">identiteetti numero</span></span>
  
<span data-ttu-id="845bf-299">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="845bf-299">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="845bf-300">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="845bf-300">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="845bf-301">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="845bf-301">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="845bf-302">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="845bf-302">tunnusnumero</span></span>
  
<span data-ttu-id="845bf-303">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="845bf-303">kansallinen tunnus numero</span></span>
  
<span data-ttu-id="845bf-304">hetu</span><span class="sxs-lookup"><span data-stu-id="845bf-304">hetu</span></span>
  
## <a name="france"></a><span data-ttu-id="845bf-305">法国</span><span class="sxs-lookup"><span data-stu-id="845bf-305">France</span></span>

<span data-ttu-id="845bf-306">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "华北社会安全号码 (INSEE)" 一节。</span><span class="sxs-lookup"><span data-stu-id="845bf-306">For details, see the section "France Social Security Number (INSEE)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="845bf-307">德国</span><span class="sxs-lookup"><span data-stu-id="845bf-307">Germany</span></span>

<span data-ttu-id="845bf-308">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "德国身份证号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="845bf-308">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="845bf-309">希腊</span><span class="sxs-lookup"><span data-stu-id="845bf-309">Greece</span></span>

<span data-ttu-id="845bf-310">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "希腊国家 ID 卡" 一节。</span><span class="sxs-lookup"><span data-stu-id="845bf-310">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="845bf-311">匈牙利</span><span class="sxs-lookup"><span data-stu-id="845bf-311">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="845bf-312">格式</span><span class="sxs-lookup"><span data-stu-id="845bf-312">Format</span></span>

<span data-ttu-id="845bf-313">9个数字, 不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="845bf-313">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="845bf-314">模式</span><span class="sxs-lookup"><span data-stu-id="845bf-314">Pattern</span></span>

<span data-ttu-id="845bf-315">九个数字</span><span class="sxs-lookup"><span data-stu-id="845bf-315">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="845bf-316">校验和</span><span class="sxs-lookup"><span data-stu-id="845bf-316">Checksum</span></span>

<span data-ttu-id="845bf-317">是</span><span class="sxs-lookup"><span data-stu-id="845bf-317">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="845bf-318">定义</span><span class="sxs-lookup"><span data-stu-id="845bf-318">Definition</span></span>

<span data-ttu-id="845bf-319">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="845bf-319">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="845bf-320">函数`Func_hungary_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="845bf-320">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="845bf-321">找到了中`Keywords_hungary_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="845bf-321">A keyword from  `Keywords_hungary_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="845bf-322">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="845bf-322">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="845bf-323">函数`Func_hungary_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="845bf-323">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="845bf-324">关键字</span><span class="sxs-lookup"><span data-stu-id="845bf-324">Keywords</span></span>

#### <a name="keywordshungaryeussnorequivalent"></a><span data-ttu-id="845bf-325">Keywords_hungary_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="845bf-325">Keywords_hungary_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="845bf-326">匈牙利语社会安全号码</span><span class="sxs-lookup"><span data-stu-id="845bf-326">hungarian social security number</span></span>
  
<span data-ttu-id="845bf-327">social security number
</span><span class="sxs-lookup"><span data-stu-id="845bf-327">social security number</span></span>
  
<span data-ttu-id="845bf-328">socialsecuritynumber #</span><span class="sxs-lookup"><span data-stu-id="845bf-328">socialsecuritynumber#</span></span>
  
<span data-ttu-id="845bf-329">hssn #</span><span class="sxs-lookup"><span data-stu-id="845bf-329">hssn#</span></span>
  
<span data-ttu-id="845bf-330">socialsecuritynno</span><span class="sxs-lookup"><span data-stu-id="845bf-330">socialsecuritynno</span></span>
  
<span data-ttu-id="845bf-331">hssn</span><span class="sxs-lookup"><span data-stu-id="845bf-331">hssn</span></span>
  
<span data-ttu-id="845bf-332">taj</span><span class="sxs-lookup"><span data-stu-id="845bf-332">taj</span></span>
  
<span data-ttu-id="845bf-333">taj #</span><span class="sxs-lookup"><span data-stu-id="845bf-333">taj#</span></span>
  
<span data-ttu-id="845bf-334">ssn</span><span class="sxs-lookup"><span data-stu-id="845bf-334">ssn</span></span>
  
<span data-ttu-id="845bf-335">ssn</span><span class="sxs-lookup"><span data-stu-id="845bf-335">ssn#</span></span>
  
<span data-ttu-id="845bf-336">社会保障号</span><span class="sxs-lookup"><span data-stu-id="845bf-336">social security no</span></span>
  
<span data-ttu-id="845bf-337">áfa</span><span class="sxs-lookup"><span data-stu-id="845bf-337">áfa</span></span>
  
<span data-ttu-id="845bf-338">közösségi adószám</span><span class="sxs-lookup"><span data-stu-id="845bf-338">közösségi adószám</span></span>
  
<span data-ttu-id="845bf-339">általános forgalmi adó szám</span><span class="sxs-lookup"><span data-stu-id="845bf-339">általános forgalmi adó szám</span></span>
  
<span data-ttu-id="845bf-340">hozzáadottérték adó</span><span class="sxs-lookup"><span data-stu-id="845bf-340">hozzáadottérték adó</span></span>
  
<span data-ttu-id="845bf-341">áfa szám</span><span class="sxs-lookup"><span data-stu-id="845bf-341">áfa szám</span></span>
  
<span data-ttu-id="845bf-342">magyar áfa szám</span><span class="sxs-lookup"><span data-stu-id="845bf-342">magyar áfa szám</span></span>
  
## <a name="portugal"></a><span data-ttu-id="845bf-343">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="845bf-343">Portugal</span></span>

<span data-ttu-id="845bf-344">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "葡萄牙公民卡片号" 部分。</span><span class="sxs-lookup"><span data-stu-id="845bf-344">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="spain"></a><span data-ttu-id="845bf-345">西班牙</span><span class="sxs-lookup"><span data-stu-id="845bf-345">Spain</span></span>

<span data-ttu-id="845bf-346">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "西班牙社会安全号码 (SSN)" 一节。</span><span class="sxs-lookup"><span data-stu-id="845bf-346">For details, see the section "Spain Social Security Number (SSN)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="sweden"></a><span data-ttu-id="845bf-347">瑞典</span><span class="sxs-lookup"><span data-stu-id="845bf-347">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="845bf-348">格式</span><span class="sxs-lookup"><span data-stu-id="845bf-348">Format</span></span>

<span data-ttu-id="845bf-349">12个数字, 不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="845bf-349">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="845bf-350">模式</span><span class="sxs-lookup"><span data-stu-id="845bf-350">Pattern</span></span>

<span data-ttu-id="845bf-351">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="845bf-351">12 digits:</span></span>
  
-  <span data-ttu-id="845bf-352">与出生日期对应的8位数字 (YYYYMMDD)</span><span class="sxs-lookup"><span data-stu-id="845bf-352">Eight digits that correspond to the birth date (YYYYMMDD)</span></span> 
    
- <span data-ttu-id="845bf-353">与序列号对应的三个数字, 其中:</span><span class="sxs-lookup"><span data-stu-id="845bf-353">Three digits that correspond to a serial number where:</span></span> 
    
  - <span data-ttu-id="845bf-354">序列号中的最后一个数字指示在为 "男" 分配一个奇数号码时的性别, 以及一个 "女" 的偶数号码。</span><span class="sxs-lookup"><span data-stu-id="845bf-354">The last digit in the serial number indicates gender by the assignment of an odd number for male and an even number for female</span></span>
    
  - <span data-ttu-id="845bf-355">最多 1990, 将序列号 corresponded 分配给在其中, 号码持有者出生或 (如果在1947之前出生) 的县 (根据纳税记录, 在年1月1日, 使用特殊代码 (通常为第七个数字) 的特殊代码 (通常为9号)immigrants</span><span class="sxs-lookup"><span data-stu-id="845bf-355">Up to 1990, the assignment of serial number corresponded to the county where the bearer of the number was born or (if born before 1947) where he/she had been living, according to tax records, on January 1, 1947, with a special code (usually 9 as the 7th digit) for immigrants</span></span> 
    
- <span data-ttu-id="845bf-356">一个校验位</span><span class="sxs-lookup"><span data-stu-id="845bf-356">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="845bf-357">校验和</span><span class="sxs-lookup"><span data-stu-id="845bf-357">Checksum</span></span>

<span data-ttu-id="845bf-358">是</span><span class="sxs-lookup"><span data-stu-id="845bf-358">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="845bf-359">定义</span><span class="sxs-lookup"><span data-stu-id="845bf-359">Definition</span></span>

<span data-ttu-id="845bf-360">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="845bf-360">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="845bf-361">函数`Func_sweden_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="845bf-361">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="845bf-362">找到了中`Keywords_sweden_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="845bf-362">A keyword from  `Keywords_sweden_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="845bf-363">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="845bf-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="845bf-364">函数`Func_sweden_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="845bf-364">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_sweden_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="845bf-365">关键字</span><span class="sxs-lookup"><span data-stu-id="845bf-365">Keywords</span></span>

#### <a name="keywordsswedeneussnorequivalent"></a><span data-ttu-id="845bf-366">Keywords_sweden_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="845bf-366">Keywords_sweden_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="845bf-367">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="845bf-367">personal id number</span></span>
  
<span data-ttu-id="845bf-368">identification number
</span><span class="sxs-lookup"><span data-stu-id="845bf-368">identification number</span></span>
  
<span data-ttu-id="845bf-369">个人 id 否</span><span class="sxs-lookup"><span data-stu-id="845bf-369">personal id no</span></span>
  
<span data-ttu-id="845bf-370">identity no</span><span class="sxs-lookup"><span data-stu-id="845bf-370">identity no</span></span>
  
<span data-ttu-id="845bf-371">标识否</span><span class="sxs-lookup"><span data-stu-id="845bf-371">identification no</span></span>
  
<span data-ttu-id="845bf-372">个人标识编号</span><span class="sxs-lookup"><span data-stu-id="845bf-372">personal identification no</span></span>
  
<span data-ttu-id="845bf-373">personnummer id</span><span class="sxs-lookup"><span data-stu-id="845bf-373">personnummer id</span></span>
  
<span data-ttu-id="845bf-374">personligt id-nummer</span><span class="sxs-lookup"><span data-stu-id="845bf-374">personligt id-nummer</span></span>
  
<span data-ttu-id="845bf-375">unikt id-nummer</span><span class="sxs-lookup"><span data-stu-id="845bf-375">unikt id-nummer</span></span>
  
<span data-ttu-id="845bf-376">personnummer</span><span class="sxs-lookup"><span data-stu-id="845bf-376">personnummer</span></span>
  
<span data-ttu-id="845bf-377">identifikationsnumret</span><span class="sxs-lookup"><span data-stu-id="845bf-377">identifikationsnumret</span></span>
  
<span data-ttu-id="845bf-378">personnummer #</span><span class="sxs-lookup"><span data-stu-id="845bf-378">personnummer#</span></span>
  
<span data-ttu-id="845bf-379">identifikationsnumret #</span><span class="sxs-lookup"><span data-stu-id="845bf-379">identifikationsnumret#</span></span>
  
## <a name="see-also"></a><span data-ttu-id="845bf-380">另请参阅</span><span class="sxs-lookup"><span data-stu-id="845bf-380">See also</span></span>

[<span data-ttu-id="845bf-381">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="845bf-381">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

