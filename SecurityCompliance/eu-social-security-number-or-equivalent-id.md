---
title: 欧盟社会保险号或等效 ID
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 1fabd341-e594-4bfe-961c-62aa82893f60
description: 本主题演示数据丢失防护 (DLP) 策略检测到的欧盟社会保险号或等效 ID 敏感信息类型时的寻找。此敏感信息类型定义不同的模式、 关键字和每个国家/地区其他证据。
ms.openlocfilehash: 6f1027dcfb648ed937b8180d74d4bc6348dab650
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525285"
---
# <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="191cc-104">欧盟社会保险号或等效 ID</span><span class="sxs-lookup"><span data-stu-id="191cc-104">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="191cc-p102">本主题演示数据丢失防护 (DLP) 策略检测到的欧盟社会保险号码 (SSN) 或等效 ID 敏感信息类型时的寻找。此敏感信息类型定义不同的模式、 关键字和每个国家/地区其他证据。</span><span class="sxs-lookup"><span data-stu-id="191cc-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Social Security Number (SSN) or Equivalent ID sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="191cc-107">奥地利</span><span class="sxs-lookup"><span data-stu-id="191cc-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="191cc-108">格式</span><span class="sxs-lookup"><span data-stu-id="191cc-108">Format</span></span>

<span data-ttu-id="191cc-109">10 位数字以指定格式</span><span class="sxs-lookup"><span data-stu-id="191cc-109">10 digits in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="191cc-110">模式</span><span class="sxs-lookup"><span data-stu-id="191cc-110">Pattern</span></span>

<span data-ttu-id="191cc-111">10 个数字：</span><span class="sxs-lookup"><span data-stu-id="191cc-111">10 digits:</span></span>
  
-  <span data-ttu-id="191cc-112">三个转成序列号对应的数字</span><span class="sxs-lookup"><span data-stu-id="191cc-112">Three digits that correspond to a serial number</span></span> 
    
- <span data-ttu-id="191cc-113">一个检查数字</span><span class="sxs-lookup"><span data-stu-id="191cc-113">One check digit</span></span>
    
- <span data-ttu-id="191cc-114">对应于出生日期月日的 6 个数字</span><span class="sxs-lookup"><span data-stu-id="191cc-114">Six digits that correspond to the birth date (DDMMYY)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="191cc-115">校验和</span><span class="sxs-lookup"><span data-stu-id="191cc-115">Checksum</span></span>

<span data-ttu-id="191cc-116">是</span><span class="sxs-lookup"><span data-stu-id="191cc-116">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="191cc-117">定义</span><span class="sxs-lookup"><span data-stu-id="191cc-117">Definition</span></span>

<span data-ttu-id="191cc-118">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="191cc-118">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="191cc-119">该函数`Func_austria_eu_ssn_or_equivalent`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="191cc-119">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="191cc-120">从关键字`Keywords_austria_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="191cc-120">A keyword from  `Keywords_austria_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="191cc-121">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="191cc-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="191cc-122">该函数`Func_austria_eu_ssn_or_equivalent`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="191cc-122">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="191cc-123">Keywords</span><span class="sxs-lookup"><span data-stu-id="191cc-123">Keywords</span></span>

#### <a name="keywordsaustriaeussnorequivalent"></a><span data-ttu-id="191cc-124">Keywords_austria_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="191cc-124">Keywords_austria_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="191cc-125">社会保障没有</span><span class="sxs-lookup"><span data-stu-id="191cc-125">social security no</span></span>
  
<span data-ttu-id="191cc-126">social security number
</span><span class="sxs-lookup"><span data-stu-id="191cc-126">social security number</span></span>
  
<span data-ttu-id="191cc-127">
social security code</span><span class="sxs-lookup"><span data-stu-id="191cc-127">social security code</span></span>
  
<span data-ttu-id="191cc-128">保险号</span><span class="sxs-lookup"><span data-stu-id="191cc-128">insurance number</span></span>
  
<span data-ttu-id="191cc-129">奥地利 ssn</span><span class="sxs-lookup"><span data-stu-id="191cc-129">austrian ssn</span></span>
  
<span data-ttu-id="191cc-130">ssn #</span><span class="sxs-lookup"><span data-stu-id="191cc-130">ssn#</span></span>
  
<span data-ttu-id="191cc-131">ssn</span><span class="sxs-lookup"><span data-stu-id="191cc-131">ssn</span></span>
  
<span data-ttu-id="191cc-132">保险代码</span><span class="sxs-lookup"><span data-stu-id="191cc-132">insurance code</span></span>
  
<span data-ttu-id="191cc-133">保险代码 #</span><span class="sxs-lookup"><span data-stu-id="191cc-133">insurance code#</span></span>
  
<span data-ttu-id="191cc-134">socialsecurityno #</span><span class="sxs-lookup"><span data-stu-id="191cc-134">socialsecurityno#</span></span>
  
<span data-ttu-id="191cc-135">sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="191cc-135">sozialversicherungsnummer</span></span>
  
<span data-ttu-id="191cc-136">soziale sicherheit kein</span><span class="sxs-lookup"><span data-stu-id="191cc-136">soziale sicherheit kein</span></span>
  
<span data-ttu-id="191cc-137">versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="191cc-137">versicherungsnummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="191cc-138">比利时</span><span class="sxs-lookup"><span data-stu-id="191cc-138">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="191cc-139">格式</span><span class="sxs-lookup"><span data-stu-id="191cc-139">Format</span></span>

<span data-ttu-id="191cc-140">不含空格或分隔符 11 位数字</span><span class="sxs-lookup"><span data-stu-id="191cc-140">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="191cc-141">模式</span><span class="sxs-lookup"><span data-stu-id="191cc-141">Pattern</span></span>

<span data-ttu-id="191cc-142">11 个数字</span><span class="sxs-lookup"><span data-stu-id="191cc-142">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="191cc-143">校验和</span><span class="sxs-lookup"><span data-stu-id="191cc-143">Checksum</span></span>

<span data-ttu-id="191cc-144">是</span><span class="sxs-lookup"><span data-stu-id="191cc-144">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="191cc-145">定义</span><span class="sxs-lookup"><span data-stu-id="191cc-145">Definition</span></span>

<span data-ttu-id="191cc-146">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="191cc-146">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="191cc-147">该函数`Func_belgium_eu_ssn_or_equivalent`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="191cc-147">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="191cc-148">从关键字`Keywords_belgium_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="191cc-148">A keyword from  `Keywords_belgium_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="191cc-149">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="191cc-149">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="191cc-150">该函数`Func_belgium_eu_ssn_or_equivalent`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="191cc-150">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="191cc-151">Keywords</span><span class="sxs-lookup"><span data-stu-id="191cc-151">Keywords</span></span>

#### <a name="keywordsbelgiumeussnorequivalent"></a><span data-ttu-id="191cc-152">Keywords_belgium_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="191cc-152">Keywords_belgium_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="191cc-153">比利时国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="191cc-153">belgian national number</span></span>
  
<span data-ttu-id="191cc-154">国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="191cc-154">national number</span></span>
  
<span data-ttu-id="191cc-155">social security number
</span><span class="sxs-lookup"><span data-stu-id="191cc-155">social security number</span></span>
  
<span data-ttu-id="191cc-156">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="191cc-156">nationalnumber#</span></span>
  
<span data-ttu-id="191cc-157">ssn #</span><span class="sxs-lookup"><span data-stu-id="191cc-157">ssn#</span></span>
  
<span data-ttu-id="191cc-158">ssn</span><span class="sxs-lookup"><span data-stu-id="191cc-158">ssn</span></span>
  
<span data-ttu-id="191cc-159">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="191cc-159">nationalnumber</span></span>
  
<span data-ttu-id="191cc-160">bnn #</span><span class="sxs-lookup"><span data-stu-id="191cc-160">bnn#</span></span>
  
<span data-ttu-id="191cc-161">bnn</span><span class="sxs-lookup"><span data-stu-id="191cc-161">bnn</span></span>
  
<span data-ttu-id="191cc-162">个人标识号</span><span class="sxs-lookup"><span data-stu-id="191cc-162">personal id number</span></span>
  
<span data-ttu-id="191cc-163">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="191cc-163">personalidnumber#</span></span>
  
<span data-ttu-id="191cc-164">numéro 国家/地区</span><span class="sxs-lookup"><span data-stu-id="191cc-164">numéro national</span></span>
  
<span data-ttu-id="191cc-165">numéro de sécurité
</span><span class="sxs-lookup"><span data-stu-id="191cc-165">numéro de sécurité</span></span>
  
<span data-ttu-id="191cc-166">numéro d'assuré</span><span class="sxs-lookup"><span data-stu-id="191cc-166">numéro d'assuré</span></span>
  
<span data-ttu-id="191cc-167">identifiant 国家/地区</span><span class="sxs-lookup"><span data-stu-id="191cc-167">identifiant national</span></span>
  
<span data-ttu-id="191cc-168">identifiantnational #</span><span class="sxs-lookup"><span data-stu-id="191cc-168">identifiantnational#</span></span>
  
<span data-ttu-id="191cc-169">numéronational #</span><span class="sxs-lookup"><span data-stu-id="191cc-169">numéronational#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="191cc-170">克罗地亚</span><span class="sxs-lookup"><span data-stu-id="191cc-170">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="191cc-171">格式</span><span class="sxs-lookup"><span data-stu-id="191cc-171">Format</span></span>

<span data-ttu-id="191cc-172">没有空格和分隔符 11 位数字</span><span class="sxs-lookup"><span data-stu-id="191cc-172">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="191cc-173">模式</span><span class="sxs-lookup"><span data-stu-id="191cc-173">Pattern</span></span>

 <span data-ttu-id="191cc-174">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="191cc-174">11 digits:</span></span> 
  
-  <span data-ttu-id="191cc-175">10 位数字</span><span class="sxs-lookup"><span data-stu-id="191cc-175">Ten digits</span></span> 
    
- <span data-ttu-id="191cc-176">一个检查数字</span><span class="sxs-lookup"><span data-stu-id="191cc-176">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="191cc-177">校验和</span><span class="sxs-lookup"><span data-stu-id="191cc-177">Checksum</span></span>

<span data-ttu-id="191cc-178">是</span><span class="sxs-lookup"><span data-stu-id="191cc-178">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="191cc-179">定义</span><span class="sxs-lookup"><span data-stu-id="191cc-179">Definition</span></span>

<span data-ttu-id="191cc-180">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="191cc-180">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="191cc-181">该函数`Func_croatia_eu_ssn_or_equivalent`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="191cc-181">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="191cc-182">从关键字`Keywords_croatia_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="191cc-182">A keyword from  `Keywords_croatia_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="191cc-183">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="191cc-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="191cc-184">该函数`Func_croatia_eu_ssn_or_equivalent`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="191cc-184">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="191cc-185">Keywords</span><span class="sxs-lookup"><span data-stu-id="191cc-185">Keywords</span></span>

#### <a name="keywordscroatiaeussnorequivalent"></a><span data-ttu-id="191cc-186">Keywords_croatia_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="191cc-186">Keywords_croatia_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="191cc-187">个人识别号</span><span class="sxs-lookup"><span data-stu-id="191cc-187">personal identification number</span></span>
  
<span data-ttu-id="191cc-188">主公民号码</span><span class="sxs-lookup"><span data-stu-id="191cc-188">master citizen number</span></span>
  
<span data-ttu-id="191cc-189">国家/地区标识号</span><span class="sxs-lookup"><span data-stu-id="191cc-189">national identification number</span></span>
  
<span data-ttu-id="191cc-190">social security number
</span><span class="sxs-lookup"><span data-stu-id="191cc-190">social security number</span></span>
  
<span data-ttu-id="191cc-191">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="191cc-191">nationalnumber#</span></span>
  
<span data-ttu-id="191cc-192">ssn #</span><span class="sxs-lookup"><span data-stu-id="191cc-192">ssn#</span></span>
  
<span data-ttu-id="191cc-193">ssn</span><span class="sxs-lookup"><span data-stu-id="191cc-193">ssn</span></span>
  
<span data-ttu-id="191cc-194">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="191cc-194">nationalnumber</span></span>
  
<span data-ttu-id="191cc-195">bnn #</span><span class="sxs-lookup"><span data-stu-id="191cc-195">bnn#</span></span>
  
<span data-ttu-id="191cc-196">bnn</span><span class="sxs-lookup"><span data-stu-id="191cc-196">bnn</span></span>
  
<span data-ttu-id="191cc-197">个人标识号</span><span class="sxs-lookup"><span data-stu-id="191cc-197">personal id number</span></span>
  
<span data-ttu-id="191cc-198">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="191cc-198">personalidnumber#</span></span>
  
<span data-ttu-id="191cc-199">oib</span><span class="sxs-lookup"><span data-stu-id="191cc-199">oib</span></span>
  
<span data-ttu-id="191cc-200">osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="191cc-200">osobni identifikacijski broj</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="191cc-201">捷克共和国</span><span class="sxs-lookup"><span data-stu-id="191cc-201">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="191cc-202">格式</span><span class="sxs-lookup"><span data-stu-id="191cc-202">Format</span></span>

<span data-ttu-id="191cc-203">10 位数字和反斜杠中指定的模式</span><span class="sxs-lookup"><span data-stu-id="191cc-203">Ten digits and a backslash in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="191cc-204">模式</span><span class="sxs-lookup"><span data-stu-id="191cc-204">Pattern</span></span>

<span data-ttu-id="191cc-205">10 位数字和反斜杠：</span><span class="sxs-lookup"><span data-stu-id="191cc-205">Ten digits and a backslash:</span></span>
  
- <span data-ttu-id="191cc-206">对应于出生日期 (YYMMDD) 的 6 个数字：</span><span class="sxs-lookup"><span data-stu-id="191cc-206">Six digits that correspond to the birth date (YYMMDD):</span></span> 
    
- <span data-ttu-id="191cc-207">反斜杠</span><span class="sxs-lookup"><span data-stu-id="191cc-207">A backslash</span></span>
    
- <span data-ttu-id="191cc-208">与用于分隔人员在相同日期出生日期序列号对应的三个数字</span><span class="sxs-lookup"><span data-stu-id="191cc-208">Three digits that correspond to a serial number that separates persons born on the same date</span></span>
    
- <span data-ttu-id="191cc-209">一个检查数字</span><span class="sxs-lookup"><span data-stu-id="191cc-209">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="191cc-210">校验和</span><span class="sxs-lookup"><span data-stu-id="191cc-210">Checksum</span></span>

<span data-ttu-id="191cc-211">是</span><span class="sxs-lookup"><span data-stu-id="191cc-211">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="191cc-212">定义</span><span class="sxs-lookup"><span data-stu-id="191cc-212">Definition</span></span>

<span data-ttu-id="191cc-213">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="191cc-213">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="191cc-214">该函数`Func_czech_republic_eu_ssn_or_equivalent`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="191cc-214">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="191cc-215">从关键字`Keywords_czech_republic_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="191cc-215">A keyword from  `Keywords_czech_republic_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="191cc-216">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="191cc-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="191cc-217">该函数`Func_czech_republic_eu_ssn_or_equivalent`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="191cc-217">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="191cc-218">Keywords</span><span class="sxs-lookup"><span data-stu-id="191cc-218">Keywords</span></span>

#### <a name="keywordsczechrepubliceussnorequivalent"></a><span data-ttu-id="191cc-219">Keywords_czech_republic_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="191cc-219">Keywords_czech_republic_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="191cc-220">出生号码</span><span class="sxs-lookup"><span data-stu-id="191cc-220">birth number</span></span>
  
<span data-ttu-id="191cc-221">国家/地区标识号</span><span class="sxs-lookup"><span data-stu-id="191cc-221">national identification number</span></span>
  
<span data-ttu-id="191cc-222">个人识别号</span><span class="sxs-lookup"><span data-stu-id="191cc-222">personal identification number</span></span>
  
<span data-ttu-id="191cc-223">social security number
</span><span class="sxs-lookup"><span data-stu-id="191cc-223">social security number</span></span>
  
<span data-ttu-id="191cc-224">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="191cc-224">nationalnumber#</span></span>
  
<span data-ttu-id="191cc-225">ssn #</span><span class="sxs-lookup"><span data-stu-id="191cc-225">ssn#</span></span>
  
<span data-ttu-id="191cc-226">ssn</span><span class="sxs-lookup"><span data-stu-id="191cc-226">ssn</span></span>
  
<span data-ttu-id="191cc-227">国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="191cc-227">national number</span></span>
  
<span data-ttu-id="191cc-228">个人标识号</span><span class="sxs-lookup"><span data-stu-id="191cc-228">personal id number</span></span>
  
<span data-ttu-id="191cc-229">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="191cc-229">personalidnumber#</span></span>
  
<span data-ttu-id="191cc-230">rč</span><span class="sxs-lookup"><span data-stu-id="191cc-230">rč</span></span>
  
<span data-ttu-id="191cc-231">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="191cc-231">rodné číslo</span></span>
  
<span data-ttu-id="191cc-232">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="191cc-232">rodne cislo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="191cc-233">丹麦</span><span class="sxs-lookup"><span data-stu-id="191cc-233">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="191cc-234">格式</span><span class="sxs-lookup"><span data-stu-id="191cc-234">Format</span></span>

<span data-ttu-id="191cc-235">10 位数字和连字符中指定的模式</span><span class="sxs-lookup"><span data-stu-id="191cc-235">Ten digits and a hyphen in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="191cc-236">模式</span><span class="sxs-lookup"><span data-stu-id="191cc-236">Pattern</span></span>

<span data-ttu-id="191cc-237">10 位数字和连字符：</span><span class="sxs-lookup"><span data-stu-id="191cc-237">Ten digits and a hyphen:</span></span>
  
- <span data-ttu-id="191cc-238">对应于出生日期月日的 6 个数字</span><span class="sxs-lookup"><span data-stu-id="191cc-238">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="191cc-239">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="191cc-239">A hyphen</span></span>
    
- <span data-ttu-id="191cc-240">四位数字对应序列号</span><span class="sxs-lookup"><span data-stu-id="191cc-240">Four digits that correspond to a sequence number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="191cc-241">校验和</span><span class="sxs-lookup"><span data-stu-id="191cc-241">Checksum</span></span>

<span data-ttu-id="191cc-242">是</span><span class="sxs-lookup"><span data-stu-id="191cc-242">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="191cc-243">定义</span><span class="sxs-lookup"><span data-stu-id="191cc-243">Definition</span></span>

<span data-ttu-id="191cc-244">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="191cc-244">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="191cc-245">该函数`Func_denmark_eu_ssn_or_equivalent`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="191cc-245">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="191cc-246">从关键字`Keywords_denmark_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="191cc-246">A keyword from  `Keywords_denmark_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="191cc-247">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="191cc-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="191cc-248">该函数`Func_denmark_eu_ssn_or_equivalent`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="191cc-248">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="191cc-249">Keywords</span><span class="sxs-lookup"><span data-stu-id="191cc-249">Keywords</span></span>

#### <a name="keywordsdenmarkeussnorequivalent"></a><span data-ttu-id="191cc-250">Keywords_denmark_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="191cc-250">Keywords_denmark_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="191cc-251">个人识别号</span><span class="sxs-lookup"><span data-stu-id="191cc-251">personal identification number</span></span>
  
<span data-ttu-id="191cc-252">国家/地区标识号</span><span class="sxs-lookup"><span data-stu-id="191cc-252">national identification number</span></span>
  
<span data-ttu-id="191cc-253">social security number
</span><span class="sxs-lookup"><span data-stu-id="191cc-253">social security number</span></span>
  
<span data-ttu-id="191cc-254">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="191cc-254">nationalnumber#</span></span>
  
<span data-ttu-id="191cc-255">ssn #</span><span class="sxs-lookup"><span data-stu-id="191cc-255">ssn#</span></span>
  
<span data-ttu-id="191cc-256">ssn</span><span class="sxs-lookup"><span data-stu-id="191cc-256">ssn</span></span>
  
<span data-ttu-id="191cc-257">国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="191cc-257">national number</span></span>
  
<span data-ttu-id="191cc-258">个人标识号</span><span class="sxs-lookup"><span data-stu-id="191cc-258">personal id number</span></span>
  
<span data-ttu-id="191cc-259">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="191cc-259">personalidnumber#</span></span>
  
<span data-ttu-id="191cc-260">cpr nummer</span><span class="sxs-lookup"><span data-stu-id="191cc-260">cpr-nummer</span></span>
  
<span data-ttu-id="191cc-261">personnummer</span><span class="sxs-lookup"><span data-stu-id="191cc-261">personnummer</span></span>
  
## <a name="finland"></a><span data-ttu-id="191cc-262">芬兰</span><span class="sxs-lookup"><span data-stu-id="191cc-262">Finland</span></span>

### <a name="format"></a><span data-ttu-id="191cc-263">格式</span><span class="sxs-lookup"><span data-stu-id="191cc-263">Format</span></span>

<span data-ttu-id="191cc-264">以指定格式 11 个字符组合</span><span class="sxs-lookup"><span data-stu-id="191cc-264">An 11-character combination in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="191cc-265">模式</span><span class="sxs-lookup"><span data-stu-id="191cc-265">Pattern</span></span>

<span data-ttu-id="191cc-266">以指定格式 11 个字符组合：</span><span class="sxs-lookup"><span data-stu-id="191cc-266">An 11-character combination in the specified format:</span></span>
  
-  <span data-ttu-id="191cc-267">六位数字</span><span class="sxs-lookup"><span data-stu-id="191cc-267">Six digits</span></span> 
    
- <span data-ttu-id="191cc-268">一个实例下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="191cc-268">One instance of one of the following:</span></span>
    
  - <span data-ttu-id="191cc-269">Plus 符号</span><span class="sxs-lookup"><span data-stu-id="191cc-269">Plus symbol</span></span>
    
  - <span data-ttu-id="191cc-270">减号</span><span class="sxs-lookup"><span data-stu-id="191cc-270">Minus symbol</span></span>
    
  - <span data-ttu-id="191cc-271">字母"A"（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="191cc-271">The letter "A" (not case-sensitive)</span></span>
    
- <span data-ttu-id="191cc-272">三位数字</span><span class="sxs-lookup"><span data-stu-id="191cc-272">Three digits</span></span>
    
- <span data-ttu-id="191cc-273">一个字母或一位数</span><span class="sxs-lookup"><span data-stu-id="191cc-273">One letter or one digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="191cc-274">校验和</span><span class="sxs-lookup"><span data-stu-id="191cc-274">Checksum</span></span>

<span data-ttu-id="191cc-275">是</span><span class="sxs-lookup"><span data-stu-id="191cc-275">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="191cc-276">定义</span><span class="sxs-lookup"><span data-stu-id="191cc-276">Definition</span></span>

<span data-ttu-id="191cc-277">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="191cc-277">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="191cc-278">该函数`Func_finland_eu_ssn_or_equivalent`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="191cc-278">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="191cc-279">从关键字`Keywords_finland_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="191cc-279">A keyword from  `Keywords_finland_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="191cc-280">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="191cc-280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="191cc-281">该函数`Func_finland_eu_ssn_or_equivalent`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="191cc-281">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="191cc-282">Keywords</span><span class="sxs-lookup"><span data-stu-id="191cc-282">Keywords</span></span>

#### <a name="keywordsfinlandeussnorequivalent"></a><span data-ttu-id="191cc-283">Keywords_finland_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="191cc-283">Keywords_finland_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="191cc-284">identification number
</span><span class="sxs-lookup"><span data-stu-id="191cc-284">identification number</span></span>
  
<span data-ttu-id="191cc-285">个人 id</span><span class="sxs-lookup"><span data-stu-id="191cc-285">personal id</span></span>
  
<span data-ttu-id="191cc-286">标识号</span><span class="sxs-lookup"><span data-stu-id="191cc-286">identity number</span></span>
  
<span data-ttu-id="191cc-287">芬兰国家/地区 id 号</span><span class="sxs-lookup"><span data-stu-id="191cc-287">finnish national id number</span></span>
  
<span data-ttu-id="191cc-288">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="191cc-288">personalidnumber#</span></span>
  
<span data-ttu-id="191cc-289">国家/地区标识号</span><span class="sxs-lookup"><span data-stu-id="191cc-289">national identification number</span></span>
  
<span data-ttu-id="191cc-290">id 号</span><span class="sxs-lookup"><span data-stu-id="191cc-290">id number</span></span>
  
<span data-ttu-id="191cc-291">国家/地区 id 没有。</span><span class="sxs-lookup"><span data-stu-id="191cc-291">national id no.</span></span>
  
<span data-ttu-id="191cc-292">国家/地区 id 号</span><span class="sxs-lookup"><span data-stu-id="191cc-292">national id number</span></span>
  
<span data-ttu-id="191cc-293">id 没有</span><span class="sxs-lookup"><span data-stu-id="191cc-293">id no</span></span>
  
<span data-ttu-id="191cc-294">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="191cc-294">tunnistenumero</span></span>
  
<span data-ttu-id="191cc-295">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="191cc-295">henkilötunnus</span></span>
  
<span data-ttu-id="191cc-296">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="191cc-296">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="191cc-297">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="191cc-297">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="191cc-298">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="191cc-298">identiteetti numero</span></span>
  
<span data-ttu-id="191cc-299">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="191cc-299">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="191cc-300">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="191cc-300">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="191cc-301">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="191cc-301">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="191cc-302">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="191cc-302">tunnusnumero</span></span>
  
<span data-ttu-id="191cc-303">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="191cc-303">kansallinen tunnus numero</span></span>
  
<span data-ttu-id="191cc-304">hetu</span><span class="sxs-lookup"><span data-stu-id="191cc-304">hetu</span></span>
  
## <a name="france"></a><span data-ttu-id="191cc-305">法国</span><span class="sxs-lookup"><span data-stu-id="191cc-305">France</span></span>

<span data-ttu-id="191cc-306">有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"法国社会保险号 (INSEE)"。</span><span class="sxs-lookup"><span data-stu-id="191cc-306">For details, see the section "France Social Security Number (INSEE)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="191cc-307">德国</span><span class="sxs-lookup"><span data-stu-id="191cc-307">Germany</span></span>

<span data-ttu-id="191cc-308">有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"德国身份证编号"。</span><span class="sxs-lookup"><span data-stu-id="191cc-308">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="191cc-309">希腊</span><span class="sxs-lookup"><span data-stu-id="191cc-309">Greece</span></span>

<span data-ttu-id="191cc-310">有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"希腊国家 ID 卡"。</span><span class="sxs-lookup"><span data-stu-id="191cc-310">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="191cc-311">匈牙利</span><span class="sxs-lookup"><span data-stu-id="191cc-311">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="191cc-312">格式</span><span class="sxs-lookup"><span data-stu-id="191cc-312">Format</span></span>

<span data-ttu-id="191cc-313">没有空格和分隔符的九个数字</span><span class="sxs-lookup"><span data-stu-id="191cc-313">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="191cc-314">模式</span><span class="sxs-lookup"><span data-stu-id="191cc-314">Pattern</span></span>

<span data-ttu-id="191cc-315">九个数字</span><span class="sxs-lookup"><span data-stu-id="191cc-315">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="191cc-316">校验和</span><span class="sxs-lookup"><span data-stu-id="191cc-316">Checksum</span></span>

<span data-ttu-id="191cc-317">是</span><span class="sxs-lookup"><span data-stu-id="191cc-317">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="191cc-318">定义</span><span class="sxs-lookup"><span data-stu-id="191cc-318">Definition</span></span>

<span data-ttu-id="191cc-319">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="191cc-319">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="191cc-320">该函数`Func_hungary_eu_ssn_or_equivalent`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="191cc-320">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="191cc-321">从关键字`Keywords_hungary_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="191cc-321">A keyword from  `Keywords_hungary_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="191cc-322">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="191cc-322">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="191cc-323">该函数`Func_hungary_eu_ssn_or_equivalent`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="191cc-323">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="191cc-324">Keywords</span><span class="sxs-lookup"><span data-stu-id="191cc-324">Keywords</span></span>

#### <a name="keywordshungaryeussnorequivalent"></a><span data-ttu-id="191cc-325">Keywords_hungary_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="191cc-325">Keywords_hungary_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="191cc-326">匈牙利语社会保险号码</span><span class="sxs-lookup"><span data-stu-id="191cc-326">hungarian social security number</span></span>
  
<span data-ttu-id="191cc-327">social security number
</span><span class="sxs-lookup"><span data-stu-id="191cc-327">social security number</span></span>
  
<span data-ttu-id="191cc-328">socialsecuritynumber #</span><span class="sxs-lookup"><span data-stu-id="191cc-328">socialsecuritynumber#</span></span>
  
<span data-ttu-id="191cc-329">hssn #</span><span class="sxs-lookup"><span data-stu-id="191cc-329">hssn#</span></span>
  
<span data-ttu-id="191cc-330">socialsecuritynno</span><span class="sxs-lookup"><span data-stu-id="191cc-330">socialsecuritynno</span></span>
  
<span data-ttu-id="191cc-331">hssn</span><span class="sxs-lookup"><span data-stu-id="191cc-331">hssn</span></span>
  
<span data-ttu-id="191cc-332">泰姬陵</span><span class="sxs-lookup"><span data-stu-id="191cc-332">taj</span></span>
  
<span data-ttu-id="191cc-333">泰姬陵 #</span><span class="sxs-lookup"><span data-stu-id="191cc-333">taj#</span></span>
  
<span data-ttu-id="191cc-334">ssn</span><span class="sxs-lookup"><span data-stu-id="191cc-334">ssn</span></span>
  
<span data-ttu-id="191cc-335">ssn #</span><span class="sxs-lookup"><span data-stu-id="191cc-335">ssn#</span></span>
  
<span data-ttu-id="191cc-336">社会保障没有</span><span class="sxs-lookup"><span data-stu-id="191cc-336">social security no</span></span>
  
<span data-ttu-id="191cc-337">áfa</span><span class="sxs-lookup"><span data-stu-id="191cc-337">áfa</span></span>
  
<span data-ttu-id="191cc-338">közösségi adószám</span><span class="sxs-lookup"><span data-stu-id="191cc-338">közösségi adószám</span></span>
  
<span data-ttu-id="191cc-339">általános forgalmi adó szám</span><span class="sxs-lookup"><span data-stu-id="191cc-339">általános forgalmi adó szám</span></span>
  
<span data-ttu-id="191cc-340">hozzáadottérték adó</span><span class="sxs-lookup"><span data-stu-id="191cc-340">hozzáadottérték adó</span></span>
  
<span data-ttu-id="191cc-341">áfa szám</span><span class="sxs-lookup"><span data-stu-id="191cc-341">áfa szám</span></span>
  
<span data-ttu-id="191cc-342">magyar áfa szám</span><span class="sxs-lookup"><span data-stu-id="191cc-342">magyar áfa szám</span></span>
  
## <a name="portugal"></a><span data-ttu-id="191cc-343">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="191cc-343">Portugal</span></span>

<span data-ttu-id="191cc-344">有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"葡萄牙公民卡号"。</span><span class="sxs-lookup"><span data-stu-id="191cc-344">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="spain"></a><span data-ttu-id="191cc-345">西班牙</span><span class="sxs-lookup"><span data-stu-id="191cc-345">Spain</span></span>

<span data-ttu-id="191cc-346">有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"西班牙社会保险号码 (SSN)"。</span><span class="sxs-lookup"><span data-stu-id="191cc-346">For details, see the section "Spain Social Security Number (SSN)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="sweden"></a><span data-ttu-id="191cc-347">瑞典</span><span class="sxs-lookup"><span data-stu-id="191cc-347">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="191cc-348">格式</span><span class="sxs-lookup"><span data-stu-id="191cc-348">Format</span></span>

<span data-ttu-id="191cc-349">没有空格和分隔符的 12 个数字</span><span class="sxs-lookup"><span data-stu-id="191cc-349">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="191cc-350">模式</span><span class="sxs-lookup"><span data-stu-id="191cc-350">Pattern</span></span>

<span data-ttu-id="191cc-351">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="191cc-351">12 digits:</span></span>
  
-  <span data-ttu-id="191cc-352">八个数字对应于出生日期 （年月日）</span><span class="sxs-lookup"><span data-stu-id="191cc-352">Eight digits that correspond to the birth date (YYYYMMDD)</span></span> 
    
- <span data-ttu-id="191cc-353">三个转成序列号对应的数字位置：</span><span class="sxs-lookup"><span data-stu-id="191cc-353">Three digits that correspond to a serial number where:</span></span> 
    
  - <span data-ttu-id="191cc-354">序列号中的最后一位指示通过分配的奇数的男性和女性为偶数的性别</span><span class="sxs-lookup"><span data-stu-id="191cc-354">The last digit in the serial number indicates gender by the assignment of an odd number for male and an even number for female</span></span>
    
  - <span data-ttu-id="191cc-355">过去 1990，分配的序列号通过信到县或其中出生号码的持有者 （如果出生日期之前 1947年） 其中他/她具有已生活，根据税费记录 1947，年 1 月 1，与特殊代码 (通常为 7 位数字 9) 的移民</span><span class="sxs-lookup"><span data-stu-id="191cc-355">Up to 1990, the assignment of serial number corresponded to the county where the bearer of the number was born or (if born before 1947) where he/she had been living, according to tax records, on January 1, 1947, with a special code (usually 9 as the 7th digit) for immigrants</span></span> 
    
- <span data-ttu-id="191cc-356">一个检查数字</span><span class="sxs-lookup"><span data-stu-id="191cc-356">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="191cc-357">校验和</span><span class="sxs-lookup"><span data-stu-id="191cc-357">Checksum</span></span>

<span data-ttu-id="191cc-358">是</span><span class="sxs-lookup"><span data-stu-id="191cc-358">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="191cc-359">定义</span><span class="sxs-lookup"><span data-stu-id="191cc-359">Definition</span></span>

<span data-ttu-id="191cc-360">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="191cc-360">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="191cc-361">该函数`Func_sweden_eu_ssn_or_equivalent`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="191cc-361">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="191cc-362">从关键字`Keywords_sweden_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="191cc-362">A keyword from  `Keywords_sweden_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="191cc-363">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="191cc-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="191cc-364">该函数`Func_sweden_eu_ssn_or_equivalent`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="191cc-364">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="191cc-365">Keywords</span><span class="sxs-lookup"><span data-stu-id="191cc-365">Keywords</span></span>

#### <a name="keywordsswedeneussnorequivalent"></a><span data-ttu-id="191cc-366">Keywords_sweden_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="191cc-366">Keywords_sweden_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="191cc-367">个人标识号</span><span class="sxs-lookup"><span data-stu-id="191cc-367">personal id number</span></span>
  
<span data-ttu-id="191cc-368">identification number
</span><span class="sxs-lookup"><span data-stu-id="191cc-368">identification number</span></span>
  
<span data-ttu-id="191cc-369">个人 id 没有</span><span class="sxs-lookup"><span data-stu-id="191cc-369">personal id no</span></span>
  
<span data-ttu-id="191cc-370">标识无</span><span class="sxs-lookup"><span data-stu-id="191cc-370">identity no</span></span>
  
<span data-ttu-id="191cc-371">标识无</span><span class="sxs-lookup"><span data-stu-id="191cc-371">identification no</span></span>
  
<span data-ttu-id="191cc-372">个人标识号没有</span><span class="sxs-lookup"><span data-stu-id="191cc-372">personal identification no</span></span>
  
<span data-ttu-id="191cc-373">personnummer id</span><span class="sxs-lookup"><span data-stu-id="191cc-373">personnummer id</span></span>
  
<span data-ttu-id="191cc-374">personligt id nummer</span><span class="sxs-lookup"><span data-stu-id="191cc-374">personligt id-nummer</span></span>
  
<span data-ttu-id="191cc-375">unikt id nummer</span><span class="sxs-lookup"><span data-stu-id="191cc-375">unikt id-nummer</span></span>
  
<span data-ttu-id="191cc-376">personnummer</span><span class="sxs-lookup"><span data-stu-id="191cc-376">personnummer</span></span>
  
<span data-ttu-id="191cc-377">identifikationsnumret</span><span class="sxs-lookup"><span data-stu-id="191cc-377">identifikationsnumret</span></span>
  
<span data-ttu-id="191cc-378">personnummer #</span><span class="sxs-lookup"><span data-stu-id="191cc-378">personnummer#</span></span>
  
<span data-ttu-id="191cc-379">identifikationsnumret #</span><span class="sxs-lookup"><span data-stu-id="191cc-379">identifikationsnumret#</span></span>
  
## <a name="see-also"></a><span data-ttu-id="191cc-380">另请参阅</span><span class="sxs-lookup"><span data-stu-id="191cc-380">See also</span></span>

[<span data-ttu-id="191cc-381">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="191cc-381">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

