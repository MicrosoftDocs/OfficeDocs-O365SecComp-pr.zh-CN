---
title: 欧盟社会安全号码或等效 ID
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主题介绍当数据丢失防护 (DLP) 策略检测到欧盟社会保险号码或等效 ID 敏感信息类型时, 将会查找什么。 此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。
ms.openlocfilehash: c0c808eafa52209c79f3b4e8a2113f587fd8a771
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32255550"
---
# <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="380cd-104">欧盟社会安全号码或等效 ID</span><span class="sxs-lookup"><span data-stu-id="380cd-104">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="380cd-105">本主题介绍当数据丢失防护 (DLP) 策略检测到欧盟社会保险号码 (SSN) 或等效 ID 敏感信息类型时, 会查找什么内容。</span><span class="sxs-lookup"><span data-stu-id="380cd-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Social Security Number (SSN) or Equivalent ID sensitive information type.</span></span> <span data-ttu-id="380cd-106">此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。</span><span class="sxs-lookup"><span data-stu-id="380cd-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="380cd-107">奥地利</span><span class="sxs-lookup"><span data-stu-id="380cd-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="380cd-108">Format</span><span class="sxs-lookup"><span data-stu-id="380cd-108">Format</span></span>

<span data-ttu-id="380cd-109">以指定格式表示的10个数字</span><span class="sxs-lookup"><span data-stu-id="380cd-109">10 digits in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="380cd-110">模式</span><span class="sxs-lookup"><span data-stu-id="380cd-110">Pattern</span></span>

<span data-ttu-id="380cd-111">10 个数字：</span><span class="sxs-lookup"><span data-stu-id="380cd-111">10 digits:</span></span>
  
-  <span data-ttu-id="380cd-112">与序列号对应的三个数字</span><span class="sxs-lookup"><span data-stu-id="380cd-112">Three digits that correspond to a serial number</span></span> 
    
- <span data-ttu-id="380cd-113">一个校验位</span><span class="sxs-lookup"><span data-stu-id="380cd-113">One check digit</span></span>
    
- <span data-ttu-id="380cd-114">与出生日期对应的6个数字 (DDMMYY)</span><span class="sxs-lookup"><span data-stu-id="380cd-114">Six digits that correspond to the birth date (DDMMYY)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="380cd-115">校验和</span><span class="sxs-lookup"><span data-stu-id="380cd-115">Checksum</span></span>

<span data-ttu-id="380cd-116">是</span><span class="sxs-lookup"><span data-stu-id="380cd-116">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="380cd-117">定义</span><span class="sxs-lookup"><span data-stu-id="380cd-117">Definition</span></span>

<span data-ttu-id="380cd-118">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="380cd-118">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="380cd-119">函数`Func_austria_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="380cd-119">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="380cd-120">找到了中`Keywords_austria_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="380cd-120">A keyword from  `Keywords_austria_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="380cd-121">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="380cd-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="380cd-122">函数`Func_austria_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="380cd-122">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="380cd-123">关键字</span><span class="sxs-lookup"><span data-stu-id="380cd-123">Keywords</span></span>

#### <a name="keywordsaustriaeussnorequivalent"></a><span data-ttu-id="380cd-124">Keywords_austria_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="380cd-124">Keywords_austria_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="380cd-125">社会保障号</span><span class="sxs-lookup"><span data-stu-id="380cd-125">social security no</span></span>
  
<span data-ttu-id="380cd-126">social security number</span><span class="sxs-lookup"><span data-stu-id="380cd-126">social security number</span></span>
  
<span data-ttu-id="380cd-127">social security code</span><span class="sxs-lookup"><span data-stu-id="380cd-127">social security code</span></span>
  
<span data-ttu-id="380cd-128">保险号</span><span class="sxs-lookup"><span data-stu-id="380cd-128">insurance number</span></span>
  
<span data-ttu-id="380cd-129">奥地利 ssn</span><span class="sxs-lookup"><span data-stu-id="380cd-129">austrian ssn</span></span>
  
<span data-ttu-id="380cd-130">ssn</span><span class="sxs-lookup"><span data-stu-id="380cd-130">ssn#</span></span>
  
<span data-ttu-id="380cd-131">ssn</span><span class="sxs-lookup"><span data-stu-id="380cd-131">ssn</span></span>
  
<span data-ttu-id="380cd-132">保险费代码</span><span class="sxs-lookup"><span data-stu-id="380cd-132">insurance code</span></span>
  
<span data-ttu-id="380cd-133">保险代码 #</span><span class="sxs-lookup"><span data-stu-id="380cd-133">insurance code#</span></span>
  
<span data-ttu-id="380cd-134">socialsecurityno #</span><span class="sxs-lookup"><span data-stu-id="380cd-134">socialsecurityno#</span></span>
  
<span data-ttu-id="380cd-135">sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="380cd-135">sozialversicherungsnummer</span></span>
  
<span data-ttu-id="380cd-136">soziale sicherheit kein</span><span class="sxs-lookup"><span data-stu-id="380cd-136">soziale sicherheit kein</span></span>
  
<span data-ttu-id="380cd-137">versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="380cd-137">versicherungsnummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="380cd-138">比利时</span><span class="sxs-lookup"><span data-stu-id="380cd-138">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="380cd-139">Format</span><span class="sxs-lookup"><span data-stu-id="380cd-139">Format</span></span>

<span data-ttu-id="380cd-140">11位数, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="380cd-140">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="380cd-141">模式</span><span class="sxs-lookup"><span data-stu-id="380cd-141">Pattern</span></span>

<span data-ttu-id="380cd-142">11 个数字</span><span class="sxs-lookup"><span data-stu-id="380cd-142">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="380cd-143">校验和</span><span class="sxs-lookup"><span data-stu-id="380cd-143">Checksum</span></span>

<span data-ttu-id="380cd-144">是</span><span class="sxs-lookup"><span data-stu-id="380cd-144">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="380cd-145">定义</span><span class="sxs-lookup"><span data-stu-id="380cd-145">Definition</span></span>

<span data-ttu-id="380cd-146">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="380cd-146">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="380cd-147">函数`Func_belgium_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="380cd-147">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="380cd-148">找到了中`Keywords_belgium_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="380cd-148">A keyword from  `Keywords_belgium_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="380cd-149">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="380cd-149">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="380cd-150">函数`Func_belgium_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="380cd-150">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="380cd-151">关键字</span><span class="sxs-lookup"><span data-stu-id="380cd-151">Keywords</span></span>

#### <a name="keywordsbelgiumeussnorequivalent"></a><span data-ttu-id="380cd-152">Keywords_belgium_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="380cd-152">Keywords_belgium_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="380cd-153">比利时国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="380cd-153">belgian national number</span></span>
  
<span data-ttu-id="380cd-154">国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="380cd-154">national number</span></span>
  
<span data-ttu-id="380cd-155">social security number</span><span class="sxs-lookup"><span data-stu-id="380cd-155">social security number</span></span>
  
<span data-ttu-id="380cd-156">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="380cd-156">nationalnumber#</span></span>
  
<span data-ttu-id="380cd-157">ssn</span><span class="sxs-lookup"><span data-stu-id="380cd-157">ssn#</span></span>
  
<span data-ttu-id="380cd-158">ssn</span><span class="sxs-lookup"><span data-stu-id="380cd-158">ssn</span></span>
  
<span data-ttu-id="380cd-159">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="380cd-159">nationalnumber</span></span>
  
<span data-ttu-id="380cd-160">bnn #</span><span class="sxs-lookup"><span data-stu-id="380cd-160">bnn#</span></span>
  
<span data-ttu-id="380cd-161">bnn</span><span class="sxs-lookup"><span data-stu-id="380cd-161">bnn</span></span>
  
<span data-ttu-id="380cd-162">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="380cd-162">personal id number</span></span>
  
<span data-ttu-id="380cd-163">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="380cd-163">personalidnumber#</span></span>
  
<span data-ttu-id="380cd-164">numéro 国家</span><span class="sxs-lookup"><span data-stu-id="380cd-164">numéro national</span></span>
  
<span data-ttu-id="380cd-165">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="380cd-165">numéro de sécurité</span></span>
  
<span data-ttu-id="380cd-166">numéro d'assuré</span><span class="sxs-lookup"><span data-stu-id="380cd-166">numéro d'assuré</span></span>
  
<span data-ttu-id="380cd-167">identifiant 国家</span><span class="sxs-lookup"><span data-stu-id="380cd-167">identifiant national</span></span>
  
<span data-ttu-id="380cd-168">identifiantnational #</span><span class="sxs-lookup"><span data-stu-id="380cd-168">identifiantnational#</span></span>
  
<span data-ttu-id="380cd-169">numéronational #</span><span class="sxs-lookup"><span data-stu-id="380cd-169">numéronational#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="380cd-170">克罗地亚</span><span class="sxs-lookup"><span data-stu-id="380cd-170">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="380cd-171">Format</span><span class="sxs-lookup"><span data-stu-id="380cd-171">Format</span></span>

<span data-ttu-id="380cd-172">11个数字, 无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="380cd-172">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="380cd-173">模式</span><span class="sxs-lookup"><span data-stu-id="380cd-173">Pattern</span></span>

 <span data-ttu-id="380cd-174">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="380cd-174">11 digits:</span></span> 
  
-  <span data-ttu-id="380cd-175">10位数字</span><span class="sxs-lookup"><span data-stu-id="380cd-175">Ten digits</span></span> 
    
- <span data-ttu-id="380cd-176">一个校验位</span><span class="sxs-lookup"><span data-stu-id="380cd-176">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="380cd-177">校验和</span><span class="sxs-lookup"><span data-stu-id="380cd-177">Checksum</span></span>

<span data-ttu-id="380cd-178">是</span><span class="sxs-lookup"><span data-stu-id="380cd-178">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="380cd-179">定义</span><span class="sxs-lookup"><span data-stu-id="380cd-179">Definition</span></span>

<span data-ttu-id="380cd-180">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="380cd-180">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="380cd-181">函数`Func_croatia_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="380cd-181">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="380cd-182">找到了中`Keywords_croatia_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="380cd-182">A keyword from  `Keywords_croatia_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="380cd-183">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="380cd-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="380cd-184">函数`Func_croatia_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="380cd-184">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="380cd-185">关键字</span><span class="sxs-lookup"><span data-stu-id="380cd-185">Keywords</span></span>

#### <a name="keywordscroatiaeussnorequivalent"></a><span data-ttu-id="380cd-186">Keywords_croatia_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="380cd-186">Keywords_croatia_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="380cd-187">个人标识号</span><span class="sxs-lookup"><span data-stu-id="380cd-187">personal identification number</span></span>
  
<span data-ttu-id="380cd-188">主公民号码</span><span class="sxs-lookup"><span data-stu-id="380cd-188">master citizen number</span></span>
  
<span data-ttu-id="380cd-189">national identification number</span><span class="sxs-lookup"><span data-stu-id="380cd-189">national identification number</span></span>
  
<span data-ttu-id="380cd-190">social security number</span><span class="sxs-lookup"><span data-stu-id="380cd-190">social security number</span></span>
  
<span data-ttu-id="380cd-191">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="380cd-191">nationalnumber#</span></span>
  
<span data-ttu-id="380cd-192">ssn</span><span class="sxs-lookup"><span data-stu-id="380cd-192">ssn#</span></span>
  
<span data-ttu-id="380cd-193">ssn</span><span class="sxs-lookup"><span data-stu-id="380cd-193">ssn</span></span>
  
<span data-ttu-id="380cd-194">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="380cd-194">nationalnumber</span></span>
  
<span data-ttu-id="380cd-195">bnn #</span><span class="sxs-lookup"><span data-stu-id="380cd-195">bnn#</span></span>
  
<span data-ttu-id="380cd-196">bnn</span><span class="sxs-lookup"><span data-stu-id="380cd-196">bnn</span></span>
  
<span data-ttu-id="380cd-197">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="380cd-197">personal id number</span></span>
  
<span data-ttu-id="380cd-198">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="380cd-198">personalidnumber#</span></span>
  
<span data-ttu-id="380cd-199">oib</span><span class="sxs-lookup"><span data-stu-id="380cd-199">oib</span></span>
  
<span data-ttu-id="380cd-200">osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="380cd-200">osobni identifikacijski broj</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="380cd-201">捷克共和国</span><span class="sxs-lookup"><span data-stu-id="380cd-201">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="380cd-202">Format</span><span class="sxs-lookup"><span data-stu-id="380cd-202">Format</span></span>

<span data-ttu-id="380cd-203">指定模式中的10个数字和一个反斜杠</span><span class="sxs-lookup"><span data-stu-id="380cd-203">Ten digits and a backslash in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="380cd-204">模式</span><span class="sxs-lookup"><span data-stu-id="380cd-204">Pattern</span></span>

<span data-ttu-id="380cd-205">10个数字和一个反斜杠:</span><span class="sxs-lookup"><span data-stu-id="380cd-205">Ten digits and a backslash:</span></span>
  
- <span data-ttu-id="380cd-206">与出生日期对应的6个数字 (YYMMDD):</span><span class="sxs-lookup"><span data-stu-id="380cd-206">Six digits that correspond to the birth date (YYMMDD):</span></span> 
    
- <span data-ttu-id="380cd-207">反斜杠</span><span class="sxs-lookup"><span data-stu-id="380cd-207">A backslash</span></span>
    
- <span data-ttu-id="380cd-208">与一个序列号相对应的三个数字, 用于分隔出生于同一日期的人员</span><span class="sxs-lookup"><span data-stu-id="380cd-208">Three digits that correspond to a serial number that separates persons born on the same date</span></span>
    
- <span data-ttu-id="380cd-209">一个校验位</span><span class="sxs-lookup"><span data-stu-id="380cd-209">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="380cd-210">校验和</span><span class="sxs-lookup"><span data-stu-id="380cd-210">Checksum</span></span>

<span data-ttu-id="380cd-211">是</span><span class="sxs-lookup"><span data-stu-id="380cd-211">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="380cd-212">定义</span><span class="sxs-lookup"><span data-stu-id="380cd-212">Definition</span></span>

<span data-ttu-id="380cd-213">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="380cd-213">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="380cd-214">函数`Func_czech_republic_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="380cd-214">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="380cd-215">找到了中`Keywords_czech_republic_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="380cd-215">A keyword from  `Keywords_czech_republic_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="380cd-216">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="380cd-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="380cd-217">函数`Func_czech_republic_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="380cd-217">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="380cd-218">关键字</span><span class="sxs-lookup"><span data-stu-id="380cd-218">Keywords</span></span>

#### <a name="keywordsczechrepubliceussnorequivalent"></a><span data-ttu-id="380cd-219">Keywords_czech_republic_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="380cd-219">Keywords_czech_republic_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="380cd-220">出生号码</span><span class="sxs-lookup"><span data-stu-id="380cd-220">birth number</span></span>
  
<span data-ttu-id="380cd-221">national identification number</span><span class="sxs-lookup"><span data-stu-id="380cd-221">national identification number</span></span>
  
<span data-ttu-id="380cd-222">个人标识号</span><span class="sxs-lookup"><span data-stu-id="380cd-222">personal identification number</span></span>
  
<span data-ttu-id="380cd-223">social security number</span><span class="sxs-lookup"><span data-stu-id="380cd-223">social security number</span></span>
  
<span data-ttu-id="380cd-224">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="380cd-224">nationalnumber#</span></span>
  
<span data-ttu-id="380cd-225">ssn</span><span class="sxs-lookup"><span data-stu-id="380cd-225">ssn#</span></span>
  
<span data-ttu-id="380cd-226">ssn</span><span class="sxs-lookup"><span data-stu-id="380cd-226">ssn</span></span>
  
<span data-ttu-id="380cd-227">国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="380cd-227">national number</span></span>
  
<span data-ttu-id="380cd-228">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="380cd-228">personal id number</span></span>
  
<span data-ttu-id="380cd-229">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="380cd-229">personalidnumber#</span></span>
  
<span data-ttu-id="380cd-230">rč</span><span class="sxs-lookup"><span data-stu-id="380cd-230">rč</span></span>
  
<span data-ttu-id="380cd-231">rodnéčíslo</span><span class="sxs-lookup"><span data-stu-id="380cd-231">rodné číslo</span></span>
  
<span data-ttu-id="380cd-232">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="380cd-232">rodne cislo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="380cd-233">丹麦</span><span class="sxs-lookup"><span data-stu-id="380cd-233">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="380cd-234">Format</span><span class="sxs-lookup"><span data-stu-id="380cd-234">Format</span></span>

<span data-ttu-id="380cd-235">指定模式中的10个数字和一个连字符</span><span class="sxs-lookup"><span data-stu-id="380cd-235">Ten digits and a hyphen in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="380cd-236">模式</span><span class="sxs-lookup"><span data-stu-id="380cd-236">Pattern</span></span>

<span data-ttu-id="380cd-237">10个数字和一个连字符:</span><span class="sxs-lookup"><span data-stu-id="380cd-237">Ten digits and a hyphen:</span></span>
  
- <span data-ttu-id="380cd-238">与出生日期对应的6个数字 (DDMMYY)</span><span class="sxs-lookup"><span data-stu-id="380cd-238">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="380cd-239">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="380cd-239">A hyphen</span></span>
    
- <span data-ttu-id="380cd-240">与序列号对应的四个数字</span><span class="sxs-lookup"><span data-stu-id="380cd-240">Four digits that correspond to a sequence number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="380cd-241">校验和</span><span class="sxs-lookup"><span data-stu-id="380cd-241">Checksum</span></span>

<span data-ttu-id="380cd-242">是</span><span class="sxs-lookup"><span data-stu-id="380cd-242">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="380cd-243">定义</span><span class="sxs-lookup"><span data-stu-id="380cd-243">Definition</span></span>

<span data-ttu-id="380cd-244">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="380cd-244">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="380cd-245">函数`Func_denmark_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="380cd-245">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="380cd-246">找到了中`Keywords_denmark_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="380cd-246">A keyword from  `Keywords_denmark_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="380cd-247">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="380cd-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="380cd-248">函数`Func_denmark_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="380cd-248">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="380cd-249">关键字</span><span class="sxs-lookup"><span data-stu-id="380cd-249">Keywords</span></span>

#### <a name="keywordsdenmarkeussnorequivalent"></a><span data-ttu-id="380cd-250">Keywords_denmark_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="380cd-250">Keywords_denmark_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="380cd-251">个人标识号</span><span class="sxs-lookup"><span data-stu-id="380cd-251">personal identification number</span></span>
  
<span data-ttu-id="380cd-252">national identification number</span><span class="sxs-lookup"><span data-stu-id="380cd-252">national identification number</span></span>
  
<span data-ttu-id="380cd-253">social security number</span><span class="sxs-lookup"><span data-stu-id="380cd-253">social security number</span></span>
  
<span data-ttu-id="380cd-254">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="380cd-254">nationalnumber#</span></span>
  
<span data-ttu-id="380cd-255">ssn</span><span class="sxs-lookup"><span data-stu-id="380cd-255">ssn#</span></span>
  
<span data-ttu-id="380cd-256">ssn</span><span class="sxs-lookup"><span data-stu-id="380cd-256">ssn</span></span>
  
<span data-ttu-id="380cd-257">国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="380cd-257">national number</span></span>
  
<span data-ttu-id="380cd-258">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="380cd-258">personal id number</span></span>
  
<span data-ttu-id="380cd-259">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="380cd-259">personalidnumber#</span></span>
  
<span data-ttu-id="380cd-260">cpr-nummer</span><span class="sxs-lookup"><span data-stu-id="380cd-260">cpr-nummer</span></span>
  
<span data-ttu-id="380cd-261">personnummer</span><span class="sxs-lookup"><span data-stu-id="380cd-261">personnummer</span></span>
  
## <a name="finland"></a><span data-ttu-id="380cd-262">芬兰</span><span class="sxs-lookup"><span data-stu-id="380cd-262">Finland</span></span>

### <a name="format"></a><span data-ttu-id="380cd-263">Format</span><span class="sxs-lookup"><span data-stu-id="380cd-263">Format</span></span>

<span data-ttu-id="380cd-264">指定格式的11个字符的组合</span><span class="sxs-lookup"><span data-stu-id="380cd-264">An 11-character combination in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="380cd-265">模式</span><span class="sxs-lookup"><span data-stu-id="380cd-265">Pattern</span></span>

<span data-ttu-id="380cd-266">指定格式的11个字符的组合:</span><span class="sxs-lookup"><span data-stu-id="380cd-266">An 11-character combination in the specified format:</span></span>
  
-  <span data-ttu-id="380cd-267">六位数字</span><span class="sxs-lookup"><span data-stu-id="380cd-267">Six digits</span></span> 
    
- <span data-ttu-id="380cd-268">以下任一实例:</span><span class="sxs-lookup"><span data-stu-id="380cd-268">One instance of one of the following:</span></span>
    
  - <span data-ttu-id="380cd-269">加号符号</span><span class="sxs-lookup"><span data-stu-id="380cd-269">Plus symbol</span></span>
    
  - <span data-ttu-id="380cd-270">负号</span><span class="sxs-lookup"><span data-stu-id="380cd-270">Minus symbol</span></span>
    
  - <span data-ttu-id="380cd-271">字母 "A" (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="380cd-271">The letter "A" (not case-sensitive)</span></span>
    
- <span data-ttu-id="380cd-272">三位数字</span><span class="sxs-lookup"><span data-stu-id="380cd-272">Three digits</span></span>
    
- <span data-ttu-id="380cd-273">一个字母或一个数字</span><span class="sxs-lookup"><span data-stu-id="380cd-273">One letter or one digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="380cd-274">校验和</span><span class="sxs-lookup"><span data-stu-id="380cd-274">Checksum</span></span>

<span data-ttu-id="380cd-275">是</span><span class="sxs-lookup"><span data-stu-id="380cd-275">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="380cd-276">定义</span><span class="sxs-lookup"><span data-stu-id="380cd-276">Definition</span></span>

<span data-ttu-id="380cd-277">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="380cd-277">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="380cd-278">函数`Func_finland_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="380cd-278">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="380cd-279">找到了中`Keywords_finland_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="380cd-279">A keyword from  `Keywords_finland_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="380cd-280">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="380cd-280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="380cd-281">函数`Func_finland_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="380cd-281">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="380cd-282">关键字</span><span class="sxs-lookup"><span data-stu-id="380cd-282">Keywords</span></span>

#### <a name="keywordsfinlandeussnorequivalent"></a><span data-ttu-id="380cd-283">Keywords_finland_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="380cd-283">Keywords_finland_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="380cd-284">identification number</span><span class="sxs-lookup"><span data-stu-id="380cd-284">identification number</span></span>
  
<span data-ttu-id="380cd-285">个人 id</span><span class="sxs-lookup"><span data-stu-id="380cd-285">personal id</span></span>
  
<span data-ttu-id="380cd-286">标识号码</span><span class="sxs-lookup"><span data-stu-id="380cd-286">identity number</span></span>
  
<span data-ttu-id="380cd-287">芬兰国家/地区 id 号</span><span class="sxs-lookup"><span data-stu-id="380cd-287">finnish national id number</span></span>
  
<span data-ttu-id="380cd-288">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="380cd-288">personalidnumber#</span></span>
  
<span data-ttu-id="380cd-289">national identification number</span><span class="sxs-lookup"><span data-stu-id="380cd-289">national identification number</span></span>
  
<span data-ttu-id="380cd-290">id 号</span><span class="sxs-lookup"><span data-stu-id="380cd-290">id number</span></span>
  
<span data-ttu-id="380cd-291">国家/地区 id 编号。</span><span class="sxs-lookup"><span data-stu-id="380cd-291">national id no.</span></span>
  
<span data-ttu-id="380cd-292">国家/地区 id 号</span><span class="sxs-lookup"><span data-stu-id="380cd-292">national id number</span></span>
  
<span data-ttu-id="380cd-293">id 号</span><span class="sxs-lookup"><span data-stu-id="380cd-293">id no</span></span>
  
<span data-ttu-id="380cd-294">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="380cd-294">tunnistenumero</span></span>
  
<span data-ttu-id="380cd-295">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="380cd-295">henkilötunnus</span></span>
  
<span data-ttu-id="380cd-296">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="380cd-296">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="380cd-297">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="380cd-297">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="380cd-298">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="380cd-298">identiteetti numero</span></span>
  
<span data-ttu-id="380cd-299">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="380cd-299">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="380cd-300">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="380cd-300">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="380cd-301">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="380cd-301">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="380cd-302">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="380cd-302">tunnusnumero</span></span>
  
<span data-ttu-id="380cd-303">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="380cd-303">kansallinen tunnus numero</span></span>
  
<span data-ttu-id="380cd-304">hetu</span><span class="sxs-lookup"><span data-stu-id="380cd-304">hetu</span></span>
  
## <a name="france"></a><span data-ttu-id="380cd-305">法国</span><span class="sxs-lookup"><span data-stu-id="380cd-305">France</span></span>

<span data-ttu-id="380cd-306">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "华北社会安全号码 (INSEE)" 一节。</span><span class="sxs-lookup"><span data-stu-id="380cd-306">For details, see the section "France Social Security Number (INSEE)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="380cd-307">德国</span><span class="sxs-lookup"><span data-stu-id="380cd-307">Germany</span></span>

<span data-ttu-id="380cd-308">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "德国身份证号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="380cd-308">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="380cd-309">希腊</span><span class="sxs-lookup"><span data-stu-id="380cd-309">Greece</span></span>

<span data-ttu-id="380cd-310">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "希腊国家 ID 卡" 一节。</span><span class="sxs-lookup"><span data-stu-id="380cd-310">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="380cd-311">匈牙利</span><span class="sxs-lookup"><span data-stu-id="380cd-311">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="380cd-312">Format</span><span class="sxs-lookup"><span data-stu-id="380cd-312">Format</span></span>

<span data-ttu-id="380cd-313">9个数字, 不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="380cd-313">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="380cd-314">模式</span><span class="sxs-lookup"><span data-stu-id="380cd-314">Pattern</span></span>

<span data-ttu-id="380cd-315">九个数字</span><span class="sxs-lookup"><span data-stu-id="380cd-315">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="380cd-316">校验和</span><span class="sxs-lookup"><span data-stu-id="380cd-316">Checksum</span></span>

<span data-ttu-id="380cd-317">是</span><span class="sxs-lookup"><span data-stu-id="380cd-317">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="380cd-318">定义</span><span class="sxs-lookup"><span data-stu-id="380cd-318">Definition</span></span>

<span data-ttu-id="380cd-319">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="380cd-319">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="380cd-320">函数`Func_hungary_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="380cd-320">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="380cd-321">找到了中`Keywords_hungary_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="380cd-321">A keyword from  `Keywords_hungary_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="380cd-322">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="380cd-322">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="380cd-323">函数`Func_hungary_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="380cd-323">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="380cd-324">关键字</span><span class="sxs-lookup"><span data-stu-id="380cd-324">Keywords</span></span>

#### <a name="keywordshungaryeussnorequivalent"></a><span data-ttu-id="380cd-325">Keywords_hungary_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="380cd-325">Keywords_hungary_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="380cd-326">匈牙利语社会安全号码</span><span class="sxs-lookup"><span data-stu-id="380cd-326">hungarian social security number</span></span>
  
<span data-ttu-id="380cd-327">social security number</span><span class="sxs-lookup"><span data-stu-id="380cd-327">social security number</span></span>
  
<span data-ttu-id="380cd-328">socialsecuritynumber #</span><span class="sxs-lookup"><span data-stu-id="380cd-328">socialsecuritynumber#</span></span>
  
<span data-ttu-id="380cd-329">hssn #</span><span class="sxs-lookup"><span data-stu-id="380cd-329">hssn#</span></span>
  
<span data-ttu-id="380cd-330">socialsecuritynno</span><span class="sxs-lookup"><span data-stu-id="380cd-330">socialsecuritynno</span></span>
  
<span data-ttu-id="380cd-331">hssn</span><span class="sxs-lookup"><span data-stu-id="380cd-331">hssn</span></span>
  
<span data-ttu-id="380cd-332">taj</span><span class="sxs-lookup"><span data-stu-id="380cd-332">taj</span></span>
  
<span data-ttu-id="380cd-333">taj #</span><span class="sxs-lookup"><span data-stu-id="380cd-333">taj#</span></span>
  
<span data-ttu-id="380cd-334">ssn</span><span class="sxs-lookup"><span data-stu-id="380cd-334">ssn</span></span>
  
<span data-ttu-id="380cd-335">ssn</span><span class="sxs-lookup"><span data-stu-id="380cd-335">ssn#</span></span>
  
<span data-ttu-id="380cd-336">社会保障号</span><span class="sxs-lookup"><span data-stu-id="380cd-336">social security no</span></span>
  
<span data-ttu-id="380cd-337">áfa</span><span class="sxs-lookup"><span data-stu-id="380cd-337">áfa</span></span>
  
<span data-ttu-id="380cd-338">közösségi adószám</span><span class="sxs-lookup"><span data-stu-id="380cd-338">közösségi adószám</span></span>
  
<span data-ttu-id="380cd-339">általános forgalmi adó szám</span><span class="sxs-lookup"><span data-stu-id="380cd-339">általános forgalmi adó szám</span></span>
  
<span data-ttu-id="380cd-340">hozzáadottérték adó</span><span class="sxs-lookup"><span data-stu-id="380cd-340">hozzáadottérték adó</span></span>
  
<span data-ttu-id="380cd-341">áfa szám</span><span class="sxs-lookup"><span data-stu-id="380cd-341">áfa szám</span></span>
  
<span data-ttu-id="380cd-342">magyar áfa szám</span><span class="sxs-lookup"><span data-stu-id="380cd-342">magyar áfa szám</span></span>
  
## <a name="portugal"></a><span data-ttu-id="380cd-343">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="380cd-343">Portugal</span></span>

<span data-ttu-id="380cd-344">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "葡萄牙公民卡片号" 部分。</span><span class="sxs-lookup"><span data-stu-id="380cd-344">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="spain"></a><span data-ttu-id="380cd-345">西班牙</span><span class="sxs-lookup"><span data-stu-id="380cd-345">Spain</span></span>

<span data-ttu-id="380cd-346">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "西班牙社会安全号码 (SSN)" 一节。</span><span class="sxs-lookup"><span data-stu-id="380cd-346">For details, see the section "Spain Social Security Number (SSN)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="sweden"></a><span data-ttu-id="380cd-347">瑞典</span><span class="sxs-lookup"><span data-stu-id="380cd-347">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="380cd-348">Format</span><span class="sxs-lookup"><span data-stu-id="380cd-348">Format</span></span>

<span data-ttu-id="380cd-349">12个数字, 不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="380cd-349">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="380cd-350">模式</span><span class="sxs-lookup"><span data-stu-id="380cd-350">Pattern</span></span>

<span data-ttu-id="380cd-351">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="380cd-351">12 digits:</span></span>
  
-  <span data-ttu-id="380cd-352">与出生日期对应的8位数字 (YYYYMMDD)</span><span class="sxs-lookup"><span data-stu-id="380cd-352">Eight digits that correspond to the birth date (YYYYMMDD)</span></span> 
    
- <span data-ttu-id="380cd-353">与序列号对应的三个数字, 其中:</span><span class="sxs-lookup"><span data-stu-id="380cd-353">Three digits that correspond to a serial number where:</span></span> 
    
  - <span data-ttu-id="380cd-354">序列号中的最后一个数字指示在为 "男" 分配一个奇数号码时的性别, 以及一个 "女" 的偶数号码。</span><span class="sxs-lookup"><span data-stu-id="380cd-354">The last digit in the serial number indicates gender by the assignment of an odd number for male and an even number for female</span></span>
    
  - <span data-ttu-id="380cd-355">最多 1990, 将序列号 corresponded 分配给在其中, 号码持有者出生或 (如果在1947之前出生) 的县 (根据纳税记录, 在年1月1日, 使用特殊代码 (通常为第七个数字) 的特殊代码 (通常为9号)immigrants</span><span class="sxs-lookup"><span data-stu-id="380cd-355">Up to 1990, the assignment of serial number corresponded to the county where the bearer of the number was born or (if born before 1947) where he/she had been living, according to tax records, on January 1, 1947, with a special code (usually 9 as the 7th digit) for immigrants</span></span> 
    
- <span data-ttu-id="380cd-356">一个校验位</span><span class="sxs-lookup"><span data-stu-id="380cd-356">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="380cd-357">校验和</span><span class="sxs-lookup"><span data-stu-id="380cd-357">Checksum</span></span>

<span data-ttu-id="380cd-358">是</span><span class="sxs-lookup"><span data-stu-id="380cd-358">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="380cd-359">定义</span><span class="sxs-lookup"><span data-stu-id="380cd-359">Definition</span></span>

<span data-ttu-id="380cd-360">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="380cd-360">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="380cd-361">函数`Func_sweden_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="380cd-361">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="380cd-362">找到了中`Keywords_sweden_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="380cd-362">A keyword from  `Keywords_sweden_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="380cd-363">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="380cd-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="380cd-364">函数`Func_sweden_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="380cd-364">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="380cd-365">关键字</span><span class="sxs-lookup"><span data-stu-id="380cd-365">Keywords</span></span>

#### <a name="keywordsswedeneussnorequivalent"></a><span data-ttu-id="380cd-366">Keywords_sweden_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="380cd-366">Keywords_sweden_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="380cd-367">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="380cd-367">personal id number</span></span>
  
<span data-ttu-id="380cd-368">identification number</span><span class="sxs-lookup"><span data-stu-id="380cd-368">identification number</span></span>
  
<span data-ttu-id="380cd-369">个人 id 否</span><span class="sxs-lookup"><span data-stu-id="380cd-369">personal id no</span></span>
  
<span data-ttu-id="380cd-370">identity no</span><span class="sxs-lookup"><span data-stu-id="380cd-370">identity no</span></span>
  
<span data-ttu-id="380cd-371">标识否</span><span class="sxs-lookup"><span data-stu-id="380cd-371">identification no</span></span>
  
<span data-ttu-id="380cd-372">个人标识编号</span><span class="sxs-lookup"><span data-stu-id="380cd-372">personal identification no</span></span>
  
<span data-ttu-id="380cd-373">personnummer id</span><span class="sxs-lookup"><span data-stu-id="380cd-373">personnummer id</span></span>
  
<span data-ttu-id="380cd-374">personligt id-nummer</span><span class="sxs-lookup"><span data-stu-id="380cd-374">personligt id-nummer</span></span>
  
<span data-ttu-id="380cd-375">unikt id-nummer</span><span class="sxs-lookup"><span data-stu-id="380cd-375">unikt id-nummer</span></span>
  
<span data-ttu-id="380cd-376">personnummer</span><span class="sxs-lookup"><span data-stu-id="380cd-376">personnummer</span></span>
  
<span data-ttu-id="380cd-377">identifikationsnumret</span><span class="sxs-lookup"><span data-stu-id="380cd-377">identifikationsnumret</span></span>
  
<span data-ttu-id="380cd-378">personnummer #</span><span class="sxs-lookup"><span data-stu-id="380cd-378">personnummer#</span></span>
  
<span data-ttu-id="380cd-379">identifikationsnumret #</span><span class="sxs-lookup"><span data-stu-id="380cd-379">identifikationsnumret#</span></span>
  
## <a name="see-also"></a><span data-ttu-id="380cd-380">另请参阅</span><span class="sxs-lookup"><span data-stu-id="380cd-380">See also</span></span>

[<span data-ttu-id="380cd-381">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="380cd-381">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

